# Pixel UI Kit

> 像素风格 UI/UX 组件库 + Icon 图标库 | 三版本并行

---

## 这是什么

一套像素风格的 UI 组件库，提供 **三个独立版本**，每个版本完全自包含，互不影响。

| 版本 | 目录 | 风格 | 适合场景 |
|------|------|------|----------|
| **渐变色版** | `gradient/` | 像素+渐变融合，圆角柔和，发光阴影 | 营销页、Dashboard、展示型项目 |
| **极简风版** | `minimal/` | 硬像素风，方正边框，方块阴影，0圆角 | 工具应用、管理后台、复古游戏风 |
| **自定义版** | `custom/` | 全变量驱动，颜色随意定制 | 品牌定制、多主题切换 |

## 快速开始

每个版本的用法都一样简单：

```html
<!-- 引入 CSS -->
<link rel="stylesheet" href="gradient/pixel-gradient.css">
<!-- 或 -->
<link rel="stylesheet" href="minimal/pixel-minimal.css">
<!-- 或 -->
<link rel="stylesheet" href="custom/pixel-custom.css">

<!-- 引入图标 (SVG Sprite) -->
<!-- 已在 CSS 中通过 @import 或 HTML 中直接引入 -->

<!-- 使用组件 -->
<button class="pg-btn pg-btn--primary">按钮</button>
<button class="pm-btn pm-btn--primary">按钮</button>
<button class="pc-btn pc-btn--primary">按钮</button>
```

## 特性

- **纯 CSS 实现** — 零依赖，无需 JS 框架
- **CSS 变量驱动** — 改几个变量就能换整套皮肤（尤其是 custom 版）
- **亮/暗主题** — 通过 `data-theme="dark"` 切换
- **Icon 图标最高层级** — z-index: 9999，永远不被遮挡
- **8px 网格系统** — 间距遵循 8px 倍数
- **WCAG AA 可访问性** — 焦点样式、语义化标签、减少动效支持

## 文件结构

```
pixel-ui-kit/
├── README.md              ← 你在这里
├── TASKS.md              ← 开发任务文档
├── gradient/             ← 渐变色版
│   ├── README.md
│   ├── pixel-gradient.css
│   ├── pixel-icons.svg
│   └── index.html        ← 在线预览这个
├── minimal/              ← 极简风版
│   ├── README.md
│   ├── pixel-minimal.css
│   ├── pixel-icons.svg
│   └── index.html        ← 在线预览这个
└── custom/               ← 自定义版
    ├── README.md
    ├── pixel-custom.css
    ├── pixel-icons.svg
    └── index.html        ← 在线预览这个
```

## 浏览器支持

- Chrome 88+
- Firefox 78+
- Safari 14+
- Edge 88+

## 开发状态

[查看 TASKS.md](./TASKS.md) 了解当前开发进度。

---

_Made by EccenTri | 重庆 | 2026_
