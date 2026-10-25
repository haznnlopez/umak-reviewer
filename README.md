# Quiz Hive

A no-build, single-page quiz game for any subject. Friendly flat design, custom vector icons and avatars, sounds, confetti, live multiplayer, practice modes, and decks you can upload yourself.

## Decks
- The built-in **IT Olympics** deck (1,784 questions, 12 topics) is included on every device.
- **Decks** (home screen) lets each user upload their own files: `.xlsx`, `.xls`, `.csv`, `.json`, `.txt`, `.md`. They are converted into a deck, saved in that browser, and can be downloaded back as an `.xlsx` workbook. Choose a deck and every mode uses it.
- Excel/CSV: columns **Question** and **Answer** (optional **Topic**, **Difficulty**, **Type**). Text files: `question | answer`, `Q:`/`A:` pairs, or `Term: definition` lines; `# Heading` sets the topic.

## Modes
- **Host a live game**: your screen shows the question; players join on their phones with a 4-character code, pick an avatar, and see the question on their own screens. Multiple choice (4 related choices), fill in the blank (typed, auto-checked), or mixed. A leaderboard with rising and dropping animation appears between questions.
- **Join a game**: enter the code, a nickname, and choose an avatar.
- **Practice**: Quiz round, Survival, Speed sprint, Weak spots, Flashcards, with hints and progress tracking.
- **Team round**: teams on one screen, host awards points.

## Host it free on GitHub Pages
1. Create a public GitHub repository and upload everything in this folder to the repository root (`index.html`, `vendor/`, `.nojekyll`, `README.md`, `reviewer/`).
2. Go to **Settings > Pages**, choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
3. After a minute or two the site is live at `https://<your-username>.github.io/<repo-name>/`.

## Notes and limits
- No game server: the host's browser runs the game and players connect peer-to-peer (WebRTC) through the free public PeerJS signaling service. The host must keep the tab open. Strict school or office firewalls can block peer-to-peer, so test on your real network.
- Uploaded decks, practice progress and history are stored in each user's own browser (localStorage). Clearing browser data removes them, so download decks you want to keep.
- Text files cannot be turned into questions automatically unless they follow the formats above; the app does not write questions from free-form prose.
