# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个简单的贪吃蛇游戏，所有代码（HTML、CSS、JavaScript）都内联在 `snake-game.html` 单个文件中。

## 运行游戏

直接在浏览器中打开 `snake-game.html` 文件即可运行游戏。

```bash
open snake-game.html
```

## 游戏架构

游戏使用 HTML5 Canvas 进行渲染，主要组件：

- **画布设置**: 400x400 像素，20x20 网格（每格 20 像素）
- **游戏循环**: 使用 `setInterval` 控制游戏速度，初始速度 100ms/帧
- **游戏状态**: 通过 `isGameRunning` 标志控制运行/暂停
- **难度递增**: 每吃到食物游戏速度加快 2ms，最低 50ms/帧

### 关键函数

- `initGame()`: 初始化游戏状态，重置蛇和分数
- `gameStep()`: 每帧执行移动和绘制
- `moveSnake()`: 计算蛇的新位置，检测碰撞（墙壁/自身）
- `drawGame()`: 绘制游戏画面（网格、食物、蛇）
- `placeFood()`: 在随机位置生成食物（避开蛇身）
- `startGame()` / `pauseGame()` / `resetGame()`: 控制游戏流程

### 控制方式

- 方向键: `↑` `↓` `←` `→`
- WASD 键: `W` `A` `S` `D`

### 视觉特性

- 渐变背景和按钮效果
- 蛇身从绿色渐变到深色
- 蛇头带有眼睛（白色+黑色瞳孔）
- 游戏结束弹出带动画的模态框
