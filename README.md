# VR Climbing Game (working title TBD)

An endless VR climbing game for Meta Quest 2, built in Unreal Engine 5 with Blueprints. Climb as high as you can in one run while wind, cold, and nightfall make the wall harder, then spend what you earned on upgrades and go again.

CS310 term project. The full design is in [docs/GDD.md](docs/GDD.md).

**Status:** the project exists (Unreal Engine 5.8, VR template). Android build setup is in progress; nothing has run on a headset yet.

## Repository layout

```
.
├── README.md
├── docs/
│   └── GDD.md          Game design document
├── game.uproject       Unreal project file (created from the VR template)
├── Config/             Project settings (.ini, plain text)
├── Content/
│   ├── XRFramework/    Template VR pawn, input, and sample level
│   ├── XRMannequins/   Template hand and body meshes
│   ├── VRSpectator/    Template spectator camera
│   ├── LevelPrototyping/  Template blockout meshes
│   ├── Weapons/        Template sample props
│   └── Climb/          Everything we make
├── .gitattributes      Git LFS rules for binary assets
└── .gitignore
```

The template folders stay as a reference. Copy an asset into `Content/Climb/` before changing it instead of editing it in place.

### Inside `Content/Climb/`

| Folder | Holds |
|--------|-------|
| `Core/` | Game mode, game instance, save game, shared enums and structs |
| `Player/` | VR pawn, hands, grab and stamina components |
| `Wall/` | Hold actors, wall chunks, wall generator |
| `Hazards/` | Wind, birds, falling rocks |
| `Environment/` | Day/night cycle, weather, sky |
| `UI/` | Pre-climb menu, results screen, in-world HUD |
| `Data/` | Data tables and curves for tuning (hold types, difficulty phases, prices) |
| `Maps/` | Levels |
| `Art/` | Meshes, materials, textures, VFX |
| `Audio/` | Sound effects and music |

Folders are added when the first asset that belongs in them exists.

### Asset naming

| Prefix | Asset type |
|--------|------------|
| `BP_` | Blueprint actor |
| `BPC_` | Blueprint component |
| `BPI_` | Blueprint interface |
| `WBP_` | Widget Blueprint |
| `E_` / `S_` | Enum / struct |
| `DT_` | Data table |
| `SM_` | Static mesh |
| `M_` / `MI_` | Material / material instance |
| `T_` | Texture |
| `L_` | Level |

## Setup

You need:

1. **Unreal Engine 5** from the Epic Games Launcher. Everyone on the project must use the same version; this project uses **5.8**. In the launcher's install options for the engine, include the **Android** target platform.
2. **Android toolchain** for building to the headset. In the editor, use **Platforms › SDK Management › Android › Install Sdk**; it installs Android Studio and the SDK, NDK, and JDK versions this engine release expects. Log out and back in afterwards. Details are in Epic's [automated Android setup guide](https://dev.epicgames.com/documentation/unreal-engine/automated-android-sdk-ndk-and-jdk-setup-in-unreal-engine).
3. **A Quest 2 in developer mode**, connected by USB, with USB debugging allowed. Developer mode is turned on from the Meta Horizon phone app and needs a (free) Meta developer account.
4. **Git LFS** (`git lfs install` once per machine). Without it, `.uasset` and `.umap` files check out as small text pointers and the editor cannot open them.

### Running the game

Open `game.uproject`. To play on the headset, connect it, open the **Platforms** menu, and pick the Quest under the Android devices.

On macOS there is no Quest Link, so the editor's VR Preview does not work; the headset only runs packaged builds. On Windows with Link you can use VR Preview directly.

## Working with binary assets

Blueprints, levels, and most other Unreal assets are binary. Git cannot merge them, so:

- Only one person edits a given asset at a time. Say which assets you are working on before you start.
- Commit small and often, and pull before opening the editor.
- Keep logic in small, focused Blueprints and components rather than one large pawn or level Blueprint. That is also what keeps two people from needing the same file.

## Roadmap

| # | Milestone | Done when |
|---|-----------|-----------|
| 0 | Setup | The template level runs on a Quest 2 |
| 1 | Climb prototype | You can grab holds and pull yourself up a static wall |
| 2 | Stamina and hold types | Grip drains by hold type, and running out makes you fall |
| 3 | Run loop | Falling ends the run, shows height reached, and restarts |
| 4 | Wall generation | The wall builds itself above you and is always climbable |
| 5 | Hazards and day/night | Wind, cold, and darkness stack as the run goes on |
| 6 | Progression | Currency, upgrades, saved best height |
| 7 | Polish | Art, audio, comfort options, performance on device |

Milestones 1 to 3 are the minimum playable version.
