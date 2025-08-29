# Creating a Modpack

Creating a modpack is as simple as creating a subfolder in the mods directory.
The same applies for [addons](./addons.md).

## Upon startup

When you start up the mod for the first time, a warning will typically be
dispatched, asking you whether or not you want the engine to create the
modpack's configuration file:

![A warning on a black screen with a title of "Missing mod folder
configuration" states: "Your mod is currently missing a mod config file!
Would you like to automatically generate one? (PS: If this is not your mod
please disable Developer Mode to stop this popup from appearing.)" Two
buttons, each labeled "Not Now" and "Yes" respectively, are present on the
warning.](../img/modpack-config-warning.png)

In most cases, you should allow the engine to generate the configuration file.
This file is responsible for defining the metadata of your mod, as well as
additional things, like Discord Rich Presence and state redirects. However,
in certain cases, you may not want to have a configuration file at all, such
as with testing.

There is also an option that should theoretically disable this popup right
beside [Developer Mode](../setup/developer-mode.md) while keeping that state
intact.
