# Made For You — Birthday Page

A single-page, animated birthday website: an intro screen with a wax-seal
button, a typewriter-style letter reveal, background music + a voice note,
and floating heart particles.

## Files needed in the same folder

| File | Purpose | Required? |
|---|---|---|
| `index.html` | The page itself | ✅ |
| `his-photo.jpg` | Photo shown on the page | Add your own |
| `music.mp3` | Soft background/instrumental track | Add your own |
| `voice.mp3` | You reading the letter aloud | Add your own |

## How to personalize

1. **Photo**
   Find the `PHOTO GOES HERE` marker in the HTML and replace the
   `<div class="photo-placeholder">` with:
   ```html
   <img src="his-photo.jpg" alt="Monu">
   ```
   Put the image file next to `index.html`.

2. **The letter**
   In the `<script>` section, find:
   ```js
   const letterText = `...`
   ```
   Replace the placeholder text with your own message. Leave a blank line
   between paragraphs — each blank line becomes a paragraph break in the
   typewriter animation.

3. **Background music + voice note**
   Find the two `<audio>` tags (`id="bg-music"` and `id="voice-note"`) and
   point their `src="..."` at your own files, e.g.:
   - `music.mp3` — a soft instrumental/romantic track
   - `voice.mp3` — you reading the letter out loud

   Place both audio files in the same folder as `index.html`.

4. **Signature**
   Find `[Your Name]` near the bottom of the letter section and replace it
   with your name or nickname.

## How it works

- **Intro screen**: tapping/clicking the seal (or pressing Enter/Space)
  fades out the intro and reveals the page.
- **Open letter button**: starts the background music and voice note, then
  types the letter out character by character.
- **Audio toggle**: pauses/resumes both tracks together; the voice note is
  boosted louder than the music via the Web Audio API.
- **Floating hearts**: a decorative particle animation runs continuously in
  the background (respects `prefers-reduced-motion`).

## How to use it

Just open `index.html` in a browser — no build step, server, or
dependencies required (it pulls two Google Fonts over the internet, so an
internet connection is needed for those to load). To share it, upload the
folder (HTML + photo + audio files) to any static host, or zip it and send
it directly.

## Notes

- Mobile-friendly (responsive layout, `viewport-fit=cover` for notches).
- Autoplay is intentionally gated behind a user click/tap (`Open Letter` /
  seal), since most browsers block audio autoplay without interaction.
