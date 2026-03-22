# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A collection of browser-based games built as standalone HTML files — no build system, no dependencies, no server required. Open any `.html` file directly in a browser to run it.

## Files

- `index.html` — Landing page (currently a placeholder "Hello world")
- `tictactoe.html` — Two-player Tic Tac Toe with score tracking and win animations
- `shooter.html` — Top-down shooter with multiple levels, enemy types (walker, runner, tank, boss), waves, pickups, and a canvas-based game loop

## Architecture

Each game is fully self-contained in a single HTML file: CSS in `<style>`, logic in `<script>`, no external assets or imports.

**Tic Tac Toe** (`tictactoe.html`): DOM-based. Game state is a flat 9-element array. Win detection checks all 8 combinations in `WINS`. Score persists across rounds within a session.

**Top-Down Shooter** (`shooter.html`): Canvas-based (`800×600`). Uses a `requestAnimationFrame` game loop. State machine: `MENU → PLAYING → WAVE_CLEAR → LEVEL_CLEAR → GAME_OVER / WIN`. Levels are defined in a `LEVELS` array with wave compositions. Input is tracked via `keys` object (keyboard) and `mouse` object (position + click state).

## Git Workflow

After every code change, commit and push to GitHub (`origin main`).
