=====================
diazotheme.goldilocks
=====================


Introduction
============

``diazotheme.goldilocks`` package provides diazo themes based on the `Goldilocks Approach CSS framework`_ 
using the **theming** and **packaging** features available for create `Diazo`_ theme
using `plone.app.theming`_.

``diazotheme.goldilocks`` package contains the following diazo implementations: 

- **Goldilocks Inverted Theme**, is the Goldilocks Inverted theme on diazo based.
- **Goldilocks Starter Theme**, is the Goldilocks Starter theme on diazo based.
- **Goldilocks Theme**, a diazo theme based for Goldilocks.


How to create a child theme
---------------------------

Any of the three theme folders can be used to create your own child theme, 
based on `diazoframework.goldilocks`_. You can either wrap the theme up in a package 
or you can create a zip file of the folder and upload that to the theme panel.

There are two ways of creating a child theme.


The package way
^^^^^^^^^^^^^^^

For this example, lets assume we are creating a package called
``diazotheme.newtheme`` and we will copy the ``starter`` theme in this 
package.

1. Created the ``diazotheme.newtheme`` package (for instance through ``paster`` script).

2. Copy ``diazotheme.goldilocks/diazotheme/goldilocks/starter`` to
   ``diazotheme.newtheme/diazotheme/newtheme/starter``.

3. Rename ``diazotheme.newtheme/diazotheme/newtheme/starter``
   to ``diazotheme.newtheme/diazotheme/newtheme/static`` (arbitrary
   name).

4. Add `<plone:static directory="static" name="newtheme" type="theme"/>`
   to ``diazotheme.newtheme/diazotheme/newtheme/configure.zcml``.

5. Change ``diazotheme.newtheme/diazotheme/newtheme/static/manifest.cfg``
   to reflect the changes, so: ::

        [theme]
        title = New theme
        description = Describe the new theme
        rules = /++theme++newtheme/rules.xml
        prefix = /++theme++newtheme
        doctype = <!DOCTYPE html>
        preview = preview.png


The zip file way
^^^^^^^^^^^^^^^^

Again, lets assume we use the ``theme`` theme and we want to end up
with the ``newtheme`` name.

1. Copy ``diazotheme.goldilocks/diazotheme/goldilocks/theme`` to your file system.

2. Rename ``theme`` to ``newtheme`` (the folder name will become the
   theme name in the theme panel)

3. Change ``newtheme/manifest.cfg``
   to reflect the changes, so: ::

        [theme]
        title = New theme
        description = Describe the new theme
        rules = /++theme++newtheme/rules.xml
        prefix = /++theme++newtheme
        doctype = <!DOCTYPE html>
        preview = preview.png

4. Customize your theme.

5. When you are finished customizing, create a zip archive of the 
   ``newtheme`` folder.

6. Upload the ``newtheme.zip`` in the plone theme panel.


Screenshots
===========


Goldilocks Inverted Theme
-------------------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/TH-code/diazotheme.goldilocks/raw/master/diazotheme/goldilocks/inverted/preview.png
  :alt: Goldilocks Inverted Theme
  :align: center


Goldilocks Theme
----------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/TH-code/diazotheme.goldilocks/raw/master/diazotheme/goldilocks/theme/preview.png
  :alt: Goldilocks Theme
  :align: center


Requirements
============

- From the Plone 4.1.x To the Plone 4.3 latest version (https://plone.org/download)
- The ``plone.app.theming`` package (*You will need enable it via "Add-ons" control 
  panel to use this package*)
- The ``diazoframework.goldilocks`` package (*You will need enable it via "buildout" 
  configuration to use this package*)

Features
========

- Provides the diazo rules for *Goldilocks Inverted* theme.
- Provides the diazo rules for *Goldilocks Starter* theme.
- Provides the diazo rules for *Goldilocks* theme.


Installation
============


Buildout
--------

If you are a developer, you might enjoy installing it via buildout.

For install ``diazotheme.goldilocks`` package add it to your ``buildout`` section's 
*eggs* parameter e.g.: ::

   [buildout]
    ...
    eggs =
        ...
        diazotheme.goldilocks


and then running ``bin/buildout``.

Or, you can add it as a dependency on your own product ``setup.py`` file: ::

    install_requires=[
        ...
        'diazotheme.goldilocks',
    ],


Resources
=========

This package is the parent of all Plone diazo themes and 
provides rule that are practical to use in other diazo themes.


Goldilocks Inverted Theme
-------------------------

The resources of this theme can be reached through

    ``/++theme++goldilocks-inverted``

There are placed at ``diazotheme.goldilocks/diazotheme/goldilocks/inverted`` 
directory with following resources files:

::

    _ inverted
      Provides the resources from "Goldilocks Inverted Theme".
      _ manifest.cfg
      _ preview.png
      _ rules.xml


Goldilocks Starter Theme
------------------------

The resources of this theme can be reached through

    ``/++theme++goldilocks-starter``

There are placed at ``diazotheme.goldilocks/diazotheme/goldilocks/starter`` 
directory with following resources files:

::

    _ starter
      Provides the resources from "Goldilocks Starter Theme".
      _ manifest.cfg
      _ rules.xml


Goldilocks Theme
----------------

The resources of this theme can be reached through

    ``/++theme++goldilocks``

There are placed at ``diazotheme.goldilocks/diazotheme/goldilocks/theme`` 
directory with following resources files:

::

    _ theme
      Provides the resources from "Goldilocks Theme".
      _ rules
        _ head
          _ theme.xml
      _ manifest.cfg
      _ preview.png
      _ rules.xml


Contribute
==========

- Issue Tracker: https://github.com/TH-code/diazotheme.goldilocks/issues
- Source Code: https://github.com/TH-code/diazotheme.goldilocks


License
=======

The project is licensed under the GPLv2.


Credits
-------

- Thijs Jonkman (t.jonkman at gmail dot com).


Amazing contributions
---------------------

- Leonardo J. Caballero G. aka macagua (leonardocaballero at gmail dot com).

You can find an updated list of package contributors on https://github.com/TH-code/diazotheme.goldilocks/contributors

.. _`Goldilocks Approach CSS framework`: http://goldilocksapproach.com/
.. _`Diazo`: http://diazo.org
.. _`plone.app.theming`: https://pypi.org/project/plone.app.theming/
.. _`diazoframework.goldilocks`: https://github.com/TH-code/diazoframework.goldilocks
.. _`diazotheme.goldilocks`: https://github.com/TH-code/diazotheme.goldilocks
