# Hexerator design document

## Goals

Hexerator is a hex editor aiming to aid in pattern recognition and binary file discovery.
It also aims to be a good and versatile hex editor usable in a large amount of scenarios,
including editing `/proc/id/mem` and reading streaming sources, making it usable to read
piped data.

## User interface

### Perspective
A `Perspective` is a view into a `Region` with a specific `column count`.

A variable column count is very helpful for better recognizing certain patterns in data, and is one of the core features of hexerator. A `Perspective` on its own doesn't really do much. To make use of perspectives, there are `View`s.

### View

A `View` is a region on the `Viewport` that provides a look into the data presented by a perspective. A view can be one of multiple kinds, like hex, ascii, block (pixel, kind of like a minimap), and it's scrollable, allowing you to explore different parts of a perspective. You can have multiple views on the `Viewport`. There is a `focused` view that you are currently focused on and scrolling/editing, etc.
By default, all views that share the same perspective sync their scroll offsets with the `focused` view. This behavior can be turned off if independent scrolling is desired.

### Viewport

The `Viewport` is the area in the window where the `Views` are laid out.
The other things that take up space in the window are the UI panels and windows.

## Concepts

### BinData
The `BinData` is the raw binary data opened inside hex editor.
It can be opened from a file, or streamed from a streaming source, like a pipe.

### Region
A `Region` is a slice of the `BinData`.
It has a `start` offset which determines where it begins,
and an `end` offset which determines where it ends.

A `Region` can be given a `name` to give it an easy to remember
identifier and also help remember what it's about.

It can also have a `description` which can give further useful information about it.

### Meta
A `Meta` is all the metadata about a binary format. It can include things like `Region`s and `View`s that aid understanding
of a binary format.

## Limits
To make development easier, and help keep my sanity, hexerator defines some value limits.

### File size
The supported file size is `min(usize, i64)`, which is ~4GB on 32 bit platforms,
and practically limitless on 64 bit platforms. 16 bit platforms are not supported.

### Resolution and mouse position
These are i16, meaning values higher than 32767 are not supported.
The minimum supported resolution is 920x620. The ui is not designed and tested for
resolutions lower than that.

### Block size
A block, or cell (final name not decided) is the element that displays a value.
Like a hex pair, an ascii character, etc.
The size range is `1..i16::MAX`.
