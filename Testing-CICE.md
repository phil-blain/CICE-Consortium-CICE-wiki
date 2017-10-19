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

An example of how testing data is organized follows. We recommend setting up a similar path structure. You will need to set up your own inputdata path, but the organization of directories below that should follow the structure below and should automatically unpack as so from the *.tar.gz files off the ftp site.

inputdata = '/glade/p/cesm/pcwg_dev/'

   $inputdata'/CICE_data/'

       forcing/

         gx1/COREII/

            4XDAILY/

               u_10*.data

               v_10*.data

               q_10*.dat

               t_10*.dat

            MONTHLY/

               cldf.omip.dat

               prec.nmyr.dat

         gx3/NCAR_bulk/

            4XDAILY/

               u_10.1997.data

               v_10.1997.data

               q_10.1997.dat

               t_10.1997.dat

               dn10.1997.dat

            MONTHLY/

               cldf.1997.dat

               prec.1997.dat

               swdn.1997.dat

       grid/

          gx1/

             grid_gx1.bin

             kmt_gx1.bin

          gx3/

             grid_gx3.bin

             kmt_gx3.bin

             grid_gx3.nc

             kmt_gx3.nc

       ic/

          gx1/
   
             iced_gx1_v5.nc

          gx3/

            iced_gx3_v5.nc


## Test results
(links)