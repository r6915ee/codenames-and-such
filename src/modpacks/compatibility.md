# Cross-compatibility

In general, a good way to test your mod for cross-compatibility is to have
playtesters on various platforms, to see how it performs and to look for
oddities.

Another valid option is to develop *entirely* on a platform other than Windows.
This is especially the case for Linux distributions, such as
[Ubuntu](https://ubuntu.com/desktop), [Fedora](https://fedoraproject.org/),
[Arch](https://archlinux.org/), and even [NixOS](https://nixos.org/) using
a runtime, as a few examples.

Use the console to look for filename errors, and correct them as usual.

## Wine and Derivatives

UNIX users in general have a tool called [Wine](https://www.winehq.org) that
allows users to run Windows games on UNIX. This includes macOS, since that
is based on UNIX to some capacity.

A fork of Wine exclusive to Linux users is
[Proton](https://github.com/ValveSoftware/Proton), which is also available
to Steam Deck users as SteamOS is based off of
[Arch Linux](https://archlinux.org/). This provides special enhancements to
make games work better.

Unfortunately, both of these tools aren't native, which is what this page is
for.

When playtesting on anything UNIX-based, including the Steam Deck, preferably
use a **native build** instead of Wine and/or Proton. This ensures that
filenames and other features work correctly and errors can be found more
easily. Development purely on either of these, especially on Linux, is also a
valid option if you want to ensure cross-compatibility.
