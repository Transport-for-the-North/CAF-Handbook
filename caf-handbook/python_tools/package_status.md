# Package Status

The Common Analytical Framework is built using a Polylithic design, meaning it is made up of numerous small modules that
all interconnect. This reduces overhead on the development and collaboration side, as there is less code to think about
in each module. A downside of this approach is the lack of clarity of what else is available and how developed it is. 
This page aims to clarify that with the below table. 

For explanations on each of the terms being used in the table, please see below or the contents to the right.

% Table is ordered by CAF status, then alphabetically
% To add - CAF.LGV
```{list-table}
:header-rows: 1

* - Tool Name (with link)
  - CAF Status
  - Interface
  - Latest PyPI Version
  - Latest Conda Forge Version
  
* - [caf.space](https://github.com/Transport-for-the-North/caf.space)
  - CAF Release
  - Python API, GUI
  - <a href="https://pypi.org/project/caf.space/"><img alt="Latest release" src="https://img.shields.io/github/release/transport-for-the-north/caf.space.svg?style=flat-square&maxAge=86400"></a>
  - <a href="https://anaconda.org/conda-forge/caf.space"><img alt="Conda" src="https://img.shields.io/conda/v/conda-forge/caf.space?style=flat-square&logo=condaforge"></a>

* - [caf.toolkit](https://github.com/Transport-for-the-North/caf.toolkit)
  - CAF Release
  - Python API, CLI
  - <a href="https://pypi.org/project/caf.toolkit/"><img alt="Latest release" src="https://img.shields.io/github/release/transport-for-the-north/caf.toolkit.svg?style=flat-square&maxAge=86400"></a>
  - <a href="https://anaconda.org/conda-forge/caf.toolkit"><img alt="Conda" src="https://img.shields.io/conda/v/conda-forge/caf.toolkit?style=flat-square&logo=condaforge"></a>
  
* - [caf.carbon](https://github.com/Transport-for-the-North/caf.carbon)
  - Beta
  - Python API
  - None Currently
  - None Currently
  
* - [caf.distribute](https://github.com/Transport-for-the-North/caf.distribute)
  - Beta
  - Python API
  - <a href="https://pypi.org/project/caf.distribute/"><img alt="Latest release" src="https://img.shields.io/github/release/transport-for-the-north/caf.distribute.svg?style=flat-square&maxAge=86400"></a>
  - <a href="https://anaconda.org/conda-forge/caf.distribute"><img alt="Conda" src="https://img.shields.io/conda/v/conda-forge/caf.distribute?style=flat-square&logo=condaforge"></a>
  
* - [caf.viz](https://github.com/Transport-for-the-North/caf.viz)
  - Beta
  - Python API
  - <a href="https://pypi.org/project/caf.viz/"><img alt="Latest release" src="https://img.shields.io/github/release/transport-for-the-north/caf.viz.svg?style=flat-square&maxAge=86400"></a>
  - <a href="https://anaconda.org/conda-forge/caf.viz"><img alt="Conda" src="https://img.shields.io/conda/v/conda-forge/caf.viz?style=flat-square&logo=condaforge"></a>
  
* - [caf.core](https://github.com/Transport-for-the-North/caf.core)
  - Alpha
  - Python API
  - None Currently
  - None Currently
 
* - [caf.ml](https://github.com/Transport-for-the-North/caf.ml)
  - Alpha
  - Python API
  - None Currently
  - None Currently  
  
* - [caf.tem](https://github.com/Transport-for-the-North/caf.tem)
  - Pre-Alpha
  - Python API
  - None Currently
  - None Currently
  
```

## CAF Status
Note on CAF status and another page

## Interface
Different interfaces considered for different modules.
All have a python API as default, as part of development.
Try to focus on most useful.
Open the requests for more interfaces if desired.

### Python API
What does this mean?
WHat can the user expect from this?
- Reliable
- cut down
- usable

### CLI
Command Line interface. Provide example of usage.

### GUI
Graphic User Interface. Example of usage.

## PyPI version
Why some packages are released here and not others. Why is this the default?

## Conda Forge version
Why deploy here? Why does this version tend to lag behind?