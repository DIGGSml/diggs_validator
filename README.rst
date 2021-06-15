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

* Validation Features have been added to valdiate a DIGGS file against XML Syntax rules and the latest DIGGS Schema (Version 2.5.a).
* The validation process is also working with the Command Line Interface.


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

DIGGS validation
--------------

To use pydiggs in a Python project::

    from pydiggs import validation

If the DIGGS file is in your current working directory::

    validation("DIGGS_File_Name")

If the DIGGS file is not in your current working directory::

    validation("Full_DIGGS_File_Path")



To use validate DIGGS file in the Command Line Interface::

    pydiggs check "DIGGS_File_Name" or "Full_DIGGS_File_Path"


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
* DIGGS validation features have been added.
