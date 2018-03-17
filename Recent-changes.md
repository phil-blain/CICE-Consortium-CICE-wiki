# Important changes to the code since the last numbered release

     Date of last update:  17 Mar 2018
     By:  E. Hunke
     Last numbered version:  CICE v5.1.2  

Background: 

[CICE v5.1.2](https://github.com/CICE-Consortium/CICE-svn-trunk/releases/tag/cice-5.1.2) was tagged at r954 of the subversion trunk.  The last commit to the trunk was [r1134](https://github.com/CICE-Consortium/CICE-svn-trunk/commit/ac5d48162210ac021dfa2c0d9e2c43a011a84a73#diff-cdf82f1995461279ffcf99d9aeb2cf34).  All changes after that were merged into “colpkg” branches.  The rasm_colpkg branch was the starting point for what became the new github CICE repository.  [svn revision numbers not linked below were in private branches of the svn repository and later merged into the trunk.]

Major changes:

- A new fast-ice parameterization
- Full vertical biogeochemistry
- Independent column physics package [Icepack](https://github.com/CICE-Consortium/Icepack) implemented as a git submodule
- A flexible, extensible, robust interface between the column physics modules and the driver
- Restructured code and forcing data directories
- A warning package that captures diagnostic and error information from within the column physics, for printing by the driver
- An entirely new scripting system- A comprehensive test suite of various configuration options, with quality control and compliance tests
- Automated testing using Travis CI
- Automated test reporting organized by hash, version, machine and branch, for both the primary Consortium repository and user forks
- Online documentation
- See also updates in Icepack [releases](https://github.com/CICE-Consortium/Icepack/releases) and [recent changes](https://github.com/CICE-Consortium/Icepack/wiki/Recent-changes)

Enhancements:

- Change use of ULAT to TLAT to determine what latitudes initial ice is present in set_state_var [r970]
- add 4d fields (categories, vertical ice)  [r1076](https://github.com/CICE-Consortium/CICE-svn-trunk/commit/c53339b0784151ba0ec8bf50503f042ee80175aa#diff-cdf82f1995461279ffcf99d9aeb2cf34)
- Update PIO; Universal large file support [r1094]
- Remove calendar_type from namelist options and initialize it based on the namelist flag use_leap_years.  [r1098]
- Add fbot to history output [r1107]
- Add shortwave diagnostics [r1108]
- Modifications to enable ocean and ice biogeochemical coupling [r1111, r1200]
- Remove the computational overhead of coupling BGC when it is not being used [r1123]
- Change reference to char_len in stop_label [r1143]
- Add grounding scheme and tensile strength [#52](https://github.com/CICE-Consortium/CICE/pull/52)
- Add new namelist options for dynamics parameters [#52](https://github.com/CICE-Consortium/CICE/pull/52)
- Update Icepack version in CICE (Icepack v1.0.0 [#81](https://github.com/CICE-Consortium/CICE/pull/81))

Bug fixes:

- Properly read and rotate ocean currents from 3D gx1 netcdf data [r959](https://github.com/CICE-Consortium/CICE-svn-trunk/commit/223e60fd4c153e796e57d84a584a85746ca8dec8#diff-9cf44cea82e766a5d1ed6adf3f60de17)
- Correct diagnostic output 'avg salinity'  [r1022]
- Bug fix for padded domains.  [r1031](https://github.com/CICE-Consortium/CICE-svn-trunk/commit/ec741d777b7a9ddab2f40fbe86e0e034427e448b#diff-cdf82f1995461279ffcf99d9aeb2cf34)
- Use VGRD instead of VGRDi for 3D [r1037]
- change shortwave calculation to depend on the net shortwave sum instead of cosine of the zenith angle (not BFB:  in addition to the different shortwave calculation, albedo output in history is different).
[r1076](https://github.com/CICE-Consortium/CICE-svn-trunk/commit/c53339b0784151ba0ec8bf50503f042ee80175aa#diff-cdf82f1995461279ffcf99d9aeb2cf34)
- Correct available history fields. [r1082]
- Fix coupled restart bug; initialize coszen; adjust calendar_type implementation [r1094]
- Port miscellaneous changes from the various column package branches back to the trunk.  BFB in the standard configuration, but the initializations and conditional changes for coszen could change the answers in other configurations. Also the flux calculation change in ice_therm_itd.F90 could change the answers in coupled simulations.   [1102](https://github.com/CICE-Consortium/CICE-svn-trunk/commit/faa71893593ce88e6e96711d20cac5ff74cca2d8#diff-cdf82f1995461279ffcf99d9aeb2cf34)
- Ensure fractions of snow, ponds and bare ice add to one [r1120](https://github.com/CICE-Consortium/CICE-svn-trunk/commit/8052b8accac2c8895ae3c600282631332ca22b4b#diff-cdf82f1995461279ffcf99d9aeb2cf34)
- Zero out thin-pond fraction for radiation in cesm, topo pond schemes (not BFB), and set albedo=1 where/when there is no incoming shortwave (changes the average-albedo diagnostic), and fix thin (cesm) ponds overlapping snow. [r1126, r1132]
- Fix padding when using the extended-grid functionality, to prevent arrays out of bounds.  [r1128]
- Change dynamics halo update mask from icetmask to iceumask (fixes occasional exact restart problem and error in halo update) [r1133]
- Add surface flooding and surface runoff terms which increase with open water area in surface condition for update_hbrine, z_salinity, z_biogeochemistry [r1161]
- Set all tracer values to c0 over land after initialization [#16](https://github.com/CICE-Consortium/CICE/pull/16)
- Remove OpenMP directives for loops that do not appear to be thread safe [#25](https://github.com/CICE-Consortium/CICE/pull/25)
- Remove iblk from timer starts [#98](https://github.com/CICE-Consortium/CICE/pull/98)

Additional information:

Regarding logic behind the ice_therm_itd.F90 modification at revision  [1102](https://github.com/CICE-Consortium/CICE-svn-trunk/commit/faa71893593ce88e6e96711d20cac5ff74cca2d8#diff-cdf82f1995461279ffcf99d9aeb2cf34), there are two namelist 
flags in play here:
 
update_ocn_f = true if the ocean model being coupled does not assume fresh water 
and salt content of frazil ice (e.g. HadGEM, ACME); otherwise update_ocn_f = false.
 
ktherm = 2 includes the fresh water and salt content of frazil ice in its 
calculations, consistent with update_ocn_f = true, and therefore if 
update_ocn_f = false then these need to be removed from the fluxes. 
ktherm = 0 and 1 do not include fresh water and salt content in their 
calculations, and therefore if update_ocn_f = true then they need to be added.

Diagnostics also change at r 1130:
do not include frazil ice formation for the case ktherm=2 
and update_ocn_f = F, by implementing a new variable frazil_diag.  (POP 
assumes fresh water and salt fluxes due to frazil ice are not included in 
the coupling fluxes.)  Reduces errors in the water and salt diagnostics.  

[Previous numbered release](https://github.com/CICE-Consortium/CICE-svn-trunk/releases) 