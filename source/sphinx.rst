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


.. meta::
    :description: My Online Technical Docs
    :keywords: PHP, MySQL, Git, Laravel, Symfony, Composer, HTML5, JavaScript, Phalcon, CakePHP, Java, Unix Shell Scripting, Node Js, CSS, eJabberd XMPP Server, SPHINX - Python Documentation Generator, Docker
    :author: Jasper Carpizo

.. raw:: html

   <meta property="og:image" content="jcarpizo.jpg"/>
   <meta property="og:title" content="My Online Technical Docs"/>
   <meta property="og:site_name" content="Jasper Carpizo"/>
   <meta property="og:url" content="https://jcarpizo.github.io"/>
   <meta property="og:type" content="blog"/>