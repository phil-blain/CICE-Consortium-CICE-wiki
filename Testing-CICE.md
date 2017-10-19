Instructions for setting up standard tests (e.g. regression, restart) are in the 
[Testing](https://cice-consortium.github.io/CICE/cice_7_testing.html) subsection of the documentation.

## Forcing Data

The near surface data required for testing CICE can be found at the following anonymous FTP site. The directory structure for CICE data is described below. gx1 and gx3 directories include the grid files as well as near surface wind (u,v), temperature (t), and moisture (q) forcing fields. Climatological cloud and precipitation forcing fields are available under "Additional testing data." Note that the user will need to extract the data from the *tar.gz files.

_**All data:**_

All available forcing, initial condition, and grid data for both resolutions (gx1 and gx3) are available here (19G): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_all.tar.gz

It is also possible to download only portions of the data for one or both grids. See below for details.

_**grid and initial conditions:**_

Initial conditions, grid, and kmt files are provided for each of the two grids (gx1 and gx3). These files are available here (24M): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_ic_grid.tar.gz

_**gx1 forcing data:**_

Five years (2005-2009) of forcing data are available. In order to make downloading more manageable, forcing files are separated into 4x daily data for near surface fields (u_10, v_10, q_10, t_10) and monthly cloud forcing and precipitation fields.

gx1 monthly data (16M): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_MONTHLY.tar.gz

gx1 4x daily data for 2005 (3.6G): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2005.tar.gz

gx1 4x daily data for 2006 (3.6G): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2006.tar.gz

gx1 4x daily data for 2007 (3.6G): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2007.tar.gz

gx1 4x daily data for 2008 (3.6G): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2008.tar.gz

gx1 4x daily data for 2009 (3.6G): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2009.tar.gz

If more than 5 years of data are required for your work, information and instructions about how users can generate 50 years of forcing data can also be found [here](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/gx1_50yr_scrip.tar.gz). These data will not be arranged in the directory structure described below and the user is responsible for arranging files appropriately.

_**gx3 forcing data:**_

One year (1997) of forcing data are available, which include 4x daily data for near surface fields (u_10, v_10, q_10, t_10, dn_10) as well as monthly cloud forcing, precipitation, and shortwave down radiation fields. All gx3 forcing data are available here (428M): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx3_all.tar.gz

_**Directory structure:**_

An example of how testing data is organized follows. We recommend setting up a similar path structure. You will need to set up your own 'inputdata' path, but the organization of directories below that should follow the structure below and should automatically unpack as so from the *.tar.gz files off the ftp site.

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


_**FTP from the command line:**_

To access these files from the command line instead of the URLs listed above:

$ ftp ftp.cgd.ucar.edu

$ Name: [anonymous]

$ Password: [user's email address]

$ cd /archive/Model-Data/CICE/

Then use standard ftp commands to obtain the relevant files from these subdirectories.


## Test results
(links)