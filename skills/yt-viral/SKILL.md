---
name: yt-viral
description: >-
  Find what's really working in the user's niche on YouTube, rank it by how far
  each video beat its own channel, then name the formula. Use for "what's
  working right now", "find viral videos in my niche", "why did this blow up",
  competitor research, or a swipe file.
---

# yt-viral

Raw view counts just rank how big a channel is, not how good an idea is. This
ranks by **multiple over each channel's own median**, which is the only version
of the question that's actually about the video.

```bash
python3 swipe.py collected.json --min 2.0
```

## Gathering the input

You need at least **four videos per channel**, or the median means nothing, and
the tool will skip that channel and tell you. Gather them however the user
likes - `yt-dlp --flat-playlist -J` on a channel URL is quickest, the public
page works, and so does a list typed by hand.

```json
[{"channel":"...","title":"...","views":412000,"url":"...","duration":613}]
```

**Read, don't scrape.** Public listings only, never a logged-in session, never
the user's own account login.

## Reading the result

The multiple is the signal. The formula line is a judgement about the TITLE,
matched against [the 21 formulas](../yt-script/hooks.json) - it isn't a claim
about why the video did well, and you should say that when you show it.

What to give back: the top five with their multiples, the formula each one
used, and the ONE structural thing they have in common. Then the harder part:
which of those the user could actually make this week, in their own voice, with
what they've got.

## The gate

Nothing here gets published. This skill writes and you publish. Every result
ends with a block the user copies, and the last line of every run asks:
**ship it, or change it?**
