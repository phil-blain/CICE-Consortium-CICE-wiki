[Online and searchable documentation of the current version of CICE](https://cice-consortium.github.io/CICE/)

["Quick Start"](https://cice-consortium.github.io/CICE/cice_2_quick_start.html) subsection of documentation

To port CICE to your machine for testing, you will need to do the following:
1.  Install external software
+ a Fortran compiler
+ netcdf version 3.6.3 (optional but recommended)
+ gnuplot ??? (for visualization of test results)
2.  Download CICE.  We recommend using github to interact with the Consortium; other download options are listed in the [README.md](https://github.com/CICE-Consortium/CICE/blob/master/README.md) file.
+ fork the CICE and Icepack repositories
+ clone the code as described in the [CICE Git and Workflow Guide](https://docs.google.com/document/d/1rR6WAvZQT9iAMUp-m_HZ06AUCCI19mguFialsMCYs9o)
3.  Prepare env.machine, Macros.machine and the cice.run.setup.csh script, if they do not already exist for your machine, as described in the ["Quick Start"](https://cice-consortium.github.io/CICE/cice_2_quick_start.html) section
4. Download and untar the [gx3 forcing data](https://github.com/CICE-Consortium/CICE/wiki/Testing-CICE) to the location defined in the scripts (ICE_MACHINE_INPUTDATA in the env file)


