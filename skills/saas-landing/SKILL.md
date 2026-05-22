---
name: saas-landing
description: |
  单页 SaaS 着陆页，含 hero、功能特性、社交信任、定价方案、CTA 和页脚。
  触发词：saas landing, 营销页, 产品着陆页。
triggers:
  - "saas landing"
  - "marketing page"
  - "产品着陆页"
  - "营销页"
  - "SaaS 着陆页"

od:
  mode: prototype
  preview:
    type: html
    entry: index.html
  design_system:
    requires: true
    sections: [color, typography, layout, components]
  craft:
    requires: [typography, color, anti-ai-slop]
  inputs:
    - name: product_name
      type: string
      required: true
      description: 产品名称
    - name: tagline
      type: string
      required: true
      description: 产品标语
    - name: has_pricing
      type: boolean
      default: true
      description: 是否包含定价方案
  homo:
    department: 产品设计部
    skill_group: 着陆页设计组
    category: 原型设计
    ai_required: 1
---

# SaaS 着陆页工作流

## 第一步：读取设计系统

1. 从 cwd 读取 `DESIGN.md`（如果存在）
2. 采用其中的色板、字体、布局规则和组件样式
3. 如果不存在 DESIGN.md，使用默认的现代简约风格

## 第二步：搭建页面结构

使用 `assets/base.html` 作为模板，构建以下区块：

```
┌─────────────────────────┐
│     导航栏 (Navbar)      │
├─────────────────────────┤
│   Hero 区               │
│   · 主标题（h1）          │
│   · 副标题/标语           │
│   · CTA 按钮             │
├─────────────────────────┤
│   社交信任 (Logo Bar)    │
├─────────────────────────┤
│   功能特性 (3-6 个)      │
│   · 每个含图标 + 标题     │
│   · 说明文字             │
├─────────────────────────┤
│   数据/成果展示          │
├─────────────────────────┤
│   定价方案 (如需要)       │
│   · 3 个方案卡片         │
│   · 推荐方案突出显示      │
├─────────────────────────┤
│   FAQ                   │
├─────────────────────────┤
│   CTA 底部              │
├─────────────────────────┤
│     页脚                │
└─────────────────────────┘
```

## 第三步：编写严格规则

### 禁止事项（Anti-AI-slop）

- ❌ 紫色渐变 hero（`#6366f1` 是 AI 默认色，禁用）
- ❌ 用 emoji 当功能图标（📊 💡 🚀 ✨）
- ❌ 虚构数据（"10× faster"，"4000+ customers"）
- ❌ 使用 Inter 作为显示字体
- ❌ 圆角卡片 + 左边框强调（"AI 默认三件套"）

### 必须遵守

- ✅ 内联所有 CSS，不依赖外部 CDN
- ✅ 系统字体栈作为后备
- ✅ 字距规则：全大写字标注 ≥0.06em
- ✅ 主色在页面出现不超过 3 次
- ✅ 保持 OKLch 色域意识

## 第四步：自我评审

生成前，对照 `references/checklist.md` 自我检查，通过 P0 才能输出。

## 第五步：输出

将最终产物写入 `index.html`，内联所有样式，确保离线可用。
