## Forcing Data

Data files for testing CICE and that were included with code distributions from the svn repository are too large to be kept on github. The near surface data required for testing CICE can be found at the anonymous FTP site paths listed below. Details about each dataset follow the FTP paths.

Specific instructions for setting up standard tests (e.g. regression, restart) are in the User's Guide section of the documentation.

#### _File Availability:_

File name | size | download link | wiki description |
----|:---:|:---:|:---:|
| **Grid and IC files** | (25M) | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_ic_grid.tar.gz) | [link](https://github.com/CICE-Consortium/CICE/wiki/CICE-Input-Data/#grid-files-and-initial-conditions) |
| **gx1 *monthly* forcing data** | (32M) | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_MONTHLY.tar.gz) | [link](https://github.com/CICE-Consortium/CICE/wiki/CICE-Input-Data/#gx1-forcing-data) |
| **gx1 2005 *4x and 8x daily* forcing data** | (11G) | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2005.tar.gz) | [link](https://github.com/CICE-Consortium/CICE/wiki/CICE-Input-Data/#gx1-forcing-data) |
| **gx1 2006 *4x and 8x daily* forcing data** | (11G) | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2006.tar.gz) | [link](https://github.com/CICE-Consortium/CICE/wiki/CICE-Input-Data/#gx1-forcing-data) |
| **gx1 2007 *4x and 8x daily* forcing data** | (11G) | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2007.tar.gz) | [link](https://github.com/CICE-Consortium/CICE/wiki/CICE-Input-Data/#gx1-forcing-data) |
| **gx1 2008 *4x and 8x daily* forcing data** | (11G) | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2008.tar.gz) | [link](https://github.com/CICE-Consortium/CICE/wiki/CICE-Input-Data/#gx1-forcing-data) |
| **gx1 2009 *4x and 8x daily* forcing data** | (11G) | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx1_2009.tar.gz) | [link](https://github.com/CICE-Consortium/CICE/wiki/CICE-Input-Data/#gx1-forcing-data) |
| **gx3 *all* forcing data** | (4.1G) | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_forcing_gx3_all.tar.gz) | [link](https://github.com/CICE-Consortium/CICE/wiki/CICE-Input-Data/#gx1-forcing-data) |

A link to the newly added or updated forcing files is found [below](https://github.com/CICE-Consortium/CICE/wiki/CICE-Input-Data#updated-files).


### _**grid files and initial conditions:**_

Initial conditions, grid, and kmt files are provided for each of the two grids (gx1 and gx3). We also provide grid and kmt files for the tripole grid (tx1). 

### _**gx1 forcing data:**_

Five years (2005-2009) of forcing data are available from the FTP from two sources. 

1) COREII (Large and Yeager 2009) forcing files are 4x daily data by year for the following near surface fields: Zonal Wind (u_10), Meridional Wind (v_10), 10m Specific Humidity (q_10), and 10m Temperature (t_10). The monthly cloud forcing (cldf) and precipitation (prec) climatological fields are separate.

   _Large, W.G. and S.G. Yeager (2009).The global climatology of an interannually varying air-sea flux data set. Climate Dynamics, 33, 341-364. https://doi.org/10.1007/s00382-008-0441-3_

2) JRA55 forcing (Tsujino et. al 2018) files are 8x daily data by year with the following fields: X-ward wind (wndewd), Y-ward wind (wndnwd), Specific Humidity (spchmd), Air Temperature (airtmp), Total Precipitation (ttlpcp), Downward Surface Longwave (dlwsfc), and Downward Surface Shortwave (glbrad). As a result, there is no need for monthly files or cloud fraction when using the JRA55 forcing.

   **If you publish a paper using the JRA55 dataset *please* be sure to cite this paper.** _Tsujino, H., Urakawa, S., Nakano, H., Small, R. J., Kim, W. M., Yeager, S. G., et al. (2018). JRA‐55 based surface dataset for driving ocean–sea‐ice models (JRA55‐do). Ocean Modelling. https://doi.org/10.1016/j.ocemod.2018.07.002_ 

#### _**Additional Years:**_

