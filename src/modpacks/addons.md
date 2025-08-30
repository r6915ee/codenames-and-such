# Addons

Addons are a special type of modpack that exist in the addons subfolder, instead
of the mods subfolder, and are always loaded up. They are useful for defining
quick scripts to get things done more productively, but are also good for
new features, quality of life improvements, or even fully-fledged frameworks.

Modpacks can use a lot of data from an addon. So, this can lead to unique
setups, particularly with [global scripts](../scripting/global-scripts.md).

## Examples

### Addon's global script:

```haxe
static function addonHandleData(data:Array) {
    trace(data);
}
```

### Mod's global script:

```haxe
function new() {
    addonHandleData([1, 2, 3]);
}
```

## Caveats
However, do note that, because variables and functions have the chance to not
exist or be from the required addon, it's a good idea to check the existence of
an addon using
[`ModsFolder`](https://codename-engine.com/api-docs/funkin/backend/assets/ModsFolder).
