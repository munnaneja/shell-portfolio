# Munn's Portfolio

A slideshow portfolio. One project on screen at a time, arrows to move between them,
a rope running down between the media squares tying them together. Every project opens
with a **context cloud** — what was going on in your life, and why you built the thing.

```
index.html          the page (HTML + CSS + JS)
projects.js         your content — years, titles, context, wins, fails, media paths
assets/profile.jpg  hero photo
assets/media/       everything you upload — photos, .mp4 clips, résumé PDF
```

## Moving around

- **Down arrow** (bottom of the screen) goes to the next slide, **up arrow** (top) goes back.
  The first slide only has a down arrow; the last only has an up.
- Up/down arrow keys do the same thing. The dots on the right jump anywhere.
  The scroll wheel does **not** change slides — it scrolls whatever is under the cursor,
  so long text columns read normally.
- Slide order: you → the projects → future works → contact.
- A project's text column scrolls on its own if you write a lot, and the year, title and
  role stay pinned at the top of it so the project name is always on screen.

## Future works

Built exactly like a project slide — context cloud, one big media box with arrows and a
caption, writing on the right. Its two ledger blocks are **What it does** and **What I'd
need** instead of wins and fails.


They sit between the projects and contact — one per entry in `SITE.futures`. **+ ADD SLIDE**
and **REMOVE THIS SLIDE** (edit mode, under the text) manage them.

## The context cloud

Every project shows its cloud first: a big yellow date in the top-left corner (the
`period` field — editable like everything else), a photo or clip in the middle, your text below,
and an **Okay** button. Okay dismisses it and reveals the project. Each project has its
own cloud with its own media and text, and once you've okayed one it stays dismissed —
come back to that project and it goes straight to the work. **Read the context again**
at the bottom of a project brings its cloud back.

## Writing your content

The page opens in edit mode. Every box marked **text here** is typeable — click it and
start writing. "What worked" and "What didn't" are each one block of text that wraps
and grows as long as you need; Enter starts a new line inside them. Your typing saves
to this browser as you go, so you can close the tab and come back to the draft.

The small pencil button in the bottom-left corner holds two things. **Preview** hides
the guide boxes and empty squares so you see the page the way a visitor will.
**Export projects.js** downloads your content — replace the `projects.js` in this
folder with it to make it permanent and pushable.

You can also just type the strings straight into `projects.js` — same thing.

## Résumé

The first slide has a **RESUME HERE** box under your name. Drag a PDF onto it (or click
to browse) and it turns into a **Résumé** button — clicking that opens the PDF in a
popup over the page, with "Open in a new tab" and Escape to close. The × on the button
(edit mode only) removes it.

Same rule as media: copy the PDF into `assets/media/` yourself, keeping the filename.
The export records it as `assets/media/<filename>.pdf`. Everything you upload —
photos, clips, résumé — lives in that one folder.

## Media

Each project shows **one big media box at a time**. If it holds more than one, arrows and
a counter appear under it — click them, or use the left/right arrow keys, to flip through.
In edit mode, **+ ADD BOX** appends another and **REMOVE THIS** deletes the one on screen.
Up/down arrows and the scroll wheel still move between projects, not between photos.

Drag a photo or an `.mp4` onto any square marked **MEDIA HERE** (or click it to browse).
Every box has a **caption here** line under it — type in it or leave it blank, and a blank
one is invisible to visitors. Captions are stored on the media item and survive swapping
the photo out.
Two squares per project, plus two in each context cloud. Fill one cloud square for a
single wide panel, both for a side-by-side pair. The cloud panels show the whole frame
rather than cropping to fill, so tall phone photos keep their subject.

The page previews the file immediately, but a browser can't save it into the repo for
you — so **copy the file into `assets/media/` yourself**. The export writes the path as
`assets/media/<filename>`, so as long as the filename matches, it loads once you push.

Sizes: photos ~1600px wide and under ~400KB. Video as H.264 MP4, under ~10MB
(GitHub rejects anything over 100MB).

## Publishing to GitHub Pages

```bash
git init
git add .
git commit -m "portfolio"
git branch -M main
git remote add origin https://github.com/YOURUSERNAME/YOURREPO.git
git push -u origin main
```

Then **Settings → Pages → Deploy from a branch → `main` / `(root)`**.
Live at `https://YOURUSERNAME.github.io/YOURREPO/` within a minute or two.

Edit mode is local to whoever opens the page — a visitor typing on it changes nothing
for anyone else, and nothing reaches the repo. It's a writing tool for you.

## Local preview

```bash
python -m http.server 4173
```

http://localhost:4173
