# Titan Quest Ultimate Exporter

**Titan Quest Ultimate Exporter** is a Windows tool for inspecting, previewing, and exporting Titan Quest game assets.

It helps users work with Titan Quest files such as `.ARC`, `.ARZ`, `.MSH`, `.ANM`, and `.TEX` through a simple graphical interface, without needing to manually run command-line commands for each file.

> Current release: executable-only preview.  
> Source code is not publicly available at this time.

---

## Installation

1. Go to the [Releases](https://github.com/ArlanSousa90/Titan-Quest-Ultimate-Exporter/releases/latest) section and download `TQUE-v1.1.0-win-x64.zip`.
2. Extract the `.zip` file.
3. Run `TQUE.exe`.

> This release is currently distributed as an executable-only preview.

---


## Features

- Open one or more Titan Quest asset files.
- Drag and drop supported files directly into the application.
- Auto-detect supported file types.
- Inspect loaded assets using a TreeView.
- Preview and export directly from inside `.ARC` archives — no need to extract first.
- Preview `.TEX` texture files inside the application, pixel-perfect (1:1) with zoom and adjustment sliders.
- Preview 3D models inside the application, with a built-in animation player.
- Select which skin/texture to apply in the 3D preview.
- Read Titan Quest database files (`.ARZ`) and inspect `.DBR` / `.TXT` records.
- Search and filter large archives, with lazy loading to keep the UI responsive.
- Export textures to `.BMP`, `.PNG`, `.TGA`, and `.PSD` (TGA/PSD are handy for the Art Manager).
- Export models and animations to modern 3D formats.
- Extract audio to `.MP3` and `.WAV`.
- Choose which export formats you want, per asset type.
- Organize exported files automatically by object and format.
- Set default load / export folders in Preferences, and auto-detect your Steam Titan Quest install.
- Multi-language interface — starts in English; you can change the language on first run.
- Show loading and export progress in the status bar.
- Support grouped views for `.ARC` archives.

---

## Supported File Types

| File Type | Description |
|---|---|
| `.ARC` | Titan Quest archive files containing models, textures, animations, and other assets |
| `.ARZ` | Titan Quest database files containing compiled records (`.DBR` / `.TXT`) |
| `.MSH` | Titan Quest 3D model files |
| `.ANM` | Titan Quest animation files |
| `.TEX` | Titan Quest texture files |

---

## Supported Export Formats

### 3D Models and Animations

| Format | Description |
|---|---|
| `.GLB` | glTF binary format, useful for previewing and modern 3D workflows (Like Blender) |
| `.FBX` | Common 3D exchange format used by tools such as Blender, Maya, and Unreal Engine |
| `.SMD` | Source Engine / Half-Life Studio Model Data format |
| `.OBJ` | Wavefront OBJ, a widely supported static mesh format |
| `.PSK/.PSA` | Unreal ActorX mesh and animation formats |

### Textures

| Format | Description |
|---|---|
| `.BMP` | Default texture export format |
| `.PNG` | Compressed image format useful for quick viewing and sharing |
| `.TGA` | Truevision TGA, commonly used by the Titan Quest Art Manager |
| `.PSD` | Photoshop document, useful for editing textures before re-importing |

### Audio

| Format | Description |
|---|---|
| `.MP3` | Compressed audio (converted with the bundled FFmpeg) |
| `.WAV` | Uncompressed audio extracted from archives |

---

## How It Works

1. Open the application.
2. Click **Open** or drag and drop supported files into the first screen.
3. The application detects the file type automatically.
4. Review the loaded assets in the TreeView.
5. Select the models, textures, and animations you want to export.
6. Choose the desired output formats.
7. Click **Next**.
8. Select the output folder.
9. Click **Export**.

---

## `.ARC` Archive Support

The tool can inspect `.ARC` archive files and display their contents.

The `.ARC` tree mirrors the archive's real folder structure, and you can preview and export assets directly from inside the archive without extracting it first.

Two organization modes are supported:

### Grouped by Type

```text
Creatures.arc
  Models
  Textures
  Animations
```

### Grouped by Affinity / Object

```text
Creatures.arc
  Bat
    Model
    Textures
    Animations
  Earth Elemental
    Model
    Textures
    Animations
```

The affinity view is useful when you want to export a complete object, such as a creature, with its model, textures, and animations together.

---

## `.ARZ` Database Support

The tool can open Titan Quest database archives (`.ARZ`), such as `database.arz`, and browse their records.

- Inspect compiled `.DBR` / `.TXT` records in the TreeView.
- Preview a record as a key/value list.
- Export a record to a text file.
- A search / filter box and lazy loading keep the interface responsive even with very large databases (~74k records).

---

## Export Folder Structure

The application organizes exported files automatically.

Example for a creature/model export:

```text
TQUE Export/
  bat/
    textures/
      BMP/
      PNG/
    model/
      GLB/
      FBX/
      SMD/
      PSK_PSA/
```

Example for texture-only export:

```text
TQUE Export/
  textures/
    BMP/
    PNG/
```

---

## Important Notes About `.ANM` Files

`.ANM` files contain animation data only.

To export or preview animations correctly, the related `.MSH` model file must be available. In many Titan Quest folders, animation files are stored inside an `anm` subfolder, while the model file is stored in the parent folder.

Example:

```text
monster/bat/bat01.msh
monster/bat/anm/bat_attalpha.anm
monster/bat/anm/bat_idle.anm
```

The application attempts to locate the related `.MSH` file automatically.

---

## 3D Preview

The application includes an internal 3D preview panel.

The preview is intended to help users quickly inspect models and animations before exporting. It includes a built-in animation player, and works directly on assets inside `.ARC` archives — no extraction required. When possible, the tool applies related textures automatically, and you can select which skin/texture to apply.

If no texture is found, the preview uses a darker background and adjusted material color to make the model easier to see.

---

## Texture Preview

`.TEX` files can be previewed directly inside the application.

The preview is pixel-perfect (1:1) instead of blurry, and includes zoom and adjustment sliders so you can inspect textures closely.

Textures can be exported as:

- `.BMP`
- `.PNG`
- `.TGA`
- `.PSD`

By default, `.BMP` is selected.

---

## Preferences & Language

- Set default **load** and **export** folders so you don't have to browse every time.
- The tool **auto-detects your Steam** Titan Quest installation when available.
- The interface **starts in English** by default; you can pick another language on first run and change it later in Preferences.

---

## Requirements

- Windows 64-bit
- Titan Quest asset files
- Microsoft Edge WebView2 Runtime for 3D preview

No .NET installation is required — the executable is self-contained. FFmpeg is bundled for `.MP3` conversion, so no extra install is needed.

If the 3D preview does not appear, install the Microsoft Edge WebView2 Runtime.

---


## Current Status

This is an early preview release.

The project is actively being improved. Current focus areas include:

- better `.ARC` archive grouping
- improved animation-to-model matching
- improved texture detection for 3D preview
- cleaner export organization
- better compatibility with Titan Quest assets
- improved preview and export feedback

---

## Roadmap

Planned or possible future improvements:

- Better 3D preview controls
- Better animation playback controls
- More detailed asset metadata
- Improved `.ARC` object grouping
- Batch export profiles
- Export presets for Blender, Unreal Engine, and modding workflows
- Public source code release in the future

---

## Disclaimer

This is an unofficial tool and is not affiliated with, endorsed by, or supported by the developers or publishers of Titan Quest.

Titan Quest and related assets belong to their respective owners.

This tool is intended for personal asset inspection, modding workflows, and educational purposes.

This release bundles [FFmpeg](https://ffmpeg.org), used under the terms of its GPL/LGPL license, for audio conversion.

---

## Download

Download the latest executable from the [Releases](https://github.com/ArlanSousa90/Titan-Quest-Ultimate-Exporter/releases/latest) section of this repository.

> Source code is not included in the current release.


## Images

> Initial interface
<img width="1159" height="836" alt="home" src="https://github.com/user-attachments/assets/0395ca5f-f58a-4894-bd26-854ebb24614a" />


> Select any TQ file
<img width="1124" height="586" alt="PickFile" src="https://github.com/user-attachments/assets/a2cf3a7c-a6c9-4cea-9c5b-056c6e14610b" />

> Preview loaded files and select the export format (models, animations and textures)
<img width="1153" height="817" alt="selectAll" src="https://github.com/user-attachments/assets/1691a8ce-21a5-4563-ae8d-35d494540d56" />

> Choose the output folder and export
<img width="1155" height="832" alt="exporting" src="https://github.com/user-attachments/assets/05d7e14d-e0f3-4eef-ac0e-2bd474744526" />

> Wait the extraction and convertion
<img width="1157" height="829" alt="logs" src="https://github.com/user-attachments/assets/daaeaf71-81f2-4eae-9724-79b15f9318b2" />

> Open the models using Blender, milkshape 3D or any other 3D software.
<img width="800" height="421" alt="image" src="https://github.com/user-attachments/assets/4442cb6a-81a7-4136-92fc-b6634204b3fc" />
