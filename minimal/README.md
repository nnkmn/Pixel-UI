# Pixel Minimal UI — 极简风版

> 硬像素风组件库 | v3.0.0

## 设计风格

- 硬边框、方块阴影（0~2px 圆角）
- step-end 过渡动画（复古游戏感）
- 等宽字体为主
- 适合工具类应用、管理后台、极简主义项目

## 文件说明

| 文件 | 说明 |
|------|------|
| `pixel-minimal.css` | 主样式表 |
| `pixel-icons.svg` | 图标库 (60+ 图标) |
| `index.html` | 组件演示页 |
| 本文件 | 自述文档 |

## 快速开始

```html
<!-- 引入图标 -->
<div style="display: none">
  <svg xmlns="http://www.w3.org/2000/svg">
    <!-- 复制 pixel-icons.svg 内容 -->
  </svg>
</div>

<!-- 引入样式 -->
<link rel="stylesheet" href="pixel-minimal.css">

<!-- 使用 -->
<button class="pm-btn pm-btn-primary">
  <svg class="pm-icon"><use href="#pm-icon-check"></use></svg>
  提交
</button>
```

## CSS 变量前缀

所有变量使用 `--pm-` 前缀，class 使用 `.pm-` 前缀。

### 设计特点

- 圆角极小或为零（`--pm-radius-sm: 0px`）
- 阴影用偏移硬阴影（非模糊）
- 过渡动画用 `step-end` 模拟像素感
- 字体默认等宽（Press Start 2P / VT323）

### 可自定义变量

```css
:root {
  --pm-primary-500: #4061ff;     /* 主色 */
  --pm-border-color: #000;       /* 边框色 */
  --pm-shadow-md: 4px 4px 0 #000; /* 硬阴影 */
}
```

## 组件列表

同 gradient 版，全部组件都有对应实现：
Button, Input, Checkbox/Radio/Switch, Card, Avatar, Badge, Alert,
Tabs, Navbar, Breadcrumb, Pagination, Progress, Loading, Table,
Dropdown, Tooltip, Modal, Divider, Empty State

## 图标使用

z-index: 9999 强制最高层。

```html
<svg class="pm-icon"><use href="#pm-icon-name"></use></svg>
<svg class="pm-icon pm-icon-lg"><use href="#pm-icon-terminal"></use></svg>
```

## 主题切换

```html
<body data-theme="dark">   <!-- 暗色：黑底白字 -->
```
