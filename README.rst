**Description**

This repo hosts the source files for the `After Effects Expression Reference` that will soon be hosted on an Aenhancers sub-directory. It is still in development, so feel free to contribute.

The original documentation can be found over at `Adobe <https://helpx.adobe.com/after-effects/using/expression-language-reference.html>`_

----

**Contribution**

Contributors are welcome and encouraged to suggest fixes, adjustments, notes/warnings, and anything else that may help the project.

----

**Build HTML Locally**

You may want to build the HTML locally before pushing, in order to ensure that the result is what you'd expect. These files aren't included in the git repo, nor are they used online; this is solely to create a local, offline version of the online docs.

- Install ``Python 2.7``
- Install ``pip``
- Navigate to the project directory and run ``pip install -r requirements.txt``
- Build the docs using ``make html``

----

**Admonitions Usage**

Currently, the following `admonitions <http://docutils.sourceforge.net/docs/ref/rst/directives.html#admonitions>`_ are in use in this project. Try to keep one piece of data per note, for easier parsing.

	.. note::
		Notes detail version added, and/or relevant pieces of information.

	.. tip::
		Tips supply helpful suggestions on usage or behaviours.

	.. warning::
		Warnings convey negative behaviours, or when something won't work the way you'd expect.

----

**Licensing & Ownership**

This project exists for educational purposes only. All content is copyright Adobe Systems Incorporated.
