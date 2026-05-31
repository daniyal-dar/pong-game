# 🏓 Pong Game using raylib

A sleek, classic 2D retro arcade Pong implementation built from scratch in C++ using the Raylib multimedia library. This project showcases robust Object-Oriented Programming (OOP) architectures and custom gameplay mechanics, supporting both classic head-to-head local multi-player and an automated AI Bot system mode.

---

## 🚀 Download and Play

The game is pre-compiled and ready to run. You do not need to install Visual Studio or download the source code to play!

[![Download Game Here](https://img.shields.io/badge/DOWNLOAD-Game%20Executable-brightgreen?style=for-the-badge&logo=windows)](https://github.com/daniyal-dar/pong-game/releases/latest)

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
- [cite_start]**Player**: Tracks individual statistics including string metrics (`name`) and real-time scoring states (`score`)[cite: 63, 64]. [cite_start]Exposes score advancement hooks (`incScore()`) and text coordinates alignment[cite: 64].
- [cite_start]**Paddle**: The physical base entity mapping 2D floating-point coordinates, boundary spaces, bounding rectangles, rendering hues, and basic controller updating frames[cite: 59, 60].
- [cite_start]**Bot**: An intelligent extension of the `Paddle` object via structural inheritance[cite: 61, 64]. [cite_start]Overrides behavior to track the vertical axis rendering vector of the active `Ball` dynamically[cite: 61].
- [cite_start]**Ball**: Regulates dimensional movement vectors, automated state resets using a `resetTimer` setup, audio cue interaction handling, and structural dependencies to scale and update player scores[cite: 61, 62, 63].

---

## ⚙️ Compilation and Environment Configuration

[cite_start]To safely compile, run, and link this software locally inside Visual Studio 2022, open the solution and apply the following steps[cite: 1]:

### 1. Project Global Targeting
- [cite_start]Right-click your project name in the Solution Explorer and select **Properties**[cite: 1].
- [cite_start]Set the **Configuration** dropdown context to **All Configurations**[cite: 2].
- [cite_start]Set the **Platform** dropdown target to **x64**[cite: 2].

### 2. Explicit Library Paths Configuration
- [cite_start]**Header Maps**: Navigate to `C/C++` -> `General` -> `Additional Include Directories` and add[cite: 3]:
  [cite_start]`$(ProjectDir)..\raylib\include` [cite: 4]
- [cite_start]**Binary Lib Links**: Navigate to `Linker` -> `General` -> `Additional Library Directories` and add[cite: 4]:
  [cite_start]`$(ProjectDir)..\raylib\lib` [cite: 5]
- [cite_start]**Linker Dependencies**: Navigate to `Linker` -> `Input` -> `Additional Dependencies` and add these five low-level system mapping extensions[cite: 5]:
  - [cite_start]`raylib.lib` [cite: 5]
  - [cite_start]`winmm.lib` [cite: 5]
  - [cite_start]`gdi32.lib` [cite: 5]
  - [cite_start]`user32.lib` [cite: 5]
  - [cite_start]`shell32.lib` [cite: 5]

---

## 📟 Framework API Integrations

[cite_start]The architecture directly consumes low-level engine methods native to the Raylib ecosystem to coordinate assets, runtime frame limits, and shape transformations[cite: 6]:

### Window & Screen Tracking
- [cite_start]`InitWindow()`: Handles core application interface dimensions and application title tags[cite: 6, 7].
- [cite_start]`SetTargetFPS()`: Locks updates cleanly to target rates for delta stability across hardware variants[cite: 8, 9].
- [cite_start]`WindowShouldClose()`: Explicit boolean polling loop looking for escape triggers or window exits[cite: 10, 11].

### Drawing Loop Layout
- [cite_start]Rendering arrays use synchronized engine context buffers sandwiched cleanly between `BeginDrawing()` and `EndDrawing()` checkpoints over an active `ClearBackground()` color reset pattern[cite: 16, 17, 18, 19, 20, 21].
- [cite_start]Screen objects utilize procedural drawing definitions including `DrawCircle()` [cite: 22, 23][cite_start], `DrawRectangle()` [cite: 24, 25][cite_start], `DrawRectangleRounded()` [cite: 26, 27, 28][cite_start], and vector paths via `DrawLine()`[cite: 29, 30, 31].

### Audio Pipeline Control
- [cite_start]Multi-channel tracking hooks are processed using `InitAudioDevice()` [cite: 51, 52] [cite_start]and terminated on exit with `CloseAudioDevice()`[cite: 56].
- [cite_start]Live tracking variables (.mp3 or .wav sound clips) stream via `LoadSound()` [cite: 52, 53][cite_start], fire actions with `PlaySound()` [cite: 53, 54][cite_start], and purge clean memory allocations via `UnloadSound()`[cite: 54, 55].

---

## 📄 License

This software release is provided under standard open-use guidelines. See the repository documentation module for extended asset configuration and details.
