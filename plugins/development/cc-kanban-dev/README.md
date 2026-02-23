# CC-Kanban Dev Plugin

CC-Kanban 项目开发工具集插件，提供前端、UI/UX、测试等技能和代理。

## 包含内容

### Skills (智能技能)
- `prepare-dev-request-context` - 开发前准备上下文
- `project-guide-generator` - 项目指引生成器
- `test-acceptance-flow` - 测试验收流程
- `ui-ux-pro-max` - UI/UX 设计工具

### Agents (子代理)
- `frontend-react-expert` - 前端 React 专家

### Commands (命令)
- `dev` - 启动开发模式
- `build` - 构建项目
- `build-main` - 仅编译主进程
- `package` - 打包应用
- `install` - 安装依赖
- `preview` - 预览构建结果
- `demo` - 运行 Agent SDK 演示

### Hooks (事件钩子)
- `PostToolUse` - 文件编辑后记录日志
- `PreToolUse` - Git 提交前提示检查
- `SessionStart` - 会话开始欢迎信息

## 使用方法

### 方式 1: 临时加载（开发测试）

```bash
claude --plugin-dir ./plugins/cc-kanban-dev
```

### 方式 2: 项目范围安装

插件已配置在 `.claude/settings.json` 中，所有项目成员克隆后即可使用。

### 调用方式

```
# Skills
/cc-kanban-dev:prepare-dev-request-context
/cc-kanban-dev:project-guide-generator
/cc-kanban-dev:test-acceptance-flow
/cc-kanban-dev:ui-ux-pro-max

# Agents
/cc-kanban-dev:frontend-react-expert

# Commands
/cc-kanban-dev:dev
/cc-kanban-dev:build
/cc-kanban-dev:package
/cc-kanban-dev:install
```

## 目录结构

```
plugins/cc-kanban-dev/
├── .claude-plugin/
│   └── plugin.json          # 插件清单
├── agents/
│   └── frontend-react-expert.md
├── skills/
│   ├── prepare-dev-request-context/
│   ├── project-guide-generator/
│   ├── test-acceptance-flow/
│   └── ui-ux-pro-max/
├── commands/
│   ├── dev.md
│   ├── build.md
│   ├── build-main.md
│   ├── package.md
│   ├── install.md
│   ├── preview.md
│   └── demo.md
├── hooks/
│   └── hooks.json
└── README.md
```

## 后续扩展

- 添加 MCP Servers 连接 GitHub、JIRA
- 添加 LSP Servers 支持更多语言
- 添加更多 Hooks（lint、format）
