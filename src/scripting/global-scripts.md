# Global Scripts

Global scripts are unique scripts located directly under the `data` subfolder.
They are typically used to manage the entire mod.

A typical standard for global script names is simply `global.hx`, but any other
name can be supplied as well.

Global scripts are nowadays somewhat generic, since they were originally used
for handling state redirects by script, but have since had that functionality
deprecated in favor of configuring state redirects in the modpack
configuration. However, a lot can still be done with them.

## Callbacks

* `new`: Self-explanatory. This is nearly identical to the standard `create`
  callback.
* `focusLost`: Alternative name for `onFocusLost`.
* `focusGained`: Alternative name for `onFocus`.

### Time-based

* `<pre, post>Draw`: Standard drawing callbacks.
* `<pre, post>GameStart`: Callbacks that are emitted while setting up the game.
* `<pre, post>GameReset`: Callbacks that are typically issued while resetting
  the game.
* `<pre, post>StateSwitch`: Usually emmited in response to state switching.
  The former variation was originally used for state redirects, but that form
  of state redirects had been deprecated.
* `preStateCreate`: Called before creating a state using that state's `create`
  callback.

## Global Namespace

Interestingly, global scripts do not operate on something like a state.
Instead, they have their own namespace of sorts that each and every loaded
global script share through the `GlobalScript` class.

However, three separate methods exist to allow global scripts to interact with
each other. The simplest one is to define shared variables and functions as
static ones in order to provide the simplest syntax possible. As such, this
is what this book provides.

Consider the [example provided in Addons](../modpacks/addons.md#examples).
The `addonHandleData` function is defined as static. This allows the
possibility to use that function in other scripts as if it were part of that
script, which simplifies a lot of syntax.

### Examples

### Sharing an Array

#### Addon's global script:

```haxe
static var data:Array<Int> = [0, 1, 2, 3, 4];
```

#### Mod's global script:

```haxe
function new() {
    trace(data);
}
```
