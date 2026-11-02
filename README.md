# AudioShake plugins

AudioShake plugins and skills for AI coding agents: [Claude Code](https://claude.com/claude-code),
[Codex](https://developers.openai.com/codex) and the ChatGPT desktop app.
Ask your agent for stems, an instrumental, clean dialogue or lyrics with word timings,
and it runs [AudioShake](https://www.audioshake.ai) models for you.

## Install

You need an AudioShake account. Create an API key in the
[AudioShake dashboard](https://dashboard.audioshake.ai) and export it as
`AUDIOSHAKE_API_KEY`, or let your agent walk you through `audioshake login`.

### Claude Code

Inside Claude Code:

```
/plugin marketplace add audioshake/claude-plugins
/plugin install audioshake-cli@audioshake
```

Or from your shell:

```bash
claude plugin marketplace add audioshake/claude-plugins
claude plugin install audioshake-cli@audioshake
```

### Codex

From your shell:

```bash
codex plugin marketplace add audioshake/claude-plugins
codex plugin add audioshake-cli@audioshake
```

Inside a Codex session, `/plugins` opens the same catalog. In the ChatGPT
desktop app, open the Plugins Directory and choose the AudioShake marketplace.

## Plugins

| Plugin | What it does | Source |
| --- | --- | --- |
| `audioshake-cli` | Runs AudioShake models through the `audioshake` CLI and Python library: stem separation, dialogue and effects isolation, speech clean-up, multi-speaker separation, music detection and removal, lyric transcription and alignment. | [audioshake-python](https://github.com/audioshake/audioshake-python/tree/main/plugin) |

Once installed, just ask:

- "Split `song.wav` into vocals, drums, bass and other."
- "Make an instrumental of every track in `./album`."
- "Pull the dialogue out of `scene.mp4` and drop the music."
- "Transcribe the lyrics of `track.mp3` with word timings."

Every run costs credits, charged per minute of audio for each model. Your agent
checks with you before large batches.

## Updates

Each plugin entry points at a release or branch of the project it comes from.
To get the latest:

```
/plugin marketplace update audioshake      # Claude Code
codex plugin marketplace upgrade audioshake  # Codex
```

## How this repository is laid out

One catalog, two manifests. Both list the same plugins from the same sources.

| File | Read by |
| --- | --- |
| `.claude-plugin/marketplace.json` | Claude Code |
| `.agents/plugins/marketplace.json` | Codex CLI, Codex IDE extensions, ChatGPT desktop |

Each plugin's own directory carries a `.claude-plugin/plugin.json` and a
`.codex-plugin/plugin.json`, with a shared `skills/` folder in the open
[Agent Skills](https://agentskills.io) format. The skills also install directly
into any agent that reads that format, with no marketplace involved.

## Issues

Report a problem with a plugin in its source repository, linked in the table
above. For account or API questions, see the
[AudioShake developer docs](https://developer.audioshake.ai).
