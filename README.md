# Oa's Edu Tool

A fun, offline learning game for Oa (Grade 1). One file, no install, no internet.

**To play:** double-click `index.html` (or save it to a tablet and open it in the browser).
Tap anywhere once to start the music.

## What is in it

- **Maths** (adaptive; 8 out of 10 right opens the next topic): counting and grouping, skip counting (2s, 5s, 10s) and doubling, adding to 10, adding to 20, two-digit adding with no carrying, taking away, times tables (2, 5, 10, then 3 and 4). Questions get harder as he gets them right.
- **Reading:** seven Supa Strikas stories (player and team names, shirt numbers, a world tour of the Super League teams, and one where Oa trains with them) plus eight early-reader story books. New words are highlighted in yellow, tapping any word says it, and finished books add words to "My Words". Some stories star Oa.
- **Three ways to answer:** type it, choose it, or drag it (including dragging things into baskets to make groups).
- **Points and high score:** first-try answers score 10 (plus streak bonus), second try 5. A round's score is multiplied by accuracy (×1 at 90%+, ×0.8 at 70%+, otherwise ×0.6), so wrong answers lower the high score. Every 50 points earns an arcade token.
- **Games** (each play uses 1 token, earned with points):
  - **Catch & Dodge:** catch insulin pens (+1 heart), coins and low-carb snacks; dodge high-carb sweets and food. It is a game, not medical advice.
  - **Penalty Kicks:** five shots against a keeper. Tap in the goal to aim; the top corners are unsaveable but easy to miss.
  - **Tic Tac Toe** and **Connect 4:** Easy, Tricky or Genius computer, or 2 players on one tablet. Wins, draws and losses earn points.
- **Oa the character:** drawn from Oa's photo in a cartoon style: curly hair, big grin, white shirt with "Fly Emirates", number 10 on the shorts (and on the back).
- **Themes:** purple, teal, blue or green (the 🎨 button).
- **Sound:** the music and sound effects are generated in code (WebAudio), there are no audio files. 🔊 mutes.

## Grown-ups (⚙️ button, asks a quick sum)

Unlock all topics and books, give a bonus token, or reset progress. Progress is saved in the browser (`localStorage`), so use the same browser and device each time.

## Adding content

Everything lives in `index.html`:

- Supa Strikas players and kit colours: `PLAYERS` and `KIT` (art tokens look like `SS:shakes`, `SS:joe:cheer`). These are my own drawings in the show's style (red kit with the big star, Big Bo in yellow), made for private family use, not official art.
- Stories: the `BOOKS` array (pages of text plus emoji pictures, `OA` for Oa, a `quiz` of three fill-in-the-gap questions).
- Maths: one generator per topic in `GEN`; topics are listed in `TOPICS`.
- Oa's look: `CONFIG.character` colours and the `oa()` drawing. Token cost per game: `COST`.
- Settings such as points per token and arcade length: `CONFIG`.
