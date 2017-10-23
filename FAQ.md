


**Q: __Enthalpy corrections__**  My diagnostics file contains a warning that the initial temperature is too warm.  The code recovers, but what is happening here?

>  Starting thermo, T > Tmax, layer           1
>  istep1, my_task, i, j, k:       49167          29           4         190           1
>  zTin = -7.658739752000057E-002 , Tmax= -7.660018851607993E-002
>  zSin =   1.41357047372424     
>  hin =   4.71848719600473     
>  zqin =  -331444.829450586     
>  qmlt=  -331500.184635007     
>  Tmlt= -7.660018851607993E-002
>  Corrected quantities
>  zqin=  -331501.184635007     
>  zTin= -7.660018876641461E-002



**A:**  In order to ensure conservation of energy and salt content, the advection routines will occasionally limit changes to either enthalpy or bulk salinity. The mushy thermodynamics routine determines temperature from both enthalpy and bulk salinity. Since the limiting changes performed in the advection routine are not applied consistently (from a mushy physics point of view) to both enthalpy and bulk salinity, the resulting temperature may be changed to be greater than the limit allowed in the thermodynamics routines. If this situation is detected, the code corrects the enthalpy so the temperature is below the limiting value. Conservation of energy is ensured by placing the excess energy in the ocean. The code also writes a warning that this has occurred to the diagnostics file, as in the example above. This situation only occurs with the mushy thermodynamics (ktherm=2) and should only occur very infrequently and have a minimal effect on results. The addition of the heat to the ocean may reduce ice formation by a small amount afterwards.

**Q: __EVP time steps__** Although the CICE documentation gives good hints how to choose the main time step dt, it is not clear to me where the ratio 1:40:120 is derived. I would be really grateful if you could give some advice how to make "the best" choice for the EVP sub-time stepping and value of E,,0,,.

**A:**  The subcycling step in EVP is really an iteration to damp out the elastic waves, which are generated every time the mass/strength changes.  The ratio, 1:40:120, is essentially the subcycling time step to the damping timescale to the full time step, the full time step being defined by when the mass, strength and surface forcing changes.  We need the damping timescale to be sufficiently shorter than the full time step so that the elastic waves CAN damp out within it, and we need the subcycling timestep sufficiently shorter than the damping timescale to actually accomplish the damping.   A choice of 1:80:240 is better in the sense that you'll damp the elastic waves more completely, but on the other hand it will be more expensive to run---the parameter choices are really a balancing act between how small the residual error is and how many computational cycles you're willing to spend to get there, as is often the case in numerical modeling.  When the ice strength P is very large, the elastic waves are larger and more difficult to damp out.  The elastic wave damping vs ice strength issues are more fully explained in this paper:

Hunke, E. C.  Viscous-Plastic Sea Ice Dynamics with the EVP Model: Linearization 
Issues. ''Journal of Computational Physics'', **170**, 18–38, 2001. 

E_0 (eyc in the code) is the ratio (damping timescale)/(full time step).  The other namelist parameter used for EVP, ndte (the number of subcycles per timestep) is an integer to ensure that the subcycling steps dte evenly divide the full timestep.

The "revised EVP" method, developed by Sylvain Bouillon et al., provides an alternative subcycling approach.  See the CICE documentation cicedoc.pdf for details, and

Bouillon, S., T. Fichefet, V. Legat, and G. Madec. The revised elastic-viscous-plastic method. ''Ocean Modelling'', submitted, 2013.

**Q: __Boundaries__**  Is there any good reason that you (now?) demand two rows (columns) of land along the boundaries?

**A:** If your land mask has at least one row of land cells along the 'closed' boundary, then you should set boundary_type to 'open' (in ice_in) and let the land mask close it.  The problem here (and the difference with version 3.14) is that the entire infrastructure of the code changed to make it like our ocean model (POP), including how the boundaries are handled, and that introduced some idiosyncrasies due to non-infrastructure-related differences between POP and CICE.   With closed boundaries and only one layer of land cells, some of the computed grid lengths along the boundary end up being zero, which causes divide-by-zero errors later in the code (these divzeroes don't appear in POP).  The 'open' option was added to get around this; we use the land mask to close the grid boundaries instead of boundary_type.  

In a way, this makes sense:  the boundary_type specifies the mathematical boundary condition along the edges of the grid (periodic, neumann, etc.), which can be useful for regional grids, while the land mask puts land where it needs to be, thereby applying a physical condition that is relatively independent of the location of the grid edges (i.e., land 'boundaries' are also in the interior of the domain).   If you have land cells along the grid edge, it doesn't matter mathematically whether the underlying boundary conditions are 'open' or 'closed'---so use 'open.'  Otherwise you'll need to add a row of land cells to your grid and land mask to avoid divzeroes.  The 'closed' option is intended only for testing purposes on small grids defined in the code without separate kmt files (grid_type='rectangular', for instance).

**Q: __Rigid ice__** I had a question regarding the implementation of your elastic-viscous-plastic (EVP) rheology in CICE, particularly in regions of rigid sea ice as I am trying to model landfast sea ice.  In your paper from 2001 (see below for detailed reference) you point out that the version of EVP as suggested there has some difficulties with rigid ice, respectively when
P / Delta becomes too large (equations (24) and (25) and text in between). You suggest that one should protect that fraction with some appropriate tuning parameter C (your equ. 25).  Looking through the documentation for CICE I don't see this parameter mentioned anywhere, and I wonder if this fraction is indeed protected in CICE.

Hunke, E. C.  Viscous-Plastic Sea Ice Dynamics with the EVP Model: Linearization 
Issues. ''Journal of Computational Physics'', **170**, 18–38, 2001. 

**A:**  Extra elastic wave damping was available through the namelist variable evp_damping in CICE versions 4.0 and 4.1 (add it to ice_in and set it to true).  The parameter 'C' in the paper is set via 'rcon' in the code (rcon=2*C*E,,0,,*dt/dte^2^).  In general this option should not be used;  in most cases the undamped elastic waves are not detrimental to the solution, as far as we know, while the extra damping can affect the solution elsewhere.    Rigid ice is the exception, of course.

The evp_damping option has been removed from CICE v5.0, due to the confusion surrounding it.  Another method, developed by Sylvain Bouillon et al., has been added.  See the CICE documentation cicedoc.pdf for details.

Bouillon, S., T. Fichefet, V. Legat, and G. Madec. The revised elastic-viscous-plastic method. ''Ocean Modelling'', submitted, 2013.

Rigid ice will be very difficult to simulate using any viscous-plastic-based model, including EVP.  The reason is that the basic, plastic model becomes singular (the viscosities become infinite) exactly when the ice becomes rigid, that is, when the strain rates become zero.  Hibler chose to regularize that singularity by making the ice highly viscous.  In EVP, the essential regularization adds elastic waves instead.  In either case, the simulated ice is not allowed to completely stop; in the VP case, the ice creeps viscously, while in the EVP case, it has elastic waves running around.  Turning on evp_damping will help reduce those elastic waves, but you will not be able to make the ice completely stop using a VP-type model, except perhaps with massive computing cycles to get the velocity below round-off. 

**Q:** Where can I find out about the MPAS framework?

**A:**  http://mpas-dev.github.io/ 