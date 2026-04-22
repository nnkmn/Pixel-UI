# Pixel Custom UI — 自定义版

> 完全可定制的组件库 | v3.0.0

## 设计风格

颜色完全通过 CSS 变量驱动。改几个值就能换整套皮肤。

适合需要品牌定制的项目、多主题切换场景。

## 文件说明

| 文件 | 说明 |
|------|------|
| `pixel-custom.css` | 主样式表（全变量驱动） |
| `pixel-icons.svg` | 图标库 (60+ 图标) |
| `index.html` | 组件演示页（含颜色选择器） |
| 本文件 | 自述文档 + 定制指南 |

## 快速开始

```html
<div style="display: none">
  <svg xmlns="http://www.w3.org/2000/svg">
    <!-- 复制 pixel-icons.svg 内容 -->
  </svg>
</div>

<link rel="stylesheet" href="pixel-custom.css">

<button class="pc-btn pc-btn-primary">按钮</button>
```

## CSS 变量前缀

变量 `--pc-*`，class `.pc-*`。

## 定制指南

### 换主色

改一个变量就够了：

```css
:root {
  --pc-primary: #ff6b35;      /* 橙色系 */
}
```

### 换整套配色方案

```css
:root {
  /* 主色 */
  --pc-primary: #10b981;           /* 绿色 */
  --pc-primary-light: #d1fae5;

  /* 功能色 */
  --pc-success: #22c55e;
  --pc-warning: #f59e0b;
  --pc-error: #ef4444;
  --pc-info: #0ea5e9;

  /* 背景 & 文字 */
  --pc-bg-primary: #ffffff;
  --pc-bg-secondary: #f8fafc;
  --pc-text-primary: #0f172a;

  /* 圆角 */
  --pc-radius-md: 12px;
  --pc-radius-lg: 20px;

  /* 阴影 */
  --pc-shadow-glow: 0 4px 20px rgba(16,185,129,0.4);
}
```

### 组件级别定制

每个组件都有独立变量：

```css
/* 按钮 */
--pc-btn-primary-bg: var(--pc-primary);
--pc-btn-primary-color: #ffffff;

/* 输入框 */
--pc-input-focus-border: var(--pc-primary);
--pc-input-focus-shadow: 0 0 0 3px color-mix(...);

/* 卡片 */
--pc-card-bg: var(--pc-bg-elevated);
--pc-card-border: var(--pc-border-color);

/* 进度条 */
--pc-progress-bg: var(--pc-primary);
```

## 组件列表

完整组件覆盖：
Button(含 Ghost/Outline), Input/Textarea/Select,
Checkbox/Radio/Switch, Card, Avatar, Badge, Alert,
Tabs(Pill模式), Navbar, Breadcrumb, Pagination,
Progress(带动画), Spinner/Dots/Skeleton, Table,
Dropdown, Tooltip, Modal, Divider, Empty State

## 图标使用

z-index: 9999 最高层显示。

```html
<svg class="pc-icon"><use href="#pc-icon-name"></use></svg>
```
