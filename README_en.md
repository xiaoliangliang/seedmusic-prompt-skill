[中文](./README.md) | [English](./README_en.md)

# SeedMusic Prompt Skill for Claude Code

A Claude Code custom skill that turns Claude into a professional AI music prompt engineer for **SeedMusic / Jimeng AI music** and other prompt-to-song models.

Describe a music idea in natural language, and this skill generates structured, production-ready Chinese music prompts covering style, scene, mood, vocals, instruments, arrangement, song structure, lyric direction, and negative constraints.

## Features

| # | Capability | Description |
|---|------------|-------------|
| 1 | **Song prompt generation** | Generate prompts for Chinese songs, English songs, vocal tracks, R&B, jazz, folk, electronic, and Chinese fusion styles |
| 2 | **BGM / soundtrack prompts** | Create background music prompts for short videos, vlogs, campaigns, events, and endings |
| 3 | **Chinese local style control** | Support guofeng, opera vocals, folk instruments, regional folk, and local musical context |
| 4 | **Vocal direction** | Specify gender, timbre, diction, breathiness, opera style, child voice, chorus, and harmony layers |
| 5 | **Arrangement control** | Control instruments, rhythm density, space, reverb, section build, and chorus impact |
| 6 | **Song structure** | Design intro, verse, pre-chorus, chorus, bridge, and outro |
| 7 | **Lyric-aware prompts** | Mix lyric language, hook direction, and music requirements into one prompt |
| 8 | **Negative constraints** | Exclude unwanted genres, vocal effects, instruments, reverb, autotune, or production styles |

## Installation

### Prerequisites

- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) installed and authenticated
- A SeedMusic / Jimeng AI music account or another AI music generation tool for using the generated prompts

### Steps

1. **Clone the repository**

```bash
git clone https://github.com/xiaoliangliang/seedmusic-prompt-skill.git
```

2. **Copy the skill into your project's `.claude/skills/` directory**

```bash
cd /path/to/your/project
mkdir -p .claude/skills/seedmusic
cp /path/to/seedmusic-prompt-skill/.claude/skills/seedmusic/SKILL.md .claude/skills/seedmusic/SKILL.md
```

3. **Verify installation**

Start Claude Code in your project:

```bash
claude
```

Then type `/seedmusic` or describe your music idea. Claude should activate the SeedMusic prompt skill automatically.

### Optional: Global Installation

```bash
mkdir -p ~/.claude/skills/seedmusic
cp /path/to/seedmusic-prompt-skill/.claude/skills/seedmusic/SKILL.md ~/.claude/skills/seedmusic/SKILL.md
```

## Usage

### Quick Start

```text
You: 帮我写一首烟雨江南国风歌曲的 SeedMusic 提示词，女声，伤感但不要太苦情
```

Claude will generate a copy-ready structured prompt for SeedMusic / Jimeng AI music.

### Triggering the Skill

The skill activates when you:

- Use the `/seedmusic` command
- Mention `SeedMusic`, `即梦音乐`, `音乐提示词`, `AI音乐`, `AI歌曲`, `BGM`, or `短视频配乐`
- Ask to write, generate, optimize, or diagnose AI music prompts

## Project Structure

```text
.
├── .claude/
│   └── skills/
│       └── seedmusic/
│           └── SKILL.md          # Core skill definition
├── .gitignore
├── README.md                     # Chinese documentation by default
└── README_en.md                  # English documentation
```

The entire skill logic is contained in one file: `.claude/skills/seedmusic/SKILL.md`.

## License

MIT

## Acknowledgements

- [SeedMusic / Jimeng AI](https://jimeng.jianying.com) by ByteDance
- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) by Anthropic
