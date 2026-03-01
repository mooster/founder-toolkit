# Founder Toolkit

Essential Claude Code skills for startup founders. Built from real operational experience, not theory.

创业者工具箱 — 从实战中提炼的 Claude Code 技能集。

## Skills

| Skill | What it does | Language |
|-------|-------------|---------|
| **investor-update** | Generate professional investor monthly/quarterly updates | EN / 中文 |
| **pitch-reviewer** | Review pitch decks with structured VC-perspective scoring (10 dimensions, 1-5 each) | EN |
| **startup-metrics** | Calculate full SaaS metrics suite (ARR, NRR, LTV, CAC, burn multiple, runway, etc.) from raw data | EN / 中文 |
| **lead-scorer** | Score and prioritize outreach leads using ICP-first methodology | EN / 中文 |
| **xhs-creator** | 小红书内容创作助手 — 内置审核红线检测、排版规范、文案套路 | 中文 |

## Install

### Option 1: Add the marketplace (recommended)

```bash
/plugin marketplace add mooster/founder-toolkit
```

Then install in Claude Code:

```bash
/plugin install founder-toolkit@mooster-founder-toolkit
```

### Option 2: Install directly from GitHub

```bash
claude plugin install --source github:mooster/founder-toolkit
```

## Usage

Once installed, skills activate automatically when Claude detects relevant context:

- Say "help me write an investor update" → `investor-update` activates
- Say "review my pitch deck" → `pitch-reviewer` activates
- Say "calculate our SaaS metrics" → `startup-metrics` activates
- Say "score these leads" → `lead-scorer` activates
- Say "帮我写小红书文案" → `xhs-creator` activates

## Why This Exists

These skills encode real operational knowledge:

- **Lead Scorer**: Based on a production scoring system that evaluated 300+ companies
- **XHS Creator**: Includes audit rules learned from actual content takedowns on Xiaohongshu
- **Investor Update**: Follows YC / a16z best practices, written by a founder who sends these
- **Pitch Reviewer**: 10-dimension framework from the other side of the table
- **Startup Metrics**: Every formula with benchmark context, not just numbers in a vacuum

## License

MIT

---

Built by **Mu Chen** · CEO @ [Canopy Cloud](https://canopycloud.com) · [GitHub](https://github.com/mooster)
