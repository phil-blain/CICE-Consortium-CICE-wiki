# Important changes to the code on the master branch since the last numbered release
 
## 

Date of last update:  11 October 2019

By:  T. Craig

[Last numbered release](https://github.com/CICE-Consortium/CICE/releases): CICE 6.0.1 (July 25, 2019)

## 

**Major changes:**

* add JRA55 forcing capability [#350](https://github.com/CICE-Consortium/CICE/pull/350) and add forcing data on the ftp input data site

**Enhancements:**

* update icepack to version 1.1.2 [#368](https://github.com/CICE-Consortium/CICE/pull/368)
* update revp [#331](https://github.com/CICE-Consortium/CICE/pull/331). Change stress initialization to previous time step for revp, to be up-to-date with literature.
* update local solar time computation [#323](https://github.com/CICE-Consortium/CICE/pull/323)
* add method to determine model depths based on a pop grid file for fast ice [#367](https://github.com/CICE-Consortium/CICE/pull/367)
* code cleanup
  * update boxslotcyl advection test to use icepack parameters [#358](https://github.com/CICE-Consortium/CICE/pull/358)
  * code cleanup based on nag compiler output [#361](https://github.com/CICE-Consortium/CICE/pull/361)
  * unify MPI interface access [#365](https://github.com/CICE-Consortium/CICE/pull/365)
  * combine 3 modules in ice_dyn_evp_1d to 1 module and rename interfaces to meet coding standard [#367](https://github.com/CICE-Consortium/CICE/pull/367)
* scripts
  * add optional machine limit settings on total pe counts and batch wall times [#349](https://github.com/CICE-Consortium/CICE/pull/349).  
  * minor update to qc test validation [#337](https://github.com/CICE-Consortium/CICE/pull/337)
  * update qc post-process plotting capabilities [#355](https://github.com/CICE-Consortium/CICE/pull/355)
  * update timeseries plotting tools, add a python version with additional capabilities [#345](https://github.com/CICE-Consortium/CICE/pull/345)
* build system
  * add circular dependency checks in the build scripts [#336](https://github.com/CICE-Consortium/CICE/pull/336)
  * refresh and improve build system including new targets and new features [#354](https://github.com/CICE-Consortium/CICE/pull/336)
* update machines
  * add limits to brooks machine [#351](https://github.com/CICE-Consortium/CICE/pull/351)
  * travis xenial update [#338](https://github.com/CICE-Consortium/CICE/pull/338)
  * cori upgrade  [#339](https://github.com/CICE-Consortium/CICE/pull/339)
  * cheyenne upgrade [#341](https://github.com/CICE-Consortium/CICE/pull/341)
  * badger upgrade [#351](https://github.com/CICE-Consortium/CICE/pull/351)
  * port to izumi [#356](https://github.com/CICE-Consortium/CICE/pull/356)
* update documentation

**Bug fixes:**
