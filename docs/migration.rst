=============================
Migration to Package Helper 2
=============================

Package Helper is **no longer maintained**. It is replaced by `Package Helper 2`_: in order to make your workflow even
easier, Package Helper 2 uses GitHub actions instead of additional services, such as Travis-CI and ReadTheDocs. For
new projects, we recommend using Package Helper 2. For your existing packages that used Package Helper, here is a
migration guide to Package Helper 2.

#. Directory ``docs`` → file ``conf.py``. In the list ``extensions``, add ``'sphinx.ext.githubpages'``.

#. File ``requirements.txt``: if this file does not exist, create it at the root of your project.

   #. Ensure that the following lines are in the file::

        sphinx>=1.4
        sphinx-rtd-theme

   #. If you want to use jupyter notebooks in your documentation, ensure that you have also::

        nbsphinx
        ipykernel

#. File ``README.rst``:

   #. Replace the badges with the following lines::

        .. image:: https://img.shields.io/pypi/v/YOUR_PACKAGE_SLUG.svg
                :target: https://pypi.python.org/pypi/YOUR_PACKAGE_SLUG
                :alt: PyPI Status

        .. image:: https://github.com/YOUR_USERNAME/YOUR_PACKAGE_SLUG/workflows/build/badge.svg?branch=master
                :target: https://github.com/YOUR_USERNAME/YOUR_PACKAGE_SLUG/actions?query=workflow%3Abuild
                :alt: Build Status

        .. image:: https://github.com/YOUR_USERNAME/YOUR_PACKAGE_SLUG/workflows/docs/badge.svg?branch=master
                :target: https://github.com/YOUR_USERNAME/YOUR_PACKAGE_SLUG/actions?query=workflow%3Adocs
                :alt: Documentation Status

        .. image:: https://codecov.io/gh/YOUR_USERNAME/YOUR_PACKAGE_SLUG/branch/master/graphs/badge.svg
                :target: https://codecov.io/gh/YOUR_USERNAME/YOUR_PACKAGE_SLUG/branch/master/graphs
                :alt: Code Coverage

   #. In these lines, replace ``YOUR_PACKAGE_SLUG`` with your package slug and ``YOUR_USERNAME`` with your GitHub
      username.

   #. If you want, replace the ReadTheDocs url with: ``https://YOUR_USERNAME.github.io/YOUR_PACKAGE_SLUG/``. We will
      keep the two documentations alive anyway, so do as you please.

#. Download the :download:`workflows directory<_static/workflows.zip>`. Uncompress it into the ``.github`` directory
   of your project. For example, you should have a file ``.github/workflows/build.yml``.

#. Commit/push.

#. On the GitHub_ page of your package:

   #. Go to "Actions". Check that your actions pass properly.

   #. *Tell GitHub Pages that the documentation files are in the "gh-pages" branch of your project:*

      #. Settings → Options (= main page) → GitHub Pages → Source.
      #. Select "gh-pages".
      #. Save.

   #. *Register your PyPI credentials as "secrets", so that GitHub can automatically publish your package on PyPI for
      you:*

      #. Settings → Secrets.
      #. Select "New repository secret". Name: ``PYPI_USERNAME``. Value: your PyPI username.
      #. Select "New repository secret". Name: ``PYPI_PASSWORD``. Value: your PyPI password.

#. Leave your ReadTheDocs "hook" alive: this way, users can still access the documentation of your package at the url
   they know.

#. On Travis-CI_ website: remove the "hook" to your project. Since you won't use Travis-CI anymore, no need to waste
   power consumption.

   #. Go to: https://travis-ci.org/account/repositories .
   #. Put your package on "off".

.. _`Package Helper 2`: https://github.com/francois-durand/package_helper_2
.. _GitHub: https://github.com
.. _ReadTheDocs: https://readthedocs.org
.. _Travis-CI: https://travis-ci.com
