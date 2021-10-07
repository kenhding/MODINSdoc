Software Info
====

Apps are managed by Snap_ 

* **snap** is both the command line interface and the application package format
* **snapd** is the background service that manages and maintains your snaps
* **snapcraft** is the command and the framework used to build your own snaps
* **Snap Store** provides a place to upload your snaps, and for users to browse and install


To check whether an App is installed on the server:

::

   snap list
   

::

  Name               Version    Rev    Tracking       Publisher   Notes
  code               7f6ab548   75     latest/stable  vscode✓     classic
  core               16-2.51.7  11743  latest/stable  canonical✓  core
  pycharm-community  2021.2.2   252    latest/stable  jetbrains✓  classic

The ``Name`` column shows the app name which is the command to open it. E.g by typing ``code``, it opens VScode for you.


   
.. Note::

    IDE Apps such as VS code and pycharm support ssh remote development, which means you can install the IDE on your PC and work remotely on the server. Without X11, this gives a better visual experience.
    If the App you need is not installed, please call 7849.


.. _Snap: https://snapcraft.io/docs


   
   
