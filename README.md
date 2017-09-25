# i3

This is a fork of the tiling window manager [i3](https://github.com/i3/i3)
with various changes, especially around the handling of floating windows.

## Changes

* XBM icons in window decorations: https://github.com/ashinkarov/i3-extras#icons-in-i3bar
  * icons scaled to window decoration height
* Adds `%mark%` in the window `title_format` (https://i3wm.org/docs/userguide.html#pango_markup)
  This shows only the *first* mark (if any).
* Changes to handling of floating windows:
  * Transient floating windows are shown on the *same* workspace as their parent (and vice-versa).
    This also means moving a window across workspaces also moves the transient parent and/or the floating child windows.
  * Transient floating windows appear above everything *only if* they, their parent or a floating child is focused.
    So a floating dialog for an unfocused window will be shown below a non-floating window that is focused.
    Floating windows are shown in the order of the transient relationship,
    i.e. transient parents are shown before their children.
