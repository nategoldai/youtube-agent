---
name: yt-script
description: >-
  Write a YouTube video script from a rough idea - hook options from 21
  formulas, scored, then the full spoken script with the retention beats
  marked. Use whenever the user wants a video script, a hook, an opening line,
  "what should I say", "write my next video", or is about to record without the
  first fifteen seconds figured out.
---

# yt-script

Turns one idea into a script people watch to the end.

There are tools in this folder and they really run. Use them. Don't judge the
hook by eye.

```bash
python3 hookscore.py hooks.txt              # rank your hook options
python3 hookscore.py --hook "one line"      # score just one
```

## Before writing

1. Read `~/.claude/youtube/voice.md` if it's there. It's the user's voice
   profile: how they talk on camera, words they never say, who they're talking
   to, and what they won't claim. If it's missing, ask for **three of their own
   videos**, read or transcribe them, work out the voice, and write the file. A
   script in the wrong voice is worse than none, because they have to say it
   out loud.
2. Never make up a number, a result or a source. If a figure would help and you
   don't have it, ask for it or write the line without it.

## The shape

**The first 15 seconds are the whole job.** They have to do three things or
the video leaks: confirm what the title promised, open a question the viewer
can't let go of, and show that the payoff is coming.

1. **Hook.** Write FIVE using [the 21 formulas](hooks.json), run them through
   `hookscore.py`, keep the best two, and show the user both with their scores.
   Never hand over just one.
2. **The turn** (0:15-0:45). Say what the video will do, in one sentence, and
   start doing it. No channel intro, no "before we start", no subscribe pitch.
   Those are the most common cause of the drop at 0:30.
3. **The body.** One idea per beat. Mark each beat with what's ON SCREEN, not
   just what's said - a talking head with nothing to look at is a podcast.
4. **The payoff.** Deliver what the hook promised, clearly, and say that you're
   delivering it: "that's the prompt, it's in the description".
5. **The close.** One ask. Not three.

## What to give back

- the two best hooks with their score panels
- the script, beat by beat, with `[ON SCREEN: ...]` on every beat
- an estimated runtime at 150 words per minute
- one line saying which formula the winning hook used and why it suits this
  idea

## The gate

Nothing here gets published. This skill writes and you publish. Every result
ends with a block the user copies, and the last line of every run asks:
**ship it, or change it?**
