=======
pydiggs
=======


.. image:: https://img.shields.io/pypi/v/pydiggs.svg
        :target: https://pypi.python.org/pypi/pydiggs

.. image:: https://travis-ci.com/xinp-hub/pydiggs.svg?branch=master
        :target: https://travis-ci.com/github/xinp-hub/pydiggs
        :alt: Build Status

.. image:: https://readthedocs.org/projects/pydiggs/badge/?version=latest
        :target: https://pydiggs.readthedocs.io/en/latest/?version=latest
        :alt: Documentation Status


.. image:: https://pyup.io/repos/github/xinp-hub/pydiggs/shield.svg
     :target: https://pyup.io/account/repos/github/xinp-hub/pydiggs/
     :alt: Updates



A Python package for Data Interchange for Geotechnical and Geoenvironmental Specialists (DIGGS).


* Free software: GNU General Public License v3
* Documentation: https://pydiggs.readthedocs.io.
* Github Repository: https://github.com/xinp-hub/pydiggs.


Features
--------

* Validate DIGGS instance files against DIGGS XSD and Schematron schemas.


============
Installation
============


Stable release
--------------

To install pydiggs, run this command in your terminal:

.. code-block:: console

    $ pip install pydiggs

This is the preferred method to install pydiggs, as it will always install the most recent stable release.

If you don't have `pip`_ installed, this `Python installation guide`_ can guide
you through the process.

.. _pip: https://pip.pypa.io
.. _Python installation guide: http://docs.python-guide.org/en/latest/starting/installation/


From sources
------------

The sources for pydiggs can be downloaded from the `Github repo`_.

You can either clone the public repository:

.. code-block:: console

    $ git clone git://github.com/xinp-hub/pydiggs

Or download the `tarball`_:

.. code-block:: console

    $ curl -OJL https://github.com/xinp-hub/pydiggs/tarball/master

Once you have a copy of the source, you can install it with:

.. code-block:: console

    $ python setup.py install


.. _Github repo: https://github.com/xinp-hub/pydiggs
.. _tarball: https://github.com/xinp-hub/pydiggs/tarball/master


=====
Usage
=====

DIGGS `validator`
--------------

To use `validator` in a Python project::

    from pydiggs import validator

Create a `validator` object for the target DIGGS instance file::

    validation = validator("DIGGS_Instance_File_Path")

Validate the DIGGS instance file against the default DIGGS XSD Schema::

    validation.schema_check()

Validate the DIGGS instance file against a specific version of the DIGGS XSD Schema::

    validation = validator("DIGGS_Instance_File_Path", schema_path = "DIGGS_Schema_File_Path")
    validation.schema_check()

Print validation log::

    print(validation.schema_validation_log)

Validate against a Schematron Schema::

    validation = validator("DIGGS_Instance_File_Path", schematron_path = "DIGGS_Schematron_File_Path")
    validation.schematron_check()

Validate a DIGGS instance File against the default DIGGS XSD Schema using `Command Line Interface`::

    pydiggs schema_check "DIGGS_Instance_File_Path"

Validate a DIGGS instance File against a specific version of DIGGS XSD Schema using `Command Line Interface`::

    pydiggs schema_check "DIGGS_Instance_File_Path" --schema_path "DIGGS_Schema_File_Path"

Validate a DIGGS instance File against a Schematron Schema using `Command Line Interface`::

    pydiggs schematron_check "DIGGS_Instance_File_Path" --schematron_path "DIGGS_Schematron_File_Path"


============
Contributing
============

Contributions are welcome, and they are greatly appreciated! Every little bit
helps, and credit will always be given. Please visit https://pydiggs.readthedocs.io for more information.


=======
History
=======
  
0.1.0 (2021-06-14)
------------------

* First release on PyPI.
* Added DIGGS Schema validation features.

0.1.2 (2021-06-30)
------------------

* Created a "validator" Class is  to incorporate all the validation-related methods.
* Added an argument to allow users specifying a specific of DIGGS XSD Schema for validation.
* Added a Schematron validation method.
* Updated Documentation.
