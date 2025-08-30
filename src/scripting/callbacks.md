# Callbacks

Callbacks, alternatively referred to as script calls, are functions that are
directly emitted by the source code and into scripts. They act somewhat
similar to entry points in most languages, including standard Haxe itself, but
are used for scripts and can usually coexist with each other.

A callback may have an [event](./events.md) attached to it, for modification
purposes.

> Most states have unique callbacks for specific purposes. One callback use
> may not work for another.

## Callback Standard

This section details the book's callback standard.

Callbacks typically go in their own section and are in unordered lists. There
will usually be a description, specifically about where the callback is usually
emitted.

Some callbacks are grouped into their own subsections, due to a similar
premise.

Three valid callback examples include:

* `[pre, post](c)reate`: Called when the script is created.
* `<pre, post>GameStart`: Called during initialization of the game.
* `onStageXMLParsed{StageXMLEvent}`: Called once the stage definition has been
  parsed successfully.

The basic syntax of the name is as follows:

* Square brackets denote optional values, where either the part can be
  omitted entirely, or one value out of the list is chosen and replaces that
  part.
* The two standard comparison operators, `<` and `>`, are similar to square
  brackets, but cannot be omitted.
* Parentheses define that one or more lowercase characters included between
  them may be capitalized when there is a prefix.
* Angle brackets are used when an event is passed to the callback. Inside
  the angle brackets is the event type for reference.
