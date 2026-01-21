# My Research Project Template

This repository is a template to help you start your own small research project in Python. It provides a basic structure to organize your code, making it easier to manage and share your work. This guide is intended for those who are new to programming and want to learn good practices.

## Getting Started

To use this template, you can either clone it or download it as a zip file. Once you have the files on your computer, you can start adding your own code.

## Project Structure

The project has the following structure:

```
.
├── my_research
│   ├── __init__.py
│   ├── scripts
│   │   ├── __init__.py
│   │   └── mr_compute_intensity_histogram.py
│   └── utils
│       ├── __init__.py
│       └── image.py
├── .gitignore
├── LICENSE
├── README.md
├── setup.cfg
└── setup.py
```

-   `my_research`: This is the main package where your Python code will live.
-   `my_research/utils`: This is a good place to put utility functions that can be reused in different parts of your project.
-   `my_research/scripts`: This is where you can put your scripts that perform specific analyses.
-   `setup.py`: This file is used to install your package.
-   `README.md`: This file provides information about your project.
-   `LICENSE`: This file contains the license for your project.
-   `.gitignore`: This file tells Git which files to ignore.

## How to Add Your Own Code

### Adding a new function

If you have a function that you think will be useful in different parts of your project, you should add it to a module in the `my_research/utils` directory.

For example, if you have a function that loads a specific type of data, you could create a new file called `my_research/utils/data.py` and add your function there.

```python
# my_research/utils/data.py

def load_my_data(filepath):
    """
    This function loads my special data format.
    """
    # Your code to load the data
    pass
```

You can then use this function in your scripts by importing it:

```python
from my_research.utils.data import load_my_data

data = load_my_data("path/to/my/data.txt")
```

### Adding a new module

If you have a set of related functions, you can group them into a module. A module is simply a Python file with a `.py` extension.

For example, if you are working with images, you could create a module called `image.py` in the `my_research/utils` directory and add all your image-related functions there. This is already done in this template.

### Adding a new script

If you want to perform a specific analysis, you can create a new script in the `my_research/scripts` directory.

For example, if you want to compute the average intensity of an image, you could create a script called `compute_average_intensity.py`:

```python
# my_research/scripts/compute_average_intensity.py

from my_research.utils.image import display_histogram
import numpy as np

# Your code to load an image
image = np.random.rand(100, 100)

# Your code to compute the average intensity
average_intensity = np.mean(image)

print(f"The average intensity is: {average_intensity}")
```

### Adding requirements

If your project depends on other Python packages, you should list them in the `setup.py` file. This will allow others to install the necessary packages when they install your project.

In `setup.py`, you will find a list called `install_requires`. You can add your dependencies there.

```python
# setup.py

from setuptools import setup, find_packages

setup(
    name='my_research',
    version='0.1',
    packages=find_packages(),
    install_requires=[
        'numpy',
        'matplotlib',
        # Add your other dependencies here
    ],
)
```

## Running the linter

To make sure your code follows the Python style guide (PEP8), you can run a linter. This template is set up to use `pycodestyle`.

To run the linter, execute the following command in the root of the project:

```bash
pycodestyle my_research
```

This will check all the Python files in the `my_research` directory and report any style violations.