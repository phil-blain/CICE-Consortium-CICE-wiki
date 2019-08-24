# Important changes to the code on the master branch since the last numbered release
 
## 

Date of last update:  24 August 2019

By:  T. Craig

[Last numbered release](https://github.com/CICE-Consortium/CICE/releases): CICE 6.0.1 (July 25, 2019)

## 

**Major changes:**

**Enhancements:**
* add optional machine limit settings on total pe counts and batch wall times [#349](https://github.com/CICE-Consortium/CICE/pull/349).  Add limits to brooks machine [#351](https://github.com/CICE-Consortium/CICE/pull/351)
* update revp [#331](https://github.com/CICE-Consortium/CICE/pull/331). Change stress initialization to previous time step for revp, to be up-to-date with literature.
* minor update to qc test validation [#337](https://github.com/CICE-Consortium/CICE/pull/337)
* update qc post-process plotting capabilities [#355](https://github.com/CICE-Consortium/CICE/pull/355)
* update timeseries plotting tools, add a python version with additional capabilities [#345](https://github.com/CICE-Consortium/CICE/pull/345)
* add circular dependency checks in the build scripts [#336](https://github.com/CICE-Consortium/CICE/pull/336)
* update machines
  * travis xenial update [#338](https://github.com/CICE-Consortium/CICE/pull/338)
  * cori upgrade  [#339](https://github.com/CICE-Consortium/CICE/pull/339)
  * cheyenne upgrade [#341](https://github.com/CICE-Consortium/CICE/pull/341)
  * badger upgrade [#351](https://github.com/CICE-Consortium/CICE/pull/351)
* update documentation

**Bug fixes:**
