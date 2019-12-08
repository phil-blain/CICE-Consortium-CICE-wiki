# Important changes to the code on the master branch since the last numbered release
 
## 

Date of last update:  8 December 2019

By:  E. Hunke

[Last numbered release](https://github.com/CICE-Consortium/CICE/releases): CICE 6.0.2 (Oct 16, 2019)

## 

This release includes a major new physics parameterization in Icepack, the joint thickness and floe size distribution (FSD) of L. Roach and colleagues, and a new directory structure for drivers used in host models, especially NUOPC caps.   

We continue to work toward an interface for Icepack that is flexible, extensive and easy to maintain, so that future Icepack upgrades minimize the amount of changes required in host models.  Toward that goal, this release includes changes to the interface that are not backwards compatible, which are detailed in the Icepack v1.2 release notes.

**Major changes:**

* Add the joint thickness and floe size distribution (FSD) [#382](https://github.com/CICE-Consortium/CICE/pull/382) 
* Rearrange the driver directory to accommodate NUOPC caps [#376](https://github.com/CICE-Consortium/CICE/pull/376) [#377](https://github.com/CICE-Consortium/CICE/pull/377) [#383](https://github.com/CICE-Consortium/CICE/pull/383)

**Enhancements:**

* Update Icepack version [#379](https://github.com/CICE-Consortium/CICE/pull/379)  **_CHECK THAT IS THE CORRECT PR REF_**
* Update Icepack interface calls to use keywords [#378](https://github.com/CICE-Consortium/CICE/pull/378)
and to be consistent with recent refactoring of the interface (see [Icepack #285](https://github.com/CICE-Consortium/Icepack/pull/285)) [#379](https://github.com/CICE-Consortium/CICE/pull/379)
* Improve automation of test reporting and Zenodo links [#370](https://github.com/CICE-Consortium/CICE/pull/370)
* Improve method for launching serial runs [#369](https://github.com/CICE-Consortium/CICE/pull/369)

**Bug fixes:**

* Use dyrect in box test [#361](https://github.com/CICE-Consortium/CICE/pull/361)
* Correct calculation of ANGLET [#377](https://github.com/CICE-Consortium/CICE/pull/377) (affects coupled fields)