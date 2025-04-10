# Package Summary

The Common Analytical Framework (CAF) modules are built using various Python packages and utilities, which
often interconnect. This page provides an overview of all available packages and a brief
summary of their usecases, for more details on the release status of packages see [](status.md)

The following sections provide a brief overview of the currently released CAF packages. Each section acts as a small advert for each package, highlighting some highly used functionality and the user interfaces available.

## caf.toolkit

<p align="center">
<a href="https://github.com/Transport-for-the-North/caf.toolkit"><img alt="GitHub Release" src="https://img.shields.io/github/v/release/Transport-for-the-North/caf.toolkit?label=GitHub"></a>
<a href="https://pypi.org/project/caf.toolkit/"><img alt="PyPI release" src="https://img.shields.io/pypi/v/caf.toolkit"></a>
<a href="https://anaconda.org/conda-forge/caf.toolkit"><img alt="Conda" src="https://img.shields.io/conda/v/conda-forge/caf.toolkit?style=flat-square&logo=condaforge"></a>
<a href='https://caftoolkit.readthedocs.io/en/stable/?badge=stable'><img alt='Documentation Status' src="https://img.shields.io/readthedocs/caftoolkit?style=flat-square&logo=readthedocs"></a>
</p>
<p align="center">
<a href="https://pypistats.org/packages/caf.toolkit"><img alt="PyPI Download Count" src="https://img.shields.io/pypi/dm/caf.toolkit?label=pypi%7Cdownloads"></a>
<a href="https://anaconda.org/conda-forge/caf.toolkit"><img alt="Conda Download Count" src="https://img.shields.io/conda/d/conda-forge/caf.toolkit"></a>
</p>

CAF.Toolkit focusses on generic tools and functions that are used across the CAF.
A command-line interface is provided for some key features.

The CLI provides access to zone translations for vector or matrix based data.
Additionally, caf.toolkit contains the follow functionality:

- **Configs** - Read, write and validate inputs from text configuration files (usually in the YAML format).
- **Logging** - Helps to manage message logging to both files and the terminal.
- **Cost distributions** - Create and handle transport cost distribution data.
- **Pandas utilities** - Additional utility functionality built around the [pandas](https://pandas.pydata.org/docs/) package. Contains common manipulations needed in transport models.

## caf.space

<p align="center">
<a href="https://github.com/Transport-for-the-North/caf.space"><img alt="GitHub Release" src="https://img.shields.io/github/v/release/Transport-for-the-North/caf.space?label=GitHub"></a>
<a href="https://pypi.org/project/caf.space/"><img alt="PyPI release" src="https://img.shields.io/pypi/v/caf.space"></a>
<a href="https://anaconda.org/conda-forge/caf.space"><img alt="Conda" src="https://img.shields.io/conda/v/conda-forge/caf.space?style=flat-square&logo=condaforge"></a>
<a href='https://cafspace.readthedocs.io/en/stable/?badge=stable'><img alt='Documentation Status' src="https://img.shields.io/readthedocs/cafspace?style=flat-square&logo=readthedocs"></a>
</p>
<p align="center">
<a href="https://pypistats.org/packages/caf.space"><img alt="PyPI Download Count" src="https://img.shields.io/pypi/dm/caf.space?label=pypi%7Cdownloads"></a>
<a href="https://anaconda.org/conda-forge/caf.space"><img alt="Conda Download Count" src="https://img.shields.io/conda/d/conda-forge/caf.space"></a>
</p>

CAF.Space contains geo-processing functionality useful
for transport planners. Primarily it is a tool for generating standard weighting
translations in `.csv` format describing how to convert between different zoning systems.

CAF space provides a command-line interface and GUI for producing zone correspondence files.
Additionally, caf.space contains the following functionality:

- **Zone Correspondence** - Calculate correspondence between two zone systems built from polygons,
  this can handle point zones and can produced population / employment weighted translations
  ([ZoneTranslation](https://cafspace.readthedocs.io/en/stable/_autosummary/caf.space.zone_translation.ZoneTranslation.html)).
- **Link to Zone** - Calculate correspondence between link data and zones (polygons),
  *currently work-in-progress in [pull request 27](https://github.com/Transport-for-the-North/caf.space/pull/27).*
- **Link to Link** - Calculate correspondence between two separate links shapefiles,
  *currently work-in-progress in [pull request 32](https://github.com/Transport-for-the-North/caf.space/pull/32).*

## caf.carbon

## caf.distribute

## caf.viz

## caf.base

## caf.mat

## caf.ml

## caf.tem
