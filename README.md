[中文](./README.md) | [English](./README_en.md)

# SeedMusic 音乐提示词 Skill — Claude Code 插件

一个 Claude Code 自定义 Skill，让 Claude 成为专业 AI 音乐提示词工程师，专门为 **SeedMusic / 即梦音乐** 等 prompt-to-song 模型生成可直接使用的中文音乐提示词。

只需要用自然语言描述你的音乐想法，Skill 会生成结构化、可复制的音乐提示词，覆盖曲风、情绪、人声、乐器、编曲、歌曲结构、歌词方向和负面约束。

## 功能特性

### 音乐提示词生成能力

| # | 能力 | 说明 |
|---|------|------|
| 1 | **歌曲提示词生成** | 生成完整人声歌曲、中文歌、英文歌、国风、R&B、爵士、民谣等音乐提示词 |
| 2 | **BGM / 配乐提示词** | 为短视频、Vlog、活动、广告、片尾等场景生成配乐提示词 |
| 3 | **中文本土曲风优化** | 支持国风、戏腔、民乐融合、东北民歌、二人转等中文语境 |
| 4 | **人声与唱法控制** | 指定性别、音色、咬字、气声、戏腔、童声、合唱、和声层次 |
| 5 | **编曲与乐器控制** | 控制乐器、节奏密度、空间感、混响、段落推进和副歌爆发 |
| 6 | **歌曲结构控制** | 按前奏、主歌、预副歌、副歌、桥段、尾奏设计完整结构 |
| 7 | **歌词混合输入** | 将歌词语言、歌词方向、Hook 和音乐要求合并写入同一提示词 |
| 8 | **负面约束** | 明确排除不想要的曲风、唱法、乐器、混响、自动修音等 |

### 内置词库

Skill 内置音乐提示词词库，包括：

- **歌曲风格**：华语流行、国风流行、戏腔国风、中文 R&B、Vocal Jazz、Acapella、Electronic、Folk 等
- **画面场景**：午夜城市街头、江南烟雨小巷、山顶火堆、酒吧角落、校园黄昏、电影片尾等
- **情绪氛围**：温暖、治愈、遗憾、孤独、空灵、宿命感、热烈、抓耳、舞台感等
- **人声表达**：空灵女声、沙哑女声、低音男声、戏腔、念白、男女合唱、和声环绕等
- **乐器编曲**：木吉他、古筝、二胡、竹笛、唢呐、三弦、brush kit、saxophone、R&B 鼓组等
- **负面约束**：不要 KTV 混响、不要自动调音感、不要流行鼓点、不要大合唱等

## 安装

### 前置要求

- 已安装并登录 [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code)
- 拥有 SeedMusic / 即梦音乐等 AI 音乐生成工具账号，用于使用生成后的提示词

### 安装步骤

1. **克隆仓库**

```bash
git clone https://github.com/xiaoliangliang/seedmusic-prompt-skill.git
```

2. **复制 Skill 文件到项目的 `.claude/skills/` 目录**

```bash
# 进入你要使用该 Skill 的项目目录
cd /path/to/your/project

# 创建 skills 目录
mkdir -p .claude/skills/seedmusic

# 复制 Skill 文件
cp /path/to/seedmusic-prompt-skill/.claude/skills/seedmusic/SKILL.md .claude/skills/seedmusic/SKILL.md
```

3. **验证安装**

在项目目录启动 Claude Code：

```bash
claude
```

输入 `/seedmusic` 或直接描述你的音乐需求。Claude 会自动激活 SeedMusic 音乐提示词 Skill。

### 全局安装（可选）

如果希望在所有项目中都能使用该 Skill，可以放到用户主目录：

```bash
mkdir -p ~/.claude/skills/seedmusic
cp /path/to/seedmusic-prompt-skill/.claude/skills/seedmusic/SKILL.md ~/.claude/skills/seedmusic/SKILL.md
```

## 使用方法

### 快速开始

启动 Claude Code，描述你想生成的音乐：

```text
You: 帮我写一首烟雨江南国风歌曲的 SeedMusic 提示词，女声，伤感但不要太苦情
```

Claude 会生成可直接复制到 SeedMusic / 即梦音乐中的结构化提示词。

### 触发方式

Skill 会在以下情况自动激活：

- 使用 `/seedmusic` 命令
- 提到关键词：`SeedMusic`、`即梦音乐`、`音乐提示词`、`AI音乐`、`AI歌曲`、`BGM`、`短视频配乐`
- 要求“写一首歌的提示词”“优化音乐 prompt”“生成 AI 音乐提示词”

### 交互流程

```text
第一步：描述音乐想法 -> “一首雨夜城市 R&B”
第二步：Claude 补齐参数 -> 曲风、情绪、人声、BPM、乐器、结构
第三步：生成提示词 -> 简单版或结构化版
第四步：微调优化 -> 调整人声、编曲、歌词、负面约束
```

