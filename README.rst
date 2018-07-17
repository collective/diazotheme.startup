==================
diazotheme.startup
==================


Introduction
============

``diazotheme.startup`` package provides diazo themes based on the `Initializr`_ 
using the **theming** and **packaging** features available for create Diazo_ theme
using `plone.app.theming`_.

This package contains six diazo themes that are good to use as startups for 
new themes. Four of the themes are to be used with `Sunburst Theme`_ as Theme base. The three
default options you get with `Initializr`_:

- **Startup Initializr Bootstrap Jumbotron** Theme, it's a HTML5 boilerplate 
  bootstap option based on `Bootstrap Jumbotron example`_. It's got the hero unit on 
  home and is making use of a lot of  trickery that has been expanded in 
  `diazotheme.bootstrap`_ package.

- **Startup Initializr HTML5 Boilerplate** Theme, it's a bare bones diazo theme that just 
  gives you normalization and default text styling based on `Classic H5BP template`_.

  The H5BP theme css and html has not been altered from the download, so with 
  new versions it should be a matter of dropping in new files.

- **Startup Initializr Responsive** Theme, it's a responsive option based on 
  `Jonathan Verrecchia Responsive template`_ (except with plonified colors).

  There is the responsive theme, which only adds responsiveness to the 
  "`Sunburst Theme`_" theme base. It should be able to be used as an easy 
  responsification option to old style themes based on Sunburst. (Some style 
  altering will probably be necessary)

The last two themes Classic and Sunburst are the sunburst and classic themes 
applied to the "(unstyled)" theme base. These would be practical to use as
a basis for fully functional themes (edit included), because they are near 
identical and they therefore all the default javascript works. 

- **Startup Plone Classic** Theme, a diazo theme for Plone `Classic Theme`_.

- **Startup Plone Sunburst** Theme, a diazo theme for Plone `Sunburst Theme`_.


How to create a child theme
---------------------------

Any of the three theme folders can be used to create your own theme. You can either 
wrap the theme up in a package or you can create a zip file of the folder and upload 
that to the theme panel.

There are two ways of creating a child theme.


The package way
^^^^^^^^^^^^^^^

For this example, lets assume we are creating a diazo package theme called
``newtheme`` and we will copy the ``h5bp`` theme in this 
package.

1. Created the ``diazotheme.newtheme`` package (for instance through ``paster`` script).

2. Copy ``diazotheme.startup/diazotheme/startup/h5bp`` to
   ``diazotheme.newtheme/diazotheme/newtheme``.

4. Add `<plone:static directory="newtheme" name="startup_initializr_newtheme" type="theme"/>`
   to ``diazotheme.startup/diazotheme/startup/configure.zcml``.

5. Change ``diazotheme.startup/diazotheme/startup/newtheme/manifest.cfg``
   to reflect the changes, so: ::

        [theme]
        title = New theme
        description = Describe the new theme
        rules = /++theme++startup_initializr_newtheme/rules.xml
        prefix = /++theme++startup_initializr_newtheme
        doctype = <!DOCTYPE html>
        preview = preview.png


The zip file way
^^^^^^^^^^^^^^^^

Again, lets assume we use the ``theme`` theme and we want to end up
with the ``newtheme`` name.

1. Copy ``diazotheme.startup/diazotheme/startup/h5bp`` to your file system.

2. Rename ``h5bp`` to ``newtheme`` (the folder name will become the
   theme name in the theme panel)

3. Change ``newtheme/manifest.cfg``
   to reflect the changes, so: ::

        [theme]
        title = New theme
        description = Describe the new theme
        rules = /++theme++startup_initializr_newtheme/rules.xml
        prefix = /++theme++startup_initializr_newtheme
        doctype = <!DOCTYPE html>
        preview = preview.png

4. Customize your theme.

5. When you are finished customizing, create a zip archive of the 
   ``newtheme`` folder.

6. Upload the ``newtheme.zip`` in the plone theme panel.


Screenshots
===========


Startup Initializr Bootstrap Jumbotron Theme
--------------------------------------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/collective/diazotheme.startup/raw/master/diazotheme/startup/bootstrap/preview.png
  :alt: Startup Initializr Bootstrap Jumbotron Theme
  :align: center


Startup Plone Classic Theme
---------------------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/collective/diazotheme.startup/raw/master/diazotheme/startup/classic/preview.png
  :alt: Startup Plone Classic Theme
  :align: center


Startup Initializr HTML5 Boilerplate Theme
------------------------------------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/collective/diazotheme.startup/raw/master/diazotheme/startup/h5bp/preview.png
  :alt: Startup Initializr HTML5 Boilerplate Theme
  :align: center


