# Meta overview

In order to understand how to use Hexerator, we'll establish some basic concepts.

## What is the Meta?

When you open a file with Hexerator, you're opening a raw binary file.
The raw binary file itself doesn't dictate how a hex editor should display it, or how to interpret
the raw binary data contained within.
Instead, it's up to the user to figure out all that stuff.
The **Meta** contains all the information on how to meaningfully interpret and display the data.
It can also contain various notes and discoveries made by the user.

## Meta components

- [Regions](#regions)
- [Perspectives](#perspectives)
- [Views](#views)
- [Layouts](#layouts)
- [Bookmarks](#bookmarks)

## Regions

Regions are the most basic metadata. They are used to mark regions of the file that are meaningfully different.
For example an executable might contain a header, executable code, and data.
These could be marked as 3 different regions in Hexerator.

The default region is the entire file.

You can select `Meta->Regions` from the top menu, or press `F8` to bring up a list of regions, and create
new ones.

In order to create a new region, you first need to [make a selection](./basic-operations.md#a-b-select).

## Perspectives

Perspectives tell Hexerator how to align the data, by setting the number of columns used to display them.
Each perspective has an associated [region](#regions).

You can press `ctrl + Left` and `ctrl + Right` arrow keys in `View` mode to adjust the column count
for the current perspective.

Additionally, perspectives have a special mode to flip the row order, to display rows upside down.
This is useful because sometimes things like images are stored upside down in binary files.
Weird, I know.

You can select `Perspective->Perspectives` from the top menu, or press `F7` to bring up a list of
perspectives, and create new ones.

## Views

Views are the windows through which data is viewed and interacted with.
Each view has an associated [perspective](#perspectives).
Views that share the same perspective scroll together. So if the hex view of a perspective is scrolled,
the text and block views scroll along with it.

Currently there are 4 basic types of views

- Hex
- Decimal
- Text
- Block

You can right click a view and select `View properties...` to look at and change the properties
of a view.

You can also select `View->Views` from the top menu, or press `F6` to bring up a list of views,
and create new views.

## Layouts

Layouts are groups of views that are displayed together.
You can create multiple layouts that show different places in the file in different ways.

A layout consists of one or more rows, and each row can contain one or more view.
Hexerator will try to lay out the views in a sensible manner, based on the row and column they belong to.

The default layout is a Hex view, a Text view, and a Block view side by side.

You can select `View->Layouts` from the top menu, or press `F5` to bring up a list of layouts, and
edit the current layout, or add new ones.

## Bookmarks

Bookmarks are places of interest in the data at various offsets.
They can also additionally be assigned a data type, which allows them
to show a handle to the data at their offset, which shows the value and allows it to be edited.

You can select `Meta->Bookmarks` from the top menu, or press `F9` to show a list of bookmarks, and
add new ones.

You can also right click a location in a view, and select `Add bookmark`.
