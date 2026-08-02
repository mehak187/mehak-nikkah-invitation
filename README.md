# nikkah-invitation

An animated nikkah invitation website — **Mehak & Shakaib**.

## Entry sequence

1. **Window** — an arched jharokha with jali shutters swings open, golden light pours out
2. **Envelope** — a wax-sealed envelope; the seal breaks and the card slides out of the pocket
3. **Invitation** — the full page reveals

## Sections

- Hero — Bismillah, Surah Ar-Rum 30:21, names in gold script over rotating mandalas
- Nikkah — date, time and venue on an arched card
- Countdown — live days / hours / minutes / seconds
- Dua — Barakallahu lakuma
- RSVP — hosts and a WhatsApp confirm button

## Details

**Sunday, 22 November 2026 · 7:00 PM**

## Editing

Everything lives in a single file: `index.html` — no build step, no dependencies.

- Names, venue and RSVP numbers: edit the HTML directly
- Countdown target: the `NIKKAH.date` line in the script
  (month is 0-based, so `10` = November)

Just open `index.html` in a browser.
