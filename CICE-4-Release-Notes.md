_Release notes for CICE versions 4.0 and 4.1_

# CICE 4.0 #

## Changes through revision r168 ##

### Summary: ###

Arrays associated with tracers on ice and snow volume (_depend, _type) were not initialized or 
updated properly.  In particular, init_transport needs to be called after
init_state in CICE_InitMod.F90.  These changes affect only the ice age 
tracer.  

Using zero instead of puny for some volume-tracer transport 
calculations improves conservation and monotonicity.  This 
changes the answers.

The variables meltb, congel, etc., have been strictly diagnostic, but now are 
needed for further parameterization development, such as melt ponds and 
biogeochemistry.  They were merged within the thermodynamics module, which 
meant that the category values were not available.  They are now available 
via the argument lists and merged along with all the other 
category fluxes.   Results are bit-for-bit the same as before.

Changes to 'save' statements in ice_grid.F90 fix a case in which grid 
lengths were being lost in certain grid cells along the lower boundary.  

In the case of closed boundaries, check blocks only along the grid edges, not in the interior.  We recommend that everyone use ns_boundary_type='open' with a row of land cells along grid edges that need to be closed.  The 'closed' option is intended for testing only.

Separate albedo components (ice, snow, melt ponds) have been added to the history 
output, along with the cosine of the zenith angle.  These components were 
buried in the Delta Eddington code and so a number of changes had to be made 
to several modules. 

