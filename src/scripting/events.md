# Callback Events

Callback events, or simply just events, are containers of data for callbacks.
They are typically the only parameter of any callback.

A callback event is different from a [chart event](./chart-events.md) in that
callback events are used exclusively for scripting, while chart events are
instantiated through charts and operate only on [`PlayState`](./gameplay.md).

## Common Events

Some events that are typically used, but are not limited to, include:

* `CancellableEvent`: Perhaps the most used and inherited, `CancellableEvent`
  is good for cancelling some sort of action. For example, it can cancel the
  gameplay countdown.
* `NoteHitEvent`: A type of `CancellableEvent` that handles the state of note
  hits, as well as things that `PlayState` should take into account, like
  the health gain.
* `NoteMissEvent`: Ditto, but for note misses.
* `EventGameEvent`: Used for handling chart events. This extends
  `CancellableEvent`, but there is typically no need to cancel.

A full list of events and their API documentation can be seen
[here](https://codename-engine.com/api-docs/funkin/backend/scripting/events/).

## Custom Events

Custom events can be defined through [`DynamicEvent`](https://codename-engine.com/api-docs/funkin/backend/scripting/events/DynamicEvent),
but there is typically no need to do this. The option is available, though.
