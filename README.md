# pyDIGGS

[![PyPI version](https://img.shields.io/pypi/v/pydiggs.svg)](https://pypi.python.org/pypi/pydiggs)
[![Python Versions](https://img.shields.io/pypi/pyversions/pydiggs)](https://pypi.org/project/pydiggs)
[![Downloads](https://static.pepy.tech/badge/pydiggs)](https://pepy.tech/project/pydiggs)
[![Downloads/Month](https://static.pepy.tech/badge/pydiggs/month)](https://pepy.tech/project/pydiggs)
[![Build Status](https://github.com/xinp-hub/pydiggs/actions/workflows/ci.yml/badge.svg)](https://github.com/xinp-hub/pydiggs/actions/workflows/ci.yml)
[![Documentation Status](https://github.com/xinp-hub/pydiggs/actions/workflows/docs.yml/badge.svg)](https://xinp-hub.github.io/pydiggs/)
[![Updates](https://pyup.io/repos/github/xinp-hub/pydiggs/shield.svg)](https://pyup.io/account/repos/github/xinp-hub/pydiggs/)


A Python package for Data Interchange for Geotechnical and Geoenvironmental Specialists (DIGGS).


* Free software: GNU General Public License v3
* Documentation: [https://xinp-hub.github.io/pydiggs](https://xinp-hub.github.io/pydiggs)
* GitHub: [https://github.com/xinp-hub/pydiggs](https://github.com/xinp-hub/pydiggs)

## Features

* Validate DIGGS instance files against DIGGS XSD, Schematron schemas, and XML Dictionaries.

## Quick Start

Install pydiggs:
```bash
pip install pydiggs
```

Basic usage:
```python
from pydiggs import validator

# Create a validator instance
v = validator.Validator()

# Validate a DIGGS XML file
v.validate_schema("path/to/your/diggs_file.xml")
```

# Installation

## Stable Release

To install pydiggs, run this command in your terminal:

```bash
pip install pydiggs
```

This is the preferred method to install pydiggs, as it will always install the most recent stable release.

If you don't have [pip](https://pip.pypa.io) installed, this [Python installation guide](https://docs.python-guide.org/starting/installation/) can guide you through the process.

## From Sources

The sources for pydiggs can be downloaded from the [GitHub repo](https://github.com/xinp-hub/pydiggs).

You can either clone the public repository:

```bash
git clone git://github.com/xinp-hub/pydiggs
```

Or download the [tarball](https://github.com/xinp-hub/pydiggs/tarball/master):

```bash
curl -OJL https://github.com/xinp-hub/pydiggs/tarball/master
```

Once you have a copy of the source, you can install it with:

```bash
poetry install
``` 


# Usage

## DIGGS `validator`

### 1. Using Jupyter Notebooks or py files

To use `validator` in a Python project:

```python
from pydiggs import validator

# Create a validator object for the target DIGGS instance file
validation = validator("DIGGS_Instance_File_Path")

# Validate the DIGGS instance file against the default DIGGS XSD Schema
validation.schema_check()

# Validate the DIGGS instance file against a specific version of the DIGGS XSD Schema
validation = validator("DIGGS_Instance_File_Path", schema_path="DIGGS_Schema_File_Path")
validation.schema_check()

# Print validation log
print(validation.schema_validation_log)

# Validate against a Schematron Schema
validation = validator("DIGGS_Instance_File_Path", schematron_path="DIGGS_Schematron_File_Path")
validation.schematron_check()

# Validate against the standard XML Dictionary file
validation = validator("DIGGS_Instance_File_Path")
validation.dictionary_check()
```

### 2. Using Command Line Interface (CLI)

Validate a DIGGS instance File against the default DIGGS XSD Schema using Command Line Interface (CLI):
```bash
pydiggs schema_check "DIGGS_Instance_File_Path"
```

Validate a DIGGS instance File against a specific version of DIGGS XSD Schema using Command Line Interface:
```bash
pydiggs schema_check "DIGGS_Instance_File_Path" --schema_path "DIGGS_Schema_File_Path"
```

Validate a DIGGS instance File against a Schematron Schema using Command Line Interface:
```bash
pydiggs schematron_check "DIGGS_Instance_File_Path" --schematron_path "DIGGS_Schematron_File_Path"
```

Validate a DIGGS instance File against the standard Dictionary XML file using Command Line Interface:
```bash
pydiggs dictionary_check "DIGGS_Instance_File_Path"
```


# Contributing


Contributions are welcome, and they are greatly appreciated! Every little bit
helps, and credit will always be given. Please visit [https://xinp-hub.github.io/pydiggs](https://xinp-hub.github.io/pydiggs) for more information.


# History

## 0.1.0 (2021-06-14)

* First release on PyPI.
* Added DIGGS Schema validation features.

## 0.1.2 (2021-06-30)

* Created a "validator" Class is  to incorporate all the validation-related methods.
* Added an argument to allow users specifying a specific version of the DIGGS XSD Schema for validation.
* Added a Schematron validation method.
* Updated Documentation.

## 0.1.3 (2023-03-19)

* Officially added the dictionary validation method.
* Switched CI/CD workflows from Travis CI to GitHub Actions.
* Updated the package publishing method to adopt Poetry.
* Updated Documentation.

## 0.1.4 (2025-01-17)

* Updated the default schema version to 2.6.
* Added new test files for schema V2.6 schema validation.
* Updated the default dictionary validation xml file to be consistent with the "DIGGS Measurement Properties" dictionary in "DIGGS Code Lists and Measurement Properties Dictionaries V0.1". (Note: if you want to validate against other dictionaries in "DIGGS Code Lists and Measurement Properties Dictionaries V0.1", you can download the dictionary file from the DIGGS website and specify the dictionary path in the validator class.)
* Updated the pytest file for testing the updates above.
* Updated the minimum python version to 3.10 to support the latest versions of dependencies.
* Updated the dependencies with the latest versions.
* Updated Documentation.
