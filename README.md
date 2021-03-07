# SlapDash 1.0.1

## "One coin to rule them all!"

SlapDash is an RNG based cryptocurrency, the block mining reward is completely random, you could receive 1 - 100,000.00 SlapDash Coins as a block reward.
You can find the 100% open-source code for this project by going to the [/slapdash](https://github.com/limiteci/SlapDash/tree/main/SlapDash) folder in this repository.

![](SlapDash/esc/SlapDash.png)

### Usage

This coin is open-source and available to utilize in any way that you see fit. The included wallet application can be used to send/receive SlapDash currency and the application itself is your own. If you are interested in mining SlapDash crypto there is an included python based mining application in the repository along with instructions on how to run it. SlapDash is a currency tool that has not yet been implemented into any known cryptocurrency exchanges so as of right now the easiest way to accumulate SlapDash is by mining. SlapDash is a **scrypt** based cryptocurrency unlike the SHA256 blockchain that the **Bitcoin Network** runs off of.

 ## SlapDash Build instructions
===================

Debian
-------

First, make sure that the required packages for Qt4 development of your
distribution are installed, for Debian and Ubuntu these are:

::

    apt-get install qt4-qmake libqt4-dev build-essential libboost-dev libboost-system-dev \
        libboost-filesystem-dev libboost-program-options-dev libboost-thread-dev \
        libssl-dev libdb4.8++-dev

then execute the following:

::

    qmake
    make

Alternatively, install `Qt Creator`_ and open the `litecoin-qt.pro` file.

An executable named `litecoin-qt` will be built.

.. _`Qt Creator`: http://qt.nokia.com/downloads/

Windows
--------

Windows build instructions:

- Download the `Qt Windows SDK`_ and install it. You don't need the Symbian stuff, just the desktop Qt.

- Download and extract the `dependencies archive`_  [#]_, or compile openssl, boost and dbcxx yourself.

- Copy the contents of the folder "deps" to "X:\\QtSDK\\mingw", replace X:\\ with the location where you installed the Qt SDK. Make sure that the contents of "deps\\include" end up in the current "include" directory.

- Open the bitcoin-qt.pro file in Qt Creator and build as normal (ctrl-B)

.. _`Qt Windows SDK`: http://qt.nokia.com/downloads/sdk-windows-cpp
.. _`dependencies archive`: https://download.visucore.com/bitcoin/qtgui_deps_1.zip
.. [#] PGP signature: https://download.visucore.com/bitcoin/qtgui_deps_1.zip.sig (signed with RSA key ID `610945D0`_)
.. _`610945D0`: http://pgp.mit.edu:11371/pks/lookup?op=get&search=0x610945D0


Mac OS X
--------

- Download and install the `Qt Mac OS X SDK`_. It is recommended to also install Apple's Xcode with UNIX tools.

- Download and install `MacPorts`_.

- Execute the following commands in a terminal to get the dependencies:

::

	sudo port selfupdate
	sudo port install boost db48 miniupnpc

- Open the bitcoin-qt.pro file in Qt Creator and build as normal (cmd-B)

.. _`Qt Mac OS X SDK`: http://qt.nokia.com/downloads/sdk-mac-os-cpp
.. _`MacPorts`: http://www.macports.org/install.php


Build configuration options
============================

UPnP port forwarding
---------------------

To use UPnP for port forwarding behind a NAT router (recommended, as more connections overall allow for a faster and more stable litecoin experience), pass the following argument to qmake:

::

    qmake "USE_UPNP=1"

(in **Qt Creator**, you can find the setting for additional qmake arguments under "Projects" -> "Build Settings" -> "Build Steps", then click "Details" next to **qmake**)

This requires miniupnpc for UPnP port mapping.  It can be downloaded from
http://miniupnp.tuxfamily.org/files/.  UPnP support is not compiled in by default.

Set USE_UPNP to a different value to control this:

+------------+--------------------------------------------------------------------------+
| USE_UPNP=- | no UPnP support, miniupnpc not required;                                 |
+------------+--------------------------------------------------------------------------+
| USE_UPNP=0 | (the default) built with UPnP, support turned off by default at runtime; |
+------------+--------------------------------------------------------------------------+
| USE_UPNP=1 | build with UPnP support turned on by default at runtime.                 |
+------------+--------------------------------------------------------------------------+

Notification support for recent (k)ubuntu versions
---------------------------------------------------

To see desktop notifications on (k)ubuntu versions starting from 10.04, enable usage of the
FreeDesktop notification interface through DBUS using the following qmake option:

::

    qmake "USE_DBUS=1"

Generation of QR codes
-----------------------

libqrencode may be used to generate QRCode images for payment requests. 
It can be downloaded from http://fukuchi.org/works/qrencode/index.html.en, or installed via your package manager. Pass the USE_QRCODE 
flag to qmake to control this:

+--------------+--------------------------------------------------------------------------+
| USE_QRCODE=0 | (the default) No QRCode support - libarcode not required                 |
+--------------+--------------------------------------------------------------------------+
| USE_QRCODE=1 | QRCode support enabled                                                   |
+--------------+--------------------------------------------------------------------------+


Berkely DB version warning
==========================

A warning for people using the *static binary* version of Litecoin on a Linux/UNIX-ish system (tl;dr: **Berkely DB databases are not forward compatible**).

The static binary version of Litecoin is linked against libdb4.8 (see also `this Debian issue`_).

Now the nasty thing is that databases from 5.X are not compatible with 4.X.

If the globally installed development package of Berkely DB installed on your system is 5.X, any source you
build yourself will be linked against that. The first time you run with a 5.X version the database will be upgraded,
and 4.X cannot open the new format. This means that you cannot go back to the old statically linked version without
significant hassle!

.. _`this Debian issue`: http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=621425

Ubuntu 11.10 warning
====================

Ubuntu 11.10 has a package called 'qt-at-spi' installed by default.  At the time of writing, having that package
installed causes litecoin-qt to crash intermittently.  The issue has been reported as `launchpad bug 857790`_, but
isn't yet fixed.

Until the bug is fixed, you can remove the qt-at-spi package to work around the problem, though this will presumably
disable screen reader functionality for Qt apps:

::

    sudo apt-get remove qt-at-spi
    
### Licence Information

 You are free to edit this software in any way you would like to. If you need further information on the lince of this repository you can find that information in the [/license](https://github.com/limiteci/SlapDash/blob/main/LICENSE) folder.



