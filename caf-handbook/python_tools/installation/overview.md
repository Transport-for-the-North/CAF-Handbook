# Installation & Set-Up

The majority of the packages within CAF are written with Python and therefore require Python
to be installed on the users system in order to use them. This section runs through the CAF recommendations
for installing Python and our packages.

## Python

The recommended method for installing Python is using [miniforge](https://conda-forge.org/download/),
which will install conda, mamba, and their dependencies, see [Miniforge Installation](#miniforge-installation)
for details. Python, and many other packages, can then be installed using the `conda install`
command e.g. `conda install python`.

```{tip}
Most CAF packages are available on PyPI and conda-forge so if you've installed Python in a
different way then `pip install` should work for all the released CAF packages.
```

```{warning}
CAF packages are not available on the default Anaconda channel, if you have installed Anaconda
then the conda-forge channel should be added. A channel can be added as a default using
`conda config --add channels conda-forge`, or can be used for a single install command
with `-c conda-forge` e.g. `conda install caf.toolkit -c conda-forge`.
```

### Miniforge Installation

[Miniforge](https://conda-forge.org/download/) is a self-contained installer which will install
conda and setup conda-forge as the default channel. During the miniforge installation the installer
will provides some options to customise the installation, these two are worth considering:

- **Register Miniforge3 as my default Python**: this will allow other programs to detect Python
  in Miniforge3 on the system.
- **Add Miniforge3 to my PATH environment variable**: this will allow conda commands to be called
  from the default Windows command-prompt, if this is disabled then conda commands should be ran
  from within the Miniforge3 prompt.

```{seealso}
[Frequently Asked Questions](faqs.md#why-do-caf-recommend-conda-forge-and-miniforge) for the
reasons behind CAF's miniforge recommendation.
```

### Conda Environments

Conda allows for different versions of Python, and dependencies, to be installed in separate
environments. Environments can be setup using the `conda create -n environment_name` command
and then need to be activated using `conda activate environment_name`.

When inside an environment you can install packages using the `conda install` command and they
won't affect packages installed in any other environments. Environments can be created, switched
between and removed very easily so it is recommended to use separate environments for different
tasks, where possible, to avoid having dependency conflicts.

For more information on working with conda and setting up separate environments for different
tools and projects see [](environments.md).
