# Common Analytical Framework Homepage

A homepage for information on development of the Common Analytical Framework

## Contributing

We welcome and recognize all contributions. You can see a list of current contributors in the [contributors tab](https://github.com/Transport-for-the-North/caf_homepage/graphs/contributors).

### Building the book

If you'd like to develop and/or build the Common Analytical Framework Homepage book, you should:

1. Clone this repository
2. Run `pip install -r requirements.txt` (it is recommended you do this within a virtual environment)
3. (Optional) Edit the books source files located in the `caf_homepage/` directory
4. Run `jupyter-book clean caf_homepage/` to remove any existing builds
5. Run `jupyter-book build caf_homepage/`

A fully-rendered HTML version of the book will be built in `caf_homepage/_build/html/`.

## Credits

This project is created using the excellent open source [Jupyter Book project](https://jupyterbook.org/) and the [executablebooks/cookiecutter-jupyter-book template](https://github.com/executablebooks/cookiecutter-jupyter-book).
