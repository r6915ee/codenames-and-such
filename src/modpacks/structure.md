# Modpack Structure

Codename uses a specific directory structure for modpacks; that is,
specific directories are for specific purposes. However, all of them can be
considered optional, with the exception of `data/config` in modern Codename.

## Generic Structure

A minimal mod should contain the following folders:

* `data`: Contains information about data, whether it be characters, stages,
  and even states. This also contains `data/config/modpack.ini`, which defines
  the configuration for your modpack using INI-style syntax. Upon entering
  a mod without this file in Developer Mode, Codename will typically display
  a warning and gives you the option to have Codename generate a sample
  configuration.
* `images`: Contains images for use in the game.
* `songs`: Contains global song scripts, as well as the actual songs
  themselves. A song takes up a subfolder in this directory, and possesses
  metadata in the form of a manifest, as well as the charts, audio assets,
  and scripts for the song.

More folders can also exist. Examples include:

* `fonts`: Includes TrueType fonts for use in the game.
* `shaders`: Includes OpenFL shaders.
* `sounds`: Contains OGG Vorbis sounds.
* `music`: Contains OGG Vorbis music.
* `videos`: Includes video files. MP4 and WebM are guaranteed to work.

Later pages will specify a relative path, but not entirely including typical
syntax. All paths will also use forward slashes (`/`) to denote directories,
being the general standard on most operating systems, excluding Windows.
Below are a few example paths:

* `data/config/modpack.ini`
* `songs/fresh/meta.json`
* `images/game/spinning-top.png`
