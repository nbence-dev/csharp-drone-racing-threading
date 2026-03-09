# 🚁 CSharp Drone Racing — Multithreaded Simulation

A console-based drone racing simulation built with **C# and .NET 8**, where five drones compete simultaneously across a 25 km course. Each drone runs on its own thread, racing in real time until one crosses the finish line first.

---

## 📋 About

This project demonstrates **multithreaded programming in C#** using `System.Threading`. Five drones are created, each assigned to its own `Thread`. They race concurrently by randomly advancing between 1–5 km per step. A `lock` object ensures thread-safe winner detection — only the first drone to reach or exceed 25 km is declared the winner.

---

## 🛠️ Tech Stack

| Technology | Version |
|---|---|
| Language | C# |
| Framework | .NET 8 |
| IDE | JetBrains Rider / Visual Studio |

---

## 🚀 Getting Started

### Prerequisites

- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0) installed on your machine
- A terminal or an IDE such as [JetBrains Rider](https://www.jetbrains.com/rider/) or [Visual Studio](https://visualstudio.microsoft.com/)

### Clone the Repository

```bash
git clone https://github.com/<your-username>/csharp-drone-racing-threading.git
cd csharp-drone-racing-threading
```

### Build the Project

```bash
dotnet build
```

### Run the Project

```bash
cd Question3_New
dotnet run
```

---

## 🎮 How It Works

1. The program launches and displays a race start banner.
2. **5 Drone objects** are created, each numbered 1–5.
3. Each drone is assigned its own **`Thread`**, which calls `drone.StartRace()`.
4. All threads start simultaneously — the race is live!
5. Each drone randomly advances **1–5 km** per step, printing its progress to the console.
6. The first drone whose `DistanceTravelled >= 25` acquires the **lock** and is declared the winner.
7. All threads `Join()` back to the main thread before the final winner announcement is printed.

---

## 📂 Project Structure

```
Question3_New/
├── Program.cs       # Entry point — sets up drones, threads, and displays the winner
├── drone.cs         # Drone class — handles racing logic, threading, and winner detection
└── Question3_New.csproj
```

---

## 💡 Key Concepts Demonstrated

- 🔷 **Multithreading** — each drone runs concurrently using `System.Threading.Thread`
- 🔷 **Thread Safety** — `lock` statement prevents race conditions on winner detection
- 🔷 **Static shared state** — a `static drone winner` field shared across all instances
- 🔷 **Object-Oriented Programming** — encapsulated `drone` class with properties and methods
- 🔷 **`Thread.Join()`** — main thread waits for all drones to finish before exiting
- 🔷 **Randomisation** — `Random.Next()` drives unpredictable race outcomes

---

## 📸 Sample Output

```
==========================================================
                     Drone Racing
                 Let the race begin!
==========================================================
Drone 3 has travelled 4 km.
Drone 1 has travelled 2 km.
Drone 5 has travelled 5 km.
...
==========================================================
Drone 3 finished the race!
==========================================================
...
==========================================================

The winner is Drone 3!
All drones have completed the race!
```

> Note: Output order will vary each run due to thread scheduling and random advancement.

---

## 📚 Academic Context

This project was developed as part of **Year 2 Programming coursework (Q3, 2025)**. The goal was to apply multithreading concepts in a practical, real-world-inspired scenario using C# and .NET 8.

---

## 📄 License

This project is for educational purposes.

