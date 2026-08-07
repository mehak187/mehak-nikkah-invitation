# nikkah-invitation

An animated nikkah invitation website — **Mehak & Shakaib**.

## Entry sequence

1. **Gate** — an ornate rose-covered gate; cut the ribbon and both leaves swing open
2. **Envelope** — a wax-sealed envelope; the seal breaks and the card slides out of the pocket
3. **Invitation** — the full page reveals

## Sections

- Hero — full-bleed `hero.png` (Bismillah, verse and names are baked into the image)
- Save the Date — live countdown with a flip on each change
- Our Nikah — three cards (date / time / venue), November 2026 calendar with a beating heart
  on the 22nd and a dashed RSVP ring on the 10th, plus View Location and Add to Calendar
- Our Story — text with three polaroids (polaroids appear only when photos exist)
- Glimpses of Us — five-photo strip, hidden until photos exist
- RSVP — WhatsApp button
- Footer — olive, monogram, quick links, contact, socials

## Details

**Sunday, 22 November 2026 · 7:00 PM**
Deewan-e-Khas Marriage Hall, Sialkot

## Photos

The entrance and stage scenes are hand-drawn inline SVG — no image files are shipped.
`gate.jpg` (supplied by the couple) is the only picture in the repo.

## Music

`music.mp3` is the couple's own track. Replace the file with any song you like — the floating
button appears only when the file loads, and disappears if it is missing.

Browsers block audio autoplay, so playback starts on the tap that opens the invitation —
that tap counts as the user gesture. The button then toggles it. The volume fades in to 50%.

## Sound effects

`sfx/boom1.mp3`–`boom3.mp3` are firework explosions from Freesound, CC0 (public domain).
One plays with each burst when the invitation opens. Three copies of each are pooled so
overlapping bursts do not cut each other off.

The floating button is the single mute control — it silences both the song and the fireworks,
and it still appears if `music.mp3` is missing.

## Adding photos and video

Every slot degrades gracefully: video beats image, image beats the drawn SVG scene, and a section
with nothing at all simply stays hidden. Nothing ever renders broken.

- **Gallery + Our Story polaroids** — any of `photos/p1.jpg` … `photos/p6.jpg`. Only the ones that exist get a frame,
  and "Moments" appears once at least one loads. Portrait crops look best (the frames are 3:4).
- **Video** — `video.mp4` in the project root. The "Our Invitation" section appears when it loads.
- **Gate** — `gate.jpg` is split into pillars + two leaves at 25.5% / 50% / 74.5% of the image
  width, so a replacement needs the same layout.

## Editing

Everything lives in a single file: `index.html` — no build step, no dependencies.

- Palette and fonts: the `:root` tokens near the top (ivory #FBF8F3, cream #F5EFE6,
  olive #6E6841, gold #B8924A, text #4B4638, border #E7DFD2)
- Names, venue and RSVP numbers: edit the HTML directly
- Countdown target: the `NIKKAH.date` line in the script
  (month is 0-based, so `10` = November)
- "Add to Calendar" builds an `.ics` from the `ICS` array in the script —
  its `DTSTART`/`DTEND` are in UTC (PKT is UTC+5), so update them too if the date changes

Just open `index.html` in a browser.
