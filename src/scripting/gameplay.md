# Gameplay Scripts

Gameplay scripts are scripts that, true to their name, affect gameplay. In
particular, they affect
[`PlayState`](https://codename-engine.com/api-docs/funkin/game/PlayState),
which is the gamestate responsible for main gameplay. The state is a standard
feature of most HaxeFlixel projects.

Gameplay scripts will generally either go directly under the `songs` subfolder
as a global song script, or into a respective song's `scripts` subfolder.

Gameplay scripts are able to modify `PlayState` in nearly every shape. They are,
however, a category of scripts in general. Things like state scripts follow
similar callbacks.

For certain functionality, some knowledge of the `PlayState` API is required.
The following examples use some parts of the API on the documentation.

## Callbacks

* `onStageXMLParsed{StageXMLEvent}`: Called once the stage definition has been
  parsed successfully.
* `onStageNodeParsed{StageNodeEvent}`: Called once a stage node has been
  parsed successfully.
* `onRatingUpdate{RatingUpdateEvent}`: Gets called upon the rating being
  updated.
* `on<Player, Dad, Note>Hit{NoteHitEvent}`: Called upon a note being hit
  during gameplay. `Player` is for the player, `Dad` is for the opponent,
  and `Note` is generic.
* `onCameraMove{CamMoveEvent}`: Issued whenever `camGame` moves.
* `onEvent{EventGameEvent}`: Despite the interesting name, this callback is
  actually issued as a result of a chart event being triggered.
* `onSubstate<Open, Close>{StateEvent}`: Gets triggered manually by
  `PlayState`.
* `onGamePause{CancellableEvent}`: Issued whenever the game is paused upon
  entering the pause menu.

### Time-based

* `on<Pre, Post>GenerateStrums{AmountEvent}`: Emitted in time for strum
  generation.
* `on[Post]NoteCreation{NoteCreationEvent}`: Called on note creation.
* `on[Post]StartCountdown{[CancellableEvent]}`: Called when starting the
  countdown.
  > Note: The `post` variant does not supply an event.
* `on[Post]Countdown{CountdownEvent}`: Ditto, but provides additional
  configuration.
* `onSong<Start, End>`: Each one gets called based on the position of the
  Conductor. However, `onSongStart` is issued before Discord Rich Presence and
  the music are actually initialized.
* `on[Post]InputUpdate{[InputSystemEvent]}`: Issued whenever the input gets
  updated.
  > Note: The `post` varaint does not supply an event.
* `on[Post]PlayerMiss{NoteMissEvent}`: Called when the player misses.
* `on[Post]GameOver{GameOverEvent}`: Issued upon the player receiving a Game
  Over.
* `onVocalsResync`: This is a special callback that is a result of an internal
  function of `PlayState`. It generally does not need to be used, but is
  available if you wish to use the functionality.

### Special Cases

* `onStartSong`: This is similar to `onSongStart`, and is issued in the same
  function internally. The only difference is that `onStartSong` is called
  after the music assets have begun playing and Discord Rich Presence has
  been updated.

## Examples

### Zoom Out Camera on Specific Camera Selection

```haxe
function onCameraMove(event:CamMoveEvent) {
  switch (curCameraTarget) {
    case 0:
      defaultCamZoom = 0.7;
    case 1:
      defaultCamZoom = 0.9;
  }
}
```

* `curCameraTarget` is an integer variable that describes which strumline
  `camGame` has to hover over.
* `defaultCamZoom` defines the zoom level to tween to by default for `camGame`.

### Use Losing Icon As Winning For Dad

```haxe
function postCreate() {
  iconP2.healthSteps = [0 => 0, 80 => 1];
}
```

* `iconP1` and `iconP2` are the health icons for the player and opponent,
  respectively. `iconP2` is used here.
* `healthSteps` is a property of a health icon in the form of a `Map`, where
  the key is the percentage of health and the value is the frame index or the
  animation name. It essentially sets at what percentage the health should be
  at for the character to use a certain icon. This property will typically be
  set to `[0 => 1, 20 => 0]`, but it is useful for this kind of setup.
