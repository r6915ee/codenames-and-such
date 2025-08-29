# Installation

Codename provides *stable* and *nightly* releases.

> Warning:
> **Do note that Codename does not support mobile at the moment**.
> There are plans to make a mobile port, but progress has restarted in recent
> times.

## Dependencies

Although most dependencies are included with Codename builds, some users,
especially Linux users, should take into caution the dependencies.

Codename, like Friday Night Funkin' itself, requires at least
[SDL](https://www.libsdl.org/index.php) to actually run. Alongside this,
[libvlc](https://www.videolan.org/vlc/libvlc.html) needs to be installed.
Codename will **refuse to run** otherwise.

## Stable release

Stable releases are generally considered to be well-tested, and should have
most fixes. On occasion, **release candidates** are included for certain
stable releases, which provide a look at what a stable release might offer,
but may not be considered fully complete.

### GitHub

[GitHub](https://github.com/CodenameCrew/CodenameEngine/) provides stable
releases, as well as release candidates.

Under the **Releases** section, you are able to see the latest version, as
well as release candidates. Pick the appropriate platform you wish to use.

> Note:
> There are additional assets available that are
> prefixed with `update`. These have special properties and generally
> should not be used manually. The reason is that those are files that the
> **automatic updater** uses, which are not guaranteed to properly work using
> replacement. For this reason, if you want to manually update, download
> the regular build instead and replace the contents of your current Codename
> build with the new one.

Download the appropriate platform and extract it. Afterwards, run the program
as you normally would.

> Windows users: **Never, ever, put Codename in your Desktop directory**. This
> directory contains special properties that don't allow Codename to run
> properly. You should place it somewhere else, like your Documents directory.

### GameBanana, itch

[GameBanana](https://gamebanana.com/mods/598553) and
[itch](https://nex-isdumb.itch.io/codename-engine) both have entries for
Codename Engine. Simply download and extract the appropriate platform,
similarly to the [GitHub method](#GitHub) mentioned above.

## Nightly release

Although not the only way, above every other method for installing a nightly
release, you should almost always consider the website. The reason for this is
that it bypasses the GitHub account requirement when using typical GitHub
Actions. As such, this section will explicitly follow the website method.

On the main page for the website, there are download buttons just a little
below the large Codename logo. Simply press on the appropriate platform's
button and you should download and extract, as usual.
