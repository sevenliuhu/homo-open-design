# HOMO Open Design — Agent 指南

本项目是 [nexu-io/open-design](https://github.com/nexu-io/open-design) 的 HOMO 集成版。
核心代码和架构参考上游项目的 `AGENTS.md`。

## 目录结构

```
adapter/          ← HOMO 适配层（SKILL.md ↔ 部门技能格式）
skills/           ← SKILL.md 适配样例（完整版 134 个参考上游）
design-systems/   ← 设计系统映射（完整版 152 个参考上游）
craft/            ← 通用工艺规则
cli/              ← CLI 检测工具
examples/         ← 使用示例
```

## 关键协议

- **SKILL.md**: Claude Code 原生技能格式，含 `od:` 扩展字段和 `homo:` HOMO 扩展字段
- **DESIGN.md**: 9 段式品牌设计系统格式
- **craft/**: 跨品牌的通用工艺规则，技能通过 `od.craft.requires` 选择注入

## Agent 工作流

1. 用户输入需求 → 检测可用 Agent CLI
2. 根据需求匹配技能（SKILL.md）
3. 注入设计系统（DESIGN.md）和工艺规则（craft/）
4. Agent 执行工作流 → 生成设计产物
5. 预览 → 迭代 → 导出
