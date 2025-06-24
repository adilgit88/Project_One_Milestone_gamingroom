

```markdown
# CS 230 • Project One – _Game Service Application_

A Java mini-game framework that demonstrates two classic design patterns—**Singleton** and **Iterator**—in the context of managing multiple game instances.  
This repository contains the starter code provided by SNHU plus the milestone deliverables (completed UML, updated source files, and tests).

---

## ✨ Project Highlights
| Pattern | Class / Method | What It Solves |
|---------|----------------|----------------|
| **Singleton** | `GameService` | Guarantees exactly one in-memory service that hands out game IDs and keeps global state. |
| **Iterator** | `GameService#addGame` / `getGame` | Traverses the collection of active games to enforce unique names and allow look-ups. |

---

## 📂 Repository Layout

```

📦cs-230-game-service
├─ docs/                  ← UML class diagram (`GameServiceSingleton.png`)
├─ src/
│  └─ main/
│     └─ java/
│        └─ edu/snhu/game/
│           ├─ GameService.java     ← Singleton + Iterator logic
│           ├─ ProgramDriver.java   ← Console entry-point
│           ├─ SingletonTester.java ← JUnit verification
│           ├─ Player.java          ← (provided; to be completed in a later milestone)
│           └─ Team.java            ← (provided; to be completed in a later milestone)
└─ README.md              ← You are here

````

---

## 🚀 Quick Start

1. **Clone and import into Eclipse**

   ```bash
   git clone https://github.com/<your-username>/cs-230-game-service.git
````

*File ▶ Import ▶ Existing Projects into Workspace*, then select the folder you just cloned.

2. **Run the application**

   *Right-click* **ProgramDriver.java** ▶ *Run As ▶ Java Application*.

3. **Run the unit tests** (optional)

   *Right-click* the `test` package ▶ *Run As ▶ JUnit Test*.

> **Java version**: Tested on JDK 17. Any Java 11+ runtime should work.

---

## 🛠️ Design Patterns in Detail

### Singleton (`GameService`)

* **Private constructor** prevents external instantiation.
* **`private static GameService instance`** holds the sole object.
* **`public static GameService getInstance()`** lazily creates (or returns) the instance.
* Thread-safety is not a requirement for the milestone; if you extend this, consider double-checked locking.

### Iterator (Java Collections)

The `games` list is a standard `ArrayList<Game>`.
`addGame` and `getGame` rely on the enhanced `for` loop (syntactic sugar for the `Iterator` interface) to:

1. Walk through all existing games.
2. Compare each game’s unique name.
3. Return or reject duplicates in `O(n)` time.

---

## 🖼️ UML Diagram

The completed class diagram is in **`docs/GameServiceSingleton.png`** (exported from Lucidchart).
Use it as a quick reference for attributes, methods, and relationships.

---

## ✍️ How to Contribute

Pull requests are welcome for refactoring, adding tests, or implementing the remaining `Player` and `Team` functionality. Please open an issue to discuss changes first.

---

## 📜 License

This project is released for educational purposes under the MIT License. See **LICENSE** for details.

---

