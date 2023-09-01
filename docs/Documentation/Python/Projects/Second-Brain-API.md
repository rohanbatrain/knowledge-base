## Project Layout

I have followed this [wiki](https://packaging.python.org/en/latest/tutorials/packaging-projects/) from official python guidelines.


### Prerequisite

You obviously need Python. The following pip packages are required in order to build your distribution of your package.

```python
pip
setuptools
build
```

### Project Structure

The following snippet shows the directory structure when i initially got started with the project. 


```
.
├── LICENSE
├── pyproject.toml
├── README.md
├── src
│   └── second-brain-api_rohanbatrain
│       ├── __init__.py
│       └── main.py
└── tests

4 directories, 5 files
``` 

### pyproject.toml

My pyproject config

```
[build-system]
requires = ["setuptools>=61.0"]
build-backend = "setuptools.build_meta" 


[project]
name = "Second Brain API"
version = "0.0.1"
authors = [
  { name="Rohan Batra", email="contact@rohanbatra.in" },
]
description = "A python package for second brain template"
readme = "README.md"
requires-python = ">=3.7"
classifiers = [
    "Programming Language :: Python :: 3",
    "License :: OSI Approved :: MIT License",
    "Operating System :: OS Independent",
]

[project.urls]
"Homepage" = "https://github.com/rohanbatrain/second-brain-api"
"Bug Tracker" = "https://github.com/rohanbatrain/second-brain-api/issues"
```


## Project Build

```python
python3 -m build
```

![out.gif](../../../attachments/out.gif)