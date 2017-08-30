# **Welcome to the [CICE](https://github.com/CICE-Consortium/CICE) wiki!**

*This page is under construction, as is the code, documentation, and testing infrastructure*

This repository contains the CICE sea ice numerical model starting with version 6.  
Prior versions can be found in https://github.com/CICE-Consortium/CICE-svn-trunk.

The column physics portion of the code, 'Icepack', is kept in a separate repository, https://github.com/CICE-Consortium/Icepack. CICE includes Icepack as a git submodule. The rest of the CICE model, including infrastructure and the dynamical core but not Icepack, is contained in the CICE repository as 'CICEcore'.   

## Release Notes  
Code documentation is included within each code repository, and links to data and other information can be found on the wiki pages of each repository.  
(link to html)   
[prior release info is here](http://oceans11.lanl.gov/trac/CICE/wiki/SourceCode)

## User and Developer Guides
"Quick Start" instructions are available in [README_v6](https://github.com/CICE-Consortium/CICE/blob/master/README_v6).  

[CICE User Guide](https://docs.google.com/document/d/1yQV565RFIQnny_Tj3WM45jJFdDYG-MwriU5BC6sC0Wk)
Detailed online and searchable documentation of the current version of CICE can be found at: https://cice-consortium.github.io/CICE/

[CICE Git and Workflow Guide](https://docs.google.com/document/d/1rR6WAvZQT9iAMUp-m_HZ06AUCCI19mguFialsMCYs9o)

The [About-Us repository](https://github.com/CICE-Consortium/About-Us) and [wiki](https://github.com/CICE-Consortium/About-Us/wiki) contain additional information, including contact information and instructions for code developers.

## Testing
Instructions for setting up standard tests (e.g. regression, restart) are in [README.test](https://github.com/CICE-Consortium/CICE/blob/master/README.test)

(add links to)
- larger files such as the gx1 grid, land mask, and forcing files
- testing data
- test results

The near surface data required for testing CICE can be found at the following anonymous FTP sites. The gx1 and gx3 directories include the grid files as well as near surface wind (u,v), temperature (t), and moisture (q) forcing fields. Climatological cloud and precipitation forcing fields are available under "Additional testing data." *Note that *tar.gz files will need to have the data extracted by the user.

gx1 data:
5 years (2005-2009) of data are available: ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/gx1_data/
Information and instructions about how users can generate 50 years of forcing data can also be found [here](ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/gx1_data/gx1scrip.tar.gz). 

gx3 data:
1 year (1997) of data are available: ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/gx3_data/

Additional testing data: ftp://ftp.cgd.ucar.edu/archive/Model-Data/CICE/other_files/

To access these files from the command line:
> ftp ftp.cgd.ucar.edu
> Name: [anonymous]
> Password: [user's email address]
> cd /archive/Model-Data/CICE/
Then the user can ftp the relevant files from the subdirectories.

## CICE Community Discussion
A community [bulletin board](https://bb.cgd.ucar.edu/forums/cice-consortium-model-development) has been set up for the CICE-Consortium community to discuss model development including bugs, diagnostics, and future directions. There are subforums for discussion of particular topics (e.g. repository questions) as well as a general forum. These forums will be monitored by consortium members but are open to the general community. To start or respond to a discussion topic users will need to create an account by clicking the "Login" button at the top of the page and then following the directions under "Create new account."
