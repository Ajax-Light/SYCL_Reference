..
  Copyright 2020 The Khronos Group Inc.
  SPDX-License-Identifier: CC-BY-4.0

.. image:: https://readthedocs.org/projects/sycl/badge/?version=latest
           :target: https://sycl.readthedocs.io/en/latest/?badge=latest
           :alt: Documentation Status

.. image:: https://api.reuse.software/badge/github.com/KhronosGroup/SYCL_Reference
          :target: https://api.reuse.software/info/github.com/KhronosGroup/SYCL_Reference
          :alt: REUSE status

==========================
 SYCL Language Reference
==========================

This repo contains the source for the SYCL reference manual published
at ReadTheDocs_.

It's a work in progress. It may be missing descriptions or entire
classes. If you see something wrong, file an issue or submit a PR to
fix it.

Automatic Publishing
====================

Commits to main branch are built and published at ReadTheDocs_.

Prerequisites
=============

The document is built with _Sphinx plugins. To install all required
software on Ubuntu::

   apt-get update -qq
   DEBIAN_FRONTEND=noninteractive xargs -a ubuntu-packages.txt apt-get install -qq
   pip3 install --upgrade --quiet -r requirements.txt

On Windows, install python_ and git_, followed by::

   pip install --upgrade --quiet -r requirements.txt

For development, you must also install `clang-format`_. This is only
needed for C++ code formatting as part of the git pre-commit hook.

Building
========

To build as HTML::

  python doc.py html

To see the document, open build/html/index.html

To build as a PDF::

  python doc.py latexpdf

To see the document, open build/latex/syclreference.pdf

Using SYCL spec headers
=======================

We use a manual process to incorporate `SYCL spec headers`_ into our
doc. The headers that were used are kept in the headers_ directory. If
this doc does not include definitions from the spec, then copy the new
header from the SYCL spec to the headers directory and update the doc.

Adding licenses to files
========================

Use the reuse_ tool

Code examples::

  reuse addheader --copyright "The Khronos Group Inc." --year 2020 --license Apache-2.0 source/examples/host-task.cpp

Doc sources::

  reuse addheader --copyright "The Khronos Group Inc." --year 2020 --license CC-BY-4.0 source/index.rst


.. _headers: reference/headers
.. _`SYCL spec headers`: https://github.com/KhronosGroup/SYCL-Docs/tree/SYCL-1.2.1/master/latex/headers
.. _ReadTheDocs: https://sycl.readthedocs.io
.. _Sphinx: https://www.sphinx-doc.org/en/master
.. _reuse: https://pypi.org/project/reuse/
.. _python: https://www.python.org/downloads/windows/
.. _git: https://git-scm.com/download/win
.. _`clang-format`: https://llvm.org/builds/
