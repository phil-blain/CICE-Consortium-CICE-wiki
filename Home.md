# **Welcome to the [CICE](https://github.com/CICE-Consortium/CICE) wiki!**

*This page is under construction, as is the code, documentation, and testing infrastructure*

This repository contains the CICE sea ice numerical model starting with version 6.  
Prior versions can be found in the [CICE-svn-trunk repository](https://github.com/CICE-Consortium/CICE-svn-trunk) and tarballs are provided for each release.

The column physics portion of the code, 'Icepack', is kept in a separate [repository](https://github.com/CICE-Consortium/Icepack). CICE includes Icepack as a git submodule. The rest of the CICE model, including infrastructure and the dynamical core but not Icepack, is contained in the CICE repository as 'CICEcore'.   

## Release Notes  
Code documentation is included within each code repository, and links to data and other information can be found on the wiki pages of each repository.  
   
Release information from CICE versions prior to version 6 is contained in the [Release Notes](https://github.com/CICE-Consortium/CICE-svn-trunk/releases) links from the [CICE-svn-trunk repository](https://github.com/CICE-Consortium/CICE-svn-trunk).

## Documentation
PDF and HTML versions of [CICE Documentation](https://readthedocs.org/projects/cice-consortium-cice/) hosted at readthedocs.org.

The [CICE Documentation wiki page](https://github.com/CICE-Consortium/CICE/wiki/CICE-Documentation) details the information available about CICE and how to modify the documentation during code development. 
   
[CICE Git Workflow Guidance](https://github.com/CICE-Consortium/About-Us/wiki/Git-Workflow-Guidance) (includes instructions for working with Icepack)

The [About-Us repository](https://github.com/CICE-Consortium/About-Us) and [wiki](https://github.com/CICE-Consortium/About-Us/wiki) contain additional information, including contact information and instructions for code developers.

The [FAQ](https://github.com/CICE-Consortium/About-Us/wiki/FAQ) includes questions about both CICE and Icepack.

## Porting

To port CICE to your machine, you will need to do the following:
1.  Install external software.
+ a Fortran compiler
+ netcdf version 3.6.3 (optional but recommended)
+ gnuplot ??? (for visualization of test results)
2.  Download CICE.  We recommend using github to interact with the Consortium; other download options are listed in the [README.md](https://github.com/CICE-Consortium/CICE/blob/master/README.md) file.
+ fork the CICE and Icepack repositories
+ clone the code as described in the [Git Workflow Guidance](https://github.com/CICE-Consortium/About-Us/wiki/Git-Workflow-Guidance)
3.  Prepare env.machine, Macros.machine and the cice.run.setup.csh script, if they do not already exist for your machine, as described in the ["Quick Start"](https://cice-consortium.github.io/CICE/cice_2_quick_start.html) section.
4. Download and untar the [gx3 forcing data](https://github.com/CICE-Consortium/CICE/wiki/Testing-CICE) to the location defined in the scripts (ICE_MACHINE_INPUTDATA in the env file), for basic testing.

## Testing
Additional information can be found on the wiki's [Testing page](https://github.com/CICE-Consortium/CICE/wiki/Testing-CICE). Specific instructions for setting up standard tests (e.g. regression, restart) are in the 
[Testing](https://cice-consortium.github.io/CICE/cice_7_testing.html) subsection of the documentation.

The near-surface data required for testing CICE is available. More information about how to download these data and test CICE can be found on the [Testing CICE](https://github.com/CICE-Consortium/CICE/wiki/Testing-CICE) wiki page. 

## CICE Community Discussion
A community [bulletin board](https://bb.cgd.ucar.edu/forums/cice-consortium-model-development) has been set up for the CICE-Consortium community to discuss model development including bugs, diagnostics, and future directions. There are subforums for discussion of particular topics (e.g. repository questions) as well as a general forum. These forums will be monitored by consortium members but are open to the general community. To start or respond to a discussion topic users will need to create an account by clicking the "Login" button at the top of the page and then following the directions under "Create new account."
