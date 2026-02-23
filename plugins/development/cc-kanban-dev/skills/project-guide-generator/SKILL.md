---
name: project-guide-generator
description: 项目指引生成器。根据项目文档、代码目录结构和关键代码分析，生成一份功能指引目录，方便后续快速定位代码。使用场景：用户说"帮我看看这个项目怎么运作的"或"我想添加一个功能但不知道在哪下手"。
version: 0.1
---

# 项目指引生成器

当用户需要**了解项目结构、定位功能代码**时使用本技能。

---

## 何时使用

- 用户说「这个项目怎么运作的」「帮我看下代码结构」
- 用户说「我想加个功能但不知道在哪」「某个功能在哪里实现的」
- 新人接手项目，需要快速了解全貌
- 需要生成项目功能索引，方便后续开发

---

## 执行步骤

### 1. 收集项目信息

**文档收集**（按优先级）：
- `CLAUDE.md` - AI 项目说明（最重要）
- `README.md` / `readme.md` - 项目介绍
- `docs/` 目录下的文档
- `CHANGELOG.md` - 变更日志
- `CONTRIBUTING.md` - 贡献指南

**代码结构分析**：
- 扫描 `src/` 目录结构，了解前后端分离
- 找到入口文件（如 `main.tsx`, `index.ts`, `App.tsx`）
- 识别技术栈：React/Vue/其他前端框架、Electron/Tauri/其他桌面框架、数据库类型

### 2. 关键代码阅读

**前端入口**：
- 前端入口文件（React: main.tsx/App.tsx, Vue: main.ts/App.vue）
- 路由配置（如果有）
- 状态管理（Zustand/Redux/Context/Store）

**后端入口**：
- 主进程入口（Electron: main/index.ts）
- IPC 处理器注册
- 数据库模型/表结构

**核心模块**：
- 找到核心业务模块目录（如 `components/`, `services/`, `stores/`）
- 识别主要功能区域

### 3. 生成指引报告

生成结构化报告，保存到 `.ccKanban/project-guide.md`，格式如下：

```markdown
# 项目功能指引

## 项目概览
- 项目名称：
- 技术栈：
- 入口文件：

## 目录结构

### 前端 (src/renderer/)
- components/ - UI 组件
- stores/ - 状态管理
- api.ts - 与主进程通信
- App.tsx - 根组件

### 主进程 (src/main/)
- index.ts - 入口
- ipc.ts - IPC 处理器
- db.ts - 数据库
- settings.ts - 配置管理

## 功能模块

### 模块名称
- 位置：`src/renderer/components/xxx.tsx`
- 功能描述
- 关键函数/方法

## 快速定位

| 功能 | 位置 |
|------|------|
| 看板列表 | src/renderer/components/KanbanBoard.tsx |
| 卡片操作 | ... |
```

---

## 输出要求

1. **语言**：使用中文
2. **报告位置**：`.ccKanban/project-guide.md`
3. **如果已存在**：询问用户是否覆盖，或追加新内容
4. **完成后**：告诉用户报告已生成，提供快速查看方式
