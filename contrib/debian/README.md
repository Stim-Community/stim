
Debian
====================
This directory contains files used to package stimd/stim-qt
for Debian-based Linux systems. If you compile stimd/stim-qt yourself, there are some useful files here.

## stim: URI support ##


stim-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install stim-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your stim-qt binary to `/usr/bin`
and the `../../share/pixmaps/stim128.png` to `/usr/share/pixmaps`

stim-qt.protocol (KDE)

