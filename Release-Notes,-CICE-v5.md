# New Features in CICE 5.0 #

### physics ###
 * A method for prognosing sea ice salinity, including improved snow-ice formation
 * Two new explicit melt pond parameterizations (topo and level-ice)
 * Sea ice biogeochemistry
 * Elastic-Anisotropic-Plastic rheology
 * Improved parameterization of form drag 
 * The "revised EVP" under-damping approach
 * Gracefully handles the case when an internal layer melts completely

### infrastructure ### 
 * Ice and snow enthalpy defined as tracers
 * Gregorian calendar with leap years
 * Reduced memory and floating-point operations for tracer calculations
 * Restarts in binary, netCDF or PIO formats
 * CPP options for categories, layers and tracers 
 * Read/write variables on the extended grid, including ghost (halo) cells

### efficiency ###
 * Parallelism option via OpenMP threads
 * Improved parallel efficiency through halo masks and new block distributions
 * Parallel I/O option via the PIO library

### miscellaneous ###
 * New history variables for melt ponds, ridging diagnostics, biogeochemistry and more
 * Corrected bugs, particularly for nonstandard configurations.

## CICE version 5.0.1 ##

* Corrections for restarts on extended grids and restart file conversions from CICE version 4.1
* New Macro and log files for ORNL machines

## CICE version 5.0.2 ##

* Removed limitation to swabs for thin snow layers from cesm (old) shortwave option (return to CICE version 4.1 behavior).

## CICE version 5.0.3 ##

Improved efficiency of writing (serial) restart files:

* allow only master_task to define a serial netcdf restart file 
* remove unnecessary restart_format conditionals
* fuse master_task conditionals
* set MPI barriers for global gathers and scatters, wrapped with new cpp flag

## CICE version 5.0.4 ##

Bug fix for mushy thermodynamics in brackish seas: 

To get the initial ice salinity when new ice forms, a fixed amount of 3 ppt 
was subtracted from the sea surface salinity (SSS), causing negative ice 
salinities when SSS < 3 ppt.  This fix keeps the same 3 ppt reduction in 
salinity for all SSS > 6 ppt, but it makes the initial sea ice salinity go 
to 0 continuously (and differentiably) as SSS approaches 0. We also added 
an arbitrary -0.1 C upper limit to the new ice temperature. 

# New Features in CICE 5.1 #

### physics ###

 * include uice, vice in atm-ice coupling updates (e.g. stress) for high frequency coupling
 * variable coefficient for ice-ocean heat flux

### new namelist options ###

 * ''gridcpl_file'' allows ice coupling on different grid than computation (default off with no impact)
 * ''bfbflag'' controls bit-for-bit global sums for global_sum_dbl and global_sum_prod_dbl 
 * ''natmiter'' for the number of iterations used in the atmo boundary layer routine. 
 * ''highfreq'' for high-frequency coupling
 * additional ''grid_type='regional' '' (for RASM)
 * ''fbot_xfer_type'' allows variable coefficient for ice-ocean heat flux
 * ''l_mpond_fresh'' turns fresh water flux from topo ponds on/off
 * ''tfrz_option'' for ocean freezing temperature
 * ''kalg'' for algae influence on delta Eddington radiation
 * ''Cf'' for frictional dissipation during mechanical deformation
 * flags for additional output in history

