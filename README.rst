======================
cookiecutter-pypackage
======================

Cookiecutter template for a Python package. See https://github.com/audreyr/cookiecutter.

* Free software: BSD license
* Pytest_ runner: Supports `unittest`, `pytest`, `nose` style tests and more
* Tox_ testing: Setup to easily test for python 2.7, 3.4
* Sphinx_ docs: Documentation raedy for generation with, for example, ReadTheDocs_
* Wheel_ support: Use the newest python package distribution standard from the get go

Usage
-----

Generate a Python package project::

    cookiecutter https://github.com/jaycee/cookiecutter-pypackage.git

Then:

* Create a repo and put it there.
* Add the repo to your ReadTheDocs account + turn on the ReadTheDocs service hook.
* Run `tox` to make sure all tests pass.
* Release your package the standard Python way.

Not Exactly What You Want?
--------------------------

Don't worry, you have options:

Similar Cookiecutter Templates
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* `audreyr/cookiecutter-pypackage`_: The original pypackage, uses unittest
for testing and other minor changes.
* `Nekroze/cookiecutter-pypackage`_: A fork of the original, adding py.test
support and other 

Fork This
~~~~~~~~~

Like everyone else making cookiecutter packages, if you want to change this a
lot, please fork it. I did to make this, you can too.

Or Submit a Pull Request
~~~~~~~~~~~~~~~~~~~~~~~~

I'll also be happy to look at pull requests for small changes. Big changes
should really just be their own cookiecutter package.

.. _Tox: http://testrun.org/tox/
.. _Sphinx: http://sphinx-doc.org/
.. _ReadTheDocs: https://readthedocs.org/
.. _`audreyr/cookiecutter-pypackage`: https://github.com/audreyr/cookiecutter-pypackage
.. _`Nekroze/cookiecutter-pypackage`: https://github.com/Nekroze/cookiecutter-pypackage
.. _Pytest: http://pytest.org/
.. _PyPy: http://pypy.org/
.. _Wheel: http://pythonwheels.com
