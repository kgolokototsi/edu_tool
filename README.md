# Oa's Edu Tool

A fun, offline learning game for Oa (Grade 1). One file, no install, no internet.

**To play:** double-click `index.html` (or save it to a tablet and open it in the browser).
Tap anywhere once to start the music.

## What is in it

- **Maths** (adaptive; 8 out of 10 right opens the next topic): counting and grouping, more or less (bigger/smaller, 1 more, 1 less, 10 more, the number between), skip counting (2s, 5s, 10s) and doubling, adding to 10, shapes (sides, corners, spotting shapes), adding to 20, telling the time (o'clock, half past, one hour later), tens and ones, two-digit adding with no carrying, taking away, story sums with the Supa Strikas (tap the sentence to hear it), halves and sharing (including sharing into baskets, and quarters), money (count rand coins, work out change), times tables (2, 5, 10, then 3 and 4). Questions get harder as he gets them right.
- **Reading:** seven Supa Strikas stories starring Shakes, El Matador, Twisting Tiger and Big Bo (player and team names, shirt numbers, a world tour of the Super League teams, and one where Oa trains with them) plus eight early-reader story books. New words are highlighted in yellow, tapping any word says it, and finished books add words to "My Words". Some stories star Oa.
- **Three ways to answer:** type it, choose it, or drag it (including dragging things into baskets to make groups).
- **Points and high score:** first-try answers score 10 (plus streak bonus), second try 5. A round's score is multiplied by accuracy (×1 at 90%+, ×0.8 at 70%+, otherwise ×0.6), so wrong answers lower the high score. Every 50 points earns an arcade token.
- **Games** (each play uses 1 token, earned with points):
  - **Catch & Dodge:** catch insulin pens (+1 heart), coins and low-carb snacks; dodge high-carb sweets and food. It is a game, not medical advice.
  - **Penalty Kicks:** five shots against a keeper. Tap in the goal to aim; the top corners are unsaveable but easy to miss.
  - **Tic Tac Toe:** Easy, Tricky or Genius computer, or 2 players on one tablet. Wins, draws and losses earn points.
  - **Supa Pairs:** memory match with the Supa Strikas and Oa (names on the cards). Easy 6 pairs, Tricky 8, Genius 10, or 2 players.
  - **Keepy Uppy:** tap the ball to keep it off the grass. Three balls; the best run in a row is the score.
  - **Red Card!:** players pop out of holes for 40 seconds. Tap the rivals in black for a red card, not the Supa Strikas in red.
  - **Copy the Coach:** Coach Ledige lights up four buttons with notes; copy the pattern as it grows. One second chance.
- **Oa the character:** drawn in the same style as the Supa Strikas players (athletic proportions, thin outline), from Oa's photo: curly high-top, big gap-toothed grin, the 2026-27 Real Madrid home kit (white, dark green collar and cuffs, pink shoulder stripes, crest, "Emirates FLY BETTER"), number 10 on the shorts and the back.
- **Themes:** purple, teal, blue or green (the 🎨 button).
- **Sound:** the music and sound effects are generated in code (WebAudio), there are no audio files. 🔊 mutes.

## Grown-ups (⚙️ button, asks a quick sum)

Unlock all topics and books, give a bonus token, or reset progress. Progress is saved in the browser (`localStorage`), so use the same browser and device each time.

## Adding content

Everything lives in `index.html`:

- Supa Strikas players and kit colours: `PLAYERS` and `KIT` (art tokens look like `SS:shakes`, `SS:joe:cheer`). These are my own drawings in the show's style (red kit with the big star, Big Bo in yellow), made for private family use, not official art. Oa and the players share one drawing function, `toon()`.
- Stories: the `BOOKS` array (pages of text plus emoji pictures, `OA` for Oa, a `quiz` of three fill-in-the-gap questions).
- Maths: one generator per topic in `GEN`; topics are listed in `TOPICS` in unlock order. A generator can return its own `opts`, and a `say` sentence (with `aloud` for how it is read out). Topics Oa has opened stay open (`S.opened`), so a new topic can go anywhere in the list. Currency for the Money topic: `CONFIG.money`.
- Oa's look: `CONFIG.character` colours and the `oa()` drawing. Token cost per game: `COST`.
- Games added after Tic Tac Toe share one handle, `G`, which `go()` stops when the screen changes. They size everything in px from JavaScript (no CSS `min()`/`clamp()`), because Oa's tablet browser is older.
- Settings such as points per token and arcade length: `CONFIG`.

## Offline and installing

When the page is opened from the web link, it saves itself on the device (a service worker, `sw.js`) so it opens with no internet afterwards. Open it once online first. Use the browser menu's "Add to home screen" to get an app icon. Updates arrive automatically the next time the device is online. If you edit the files, bump `CACHE` in `sw.js`.
