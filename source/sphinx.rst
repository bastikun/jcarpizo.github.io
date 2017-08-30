Install Sphinx Documentation
============================

Install Sphinx, either from a distribution package or from PyPI with

::

    pip install Sphinx

Setting up the documentation sources
------------------------------------

Sphinx comes with a script called sphinx-quickstart that sets up a source directory and creates a default conf.py with the most useful configuration values from a few questions it asks you. Just run

::

    sphinx-quickstart

Running the build
-----------------

::
    sphinx-build -b html sourcedir builddir

::

    sphinx-build -b html . ../en

Reference: `Sphinx documentation contents`_

.. _Sphinx documentation contents: http://www.sphinx-doc.org/en/1.5.1/contents.html