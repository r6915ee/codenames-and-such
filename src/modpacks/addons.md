# Addons

Addons are a special type of modpack that exist in the addons subfolder, instead
of the mods subfolder, and are always loaded up. They are useful for defining
quick scripts to get things done more productively, but are also good for
new features, quality of life improvements, or even fully-fledged frameworks.

Modpacks can use a lot of data from an addon. So, this can lead to unique
setups, particularly with global scripts:

### Addon's `data/global.hx`:

```haxe
static function addonHandleData(data:Array) {
    trace(data);
}
```

### Mod's `data/global.hx`:

```haxe
function new() {
    addonHandleData([1, 2, 3]);
}
```

However, do note certain particularities:

* Any variable or function that is intended to be shared between modpacks
  should be labeled with the `static` keyword. Codename will raise an error
  about an unknown variable otherwise.
* Because variables and functions have the chance to not exist or be from the
  required addon, it's a good idea to check the existence of an addon using
  [`ModsFolder`](https://codename-engine.com/api-docs/funkin/backend/assets/ModsFolder).
