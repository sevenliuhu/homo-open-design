# 示例 4：Agent CLI 对比与选择

## 16 Agent CLI 功能对比

| Agent CLI | 厂商 | 协议 | SKILL.md | 支持 | BYOK | 特点 |
|---|---|---|---|---|---|---|
| Claude Code | Anthropic | 原生 | ✅ 原生 | ✅ | 设计主力 |
| Codex CLI | OpenAI | 原生 | ✅ | ✅ | 代码能力强 |
| Devin Terminal | Cognition | shell | ✅ | ✅ | 全能型 |
| Cursor Agent | Cursor | IDE | ✅ | ✅ | IDE 集成 |
| Gemini CLI | Google | 原生 | ✅ | ✅ | 多模态 |
| OpenCode | OSS | 原生 | ✅ | ✅ | 开源免费 |
| Qwen Code | Alibaba | 原生 | ✅ | ✅ | 中文最佳 |
| Qoder CLI | Alibaba | 原生 | ✅ | ✅ | 代码优化 |
| GitHub Copilot CLI | GitHub | shell | ✅ | ✅ | 生态强 |
| Hermes (ACP) | OSS | ACP | ✅ | ✅ | 可扩展 |
| Kimi CLI (ACP) | Moonshot | ACP | ✅ | ✅ | 中文长上下文 |
| Pi (RPC) | Inflection | RPC | ✅ | ✅ | 对话式 |
| Kiro CLI (ACP) | Kiro | ACP | ✅ | ✅ | 轻量 |
| Kilo (ACP) | Kilo | ACP | ✅ | ✅ | 高性能 |
| Mistral Vibe CLI | Mistral | ACP | ✅ | ✅ | 欧洲隐私 |
| DeepSeek TUI | DeepSeek | TUI | ✅ | ✅ | 性价比之王 |

## Open Design 检测方式

```bash
# 核心检测逻辑：扫 PATH
for binary in claude codex devin cursor gemini opencode qwen qoder \
              github-copilot-cli hermes kimi pi kiro kilo \
              mistral-vibe deepseek-tui homo; do
    if command -v "$binary" &>/dev/null; then
        echo "✅ $binary found at $(which $binary)"
    fi
done
```

## HOMO 集成后的选择策略

```
用户需求 → HOMO 适配器
  ├── 中文内容为主 → Qwen Code / Kimi CLI
  ├── 设计为主 → Claude Code / Codex CLI
  ├── 代码+设计混合 → Cursor Agent / Devin
  ├── 预算优先 → DeepSeek TUI / OpenCode
  └── HOMO 智能体 → 自动路由到最合适的部门 agent
```
