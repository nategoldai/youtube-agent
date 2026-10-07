---
name: yt-edit
description: >-
  Turn the transcript of a raw recording into an edit decision list - dead air,
  filler lines and retakes, with timecodes. Use for "edit this", "cut the dead
  space", "tighten this video", "I rambled", or any request to shorten footage
  from a transcript.
---

# yt-edit

Builds an edit decision list from a timestamped transcript. It prints the cuts.
You make them.

```bash
python3 deadair.py transcript.srt              # srt, vtt or whisper json
python3 deadair.py transcript.srt --floor 0.35 --json
```

No transcript yet? Ask for one, or make one first - `whisper`,
`faster-whisper`, or the captions YouTube generates on an unlisted upload all
work. Never guess at timings.

## What it catches

- **DEAD** - pauses longer than the floor, trimmed from the MIDDLE so each side
  keeps a breath. Cutting right up against speech is what makes a tightened
  take sound breathless.
- **FILLER** - lines that are nothing but "um", "so yeah", "basically".
- **REPEAT** - a sentence started over. It's compared with the last line that
  was actual speech, not just the line before, because most retakes have an
  "um" between the two tries.

## What it won't do

It doesn't touch the video files. It has no opinion on your B-roll. A 40% cut in
the report means 40% of the SPEECH, so if the video has a long silent demo, that
number is off. Check the report against the footage before trusting the runtime
at the bottom.

## The gate

Nothing here gets published. This skill writes and you publish. Every result
ends with a block the user copies, and the last line of every run asks:
**ship it, or change it?**
