# Media assets

Drop marketing media here and reference it from the root `README.md` with a
relative path (e.g. `assets/gifs/sync.gif`).

## Layout

- `screenshots/` — static PNG/JPG screenshots (dashboard, player, library, …).
- `gifs/` — short screen-recordings exported as GIF for inline README playback.

## Tips

- **GIFs** render inline on GitHub and autoplay — best for < 10 s loops
  (a sync fan-out, a stream picker, the TV D-pad UI). Keep them under ~10 MB so
  the README stays fast to load.
- **Video** (`.mp4`/`.webm`) does *not* embed inline in a GitHub README, but a
  file committed here (or attached to a release / an Issue comment) gets a URL
  GitHub renders as an inline player when pasted into Markdown. For anything
  longer than a few seconds, prefer a hosted video (YouTube) linked with a
  clickable thumbnail image.
- Name files after what they show (`library-filter.gif`, not `rec1.gif`) so the
  README stays readable.
