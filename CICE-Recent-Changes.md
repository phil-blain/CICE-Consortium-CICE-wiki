# Important changes to the code on the master branch since the last numbered release
 
## 

Date of last update:  7 December 2019

By:  T. Craig

[Last numbered release](https://github.com/CICE-Consortium/CICE/releases): CICE 6.0.2 (Oct 16, 2019)

## 

**Major changes:**

* Add the joint thickness and floe size distribution (FSD) of L. Roach and colleagues [#382](https://github.com/CICE-Consortium/CICE/pull/382) 
* Rearrange the driver directory to accommodate NUOPC caps [#376](https://github.com/CICE-Consortium/CICE/pull/376) [#377](https://github.com/CICE-Consortium/CICE/pull/377) [#383](https://github.com/CICE-Consortium/CICE/pull/383)

**Enhancements:**

* Update Icepack interface calls to use keywords [#378](https://github.com/CICE-Consortium/CICE/pull/378)
* Update some Icepack interface calls to be consistent with recent refactoring and update some Icepack "use" statements to avoid dipping into parts of Icepack not made public by the module icepack_intfc.F90 [#379](https://github.com/CICE-Consortium/CICE/pull/379)
* Improve automation of test reporting and Zenodo links [#370](https://github.com/CICE-Consortium/CICE/pull/370)
* Improve method for launching serial runs [#369](https://github.com/CICE-Consortium/CICE/pull/369)

**Bug fixes:**

* Use dyrect in box test [#361](https://github.com/CICE-Consortium/CICE/pull/361)
* Correct calculation of ANGLET [#377](https://github.com/CICE-Consortium/CICE/pull/377) (affects coupled fields)