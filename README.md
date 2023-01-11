# mdi-workshop

## Sections

- [Folders and repo structure](#Folders-and-repo-structure)
- [Setup](#Set-up-on-local-machine)

## Folders and repo structure
The following folders are standard in a JIL analysis/project repo:

#### Code
All code is kept in this folder.

1. Analyses - a sub-folder for final analysis
2. Exploratory - a sub-folder for notebooks that are less "structured" compared to those in analyses (e.g. exploring a new dataset). These notebooks will most likely never be shared externally.
3. Ingest - a sub-folder used to clean raw data.
4. utils - a sub-folder to store helper functions

#### input
Data can be stored here, however be careful with larger datasets as github does not handle large files.

#### output
When needed, output from code can be stored here.

## Set up on local machine

To properly train ML models we will need to allow them to run for hours. While goolge colab is great for inpsecting the data, it will time out before training a proper model. The following directions are a quick start to enable you to train models on your personal computer. 

1. Clone this repo to your desktop
2. Download [Anaconda](https://www.anaconda.com/)
3. Download [VS Code](https://code.visualstudio.com/)

Now you should be able to open the repo folder in VS code and open the Jupyter notebooks. If you want to fully run the code over the raw data you will need a Stata license and follow the steps in the subsection below AFTER setting up your conda environment.

We use a stable conda environment to ensure that all repo contributors use the same packages and python/R versions. Our environments are controlled by the `environment_unpinned.yml` file. While we give everyone access to this file, please to do not alter it without knowing what you are doing. Similarly, if you are in need of a new package please let us know so that we can properly add it to the environment.yml file. While you may install a new package within your local copy of the conda environment this repo uses e.g. `conda install pandas` or `pip install boxsdk`, this will only install on __YOUR__ local copy of the environment and won't be added to the repo's general environment so others won't be able to use the package still and your code may not run for others. If you find yourself installing packages, make note of how you installed the package (`pip` or `conda`) and the version number of the package and let a repository admin know so that it can be added properly.

To run the code in our repo, you will need Anaconda. While Anaconda is a little heavy, it affords us the ability to include both python and R. Once you have installed Anaconda, you may create the environment on your local machine by navigating in a terminal to the repo directory and running the following command `conda env create --name hurr_court_env --file environments/environment_unpinned.yml`. This only needs to be done once as it will create a new environments folder in the repo from which you can activate the repo moving forward. You may need to update that folder if the `environments/environment_unpinned.yml` file changes by simply running `conda env update --name hurr_court_env --file environments/environment_unpinned.yml`. If you are running code in terminal, then you should activate the environment in the terminal via `conda activate hurr_court_env` before running the code. If you are running a jupyter notebook in VSC or any other interpreter, then you should use this environment in your kernel. **You can do this by finding the environment in the top right of the code editor where you should be able to click something like 'Python ...' and then choose your environment where you should choose this environment. If it is not available, you may need to simply restart VSC**
