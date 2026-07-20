# Public ID-mapping data

Watchario cross-references titles across seven ID namespaces — **AniList,
Kitsu, MyAnimeList, IMDb, TMDB, TheTVDB, and AniDB** — so a show you track on
one service resolves to the right entry everywhere else (and to the right
streams). We maintain that mapping data and publish it here as downloadable
release assets so anyone can use it.

## Downloads

All files are served as assets on the **[`mapping-data`][rel]** release and are
refreshed automatically (raw snapshots daily, the enrichment overlay weekly):

| File | What it is |
|---|---|
| [`anime-list-full.json`][d1] | Raw upstream ID map from [Fribb/anime-lists][fribb]. |
| [`anime-offline-database-minified.json`][d2] | Raw upstream map from the [manami-project anime-offline-database][manami]. |
| [`anime-mappings-overlay.json`][d3] | **Watchario's own enrichment overlay** — precomputed IMDb ids we derive via TMDB external-id lookups and AniList franchise-graph borrowing, filling gaps the upstream sets leave blank. Merged on top of the raw data, fill-if-missing only. |

```bash
# grab the enriched overlay
curl -L -o overlay.json \
  https://github.com/ttsiligkoudis/watchario-app/releases/download/mapping-data/anime-mappings-overlay.json
```

## Format

`anime-mappings-overlay.json` is an object with an `entries` array; each entry
carries an IMDb id keyed to the anime's other ids, e.g.:

```json
{ "entries": [ { "anilist_id": 21, "imdb_id": "tt0409591" } ], "misses": [] }
```

The raw upstream files keep their original upstream schemas — see the linked
projects for their formats.

## Provenance & licensing

The raw files are mirrors of the upstream open datasets and remain under their
original licenses — see [Fribb/anime-lists][fribb] and the
[anime-offline-database][manami]. Watchario's enrichment overlay is provided
**as-is**, with no warranty and no guarantee of accuracy or availability. See
[`LICENSE`](../LICENSE).

[rel]: https://github.com/ttsiligkoudis/watchario-app/releases/tag/mapping-data
[d1]: https://github.com/ttsiligkoudis/watchario-app/releases/download/mapping-data/anime-list-full.json
[d2]: https://github.com/ttsiligkoudis/watchario-app/releases/download/mapping-data/anime-offline-database-minified.json
[d3]: https://github.com/ttsiligkoudis/watchario-app/releases/download/mapping-data/anime-mappings-overlay.json
[fribb]: https://github.com/Fribb/anime-lists
[manami]: https://github.com/manami-project/anime-offline-database
