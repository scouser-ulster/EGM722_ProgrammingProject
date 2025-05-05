# EGM722_ProgrammingProject #
This repository is my submission for the EGM722 Programming project. This repository will be used to calculate estimated glacier area change using Landsat imagery.

# Introduction to the Repository # 
The Estimated Glacier Area Calculator is a script which provides users with an estimation of glacier area change using Landsat satellite data over a multidecadal period. 
The interactive programming notebook created using Jupyter Lab notebook aims to provide users with a quick and efficient method for calculating glacier area changes for entire mountain ranges.
The example used in the notebook is for the Kenai Mountains in Alaska between 1986 - 2024, however the script can be adapted for other mountains ranges. 
The script uses several functions from geospatial packages such as Rasterio, NumPy, and a download USGS python package (https://github.com/kapadia/usgs). 
All edits and changes to the script have been documented using commits on Github. Github was also used to fork the USGS python package to the working repository.


# Set up and Installation # 

To start the script the user needs to fork and clone the repository from Github. 
Once the user has done this, they can create a conda environment using the following environment.yaml file 

The contents of the environment.yaml is attached below:

name: EGM722_Project
channels:
  - conda-forge
  - defaults
dependencies:
  - python=3.9
  - geopandas
  - notebook
  - rasterio
  - jupyterlab
  - shapely
This module will need to be installed using pip in the conda command-line interface. 
After it has been installed to the conda environment, install it again in the usgs folder in the working directory to ensure the package’s most recent version has been installed. 
This module should be installed using pip install usgs as it cannot be installed using the conda environment

The next step is to create an account and get an Api key on the USGS’s Eros service website (https://ers.cr.usgs.gov/register/). 
After the account has been created, the user should apply for an application token so that they are authorised to use the python package (after you apply you should get access for the package almost instantly). 
Once an account has been created and an Api token has been generated for the users account, the user needs to create two separate text files containing the account username and Api token respectively.
These files will be needed in the script to use the USGS functions to collect and download the Landsat scene data.

The text files should be formatted as follows:
<Username>
<Api Token>

After the user has created the text files containing the login details for the USGS python package, edit the log in cell at the top of the script with the file path to the username and api token to use the USGS based functions in the script. 
Additionally, it is recommended if the user is planning on using their own Landsat scene data to login on the USGS EarthExplorer website (EarthExplorer) as this is the node where the Landsat scene information is stored. 
Additionally, the EarthExplorer website can be used to find cloud free imagery which can be selected for download as the python package does not include a parameter for cloud cover. 
Future adaptations may include submitting a dataset_fields query using the ‘where’ parameters to collect cloud free imagery without using the EarthExplorer website. 
However, the cloud cover key/value may not be supported in different Landsat datasets.


After, you have successfully managed to get logged in you are now ready to work through the KMGlacierAreaCalculator.ipynb script.
