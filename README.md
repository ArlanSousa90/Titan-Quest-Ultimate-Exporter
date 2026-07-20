# Titan Quest Ultimate Exporter

**Titan Quest Ultimate Exporter (TQUE)** is a self-contained Windows application for browsing, previewing, extracting, and converting assets from **Titan Quest** and its expansions.

It combines the TqueShell graphical interface with the TQAnimExporter engine, so models, animations, textures, audio, database records, effects, shaders, fonts, and quests can be handled without assembling command-line operations manually.

> Current distribution: executable-only preview. The source code is not publicly available at this time.

## Download and installation

1. Open the [latest release](https://github.com/ArlanSousa90/Titan-Quest-Ultimate-Exporter/releases/latest).
2. Download the Windows x64 ZIP package.
3. Extract the **entire** archive to a folder.
4. Run `TQUE.exe`.

Keep the bundled `Tools` folder beside `TQUE.exe`. It contains the exporter engine and FFmpeg used by the application.

No separate .NET installation is required.

## Highlights

- Browse individual `.arc` archives as a folder tree or detailed list.
- Search the selected archive or search **all ARC archives** in the configured Titan Quest installation.
- Preview assets directly from archives before exporting them.
- Export complete content categories in bulk or hand-pick individual assets.
- Convert loose model and texture files already extracted to folders.
- Auto-detect Steam and GOG Titan Quest installations.
- Preserve archive folder structure to avoid filename collisions.
- Track progress, estimated time, successful/failed items, cancellation, logs, and optional metadata.
- Use the full interface in English, Brazilian Portuguese, Chinese, Czech, or Polish.
- Add drop-in custom language and theme packages.
- Check for application updates from inside TQUE.

## What's new in the v1.2.3 line

### Experimental Lab

The new **Lab** contains advanced model and animation tools. They are under active development and may not work with every asset.

- **Merge Creatures** — combine a target creature with animations from donor creatures, including automatic animation retargeting between different skeletons, then preview and export the result as GLB.
- **Body Part Swap** — transplant a selected body region from one model to another, align the connection, remap skin weights to the target rig, retain the donor texture, and export a validation GLB.
- **Animation Retarget** — transfer motion between skeletons and generate new Titan Quest `.anm` files, including batch processing for multiple animations.

### Export and preview improvements

- Global filename/path search across every indexed `.arc` archive.
- JPEG output for `.tex` and `.tga` textures.
- Improved FBX compatibility with 3ds Max while retaining Blender support.
- 3D select mode with Ctrl+click multi-selection and bone, mesh, and material information.
- Detachable 3D preview window for multi-monitor workflows.
- Faster switching between animation clips.
- Faster initial archive indexing and responsive lazy-loaded views.
- Fallback metadata panel and raw extraction for archive entries without a dedicated viewer.
- Build number displayed in the title bar and About page.

## Supported sources and outputs

| Content | Sources | Available outputs |
|---|---|---|
| Models and animations | `.msh`, `.anm` | GLB, FBX, PSK/PSA, SMD, OBJ, original MSH/ANM |
| Textures and images | `.tex`, `.tga` | BMP, PNG, JPG, TGA, PSD, DDS, original TEX |
| Audio | `.wav`, `.mp3` | WAV, MP3 (128/192/320 kbps), OGG, FLAC |
| Database records | `database.arz` / `.dbr` | DBR, JSON, XML, searchable local HTML Wiki |
| Particle effects | `.pfx` | Original PFX, decoded JSON |
| Shaders | `.ssh` | Original SSH, decoded JSON |
| Fonts | `.fnt` | Correctly identified TTF or OTF |
| Quests | `.qst` | Original QST |

Most game assets are stored inside `.arc` resource archives. Gameplay records are stored in `database.arz`.

## ARC Exporter

The ARC Exporter is intended for focused inspection and selection:

- Browse the real archive folder hierarchy or switch to a sortable list.
- Search by filename or path and filter by extension, category, or size.
- Switch search scope between **This ARC** and **All ARCs**.
- Select models, animations, and textures individually or by type.
- Preview the selected asset inline.
- Mix raw and converted output formats in the same export plan.
- Include companion metadata files and a detailed export log.

Global search results retain the source archive, so a result can be previewed or extracted without manually locating its `.arc` file first.

## Bulk export

Dedicated bulk screens export an entire supported content type from an archive:

- 3D models and animations
- textures
- audio
- database records
- particle effects
- shaders
- fonts
- quests

Optimized batch operations open an archive once where supported. The application can place results in an archive-named subfolder and mirrors source folders where applicable.

## 3D preview

The built-in WPF 3D viewport supports:

- orbit, pan, zoom, and camera reset;
- textured, smooth, and flat shading;
- grid, axes, material groups, and skeleton overlays;
- animation selection, play/pause/stop, frame stepping, looping, and speed control;
- material and texture inspection, material variants, morph targets, and model statistics;
- mesh/part selection and inspection;
- detaching the viewer into a separate window.

No WebView2 runtime is required by the current viewer.

## Texture, audio, and text preview

- Decode `.tex` images for inline viewing, fit-to-window or 1:1 display, zoom, and dimension information.
- Play WAV and MP3 audio with seeking, transport controls, time display, volume, and mute.
- Inspect supported database and text content in a read-only viewer.
- Extract an unsupported archive entry unchanged through the fallback preview panel.

## Database support

TQUE can read a Titan Quest `database.arz`, list its compiled records, and export them as:

- `.dbr` text records;
- typed JSON;
- XML;
- a searchable local HTML Wiki with links between related records.

Large databases are listed and processed with filtering, lazy loading, and parallelized extraction where supported by the exporter engine.

## Languages, themes, and settings

Built-in interface languages:

- English
- Português (Brasil)
- 中文
- Čeština
- Polski

Language changes apply immediately. Additional JSON language packs can be dropped into the configuration folder.

TQUE includes light/default and dark themes and accepts additional `.tquetheme.json` packages. Settings are available for the Titan Quest installation, export destination, extra resource folders, FFmpeg, language, theme, and optional diagnostics.

## Requirements

- Windows 64-bit
- Titan Quest, Titan Quest Anniversary Edition, or compatible Titan Quest asset files
- Enough free disk space for the selected conversions

The release package is self-contained. The TQAnimExporter engine and FFmpeg are bundled under `Tools`.

## Notes about animations

An `.anm` contains animation data, not a complete model. Previewing or exporting animation with a character normally requires the related `.msh` skeleton/model.

Example:

```text
monster/bat/bat01.msh
monster/bat/anm/bat_attalpha.anm
monster/bat/anm/bat_idle.anm
```

TQUE attempts to associate animations with their corresponding model automatically. OBJ is a static mesh format and does not contain skeleton or animation data.

## Experimental-feature warning

Merge Creatures, Body Part Swap, and Animation Retarget are experimental. Always keep backups of original modding projects and validate generated GLB/ANM files before using them in a production workflow.

## Disclaimer

TQUE is an unofficial community tool and is not affiliated with, endorsed by, or supported by THQ Nordic, Pieces Interactive, Iron Lore Entertainment, Digital Arrow, or other Titan Quest developers and publishers.

Titan Quest and related assets belong to their respective owners. TQUE is intended for personal asset inspection, modding workflows, interoperability research, and educational use.

The release bundles [FFmpeg](https://ffmpeg.org/) for audio conversion under its applicable LGPL/GPL terms.

## Download

Download the newest Windows package from [GitHub Releases](https://github.com/ArlanSousa90/Titan-Quest-Ultimate-Exporter/releases/latest).

> Source code is not included in the current public release.
