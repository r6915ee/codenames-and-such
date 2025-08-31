# Sparrow Atlases

Sparrow atlases are the standard form of spritesheets in anything Codename,
and are used in other places, such as the original Friday Night Funkin' and
[Psych Engine](https://github.com/ShadowMario/FNF-PsychEngine).

They usually come from Adobe Flash or any derivatives, as well as
[spritesheet generators](#sprite-sheet-generators) in most cases.

A sparrow atlas comprises of an image containing all of the frames, and then
an XML file declaring the metadata and **subtextures** of the spritesheet,
which are the frames present in the image.

## Filenames

Some special considerations need to be taken into in regards to filenames and,
by extension, subtextures.

Spritesheet generators will typically use the filename of each frame as a
subtexture's name by default. This is unfortunately plagued by the fact that
art programs will typically name exported images using project metadata and the
time of the export.

Generally, when you're naming subtextures, which includes frames in spritesheet
generators, they should follow a convention:

* `anim0000`
* `anim0001`
* `anim0002`

...where `anim` is replaced by the name of the animation, and the digits at
the end being the frame number of that animation. Any number of digits can be
included, but a *good* amount is four digits, which is present in the examples
above.

> Note: Some spritesheet generators may include the file extension in the
> subtexture names. You may either need to configure the program to exlude the
> file extension, or remove the file extension manually.
