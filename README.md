# po prostu

*image viewer*

A native macOS image viewer, inspired by Geeqie. Built for fast browsing of
large RAW directories, correct colour management, and zero sharpening.

## Features

- **Fast RAW browsing.** By default the app shows the JPEG preview embedded
  in the RAW file, so a 60 MP RAW opens in tens of milliseconds. Press `D` to
  switch to a full RAW decode when you need to judge sharpness.
- **No sharpening, ever.** Full RAW decodes run with sharpening, detail and
  local tone mapping all set to zero.
- **Colour management.** Images are converted from their embedded profile to
  your monitor's profile. `C` switches the source interpretation (embedded,
  monitor, sRGB), `B` toggles a non-destructive monochrome preview.
- **Browsing.** Directory tree with bookmarks, file list, thumbnail strip,
  slideshow, sorting.
- **Star ratings written to your files.** XMP sidecars for RAW files, in-file
  XMP for JPEG, TIFF, PNG and HEIC (no pixel re-encoding), existing DxO
  PhotoLab `.dop` sidecars updated in place. Filter the list by rating.
- **Comparison.** Side by side, stacked, overlay, and a grid that arranges
  itself so the photos come out as large as possible. Zoom and pan stay in
  sync across all panes.
- **EXIF / IPTC panel**, zoom relative to the file's real resolution,
  per-photo preview rotation (never written to disk).
- **File operations**: move, copy, move to Trash, set file date from EXIF, open in an
  external editor, share.
- **Printing** one photo per page, with size, margins and placement set in
  the system print panel; while comparing, `⌘P` prints the comparison as
  shown.
- English and Polish.

Press `?` in the app for the full list of keyboard shortcuts.

## Requirements

- macOS 15 Sequoia or later
- Apple silicon or Intel (universal binary)

## Install

### Homebrew

```sh
brew install --cask kosio-labs/tap/poprostu
```

Upgrade with `brew upgrade --cask poprostu`.

### Manual

1. Download the latest `PoProstu-<version>.dmg` from
   [Releases](https://github.com/kosio-labs/poprostu/releases).
2. Drag **PoProstu** to **Applications**.
3. Remove the quarantine flag (see below): open **Terminal**
   (*Applications → Utilities*), paste this command and press Return:

   ```sh
   xattr -dr com.apple.quarantine /Applications/PoProstu.app
   ```

## Why the quarantine step

The app is not signed with an Apple Developer ID and not notarised by Apple.
macOS marks every downloaded file with a quarantine flag, and Gatekeeper
refuses to open an unnotarised app that carries it.

- **Homebrew:** the cask removes the flag for you after installing. This means
  macOS does not run its own malware check on the app. Install only if you
  trust this source.
- **Manual install:** run the `xattr` command above once after each update.
  Alternatively, try to open the app, then go to
  *System Settings → Privacy & Security* and click *Open Anyway*.

## License

Free for individuals, non-profits, educational institutions and small
companies (fewer than 100 people and under 1,000,000 USD annual revenue).
You may share the original disk image for free, but not sell, modify or
bundle it. Larger organisations: please ask. Full terms: [LICENSE](LICENSE).

## Feedback

Bug reports and suggestions: [Issues](https://github.com/kosio-labs/poprostu/issues).