In the Delta Eddington shortwave formulation, dx_exp should not be used (it was left over from the old "approximate exponential" lookup table's indexing method).  This bug prevented most (dEdd) radiation from penetrating into the ice, and none passed through to the ocean.   Now it is possible that more shortwave penetrates into an ice layer than is needed to completely melt the layer, or else it causes the computed temperature to be greater than the melting temperature, which causes the vertical thermodynamics code to abort.  A limiting scheme had been implemented for this problem but was not working correctly; it has now been fixed.  A parameter 'frac' sets the fraction of the ice layer than can be melted through; currently it is set to 1-puny, to minimize the limiting, but it may need to be made smaller.  A minimum temperature difference for absorption of radiation is also set, currently dTemp=0.01 (K).  The limiting occurs in ice_therm_vertical.F90, for both the default and Delta Eddington radiation schemes.  It changes the answers in the default configuration slightly, and it is necessary for dEdd to run at all.  Also in the Delta Eddington code, the "special case of night to day" limiting, left over from earlier incarnations, is no longer necessary and has been removed.

An "Interpretation of albedos" subsection has been added to the Troubleshooting section of the documentation.

### Overview of file changes since r145 (initial tag) ###

_some minor changes are not listed here_

drivers/*/CICE_InitMod.F90
 * call init_transport after init_state 

drivers/*/CICE_RunMod.F90
 * add albedo components (ice, snow, ponds) and counter for history output
 * use category thickness changes rather than merged quantities
 * remove melt pond temporary variables

drivers/cice4/CICE_RunMod.F90_debug
 * brought up to date

source/ice_transport_driver.F90
 * use correct dependencies for ice volume tracers (affects only ice age tracer)
 * moved diagnostic inside category loop

source/ice_transport_remap.F90
 * use c0 instead of puny for tracer calculations to improve conservation/monotonicity 

source/ice_therm_vertical.F90
 * send category thickness changes in argument list rather than merging it
 * properly limit penetrating shortwave

source/ice_flux.F90 
 * include thickness changes in merge_fluxes subroutine
 * add albedo components (ice, snow, ponds) and counter 

source/ice_grid.F90
 * save individual variables rather than doing a catch-all save at the top of the module

source/ice_domain.F90
 * check land mask in the case of closed boundaries only along the grid edges

source/ice_shortwave.F90
 * added albedo components (ice, snow, ponds) for history output
 * use proper albedo values in constant_albedos
 * remove "special case of night to day" for dEdd
 * remove some unused variables
 * remove dx_exp everywhere that it appears

source/ice_step_mod.F90
 * add albedo components (ice, snow, ponds) for history output
 * remove "special case of night to day" for dEdd
 * change loops over max_blocks to nblocks

source/ice_history.F90
input_templates/gx1/ice_in
input_templates/gx3/ice_in
 * add albedo components (ice, snow, ponds) and coszen 

source/ice_dyn_evp.F90
 * use double precision special value for diagnostic principal stresses

source/ice_diagnostics.F90
 * change loops over max_blocks to nblocks
 * use latitude when locating print_points diagnostics

doc/cicedoc.pdf
 * added "Interpretation of albedos" subsection to Troubleshooting

# CICE 4.1 # 

## Changes through revision r277 ##

Added an alternative parameterization for ice conductivity suggested by Pringle et al. (JGR 2007) and tuned the gx1 configuration to improve the ice thickness simulation.  These changes involved several parameters now in namelist, including the ice thickness above which bare ice albedo is constant, a flag for the conductivity parameterization, a parameter that determines the ridged ice thickness distribution, and the minimum friction velocity for oceanic heat flux to the underside of the ice.  A manuscript submitted to Ocean Modelling entitled "Sea Ice Thickness Sensitivities" documents these changes (contact E. Hunke).  

Implemented two tracers for tracking the ridged ice area and volume.  The actual tracers are for level (undeformed) ice area and volume, which are much easier to implement.  Ice that is not level is recognized as ridged.  Both level ice and ridged ice are offered as history output. 

Added a column configuration.  Because of the boundary conditions and other spatial assumptions in the model, this is not a single column, but a small array of columns (minimum grid size is 5x5).  However, only the single, central column is used (all other columns are designated as land). 

The history module has been generalized to allow output at different frequencies.  Five output frequencies ('1', 'h', 'd', 'm', 'y') are available simultaneously during a run.   The same variable can be output at different frequencies (say daily and monthly) via its f_<variable> string in namelist.  
Variables with a third and/or fourth dimension (i.e., vertical; categories) are also available for output in the history files.

Reduced work and memory needed for multiple tracers.  Originally the number of tracers was fixed, but in CICE version 4 some tracers may be turned off at runtime.  Arrays and loops have been reduced to the size needed only for active tracers. 

Added an alternative "T-fold" tripole grid option.  The tripole option in CICE 4.0 is for "U-fold" grids.  

Corrected bugs, particularly for nonstandard configurations (for example, nghost=2).

Except for the albedo diagnostic output, results are bit-for-bit identical to those from the previous release when using the same parameter set (conduct='MU71', ahmax=0.5, mu_rdg=4, ustar_min=0.05).   Some of these parameters have changed in the new, default ice_in files (for gx1 and col configurations, not for gx3).  In particular, ustar_min was much too large and has been reduced to 0.0005 m/s.  Now, ahmax=0.3 m corresponds with the World Meteorological Organization's definition of white ice.

### physics ###
 * Added tracers for tracking the ridged ice area and volume
 * Tuned the gx1 configuration to improve the ice thickness simulation  
   (namelist parameters: conduct, ahmax, mu_rdg, ustar_min)
 * Added option for Pringle et al (2007) conductivity

### infrastructure ###
 * Simplified and corrected some index calculations for neighbor blocks
 * Generalized indices for mapping data to ghost cells when nghost>1
 * Increment and count tracers during initialization instead of hardwiring them
 * Arrays and loops have been reduced to the size needed only for active tracers
 * Added new, alternative "T-fold" tripole grid option
 * Implemented an alternative method for averaging points along the tripole grid cut
 * Added column configuration
 * Moved several hardwired parameters into namelist
### diagnostics ###
 * The history module has been generalized to allow output at different frequencies and for additional dimensions
 * Use 'ppt' to denote salinity units instead of 'psu'
 * Call ice_write_hist initially only if write_ic is true
 * Corrected albedo weights used in diagnostics
 * Corrected indices in diagnostic routine quasilocal_max_min

### bug fixes ### 
 * Match order of operations for derived grid quantities to prevent round-off differences along the tripole grid cut.
 * Use 0 instead of puny for conditional to load tracer array, for conservation
 * Limit call to atmospheric boundary layer calculation by icells
 * Correct calendar for 360-day years.
 * Correct field_loc and field_type in some subroutine calls 
 * Declare subroutine argument ns outside of netcdf ifdef in routine icecdf 
 * Remove ustar_scale
 * Remove continuation from declaration statement in ice_flux.F90