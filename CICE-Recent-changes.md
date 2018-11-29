# Important changes to the code on the master branch since the last numbered release

     Date of last update:  28 Nov 2018
     By:  E. Hunke
     Last numbered version:  CICE 6.0.0.alpha  

This page includes changes to the CICE dycore ("cicecore"), scripts and test cases since CICE 6.0.0.alpha.  Other changes since the release of CICE v5.1.2 can be found on prior release pages for CICE and Icepack:      
https://github.com/CICE-Consortium/CICE/releases       
https://github.com/CICE-Consortium/Icepack/releases      
CICE v6.0.0 is released with Icepack v1.1.0.

Major changes:
- Update icepack [#163](https://github.com/CICE-Consortium/CICE/pull/163) [#188](https://github.com/CICE-Consortium/CICE/pull/188) [#223](https://github.com/CICE-Consortium/CICE/pull/223) [#250](https://github.com/CICE-Consortium/CICE/pull/250)
- Add CMIP6 support [#191](https://github.com/CICE-Consortium/CICE/pull/191) [#195](https://github.com/CICE-Consortium/CICE/pull/195)
- Add dynamic allocation [#194](https://github.com/CICE-Consortium/CICE/pull/194)
- Move tracer pre-processing information to namelist [#196](https://github.com/CICE-Consortium/CICE/pull/196)
- Add tripole grid and test [#201](https://github.com/CICE-Consortium/CICE/pull/201)
- Add bathymetry files for testing landfast ice [#222](https://github.com/CICE-Consortium/CICE/pull/222)
- Revise rEVP [#229](https://github.com/CICE-Consortium/CICE/pull/229) [#226](https://github.com/CICE-Consortium/CICE/pull/226)
- Refactor tracer initialization to take advantage of dynamic allocation [#235](https://github.com/CICE-Consortium/CICE/pull/235)
- Set EVP subcycling ndte=240 (increased from 120) [#250](https://github.com/CICE-Consortium/CICE/pull/250)

Enhancements:
- Travis CI [#111](https://github.com/CICE-Consortium/CICE/pull/111)
- Update documentation 
- Enhance machine support [#120](https://github.com/CICE-Consortium/CICE/pull/120)
[#125](https://github.com/CICE-Consortium/CICE/pull/125)
[#153](https://github.com/CICE-Consortium/CICE/pull/153)
[#220](https://github.com/CICE-Consortium/CICE/pull/220)
- Add queue information to scripts [#143](https://github.com/CICE-Consortium/CICE/pull/143)
[#147](https://github.com/CICE-Consortium/CICE/pull/147)
- Add version number in netcdf output [#121](https://github.com/CICE-Consortium/CICE/pull/121)
- Increase test coverage [#129](https://github.com/CICE-Consortium/CICE/pull/129)
- Implement box model tests [#151](https://github.com/CICE-Consortium/CICE/pull/151)
- Support coupling in RASM [#152](https://github.com/CICE-Consortium/CICE/pull/152) [#253](https://github.com/CICE-Consortium/CICE/pull/253)
- Rename some variables and subroutines [#158](https://github.com/CICE-Consortium/CICE/pull/158)
- Test the QC testing process [#167](https://github.com/CICE-Consortium/CICE/pull/167)
- Add subname to each routine, for diagnostics [#173](https://github.com/CICE-Consortium/CICE/pull/173)
- Move emissivity into namelist [#176](https://github.com/CICE-Consortium/CICE/pull/176)
- Clean up dummy and unused variables [#180](https://github.com/CICE-Consortium/CICE/pull/180)
- Add output variables for vector speed/direction quantities (ice, atm, ocn) [#199](https://github.com/CICE-Consortium/CICE/pull/199)
- Compare log files in addition to restart files for regression tests [#202](https://github.com/CICE-Consortium/CICE/pull/202)
- Change namelist flags, settings for consistency with Icepack [#208](https://github.com/CICE-Consortium/CICE/pull/208)
- Clarify test output [#209](https://github.com/CICE-Consortium/CICE/pull/209)
- Enhance scripts [#215](https://github.com/CICE-Consortium/CICE/pull/215)
- Move k1 to namelist [#220](https://github.com/CICE-Consortium/CICE/pull/220)
- Add HYCOM forcing for DMI [#230](https://github.com/CICE-Consortium/CICE/pull/230)
- Consolidate BGC namelist flags and clean up initialization [#240](https://github.com/CICE-Consortium/CICE/pull/240)
- Improved EAP efficiency [#257](https://github.com/CICE-Consortium/CICE/pull/257)

Bug fixes:
- Handle effective sample size > 30 in QC script [#108](https://github.com/CICE-Consortium/CICE/pull/108)
- Comment out non-thread-safe threading [#111](https://github.com/CICE-Consortium/CICE/pull/111)
- Fix QC false failures and update per Roberts et al 2018 [#145](https://github.com/CICE-Consortium/CICE/pull/145)
[#161](https://github.com/CICE-Consortium/CICE/pull/161)
- Broadcast calendar fields [#146](https://github.com/CICE-Consortium/CICE/pull/146)
- Fix binary restarts [#148](https://github.com/CICE-Consortium/CICE/pull/148)
- Mask restoring variables by land [#149](https://github.com/CICE-Consortium/CICE/pull/149)
- Fix failing tests [#163](https://github.com/CICE-Consortium/CICE/pull/163)
- Fix units for trsig in history output [#198](https://github.com/CICE-Consortium/CICE/pull/198)
- Correct parameter k1 for basal grounding scheme [#206](https://github.com/CICE-Consortium/CICE/pull/206)
- Debug zbgc [#207](https://github.com/CICE-Consortium/CICE/pull/207)
- Fix threading problem for dfresh, dfsalt [#228](https://github.com/CICE-Consortium/CICE/pull/228)
- Fix array-out-of-bounds in EAP [#257](https://github.com/CICE-Consortium/CICE/pull/257)




[Previous numbered release](https://github.com/CICE-Consortium/CICE/releases) 