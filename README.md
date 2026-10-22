# IT Olympics Quiz Bee Simulator

A no-build quiz bee app: 1,784 IT questions across 12 topics, get-ready 3-2-1 countdown, stopwatch ring, sounds, confetti, trackboard, and **live multiplayer** (Kahoot-style).

## Modes
- **Host a live game**: the host's screen shows the question; players join on their phones with a 4-character room code and tap colored answers (speed earns more points).
- **Join a game**: enter the code and a nickname.
- **Practice mode**: solo, or local teams on one screen with a host awarding points.
- **Automatic checker**: in solo practice, type your answer and it is graded automatically (typos, abbreviations, partial name lists and numbers with units are handled; borderline answers let you decide).
- **Admin panel**: upload an `.xlsx` workbook (any sheet with *Question* and *Answer* column headers; optional *Topic*, *Difficulty*, *Type*) to replace the question bank.

## Host it free on GitHub Pages
1. Create a public GitHub repository and upload everything in this folder to the repository root (`index.html`, `vendor/`, `.nojekyll`, `questions.json`, `README.md`, `reviewer/`).
2. Go to **Settings > Pages**, choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
3. After a minute or two the site is live at `https://<your-username>.github.io/<repo-name>/`.

## Changing the questions
- Quick: open the site, **Admin panel**, upload your workbook, **Use in this browser** (enough for hosting online games).
- For everyone: in the Admin panel click **Download questions.json**, then replace `questions.json` in your repository.

## How multiplayer works (and its limits)
There is no game server. The host's browser is the game server, and players connect to it peer-to-peer (WebRTC) using the free public PeerJS signaling service. The host must keep the tab open. Most home, school and mobile networks work. Strict firewalls (some schools or offices) can block peer-to-peer connections, because no TURN relay is configured. Test it on your actual network before the event.
In online mode, answers are 4-choice questions generated automatically from the bank (wrong choices come from other answers in the same topic and type).
