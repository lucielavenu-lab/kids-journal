# Kids Journal — Vision

## Origin / Problem

Two ongoing pain points, both about capturing memories of my son (age 2) before
they're lost or the backlog becomes unmanageable:

1. **Things he says and does.** Started in a paper notebook, moved to phone
   notes because the notebook wasn't always on hand. Now there's a backlog of
   phone notes that would need to be manually re-copied into the physical
   notebook — slow, and it doesn't solve the root problem (still have to
   remember to write things down in the moment).
2. **Photo album.** Physical photo album, printed photos glued in by hand.
   Selecting + printing + gluing photos from birth to age 1 took ages and the
   gluing still isn't done. Selecting photos from age 1 to age 2 hasn't even
   started. Conclusion: manual print+glue doesn't scale with current workload;
   a third-party print service is needed instead of DIY.

## Vision

A system with three inputs, feeding one output structure (a month-by-month
record of the year), across two horizons.

**Inputs:**
1. **Text/voice capture** — low-friction capture of funny things said/done,
   via a shared channel (e.g. WhatsApp) so both parents can contribute without
   extra apps or friction. The core entry point is a **voice note**: a parent
   just talks, in the moment, with nothing else required — no typing, no
   picking a date. Date/time is inferred automatically (e.g. from when the
   message was sent), not asked of the parent. Friction is the enemy here:
   if it takes more than "open chat, hold to record, speak," it won't get
   used consistently.
2. **Photo curation** — auto-select nice photos from the phone gallery
   (favorites prioritized) plus photos shared in the WhatsApp channel, with
   location read from photo metadata.
3. **Video curation** — same selection logic as photos, applied to funny video
   clips.

**Outputs:**
- A **printable book**: month-by-month, combining curated text + photos for
  the year. Produced via a third-party print provider (TBD which one) —
  DIY printing/gluing is explicitly out of scope going forward.
- A **video compilation/montage** of the funny clips, hosted online (Drive
  initially) since video can't go in the printed book.
- (Horizon 2) An **app/site** showing the same month-by-month structure,
  viewable and editable (add/edit/remove entries), that could later be
  monetized for other parents.

## Horizons

- **Horizon 1 (personal use, priority):** Get the *system* working for
  myself — capture, curation, and print/export pipelines. No app/UI required
  yet; workflows + integrations are fine.
- **Horizon 2 (monetization, later):** Turn the working system into a
  product — an app with editing, viewing, and account/multi-user support.

## Open Questions (TBD)

- Tech stack for Horizon 1 vs. Horizon 2.
- Which third-party service(s) to use for printing the book.
- Exact app requirements for Horizon 2 (deferred until Horizon 1 works).

## Project Decomposition

This is too broad for a single design; splitting into sub-projects, each with
its own brainstorm → spec → implementation plan cycle:

1. **Capture pipeline** — WhatsApp (or similar) → structured storage of
   what my son says/does. Solves the most time-pressured pain point; defines
   the data model the book will later read from. **← Starting here.**
2. **Photo curation system** — gallery + WhatsApp photos → curated monthly
   selections, with favorites priority and location metadata.
3. **Video curation system** — same selection approach, applied to video,
   output hosted on Drive.
4. **Book/album compiler + print export** — combines (1) + (2) into a
   month-by-month document formatted for a third-party print service.
5. **Horizon 2: app** — viewing/editing layer, monetization. Depends on
   1–4 existing and working first.

Each sub-project gets its own spec under `docs/specs/` once brainstormed.
