Getting Started
===============

In this guide we will walk you through setting up your Briefcase environment
for development and testing. We will assume that you have a working Python 3
install. If you don't have Python 3 set up yet, this `guide
<https://docs.python.org/3/using/index.html>`__ will help you get started.

.. note::

    Briefcase (and the whole BeeWare toolchain) requires Python 3. Support for
    different Python 3 minor versions varies depending on the platform you're
    targeting; Python 3.5+ will give you the best results.

Install platform dependencies
-----------------------------

Next, you'll need to make sure you've got the platform-specific dependencies
for the platforms you're going to target.

Windows
~~~~~~~

* Install the `WiX toolset <http://wixtoolset.org>`__.

If you're using Windows 10, you may need to enable the .NET 3.5 framework on
your machine. Select "Programs and Features" from the Start menu, then "Turn
Windows features on or off", and ensure ".NET Framework 3.5 (Includes .NET 2.0
and 3.0)" is enabled.

Mac OSX
~~~~~~~

There are no additional dependencies required to support OSX.

Linux
~~~~~

You'll need install GTK+ 3.10 or later. This is the version that ships
starting with Ubuntu 14.04 and Fedora 20. You also need to install the Python
3 bindings to GTK+. If you want to use the WebView widget, you'll also need to
have WebKit, plus the GI bindings to WebKit installed. This means you'll need
to install the following:

* **Ubuntu 14.04** ``apt-get install python3-gi gir1.2-webkit2-3.0 libcairo2-dev pkg-config libgirepository1.0-dev``

* **Ubuntu 16.04+** ``apt-get install python3-gi gir1.2-webkit2-4.0 libcairo2-dev pkg-config``
  or ``apt-get install python3-gi gir1.2-webkit2-3.0 libcairo2-dev pkg-config libgirepository1.0-dev``

* **Fedora 20+** ``dnf install python3-gobject pywebkitgtk cairo-devel pkg-config libgirepository1.0-dev``
  or ``yum install python3-gobject pywebkitgtk cairo-devel pkg-config libgirepository1.0-dev``

* **Debian Stretch** ``apt-get install python3-gi gir1.2-webkit2-4.0 libcairo2-dev pkg-config libgirepository1.0-dev``

iOS
~~~

* Install XCode from the App store. Once you've installed XCode, you must also
  install the Xcode Command Line Tools. This can be done from the Preference
  panel within XCode itself.

Android
~~~~~~~

* Install `Android Studio <https://developer.android.com/studio/index.html>`__.
  When you start Android Studio for the first time, you'll be provided a wizard
  to configure your installation; select a "standard" installation.
* Put the ``sdk/tools``, ``sdk/platform-tools`` and ``sdk/tools/bin`` directories in your path.

  - On macOS: ``~/Library/Android/sdk/tools``, ``~/Library/Android/sdk/platform-tools`` and ``~/Library/Android/sdk/tools/bin``

* Set the ``ANDROID_SDK_HOME`` directory

  - On macOS: ``~/Library/Android/sdk``

* Update the SDKs::

    $ sdkmanager --update

* Create a virtual device image, following `these instructions <https://developer.android.com/studio/run/managing-avds.html>`__.

..    $ avdmanager create avd --package "system-images;android-22;google_apis;x86" --device "Nexus 5X" --name Nexus5X

..  If prompted about creating a custom hardware profile, answer "No".

..  cd $ANDROID_SDK_HOME/tools

* Install `Gradle <https://gradle.org/>`__.

* Start the emulator::

    $ emulator @Nexus_5X_API_22

Django
~~~~~~

If you are going to create a web app with Django, you need:

* Install an LTS version of `Node <https://nodejs.org/en/download/>`__ (6.9.x)
* Install `NPM <https://docs.npmjs.com/downloading-and-installing-node-js-and-npm>`__ 4.x or higher


Create a Virtual Environment
----------------------------

We recommend creating a `virtual environment` for your project. A virtual environment is a self-contained packaging of Python where you can install the libraries needed for this project without worrying about conflicting with your other projects.

Run these commands to create the directory for your project and set up the virtual environment:

.. code-block:: bash

    $ mkdir tutorial
    $ cd tutorial
    $ python3 -m venv venv
    $ . venv/bin/activate    # For Windows CMD: venv\Scripts\activate

The last command activates the virtual environment, which means that any libraries you install at this point will go into this environment.  See the `Python venv documentation <https://docs.python.org/3/library/venv.html>`_ for complete documentation of virtual environments.

.. note::

  On some versions the activate script may be in the venv/Scripts/ folder in which
  case swap: ``$ . venv/bin/activate`` for ``$ . venv/Scripts/activate``


Install Briefcase
-----------------

The next step is to install Briefcase:

.. code-block:: bash

    $ pip install briefcase

Install Toga
-------------

Next, install Toga into your virtual environment:

macOS or Linux
~~~~~~~~~~~~~~

.. code-block:: bash

    (venv) $ pip install --pre toga

Windows
~~~~~~~

.. code-block:: bash

    (venv) C:\...>pip install --pre toga

(note: a pre-release version of Toga is currently in use.)


Install PyCairo
----------------

PyCairo must also be installed. for this you need to install system dependencies
as PyCairo requires some headers. 

.. code-block:: bash

    (venv) C:\...>pip install pycairo


Next Steps
----------

You now have a working Briefcase environment, so you can :doc:`start the first
tutorial </tutorial/tutorial-0>`.
