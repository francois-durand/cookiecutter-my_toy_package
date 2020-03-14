========
Tutorial
========

My Toy Package helps you create and maintain a package. If you use all the tools presented in this tutorial, things
will work this way:

* You create the file structure of your package in less than a minute with **cookiecutter**.

* You use the **PyCharm** IDE. It is configured to generate the documentation of your package locally and to run unit
  tests.

* Your project is on **GitHub**. When you push modifications:

    * **ReadTheDocs** automatically generates the documentation and publishes it online.
    * **Travis CI** automatically runs the unit tests on several versions of Python,
    * **Codecov** displays what parts of the package are covered by the unit tests.

* When you "draft a release" on GitHub: Travis CI not only performs the tests but also publishes your package on
  **PyPI**. This way, any Python user can install the package via ``pip install``.

* Generally, you use some external packages during the development process of your own package, for example ``sphinx``,
  ``pytest``, etc. These packages and their versions are listed in the file ``requirements_dev.txt`` of your package, so
  that each member of your team know which version is used. **PyUp** informs you when a new version of these
  third-party packages is released: you receive a pull request in GitHub and you just have to accept it.

Tick the tools that you want to use:

.. raw:: html

    <form>
        <ul style="list-style-type:none">
            <li><input type="checkbox" checked onchange="switchVisibility(this, 'venv')"> Virtualenv: virtual
                environment.</li>
            <li><input type="checkbox" checked onchange="switchVisibility(this, 'github')"> Github: collaborative
                version control.
            <ul style="list-style-type:none">
                <li><input type="checkbox" checked onchange="switchVisibility(this, 'readthedocs')"> ReadTheDocs: put a
                    beautiful documentation of the package on the web.</li>
                <li><input type="checkbox" checked onchange="switchVisibility(this, 'travis')"> Travis: run tests with
                    different versions of Python.
                <ul style="list-style-type:none">
                    <li><input type="checkbox" checked onchange="switchVisibility(this, 'pypi')"> PyPI: make the package
                        installable by "pip install".</li>
                    <li><input type="checkbox" checked onchange="switchVisibility(this, 'codecov')"> Codecov: check if
                        the unit tests cover the whole package.</li>
                </ul>
                </li>
                <li><input type="checkbox" checked onchange="switchVisibility(this, 'pyup')"> Pyup: maintain the
                    development requirements up to date.</li>
            </ul>
            </li>
        </ul>

-------------------------------
Preliminaries: Once and for All
-------------------------------

.. raw:: html
   :file: _static/preliminaries.html

-------------------
Create Your package
-------------------

.. raw:: html
   :file: _static/create_your_package.html

-------------------------------
During the Life of Your Package
-------------------------------

.. raw:: html
   :file: _static/during_the_life_of_your_package.html
