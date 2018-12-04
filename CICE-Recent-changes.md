# Important changes to the code on the master branch since the last numbered release

     Date of last update:  3 Dec 2018
     By:  E. Hunke
     Last numbered version:  CICE 6.0.0.alpha  

CICE version 6.0.0 is released with Icepack version 1.1.0. Icepack contains the column physics within CICE, first released as an independent software package in February 2018. Because the code refactoring associated with Icepack introduced significant differences with the previous CICE release (v5.1.2), we created an “alpha” version of CICE v6 in March 2018 while enhancements for the full v6 release were completed.

Since the v6.0.0.alpha release, we updated Icepack to version 1.1.0, implemented dynamic allocation for most arrays, enhanced all rheology options (EVP, rEVP, EAP), simplified the initialization procedure for tracers, added support for CMIP6 history output, improved the quality control and compliance tests, added new test configurations to the test suites, and automated basic testing using Travis CI. This release also includes many other improvements since version 5.1.2, most notably a new landfast-ice parameterization with tensile strength, and full vertical biogeochemistry with shortwave feedback on sea ice physics. The source code and forcing data directories have been restructured to allow extensions for other sea ice model components, and we implemented a flexible, extensible, robust interface between Icepack and the sea ice model driver. The code, scripts, development procedures and tasks/issues are documented online, and automated test reporting is available.

Major changes:

* Update icepack #163 #188 #223 #250 #262
* Add CMIP6 support #191 #195
* Add dynamic allocation #194
* Move tracer pre-processing information to namelist #196
* Add tripole grid and test #201
* Add bathymetry files for testing landfast ice #222
* Revise rEVP #229 #226
* Refactor tracer initialization to take advantage of dynamic allocation #235
* Set EVP subcycling ndte=240 (increased from 120) #250

Enhancements:

* Travis CI #111
* Enhance machine support #120 #125 #153 #220 #261
* Add queue information to scripts #143 #147
* Add version number in netcdf output #121
* Increase test coverage #129
* Implement box model tests #151 #254
* Support coupling in RASM #152 #253
* Rename some variables and subroutines #158
* Test the QC testing process #167
* Add subname to each routine, for diagnostics #173
* Move emissivity into namelist #176
* Clean up dummy and unused variables #180
* Add output variables for vector speed/direction quantities (ice, atm, ocn) #199
* Compare log files in addition to restart files for regression tests #202
* Change namelist flags, settings for consistency with Icepack #208
* Clarify test output #209
* Enhance scripts #215
* Move k1 to namelist #220
* Add HYCOM forcing for DMI #230
* Consolidate BGC namelist flags and clean up initialization #240
* Improve EAP efficiency #257
* Update documentation

Bug fixes:

* Handle effective sample size > 30 in QC script #108
* Comment out non-thread-safe threading #111
* Fix QC false failures and update per Roberts et al 2018 #145 #161
* Broadcast calendar fields #146
* Fix binary restarts #148
* Mask restoring variables by land #149
* Fix failing tests #163
* Fix units for trsig in history output #198
* Correct parameter k1 for basal grounding scheme #206
* Debug zbgc #207
* Fix threading problem for dfresh, dfsalt #228
* Fix array-out-of-bounds in EAP #257


[Previous numbered release](https://github.com/CICE-Consortium/CICE/releases) 