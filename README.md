Fast Food Sentiment Classifier
==============================

Train a sentiment classifier that is specific to Burger King or Wendys.

The datasets are in `data/raw/burger-king.csv` and `data/raw/wendys.csv`.
These have title, text and sentiment columns and no row appears more than once (the _text_ column IS repeated).

An example of using a dataset to train a model can be found in `notebooks/01-mf-example-sentiment-train.ipynb`.

Using this project
------------------

To run this project you need to open a terminal (iterm on mac os x, cygwin on windows, if you're on linux you likely already know what to use).
Clone this repository and navigate to the folder.
Then you can run `make` to see what you can do.
You should see something like:

```
➜ make
Available rules:
- edit
    Run Jupyter Lab
- clean
    Delete all compiled Python files
- requirements
    Install Python Dependencies
```

To run jupyter lab you run `make edit`.

If this doesn't immediately work then check out the requirements below.

You will find a single notebook which shows you how to train a model for sentiment classification.

Requirements
------------

To have a good python setup you need to manage your version of python, the dependencies for the project, and the way that you run commands.
If you have these three working well then all your projects will work.

If you choose not to set this up then you will run into trouble at some point in the future ([comic](https://xkcd.com/1987/) about this).
When that happens these instructions will still be here.

### PyEnv

You manage your python version with [pyenv](https://github.com/pyenv/pyenv#installation).
Install that now and check that when you type `pyenv` in the terminal you see reasonable output (like a description of the options instead of _command not found_).

Once pyenv is installed you then install python 3.11.6 with the command `pyenv install 3.11.6`.
Then set that as your global python with `pyenv global 3.11.6`.

Finally check that has worked with `python --version`.
If this does not say `Python 3.11.6` then you need to look carefully at the messages that were printed during the previous steps and find out what went wrong.

You can check the python versions available on the [download page of python.org](https://www.python.org/downloads/).
It is best to stay one version behind (so 3.11.x if the latest version available is 3.12.y).
That is because the data science libraries are big and complex and it often takes them some time to support the latest version of python.

### Pipx

You manage the python terminal tools that you use with [pipx](https://pipx.pypa.io/stable/).
Install that now and check that when you type `pipx` in the terminal you see reasonable output (like a description of the options instead of _command not found_).

### Poetry

You manage the project dependencies with [poetry](https://python-poetry.org/).
Install that using pipx with `pipx install poetry`.
Check that when you type `poetry` in the teminal you see reasonable output (like a description of the options instead of _command not found_).

### Make

You manage the commands to run the project with make.
This is a very old tool that uses Makefile files to list all the things to do with the project.
To install this on Mac OS X you need to ensure that you have the XCode tools installed (with the command line tools).
Linux already has this installed, and windows will get it when you install cygwin.




Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── pyproject.toml     <- The requirements file for reproducing the environment
    │
    └── src                <- Source code for use in this project.
        ├── __init__.py    <- Makes src a Python module
        │
        ├── data           <- Scripts to download or generate data
        │   └── make_dataset.py
        │
        ├── features       <- Scripts to turn raw data into features for modeling
        │   └── build_features.py
        │
        ├── models         <- Scripts to train models and then use trained models to make
        │   │                 predictions
        │   ├── predict_model.py
        │   └── train_model.py
        │
        └── visualization  <- Scripts to create exploratory and results oriented visualizations
            └── visualize.py

Poetry Installation and Usage
-----------------------------

This uses [poetry](https://poetry.eustace.io/docs/) as the package manager.
You can install it by following the instructions [here](https://poetry.eustace.io/docs/#installation).
I recommend using [pipx](https://pipxproject.github.io/pipx/) to install it, which requires installing pipx:

```
pip install --user pipx
pipx install poetry
```

Poetry uses automatically managed virtual environments.
This template already has a pyproject.toml file so to create such an environment and install the dependencies you just need to run:
```
make requirements
```

You can install new packages with the command:
```
poetry install DEPENDENCY
```
This will record the changes in the pyproject.toml and poetry.lock files, so remember to commit them.

You can run commands directly in the virtual environment without activating it.
This is done by adding the `poetry run` prefix to your command, for example:
```
poetry run python -c 'print("Hello, World!")'
```
Invoking commands in this way means you will not change the virtual environment accidentally.

--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
<p><small>Refined to use poetry as the package manager</small></p>
