# Frequently Asked Questions

## What are conda-forge and miniforge?

[Conda-forge](https://conda-forge.org/docs/) is a community maintained repository of conda packages
hosted on the conda-forge GitHub organisation. Conda-forge is built on top of the popular Anaconda
package manager but it doesn't use the default Anaconda package repository, which has some license
restrictions for commercial use.

Miniforge is the preferred conda-forge installer[^miniforge], which will install the conda
package, and environment, manager and setup conda-forge.

[^miniforge]: [conda-forge installer](https://conda-forge.org/download/)

## Why do CAF recommend conda-forge and Miniforge?

- Conda-forge is a community maintained repository, which allows CAF packages to be released on it
  and means it generally has more packages available than Anconda's default repository.
- Conda-forge doesn't have the license restricting commercial use, which Anaconda's default
  package repository does have.
- The conda package manager is very popular, well used and, with new updates, fast at
  creating environments.

There are other Python package managers available and one which was considered was [poetry](https://python-poetry.org/).
Poetry provides some additional benefits vs conda although these were not deemed significant
enough to outweigh the much greater popularity of conda based systems.

## Why do CAF recommend `requirements.txt` files?

Python has a few different formats for defining dependencies, the main four are:

- `requirements.txt`: the most basic file format, which can be used by most tools.
- `environment.yml`: a format specific to conda.
- `Pipfile`: a format specific to [pipenv](https://pipenv.pypa.io/en/latest/).
- `pyproject.toml`: a general Python configuration file which provides different sections
  for many development and build tools.

The main benefits of `requirements.txt` are:

- Not specific to a single package manager allowing users to use their preferred system.
- Much simpler to define and more flexible on the allowed values, e.g. allows defining packages
  to be installed from URLs or Git repositories.
- Works with CAF's package build method setuptools, which enables installation of CAF packages
  with pip or conda.


```{seealso}
[Requirements File section of Environments](environments.md#requirements-file) for more details
and examples.
```
