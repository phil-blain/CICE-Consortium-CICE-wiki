# Important changes to the code on the master branch since the last numbered release

     Date of last update:  16 Nov 2018
     By:  E. Hunke
     Last numbered version:  CICE 6.0.0.alpha  


Major changes:
- update icepack #163, 188, 223
- Add CMIP6 support #191, 195
- Add dynamic allocation #194
- Move tracer pre-processing information to namelist #196
- Add tripole grid and test #201
- Bathymetry files for testing landfast ice #222
- Revise rEVP #229
- Refactor tracer initialization to take advantage of dynamic allocation #235

Enhancements:
- Travis CI #111
- Update documentation #102, 106, 112, 113, 126, 127, 142, 179, 192, 195, 203, 225, 227, 229, 232, 234, 236
- Enhance machine support #120, 125, 153, 187, 220
- Add queue information to scripts #143, 147
- version number in netcdf output #121
- Increase test coverage #129
- Implement box model tests #151
- Support coupling in RASM #152
- Rename some variables and subroutines #158
- Test the QC testing process #167
- Add subname to each routine, for diagnostics #173
- Move emissivity into namelist #176
- Clean up dummy and unused variables #180
- Adding output variables for vector speed/direction quantities (ice, atm, ocn) #199
- compare log files in addition to restart files for regression tests #202
- Changed namelist flags, settings for consistency with Icepack #208
- clarify test output #209
- scripts #215
- move k1 to namelist #220
- HYCOM forcing for DMI #230

Bug fixes:
- Handle effective sample size > 30 in QC script #108
- Commented out non-thread-safe threading #111
- Fix QC false failures and update per Roberts et al 2018 #145, 161
- Broadcast calendar fields #146
- Binary restarts
- Mask restoring variables by land
- fix failing tests #163
- fix units for trsig in history output #198
- corrected parameter k1 for basal grounding scheme #206
- Debug zbgc #207
- Fix threading problem for dfresh, dfsalt #228




[Previous numbered release](https://github.com/CICE-Consortium/CICE/releases) 