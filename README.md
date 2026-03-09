# 橋をかけろ — Hashi

A browser-based implementation of the Japanese logic puzzle **Hashiwokakero** (橋をかけろ, "build bridges"), written in a single self-contained HTML5 file with no dependencies.

## How to Play

Open `index.html` in any modern browser — no build step or server required.

### Rules

- Each circle (island) contains a number indicating how many bridges must connect to it.
- Bridges run horizontally or vertically between islands.
- At most **2 bridges** may connect any pair of islands.
- Bridges **cannot cross** each other.
- When solved, all bridges form a **single connected network** spanning every island.

### Controls

| Action | Result |
|--------|--------|
| Click an island | Select it (highlighted in gold) |
| Click a reachable neighbor | Place a bridge (or add a second bridge, or remove if already doubled) |
| Click the selected island again | Deselect |
| Click empty space | Deselect |
| Right-click / Escape | Deselect |

A dashed hint line appears when hovering over a reachable island while another is selected.

## Difficulty Levels

| Level | Grid | Islands | Description |
|-------|------|---------|-------------|
| Easy | 7 × 7 | ~9 | Small grid, good for learning |
| Medium | 10 × 10 | ~17 | Balanced challenge |
| Hard | 13 × 13 | ~27 | Large grid requiring careful deduction |

Select a difficulty and press **New Game** to generate a fresh random puzzle.

## Features

- Procedurally generated puzzles — every game is unique
- Visual feedback: island borders turn **green** when satisfied, **red** when over-bridged
- Win detection checks both island values and full connectivity
- Works offline, no dependencies, single file

## Technical Notes

- Pure HTML5 Canvas + vanilla JavaScript (ES6+)
- Puzzle generation uses a union-find spanning tree to guarantee connectivity, then adds extra bridges while preventing crossings
- All bridge-crossing checks use axis-aligned segment intersection
