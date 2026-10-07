---
name: yt-audit
description: >-
  Review a YouTube channel from top to bottom - packaging, consistency, the
  first fifteen seconds, and what to fix first. Use for "audit my channel",
  "why isn't my channel growing", "look at my videos", or a pasted channel URL.
---

# yt-audit

An audit that hands back twenty problems is a way of dodging the one that
counts. This one ends with ONE fix.

## Before writing

1. Read `~/.claude/youtube/voice.md` if it's there. It's the user's voice
   profile: how they talk on camera, words they never say, who they're talking
   to, and what they won't claim. If it's missing, ask for **three of their own
   videos**, read or transcribe them, work out the voice, and write the file. A
   script in the wrong voice is worse than none, because they have to say it
   out loud.
2. Never make up a number, a result or a source. If a figure would help and you
   don't have it, ask for it or write the line without it.

## What to check, in this order

1. **The last ten titles, together.** Read them as a list, the way the channel
   page shows them. Do they promise different things? Run them through
   `../yt-package/title.py`. If every title has the same shape, that's a format
   problem, not a title problem.
2. **The thumbnails, at feed size.** Shrink them down. What still reads? If
   three of them are illegible at that size, that's the fix and nothing else
   matters yet.
3. **The first fifteen seconds of the three newest videos.** Transcribe them
   and score them with `../yt-script/hookscore.py`. This is where most channels
   lose people.
4. **Upload rhythm.** Not how often, but how STEADY. Six videos in one week and
   then a month of silence is worse than one every two weeks forever.
5. **The retention shape**, if they can export it. Use `/yt-retention`.

## What to give back

- The single biggest fix, by name, with what to do about it this week.
- Three things that already work, so they don't break them. Be specific; "your
  energy is great" isn't an observation.
- What NOT to do yet, and why.

Never start an audit with praise you don't mean, and never finish one with a
list of twenty things.

## The gate

Nothing here gets published. This skill writes and you publish. Every result
ends with a block the user copies, and the last line of every run asks:
**ship it, or change it?**
