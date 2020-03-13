# Important changes to the code on the master branch since the last numbered release
 
## 

Date of last update:  13 March 2020

By:  T. Craig

[Last numbered release](https://github.com/CICE-Consortium/CICE/releases): CICE 6.1.0 (Dec 9, 2019)

## 

**Major changes:**

**Bug fixes:**
* Correct logic for floe size distribution wave_spec_type (changes answers for fsd12 option) [#394](https://github.com/CICE-Consortium/CICE/pull/394)
* Fix threading in macros files for some machines [#396](https://github.com/CICE-Consortium/CICE/pull/396)
* Change order of operations in albedo calculation for restart consistency [#414](https://github.com/CICE-Consortium/CICE/pull/414), does not change answers in standard test cases


**Enhancements:**
* Use MPI module instead of Fortran include statement [#389](https://github.com/CICE-Consortium/CICE/pull/389)
* Update wave_spec_frac filename handling, namelist input now specifies path and filename [#417](https://github.com/CICE-Consortium/CICE/pull/417)
* Add conda environment to run on personal computers [#393](https://github.com/CICE-Consortium/CICE/pull/393) [#400](https://github.com/CICE-Consortium/CICE/pull/400) [#402](https://github.com/CICE-Consortium/CICE/pull/402)
* Update run status output based on diag_type setting [#396](https://github.com/CICE-Consortium/CICE/pull/396)
* Update machines/compilers [#401](https://github.com/CICE-Consortium/CICE/pull/401), [#416](https://github.com/CICE-Consortium/CICE/pull/416)
* Generalize cice.setup script to allow setup-only, setup+build, setup+build+run and setup+build+submit [#395](https://github.com/CICE-Consortium/CICE/pull/395) and fix bug introduced by the upgrade [#406](https://github.com/CICE-Consortium/CICE/pull/406)
* Update ice_open to use 8-byte integers [#410](https://github.com/CICE-Consortium/CICE/pull/410)
* Update Icepack version [#409](https://github.com/CICE-Consortium/CICE/pull/409), [#414](https://github.com/CICE-Consortium/CICE/pull/414), [#416](https://github.com/CICE-Consortium/CICE/pull/416), [#417](https://github.com/CICE-Consortium/CICE/pull/417)

**Documentation**
* Add html anchors when reporting results [#388](https://github.com/CICE-Consortium/CICE/pull/388)
* Update community bulletin board/forum links [#391](https://github.com/CICE-Consortium/CICE/pull/391)
* Add information for contributing [#392](https://github.com/CICE-Consortium/CICE/pull/392)
* Update documentation [#397](https://github.com/CICE-Consortium/CICE/pull/397) [#400](https://github.com/CICE-Consortium/CICE/pull/400)
* Update copyright and internal version number [#409](https://github.com/CICE-Consortium/CICE/pull/409)