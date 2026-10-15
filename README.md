# AudioShake for Claude

AudioShake plugins and skills for [Claude Code](https://claude.com/claude-code).
Ask Claude for stems, an instrumental, clean dialogue or lyrics with word timings,
and it runs [AudioShake](https://www.audioshake.ai) models for you.

## Install

Inside Claude Code:

```
/plugin marketplace add audioshake/claude-plugins
/plugin install audioshake@audioshake
```

Or from your shell:

```bash
claude plugin marketplace add audioshake/claude-plugins
claude plugin install audioshake@audioshake
```

You need an AudioShake account. Create an API key in the
[AudioShake dashboard](https://dashboard.audioshake.ai) and export it as
`AUDIOSHAKE_API_KEY`, or let Claude walk you through `audioshake login`.

## Plugins

| Plugin | What it does | Source |
| --- | --- | --- |
| `audioshake` | Runs AudioShake models through the `audioshake` CLI and Python library: stem separation, dialogue and effects isolation, speech clean-up, multi-speaker separation, music detection and removal, lyric transcription and alignment. | [audioshake-python](https://github.com/audioshake/audioshake-python/tree/main/plugin) |

Once installed, just ask:

- "Split `song.wav` into vocals, drums, bass and other."
- "Make an instrumental of every track in `./album`."
- "Pull the dialogue out of `scene.mp4` and drop the music."
- "Transcribe the lyrics of `track.mp3` with word timings."

Every run costs credits, charged per minute of audio for each model. Claude
checks with you before large batches.

## Updates

Each plugin is pinned to a tested release of the project it comes from. To get
the latest:

```
/plugin marketplace update audioshake
```

## Issues

Report a problem with a plugin in its source repository, linked in the table
above. For account or API questions, see the
[AudioShake developer docs](https://developer.audioshake.ai).
