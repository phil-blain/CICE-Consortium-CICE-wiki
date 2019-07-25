# Important changes to the code on the master branch since the last numbered release
 
## 

Date of last update:  25 June 2019

By:  T. Craig

[Last numbered release](https://github.com/CICE-Consortium/CICE/releases): CICE 6.0.0 

## 

**Major changes:**
* new, vectorized EVP kernel [#278](https://github.com/CICE-Consortium/CICE/pull/278)[#318](https://github.com/CICE-Consortium/CICE/pull/318)
* refactor code to enable bit-for-bit testing [#300](https://github.com/CICE-Consortium/CICE/pull/300)

**Enhancements:**
* update grounding scheme to depths less than 30m [#325](https://github.com/CICE-Consortium/CICE/pull/325)
* add option to write restarts each timestep [#312](https://github.com/CICE-Consortium/CICE/pull/312)
* update scripts to improve robustness [#311](https://github.com/CICE-Consortium/CICE/pull/311), [#315](https://github.com/CICE-Consortium/CICE/pull/315)
* reuse test suites [#310](https://github.com/CICE-Consortium/CICE/pull/310)
* improve build [#307](https://github.com/CICE-Consortium/CICE/pull/307)
* update documentation [#271](https://github.com/CICE-Consortium/CICE/pull/271)[#321](https://github.com/CICE-Consortium/CICE/pull/321)[#324](https://github.com/CICE-Consortium/CICE/pull/324)[#326](https://github.com/CICE-Consortium/CICE/pull/326)
* machine updates [#272](https://github.com/CICE-Consortium/CICE/pull/272), [#280](https://github.com/CICE-Consortium/CICE/pull/280), [#290](https://github.com/CICE-Consortium/CICE/pull/290), [#303](https://github.com/CICE-Consortium/CICE/pull/303), [#304](https://github.com/CICE-Consortium/CICE/pull/304), [#309](https://github.com/CICE-Consortium/CICE/pull/309), [#313](https://github.com/CICE-Consortium/CICE/pull/313), [#314](https://github.com/CICE-Consortium/CICE/pull/314), [#319](https://github.com/CICE-Consortium/CICE/pull/319)
* make bulletin board more visible in online info [#276](https://github.com/CICE-Consortium/CICE/pull/276)
* commit used to test webhooks, etc [#277](https://github.com/CICE-Consortium/CICE/pull/277)
* add ability for user to set the test directory [#281](https://github.com/CICE-Consortium/CICE/pull/281)

**Bug fixes:**
* default for --bgen failed for single tests [#300](https://github.com/CICE-Consortium/CICE/pull/300)
* poll_queue.csh failed for ubuntu [#300](https://github.com/CICE-Consortium/CICE/pull/300)