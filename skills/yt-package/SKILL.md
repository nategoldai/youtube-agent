---
name: yt-package
description: >-
  Write and check a YouTube video's title and thumbnail as one pair, testing
  for truncation, repetition and vagueness before it goes live. Use for "title
  ideas", "what should I call this", "thumbnail text", "my CTR is low",
  packaging, or any request to rename or repackage an existing video.
---

# yt-package

The title and the thumbnail are ONE thing. Writing them separately is why most
packaging fails: the thumbnail repeats the title, and half the space that earns
the click says the same thing twice.

```bash
python3 title.py --title "..." --thumb "AI RAN IT"
python3 title.py titles.txt            # one per line, ranked
```

## Before writing

1. Read `~/.claude/youtube/voice.md` if it's there. It's the user's voice
   profile: how they talk on camera, words they never say, who they're talking
   to, and what they won't claim. If it's missing, ask for **three of their own
   videos**, read or transcribe them, work out the voice, and write the file.
2. Never make up a number, a result or a source. If a figure would help and you
   don't have it, ask for it or write the line without it.

## What the tool checks, and why

- **60 characters** is where desktop search cuts a title off, **40** on the
  mobile home feed. Both get reported because they break differently: desktop
  loses the end, mobile can lose the subject.
- **The thumbnail must not repeat the title.** Different words, same promise.
- **Three words max on the thumbnail.** At feed size, a fourth word turns into
  a grey smudge.
- **A number, a name or a date** beats any adjective you could pick.
- **Two all-caps words is the limit** before a title starts to look like spam.

## Write ten, keep two

Write ten titles, run all of them through `title.py`, and show the user the top
three with their scores and the exact problem with each. For the winner, write
the thumbnail brief: the facial expression, the framing, the three words, and
what the background needs to do to stay readable at feed size.

## The gate

Nothing here gets published. This skill writes and you publish. Every result
ends with a block the user copies, and the last line of every run asks:
**ship it, or change it?**
