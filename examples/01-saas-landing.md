# 示例 1：SaaS 着陆页

## 场景

需要为一个 AI 客服助手产品生成 SaaS 着陆页。

## 操作步骤

### 方案 A：直接使用 Open Design

```bash
# 启动开发环境
pnpm tools-dev run web

# 在浏览器中：
# 1. 选择模式 → Prototype
# 2. 选择技能 → saas-landing
# 3. 选择设计系统 → 任意品牌（或默认）
# 4. 输入提示词：
"产品名称：ChatAI 客服助手
标语：智能客服，从对话开始
定位：面向中小企业的 AI 客服平台
主色：蓝色系
定价方案：3 档"
# 5. 点击生成
```

### 方案 B：通过 HOMO 接入

```bash
# HOMO 自动路由到 产品设计部 > 着陆页设计组
homo run "用 open-design 引擎为我生成一个 AI 客服助手的 SaaS 着陆页，
品牌用 modern-minimal 风格，蓝色主色调，需要定价方案"

# HOMO 适配器自动：
# 1. 解析为 OD 可执行 prompt
# 2. 注入 design system (modern-minimal)
# 3. 路由到对应部门智能体
# 4. 等待结果并返回
```

## 输出

- `index.html` — 含全部 CSS 的离线着陆页
- 预览在 iframe 中实时渲染

## HOMO 部门映射

```
HOMO 请求
  ↓
HOMO 适配器 → 解析意图 → 识别为"着陆页"
  ↓
部门路由 → 产品设计部 → 着陆页设计组
  ↓
智能体分配 → 1 个智能体（含设计系统上下文）
  ↓
Open Design daemon → 执行 saas-landing skill
  ↓
输出 index.html → 返回给 HOMO 调用方
```
