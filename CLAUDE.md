# CLAUDE.md

## 工作规范

### 网页信息采集

**优先使用 kimi-webbridge** 采集网页信息，不要使用 WebSearch/WebFetch。

工作流程：

1. 健康检查：`~/.kimi-webbridge/bin/kimi-webbridge status`
2. 导航到目标页面（使用独立 session name）
3. 用 snapshot 读取正文
4. 如果文章包含长图（height > 500px），用 `evaluate` 提取图片 URL，下载后分段裁剪读取
5. **任务完成后必须清理**：`close_session` 关闭所有打开的标签页

长图处理要点：

- 微信图片可能是 WebP 格式，需转换为 PNG
- 高度超过 2000px 的图片需分段裁剪（每段 2000px）
- 用 Read 工具逐段读取图片内容

### Skill 安装与管理（开发者）

> 以下仅适用于项目开发者，终端用户不需要关心。

使用 [skills CLI](https://skills.sh/) 管理 skill，lock file 为 `skills-lock.json`。

**安装 skill（从 lock file 恢复）：**

```bash
npx skills@latest experimental_install
```

安装后 skill 位于 `.agents/skills/` 目录。

**配置给 Claude Code：**

`skills` CLI 默认安装到 `.agents/skills/`，但 Claude Code 读取的是 `.claude/` 目录。需要手动同步：

```bash
# 方法 1：符号链接（推荐，节省空间）
ln -s $(pwd)/.agents/skills/* .claude/skills/

# 方法 2：直接拷贝
cp -r .agents/skills/* .claude/skills/
```

如果只需要部分 skill，可以单独链接：

```bash
ln -s $(pwd)/.agents/skills/triage .claude/skills/triage
ln -s $(pwd)/.agents/skills/zoom-out .claude/skills/zoom-out
```

### Skill 编写

编写 skill 时，使用 `/skill-creator` skill，不要使用 `/write-a-skill`。

### 语言

与用户中文对话，计算机专业术语保留英文。

## Agent skills

### Issue tracker

Issues live in GitHub Issues. See `docs/agents/issue-tracker.md`.

### Triage labels

Default vocabulary: needs-triage, needs-info, ready-for-agent, ready-for-human, wontfix. See `docs/agents/triage-labels.md`.

### Domain docs

Single-context layout — one `CONTEXT.md` at the repo root + `docs/adr/`. See `docs/agents/domain.md`.
