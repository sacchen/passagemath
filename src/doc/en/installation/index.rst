.. _installation-guide:

=============================================
Welcome to the passagemath Installation Guide
=============================================

This is the installation guide for passagemath, the free open-source mathematics software system.

There are two distinct ways to install passagemath, depending on your goal:

**Using passagemath (running the Sage REPL, notebooks, etc.)**
   `Installation from the provided binary wheels on PyPI <https://github.com/passagemath/passagemath?tab=readme-ov-file#full-installation-of-passagemath-from-binary-wheels-on-pypi>`__
   is the recommended method for most users. Simply run::

      pip install passagemath-standard

   This installs pre-built binary packages and does not require a copy of the source code.

**Developing or contributing to passagemath**
   If you want to modify the source code, fix bugs, or contribute new features,
   you should clone the repository and set up a development environment.
   See the project's ``setup.md`` (or the :ref:`sec-installation-from-sources` section)
   for instructions using ``git`` and ``uv``.

   You can also do both: install the binary wheels to conveniently run the Sage REPL,
   while separately cloning the repository for development work.


.. toctree::
   :maxdepth: 2

   conda
   source
   meson
   launching
   troubles
