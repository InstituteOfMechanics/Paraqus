.. _development:

Development
===========

Contributions to improve Paraqus are welcome and should be made as pull requests in the `GitHub repository <https://github.com/InstituteOfMechanics/Paraqus>`_.
In the following, some details of the package structure, implementation, and code style are summarized to help new contributors get up to speed.

Python versions
---------------

Paraqus is intended to run in a standalone Python interpreter, as well as in the Python interpreter shipped with Abaqus (Python 2.7 for releases before Abaqus 2024). The core functionality therefore must work with Python 2.X and 3.X. Abaqus-specific code in ``paraqus.abaqus`` does not need to be Python 3.X compatible.


Code style
----------

The Paraqus code style is based on `PEP 8 <https://peps.python.org/pep-0008/>`_, and is documented using Numpy style docstrings - a style guide can be found e.g. `here <https://numpydoc.readthedocs.io/en/latest/format.html>`_. We refrain from enforcing linting for commmits, but encourage contributions to adapt the style in the present code.


Package structure
-----------------

The core functionality is imported directly from the package root, for instance:

.. code-block:: python

   from paraqus import BinaryWriter

In addition to the general classes provided in the root package, the sub-package ``paraqus.abaqus`` provides functionality for the export from Abaqus, for example:

.. code-block:: python

   from paraqus.abaqus import OdbReader

Since the sub-package imports Abaqus-specific functions, it is not intended to be imported outside of the Abaqus Python interpreter (and will fail in that case).

For the same reason, the tests for Paraqus are implemented in a non-standard manner: they are located in another sub-package, called ``paraqus.tests``, and are executed directly from the package itself. In Abaqus Python, the tests are run as follows:

.. code-block:: python

   import paraqus.tests
   paraqus.tests.run_abaqus_tests()

In a Python interpreter outside of Abaqus, the tests are run by:

.. code-block:: python

   import paraqus.tests
   paraqus.tests.run_python_tests()

Both functions will generate a test report in a text file in the current working directory, called ``paraqus_test_report_abaqus.txt`` and ``paraqus_test_report_python.txt``. Note that ``run_abaqus_tests()`` includes all tests in ``run_python_tests()``, since all root package functionality is available from Abaqus, but not vice versa.


Releases
--------

When new functionality is merged into the main branch of Paraqus, a version bump should be performed (by changing the version number in the pyproject.toml). Afterwards, the release is manually pushed to the PyPI test server by the maintainers by running the corresponding GitHub action, which also checks if the non-Abaqus tests pass afterwards in a fresh installation. Only after this step completes successfully, a new release is actually pushed to PyPI by a second GitHub action.



