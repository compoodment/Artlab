# ArtLab changelog

Notable changes in public ArtLab releases, newest first.

## 0.7.0-alpha.1 — 2026-11-21

The first public release of the Rust editor. The free Linux alpha ships as a
64-bit Debian package under the ArtLab Alpha Licence. Earlier releases keep
their original licences.

- The editor and rendering engine now run in Rust.
- Paste a picture from the clipboard to start editing, or copy the finished image.
- View the image at actual pixels. Pinch to zoom on supported touchpads and screens.

### Changed

- Welcome shows recent-project thumbnails as they finish. Opening a project
  takes priority over loading thumbnails.

### Fixed

- Undo and Redo keep the effect trial open while restoring settings.
- Quitting waits for pending recovery writes.

### Upgrade notes

This release introduces the Rust project format. Finished exports open as
images. The editor explains when it cannot open a project from a Python
release and leaves that file intact.

[Release and downloads](https://github.com/compoodment/ArtLab/releases/tag/v0.7.0-alpha.1)

## 0.6.0-alpha.2 — 2026-11-19

- The editor gained the Dither visual style and direct controls for Lines.
- Related settings appear in groups in Properties.

### Added

- The Debian package includes the fonts, stylesheet and font licences for the
  new look.

### Changed

- Layers and Undo and Redo are available from the editor.

## 0.6.0-alpha.1 — 2026-11-19

- The Linux desktop package adds an applications-menu entry and registers
  `.artlab` projects with the system.
- Bloom gained a Threshold control.

### Changed

- The guides and hover hints explain painting, layer order and effect controls
  in more detail.

## 0.5.0-alpha.3 — 2026-11-18

The first public alpha was a local Linux image editor under the MIT licence.

- Open a picture, build an editable stack of effects and paint where they apply.
- Save editable projects, recover interrupted work and export finished images.
