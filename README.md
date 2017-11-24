# i3

This is a fork of the tiling window manager [i3](https://github.com/i3/i3)
with various changes, especially around the handling of floating windows
and the [title format](https://i3wm.org/docs/userguide.html#pango_markup).

## Changes

* Adds `%mark` in the window `title_format`.
  This shows only the *first* mark (if any).
* XBM icons in window decorations: https://github.com/ashinkarov/i3-extras#icons-in-i3bar
  * icons scaled to window decoration height
  * support `%icon` in the window `title_format` (so you could display the window icon multiple times if you wanted).
* Changes to handling of floating windows:
  * Transient floating windows are shown on the *same* workspace as their parent (and vice-versa).
    This also means moving a window across workspaces also moves the transient parent and/or the floating child windows.
  * Transient floating windows appear above everything *only if* they, their parent or a floating child is focused.
    So a floating dialog for an unfocused window will be shown below a non-floating window that is focused.
    Floating windows are shown in the order of the transient relationship,
    i.e. transient parents are shown before their children.
