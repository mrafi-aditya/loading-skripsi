# Loading Skripsi — Anti Bug Edition

A small browser game built with JavaScript Canvas and Flask. Keep a thesis progress bar moving by clicking bugs before they reach it and collecting coffee for bonus progress. The game ends if the stress meter reaches its limit.

**Stack:** Python · Flask · JavaScript · HTML Canvas · CSS · JSON

## Run locally

```sh
git clone https://github.com/mrafi-aditya/pert_7_la.git
cd pert_7_la
python -m venv .venv
```

Activate with `.venv\Scripts\Activate.ps1` on Windows PowerShell or `source .venv/bin/activate` on macOS/Linux, then:

```sh
python -m pip install -r requirements.txt
python app.py
```

Open `http://127.0.0.1:5000`, enter a player name, and choose **Mulai Game**. Use your own environment; the repository contains previously committed environment directories that are not needed to install or run the application.

## Components

| Path | Responsibility |
|---|---|
| [app.py](app.py) | Flask page and score endpoints |
| [templates/index.html](templates/index.html) | Game page and leaderboard |
| [static/game.js](static/game.js) | Game loop and browser interaction |
| [static/style.css](static/style.css) | Presentation |
| `scores.json` | Local top-ten leaderboard |

`GET /api/scores` returns the leaderboard. `POST /api/scores` accepts `name`, `score`, `bugs`, and `seconds`, then stores the top ten entries. These are browser-submitted scores; no anti-cheat claim is made.

## Scope

This is a coursework prototype. The supplied entry point enables Flask debug mode for local development. Scores are stored in a single JSON file without multi-process coordination. Cleaning tracked virtual environments and adding deployment configuration are separate maintenance tasks; the game source and history are retained.
