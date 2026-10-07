---
name: yt-seo
description: >-
  Write the description, chapters, tags and search-facing text for a YouTube
  video, aimed at what a real person would type. Use for "write my
  description", "add chapters", "timestamps", "tags", "SEO", "help this video
  get found", or "nobody can find this".
---

# yt-seo

Search matters less than packaging, but more than people think for evergreen
videos. If the video is aimed at the subscriber feed, say so and put the effort
into `/yt-package` instead.

```bash
python3 chapters.py transcript.srt --target 8
```

## Before writing

1. Read `~/.claude/youtube/voice.md` if it's there. It's the user's voice
   profile: how they talk on camera, words they never say, who they're talking
   to, and what they won't claim. If it's missing, ask for **three of their own
   videos**, read or transcribe them, work out the voice, and write the file.
2. Never make up a number, a result or a source. If a figure would help and you
   don't have it, ask for it or write the line without it.

## The description

- **Only the first two lines get read.** They show above "...more" and they're
  the search snippet. Say what the video gives people, in the words they'd have
  searched.
- Next, the link or resource if there is one, so it sits above the fold.
- Then the chapters (see below).
- Then the longer version: what's covered, who it's for, and what it assumes
  they already know.

## Chapters

`chapters.py` finds the breaks in a timestamped transcript. A chapter list that
breaks any of YouTube's rules quietly fails, and the block just sits in the
description doing nothing:

- The first one must be **00:00**.
- There must be **at least three**.
- Each one must be **at least 10 seconds** long.

The tool checks all three and tells you when a list won't work instead of
letting you paste it.

It's good at finding the BREAKS - it scores the pauses you actually took by how
much the vocabulary changes across them. The titles it gives are just the topic
words, so treat them as a draft. A chapter called "Thumbnails Titles Packaging"
is a placeholder. Rewrite each one as the promise of that section, in the user's
voice, in three to five words.

Chapters double as a retention check: if a section can't be named in five
words, it's either two sections or it's filler.

## Tags, honestly

Tags are a weak signal, and YouTube has said so. Use them to clear up ambiguity:
alternate spellings, tool names, the abbreviations people really type. Then
stop. Fifteen is plenty. A wall of tags isn't a strategy, and stuffing in
unrelated ones breaks the rules.

## The search test

Before handing anything over, write down the three searches this video should
win, and check that the title and the first two lines of the description contain
the words from those searches. If they don't, the title is the problem, not the
description.

## The gate

Nothing here gets published. This skill writes and you publish. Every result
ends with a block the user copies, and the last line of every run asks:
**ship it, or change it?**
