# Environments

During the installation and use of Python, and it's many packages, it is recommended to use
an environment manager to avoid conflicting versions of packages when working on different projects.
CAF recommends using conda (specifically conda-forge) for managing Python environments.

```{note}
Environments (within the context of Python and this document) are separate installations of
Python which do not interact with one another.
```

Conda allows you to create separate environments, each containing their own files, packages,
and package dependencies. The contents of each environment do not interact with each other.[^conda_envs]
CAF recommends creating different environments for different projects and in some cases tasks, dependent
on the tools / packages being used.

[^conda_envs]: [Creating Environments (conda documentation)](https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html#creating-environments)

```{important}
When working with Python you should **always** define the packages, and minimum version, required
for your script or process in one, or more, [requirements files](#requirements-file). This is
especially important when sharing the process with others.
```

## Create an Environment

```{important}
This section assumes that conda has been installed using miniforge, see [](#overview).
```

Our recommended method for creating environments is using the `conda create` command with one,
or more, "requirements.txt" files.

`conda create -n env_name --file requirements.txt --file requirements_dev.txt`

The above command will install all packages found in "requirements.txt" and "requirements_dev.txt",
see [Requirements File](#requirements-file) for more information on those files.

```{note}
Conda environments need to be activated with `conda activate env_name` to use them, many
code editors (such as VS Code or PyCharm) will do this automatically.
```

Additional to the method above the create command can be used to create an environment without
installation any packages:

`conda create -n env_name`

Packages can also be defined directly in the command itself:

`conda create -n env_name python numpy pandas`

This will create a new environment called "env_name" and install the most up to date versions of
python, numpy and pandas, version restrictions can be defined using the same syntax as in the
[Requirements File](#requirements-file) e.g. "pandas>=2.1". More information on the conda create
command is available in the
[create command documentation](https://docs.conda.io/projects/conda/en/latest/commands/create.html).

## Working with Conda Environments

This section outlines a few useful commands available within conda, more information is available
in the [Conda Cheatsheet (conda documentation)](https://docs.conda.io/projects/conda/en/latest/user-guide/cheatsheet.html).

- `conda create`: create an environment, see [Create an Environment](#create-an-environment).
- `conda activate env_name`: activate the conda environment with the name "env_name".
- `conda info --envs`: show a list of all conda environments on this machine, see
  [conda info documentation](https://docs.conda.io/projects/conda/en/latest/commands/info.html).
- `conda install package`: install "package" in currently activated environment, see
  [conda install](https://docs.conda.io/projects/conda/en/latest/commands/install.html).
- `conda uninstall package`: uninstall "package" from currently activated environment.
- `conda list`: list all packages, in activated environment, with the versions and channels,
  see [conda list](https://docs.conda.io/projects/conda/en/latest/commands/list.html).
- `conda remove -n env_name --all`: uninstall all packages from "env_name" and completely remove
  the environment, see [conda remove](https://docs.conda.io/projects/conda/en/latest/commands/remove.html).

```{warning}
Any commands which act on the currently activated environment will act on the base environment
if no other is activated.
```

## Requirements File

The recommended approach to defining a repositories requirements is within one, or more,
`requirements.txt` files.[^reqfile]  These are simply a list of all the packages required by the project
and their relevant version restrictions, an [example of a requirements.txt file](example_file) is shown below,
each requirement is listed on a separate line in the text file.

[^reqfile]: [Requirements File Format (pip documentation)](https://pip.pypa.io/en/stable/reference/requirements-file-format/)

```{seealso}
[Frequently Asked Questions](faqs.md#why-do-caf-recommend-requirementstxt-files) for an explanation
of why CAF recommends `requirements.txt` files.
```

In CAF we recommend splitting dependencies into multiple requirements files:

- `requirements.txt`: main requirements file in the root of the repository which contains all the
  dependencies required to use and run the package.
- `requirements_dev.txt`: list of all the dependencies required for developing the package e.g.
  testing, linting and building.
- `docs/requirements.txt`: dependencies required for building the documentation e.g. sphinx.
- `examples/requirements.txt`: additional dependencies required for running any example scripts
  which are provided in the repository (and documentation).
- `requirements_{option}.txt`: optional dependencies which are required for certain specific features
  of the package, '{option}` should be replaced with a sensible name for the optional feature.
  These should be used sparingly as in most cases features of the package shouldn't be hidden behind
  optional dependencies.

```{note}
Many Python packages (including all CAF packages) use the [Semantic Versioning 2.0.0](https://semver.org/) (SemVer)
scheme for writing version numbers. In SemVer the version is split into three main parts MAJOR.MINOR.PATCH,
which are incremented to reflect the type of changes in the new version.

- Increment MAJOR version when you make incompatible API changes, i.e. code written to use
  1.7 of a package might not work with 2.0
- Increment MINOR version when you add functionality in a backward compatible manner, i.e. any
  code written to work with 1.6 should still work on 1.7
- Increment PATCH version when you make backward compatible bug fixes

SemVer provides more functionality for pre-release and build metadata which is described in detail
in the [Semantic Versioning Specification](https://semver.org/#semantic-versioning-specification-semver).
```

(example_file)=

### Example of a `requirements.txt` file

```none
pandas>=2.0
numpy>=1.4.2,<2
matplotlib==3.4
caf.space==1
caf.toolkit[hdf]
```

In the example above some of the possible version constraints are shown,
the meaning of each line is outlined below:

- `pandas>=2.0`: pandas should be greater than, or equal to, 2.0.
  2.0, 2.0.1, 2.1 are all acceptable versions
- `numpy>=1.4.2,<2`: numpy should be greater than, or equal to, 1.4.2 **and** less than 2.
  1.4.2, 1.5, 1.6 are acceptable but 1.2, 1.4.1 and 2.1 are not.
- `matplotlib==3.4`: matplotlib should be equal to 3.4 up to the minor version number, but the patch
  number can be anything. 3.4 and 3.4.3 are acceptable but 3.3 and 3.5 are not.
- `caf.space==1`: caf.space should be equal to 1 up to the major version i.e. the minor and patch
  versions can be anything. 1.5 is acceptable but 0.5 and 2.1 are not.
- `caf.toolkit[hdf]`: any version of caf.toolkit is acceptable but the optional dependencies labelled
  as 'hdf' should also be included.

```{attention}
The example requirements file doesn't necessarily contain a compatible set of requirements.
```

## Conda Limitations

There are two cases where conda cannot handle the installation of some packages, in these cases
installation will need to be done with [`pip install`](https://pip.pypa.io/en/stable/cli/pip_install/).

```{tip}
`pip install` can be ran inside a conda environment to install the packages their, but it should
only be used when `conda install` won't work.
```

1. If a package, or version, isn't available on [conda-forge](https://conda-forge.org/packages/),
   but is available on [PyPI](https://pypi.org/) then you will need to use `pip install`.
2. If a package, or version, isn't available on [conda-forge](https://conda-forge.org/packages/)
   or [PyPI](https://pypi.org/) then you may need to install it directly from GitHub using
   `pip install git+github_url`, see [Pip Install](#pip-install) for details.

When packages cannot be installed with conda it is often useful to define a separate requirements
file (requirements_pip.txt), which lists all these packages and versions. This should be used
sparingly as installing packages from multiple sources is not encouraged.

## Pip Install

```{tip}
Pip can install from a requirements file using `pip install -r requirements.txt`.
```

[Pip](https://pip.pypa.io/en/latest/) is the package installer for Python and, although it can't
manage environments, it does provide some functionality not available in conda. The four main
pieces of extra functionality are installing from a git repository (e.g. GitHub), installing from
a zipfile, editable installs or selecting optional dependencies. The pip install documentation
provides an [examples](https://pip.pypa.io/en/stable/cli/pip_install/#examples) section which
shows all the different methods for installing packages with pip.

```{attention}
Using pip install in any of the methods within this section only works for packages that have
the build configuration setup correctly, within CAF the build configuration is defined in
[pyproject.toml](#pyprojecttoml).
```

### Zipfile / Local Folder

Pip can install from a local folder or a zipfile, both local and online, this is done by providing
the URL or path to the file or folder.

`pip install https://github.com/Transport-for-the-North/caf.toolkit/archive/refs/heads/main.zip`

Above will install caf.toolkit from the a zipped version of the main branch on the GitHub repository,
see [Git Repository](#git-repository) for a better method for installing from GitHub.

`pip install Documents/my_package` will install whatever package is found in the "my_package" folder.

```{attention}
Installing can only be done from a public URL, see [Git Repository](#git-repository) for a way to
install from private GitHub repositories.
```

### Git Repository

When installing packages from a git (or other VCS) the recommended method is to use pip install
with git directly this is done using the `git+` before the repository URL.

`pip install git+https://github.com/Transport-for-the-North/caf.toolkit.git`

Above will install caf.toolkit from the default branch on GitHub, the following can be used to
select a different branch.

`pip install git+https://github.com/Transport-for-the-North/caf.toolkit.git@custom_branch`

```{note}
Installing packages directly from the git repository requires git to be installed on your
machine.
```

### Editable Installs

A package can be installed with pip in a way that allows the package to be edited without
reinstallation, this is primarily used to allow for editing the dependency of a package alongside
editing the main package itself.

Editable installs are done using the `-e` flag for `pip install` and can be used when installing
from a local folder or from a git repository.

`pip install -e Documents/my_package`

Above will install "my_package" so that any changes to it are picked up immediately.

```{attention}
Only use editable installs for packages you plan to edit, instead install from git
if not available on conda-forge or PyPI.
```

### Optional Dependencies

Some packages define some dependency as optional where they're only needed for a specific feature
of the package which many people may not need. This allows for a smaller subset of dependencies for
most users.

Pip can install optional dependencies with any of it's installation methods by including them after
the package name within '[]'. The code below shows examples of installing optional dependencies.

```none
pip install caf.toolkit[option_a]
pip install caf.toolkit[option_a] @ git+https://github.com/Transport-for-the-North/caf.toolkit.git
pip install my_package[option] @ Documents/my_package
pip install caf.toolkit[option_a, option_b]
```

## Pyproject.toml

Pyproject.toml is a configuration file used by many Python tools and contains different sections
for each tool. Within CAF packages there are two main uses of the pyproject.toml:

- The settings for building and releasing the package; and
- Parameters for any linters, formatters, tests or other development tools which we use.

The build parameters are required for pip install to work on the package and for releasing the
package on PyPI or conda-forge, they're defined in the following two tables:

- `[build-system]`: what requirements are needed to build the package.
- `[project]`: this table contains the package metadata e.g. description, authors and dependencies.

```{tip}
The project dependencies aren't defined explicitly within pyproject.toml, the file just includes
links to any `requirements.txt` files.
```

In addition to the build parameters the configuration file also contains parameters for any
development tools we use, these are all defined within the `[tool]` table in their own specific
sub-tables e.g. `[tool.pylint]` and `[tool.pytest]`, see the relevant tool for information on the
specific parameters available.
