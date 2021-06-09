# M01T01 - Setting Up Python

> A water boa for a python!

Two primary sources for installation of Python packages are the [Python's official distribution](https://www.python.org) and the [Anaconda distribution](https://www.anaconda.com/). 
Each of them use their own package managers (`pip` and `conda` respectively) to install and update packages as well as create virtual environments to support multiple versions of Python in the same machine.

Due to some advantages (package dependency analysis and math kernel optimization libraries) of the Anaconda distribution over the official Python one, by default, we will be using the Anaconda distribution unless specifically mentioned otherwise.

## Installing the Anaconda Individual Edition
![Conda](https://img.shields.io/conda/vn/conda-forge/conda?label=version&style=flat-square)
![Conda](https://img.shields.io/conda/dn/conda-forge/conda?style=flat-square)

Originally aimed for data science and machine learning, the *Anaconda Individual Edition* is a free distribution for Python and R programming languages constituting of a large number of packages for both. 
The package manager `conda` analyzes the installed packages and verifies the dependencies making the installation breakdown-proof for existing projects. 
A light-weight, minimal edition of the distribution is also available under the name [Miniconda](https://docs.conda.io/en/latest/miniconda.html).

### On Windows/MacOS

Download the graphical installer (`.exe`/`.pkg`) for the latest version of Anaconda Python from the [individual product download page](https://www.anaconda.com/products/individual) for the specific version of your operating system and run it.

***Note: If Anaconda is the only distribution of Python in your system, make sure to check both "Add Anaconda to the system PATH environment variable" and "Register Anaconda as the system Python 3.x".***

### On Linux

Before installing Anaconda, update the *Debian* build-tools by executing:

```bash
sudo apt-get install --upgrade build-essential
```

Download the command line installer (`.sh`) for the latest version of Anaconda Python from the [individual product download page](https://www.anaconda.com/products/individual). Alternatively, you can download the installer from the terminal using `curl` (cURL) using the following commands:

```bash
sudo apt-get install --upgrade curl
curl -O https://repo.anaconda.com/archive/Anaconda3-2020.07-Linux-x86_64.sh
```

Install the downloaded file by running the following command in the terminal, replacing `path/to/downloaded/file` with the complete path to the directory of the file along with the file name:

```bash
bash path/to/downloaded/file.sh
```

***Note: Linux usually comes with official Python distributions accessible through `python3` for version 3.x and `python` for version 2.x.*** 
***Installing and initializing conda will override the default `python` command in the terminal with Anaconda's version of Python.***

## Initializing the conda Environment

*conda-forge* is a community-driven packaging system for conda dedicated for the scientific computing community. It provides a wide collection of recipies, build infrastructure and distributions. 
To add it as the first-hit channel, open the Anaconda command prompt in the elevated (administrator) mode and execute the following lines:

```bash
conda config --add channels conda-forge
conda config --set channel_priority strict
```

Initialize the conda environment using:

```bash
conda init
```

To verify the version of Python installed, run:

```bash
python --version
```

The output should be of the form:

```bash
Python 3.x.x
```

*In Linux systems, the initialization scripts for `conda` are available inside the `$HOME/.bashrc` file.*

## Creating Python Environments

It is useful to create individual virtual environments to run different versions of Python depending on the requirements of specific packages. 
And the `conda` package provides an easy way to manage such virtual environments.

To create a new environment (say, by the name `py38`) supporting a particular version of Python (say Python 3.8.x), use the following command:

```
conda create --name py38 python=3.8
```

Once the creation is complete, you can activate the environment by:

```
conda activate py38
```

To remove the created environment, use the following command:

```
conda env remove --name py38
```

## Managing Anaconda Packages

To install a package, use the following command by replacing `package` with its name and `version` with its requied version:

```bash
conda install package=version
```

To install multiple packages, append them one after the other separated by spaces.

To list all installed packages, use:

```bash
conda list
```

To update all packages, use:

```bash
conda update --all
```

To remove a package, use the following command by replacing `package` with its name:

```bash
conda remove package
```

[Conda's official cheat sheet](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf) collects a comprehensive list of commands available via the `conda` package.

[\[Next\] M01T02 - The Python Interpreter &#8594;](./m01t02-the-python-interpreter.md)