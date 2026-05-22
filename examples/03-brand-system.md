# 示例 3：品牌设计系统创建

## 场景

需要根据品牌需求创建一份完整的 `DESIGN.md` 设计系统。

## 操作步骤

### Open Design 方式

```bash
pnpm tools-dev run web

# 选 Design System 模式 → design-md 技能
# 提示：
"为我的品牌'星云科技'创建一份设计系统：
这是一个面向开发者的云服务平台
目标受众：25-40 岁专业开发者
风格偏好：现代、科技感、深色主题
主色：深蓝 + 青色"
```

### HOMO 集成方式

```bash
homo run "使用 open-design 创建品牌设计系统
品牌名：星云科技
类型：B2B 云服务
受众：开发者
风格：科技感深色主题
品牌创意部 → 设计系统组"
```

## 输出 DESIGN.md 结构

```markdown
# 星云科技 Design System

## Visual Theme & Atmosphere
科技感、深色主题、开发者友好
...

## Color Palette & Roles
--accent: #0891b2 (青色)
--surface: #0f172a (深色)
--text: #f8fafc
...

## Typography Rules
正文: Inter / 16px / line-height 1.6
代码: JetBrains Mono / 14px
Display: 48px / weight 700

## Component Stylings
按钮 → 圆角 6px / 青蓝渐变 hover
卡片 → 深色背景 / 薄边框 1px solid rgba(255,255,255,0.1)
...

## Layout Principles
12 列网格 / 24px gutter
Z-pattern 阅读引导
...

## And more...
```

## 8 个设计系统的可视化对比

```
┌──────────┬──────────┬──────────┬──────────┐
│ Linear   │ Stripe   │ Vercel   │ Notion   │
│ (清爽)    │ (多彩)   │ (极简)   │ (务实)   │
├──────────┼──────────┼──────────┼──────────┤
│ Apple    │ Ant      │ Shopify  │ 小红书   │
│ (精致)    │ (规范)   │ (活力)   │ (社区)   │
└──────────┴──────────┴──────────┴──────────┘
```
