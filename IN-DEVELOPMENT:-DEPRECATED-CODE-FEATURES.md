#
**The following code features been determined to be deprecated. They are no longer maintained and will be removed from the code six months (too soon? should it be 12 months?) from the date given below.**

_**If you have concerns about these planned code deprecations, please begin a conversation at the [CICE Community Forum](https://xenforo.cgd.ucar.edu/cesm/forums/cice-consortium.146/).**_

## 

Date:  11 March 2020

By:  A. DuVivier

## 
**Upwind advection:**
* The upwind advection horizontal transport is less accurate than the incremental remapping scheme.
* [Namelist option set in _dynamics_nml_](https://cice-consortium-cice.readthedocs.io/en/master/user_guide/ug_case_settings.html#table-of-namelist-options): advection = upwind
* [Documentation](https://cice-consortium-cice.readthedocs.io/en/master/science_guide/sg_horiztrans.html)

**CESM Melt Ponds:**
* The CESM melt pond scheme is less sophisticated than the level-ice or deformed-ice schemes.
* [Namelist option set in _tracer_nml_](https://cice-consortium-cice.readthedocs.io/en/master/user_guide/ug_case_settings.html#table-of-namelist-options): tr_pond_cesm = true
* [Documentation](https://cice-consortium-cice.readthedocs.io/en/master/science_guide/sg_tracers.html#tracers)

**Delta Function ITD remapping:**
* Having a single delta step for an ITD category is less sophisticated than the linear remapping approximation.
* [Namelist option set in _thermo_nml_](https://cice-consortium-cice.readthedocs.io/en/master/user_guide/ug_case_settings.html#table-of-namelist-options): kitd = 0
* [Documentation](https://cice-consortium-icepack.readthedocs.io/en/master/science_guide/sg_itd.html#ice-thickness-distribution)

**Old Ridging Participation and Redistribution:**
* REASONING??.
* [Namelist option set in _dynamics_nml_](https://cice-consortium-cice.readthedocs.io/en/master/user_guide/ug_case_settings.html#table-of-namelist-options): krdg_partic = 0  and krdg_redist = 0
* [Documentation](https://cice-consortium-cice.readthedocs.io/en/master/user_guide/ug_implementation.html#choosing-an-appropriate-time-step)

