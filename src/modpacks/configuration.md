# Modpack Configuration

If you followed the previous page, you should have a file under `data/config`
called `modpack.ini`.

This file is the modpack's configuration file. It defines metadata for the mod,
but also details things like Discord Rich Presence, flags, and state redirects.

The modpack configuration file is in the INI/CFG syntax. If you have configured
tools like GNU GRUB manually before, then the syntax should be the same.

The following section will list entries that are included by the generated
configuration. You can tweak them to your liking.

## Available tables

### Common

This section prepends the entries below with `MOD_`.

|Option       |Default Value              |Description                     |
|-------------|---------------------------|--------------------------------|
|NAME         |"YOUR MOD NAME HERE"       |Mod name                        |
|DESCRIPTION  |"YOUR MOD DESCRIPTION HERE"|Mod description, e.g. a tagline |
|AUTHOR       |"YOU/YOUR TEAM HERE"       |Mod author, e.g. "Mod Team"     |
|VERSION      |"YOUR MOD'S VERSION HERE"  |Mod version, e.g. v0.1.0        |
|API_VERSION  |1                          |Engine API version (don't edit!)|
|DOWNLOAD_LINK|"YOUR MOD PAGE LINK HERE"  |Mod download link               |
|ICON         |"path/to/icon.png"         |Mod's window icon in PNG format |

### Flags

This section does not apply a prefix to the options.

|Option                |Default Value              |Description                    |
|----------------------|---------------------------|-------------------------------|
|DISABLE_WARNING_SCREEN|true                       |Disables WarningState          |
|DISABLE_LANGUAGES     |true                       |Disables multi-language support|

### Discord

This section uses the `MOD_DISCORD_` prefix.

|Option       |Default Value|Description            |
|-------------|-------------|-----------------------|
|CLIENT_ID    |""           |Application ID         |
|LOGO_KEY     |""           |Large image key to use |
|LOGO_TEXT    |""           |Large image key tooltip|

### State Redirects

This section is special, in that it's dynamic. All of the options here are
state names, and the values are either a class path or a custom state under
`data/states`. The generated configuration should include examples.

Additionally, a `force` variant is available for overriding state redirects
from other addons and/or mods.
