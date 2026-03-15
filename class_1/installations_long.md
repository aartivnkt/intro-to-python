# Installations

Note: GitHub installations are in `installations_github.md` file, please refer to that file to install GitHub.

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

## Install `JupyterLab`

Documentation is here https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html

To install using pip, run 
```bash
pip3 install jupyterlab
```

## Install `ipykernel`

Run the following
```
pip3 install jupyterlab ipykernel
python -m ipykernel install --user --name=venv_3.12.7 --display-name "Python 3.12.7"
```

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
```

### Deactivate `virtualenv`
```bash
deactivate
```

# Test installations of JupyterLab, Python and other dependencies

Ensure python 3.12.7 kernel can be selected in JupyerLab, under the kernel dropdown. Close any JupyterLab sessions if you have them open. Type `jupyter lab` in the `intro-to-python` directory. Choose "Python 3.12.7" kernel from the top right. Activate virtualenv. Run `worksheet_1a.ipynb` and `worksheet_1b.ipynb` in virtualenv to experiment with installations!

