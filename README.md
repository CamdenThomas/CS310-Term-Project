# VR Game — Game Design Document

> **Engine:** Unreal Engine 5 (Epic Games Launcher) · **Target headset:** Meta Quest 2
> **Status:** Pre-production. Fill out every section before starting development.
> _Source idea: Notion › Projects › [VR Game](https://app.notion.com/p/3ed45edc13da80a2bddfe14387d30ba4)_

**How to use this template:** Replace each `_TBD_` and answer the prompts under each heading. Short answers are fine. The goal is to make every major decision up front so the dev plan follows from this doc.

---

## 1. Overview

### 1.1 Working Title
_TBD_

### 1.2 Elevator Pitch
How high can you go in one climb? Scale an endless cliff starting in the morning. As the day turns to night and you climb higher, the wind and cold get worse until a gust finally knocks you off. Then spend what you earned on upgrades and try again.

### 1.3 Original Concept Notes
- Climbing simulator
- Wind, birds, and falling rocks try to knock you down
- Harder positions on the wall burn stamina faster
- If you climb long enough, the weather or day cycle changes
- Infinitely generated wall

### 1.4 Genre & Tone
- **Genre:** Arcade endless climber with roguelite-style upgrades between runs
- **Tone / mood:** Easygoing and cartoonish at the start, getting tense as the run goes on
- **Learning style:** You learn as you go. Each fall teaches you something, and upgrades make the next run go further.

### 1.5 Target Audience
_Who is this for? VR beginners or experienced players? Average session length?_

### 1.6 Unique Selling Points
1. _TBD_
2. _TBD_
3. _TBD_

### 1.7 Inspirations / Reference Games
_e.g. The Climb 2, Gorilla Tag, Getting Over It. What do you take from each, and what do you avoid?_

---

## 2. Gameplay

### 2.1 Core Loop
Grab a hold → manage stamina → brace against wind and cold → reach the next hold → repeat.

### 2.2 Session Loop
1. **Menu:** In the small pre-climb menu, buy equipment or unlock skills, then press **Climb**.
2. **Morning:** Easy conditions, so you learn the wall.
3. **Day to first night:** Hazards start. The first night is only a little cold.
4. **Hazards build up:** The higher and longer you climb, the more hazards stack up (stronger and more frequent wind, colder fingers, darkness).
5. **Fall:** Eventually a gust or a lost grip knocks you off. The run is over.
6. **Results:** Your height is logged and your leaderboard rank is shown, then you go back to the menu.

### 2.3 Meta Loop / Progression
- Between runs, spend _TBD currency_ on **equipment** and/or a **skill tree** _(undecided: one, the other, or both)_.
- Upgrades counter specific hazards so each run goes further, which makes progression feel faster.
- How you earn currency: _TBD_ (e.g. based on height reached, collectibles on the wall)

### 2.4 Win / Lose Conditions
- **Win / goal:** None, the climb is endless. The goal is to beat your best height.
- **Fail state:** One fall ends the run. No checkpoints or lives.

### 2.5 Scoring
- **Score:** Highest point reached in one climb.
- **Leaderboard:** One leaderboard. Local or online: _TBD_

### 2.6 Difficulty Curve
Difficulty rises with **height and time**. Hazards stack instead of resetting.

| Phase | Trigger (height / time) | Conditions |
|-------|-------------------------|------------|
| Morning | Start | Calm, warm, good visibility |
| Afternoon | _TBD_ | Light wind gusts begin |
| First night | _TBD_ | Dark and mildly cold, with a small grip / stamina penalty |
| Following days / nights | _TBD_ | Wind gets faster and more frequent, each night is colder, and fingers freeze faster |
| Late run | _TBD_ | Cold, high, and windy at once, so a gust will eventually knock you off |

---

## 3. Mechanics & Systems

### 3.1 Climbing / Grabbing
- How does a grab work? (grip button, trigger, proximity to hold)
- Physics-based hands or kinematic hands?
- Can you grab any surface or only specific holds?
- One-handed hanging allowed?
- Jumping / lunging (dynos)?

### 3.2 Stamina System
- Per hand or a single shared bar?
- Drain rates by hold type / body position: _TBD_
- How does stamina recover? (rest ledges, both hands on good holds, items)
- What happens at zero stamina? (hand slips, forced drop)

### 3.3 Hold Types
| Hold | Description | Stamina Cost | Notes |
|------|-------------|--------------|-------|
| Jug | _TBD_ | _TBD_ | |
| Crimp | _TBD_ | _TBD_ | |
| Sloper | _TBD_ | _TBD_ | |
| Ledge / rest | _TBD_ | _TBD_ | |
| _Other_ | | | |

### 3.4 Hazards
| Hazard | Behavior | Telegraph / Warning | Counterplay | Introduced At |
|--------|----------|---------------------|-------------|---------------|
| Wind | _TBD_ | _TBD_ | _TBD_ | _TBD_ |
| Birds | _TBD_ | _TBD_ | _TBD_ | _TBD_ |
| Falling rocks | _TBD_ | _TBD_ | _TBD_ | _TBD_ |
| _Other_ | | | | |

### 3.5 Weather & Day/Night Cycle
Weather and night are **hazards that affect climbing ability**, not just how the game looks.

- **Cycle:** Starts in the morning. Time of day moves forward as you climb. Trigger: _TBD_ (real time, height, or both)
- **Night:** Lower visibility, and the cold builds faster. The first night is mild, and each later night is colder.
- **Cold / colder fingers:** _TBD effect_ (e.g. faster stamina drain, weaker grip, slower stamina recovery)
- **Wind:** Gusts push the player. They get stronger and more frequent as the run goes on.
- Other weather states (rain, snow, fog)? _TBD_

### 3.6 Procedural Wall Generation
- Generation approach: _TBD_ (pre-made chunks stitched together, fully procedural hold placement, hybrid)
- Chunk size and how far ahead / behind to keep loaded
- Rules that guarantee the wall is always climbable (max reach distance, rest spots)
- Seeded generation (repeatable runs / daily challenge)?
- How do biomes or themes change with height?

### 3.7 Equipment (bought between runs)
_Undecided whether to include. Ideas: each item counters a hazard._

| Item | Effect | Cost | Counters |
|------|--------|------|----------|
| Gloves | _TBD_ | _TBD_ | Cold |
| Chalk | _TBD_ | _TBD_ | Stamina drain |
| Headlamp | _TBD_ | _TBD_ | Night visibility |
| Windbreaker / harness | _TBD_ | _TBD_ | Wind |
| _TBD_ | | | |

### 3.8 Skill Tree
_Undecided whether to include. Possible branches:_
- **Endurance:** more stamina, faster recovery
- **Grip:** stronger hold on hard holds, resist wind
- **Cold resistance:** slower finger freezing
- Number of tiers, cost per node: _TBD_

### 3.9 Currency
- Name: _TBD_
- Earned by: _TBD_
- Spent in: the pre-climb menu (equipment / skill tree)

---

## 4. VR Design (Quest 2)

### 4.1 Play Space
- Standing, seated, or both?
- Roomscale or stationary? Minimum play area?

### 4.2 Locomotion
_Climbing is the main movement. Any other locomotion (smooth turn, snap turn, teleport on ledges)?_

### 4.3 Comfort & Motion Sickness
- Snap turn vs smooth turn options
- Vignette while falling / moving?
- What happens to the camera on a fall? (fade to black, slow fall, instant reset)
- Comfort settings menu: _TBD_

### 4.4 Controls Mapping (Quest Touch Controllers)
| Input | Action |
|-------|--------|
| Grip | _TBD_ |
| Trigger | _TBD_ |
| A / X | _TBD_ |
| B / Y | _TBD_ |
| Thumbstick | _TBD_ |
| Menu button | _TBD_ |

### 4.5 Hand Presence
_Hand models, gloves, or controllers? Hand tracking support (no controllers)?_

### 4.6 Haptics
_When do controllers vibrate? (grab, slipping, low stamina, hazard hit)_

### 4.7 Player Body / Avatar
_Floating hands only, or full body / arms (IK)?_

---

## 5. Technical Plan

### 5.1 Engine & Version
- **Engine:** Unreal Engine 5.__ (pick exact version and stick with it)
- **Blueprints, C++, or both?** Blueprints only
- **VR framework:** _TBD_ (OpenXR, Meta XR plugin, UE VR Template as a starting point)

### 5.2 Build Target
- **Standalone Quest 2 (Android APK)** or **PC VR via Quest Link / Air Link**? _TBD_
- If standalone: Android SDK/NDK setup, sideloading method (Meta Quest Developer Hub / adb)
- Rendering path: _TBD_ (mobile forward renderer for standalone)

### 5.3 Performance Budget
- Target frame rate: _TBD_ (72 / 90 / 120 Hz)
- Max draw calls / triangles per frame: _TBD_
- Lighting approach: _TBD_ (baked vs dynamic; dynamic day/night is expensive on Quest)
- Texture size limits: _TBD_
- How will you profile? (Unreal stat commands, OVR Metrics Tool, RenderDoc)

### 5.4 Key Systems / Architecture
_List the main classes or Blueprints you expect to need (e.g. VRPawn, GrabComponent, StaminaComponent, WallGenerator, HazardSpawner, WeatherManager, GameMode, SaveGame)._

### 5.5 Save Data
_What is saved? (high scores, settings, unlocks) Local only?_

### 5.6 Version Control
- Git with Git LFS for `.uasset` / `.umap`? _TBD_
- `.gitignore` for Unreal (Binaries, Intermediate, Saved, DerivedDataCache)

---

## 6. World & Level Design

### 6.1 Setting
_Where is this wall? (real mountain, fantasy cliff, sky tower) Is there lore or story?_

### 6.2 Level Structure
**One level, one zone:** a single endless wall. Variety comes from time of day, weather, and stacking hazards, not from new biomes (see 2.6).

### 6.3 Starting Area / Tutorial
No formal tutorial, players learn as they go. The calm morning start acts as a safe practice section. Optional first-run hints: _TBD_

### 6.4 Landmarks & Sense of Height
_How do players feel how high they are? (ground fading, clouds, height markers, skybox)_

---

## 7. Story & Narrative (optional)

- Is there a story? _TBD_
- Main character / who is climbing? _TBD_
- How is it delivered? (none, environmental, text, voice) _TBD_

---

## 8. Art Direction

### 8.1 Visual Style
Simple, cartoonish, low-poly. This also keeps Quest 2 performance manageable. Reference images / moodboard: _TBD_

### 8.2 Color Palette
_TBD_

### 8.3 Asset List
| Asset | Type | Source (make / Fab / free pack) | Priority |
|-------|------|---------------------------------|----------|
| Climbing holds | Mesh | _TBD_ | High |
| Wall chunks | Mesh | _TBD_ | High |
| Hands | Skeletal mesh | _TBD_ | High |
| Birds | Skeletal mesh + anim | _TBD_ | Medium |
| Rocks | Mesh | _TBD_ | Medium |
| Skybox / weather VFX | Material / Niagara | _TBD_ | Medium |

---

## 9. Audio

- **Music:** _TBD_ (style, dynamic with height or weather?)
- **SFX list:** grabbing, slipping, wind, bird calls, rockfall, heavy breathing at low stamina, falling, _TBD_
- **Spatial audio:** _TBD_ (directional warnings for incoming hazards)
- **Sources:** _TBD_ (self-made, free libraries, licensing)

---

## 10. UI / UX

### 10.1 Menus
- **Pre-climb menu (small):** shop / skill tree, plus a **Climb** button. Also settings: _TBD_
- **Game over:** height reached and leaderboard rank, then back to the menu
- **Pause:** _TBD_
- In-VR world-space panels vs. floating UI: _TBD_

### 10.2 HUD
_How is stamina shown? (watch on wrist, hand color, glove glow, no HUD) How are height and score shown?_

### 10.3 Feedback
_How does the player know a hold is grabbable, stamina is low, or a hazard is coming?_

### 10.4 Settings
_Comfort options, dominant hand, height calibration, audio volume, turning type._

---

## 11. Accessibility

- Seated mode / reach assistance
- Adjustable difficulty or stamina
- Subtitles or visual cues for audio warnings
- Colorblind-friendly hold and hazard indicators
- _TBD_

---

## 12. Scope & Production

### 12.1 MVP (Minimum Playable Version)
_The smallest version that proves the fun. Example: grab and climb + stamina + one hazard + generated wall + fall = restart._
- [ ] _TBD_
- [ ] _TBD_

### 12.2 Nice-to-Have Features
- [ ] _TBD_

### 12.3 Out of Scope (Won't Do)
- Multiple levels or zones / biomes
- Multiple leaderboards or game modes
- C++ (Blueprints only)
- _TBD_

### 12.4 Milestones
| Milestone | Goal | Target Date |
|-----------|------|-------------|
| Setup | UE5 project runs on Quest 2 (empty scene) | _TBD_ |
| Prototype | Grab and climb a static wall | _TBD_ |
| Core systems | Stamina, hazards, generation | _TBD_ |
| Content | Art, audio, weather, UI | _TBD_ |
| Polish / test | Performance, comfort, bugs | _TBD_ |
| Final | Submission build | _TBD_ |

### 12.5 Team & Roles
| Name | Role / Responsibilities |
|------|-------------------------|
| _TBD_ | _TBD_ |

### 12.6 Course Requirements
_Paste any CS310 assignment requirements, rubric items, or deadlines here so the design covers them._

---

## 13. Testing

- How will you playtest? (who, how often)
- What will you measure? (comfort, fun, difficulty, frame rate)
- How will you collect and act on feedback?

---

## 14. Risks & Open Questions

| Risk / Question | Impact | Plan / Mitigation |
|-----------------|--------|-------------------|
| Quest 2 performance with procedural walls + dynamic weather | High | _TBD_ |
| Motion sickness when falling | High | _TBD_ |
| Physics grab feels bad / jittery | Medium | _TBD_ |
| _TBD_ | | |

---

## 15. Changelog

| Date | Change |
|------|--------|
| 2026-10-02 | Created GDD template from Notion concept |
| 2026-10-02 | Filled in core loop, run structure, progression, hazard escalation, scope, art style, Blueprints |
