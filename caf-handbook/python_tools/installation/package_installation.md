# Tool & Model Installation

CAF packages can generally be split into two use cases:

- **Tools & models**: running as a standalone process from a command-line (CLI) or graphical user
  interface (GUI), no Python coding is required.
- **Package**: importing into another Python script / process to use the functionality.

Generally all CAF packages will allow for use as a package but many will provide a subset of
functionality which can be used from a CLI or GUI. All packages labelled as models will provide a
CLI at minimum, see [](../packages/models.md).

Installation of tools & models should be done using [pipx](#pipx), in most cases, whereas
installation of packages should be done with [conda](#conda).

```{important}
This section assumes that conda has been installed using miniforge, see [](#overview).
```

## Pipx

[Pipx](https://pipx.pypa.io/stable/) is a command-line utility which allows for the installation
of Python packages as standalone utilities in isolated environments. Pipx is the recommended method
for installing all CAF tools & models, but it is not recommended for installing packages which will
be imported in Python.

```{attention}
Pipx requires the package developer to enable, which may not be setup for all CAF packages.
If pipx setup is required for a specific package please create a GitHub issue on the relevant
repository.
```

### Installation

Pipx can be installed using conda and should be installed in your base conda environment, so it
can be called from anywhere, with:

`conda install pipx`

Once installed you should be able to call the `pipx` command from anywhere. Before attempting to
install anything pipx recommends running `pipx ensurepath` to make sure the install directory is
included in the PATH environment variable, this enables installed tools to be called from
command-prompt.

### Usage

Pipx provides an install command which will create a new Python environment and install the
specified package. This installation methods makes sure each installation is separate and can have
different Python or dependency versions if required. Pipx installation also allows for the installed
packages to be called directly from command-prompt.

Using pipx to install caf.toolkit is done simply by running `pipx install caf.toolkit`.

Once install caf.toolkit can be ran simply by calling `caf.toolkit` from command-prompt.

Some common pipx commands are listed below, more information can be found on
[pipx docs](https://pipx.pypa.io/stable/docs/) or by calling `pipx` on its own.

- `pipx install package_name`: will install "package_name", and all it's dependencies, in it's own
  isolated environment, e.g. `pipx install caf.toolkit`.
- `pipx list`: will list all installed apps.
- `pipx upgrade package_name`: will check for updates, and install them, for "package_name".
- `pipx uninstall package_name`: will uninstall the "package_name" package.

```{attention}
Pipx is only useful for installing packages which provide an interface to users, for installing
packages and importing them in your own Python scripts, or packages, see [conda](#conda) below.
```

## Conda

```{important}
This section assumes that conda has been installed using miniforge, see [](#overview).
```

CAF recommends the use of conda (specifically conda-forge) for installation of Python and packages,
see [](faqs.md) for some more information about the recommendation. When using conda it is
recommended not to install packages into the base environment and instead create different
environments for each project or workflow, see [](environments.md).

Creating a new environment and installing a single package can be done with the `conda create`
command.

`conda create -n toolkit caf.toolkit`

The above command will create a new environment called "toolkit" and install the most recent version
of caf.toolkit in it. Once a package is installed it can be called from command-prompt by activating
the environment and then running the package with Python:

```none
conda activate toolkit
python -m caf.toolkit
```

`python -m package` allows running an installed package by running the package's `__main__.py`
script. Not all Python packages will provide a `__main__.py` script so may not be runnable, but
CAF tools & models do provide this functionality.

```{note}
While all CAF packages are planned to be released on PyPI and conda-forge, early versions of them
may not be. These can still be installed and used but require installation with pip directly,
see the [Pip Install section of Environments](environments.md#pip-install) for details.
```

### Importing a Package

If using a CAF package within your own Python script, this should still be installed with conda.
However, a `requirements.txt` file should be created for your script and the dependencies should be
listed there, see the [Requirements File section of Environments](environments.md#requirements-file)
for details.

For example if using caf.toolkit's functionality within another Python script.

1. Create a `requirements.txt` file and list caf.toolkit and any other dependencies.
2. Create a conda environment and install everything you need,
   `conda create -n environment_name --file requirements.txt`.
3. Import caf.toolkit using `import caf.toolkit as ctk`.

```{tip}
When defining your `requirements.txt` file start with only the dependencies needed at the moment,
more can be added later when required.
```
