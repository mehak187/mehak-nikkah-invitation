# nikkah-invitation

An animated nikkah invitation website — **Mehak & Shakaib**.

## Entry sequence

1. **Gate** — an ornate rose-covered gate; cut the ribbon and both leaves swing open
2. **Envelope** — a wax-sealed envelope; the seal breaks and the card slides out of the pocket
3. **Invitation** — the full page reveals

## Sections

- Hero — Bismillah, Surah Ar-Rum 30:21, names in rose script over rotating mandalas
- Entrance — full-bleed venue photo (or a drawn night-palace scene)
- Nikkah — date, time and venue on an arched card, with a November calendar and a heart on the 22nd
- Nikkah stage — full-bleed stage photo (or a drawn palace-and-sehra scene)
- Countdown — live days / hours / minutes / seconds
- Dua — Barakallahu lakuma
- Moments — photo gallery
- RSVP — hosts and a WhatsApp confirm button

## Details

**Sunday, 22 November 2026 · 7:00 PM**
Deewan-e-Khas Marriage Hall, Sialkot

## Photos

The entrance and stage scenes are hand-drawn inline SVG — no image files are shipped.
`gate.jpg` (supplied by the couple) is the only picture in the repo.

## Adding photos and video

Every slot degrades gracefully: video beats image, image beats the drawn SVG scene, and a section
with nothing at all simply stays hidden. Nothing ever renders broken.

- **Entrance** — `hall.mp4` (autoplays, muted, looped) or `hall.jpg`. Landscape crops work best.
- **Nikkah stage** — `stage.mp4` or `stage.jpg`, same rules.
  Delete both and the hand-drawn SVG scene takes over.
- **Gallery** — any of `photos/p1.jpg` … `photos/p6.jpg`. Only the ones that exist get a frame,
  and "Moments" appears once at least one loads. Portrait crops look best (the frames are 3:4).
- **Video** — `video.mp4` in the project root. The "Our Invitation" section appears when it loads.
- **Gate** — `gate.jpg` is split into pillars + two leaves at 25.5% / 50% / 74.5% of the image
  width, so a replacement needs the same layout.

## Editing

Everything lives in a single file: `index.html` — no build step, no dependencies.

- Names, venue and RSVP numbers: edit the HTML directly
- Countdown target: the `NIKKAH.date` line in the script
  (month is 0-based, so `10` = November)
- "Add to Calendar" builds an `.ics` from the `ICS` array in the script —
  its `DTSTART`/`DTEND` are in UTC (PKT is UTC+5), so update them too if the date changes

Just open `index.html` in a browser.
