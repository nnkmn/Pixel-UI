# Pixel UI Kit

> 像素风格 UI/UX 组件库 + Icon 图标库 | 三版本并行 | 纯 CSS 零依赖

---

## 版本一览

| 版本 | 目录 | 前缀 | 风格 | 适合场景 |
|------|------|------|------|----------|
| **渐变色版** | `gradient/` | `--pg-` / `.pg-` | 像素+渐变融合，柔和圆角，发光阴影 | 营销页、Dashboard、展示型项目 |
| **极简风版** | `minimal/` | `--pm-` / `.pm-` | 硬像素风，方正边框，方块阴影，0 圆角 | 工具应用、管理后台、复古游戏风 |
| **自定义版** | `custom/` | `--pc-` / `.pc-` | 全 CSS 变量驱动，颜色随意定制 | 品牌定制、多主题切换 |

---

## 快速开始

每个版本用法一样：引入图标 sprite + 引入样式表 + 使用组件。

### 渐变色版 (gradient)

```html
<!-- 1. 引入图标 Sprite（内联到 HTML） -->
<svg xmlns="http://www.w3.org/2000/svg" style="display:none">
  <symbol id="pg-icon-home" viewBox="0 0 24 24"><path fill="currentColor" d="M12 3L2 12h3v8h6v-6h2v6h6v-8h3L12 3z"/></symbol>
  <!-- ... 更多图标 ... -->
</svg>

<!-- 2. 引入样式 -->
<link rel="stylesheet" href="gradient/pixel-gradient.css">

<!-- 3. 使用组件 -->
<button class="pg-btn pg-btn-primary">按钮</button>
<button class="pg-btn pg-btn-icon pg-btn-primary">
  <svg class="pg-icon"><use href="#pg-icon-search"></use></svg>
</button>

<!-- 4. 暗色主题（可选） -->
<body data-theme="dark">
```

### 极简风版 (minimal)

```html
<link rel="stylesheet" href="minimal/pixel-minimal.css">

<button class="pm-btn pm-btn-primary">硬像素按钮</button>
<input class="pm-input" placeholder="输入..." />
```

### 自定义版 (custom)

```html
<link rel="stylesheet" href="custom/pixel-custom.css">

<button class="pc-btn pc-btn-primary">可定制按钮</button>
```

---

## 特性（三版本通用）

- **纯 CSS 实现** — 零 JS 依赖
- **CSS 变量驱动** — 改几个变量换整套皮肤
- **亮/暗主题切换** — `data-theme="dark"` 一行搞定
- **Icon 最高层级** — z-index: 9999，永远不被遮挡
- **8px 网格系统** — 间距遵循 8px 倍数
- **WCAG AA 可访问性** — 焦点样式、语义化标签、减少动效支持
- **60+ SVG 图标** — 内联 sprite，无需外部请求

---

## 文件结构

```
pixel-ui-kit/
├── .gitignore
├── LICENSE
├── README.md                  ← 总文档（你在这里）
│
├── gradient/                  # ★ 渐变色版
│   ├── pixel-gradient.css     #   主样式表
│   ├── pixel-icons.svg        #   图标库（独立文件）
│   ├── index.html             #   组件演示页 ← 点这个看效果
│   └── README.md              #   子文档
│
├── minimal/                   # ★ 极简风版
│   ├── pixel-minimal.css      #   主样式表
│   ├── pixel-icons.svg        #   图标库
│   ├── index.html             #   组件演示页
│   └── README.md              #   子文档
│
└── custom/                    # ★ 自定义版
    ├── pixel-custom.css       #   主样式表（全变量驱动）
    ├── pixel-icons.svg        #   图标库
    ├── index.html             #   演示页 + 颜色定制器
    └── README.md              #   子文档
```

---

## 各版本详细说明

---

### 🎨 渐变色版 (Gradient) — `gradient/`

**设计风格**

像素风与渐变色融合。按钮带渐变背景和发光阴影，圆角柔和（6~24px），整体现代感强。

**核心特点**
- 渐变按钮（`--pg-gradient-primary`）
- 发光阴影效果（`box-shadow` + 多层叠加）
- 柔和圆角（`--pg-radius-sm: 4px` ~ `--pg-radius-xl: 24px`）
- Inter 字体为主

**CSS 变量示例**

```css
:root {
  --pg-primary-500: #667eea;         /* 主色 */
  --pg-secondary-500: #764ba2;       /* 辅助色 */
  --pg-gradient-primary: linear-gradient(135deg, #667eea, #764ba2);  /* 渐变 */
  --pg-radius-md: 12px;
  --pg-font-sans: 'Inter', sans-serif;
}
```

**组件列表**

