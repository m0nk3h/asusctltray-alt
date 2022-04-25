# asusctltray-alt

Alternate version for compatibility with [asus-x13-gpu-switching](https://github.com/hyphone/asus-x13-gpu-switching), and forked from the excellent [asusctltray](https://github.com/Baldomo/asusctltray)

This is a very simple hack to enable the alternate gfx switching mode for the Asus ROG Flow X13 2021 model.

This is a simple tray widget based on `appindicator` which lets the user change their ROG laptop power profiles and graphics mode on the fly. Easy turbo boost toggling is also included (it was temporarily removed from `asusctl`).

## Table of contents
- [asusctltray](#asusctltray)
  - [Table of contents](#table-of-contents)
  - [Installation](#installation)
    - [Manual install](#manual-install)
    - [Note for GNOME 40+ users](#note-for-gnome-40-users)
  - [Usage](#usage)
  - [Screenshots](#screenshots)

## Installation
This project depends on `AppIndicator3`. Refer to your distro's documentation/software repositories to install it (both the runtime and development files are needed).

### Manual install
Running the script `install.sh` as root will install `asusctltray` and `asusgetmode` to `/usr/local/bin`, the icon to `/usr/share/pixmaps` and the `asusctl.desktop` to `/usr/share/applications`. This makes the tray icon available in application menus.

### Note for GNOME 40+ users
GNOME dropped support for `appindicator`/tray icons (see [blog post](https://blogs.gnome.org/aday/2017/08/31/status-icons-and-gnome/) and [Status of Status Icons in GNOME Shell](https://discourse.gnome.org/t/status-of-status-icon-in-gnome-shell/6441)). 

Unofficial support for tray icons can be easily brought back to the shell with [ubuntu/gnome-shell-extension-appindicator](https://github.com/ubuntu/gnome-shell-extension-appindicator), which I tested with asusctltray and can recommend.

Moreover, GNOME users should check out the excellent [asusctl-gex](https://gitlab.com/asus-linux/asusctl-gex/-/tree/main) shell extension from the maintainers of `asusctl`.

## Usage
> ⚠️ `pkexec` is required for boost toggling

On click: open context menu with all the profiles, selecting one will apply it (`dbus` is used extensively for profile switching).
