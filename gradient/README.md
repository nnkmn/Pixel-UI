# Pixel Gradient UI — 渐变色版

> 像素风 + 渐变色融合的组件库 | v3.0.0

## 设计风格

- 渐变按钮、发光阴影
- 圆角柔和（6px ~ 24px）
- 现代感强，适合 Dashboard / 营销页面
- 亮/暗主题切换支持

## 文件说明

| 文件 | 说明 |
|------|------|
| `pixel-gradient.css` | 主样式表 |
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
<link rel="stylesheet" href="pixel-gradient.css">

<!-- 使用 -->
<button class="pg-btn pg-btn-primary">
  <svg class="pg-icon"><use href="#pg-icon-home"></use></svg>
  按钮
</button>
```

## CSS 变量前缀

所有变量使用 `--pg-` 前缀，class 使用 `.pg-` 前缀。

### 可自定义变量示例

```css
:root {
  --pg-primary-500: #667eea;        /* 主色 */
  --pg-radius-md: 12px;             /* 圆角 */
  --pg-font-sans: 'Inter', sans-serif;
}
```

## 组件列表

- **基础**: Button, Input, Textarea, Select
- **表单**: Checkbox, Radio, Switch
- **布局**: Card, Avatar, Badge
- **反馈**: Alert, Progress, Loading/Spinner/Skeleton
- **导航**: Navbar, Tabs, Breadcrumb, Pagination
- **数据**: Table
- **交互**: Dropdown, Tooltip, Modal
- **工具**: Divider, Empty State

## 图标使用

所有图标 z-index 强制为 9999，确保显示在所有图层之上。

```html
<svg class="pg-icon"><use href="#pg-icon-name"></use></svg>
<svg class="pg-icon pg-icon-lg"><use href="#pg-icon-search"></use></svg>
```

## 主题切换

```html
<!-- 亮色 -->
<body data-theme="light">

<!-- 暗色 -->
<body data-theme="dark">
```
