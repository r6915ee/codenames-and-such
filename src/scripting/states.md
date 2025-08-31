# State Scripts

State scripts either extend a state, just like a stage or
[gameplay script](./gameplay.md) with their respective data, but can also be
custom states using two features:
[`ModState`s](https://codename-engine.com/api-docs/funkin/backend/scripting/ModState)
and **state redirects**. The following applies to substates as well.

## Callbacks

* `<step, beat, measure>Hit{Int}`: Called per the unit of song measurement used.
* `onFocus`: Called when the window has been focused.
* `onFocusLost`: Called when the window has lost focus.
* `onStateSwitch{StateEvent}`: Gets ran whenever the state is switched.
* `onOpenSubState{StateEvent}`: Gets ran whenever a substate is opened.
* `onResize{ResizeEvent}`: Gets called whenever the window is resized.
* `destroy`: Issued whenever the state's memory is cleaned up.

### Time-based

* `[pre, post](c)reate`: Called when creating the state/substate.
* `[pre, post](u)pdate{Float}`: Called once per frame.
* `[post](d)raw{DrawEvent}`: Called once per draw.

## ModState

`ModState` is the core functionality for custom states, and is also used by
the state redirects feature. It defines a custom state to use.

You can switch to a pure `ModState` using:

```haxe
FlxG.switchState(new ModState("state"));
```

This will issue a regular state switch. The `ModState` constructor takes the
state filename (under `data/states` and without the file extension).
Additionally, some `Dynamic` data can be passed to the `ModState` from the
current one, usually in the JSON format.

Substates should use `ModSubState` instead. It provides mostly the same
functionality, but instead operates on substates. The example above would
instead be this with `ModSubState`:

```haxe
openSubState(new ModSubState("substate"));
```

## State Redirects

State redirects can be configured using the [modpack
configuration](../modpacks/configuration.md), under the `StateRedirects`
section.

> Warning: State redirects will only work if no script exists under the same
> name as the state it's replacing. In that case, it's a simple state
> extension.

```ini
[StateRedirects]
MainMenuState="mainMenu"
```

This example sets the main menu to redirect to the custom state,
`data/states/mainMenu.hx`. All this does is intercept the state switching
mechanism to use a `ModState` if a state redirect is available.

## Custom Transitions

It is possible to load a custom transition between states using either the
modpack configuration, or
[`MusicBeatTransition`](https://codename-engine.com/api-docs/funkin/backend/MusicBeatTransition)'s
`script` property.

The following demonstrates a sample configuration that sets the
`DEFAULT_TRANSITION_SCRIPT` flag to point to a custom transition script:

```ini
[Flags]
# Note: Script paths in these kinds of flags need to be full; they aren't
# handled automatically.
DEFAULT_TRANSITION_SCRIPT="data/states/transition.hx"
```

### Callbacks

* `destroy`: Called upon the memory for the transition being cleaned up.
  Simply put, this is when the transition has finished and needs to be removed.
* `onSkip{CancellableEvent}`: Transitions can be skipped by holding the shift
  key. The event for this can be cancelled in order to avoid this behavior.

#### Time-based

* `[post](c)reate{TransitionCreationEvent}`: Called upon the transition being
  created. The normal variant can be cancelled to prevent the `post` variant
  from running.
* `[post](u)pdate{Float}`: Called once every frame.
* `on[Post]Finish{[CancellableEvent]}`: Called when the transition has
  finished. This may be cancelled to stop the state from switching, and to
  stop the `post` variant from running.
  > Note: The `post` variant does not take an event.

## Special Cases

### Pause Menu

The `DEFAULT_PAUSE_SCRIPT` flag should be able to set an extension for the
pause menu if you don't want to name the script the same name as
`PauseSubState`.

```ini
[Flags]
DEFAULT_PAUSE_SCRIPT="data/states/pause.hx"
```

Do note, however, that **this is not equivalent to a state redirect, nor is
that possible to do using the configuration**. Instead, you may want to do the
following in a [gameplay script](./gameplay.md):

```haxe
function onGamePause(event:CancellableEvent) {
    event.cancel();
    // The following is done in order to make sure that the game pauses
    // correctly.
    persistentUpdate = false;
    persistentDraw = true;
    paused = true;
    // Finally, open the substate!
    openSubState(new ModSubState("pause"));
}
```
