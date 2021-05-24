# WacomDisplayMap

Easily rotate the orientation of a Wacom graphics tablet, without having
to muck through a bunch of device lists.

## Authors

- Jason C. McDonald (CodeMouse92)

## Compatibility

This should work on any Debian-based system, and may also work on other Linux
systems. It is designed to work automatically with any graphics tablet that can
be controlled by `xsetwacom`.

**If you encounter any problems with any Linux system or Wacom tablet, please
report in Issues!**

## History

Many Ubuntu systems include a control panel for Wacom graphics tablets, but
some popular distributions (including Ubuntu MATE) don't. This handy script
allows you to quickly map your Wacom tablet to any connected display.

## Prerequisites

You must have the package `pcregrep` installed on your system, which should be
available from your system's default package repository. You should also have
`xsetwacom` on your system, which is usually pre-installed on Ubuntu by default.

## Installation

Simply place the `wacomrotate` file in a convenient place for scripts, and be sure
the location is included in your environment path. Mark the script as executable
via `chmod +x wacomrotate`.

Here's an example install, placing the script in your `/usr/local/bin`
directory. Note that we only need the `sudo` because we're working in a system
directory.

```bash
# Move to the location where the script will live.
$ cd /usr/local/bin
# Download the script file from GitHub directly.
$ sudo wget https://github.com/CodeMouse92/WacomRotate/raw/main/wacomrotate
# Make the script executable. (You are encouraged to read the file BEFORE doing this, so you know what it does.
$ sudo chmod +x wacomrotate
# Run the script, rotating to the default (landscape) orientation.
$ wacomrotate l
```

## Usage

To rotate the orientation of your graphics tablet, run `wacomrotate` with one of four possible arguments:

- `wacomrotate l` sets the orientation to the default landscape mode.
- `wacomrotate lf` flips the landscape orientation; this may also be considered "left-handed" mode.
- `wacomrotate p` sets the orientation to portrait mode, with the left side of the tablet being the new "top"
- `wacomrotate pf` flips the portrait orientation, so the left side of the tablet is the new "bottom"

First, it will search for compatible Wacom devices. If you receive the message...

> No Wacom stylus or eraser detected.

...be sure you've connected your Wacom graphics tablet to your computer.

Next, it will automatically detect the rotatable devices and adjust them as per your requested orientation.