If more than 5 years of gx1 forcing data are required for your work, information and instructions about how users can generate 50 years of forcing data can also be found at ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/gx1_50yr_scrip.tar.gz. These data will not be arranged in the directory structure described below and the user is responsible for arranging files appropriately.  The Consortium recommends against using the stand-alone configuration for scientific studies.  See the [FAQ](https://github.com/CICE-Consortium/About-Us/wiki/FAQ-(Frequently-Asked-Questions)#stand-alone-configuration-and-forcing).

### _**gx3 forcing data:**_

Forcing data are available from the FTP from three sources. 

1) NCAR_bulk forcing files are are available for one year (1997). These include 4x daily data for near surface fields (u_10, v_10, q_10, t_10, dn_10) as well as monthly cloud forcing, precipitation, and shortwave down radiation fields. 

2) JRA55 forcing (Tsujino et. al 2018) files are 8x daily data by year with the following fields: X-ward wind (wndewd), Y-ward wind (wndnwd), Specific Humidity (spchmd), Air Temperature (airtmp), Total Precipitation (ttlpcp), Downward Surface Longwave (dlwsfc), and Downward Surface Shortwave (glbrad). As a result, there is no need for monthly files or cloud fraction when using the JRA55 forcing.

   **If you publish a paper using the JRA55 dataset *please* be sure to cite this paper.** _Tsujino, H., Urakawa, S., Nakano, H., Small, R. J., Kim, W. M., Yeager, S. G., et al. (2018). JRA‐55 based surface dataset for driving ocean–sea‐ice models (JRA55‐do). Ocean Modelling. https://doi.org/10.1016/j.ocemod.2018.07.002_ 

3) Wave Watch 3 (WW3) surface ocean wave spectral forcing necessary for the floe size distribution.

## Updated Files
Users needing just the new files (detailed below) can download just these updated files here: ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/CICE_data_new.tar.gz . 

A list of file updates or additions is shown below and will be updated with new additions. After 6 months the files will be incorporated in the full data files an no longer considered "new". Users will be responsible for downloading and extracting the new files.

### List of new files and date added to ftp tarballs
* _March 2020_: 

```
inputdata = '/glade/p/cesm/pcwg_dev/'   
   CICE_data/forcing/gx3
     JRA55/8XDAILY/
        JRA55_gx3_03hr_forcing_2005.nc
        JRA55_gx3_03hr_forcing_2006.nc
        JRA55_gx3_03hr_forcing_2007.nc 
        JRA55_gx3_03hr_forcing_2008.nc 
        JRA55_gx3_03hr_forcing_2009.nc
     ww3.20100101_efreq_remapgx3.nc
```

We have adopted a convention of appending any new files with `_yyyymmdd` for the date the file was created to better track any file updates or additions. 

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
            JRA55/
               8XDAILY/
                  JRA55_03hr_forcing_2005.nc
                  JRA55_03hr_forcing_2006.nc
                  JRA55_03hr_forcing_2007.nc
                  JRA55_03hr_forcing_2008.nc
                  JRA55_03hr_forcing_2009.nc
            WOA/
               MONTHLY/
                  nitrate_climatologyWOA_gx1v6f_20150107.nc
                  silicate_climatologyWOA_gx1v6f_20150107.nc
         gx3/
            ww3.20100101_efreq_remapgx3.nc
            NCAR_bulk/
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
            JRA55/
               8XDAILY/
                  JRA55_gx3_03hr_forcing_2005.nc
                  JRA55_gx3_03hr_forcing_2006.nc
                  JRA55_gx3_03hr_forcing_2007.nc
                  JRA55_gx3_03hr_forcing_2008.nc
                  JRA55_gx3_03hr_forcing_2009.nc
       grid/
          gx1/
             grid_gx1.bin
             kmt_gx1.bin
             global_gx1.bathy.nc
          gx3/
             grid_gx3.bin
             kmt_gx3.bin
             grid_gx3.nc
             kmt_gx3.nc
             global_gx3.bathy.nc
          tx1/
             grid_tx1.bin
             kmt_tx1.bin
       ic/
          gx1/
             iced_gx1_v5.nc
          gx3/
            iced_gx3_v5.nc
```

## _**FTP from the command line:**_

To access these files from the command line instead of the URLs listed above::

*    $ ftp ftp.cgd.ucar.edu
*    $ Name: [anonymous]
*    $ Password: [user's email address]
*    $ cd /archive/Model-Data/CICE/

Then use standard ftp commands to obtain the relevant files from these subdirectories.