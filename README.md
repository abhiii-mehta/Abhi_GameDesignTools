# Game Architecture Package

This is my default Unity starter package — a reusable foundation I use in every new game project. It includes modular UI systems, scene loading, player profiles with high scores, and a dialogue system using Yarn Spinner.

---

## What's Included

### UI Systems

- **Main Menu**  
  - Level Selection  
  - Sound Toggle  
  - Credits Panel  
- **Pause Menu**
- **Game Over Panel**

### Scene Management

- Async scene loading via `SceneManager.LoadSceneAsync`
- Loading screen prefab
- Debug log if scenes are missing in Build Settings

### Player Profile System

- Add, delete, and select up to 5 player profiles
- Each player has an individual high score
- Data saved using `PlayerPrefs`
- Modular UI with prefab slot templates

### Dialogue System (Yarn Spinner)

- Yarn Spinner-based dialogue system
- Supports branching dialogue, choices, and markup
- Comes with an **example scene** showcasing integration
- Fully customizable via Yarn’s Unity UI system

---

## How to Use

1. **Import this package** into any Unity 2021.3+ project.
2. Drag in prefabs:
   - `MainMenuBundle` (main UI)
   - `PlayerSelectPanel` (profile screen)
   - `PlayerProfileManager` (logic)
   - `Dialogue System` prefab (for Yarn)
3. Assign inspector references:
   - `PlayerSelectUI` → slot prefab, container, buttons
   - `MenuManager.cs` → for scene and panel transitions
4. Add your game scenes (e.g., `Level01`, `GameScene`) to Build Settings.
5. Customize the UI and logic to fit your game.

---

## Dependencies

- Unity 2021.3 or newer
- TextMeshPro (`com.unity.textmeshpro`)
- [Yarn Spinner](https://yarnspinner.dev) (`dev.yarnspinner.dialogue`)

To automatically install Yarn Spinner, make sure this line is in your `package.json`:

```json
"dependencies": {
  "dev.yarnspinner.dialogue": "2.0.0"
}


---

## Author

**Made by Abhi** — game designer & developer  
This is my personal architecture to reduce repetition and speed up development in game jams, prototypes, and full games.

