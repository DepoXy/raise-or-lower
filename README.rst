@@@@@@@@@@@@@@@@@@
``raise-or-lower``
@@@@@@@@@@@@@@@@@@

Cross-platform shell interface to raise or minimize desktop windows.

- You can use this project on:

  - `GNOME Shell <https://wiki.gnome.org/Projects/GnomeShell>`__
    (using the `Wayland <https://wayland.freedesktop.org/>`__ display server);

  - `macOS <https://www.apple.com/os/macos/>`__; and

  - The (legacy)
    `X Window System <https://www.x.org/wiki/>`__
    (such as within the wonderful
    `MATE Desktop Environment <https://mate-desktop.org/>`__).

- See `Dependencies`_ for the requirements for your system.

#####
Usage
#####

Pass the name of the window you want to raise or lower.

- E.g., this will raise or lower the window titled "nvim"::

    $ ./bin/raise-or-lower "nvim"

  - If the command finds a window titled "nvim" and it
    does not have focus, that window will be raised atop
    ("to the front of") other windows, even if the window
    is currently minimized (or hidden).

    But if the identified window currently has focus, it'll
    be minimized (hidden) instead.

- If you want to disable the *toggle* functionality, so
  that if the window already has focus, nothing happens
  (it won't be minimized), use a special environment
  variable, ``RAISELOWER_RAISE_ONLY``, e.g.,::

    $ RAISELOWER_RAISE_ONLY=true ./bin/raise-or-lower "nvim"

- If the targeted window might have different names, you
  can pass more than one window title to match.

  - E.g., if you use the same browser window for email
    as well as for text messages, you might want to
    raise that window regardless of which tab is
    active, e.g.,::

    $ ./bin/raise-or-lower "Email" "Messages"

- Note that, generally, you won't call this command from
  the command line. You'll likely want to wire this command
  into some other mechanism.

  For example, the author uses this command with a number
  of different custom
  `GNOME Shell Keyboard Shortcuts
  <https://help.gnome.org/users/gnome-help/stable/keyboard-shortcuts-set.html.en>`__
  to front specific desktop windows (e.g., I have one
  shortcut that finds and fronts my email window, another
  that finds and fronts my music player, etc.).

  That said, you might enjoy a more robust solution
  for your keyboard shortcuts.

  - An excellent solution for GNOME keyboard shortcuts
    is the |run-or-raise|_
    `GNOME Shell extension <https://extensions.gnome.org/>`__

    You can easily |install-RoR|_.

.. |run-or-raise| replace:: ``run-or-raise``
.. _run-or-raise: https://github.com/CZ-NIC/run-or-raise

.. |install-RoR| replace:: install ``run-or-raise`` from its extension page
.. _install-RoR: https://extensions.gnome.org/extension/1336/run-or-raise/

############
Dependencies
############

- For GNOME Shell functionality, install the |window-calls|_ GNOME Shell extension.

- For macOS functionality, install the |Hammyspoony|_ |Hammerspoon|_ Spoon.

- For X Window System functionality, this project uses the built-in |wmctrl|_
  command.

.. |window-calls| replace:: ``window-calls``
.. _window-calls: https://extensions.gnome.org/extension/4724/window-calls/

.. |Hammyspoony| replace:: *Hammyspoony*
.. _Hammyspoony: https://github.com/DepoXy/macOS-Hammyspoony#🥄

.. |Hammerspoon| replace:: Hammerspoon
.. _Hammerspoon: https://www.hammerspoon.org/

.. |wmctrl| replace:: ``wmctrl``
.. _wmctrl: https://en.wikipedia.org/wiki/Wmctrl

################
Related Projects
################

This project is used by two of the author's other projects:

https://github.com/DepoXy/depoxy 🍯

https://github.com/DepoXy/gvim-open-kindness 🐬
