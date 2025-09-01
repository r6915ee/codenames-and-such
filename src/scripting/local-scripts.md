# Local Scripts

Local scripts are what this book refers to as scripts that share the same
namespace as proper [Gameplay Scripts](./gameplay.md).

Below is a table, detailing the various types of local scripts:

|Parent   |Location                   |
|---------|---------------------------|
|Stage    |`data/stages/{stage}.hx`   |
|Character|`data/characters/{char}.hx`|
|Event    |`data/events/{event}.hx`   |
|Notetype |`data/notes/{note}.hx`     |

Each one has an assigned **parent** that details their type. Each local
script only gets run when their parent is active; for example, in the case
of a stage script, then the stage would be active.

Do note that, in the case of a stage script, then the script has access
to the stage elements as variables.

## Callbacks

Shared with [Gameplay Scripts](./gameplay.md).
