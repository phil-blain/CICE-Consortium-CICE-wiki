[Online and searchable documentation of the current version of CICE](https://cice-consortium.github.io/CICE/)

["Quick Start"](https://cice-consortium.github.io/CICE/cice_2_quick_start.html) subsection of documentation

To port CICE to your machine for testing, you will need to do the following:
1.  Install external software
+ a Fortran compiler
+ netcdf version 3.6.3 (optional but recommended)
+ gnuplot ??? (for visualization of test results)
2.  Download CICE
+ fork the CICE and Icepack repositories
+ clone the code as described in the [CICE Git and Workflow Guide](https://docs.google.com/document/d/1rR6WAvZQT9iAMUp-m_HZ06AUCCI19mguFialsMCYs9o)
3.  Prepare the scripts and data, if they do not already exist for your machine
+ cd to scripts/machines/ in a local branch of your CICE fork
+ copy existing env.machine and Macros.machine files to new names for your new machine
+ edit the env and Macros files
+ cd to scripts/
+ edit the cice.run.setup.csh script to add a section for your machine for the batch settings and for the job launch settings
+ download and untar the [gx3 forcing data](https://github.com/CICE-Consortium/CICE/wiki/Testing-CICE) to the location defined by ICE_MACHINE_INPUTDATA in the env file
+ create a file in your home directory called .cice_proj and add your preferred account name to the first line.

You can now create a case and test.  If there are problems, you can manually edit the env, Macros, and cice.run files in the case directory until things are working properly.  Then you can copy the env and Macros files back to scripts/machines/.  Manually modify the cice.run.setup.csh script if any changes are needed there.
