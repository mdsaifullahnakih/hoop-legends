# 🏀 Hoop Legends

A fast, two-player 3D basketball shooting game that runs entirely in your browser. No install, no build step, no backend: just open the page and play.

[![License: MIT](https://img.shields.io/badge/License-MIT-orange.svg)](LICENSE)
![Made with Three.js](https://img.shields.io/badge/Made%20with-Three.js-black)

**▶ Play it here: https://YOUR-USERNAME.github.io/hoop-legends/**

<!-- Add a screenshot or GIF here:  ![Hoop Legends](docs/screenshot.png) -->

## Features

- Two players, turn-based shooting on one device
- 3D court, ball physics and net, rendered with Three.js
- Drag-to-aim controls for touch and mouse, plus full keyboard support
- Live scoreboard, 2:30 match clock and a vertical power meter
- Win by reaching 100 points, or by leading when the clock runs out
- Sound effects, victory fireworks and applause
- Welcome-screen background music that stops the moment the match starts
- Responsive layout for phones, tablets and desktops (portrait and landscape)
- One self-contained `index.html` file

## How to play

1. Press **PLAY GAME** on the welcome screen.
2. Players take turns. Player 1 goes first.
3. A basket scores **+10**. A miss costs **−10** (your score never drops below 0).
4. The first player to reach **100 points** wins immediately.
5. If nobody reaches 100, the player with the higher score when the 2:30 clock runs out wins. Equal scores are a draw.

### Controls

| Action | Mouse / Touch | Keyboard |
| --- | --- | --- |
| Set power | Drag **down** (pull the ball back) | `↑` / `↓` |
| Aim left / right | Drag sideways | `←` / `→` |
| Shoot | Release the drag, or tap **SHOOT** | `Space` / `Enter` |
| Back to the welcome screen | **Restart** button | – |
| Mute / unmute | **Sound on/off** button | – |

> **Note:** browsers block audio until you interact with the page, so the welcome music starts on your first tap, click or key press.

## Run it locally

No dependencies to install. Either double-click `index.html`, or serve the folder with any static server:

```bash
git clone https://github.com/YOUR-USERNAME/hoop-legends.git
cd hoop-legends
python3 -m http.server 8000
# open http://localhost:8000
```

An internet connection is needed the first time, because Three.js and the fonts are loaded from CDNs (see [Tech stack](#tech-stack)).

## Deploy to GitHub Pages

1. Push this repository to GitHub.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select branch `main` and folder `/ (root)`, then **Save**.
4. After about a minute the game is live at `https://YOUR-USERNAME.github.io/hoop-legends/`.

## Project structure

```
hoop-legends/
├── index.html        # the whole game: HTML, CSS, JavaScript and embedded music
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
└── .gitignore
```

`index.html` is about 3 MB because the welcome-screen music is embedded as a base64 string. That keeps the game a single file that works anywhere.

## Tech stack

- **Vanilla JavaScript**, HTML5 and CSS3
- **[Three.js](https://threejs.org/) r128** for 3D rendering (loaded from cdnjs)
- **Web Audio API** for sound effects and music playback
- **Google Fonts**: Orbitron and Rajdhani

Works in current versions of Chrome, Edge, Firefox and Safari (desktop and mobile). WebGL and Web Audio are required.

## Customising

All game settings live in the `<script>` section of `index.html`.

| What | Where to look |
| --- | --- |
| Match length | `const MATCH_MS = 150000;` (milliseconds) |
| Points to win | `>= 100` in `resolve()` and `finishMatch()` |
| Points per basket or miss | `+= 10` and `- 10` in `resolve()` |
| Music volume | `const MUS_VOL = 0.6;` |
| Welcome music | the `BGM_B64` string (base64 mp3) |

If you change the match length or the winning score, also update the text in the **How to play** box on the welcome screen.

To use a different welcome track, encode your mp3 and paste the output into `BGM_B64`:

```bash
base64 -w0 my-track.mp3      # macOS: base64 -i my-track.mp3
```

## Credits

- 3D engine: [Three.js](https://threejs.org/) (MIT)
- Fonts: [Orbitron](https://fonts.google.com/specimen/Orbitron) and [Rajdhani](https://fonts.google.com/specimen/Rajdhani) (SIL Open Font License 1.1)
- Welcome music: *Game Music* by tatamusic. Source and licence: **[add the link to the track page here]**

## Contributing

Bug reports, ideas and pull requests are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

## License

The source code is released under the [MIT License](LICENSE).

The MIT License covers the game's code only. The background music remains the property of its author and is used under its own licence (see [Credits](#credits)).
