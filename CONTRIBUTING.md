# Contributing to Hoop Legends

Thanks for wanting to help! This project is small on purpose: one HTML file, no build tools. Contributions of any size are welcome.

## Ways to contribute

- **Report a bug**: open an issue with the browser and device you used, the steps to reproduce, what you expected and what happened. Screenshots or a short screen recording help a lot.
- **Suggest a feature**: open an issue describing the idea and why it would make the game better.
- **Send a pull request**: fixes, polish, new features, translations or documentation improvements.

## Getting started

1. Fork the repository and clone your fork.
2. Create a branch: `git checkout -b fix/short-description` (or `feat/short-description`).
3. Open `index.html` in your browser, or serve the folder with `python3 -m http.server 8000`.
4. Edit `index.html`, refresh, and test.

There is nothing to install or compile.

## Code guidelines

- Keep the game a **single self-contained `index.html`** unless a change clearly needs more files.
- Use plain JavaScript (no frameworks or build steps).
- Keep the existing section layout: audio, rendering, physics, input and main loop.
- Match the surrounding code style (2-space indentation, `const`/`let`, short comments that explain *why*).
- Don't add new external scripts or fonts without discussing it in an issue first. Every external resource must come from a trusted CDN and be pinned to an exact version.
- Keep the game playable with touch, mouse **and** keyboard.
- Respect `prefers-reduced-motion` for new animations.

## Test checklist

Before opening a pull request, check these by hand:

- [ ] The welcome screen shows, and the music starts after the first tap or key press
- [ ] **PLAY GAME** starts the match and the music stops immediately
- [ ] Aiming works with drag (touch and mouse) and with the arrow keys
- [ ] A basket gives +10, a miss gives −10, and the score never goes below 0
- [ ] Reaching 100 points ends the match; when time runs out the higher score wins
- [ ] The Restart and Play Again buttons return to the welcome screen
- [ ] The sound toggle mutes and unmutes
- [ ] The layout still works on a phone (portrait and landscape) and on desktop
- [ ] The browser console shows no errors

## Commit messages

Short, present-tense summaries, for example:

```
fix: ball no longer sticks to the rim
feat: add a sudden-death round for draws
docs: clarify the keyboard controls
```

## Pull requests

- Keep each pull request focused on one change.
- Describe what changed and why, and add a screenshot or GIF for anything visual.
- Add a line to the `Unreleased` section of [CHANGELOG.md](CHANGELOG.md).

## Licensing

By contributing you agree that your contribution is released under the project's [MIT License](LICENSE).
