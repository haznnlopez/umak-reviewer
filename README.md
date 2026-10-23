# IT Olympics Quiz Bee Simulator

A no-build, single-page quiz bee app with 1,784 IT questions across 12 topics. Friendly flat design, custom vector icons, sounds, confetti, live multiplayer, and a practice area.

## Modes
- **Host a live game**: your screen shows the question; players join on their phones with a 4-character room code. Choose **multiple choice** (4 related choices), **fill in the blank** (typed and auto-checked, with blank boxes as a hint), or **mixed**. Faster correct answers earn more points; "close" typed answers earn half.
- **Join a game**: enter the code and a nickname.
- **Practice**: Quiz round, Survival (3 hearts), Speed sprint (60 s), Weak spots (replays what you missed), and Flashcards. Answer by typing (auto-checked) or multiple choice, use hints, and track mastery per topic.
- **Team round**: teams on one screen, host awards points.
- **Admin panel**: upload an `.xlsx` workbook (any sheet with *Question* and *Answer* headers; optional *Topic*, *Difficulty*, *Type*).

## Host it free on GitHub Pages
1. Create a public GitHub repository and upload everything in this folder to the repository root (`index.html`, `vendor/`, `.nojekyll`, `questions.json`, `README.md`, `reviewer/`).
2. Go to **Settings > Pages**, choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
3. After a minute or two the site is live at `https://<your-username>.github.io/<repo-name>/`.

## Changing the questions
- Quick: Admin panel, upload your workbook, **Use in this browser** (enough for hosting).
- For everyone: Admin panel, **Download questions.json**, replace `questions.json` in the repository.

## Notes and limits
- No game server: the host's browser runs the game and players connect peer-to-peer (WebRTC) through the free public PeerJS signaling service. The host must keep the tab open. Strict school or office firewalls can block peer-to-peer, so test on your real network.
- Practice progress, history, and uploaded banks are stored in each browser (localStorage).
- Multiple-choice wrong answers are generated from related answers in the bank (same topic and type, similar wording). Computation questions get nearby numbers.
