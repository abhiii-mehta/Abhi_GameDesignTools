# Game Architecture Package

This is my default Unity starter package — a reusable foundation I use in every new game project. It includes modular UI systems, scene loading, player profiles with high scores, and a dialogue system using Yarn Spinner.

---

## What's Included:

### UI Systems (Menu Package)

* **Main Menu** with:

  * Level selection
  * Sound toggle
  * Credits panel
* **Pause Menu**
* **Game Over Panel**
* Clean & customizable layout (TextMeshPro-based)

### Scene Management

* Asynchronous scene loading with `SceneManager.LoadSceneAsync`
* Loading screen panel prefab
* Debug log for missing scenes in Build Settings

### High Score Manager (Player Profile System)

* Add, delete, and select up to 5 player profiles
* Each player tracks their own high score
* All data saved using `PlayerPrefs`
* Modular and UI-ready with reusable prefabs

### Dialogue System (Yarn Spinner)

* Fully integrated Yarn Spinner dialogue system
* Branching dialogue, player choices, variable support
* Built-in prefab with sample `.yarn` script
* Example scene included

---

## Architecture Principles

* Clean modular structure in `/Runtime/`
* Single entry point through `MenuManager.cs`
* Decoupled UI logic from visuals
* Easily extendable across multiple Unity projects

---

#  How to Use

## UI Systems (Menus)

**1. Prefabs to Use**

* `MainMenuBundle`
* `PausePanel`
* `GameOverPanel`

**2. Hook Up Buttons**

* Use `MenuManager.cs` to:

  * Start game: `LoadScene(string sceneName)`
  * Pause/resume: `TogglePause()`
  * Exit game: `ExitGame()`

**3. Customize**

* Modify button visuals in prefab
* Add your own transitions, animations, or sound FX

---

## Scene Loading System

**1. Setup**

* Add your game scenes in `File > Build Settings`
* Use `MenuManager.cs` or `SceneLoader.cs` to load them

**2. Use in Code**

```csharp
SceneManager.LoadSceneAsync("Level01");
```

**3. Optional**

* Use the loading screen prefab during transitions
* It auto-hides after scene load completes

---

## High Score Manager (Player Profile System)

**1. Add These Prefabs**

* `PlayerProfileManager` (GameObject)
* `PlayerSelectPanel` (Canvas UI)
* `PlayerSlotPanel` (Slot prefab for each player)

**2. Assign in `PlayerSelectUI.cs`**

* `playerSlotPrefab` → `PlayerSlotPanel`
* `playerListContainer` → Vertical layout group
* `continueButton`, `deleteAllDataButton` → your UI buttons

**3. Player Slot Setup**

* Each slot must have:

  * Player name text
  * Score text
  * Select button
  * Delete button

**4. Save Score in Code**

```csharp
HighScoreManager.TrySetNewHighScore(120);
```

**5. Load Score**

```csharp
int best = HighScoreManager.GetCurrentHighScore();
```

---

## Dialogue System (Yarn Spinner)

**1. Install Dependency**
Add to `manifest.json`:

```json
"dev.yarnspinner.dialogue": "2.0.0"
```

**2. Add to Scene**

* Drag in `DialogueSystem.prefab` (with Dialogue Runner, Line View, Option View)
* Assign `.yarn` script to the Yarn Project field

**3. Write Your Yarn Script**

```yarn
title: Start
---
Hello, traveler!
-> Tell me more
    This is Yarn Spinner.
-> Goodbye
    See you later!
===
```

**4. Trigger Dialogue**

```csharp
DialogueRunner runner = FindObjectOfType<DialogueRunner>();
runner.StartDialogue("Start");
```

---

## Dependencies

* Unity 2021.3 or newer
* TextMeshPro (`com.unity.textmeshpro`)
* Yarn Spinner (`dev.yarnspinner.dialogue`)

---

## Author

Made by **Abhi** — game designer & developer
Built to reduce repetition and speed up development in game jams, prototypes, and full games.
