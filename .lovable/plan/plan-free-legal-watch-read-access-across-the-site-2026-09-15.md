# Plan: Free & legal watch/read access across the site

## Goal
Let visitors watch or read as much Re:Zero content as possible directly from (or one click away from) the site — using only free, legal sources. No unofficial streaming or scanlation links.

## What gets added

### 1. Web novel reader links (fully free)
- The web novel is published free on Shōsetsuka ni Narō (original Japanese); add per-arc "Read the web novel free" links on the Novels page.
- Add a note pointing to community English translations of the web novel (the source being free makes these the standard legal-adjacent route).

### 2. Official video embeds on the Anime page
- Embed official YouTube videos (openings, trailers, clips from Kadokawa's official channel) directly on each series/film panel, playable on-site.
- Each of the five entries (S1, S2, S3, Memory Snow, Frozen Bond) gets an embedded player.

### 3. "Watch free" / "Read" panels
- Every anime entry gets a watch panel listing free options first (Crunchyroll free with ads where available, Muse Asia's free YouTube channel for eligible regions), then paid options.
- Manga entries get links to official preview chapters and where volumes can be bought/borrowed.

## Technical details
- Extend `src/lib/rezero-data.ts` with `links` (label, url, free: boolean) and `youtubeId` fields per entry.
- New `WatchPanel` component (lazy-loaded YouTube iframe embed) and link lists rendered in `anime.tsx`, `novels.tsx`, `manga.tsx`.
- No backend, no new dependencies.

## Not included
- No links to pirate streaming or scanlation sites — those can't be added regardless of cost or distribution.
