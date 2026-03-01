---
name: xhs-creator
description: This skill should be used when the user asks to "写小红书", "小红书文案", "XHS post", "红书内容", "种草笔记", "轮播图文案", or wants to create content for Xiaohongshu (Little Red Book). Provides built-in content audit rules, platform-specific formatting, and Chinese social media copywriting guidance.
---

# 小红书内容创作助手

Create Xiaohongshu posts that comply with platform content rules, with built-in audit detection for banned content.

## Process

### Step 1: Understand the Brief

Gather the following before writing:

- **Topic**: What is the post about?
- **Goal**: 种草 (product recommendation) / 教程 (tutorial) / 引流 (traffic) / 个人IP (personal branding)?
- **Style**: 口语闲聊 (casual chat) / 干货清单 (listicle) / 故事型 (storytelling)?

### Step 2: Generate Content

**Title requirements:**
- Maximum 20 characters
- Include 1-2 emoji for visual appeal
- Questions or numbers perform best ("3 个方法让你..." / "为什么...")

**Body requirements:**
- Conversational tone with 小红书 vocabulary ("家人们"、"真的绝了"、"姐妹们")
- Short paragraphs (2-3 lines each)
- Emoji as visual separators (not excessive)
- Numbered lists for actionable content
- End with engagement hook: "你们觉得呢？" / "评论区告诉我～"

**Hashtags:**
- 5-10 relevant topics
- Mix broad topics (#日常分享) with precise ones (#效率工具推荐)

**Publishing advice:**
- Optimal posting: 8-10 PM or 12-1 PM
- First image determines click-through rate

### Step 3: Mandatory Audit Check

After generating content, scan against the audit rules in `references/audit-rules.md`. This step is **non-negotiable** — violating any rule results in the post being silently hidden by the platform.

For each flagged term:
1. Identify the violation
2. Replace with the safe alternative from the reference table
3. Inform the user what was changed and why

### Step 4: Image/Carousel Guidelines

When the user needs visual content:
- Dimensions: **1080x1440** (3:4 portrait) for best display
- Carousel: 5-9 slides, first slide is most critical
- Text on images must NOT use emoji (font rendering issue — displays as squares)
- Use colored circle icons or text labels instead of emoji
- Badge/label widths must adapt to text content length

## Output Format

```
📌 标题：[≤20 chars with emoji]

正文：
[Conversational body with emoji separators]
[Engagement hook at end]

话题：#tag1 #tag2 #tag3 ...

发布建议：[Timing + first image advice]

⚠️ 审核检查：[List any replacements made, or "通过，无敏感词"]
```

## Additional Resources

### Reference Files

- **`references/audit-rules.md`** — Complete list of banned terms, safe replacements, and platform audit rules. Consult this file for every post before output.
