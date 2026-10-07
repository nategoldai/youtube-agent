---
name: yt-shorts
description: >-
  Find the Shorts hiding inside a long video and write them, using the
  transcript to pick moments that stand on their own. Use for "cut this into
  shorts", "clip this", "repurpose this video", or "what should I clip".
---

# yt-shorts

A Short cut from a long video isn't just a clip of the best moment. It's a
moment that **still works without the rest of the video**, and there are far
fewer of those.

## Choosing

Read the transcript and look for stretches of 20-55 seconds where all three are
true:

1. It opens on a complete thought. If the first sentence needs the minute
   before it, it's not a Short.
2. Something turns in it - a claim, then something that complicates or proves
   it.
3. It ends on a strong line, not a trail-off.

Rank the options and show the user the top five with timecodes and first lines,
so they can reject one without reading the whole transcript.

## Writing each one

- **A NEW first line.** The long video's line assumes context this viewer
  doesn't have. Write a replacement and run it through
  `../yt-script/hookscore.py`.
- **On-screen text for the first two seconds**, in different words from the
  spoken line.
- **A loop point**: what the last line sets up so that the first line answers
  it.
- A note on vertical framing - what gets cropped out of the 16:9 shot and
  whether that matters.

## The gate

Nothing here gets published. This skill writes and you publish. Every result
ends with a block the user copies, and the last line of every run asks:
**ship it, or change it?**
