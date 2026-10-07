---
name: yt-retention
description: >-
  Read a YouTube Studio audience-retention export, find where viewers really
  drop off, and say what to change. Use for "why do people stop watching", "my
  retention is bad", a pasted retention chart or CSV, or "fix my pacing".
---

# yt-retention

The retention graph is the only honest feedback YouTube gives you, and almost
nobody downloads it.

```bash
python3 retention.py retention.csv --duration 600
python3 retention.py retention.csv --transcript transcript.srt
```

Getting the file: Studio -> pick a video -> Analytics -> Engagement -> the
audience-retention chart -> the download icon -> "Audience retention".

## Three separate problems

- **HOOK LEAK** - how many people leave in the first 30 seconds. Under 25% is
  healthy. Always fix this first, and it's always the first fifteen seconds of
  the script, never the edit.
- **CLIFFS** - single sharp drops. A cliff is a moment: a topic switch with no
  warning, a sponsor read, a long setup. With `--transcript`, the tool prints
  what was being said right there, which turns the report from interesting
  into useful.
- **SLIDE** - the steady drain through the middle. A flat slide is pacing. The
  fix is cutting, not rewriting.

## What to give back

Name the single biggest leak and one change to fix it. Not a list of five. Give
the rest only if asked. And if the hook leak is healthy and the slide is flat,
say the video is fine and the problem is packaging, and point them to
`/yt-package`.

## The gate

Nothing here gets published. This skill writes and you publish. Every result
ends with a block the user copies, and the last line of every run asks:
**ship it, or change it?**
