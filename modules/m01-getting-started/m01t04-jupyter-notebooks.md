# M01T04 - The Jupyter Notebook and JupyterLab

![Conda](https://img.shields.io/conda/vn/conda-forge/jupyter?label=version&style=for-the-badge)
![Conda](https://img.shields.io/conda/dn/conda-forge/jupyter?style=for-the-badge)

> A journey to the largest pynet (*planet*)!

[`Project Jupyter`](https://jupyter.org/) provides a great way to work with different languages, be it to perform quick calculations or run extensive models.
The classic `Jupyter Notebook` is a lighweight web-based application to create presentable views or document computational workflows. 
It's modern interface is known as the `JupyterLab`, which is a modular, feature-rich web-based interactive development environment suitable for a variety of workflows.
Both of them provide a handful of tools to work with Python-based scripts.

## Installing the Jupyter Notebook and JupyterLab

Jupyter Notebook and JupyterLab already come bundled inside the base environment when `Anaconda` is installed.
One can also install them in any environment (say, the `py312` environment) with the following command:

```bash
conda install -n py312 notebook jupyterlab
```

## Multi-environment Execution

It is [advisable](https://towardsdatascience.com/how-to-set-up-anaconda-and-jupyter-notebook-the-right-way-de3b7623ea4a) to install the notebook applications in the `base` environment and access the kernels of other environments through it without explicitly installing it in the other environments.
To do this, one needs to install [nb_conda_kernels](https://github.com/Anaconda-Platform/nb_conda_kernels) in the `base` environment (or the specific environment using which the notebook servers will be run) using:

```bash
conda install -n base nb_conda_kernels
```

Then, in any other environment (say, the `py312` environment), one can just install the IPython kernel by exectuing:

```bash
conda activate py312
conda install ipykernel
```

Additionally, the interactive IPython widgets (more about it later) can be installed in this environment using:

```bash
conda install ipywidgets
```

[&#8592; \[Previous\] M01T03 - The Spyder IDE](./m01t03-the-spyder-ide.md)

[\[Next\] M01T05 - Python in VSCode &#8594;](./m01t05-python-in-vscode.md)