<h1 align="center"><a href="https://artlab.putment.com"><img src="https://artlab.putment.com/assets/orb-512.png"
width="128" alt="ArtLab"></a><br>ArtLab</h1>

<p align="center"><b>A free desktop photo and art editor.</b><br>
<a href="https://artlab.putment.com">Website</a> · <a href="#install-the-desktop-app">Install</a> ·
<a href="https://artlab.putment.com/docs/">Guide</a> · <a href="https://artlab.putment.com/effects/">Every effect, played</a> ·
<a href="CHANGELOG.md">Changelog</a></p>

## What it is

ArtLab is a desktop editor for layered print, colour and distortion effects. Try effects live on an image, paint
where they apply, and save a project to edit again. Export a PNG, JPEG or WebP, or record a short looping GIF.

ArtLab is in alpha: it works, but things can change between versions. Back up projects you care about.

This repository holds ArtLab's downloads, its [changelog](CHANGELOG.md), its licence and its issue tracker.
ArtLab's source code isn't public.

## How to get it

### Install the desktop app

| System | Status |
| --- | --- |
| Debian 13 (64-bit x86) | Linux desktop package |
| Ubuntu 24.04 LTS (64-bit x86) | Linux desktop package |
| Windows | No public package in this release |

1. Download [`artlab_0.7.0-alpha.1_amd64.deb`](https://github.com/compoodment/ArtLab/releases/download/v0.7.0-alpha.1/artlab_0.7.0-alpha.1_amd64.deb).
2. In a terminal in the folder containing the `.deb`, run `sha256sum artlab_0.7.0-alpha.1_amd64.deb`.
   Compare the value printed before the filename with the entry for that file in
   [`SHA256SUMS`](https://github.com/compoodment/ArtLab/releases/download/v0.7.0-alpha.1/SHA256SUMS).
3. Open the verified `.deb` in your software installer and choose **Install**. If the file opens in an
   archive viewer, run the install command in the same terminal.

   ```sh
   sudo apt install ./artlab_0.7.0-alpha.1_amd64.deb
   ```

4. Choose **ArtLab** in the applications menu. The [guide](https://artlab.putment.com/docs/) walks through
   opening an image and saving your work.

The installer adds the app icon and registers `.artlab` projects with the file manager. HEIC import requires
the optional `libheif1` package at version 1.23.6 or later in the 1.x series, with an HEVC decoder.

To remove ArtLab, remove it in your software installer or run `sudo apt remove artlab`. Your projects and exports
stay in your folders.

## Licence

ArtLab is free to use under the [ArtLab Alpha Licence](LICENSE). Get it only from this repository's releases or
the [website's download page](https://artlab.putment.com/download/). Its bundled components keep their own
licences: see [notices/](notices/), the same files ArtLab installs in `/usr/share/doc/artlab`.

## Privacy

ArtLab doesn't send your pictures or projects anywhere. The optional update check, off until you switch it on in
**Edit → Settings…**, asks GitHub once a day whether a newer version is out. Nothing is downloaded.

## Questions and problems

Open an [issue](https://github.com/compoodment/ArtLab/issues) for a bug or an idea. Say which version you use:
it's in **Help → About** and in `artlab --version`. For licence questions, or anything you'd rather not post in
public, email [artlab@putment.com](mailto:artlab@putment.com).
