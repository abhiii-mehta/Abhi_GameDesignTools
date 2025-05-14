# Game Architecture Package

This is my default Unity starter package — a reusable foundation I use in every new game project. It includes modular UI systems, scene loading functionality, and a complete local player profile + high score manager.

---

##  What’s Included

###  UI Systems

- **Main Menu** with:
  - Level Selection
  - Sound Toggle
  - Credits Panel
- **Pause Menu**
- **Game Over Panel**

###  Scene Management

- Loads game scenes using `SceneManager.LoadSceneAsync`
- Built-in loading screen panel
- Debug logs if a scene is missing from Build Settings

###  Player Profile System

- Add, select, and delete up to 5 local player profiles
- Tracks and saves high scores for each player using `PlayerPrefs`
- Prefabs for UI panel and slot system

---

##  How to Use

1. **Import the package** into your Unity project
2. Drag the following prefabs into your scene:
   - `MainMenuBundle` (for menus)
   - `PlayerSelectPanel` (for name selection)
   - `PlayerProfileManager` (empty object with save logic)
3. Assign the required references in the Inspector:
   - `PlayerSelectUI` → needs player slot prefab, container, buttons
4. Hook up UI buttons to:
   - `MenuManager.cs` → for Start, Exit, Pause
   - `PlayerSelectUI.cs` → for profile selection
5. Add your game scenes (e.g., `Level01`, `GameScene`) to Build Settings
6. Customize UI visuals and flow as needed

---

##  Requirements

- Unity 2021.3 or newer
- TextMeshPro (auto-included)
- Works with both built-in and URP pipelines

---

##  Author

**Made by Abhi** — game designer & developer  
This is my personal architecture to reduce repetition and speed up development in game jams, prototypes, and full games.

