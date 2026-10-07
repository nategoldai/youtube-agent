# The YouTube agent skill, by NateGold

Ten Claude skills that help you run a YouTube channel. Free, MIT licensed, no
signup, no API key, nothing to connect.

One writes your script from 21 hook formulas and scores the hook before you
film a single take. One checks the title and thumbnail as a single pair,
because writing them separately is why half your click space ends up saying the
same thing twice. One reads your audience-retention export and tells you the
exact second people left and what you were saying when they did. One turns a
transcript into an edit decision list. One finds the Shorts already hiding in a
long video. One finds what's working in your niche and ranks it by how far each
video beat its own channel, not by how big the channel is.

**Nothing goes live until you put it there.** These skills write. You upload.

## Install

Paste this into Claude:

```
https://github.com/nategoldai/youtube-agent

Install this skill, then confirm /yt-script works.
```

Or do it yourself, in Claude Code:

```bash
git clone https://github.com/nategoldai/youtube-agent.git
cp -r youtube-agent/skills/yt-* ~/.claude/skills/
```

Or as a plugin:

```
/plugin marketplace add nategoldai/youtube-agent
/plugin install youtube-agent
```

Want it for one project only? Copy the same folders into that repo's
`.claude/skills/`. Not using Claude Code? Paste any single `SKILL.md` at the
start of a chat and it works as a mode. You lose the six Python tools, which
are most of the value of `/yt-script`, `/yt-retention` and `/yt-edit`, but
everything else works.

Next, spend ten minutes on [`templates/voice.md`](templates/voice.md). Copy it
to `~/.claude/youtube/voice.md` and fill it in, or send Claude three of your own
videos and say "write my voice.md from these". Every skill reads that file, and
it matters more here than anywhere, because you have to say the words out loud.

## The 10 skills

| command | what it does |
| --- | --- |
| `/yt-script` | Turns one idea into a script. Five hooks from [21 formulas](skills/yt-script/hooks.json), scored, then the spoken script with the retention beats marked. |
| `/yt-package` | Title and thumbnail as one pair, checked for truncation, repetition and vagueness. |
| `/yt-edit` | Turns a transcript into an edit decision list: dead air, filler lines, retakes, with timecodes. |
| `/yt-comment` | Sorts the comment section into four piles, then replies in your voice. Tells you which one to pin. |
| `/yt-plan` | A week that fits the hours you really have. One anchor, one quick one, three Shorts. |
| `/yt-viral` | What's working in your niche, ranked against each channel's own median. |
| `/yt-retention` | Reads your retention export properly: hook leak, cliffs, slide, and what to change. |
| `/yt-shorts` | The Shorts already inside a long video, with a new first line for each. |
| `/yt-seo` | The description, valid chapters, the tags worth having, and the three searches this should win. |
| `/yt-audit` | Your whole channel, ending in ONE fix instead of twenty. |

## The six tools

Each one runs on plain Python 3 with nothing extra to install. They're what
make these skills more than just prompts.

```bash
python3 skills/yt-script/hookscore.py --hook "one line"        # 5-part hook score
python3 skills/yt-package/title.py --title "..." --thumb "..." # title + thumbnail checker
python3 skills/yt-edit/deadair.py transcript.srt               # edit decision list
python3 skills/yt-seo/chapters.py transcript.srt               # valid chapters
python3 skills/yt-retention/retention.py retention.csv         # where they left, and why
python3 skills/yt-viral/swipe.py collected.json --min 2.0      # outliers vs. each channel's median
```

## The fine print

The part most packs skip.

**It doesn't publish.** YouTube's Data API would allow it with your own OAuth,
which isn't true of Instagram, where posting isn't available at all. It's still
not built in here: every skill ends with a block you copy and one question -
ship it, or change it? Be wary of anything that claims to run your channel on
its own.

**`hookscore.py` is a rough guide, not a prediction.** It was tuned on 74 real
short-form hooks (the first 15 seconds of auto-captions, the top 8 and bottom 8
by views across five channels). It's good at telling deliberately bad hooks
from real ones. It's barely able to tell a creator's hits from their own misses.
A low score is a reason to look again; a high score isn't a promise.

**The formula label is about the words, not the result.** When `/yt-viral` says
a title used The Statistic, that's a judgement about the title you can see, not
a claim about why the video got its views.

**`/yt-viral` reads, it doesn't scrape.** Public listings only. It never logs in
as you and never touches your passwords.

**Tags barely matter**, and this pack tells you so instead of selling you a tag
generator.

**Nothing makes up a number.** If a skill needs a figure it doesn't have, it
asks you or writes the line without it.

## Credit

Made by NateGold ([@nategold.ai](https://www.tiktok.com/@nategold.ai)).

## License

MIT. Use it, change it, ship it.
