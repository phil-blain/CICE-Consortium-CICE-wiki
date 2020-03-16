# Forcing Data

Data files for testing CICE and that were included with code distributions from the svn repository are too large to be kept on github. The near surface data required for testing CICE can be found at the anonymous FTP site paths listed below. Details about each dataset follow the FTP paths.

Specific instructions for setting up standard tests (e.g. regression, restart) are in the User's Guide section of the documentation.

## _File Availability:_

File name | size | download link | status ('*' indicates active dataset) | wiki description |
----|:---:|:---:|:---:|:---:|
|**gx3 Datasets**| | | | |
| CICE gx3 grid files | 476 Kb | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/prototyping/CICE_data_gx3_grid.tar.gz) | * +9/2019, CICE6.0.2 | [link](https://github.com/CICE-Consortium/CICE/wiki/IN-DEVELOPMENT:-INPUT-DATA#jra55-forcing) |
| CICE gx3 initial condition files | 2.2 Mb | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/prototyping/CICE_data_gx3_ic.tar.gz) | * +9/2019, CICE6.0.2 | [link](https://github.com/CICE-Consortium/CICE/wiki/IN-DEVELOPMENT:-INPUT-DATA#jra55-forcing) |
| CICE gx3 JRA55 forcing files | 3.7 Gb | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/prototyping/CICE_data_gx3_forcing_JRA55.tar.gz) | * +9/2019, CICE6.0.2 | [link](https://github.com/CICE-Consortium/CICE/wiki/IN-DEVELOPMENT:-INPUT-DATA#jra55-forcing) |
| CICE gx3 NCAR_bulk forcing files | 428 Mb | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/prototyping/CICE_data_gx3_forcing_NCAR_bulk.tar.gz) | * | [link](https://github.com/CICE-Consortium/CICE/wiki/IN-DEVELOPMENT:-INPUT-DATA#ncar_bulk-forcing) |
| CICE gx3 WW3 forcing files | 2.9 Mb | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/prototyping/CICE_data_gx3_forcing_WW3.tar.gz) | * +12/2019, CICE6.1.0 | [link](https://github.com/CICE-Consortium/CICE/wiki/IN-DEVELOPMENT:-INPUT-DATA#ww3-forcing) |
|**gx1 Forcing Datasets**| | | |
| CICE gx1 grid files | 2.8 Mb | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/prototyping/CICE_data_gx1_grid.tar.gz) | * +9/2019, CICE6.0.2 | [link](https://github.com/CICE-Consortium/CICE/wiki/IN-DEVELOPMENT:-INPUT-DATA#jra55-forcing) |
| CICE gx1 initial condition files | 19 Mb | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/prototyping/CICE_data_gx1_ic.tar.gz) | * +9/2019, CICE6.0.2 | [link](https://github.com/CICE-Consortium/CICE/wiki/IN-DEVELOPMENT:-INPUT-DATA#jra55-forcing) |
| CICE gx1 JRA55 forcing files | 38 Gb | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/prototyping/CICE_data_gx1_forcing_JRA55.tar.gz) | * +3/2020, CICE6.1.1 | [link](https://github.com/CICE-Consortium/CICE/wiki/IN-DEVELOPMENT:-INPUT-DATA#jra55-forcing-1) |
| CICE gx1 COREII forcing files | 18 Gb | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/prototyping/CICE_data_gx1_forcing_COREII.tar.gz) | * | [link](https://github.com/CICE-Consortium/CICE/wiki/IN-DEVELOPMENT:-INPUT-DATA#core-ii-forcing) |
| CICE gx1 WOA forcing files | 17 Mb | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/prototyping/CICE_data_gx1_forcing_WOA.tar.gz) | * | [link](https://github.com/CICE-Consortium/CICE/wiki/IN-DEVELOPMENT:-INPUT-DATA#woa-forcing) |
|**tx1 Forcing Datasets**| | | |
| CICE tx1 grid files | 871 Kb | [File](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/prototyping/CICE_data_tx1_grid.tar.gz) | * +9/2019, CICE6.0.2 | [link](https://github.com/CICE-Consortium/CICE/wiki/IN-DEVELOPMENT:-INPUT-DATA#jra55-forcing) |

# Descriptions of Tar files
## _**gx3 datasets:**_
### _**Grid and Initial Condition files:**_
The gx3 grid is nominal three-degree resolution. Grid and kmt file are provided in the grid tar file. Initial conditions are also available.
### _**JRA55 forcing:**_
JRA55 forcing (Tsujino et. al 2018) files are 8x daily data by year with the following fields: X-ward wind (wndewd), Y-ward wind (wndnwd), Specific Humidity (spchmd), Air Temperature (airtmp), Total Precipitation (ttlpcp), Downward Surface Longwave (dlwsfc), and Downward Surface Shortwave (glbrad). As a result, there is no need for monthly files or cloud fraction when using the JRA55 forcing. Five years (2005-2009) of forcing data are available. **If you publish a paper using the JRA55 dataset *please* be sure to cite this paper.** 

_Tsujino, H., Urakawa, S., Nakano, H., Small, R. J., Kim, W. M., Yeager, S. G., et al. (2018). JRA‐55 based surface dataset for driving ocean–sea‐ice models (JRA55‐do). Ocean Modelling. https://doi.org/10.1016/j.ocemod.2018.07.002_ 

### _**NCAR_bulk forcing:**_
NCAR_bulk forcing files are are available for one year (1997). These include 4x daily data for near surface fields (u_10, v_10, q_10, t_10, dn_10) as well as monthly cloud forcing, precipitation, and shortwave down radiation fields. 

CITATION?? MORE INFO ABOUT DEPRECATION OR CODE RELEASE TO USE WITH?

### _**WW3 forcing:**_
Wave Watch 3 (WW3) surface ocean wave spectral forcing that is necessary for the floe size distribution.

MORE INFO? CITATION?

## _**gx1 datasets:**_
### _**Grid and Initial Condition files:**_
The gx1 grid is nominal one-degree resolution. Grid and kmt file are provided in the grid tar file. Initial conditions are also available.
### _**JRA55 forcing:**_
JRA55 forcing (Tsujino et. al 2018) files are 8x daily data by year with the following fields: X-ward wind (wndewd), Y-ward wind (wndnwd), Specific Humidity (spchmd), Air Temperature (airtmp), Total Precipitation (ttlpcp), Downward Surface Longwave (dlwsfc), and Downward Surface Shortwave (glbrad). As a result, there is no need for monthly files or cloud fraction when using the JRA55 forcing. Five years (2005-2009) of forcing data are available. **If you publish a paper using the JRA55 dataset *please* be sure to cite this paper.** 

   _Tsujino, H., Urakawa, S., Nakano, H., Small, R. J., Kim, W. M., Yeager, S. G., et al. (2018). JRA‐55 based surface dataset for driving ocean–sea‐ice models (JRA55‐do). Ocean Modelling. https://doi.org/10.1016/j.ocemod.2018.07.002_ 

#### _**CORE II forcing:**_
COREII (Large and Yeager 2009) forcing files are 4x daily data by year for the following near surface fields: Zonal Wind (u_10), Meridional Wind (v_10), 10m Specific Humidity (q_10), and 10m Temperature (t_10). The monthly cloud forcing (cldf) and precipitation (prec) climatological fields are separate. Five years (2005-2009) of forcing data are available.

   _Large, W.G. and S.G. Yeager (2009).The global climatology of an interannually varying air-sea flux data set. Climate Dynamics, 33, 341-364. https://doi.org/10.1007/s00382-008-0441-3_

MORE INFO ABOUT DEPRECATION OR CODE RELEASE TO USE WITH?

##### _**Additional Years:**_
If more than 5 years of gx1 forcing data are required for your work, information and instructions about how users can generate 50 years of forcing data can also be found at ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/gx1_50yr_scrip.tar.gz. These data will not be arranged in the directory structure described below and the user is responsible for arranging files appropriately.  The Consortium recommends against using the stand-alone configuration for scientific studies.  See the [FAQ](https://github.com/CICE-Consortium/About-Us/wiki/FAQ-(Frequently-Asked-Questions)#stand-alone-configuration-and-forcing).

### _**WOA forcing:**_
DETAILS HERE

## _**tx1 datasets:**_
### _**Grid files:**_
The tx3 grid is nominal one-degree resolution on a tripole grid. Grid and kmt file are provided in the grid tar file. Initial conditions are not yet available.

# Directory structure

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

# Naming standards
File names must be unique from any other files in the archive. The grid name should be included in the file name. 

New grid files or initial condition files for an existing dataset will be added to the existing grid and initial condition tar files. As stated above, new files added must have unique file names from those already included in the repository.

Existing forcing datasets will be updated only if there are errors found in the existing data. New forcing datasets will be added as an entirely new tar file with a new directory under the grid directory with which they are used.

 