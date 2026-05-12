# 🎮 GAME OF DSA — Algorithm Adventure Engine

> **An immersive C++ + Raylib educational game that transforms Data Structures & Algorithms into an interactive adventure world.**

[![Build & Deploy](https://github.com/vignesh2027/Game-of-DSA/actions/workflows/deploy.yml/badge.svg)](https://github.com/vignesh2027/Game-of-DSA/actions/workflows/deploy.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-cyan.svg)](LICENSE)
[![C++17](https://img.shields.io/badge/C%2B%2B-17-blue.svg)](https://en.cppreference.com/w/cpp/17)
[![Raylib 5.0](https://img.shields.io/badge/Raylib-5.0-green.svg)](https://raylib.com)

---

## 🌐 Play Online

**[▶ Play Now on GitHub Pages](https://vignesh2027.github.io/Game-of-DSA)**

No installation required — runs in your browser via WebAssembly.

---

## 🗺️ DSA Worlds

| World | Concept | Status |
|-------|---------|--------|
| 🌲 **Array Forest** | Arrays & Searching | ✅ Playable |
| 🌋 **Stack Volcano** | Stacks & LIFO | ✅ Playable |
| 🚂 **Queue Railway** | Queues & FIFO | ✅ Playable |
| 🏰 **Tree Kingdom** | BST & Traversal | ✅ Playable |
| 🌆 **Graph City** | Graphs & Pathfinding | ✅ Playable |
| ⚔️ **Sorting Arena** | Sorting Algorithms | ✅ Playable |
| 🏛️ **Recursion Temple** | Recursion & Backtracking | ✅ Playable |
| 💻 **Hash Cyber Arena** | Hash Maps & Collision | ✅ Playable |
| ⛰️ **Heap Mountain** | Heaps & Priority Queues | 🔜 Coming |
| ⏳ **DP Time Realm** | Dynamic Programming | 🔜 Coming |

---

## 🛠️ Tech Stack

- **Language**: C++17
- **Graphics**: [Raylib 5.0](https://raylib.com)
- **Build**: CMake 3.16+
- **Web**: Emscripten (WebAssembly)
- **Backend**: Firebase (Auth + Firestore + Realtime DB)
- **Deployment**: GitHub Pages via GitHub Actions

---

## 🚀 Building Locally

### Prerequisites
- CMake 3.16+
- A C++17 compiler (GCC 9+, Clang 11+, MSVC 2019+)
- (Optional) libcurl for Firebase networking on desktop

### Desktop Build
```bash
git clone https://github.com/vignesh2027/Game-of-DSA.git
cd Game-of-DSA
chmod +x scripts/build.sh
./scripts/build.sh          # Release build
./scripts/build.sh debug    # Debug build
```

Or with CMake directly:
```bash
cmake -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build --parallel
./build/GameOfDSA
```

### Web Build (requires Emscripten)
```bash
# Install Emscripten first:
git clone https://github.com/emscripten-core/emsdk.git ~/emsdk
cd ~/emsdk && ./emsdk install latest && ./emsdk activate latest

# Then build:
cd Game-of-DSA
./scripts/build.sh web

# Test locally:
cd docs && python3 -m http.server 8080
# Open http://localhost:8080
```

---

## 🔥 Firebase Setup (Optional)

1. Create a Firebase project at [console.firebase.google.com](https://console.firebase.google.com)
2. Enable **Authentication** (Email/Password) and **Firestore**
3. Copy your project credentials
4. Update `src/firebase/Firebase.h`:
   ```cpp
   static constexpr const char* PROJECT_ID = "your-project-id";
   static constexpr const char* API_KEY    = "your-api-key";
   ```
5. Update `web/shell.html` Firebase config section

---

## 🎮 Controls

| Action | Key / Mouse |
|--------|-------------|
| Navigate menus | Mouse click |
| Back / Exit world | ESC |
| Select algorithm | Click operation button |
| Input value | Type number + ENTER |
| Fullscreen | F11 |
| Scroll world select | Mouse wheel |

---

## 📐 Architecture

```
Game-of-DSA/
├── src/
│   ├── main.cpp              # Entry point
│   ├── core/
│   │   ├── Game.h/cpp        # Main game loop & screen management
│   │   ├── GameState.h       # PlayerData, Settings, GameContext
│   │   └── Colors.h          # Cyber color palette
│   ├── ui/
│   │   ├── UIComponents.h    # Buttons, panels, progress bars
│   │   └── Particle.h        # Particle system
│   ├── firebase/
│   │   └── Firebase.h        # REST API client (desktop + web)
│   ├── screens/
│   │   ├── SplashScreen.h    # Animated splash
│   │   ├── MainMenu.h        # Main menu with stats panel
│   │   ├── WorldSelect.h     # World map with card grid
│   │   └── LoginScreen.h     # Auth UI
│   └── worlds/
│       ├── World.h           # Base world class
│       ├── ArrayForest.h     # Array operations world
│       ├── StackVolcano.h    # Stack operations world
│       ├── QueueRailway.h    # Queue operations world
│       ├── TreeKingdom.h     # BST world
│       ├── GraphCity.h       # Graph algorithms world
│       ├── SortingArena.h    # Sorting visualizer world
│       ├── RecursionTemple.h # Recursion visualizer world
│       └── HashArena.h       # Hash map world
├── assets/levels/worlds.json # World/level configuration
├── web/shell.html            # Emscripten web shell
├── scripts/build.sh          # Build script
├── CMakeLists.txt            # CMake configuration
└── .github/workflows/deploy.yml  # CI/CD pipeline
```

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/new-world`
3. Commit changes: `git commit -m "Add DP Time Realm world"`
4. Push and open a PR

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

Made with ❤️ using C++ + Raylib | Deployed via GitHub Pages
