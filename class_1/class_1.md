# intro-to-python
Github repo for the Intro to Python class BIOS_26123

## Install git
To see this page, you need to clone this git repo
https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
Then run `git clone git@github.com:aartivnkt/intro-to-python.git` to clone this repo.
Before each class, remember to pull the latest git changes using `git pull origin master`

## Install Python

### Version

We will use Python 3.12.7 in this class

Links to install Python depend on the OS, see links in this page to different installations https://www.python.org/downloads/

For macOS go to https://www.python.org/downloads/macos/ and download the macOS 64-bit universal2 installer. Double click on the installer and install it. Then under applications, it will create a Python 3.12 folder and automatically open the finder window for you. Double click install certificates command to install certs, and double click update shell profile command to update shell profile

### Test Python installation
Open terminal, type `python3`, it should show you Python 3.12.7 version. To ensure Python and pip match up, check with
```bash
which python3
which pip3
```
These should match up.

## Install JupyterLab

Documentation is here https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html

To install using pip, run 
```bash
pip3 install jupyterlab
```

### Experiment with JupyterLab
After pip installation, launch using `jupyter lab`. Start working on `worksheet_1a.ipynb` to experiment with your first jupyterlab notebook that uses system Python 3.12.7. Close notebook and move onto the next section once complete. 

## Managing Python versions with `virtualenv`

### Install `virtualenv`

Run 
```bash
pip3 install pipx
pipx install virtualenv
```
Add virtualenv to path using `pipx ensurepath`
Close terminal window and re-open
Type `virtualenv` and `which virtualenv` to check installation with pipx

### Activate `virtualenv`
```bash
virtualenv venv_3.12.7
source venv_3.12.7/bin/activate
deactivate
source venv_3.12.7/bin/activate
```

### Ensure python 3.12.7 kernel can be selected in JupyerLab
Close any JupyterLab sessions if you have them open
Run the following
```
pip install jupyterlab ipykernel
python -m ipykernel install --user --name=venv_3.12.7 --display-name "Python 3.12.7"
```

Type `jupyter lab` again and work on `worksheet_1b.ipynb` this time, choosing "Python 3.12.7" kernel from the top right

### Remove all packages from `virtualenv`
To remove all packages from `virtualenv`, run the following:
```bash
rm -rf venv_3.12.7
```
Then follow all the steps for re-creating `virtualenv`, see `Activate virtualenv` section above

### Introduction to Jupyter Lab
Run `worksheet_1c.ipynb` in virtualenv to experiment with fun things in Jupyter Lab!`

