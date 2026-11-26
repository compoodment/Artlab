<h1 align="center"><a href="https://artlab.putment.com"><img src="https://artlab.putment.com/assets/orb-512.png"
width="128" alt="Artlab"></a><br>Artlab</h1>

<p align="center"><b>A free desktop photo and art editor.</b><br>
<a href="https://artlab.putment.com">Website</a> · <a href="#install-the-desktop-app">Install</a> ·
<a href="https://artlab.putment.com/docs/">Guide</a> · <a href="https://artlab.putment.com/effects/">Every effect, played</a> ·
<a href="CHANGELOG.md">Changelog</a></p>

## What it is

Artlab is a desktop editor for layered print, colour and distortion effects. Try effects live on an image, paint
where they apply, and save a project to edit again. Export a PNG, JPEG or WebP, or record a short looping GIF.

Artlab is in alpha: it works, but things can change between versions. Back up projects you care about.

This repository holds Artlab's downloads, its [changelog](CHANGELOG.md), its licence and its issue tracker.
Artlab's source code isn't public.

## How to get it

### Install the desktop app

| System | Status |
| --- | --- |
| Debian 13 (64-bit x86) | Linux desktop package |
| Ubuntu 24.04 LTS (64-bit x86) | Linux desktop package |
| Windows | No public package in this release |

1. Download [`artlab_0.8.0-alpha.2_amd64.deb`](https://github.com/compoodment/Artlab/releases/download/v0.8.0-alpha.2/artlab_0.8.0-alpha.2_amd64.deb).
2. Open the downloaded file and choose **Install**.
3. Find **Artlab** in your applications menu.

Artlab runs on X11. Wayland desktops need XWayland.
If you see **Artlab 0.8 Preview 2** in your menu, choose **Artlab** to open
the packaged version. You can open projects you made in Preview 2.

### Check the download

To check the file before installing, run `sha256sum artlab_0.8.0-alpha.2_amd64.deb` in the folder that holds it
and compare the result with the line for that file in
[`SHA256SUMS`](https://github.com/compoodment/Artlab/releases/download/v0.8.0-alpha.2/SHA256SUMS).

If the file opens in an archive viewer instead of an installer, install it from that folder with
`sudo apt install ./artlab_0.8.0-alpha.2_amd64.deb`. Opening HEIC photos needs `libheif1` 1.23.6 or later with
an HEVC decoder. Artlab explains if an HEIC photo cannot be opened.

To remove Artlab, remove it in your software installer or run `sudo apt remove artlab`. Your projects and exports
stay in your folders.

## Licence

Artlab is free to use under the [Alpha Licence](LICENSE). Get it only from this repository's releases or
the [website's download page](https://artlab.putment.com/download/). Its bundled components keep their own
licences: see [notices/](notices/), the same files Artlab installs in `/usr/share/doc/artlab`.

## Privacy

Artlab doesn't send your pictures or projects anywhere. The optional update check, off until you switch it on in
**Edit → Settings…**, asks GitHub once a day whether a newer version is out. Nothing is downloaded.

## Questions and problems

Open an [issue](https://github.com/compoodment/Artlab/issues) for a bug or an idea. Say which version you use:
it's in **Help → About** and in `artlab --version`. For licence questions, or anything you'd rather not post in
public, email [artlab@putment.com](mailto:artlab@putment.com).
