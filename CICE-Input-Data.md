## Forcing Data

Data files for testing CICE and that were included with code distributions from the svn repository are too large to be kept on github. The near surface data required for testing CICE can be found at the following anonymous FTP site paths listed below. Information on newly added or updated forcing files is described [below](https://github.com/CICE-Consortium/CICE/wiki/CICE-Input-Data#updated-files).

Specific instructions for setting up standard tests (e.g. regression, restart) are in the User's Guide section of the documentation.

### _**All data:**_

All available forcing, initial condition, and grid data for both resolution grids (gx1 and gx3) are available here (19G): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_all.tar.gz

It is also possible to download only portions of the data for one or both grids. See below for details.

### _**grid files and initial conditions:**_

Initial conditions, grid, and kmt files are provided for each of the two grids (gx1 and gx3). These files are available here (24M): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_ic_grid.tar.gz

### _**gx1 forcing data:**_

Five years (2005-2009) of forcing data are available. In order to make downloading more manageable, forcing files are separated into 4x daily data by year for near surface fields (u_10, v_10, q_10, t_10). The monthly cloud forcing and precipitation climatological fields are separate.

* monthly gx1 data (32M): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_MONTHLY.tar.gz
* 4x daily gx1 data for 2005 (3.6G): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2005.tar.gz
* 4x daily gx1 data for 2006 (3.6G): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2006.tar.gz
* 4x daily gx1 data for 2007 (3.6G): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2007.tar.gz
* 4x daily gx1 data for 2008 (3.6G): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2008.tar.gz
* 4x daily gx1 data for 2009 (3.6G): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2009.tar.gz

If more than 5 years of data are required for your work, information and instructions about how users can generate 50 years of forcing data can also be found at ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/gx1_50yr_scrip.tar.gz. These data will not be arranged in the directory structure described below and the user is responsible for arranging files appropriately.

### _**gx3 forcing data:**_

One year (1997) of forcing data are available, which include 4x daily data for near surface fields (u_10, v_10, q_10, t_10, dn_10) as well as monthly cloud forcing, precipitation, and shortwave down radiation fields. 

* all gx3 forcing data for 1997 (428M): ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx3_all.tar.gz

### _**FTP from the command line:**_

To access these files from the command line instead of the URLs listed above::

*    $ ftp ftp.cgd.ucar.edu
*    $ Name: [anonymous]
*    $ Password: [user's email address]
*    $ cd /archive/Model-Data/CICE/

Then use standard ftp commands to obtain the relevant files from these subdirectories.

## Updated Files
Recently added or updated input data will be available in the complete input data download (ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_all.tar.gz). However, users needing just the new files can download just the updated files here: ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_new.tar.gz . 

A list of file updates or additions is shown below and will be updated with new additions. After 6 months the files will be incorporated in the full data files an no longer considered "new". Users will be responsible for downloading and extracting the new files.

We have adopted a convention of appending any new files with `_yyyymmdd` for the date the file was created to better track any file updates or additions. 

### List of new files and date added to ftp tarballs
* _September 2018_: CICE_data/forcing/gx1/WOA/MONTHLY/
  * nitrate_climatologyWOA_gx1v6f_20150107.nc
  * silicate_climatologyWOA_gx1v6f_20150107.nc

## Directory structure

An example of how testing data is organized follows. We recommend setting up a similar path structure. You will need to set up your own 'inputdata' path, but the organization of the CICE_data top level directory should follow the structure below and should automatically unpack as so from the ftp's *.tar.gz files. You will need to extract the data from the downloaded *tar.gz files.

If you plan to use these data for testing previous versions of CICE (V1-V5), please note that the directory structure has changed and therefore the data files will need to be moved into the proper directories for testing previous releases.

```
inputdata = '/glade/p/cesm/pcwg_dev/'   
   CICE_data/
       forcing/
         gx1/
            COREII/
               4XDAILY/
                  u_10*.data
                  v_10*.data
                  q_10*.dat
                  t_10*.dat
               MONTHLY/
                  cldf.omip.dat
                  prec.nmyr.dat
            WOA/
               MONTHLY/
                  nitrate_climatologyWOA_gx1v6f_20150107.nc
                  silicate_climatologyWOA_gx1v6f_20150107.nc
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
```