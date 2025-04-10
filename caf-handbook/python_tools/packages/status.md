---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# CAF Packages

The Common Analytical Framework is made up of numerous small modules that interconnect.
This reduces overhead on the development and collaboration side, as the coding becomes consistent and concise.
This page aims to outline modules and their release stage.

For explanations on each of the terms being used in the table, please see below or the contents to the right.
For brief descriptions of each of the packages see [](descriptions.md).

```{code-cell} ipython3
:tags: [hide-input]

import pandas as pd

# Template string to generate links for the table
github_link = '<a href="https://github.com/Transport-for-the-North/{package}">{package}</a>'
pypi_link = '<a href="https://pypi.org/project/{package}/"><img alt="PyPI release" src="https://img.shields.io/pypi/v/{package}?label=" style="padding: 0;"></a>'
conda_link = '<a href="https://anaconda.org/conda-forge/{package}"><img alt="Conda" src="https://img.shields.io/conda/vn/conda-forge/{package}?label=" style="padding: 0;"></a>'
pypi_downloads_link = '<a href="https://pypistats.org/packages/{package}"><img alt="PyPI Download Count" src="https://img.shields.io/pypi/dm/{package}?label=" style="padding: 0;"></a>'
conda_downloads_link = '<a href="https://anaconda.org/conda-forge/{package}"><img alt="Conda Download Count" src="https://img.shields.io/conda/d/conda-forge/{package}?label=" style="padding: 0;"></a>'

# This file contain the basic package information
data = pd.read_csv("packages.csv")

# Generate the links and additional columns using the basic package data above
data["Latest PyPI Version"] = data["Tool Name"].apply(lambda x: pypi_link.format(package=x))
data["Latest Conda Forge Version"] = data["Tool Name"].apply(lambda x: conda_link.format(package=x))
data["PyPI Downloads"] = data["Tool Name"].apply(lambda x: pypi_downloads_link.format(package=x))
data["Conda Downloads"] = data["Tool Name"].apply(lambda x: conda_downloads_link.format(package=x))
data["Tool Name"] = data["Tool Name"].apply(lambda x: github_link.format(package=x))

# Style and display the table
styled = data.style.hide(axis=0).set_table_attributes('class="dataframe" style="width: 100%;"')
styled = styled.set_table_styles(
    [
        {"selector": "td", "props": "text-align: left;"},
        {"selector": "th", "props": "text-align: left;"},
    ]
)
display(styled)
```
