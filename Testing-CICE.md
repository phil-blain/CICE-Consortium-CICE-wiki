Instructions for setting up standard tests (e.g. regression, restart) are in the 
[Testing](https://cice-consortium.github.io/CICE/cice_7_testing.html) subsection of the documentation.

## Forcing Data

The near surface data required for testing CICE can be found at the following anonymous FTP sites. The gx1 and gx3 directories include the grid files as well as near surface wind (u,v), temperature (t), and moisture (q) forcing fields. Climatological cloud and precipitation forcing fields are available under "Additional testing data." Note that the user will need to extract the data from the *tar.gz files.

_**gx1 data:**_

5 years (2005-2009) of data are available: ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/gx1_data/

If more than 5 years of data are required for your work, information and instructions about how users can generate 50 years of forcing data can also be found [here](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/gx1_50yr_generation/gx1scrip.tar.gz). 

_**gx3 data:**_

1 year (1997) of data are available: ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/gx3_data/

_**Additional testing data:**_ 

climatological cloud and precip data are available: ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/other_files/

_**FTP from the command line:**_
To access these files from the command line instead of the URLs listed above:

$ ftp ftp.cgd.ucar.edu

$ Name: [anonymous]

$ Password: [user's email address]

$ cd /archive/Model-Data/CICE/

Then use standard ftp commands to obtain the relevant files from these subdirectories.

_**Directory structure:**_
An example of how testing data is organized follows. We recommend setting up a similar path structure.


atm_data_dir = '/glade/p/cesm/pcwg_dev/data'


   $atm_data_dir'/gx1_data/'

       grid.gx1

       kmt.gx1

       DATA/gx1v3/LargeYeager/
 
         4XDAILY/

            u_10*.data

            v_10*.data

            q_10*.dat

            t_10*.dat

         MONTHLY/

            cldf.omip.dat

            prec.nmyr.dat

   $atm_data_dir'/gx3_data/'

       grid.gx3

       kmt.gx3

       atm/gx3v2m/NCAR_bulk/
 
         ISCCPM/MONTHLY/RADFLX

            cldf.1997.dat

            swdn.1997.dat

         MXA/MONTHLY/PRECIP/

            prec.1997.dat

         NCEP/4XDAILY/STATES/

            dn10.1997.dat

            q_10.1997.dat

            t_10.1997.dat

            u_10.1997.dat

            v_10.1997.dat

## Test results
(links)