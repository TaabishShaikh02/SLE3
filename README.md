# SLE-3: Architectural Design (Full C4 Model) – 8-Puzzle Solver

**Course:** 02AML204 – Introduction to Artificial Intelligence
**Name:** Taabish Shaikh  |  **PRN:** 25UAM143  |  **Division:** B
**Date:** 04-Oct-2026

## Overview
This submission documents the architecture of the 8-Puzzle Solver (BFS / DFS / A*)
from SLE-1 (code) and SLE-2 (profiling and comparison). The system takes a 3x3
sliding-tile board (tiles 1–8 and a blank) and a goal board. It checks that the
puzzle is solvable, then runs the search algorithm the user picks. It reports the
moves, solution cost, nodes explored, time and memory.

## Contents
| File | Description |
|------|-------------|
| `25UAM143_SLE3.pdf` | SLE-3 report with the C4 diagrams (Levels 1–4) |
| `25UAM143_SLE3.docx` | Editable source of the report |
| `diagrams/` | Graphviz sources and exported images (optional) |

## C4 levels covered
1. **Context** – the User, Puzzle Config (input / .txt) and Console / Matplotlib display around the solver.
2. **Container** – Input Module, Search Engine, Heuristic Module, Memory / Visited Set, Output Module, Profiler.
3. **Component** – inside the Search Engine: Algorithm Selector, Frontier, Goal Test, Successor Generator, Explored Set, Path Reconstructor.
4. **Code** – classes `Node` and `Puzzle`, plus the functions `bfs`, `dfs`, `astar`, `misplaced_tiles`, `manhattan`, `reconstruct_path` and `show_solution`.

## Key design decisions
- The Heuristic Module is separate, so Manhattan and misplaced-tiles can be swapped without touching the search.
- The Visited Set is separate because the 8-puzzle has up to 181,440 reachable boards.
- BFS, DFS and A* share one loop and differ only in the Frontier type (queue, stack, priority queue).
- The Profiler sits outside the Search Engine so measuring does not change the algorithm.

## How to view
Open `25UAM143_SLE3.pdf`. If you edit the diagrams, regenerate them from the
Graphviz sources with `dot -Tpng file.dot -o file.png`.

## AI contribution note
Claude (Anthropic) helped draft the C4 diagrams (Graphviz) and the first version of
the report. [Update this to what you actually did.]

## Links
GitHub / Portfolio: <add link, or delete this line>
