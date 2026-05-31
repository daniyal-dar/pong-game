# 🏓 Pong Game using raylib

A sleek, classic 2D retro arcade Pong implementation built from scratch in C++ using the Raylib multimedia library. This project showcases robust Object-Oriented Programming (OOP) architectures and custom gameplay mechanics, supporting both classic head-to-head local multi-player and an automated AI Bot system mode.

---

## 🚀 Download and Play

The game is pre-compiled and ready to run. You do not need to install Visual Studio or download the source code to play!

[![Download Game Here](https://img.shields.io/badge/DOWNLOAD-Game%20Executable-brightgreen?style=for-the-badge&logo=windows)](https://github.com/daniyal-dar/pong-game/releases/download/V1.0.0/pong.game.release.zip)

> ⚠️ **Note for Windows Users:** Because this is an independent, unsigned hobbyist executable, Windows Defender SmartScreen might flag it as an "unrecognized app" or throw a false positive warning. To launch, simply click **"More info"** on the blue warning window, and then select **"Run anyway"**.

---

## 🎮 Game Modes & Controls

The game features dual runtime configurations. Pressing `C` instantly switches the gameplay mode on the fly!

- **Player 1 (Left Paddle):** Move Up with `W` / Move Down with `S`
- **Player 2 (Right Paddle):** Move Up with `Up Arrow` / Move Down with `Down Arrow`
- **Bot Mode (Right AI):** Automated tracking (Self-Regulating)
- **System Control:** Press `C` to switch between 2v2 and 1vBot mode

---

## 📁 Repository Structure

- **assets/**: Embedded multimedia resources like audio clips and sound effects.
- **code/**: Clean native C++ source files (.cpp, .h, .hpp modules).
- **docs/**: Technical specifications, UML definitions, and configuration lists.
- **raylib/**: Local static Raylib framework dependencies (headers, libs).
- **.gitignore**: Global environment build-exclusion file to keep the repository clean.

---

## 🛠️ Architecture & Structural OOP Design

The software divides game physics, tracking, scoring, and drawing routines across isolated classes designed around structural Object-Oriented principles.

### Core Class Profiles
- **Player**: Tracks individual statistics including string metrics (`name`) and real-time scoring states (`score`). Exposes score advancement hooks (`incScore()`) and text coordinates alignment.
- **Paddle**: The physical base entity mapping 2D floating-point coordinates, boundary spaces, bounding rectangles, rendering hues, and basic controller updating frames.
- **Bot**: An intelligent extension of the `Paddle` object via structural inheritance. Overrides behavior to track the vertical axis rendering vector of the active `Ball` dynamically.
- **Ball**: Regulates dimensional movement vectors, automated state resets using a `resetTimer` setup, audio cue interaction handling, and structural dependencies to scale and update player scores.

---

## ⚙️ Compilation and Environment Configuration

To safely compile, run, and link this software locally inside Visual Studio 2022, open the solution and apply the following steps:

### 1. Project Global Targeting
- Right-click your project name in the Solution Explorer and select **Properties**.
- Set the **Configuration** dropdown context to **All Configurations**.
- Set the **Platform** dropdown target to **x64**.

### 2. Explicit Library Paths Configuration
- **Header Maps**: Navigate to `C/C++` -> `General` -> `Additional Include Directories` and add:
  `$(ProjectDir)..\raylib\include`
- **Binary Lib Links**: Navigate to `Linker` -> `General` -> `Additional Library Directories` and add:
  `$(ProjectDir)..\raylib\lib`
- **Linker Dependencies**: Navigate to `Linker` -> `Input` -> `Additional Dependencies` and add these five low-level system mapping extensions:
  - `raylib.lib`
  - `winmm.lib`
  - `gdi32.lib`
  - `user32.lib`
  - `shell32.lib`

---

## 📟 Framework API Integrations

The architecture directly consumes low-level engine methods native to the Raylib ecosystem to coordinate assets, runtime frame limits, and shape transformations:

### Window & Screen Tracking
- `InitWindow()`: Handles core application interface dimensions and application title tags.
- `SetTargetFPS()`: Locks updates cleanly to target rates for delta stability across hardware variants.
- `WindowShouldClose()`: Explicit boolean polling loop looking for escape triggers or window exits.

### Drawing Loop Layout
- Rendering arrays use synchronized engine context buffers sandwiched cleanly between `BeginDrawing()` and `EndDrawing()` checkpoints over an active `ClearBackground()` color reset pattern.
- Screen objects utilize procedural drawing definitions including `DrawCircle()`, `DrawRectangle()`, `DrawRectangleRounded()`, and vector paths via `DrawLine()`.

### Audio Pipeline Control
- Multi-channel tracking hooks are processed using `InitAudioDevice()` and terminated on exit with `CloseAudioDevice()`.
- Live tracking variables (.mp3 or .wav sound clips) stream via `LoadSound()`, fire actions with `PlaySound()`, and purge clean memory allocations via `UnloadSound()`.

---

## 📄 License

This software release is provided under standard open-use guidelines. See the repository documentation module for extended asset configuration and details.
