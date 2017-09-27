Instructions for setting up standard tests (e.g. regression, restart) are in the 
[Testing](https://cice-consortium.github.io/CICE/cice_7_testing.html) subsection of the documentation.

## Forcing Data

The near surface data required for testing CICE can be found at the following anonymous FTP sites. The gx1 and gx3 directories include the grid files as well as near surface wind (u,v), temperature (t), and moisture (q) forcing fields. Climatological cloud and precipitation forcing fields are available under "Additional testing data." Note that the user will need to extract the data from the *tar.gz files.

_gx1 data:_

5 years (2005-2009) of data are available: ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/gx1_data/

Information and instructions about how users can generate 50 years of forcing data can also be found [here](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/gx1_50yr_generation/gx1scrip.tar.gz). 

_gx3 data:_

1 year (1997) of data are available: ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/gx3_data/

_Additional testing data:_ 

climatological cloud and precip data are available: ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/other_files/


To access these files from the command line instead of the URLs listed above:

$ ftp ftp.cgd.ucar.edu

$ Name: [anonymous]

$ Password: [user's email address]

$ cd /archive/Model-Data/CICE/

Then use standard ftp commands to obtain the relevant files from these subdirectories.

## Test results
(links)