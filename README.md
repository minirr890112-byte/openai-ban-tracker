<p align="center">
  <img src="https://img.shields.io/badge/ClawHub-downloads-0-blue" alt="ClawHub downloads">
  <img src="https://img.shields.io/badge/ban%20reasons-8-red" alt="8 ban reasons">
  <img src="https://img.shields.io/badge/license-MIT-yellow" alt="MIT license">
</p>

# 🔍 openai-ban-tracker

> **EN**: OpenAI account ban risk detection & appeal tracking CLI. Assess your risk in 9 questions, learn 8 known ban reasons, generate appeal templates in Chinese & English, scan V2EX for real-time ban signals.
>
> **中文**: OpenAI 封号风险检测与解封追踪 CLI 工具。9 题风险评估、8 种已确认封号原因、中英文申诉模板、V2EX 社区实时扫描。

> **背景 / Background**: 2026年6月，OpenAI 再次大规模封号，V2EX 社区 24 小时内出现 23 回复 + 18 回复两个热帖。用户困惑于为什么被封、如何申诉、是否会解封。 / June 2026: OpenAI launched another mass ban wave. V2EX community exploded with 23+18 reply threads within 24 hours. Users confused about why they were banned, how to appeal, and whether bans are reversed.

## 安装

```bash
pip install git+https://github.com/minirr890112-byte/openai-ban-tracker.git
```

## 快速开始

```bash
# 1. 查看社区最新动态
openai-ban-tracker status

# 2. 检测你的账号风险
openai-ban-tracker risk-check

# 3. 了解常见封号原因
openai-ban-tracker ban-reasons

# 4. 生成申诉邮件模板
openai-ban-tracker appeal --lang zh
openai-ban-tracker appeal --lang en --output appeal.txt

# 5. 实时扫描社区信号
openai-ban-tracker scan
```
## 🌐 生态系统

| Tool | Description |
|---|---|
| [cursor-doctor](https://github.com/minirr890112-byte/cursor-doctor) | Cursor IDE 诊断修复工具 |
| [claude-intel-monitor](https://github.com/minirr890112-byte/claude-intel-monitor) | AI模型降智检测 |
| [prompt-inspector](https://github.com/minirr890112-byte/prompt-inspector) | Prompt 审查触发词扫描 |


## 命令详解

### `risk-check` — 风险评估

通过 9 个问题评估你的账号被封风险，输出 0-100 风险评分：

```
$ openai-ban-tracker risk-check

⚠️  封号风险评估
———————————————————

  你是否和别人合租/共享 OpenAI 账号？
  (y/n): n

  你是否使用过淘宝/闲鱼等平台的代充服务？
  (y/n): n

  ...（共 9 题）

┌──────────────────────────────────────────────┐
│ 风险评分: 15/100                              │
│ 风险等级: 低风险                               │
└──────────────────────────────────────────────┘
```

### `ban-reasons` — 封号原因库

列出 8 种已确认的封号原因，包含：
- 风险等级（极高/高/中/低）
- 常见模式
- 预防建议
- 申诉成功率

### `appeal` — 申诉模板

生成中英文申诉邮件模板，包含已验证的申诉技巧。

### `status` — 社区动态

聚合 V2EX 最新封号/解封信号：

```
┌──────────────────────────────────────────────────────────┐
│ 日期        事件                                 回复  级别  │
├──────────────────────────────────────────────────────────┤
│ 2026-06-06  总结 OpenAI 封号问题                    23  🔴 严重│
│ 2026-06-06  OpenAI 陆续开始主动解封                  18  🔵 信息│
│ 2026-06-05  Codex 用户突然被封号                      3  🟡 警告│
│ 2026-06-04  GPT代充封号风险警告                        3  🟡 警告│
└──────────────────────────────────────────────────────────┘
```

### `scan` — 实时扫描

联网扫描 V2EX 的 openai/agent/aigc 节点，获取最新封号相关帖子。

## 数据来源

- V2EX 社区帖子（openai, agent, aigc 节点）
- Reddit r/OpenAI
- 开源社区报告

**隐私说明**: 所有风险评估在本地执行，不收集或上传任何个人信息。

## License

MIT
