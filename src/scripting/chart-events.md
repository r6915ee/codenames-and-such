# Chart Events

Chart event scripts share the same data as regular gameplay scripts, including
callbacks. However, they are **only** run when their attached chart event is
present in the chart.

While a direct chart event script is not necessary, in most cases, it can be
used without problem.

If the chart event is dependent on some other factor, like the stage, then
the management of the chart event should instead be handled by that other
factor's script, like a stage-specific flash (e.g. lightning).

Because chart events share the same namespace as regular gameplay scripts,
no examples are provided on this page.

## Callbacks

Shared with [Gameplay Scripts](./gameplay.md).
