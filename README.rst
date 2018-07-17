==================
diazotheme.startup
==================


Introduction
============

``diazotheme.startup`` package provides diazo themes based on the *Initializr* 
using the **theming** and **packaging** features available for create Diazo_ theme
using `plone.app.theming`_.

`Initializr`_ is here to kick-start the development of your new projects. It generates templates 
based on HTML5 Boilerplate by allowing you to choose which parts you want or don't want 
from it. A `responsive template`_ has also been added to start from a basic design instead 
of a blank page.

`HTML5 Boilerplate`_ (sometimes called **H5BP**) is a front-end template based on *HTML5*. 
This is the biggest differentiator from Bootstrap—it’s a template, not a framework. 
Boilerplate is, according to its author, 

*"a package of useful contraptions, hacks, and cross-browser libraries."*

While Bootstrap contains strong rules for each element of an interface, Boilerplate is more 
geared to help you with a fast and smart launch of your new project. H5BP is not about rules; 
it’s about a quick start.

This package contains *five diazo themes* that are good to use as startups for 
new themes. Four of the themes are to be used with `Sunburst Theme`_ as Theme base. 

The *three default themes* options you get with `Initializr`_:

- **Startup Bootstrap Jumbotron Initializr** Theme, it's a HTML5 boilerplate 
  bootstap option based on `Bootstrap Jumbotron example`_. It's got the hero unit on 
  home and is making use of a lot of  trickery that has been expanded in 
  `diazotheme.bootstrap`_ package.

- **Startup Classic HTML5 Boilerplate Initializr** Theme, it's a bare bones diazo theme that just 
  gives you normalization and default text styling based on `Classic H5BP Initializr`_ template.

  The **H5BP** theme css and html has not been altered from the download, so with 
  new versions it should be a matter of dropping in new files.

- **Startup Responsive Initializr** Theme, it's a responsive option based on the
  *Jonathan Verrecchia* `responsive template`_ (except with plonified colors).

  There is the responsive theme, which only adds responsiveness to the 
  "`Sunburst Theme`_" theme base. It should be able to be used as an easy 
  responsification option to old style themes based on Sunburst. (Some style 
  altering will probably be necessary)

The *last two themes* are the *Plone Classic* and *Plone Sunburst* themes 
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


Startup Bootstrap Jumbotron Initializr Theme
--------------------------------------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/collective/diazotheme.startup/raw/master/diazotheme/startup/bootstrap/preview.png
  :alt: Startup Bootstrap Jumbotron Initializr Theme
  :align: center


Startup Plone Classic Theme
---------------------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/collective/diazotheme.startup/raw/master/diazotheme/startup/classic/preview.png
  :alt: Startup Plone Classic Theme
  :align: center


Startup Classic HTML5 Boilerplate Initializr Theme
--------------------------------------------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/collective/diazotheme.startup/raw/master/diazotheme/startup/h5bp/preview.png
  :alt: Startup Classic HTML5 Boilerplate Initializr Theme
  :align: center


Startup Responsive Initializr Theme
-----------------------------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/collective/diazotheme.startup/raw/master/diazotheme/startup/responsive/preview.png
  :alt: Startup Responsive Initializr Theme
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

- Provides the diazo rules for *Startup Bootstrap Jumbotron Initializr* theme.
- Provides the diazo rules for *Startup Plone Classic* theme.
- Provides the diazo rules for *Startup Classic HTML5 Boilerplate Initializr* theme.
- Provides the diazo rules for *Startup Responsive Initializr* theme.
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


Startup Bootstrap Jumbotron Initializr
--------------------------------------

The resources of this theme can be reached through

    ``/++theme++startup_initializr_bootstrap``

There are placed at ``diazotheme.startup/diazotheme/startup/bootstrap`` 
directory with following resources files:

::

    _ bootstrap
      Provides the resources from "Startup Bootstrap Jumbotron Initializr Theme".
      _ css
      _ img
      _ js
      _ index.html
      _ manifest.cfg
      _ preview.png
      _ README.txt
      _ rules.xml


Startup Plone Classic
---------------------

The resources of this theme can be reached through

    ``/++theme++startup_classic``

There are placed at ``diazotheme.startup/diazotheme/startup/classic`` 
directory with following resources files:

::

    _ classic
      Provides the resources from "Startup Plone Classic Theme".
      _ css
      _ img
      _ index.html
      _ manifest.cfg
      _ preview.png
      _ rules.xml


Startup Classic HTML5 Boilerplate Initializr
--------------------------------------------

The resources of this theme can be reached through

    ``/++theme++startup_initializr_h5bp``

There are placed at ``diazotheme.startup/diazotheme/startup/h5bp`` 
directory with following resources files:

::

    _ h5bp
      Provides the resources from "Startup Classic HTML5 Boilerplate Initializr Theme".
      _ css
      _ img
      _ js
      _ index.html
      _ manifest.cfg
      _ preview.png
      _ README.txt
      _ rules.xml


Startup Responsive Initializr
-----------------------------

The resources of this theme can be reached through

    ``/++theme++startup_initializr_responsive``

There are placed at ``diazotheme.startup/diazotheme/startup/responsive`` 
directory with following resources files:

::

    _ responsive
      Provides the resources from "Startup Responsive Initializr Theme".
      _ css
      _ img
      _ js
      _ index.html
      _ manifest.cfg
      _ preview.png
      _ README.txt
      _ rules.xml


Startup Plone Sunburst
----------------------

The resources of this theme can be reached through

    ``/++theme++startup_sunburst``

There are placed at ``diazotheme.startup/diazotheme/startup/sunburst`` 
directory with following resources files:

::

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
.. _`responsive template`: http://verekia.com/initializr/responsive-template
.. _`Sunburst Theme`: https://github.com/plone/plonetheme.sunburst
.. _`Classic Theme`: https://github.com/plone/plonetheme.classic
.. _`Bootstrap Jumbotron example`: https://getbootstrap.com/docs/3.3/examples/jumbotron/
.. _`diazotheme.bootstrap`: https://github.com/TH-code/diazotheme.bootstrap
.. _`Classic H5BP Initializr`: https://github.com/h5bp/html5-boilerplate/blob/v4.3.0/doc/TOC.md
.. _`HTML5 Boilerplate`: https://html5boilerplate.com/
.. _`diazotheme.startup`: https://github.com/collective/diazotheme.startup
.. _`Diazo`: http://diazo.org
.. _`plone.app.theming`: https://pypi.org/project/plone.app.theming/
