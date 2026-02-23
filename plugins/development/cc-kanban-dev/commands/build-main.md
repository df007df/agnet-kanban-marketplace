---
name: build-main
description: 仅编译主进程和 preload 代码
---

编译 Electron 主进程和 preload 脚本：
- 编译 src/main/ 到 dist-main/
- 编译 src/preload/ 到 dist-main/
- 不构建前端

运行 `npm run build:main`
