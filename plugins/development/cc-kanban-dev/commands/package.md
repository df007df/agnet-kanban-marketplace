---
name: package
description: 构建并打包为可分发的应用程序
---

打包 CC-Kanban 为可分发的应用程序：
- 先运行 `npm run build`
- 然后使用 electron-builder 打包
- 输出到 release/ 目录

运行 `npm run package`

注意：需要本机可编译 sqlite3 原生模块。
