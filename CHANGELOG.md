# ArtLab changelog

Notable changes in public ArtLab releases, newest first.

## 0.7.0-alpha.1 — 2026-11-21

The first public Rust release brings 46 effects to the new editor. The free
Linux alpha ships as a 64-bit Debian package under the ArtLab Alpha Licence.
It was tested on Debian 13 and Ubuntu 24.04. Earlier releases keep their
original licences.

- Try Mezzotint, Smear and Cells, the three new effects.
- Blend, rename, duplicate and solo effect layers.
- Paste from the clipboard and export PNG, JPEG or WebP.

### Added

- **Mezzotint** turns a photo into fine grain, lines or engraved-looking strokes.
- **Smear** smooths fine detail into brush-like patches while keeping larger edges.
- **Cells** rebuilds an image from irregular patches. Give the patches outlines
  for a stained-glass effect.
- **Water** and **Liquid** gain **Noise** modes. Water warps the image in soft
  clouds. Liquid shades it in its existing colours.
- **Layers** can use blend modes, including Multiply, Screen and Overlay, for
  any effect. Rename a layer with **F2**, duplicate the selection with **Ctrl+J**,
  or **Alt+click** a visibility icon to see one layer on its own and return to
  the previous view.
- **Paste as new picture** opens a clipboard image as an editable project.
  **Copy picture** puts the rendered image back on the clipboard.
- **Actual pixels** (**1**) shows the output at one image pixel per screen pixel.
  Pinch to zoom and pan with two fingers on supported hardware. **Ctrl+wheel**
  zooms smoothly and the arrow keys pan a zoomed picture.
- **Frame** can move and resize the crop with the keyboard. Use the arrow keys
  to move it, **Shift** for larger steps, or **Alt** to resize it.
- **Export as…** adds JPEG with adjustable quality and lossless WebP. Ordinary
  PNG, JPEG and WebP can export at full size or at a smaller size you choose.
- **AVIF** opens without an extra image loader. For PNG, JPEG and WebP with a
  supported embedded colour profile, ArtLab converts the image to sRGB on open
  and tags still exports as sRGB.
- **Check for updates** is available in Settings and starts off. Turning it on
  lets ArtLab tell you when a later version is available.
- **Help → About** shows the exact build alongside the version. File can open
  the project, exports and templates folders directly.

### Changed

- The native Rust editor keeps the familiar Layer, Frame and Paint workflow,
  effect templates, editable history, and gesture and GIF recording.
- **PNG export** saves the rendered picture by default. Use **PNG with edits**
  to include the effect stack. The PNG carries an original-image fingerprint
  without its path. On reopen, choose the original to restore editable layers.
  Use a `.artlab` project when you want one file that includes the original too.
- **Welcome** fills in recent-project thumbnails as they finish. Opening a
  picture takes priority over those thumbnails. A named project can show its
  saved thumbnail while the editable project loads.
- **Restore** shows a preview of the interrupted work when one is available.
  A recovery session remains with its open window and becomes available on
  Welcome after that window exits. Restore or Discard clears the card once the
  operation succeeds.
- If another window has saved a newer project revision, ArtLab explains the
  conflict and tells you to reopen it or save a separate copy.
- **Properties** accepts exact typed values and keyboard steps. Double-clicking
  a slider restores its default. Controls report their names and values to screen
  readers, and the effect and history rows keep focus as the list changes.
- **HEIC** on Linux uses the optional `libheif1` codec (version 1.23.6 or newer
  in the 1.x series). DNG still uses the camera's embedded preview.
- **Fit** scales down the full rendered picture once editing settles. Fine print
  patterns such as Dither and Halftone are rendered at the output pixel scale.

### Fixed

- Undo and Redo step through canvas gestures and settings of the effect you
  are trying while keeping the trial open.
- Close waits for pending saves, exports and recovery writes. A failed write
  keeps the window open with the reason so you can retry.
- An older autosave finishing late leaves newer recovery or a completed save
  intact.
- Framing keeps the selected aspect ratio during a corner drag. The before and
  after view compares the same crop, rotation and mirror on both sides.
- Opening a file or restoring work reports what went wrong. A failed Restore
  leaves the recovery card available to retry.

### Upgrade notes

If you still have the Python release, use it to open its `.artlab` files. The
Rust editor uses a new project format and leaves older project files intact.
Export a finished image from Python to start a new Rust project from it.