## 使用示例

### 示例一：国风歌曲

**输入：**

```text
帮我写一首烟雨江南国风歌曲提示词，女声，伤感，适合短视频
```

**输出：**

```text
【歌曲风格】
国风流行，融合古筝、二胡、竹笛和轻柔雨声，整体舒缓清冷。

【画面场景】
江南烟雨小巷，雨停后的青石板路，旧伞、灯笼和远处若隐若现的河岸。

【情绪氛围】
遗憾、克制、清冷、细腻，不要过度苦情，要有淡淡的回忆感。

【人声要求】
温柔女声轻柔浅唱，主歌气声感强，副歌加入婉转但克制的戏腔，咬字清晰。

【编曲伴奏】
古筝分解旋律作为主线，二胡拉出伤感长音，竹笛点缀句尾，背景加入轻柔雨声。鼓点要轻，不要强烈电子节拍。

【歌曲结构】
前奏用雨声和古筝进入，主歌低声叙事，预副歌逐渐铺开，副歌用戏腔形成记忆点，尾奏用竹笛和雨声淡出。

【绝对不要】
不要 KTV 混响，不要自动调音感，不要流行舞曲鼓点，不要大合唱。
```

### 示例二：英文爵士

**输入：**

```text
写一首英文 Vocal Jazz，男低音，夜晚酒吧，慵懒微醺
```

**输出：**

```text
英文 Vocal Jazz，低音男声 crooner 风格，85 BPM。画面是深夜酒吧角落，两个人低声聊天直到天亮，情绪微醺、慵懒、自洽。

配器以钢琴、saxophone、brush kit 和低音贝斯为主。主唱靠前，咬字亲密松弛，鼓刷轻柔摆动，saxophone 在句尾做回应。不要大乐队轰鸣，不要电子节拍，不要过度修音。
```

### 示例三：东北本土风格

**输入：**

```text
写一首东北乡村风，感谢爹娘，二人转感觉但不要太土
```

**输出：**

```text
东北乡村主题歌曲，融合东北民歌和二人转风格，五声音阶旋律，明快但不轻浮。主题是感谢父母养育恩，情绪深情、豪迈、接地气。

【演唱】
口语化、直接表达，嗓音苍劲醇厚，带东北方言气质，咬字豪爽敞亮。高潮可以有哭腔、拖腔、嘶喊感，但不要变成夸张喊麦或土味神曲。

【乐器配置】
前段以二胡、唢呐、手风琴铺底；中段加入大鼓、板胡、贝斯和吉他；高潮加入呼喊式和声。

【绝对不要】
不要精致都市流行感，不要电子舞曲感，不要过度修音，不要甜歌唱法。
```

## 项目结构

```text
.
├── .claude/
│   └── skills/
│       └── seedmusic/
│           └── SKILL.md          # Skill 定义文件（核心文件）
├── .gitignore
├── README.md                     # 中文文档（默认）
└── README_en.md                  # English documentation
```

整个 Skill 的逻辑都包含在一个文件中：`.claude/skills/seedmusic/SKILL.md`。

## 常见问题

### Skill 没有自动激活怎么办？

确认 `SKILL.md` 文件位于正确路径：`.claude/skills/seedmusic/SKILL.md`。如果仍然无法激活，可以直接使用 `/seedmusic` 命令触发。

### 支持英文提示词吗？

当前 Skill 优先为 SeedMusic / 即梦音乐生成中文提示词，因为中文语境和本土曲风控制更稳定。你也可以要求它生成英文歌词、英文歌曲或双语歌曲。

### 可以生成歌词吗？

可以。由于部分音乐模型不区分“歌词”和“音乐要求”两个字段，Skill 会把歌词语言、Hook、歌词方向和音乐要求写在同一个提示词里。

### 如何让生成结果更稳定？

- 明确主曲风，不要堆太多风格
- 写清楚人声、乐器、段落结构
- 加入具体负面约束
- 对完整歌曲使用结构化提示词

## 贡献指南

欢迎贡献代码和提示词案例。可以参与的方向：

- 补充更多 SeedMusic 音乐提示词示例
- 增加更多中文本土曲风、方言、民乐融合案例
- 优化提示词质量检查规则
- 根据真实生成效果修正词库和模板

贡献步骤：

1. Fork 本仓库
2. 创建功能分支：`git checkout -b feature/your-feature`
3. 提交更改：`git commit -m "Add your feature"`
4. 推送分支：`git push origin feature/your-feature`
5. 发起 Pull Request

## 许可

MIT

## 致谢

- [SeedMusic / 即梦音乐](https://jimeng.jianying.com) — 字节跳动 AI 音乐生成能力
- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) — Anthropic 可扩展 Skill 系统