### bug fixes ###

 * vertical thermo:  fix error abort messages
 * BL99 thermo:  base temperature convergence check on 0 rather than puny
 * mushy thermo:  correct double accounting of snow ice formation in coupling variables
 * mushy thermo:  correct snow ice formation energy for nslyr > 1
 * level-ice ponds:  fix dhlid for surface inversions
 * level-ice ponds:  remove snowinfil option (default = ON)
 * level-ice ponds:  do not reset dhs when restarting
 * topo ponds:  limit snow fraction based on pond fraction
 * topo ponds:  use category temperatures instead of average temperature
 * topo ponds:  alter lid growth calculation
 * topo ponds:  set limits for pond area, depth to avoid divide-by-zero
 * topo ponds:  abort if brine salinity = 0
 * delta Eddington radiation:  initialize AOPs within ij loop
 * delta Eddington ponds: use consistent array indices
 * evp:  update stress tensor halos on the tripole grid
 * formdrag:  calculate coefficients for ice cover fraction greater than 0.001
 * formdrag:  remove extra ice-area multiplicative factors
 * formdrag:  do not allow ridge height to be less than freeboard, or keel depth to be less than draft
 * transport:  change indices from real to integer kind
 * mechanical redistribution: correct volume of snow lost in leads for nslyr > 1
 * zbgc:  rearrange namelist read commands for NAG compiler
 * OpenMP:  fix OMP directives
 * history:  fix sice attributes for netCDF
 * pio:  now works (in CESM only)
 * spacecurve:  fix decomposition
 * initialization:  aggregate all tracers upon restart initialization
 * initialization:  indxi, indxj in ice_ocean.F90 and ice_step.F90
 * initialization:  set level ice fraction = 1 when not restarting
 * initialization:  update halos before aggregating when not restarting
 * initialization:  set nonzero Cdn_atm 
 * initialization:  supply location and type information when reading tracer restart fields
 * restarts:  fix restart_dir default setting
 * array-out-of-bounds error:  alter conditionals in mpi/ice_boundary.F90
 * array-out-of-bounds error:  wrap eice_init in l_conservation_check conditional
 * array-out-of-bounds error:  make flux_bio optional
 * array-out-of-bounds error:  calculate vice_init only if l_conservation_check=T
 * divide-by-zero error:  avoid compiler complaints when nblyr=0 and vertical bgc grid is not used

### other software enhancements ###

 * more flexible mpicom setting, fully backwards compatible
 * make ''nml_filename'' size 32 chars instead of 6.
 * add tr_pond_cesm check
 * add force_restart_now flag to allow external (CESM) to force a restart as needed
 * add check in ice distribution if number of blocks is too small
 * update missing value in netcdf output
 * refactor rad_to_deg conversion in history output for consistency and parallelism
 * modify history fields setting for histfreq field, more flexible and robust.
 * modify history fields f_ checking: move away from first char ''x'' limitation, more flexible.
 * history variables are now managed internally first by stream, then by variable
 * make time2sec public in ice_calendar
 * minor fix to order of ''call calendar'' in the v4 restart file subroutine
 * make orbital variables public
 * add bit-for-bit global sums for global_sum_dbl and global_sum_prod_dbl  (''bfbflag'') 
 * add ''grid_type='regional' ''
 * add ''uninit'' debugging flag
 * modify some save and intent statements
 * refactor enthalpy adjustment in layers for improved efficiency
 * open binary files for direct-access reading and writing on the extended grid
 * allow topo ponds to be used without the delta Eddington radiation scheme (''heat_capacity=F, calc_Tsfc=F'')

### diagnostics and documentation ###

 * limit redistribution diagnostics to category 1
 * save full area, volume redistribution diagnostics instead of fractions
 * add age diagnostics
 * add total number of blocks diagnostic at initialization
 * add history fields (''vsnon, alvdf, alidf, fswint_ai, keffn_top, blkmask, uatm, vatm, fsensn_ai,'' 3D and 4D dimensions)
 * add ''io_flavor'' attribute to distinguish PIO from regular netcdf output
 * more specific title in netcdf files
 * ''print_points_state'' subroutine for explicit point diagnostics only
 * add sums to min, max diagnostics
 * turn on diagnostics when reading restart files
 * add doc/PDF/CMHB_IJHPCA2014.pdf
 * update cicedoc.pdf

### changes specific to modeling centers ###

_Hadley Centre_

 * correct ORCA grid size when using restart_ext
 * add cpp wrappers
 * add specific communicators
 * keep all blocks, including all-land blocks
 * fill ghost cells of all-land blocks with special values, on the extended grid

_CESM/RASM_

 * ''CCSMCOUPLED'' ifdef replaces ''CCSM'' and ''SEQ_MCT'' 
 * add ''coszen'' restart field
 * update abort process for CESM
 * add rpointer files
 * add output file naming convention
 * multiple instance support
 * support gregorian calendar in orbital settings
 * update cesm prescribed ice
 * CESM initialization needs
 * use different value of ''isec'' for CESM
 * modify ice-atm-ocean coupling (''Uref'') for CESM
 * add ''nextsw_cday'' for CESM use
 * add driver/cesm/
 * update Macros and run file for yellowstone
 * additional ''grid_type='regional' '' for RASM
 * adjust time for year_init
 * avoid certain grid-related code for prescribed-ice mode

## CICE version 5.1.1 ##

This version contains an error and should not be used.

## CICE version 5.1.2 ##

Bug fix for melt pond flushing in mushy thermodynamics:

The flushing velocity w had the wrong sign.  This changes the
answers.