[Release and downloads](https://github.com/compoodment/ArtLab/releases/tag/v0.7.0-alpha.1)

## 0.6.0-alpha.2 — 2026-11-19

The last public Python alpha has 43 effects and a new window style.

- Edit in ArtLab's new window with square controls and dithered highlights.
- Find effect settings in collapsible groups, and set line-based effects to run
  across or down the image.
- The editor opens projects with retired effects and tells you which layers
  were left out.

### Added

- Choose **Across** or **Down** in **Lines** for Glitch, Corrupt, PNG, VHS,
  Tape, Camera, Jello and Sheen. Existing layers start on Across.
- The Debian package includes the fonts and stylesheet for the new window,
  together with the font licences.

### Changed

- The editor has a new look with square controls, dithered highlights and a
  consistent dark palette. A system high-contrast theme takes precedence.
- The **Effects** tool is now **Layers**. **Back** and **Forward** are now
  **Undo** and **Redo**. One Add and Cancel pair stays above Properties while
  trying an effect.
- **Properties** replaces the old **more** section with collapsible groups
  for shape, tone, colour, position and motion. An effect's main controls
  start open.
- Draft previews can rise to a sharper size as the editor measures how
  quickly they appear on screen.
- Ripple's **Shape** becomes **Pattern**. Water's **Strength** setting becomes
  **Wave height**, alongside the separate layer Strength. Png is now **PNG**.
- Chrome, Sculpture, Polygon and Venom leave the effect library.

### Fixed

- Minimise the window and playback holds on the current frame. It resumes
  there when you bring the window back.
- Notices and trial controls appear without shifting the layout. Messages
  sit over the canvas, leaving the editor's controls available.
- Long filenames shorten in the middle to keep the end and the unsaved dot
  visible. The layer list scrolls while Add and the layer arrows stay put.

### Upgrade notes

ArtLab identifies and skips layers that use Chrome, Sculpture, Polygon or Venom
when opening a project or restoring work. Save under a new name to keep the
original project with those layers intact.

## 0.6.0-alpha.1 — 2026-11-19

This alpha expands the library from 12 to 47 effects and reorganises the
editor around tools, panels and workspaces.

- Browse 35 new effects, including Mosaic, Typewriter, Liquify and Sphere.
- Arrange the editor's panels and paint several chosen layers at once.
- Install the Debian desktop package to open `.artlab` files from the
  file manager.

### Added

- **Print** adds Mosaic, Typewriter, Polygon and Moire. Mosaic rebuilds an
  image with small tiles or emoji. Typewriter draws it in characters and can
  save the result as text.
- **Colour** adds Sheen, Glitch, Threshold, Channels, Invert, Spectrum, Screen,
  Burn, Y2K, Purp and Fill.
- **Light** adds Blur, Liquid and Vibe. Liquid brings out metallic highlights
  or tonal reversals.
- **Distort** adds Corrupt, Sort, Mosh, Png, Liquify, Jello, Scan, VHS, Tape,
  Venom, Whirl, Zoom, Bend and Camera.
- **3D** adds Sphere, Sculpture and Chrome. Depth also gets sparse points.
- The **Library**, **Properties**, **Layers** and **History** panels can be
  arranged or folded. **Window** offers Essentials, Effects and Compact
  workspaces and remembers the arrangement.
- The new menu, options and status bars bring editing commands, zoom,
  image size and unsaved state into view. **Help → About** and `artlab --version`
  show the version.
- **Paint** adds rectangular masks with a sharp edge and lets you paint a
  selection of several layers. Use Ctrl+click or Shift+click in Layers to
  choose them.
- The first Debian desktop package adds an applications-menu entry and
  registers `.artlab` projects with the file manager automatically. It was
  tested on Debian 13 and Ubuntu 24.04.

### Changed

- **+ Add** opens a searchable Library with thumbnails showing each effect
  on the open image. Preview and adjust a treatment in Properties before
  adding it, or double-click a tile to add it directly.
- **Pixelate** can be brushed in with the **Even** mode or applied across the
  picture with **Blocks**, which gives it a broken-video look.
- **Fisheye** gains a reflected projection. **Gradient** can keep a midtone
  and animate its palette. Water strokes make broader, interlocking waves.
- Bloom's **Glow from** control is renamed **Threshold** and starts at 0.3
  instead of 0.65. Dither starts with larger marks and fewer tones, and Mirror
  starts on its new Tiles mode.
- Edges gains a Neon mode, Ripple can shape the flow of its bands, and Halftone
  adds a light texture control.
- Stopping a recording saves the GIF straight to Exports. Export GIF can
  also loop a moving effect.
- Saving or exporting during an effect trial includes the result on screen.
- The Orb and wordmark arrive in the editor. New hover hints explain the
  controls, and the guide walks through a first edit with a worked example
  for each effect.

### Fixed

- Redo brings back a stroke undone while painting. Once a paint session ends,
  its controls reflect the edits actually kept in History.
- A crop shape larger than the picture fits inside it. A refused paint stroke
  leaves earlier work intact.
- Opening a picture in one window keeps the recent files remembered by another.
  An interrupted recovery write keeps an earlier copy available to restore.

## 0.5.0-alpha.3 — 2026-11-18

The first public alpha was a local Linux image editor under the MIT licence.

- Build an editable stack from 12 print, colour, light and distortion effects.
- Paint effects onto part of the image, crop it, and compare your result
  with the original.
- Save the original and your edits as one project or share a PNG or GIF.

### Added

- The first library includes Dither, Halftone, Gradient, Fisheye, Pixelate,
  Bloom, Depth, Ripple, Edges, Mirror, Water and Relief.
- **Layers** lets you try effects on the canvas, reorder them, adjust their
  strength and switch them on or off, up to 12 layers. Dragging on the canvas
  adjusts two settings at once for supported effects.
- **Paint** brushes an effect into part of the image and erases it to reveal
  what is underneath. **Frame** crops to a free or fixed shape and rotates or
  mirrors the picture.
- **Compare** shows the original beside the edit. Undo and Redo move through
  your changes, and **Keep** bookmarks results in History.
- **Water** lets you stir waves by dragging across the picture. Play or pause
  moving effects, record up to about three seconds of changes, or export a
  looping GIF at 320 pixels.
- `.artlab` projects contain the original and an editable stack, including
  painted masks. Welcome can restore or discard unsaved work after an
  interruption.
- Full-size PNG export uses a fresh filename. It saves recipe settings and the
  original file's path so the editor can reuse the settings later.
- Save an effect stack as a template, or apply the saved effects from an
  ArtLab PNG to another image.
- Open PNG, JPEG, TIFF, GIF, BMP or WebP. DNG uses the camera's embedded preview.
  HEIC and AVIF use an optional loader. The preview fits within 640 pixels and
  a PNG can export up to 16 million pixels.
- The alpha runs from source with Python and GTK on Linux. The optional desktop
  launcher, icon and project file association can be installed by hand.
