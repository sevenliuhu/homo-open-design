# 示例 2：杂志风 Pitch Deck

## 场景

需要一份 8 页杂志风格的投资人 Pitch Deck，使用 歸藏 的排版风格。

## 操作步骤

### 方式一：Open Design 本地

```bash
pnpm tools-dev run web

# 选 Deck 模式 → guizang-ppt 技能
# 提示：
"请为我生成一份 8 页的 AI SaaS 投资人 Pitch Deck，
公司：智联科技
产品：AI 销售助手
融资轮次：种子轮
风格：杂志风，白底黑字为主，红色点缀"
```

### 方式二：HOMO 集成

```bash
homo run "用 open-design 的杂志风 PPT 技能，
生成 8 页 AI SaaS 种子轮投资人 Pitch Deck
品牌创意部 → 演示文稿组 → 调用 guizang-ppt skill"
```

## 关键技术点

- 使用 `guizang-ppt-skill` 的原生 SKILL.md
- 自动注入 `swiss-international` 设计系统
- 5 大方向选择器（Editorial Monocle / Modern Minimal / Tech Utility / Brutalist / Warm Soft）

## HOMO 部门映射

```
品牌创意部
  └── 演示文稿组
       ├── deck-guizang-editorial（杂志风）
       ├── deck-open-slide-canvas（开放式）
       └── deck-swiss-international（瑞士风）
```

## 输出

- `index.html` — 含分页导航的单文件网页
- `slides.json` — 可导出 PPTX 的 slides 数据
