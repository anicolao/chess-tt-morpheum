# MVP Design

This document outlines the architecture and technical design for the Minimum Viable Product (MVP) of Tabletop Chess.

## Architecture
- **Framework**: SvelteKit single-page application.
- **Hosting**: Static Site Generation (SSG) using `@sveltejs/adapter-static` for deployment to GitHub Pages.
- **PWA**: Setup offline support using standard Service Workers or a SvelteKit PWA plugin.

## Game Logic
- We will leverage an existing, well-tested chess logic library (e.g., `chess.js`) to handle move validation, game state (FEN), check/checkmate detection, and move history.
- The app will not require a backend. All state is maintained locally in the browser.

## UI / UX Layout
- **The Board**: Centered on the screen. The pieces must be easily recognizable from both sides, or specifically stylized to look good from any angle.
- **Player Controls**: The screen will be divided logically. Player 1's controls (timers, captured pieces, undo/resign buttons) will be oriented normally at the bottom of the screen. Player 2's controls will be rendered at the top of the screen and rotated 180 degrees using CSS transforms, so they appear right-side up to the person sitting across the table.

## Testing Strategy
- **End-to-End (E2E)**: We will heavily rely on **Playwright** for E2E testing, simulating a sequence of touches/clicks across the board to ensure valid moves are accepted and invalid moves are rejected.
- Tests will also verify that the UI components render in their correct orientations.

## Data Models
- Game state will be stored in Svelte 5 runes/stores.
- A single game session object will contain:
  - Current FEN string.
  - Move history.
  - Timers (if a chess clock feature is enabled in the MVP).

## State Management & Architecture
- **Redux & Event Sourcing**: There is a strict requirement to use Redux for managing game and UI state. Furthermore, all state mutations must be modeled using Event Sourcing to ensure a reproducible, reliable, and testable timeline of game and UI events.
