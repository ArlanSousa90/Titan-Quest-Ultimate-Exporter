# Titan Quest Ultimate Exporter

**Titan Quest Ultimate Exporter** is a Windows tool for inspecting, previewing, and exporting Titan Quest game assets.

It helps users work with Titan Quest files such as `.ARC`, `.MSH`, `.ANM`, and `.TEX` through a simple graphical interface, without needing to manually run command-line commands for each file.

> Current release: executable-only preview.  
> Source code is not publicly available at this time.

---

## Features

- Open one or more Titan Quest asset files.
- Drag and drop supported files directly into the application.
- Auto-detect supported file types.
- Inspect loaded assets using a TreeView.
- Preview `.TEX` texture files inside the application.
- Preview 3D models and animations inside the application.
- Export textures to `.BMP` and `.PNG`.
- Export models and animations to modern 3D formats.
- Organize exported files automatically by object and format.
- Show loading and export progress in the status bar.
- Support grouped views for `.ARC` archives.

---

## Supported File Types

| File Type | Description |
|---|---|
| `.ARC` | Titan Quest archive files containing models, textures, animations, and other assets |
| `.MSH` | Titan Quest 3D model files |
| `.ANM` | Titan Quest animation files |
| `.TEX` | Titan Quest texture files |

---

## Supported Export Formats

### 3D Models and Animations

| Format | Description |
|---|---|
| `.GLB` | glTF binary format, useful for previewing and modern 3D workflows |
| `.FBX` | Common 3D exchange format used by tools such as Blender, Maya, and Unreal Engine |
| `.SMD` | Source Engine / Half-Life Studio Model Data format |
| `.PSK/.PSA` | Unreal ActorX mesh and animation formats |

### Textures

| Format | Description |
|---|---|
| `.BMP` | Default texture export format |
| `.PNG` | Compressed image format useful for quick viewing and sharing |

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

The preview is intended to help users quickly inspect models and animations before exporting. When possible, the tool attempts to apply related textures automatically.

If no texture is found, the preview uses a darker background and adjusted material color to make the model easier to see.

---

## Texture Preview

`.TEX` files can be previewed directly inside the application.

The user can choose whether to export textures as:

- `.BMP`
- `.PNG`

By default, `.BMP` is selected.

---

## Requirements

- Windows
- Titan Quest asset files
- Microsoft Edge WebView2 Runtime for 3D preview

If the 3D preview does not appear, install the Microsoft Edge WebView2 Runtime.

---

## Installation

1. Download the latest release from the **Releases** section.
2. Extract the `.zip` file.
3. Run the executable.

> This release is currently distributed as an executable-only preview.

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

---

## Download

Download the latest executable from the **Releases** section of this repository.

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