| 分类 | 组件 |
|------|------|
| 基础 | Button (Primary/Secondary/Ghost/Outline), Input, Textarea, Select |
| 表单 | Checkbox, Radio, Switch |
| 布局 | Card (普通/渐变边框), Avatar, Badge |
| 反馈 | Alert (Info/Success/Warning/Error), Progress, Spinner/Dots/Skeleton |
| 导航 | Navbar, Tabs (默认/Pill 胶囊), Breadcrumb, Pagination |
| 数据 | Table |
| 交互 | Dropdown, Tooltip, Modal |
| 工具 | Divider, Empty State |

**在线预览**: [https://nnkmn.github.io/Pixel-UI/gradient/index.html](https://nnkmn.github.io/Pixel-UI/gradient/index.html)

---

### 🔲 极简风版 (Minimal) — `minimal/`

**设计风格**

硬核像素风。边框方正，阴影是偏移硬阴影（非模糊），圆角为 0 或极小，过渡动画用 `step-end` 模拟复古游戏感。

**核心特点**
- 圆角为零或接近零（`--pm-radius-sm: 0px`）
- 方块硬阴影（`4px 4px 0 #000`，无 blur）
- `transition-timing-function: step-end` 复古动画感
- 默认使用等宽/像素字体

```css
:root {
  --pm-primary-500: #4061ff;          /* 主色 */
  --pm-border-color: #000;            /* 边框色 */
  --pm-shadow-md: 4px 4px 0 #000;     /* 硬阴影 */
  --pm-font-mono: 'Press Start 2P', monospace;
}
```

**组件覆盖**

全部组件与 gradient 版对应实现：
Button, Input, Checkbox/Radio/Switch, Card, Avatar, Badge,
Alert, Tabs, Navbar, Breadcrumb, Pagination, Progress,
Spinner/Skeleton, Table, Dropdown, Tooltip, Modal, Divider, Empty State

**在线预览**: [https://nnkmn.github.io/Pixel-UI/minimal/index.html](https://nnkmn.github.io/Pixel-UI/minimal/index.html)

---

### 🎛️ 自定义版 (Custom) — `custom/`

**设计风格**

颜色完全通过 CSS 变量驱动。改几个值就能换整套皮肤，适合品牌定制和多主题场景。

**核心特点**
- 所有颜色都是顶层变量，一处修改全局生效
- 每个组件有独立变量支持精细控制
- 演示页自带**颜色选择器**，实时调色预览

#### 快速换主色

```css
:root { --pc-primary: #ff6b35; }  /* 改一行就换色系 */
```

#### 换整套配色方案

```css
:root {
  /* 功能色 */
  --pc-success: #22c55e;
  --pc-warning: #f59e0b;
  --pc-error: #ef4444;
  --pc-info: #0ea5e9;

  /* 背景 & 文字 */
  --pc-bg-primary: #ffffff;
  --pc-bg-secondary: #f8fafc;
  --pc-text-primary: #0f172a;

  /* 圆角 & 阴影 */
  --pc-radius-md: 12px;
  --pc-shadow-glow: 0 4px 20px rgba(16,185,129,0.4);
}
```

#### 组件级别变量

```css
/* 按钮 */      --pc-btn-primary-bg: var(--pc-primary);
/* 输入框 */    --pc-input-focus-border: var(--pc-primary);
/* 卡片 */      --pc-card-bg: var(--pc-bg-elevated);
/* 进度条 */    --pc-progress-bg: var(--pc-primary);
```

**在线预览**: [https://nnkmn.github.io/Pixel-UI/custom/index.html](https://nnkmn.github.io/Pixel-UI/custom/index.html) （含颜色定制器）

---

## 图标库

三个版本共用同一套 60+ 图标，仅前缀不同：

```html
<!-- gradient -->
<svg class="pg-icon"><use href="#pg-icon-search"></use></svg>

<!-- minimal -->
<svg class="pm-icon"><use href="#pm-icon-search"></use></svg>

<!-- custom -->
<svg class="pc-icon"><use href="#pc-icon-search"></use></svg>
```

**可用图标**（60 个）：

home, user, settings, search, menu, close, plus, check, info, warning, error, success,
file, folder, download, upload, eye, lock, star, heart, message, bell, edit, trash,
copy, refresh, save, share, phone, mail, calendar, clock, location, play, pause,
bar-chart, line-chart, database, server, image,
arrow-right/down/left/up, chevron-left/right/up/down, external-link, filter, logout,
github, moon, sun, zoom-in/out, grid, list, inbox

**所有图标 z-index 强制为 9999**，确保不被其他元素遮挡。

尺寸：`.icon` (16×16)、`.icon-sm` (14×14)、`.icon-lg` (24×24)、`.icon-xl` (32×32)

---

## 浏览器支持

- Chrome / Edge 88+
- Firefox 78+
- Safari 14+

---

## License

[MIT](./LICENSE)