Startup Initializr Responsive Theme
-----------------------------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/collective/diazotheme.startup/raw/master/diazotheme/startup/responsive/preview.png
  :alt: Startup Initializr Responsive Theme
  :align: center


Startup Plone Sunburst Theme
----------------------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/collective/diazotheme.startup/raw/master/diazotheme/startup/sunburst/preview.png
  :alt: Startup Plone Sunburst Theme
  :align: center


Requirements
============

- From the Plone 4.1.x To the Plone 4.3 latest version (https://plone.org/download)
- The ``plone.app.theming`` package (*You will need enable it to use this package*)


Features
========

- Provides the diazo rules for "Startup Initializr Bootstrap Jumbotron* theme.
- Provides the diazo rules for *Startup Plone Classic* theme.
- Provides the diazo rules for *Startup Initializr HTML5 Boilerplate* theme.
- Provides the diazo rules for *Startup Initializr Responsive* theme.
- Provides the diazo rules for *Startup Plone Sunburst* theme.


Installation
============


Buildout
--------

If you are a developer, you might enjoy installing it via buildout.

For install ``diazotheme.startup`` package add it to your ``buildout`` section's 
*eggs* parameter e.g.: ::

   [buildout]
    ...
    eggs =
        ...
        diazotheme.startup


and then running ``bin/buildout``.

Or, you can add it as a dependency on your own product ``setup.py`` file: ::

    install_requires=[
        ...
        'diazotheme.startup',
    ],


Resources
=========

This package is the parent of all Plone diazo themes and 
provides rule that are practical to use in other diazo themes.

The resources of this framework can be reached through

- **Startup Initializr Bootstrap Jumbotron** Theme
    ``/++theme++startup_initializr_bootstrap``
- **Startup Plone Classic** Theme
    ``/++theme++startup_classic``
- **Startup Initializr HTML5 Boilerplate** Theme
    ``/++theme++startup_initializr_h5bp``
- **Startup Initializr Responsive** Theme
    ``/++theme++startup_initializr_responsive``
- **Startup Plone Sunburst** Theme
    ``/++theme++startup_sunburst``

There are placed at ``diazotheme.startup/diazotheme/startup/`` directory 
with following resources files:

::

    _ bootstrap
      Provides the resources from "Startup Initializr Bootstrap Jumbotron Theme".
      _ css
      _ img
      _ js
      _ index.html
      _ manifest.cfg
      _ preview.png
      _ README.txt
      _ rules.xml
      
    _ classic
      Provides the resources from "Startup Plone Classic Theme".
      _ css
      _ img
      _ index.html
      _ manifest.cfg
      _ preview.png
      _ rules.xml
      
    _ h5bp
      Provides the resources from "Startup Initializr HTML5 Boilerplate Theme".
      _ css
      _ img
      _ js
      _ index.html
      _ manifest.cfg
      _ preview.png
      _ README.txt
      _ rules.xml
      
    _ responsive
      Provides the resources from "Startup Initializr Responsive Theme".
      _ css
      _ img
      _ js
      _ index.html
      _ manifest.cfg
      _ preview.png
      _ README.txt
      _ rules.xml
      
    _ sunburst
      Provides the resources from "Startup Plone Sunburst Theme".
      _ css
      _ img
      _ index.html
      _ manifest.cfg
      _ preview.png
      _ README.txt
      _ rules.xml


Contribute
==========

- Issue Tracker: https://github.com/collective/diazotheme.startup/issues
- Source Code: https://github.com/collective/diazotheme.startup


License
=======

The project is licensed under the GPLv2.


Credits
-------

- Thijs Jonkman (t.jonkman at gmail dot com).


Amazing contributions
---------------------

- Leonardo J. Caballero G. aka macagua (leonardocaballero at gmail dot com).

You can find an updated list of package contributors on https://github.com/collective/diazotheme.startup/contributors

.. _`Initializr`: http://www.initializr.com/
.. _`Sunburst Theme`: https://github.com/plone/plonetheme.sunburst
.. _`Classic Theme`: https://github.com/plone/plonetheme.classic
.. _`Bootstrap Jumbotron example`: https://getbootstrap.com/docs/3.3/examples/jumbotron/
.. _`diazotheme.bootstrap`: https://github.com/TH-code/diazotheme.bootstrap
.. _`Classic H5BP template`: https://github.com/h5bp/html5-boilerplate/blob/v4.3.0/doc/TOC.md
.. _`Jonathan Verrecchia Responsive template`: http://verekia.com/initializr/responsive-template
.. _`diazotheme.startup`: https://github.com/collective/diazotheme.startup
.. _`Diazo`: http://diazo.org
.. _`plone.app.theming`: https://pypi.org/project/plone.app.theming/
