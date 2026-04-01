# 严莹个人网站 — 设计规范文档 (Design System)

> 风格关键词：**手绘涂鸦风 (Sketchy/Hand-drawn)** · 便利贴质感 · 学术温暖 · 俏皮专业

---

## 1. 设计理念

整体视觉风格为 **"Notebook Sketch"** — 手绘笔记本风格。通过不规则圆角（wobbly border-radius）、实色偏移阴影、虚线边框和手写体字体，营造出**便利贴 + 手绘草稿**的亲和感，同时保持信息的专业性和可读性。

---

## 2. 色彩系统

### 2.1 核心调色板

| Token | 色值 | 用途 |
|-------|------|------|
| `--bg` | `#FDFBF7` | 页面背景（暖白/米白色） |
| `--fg` | `#2D2D2D` | 主文字色 / 边框色 / 深色实底 |
| `--muted` | `#E5E0D8` | 次要/柔和色（标签底色、分隔线、背景点阵） |
| `--accent` | `#FF4D4D` | 强调色/红色（CTA、高亮、图钉、活跃圆点） |
| `--border` | `#2D2D2D` | 边框色（与 `--fg` 一致） |
| `--blue` | `#2D5DA1` | 辅助蓝色（链接、角色标签、工具标签） |
| `--yellow` | `#FFF9C4` | 便利贴黄色底色（标签背景、高亮卡片） |
| `--white` | `#FFFFFF` | 纯白（卡片背景） |

### 2.2 语义色彩

| 场景 | 颜色 | 说明 |
|------|------|------|
| 主按钮/CTA | `--fg` (#2D2D2D) 底，hover → `--accent` | 深色实底 → 红色高亮 |
| 强调文字 | `--accent` (#FF4D4D) | section 标题中的高亮词 |
| 辅助文字 | `#555` / `#666` / `#777` / `#888` / `#999` | 不同层级的灰色文字 |
| 链接/角色 | `--blue` (#2D5DA1) | 教育学位、工具标签 |
| 标签底色 | `--yellow` (#FFF9C4) | section-label、stat-box、stack-badge |
| Footer | `--fg` 背景 + `--bg` 文字 | 深底反白 |

### 2.3 背景纹理

```css
background-image: radial-gradient(#e5e0d8 1px, transparent 1px);
background-size: 24px 24px;
```
米白底色叠加 **24px 间距的小圆点网格**，模拟手绘笔记本的网格纸质感。

---

## 3. 字体系统

### 3.1 字体栈

| Token | 字体 | 用途 |
|-------|------|------|
| `--font-head` | `'Kalam', cursive` | 标题 / 手写体（英文手写风格） |
| `--font-body` | `'Noto Sans SC', 'Patrick Hand', sans-serif` | 正文 / 中文（思源黑体 + 英文手写备选） |

### 3.2 字号规范

| 元素 | 字号 | 字重 | 字体 |
|------|------|------|------|
| Hero 名字 | `4.2rem` (移动端 `3rem`) | 700 | `--font-head` |
| Section 标题 | `2.6rem` | 700 | `--font-head` |
| Hero 副标题 | `1.25rem` | 400 | `--font-body` |
| Section Label | `0.85rem` | - | `--font-head` |
| Nav Logo | `1.4rem` | 700 | `--font-head` |
| 卡片标题 | `1.05~1.3rem` | 700 | `--font-head` |
| 正文描述 | `0.84~0.95rem` | 400 | `--font-body` |
| 标签/元信息 | `0.7~0.8rem` | 400/500 | `--font-body` |
| Footer 名字 | `2.4rem` | 700 | `--font-head` |

### 3.3 行高

| 场景 | 行高 |
|------|------|
| 标题 | `1.1~1.15` |
| 正文/描述 | `1.5~1.7` |
| 卡片内容 | `1.4~1.6` |

---

## 4. 间距系统

### 4.1 页面布局

| 属性 | 值 |
|------|------|
| 最大内容宽度 | `1000px` |
| Section 上下 padding | `80px` |
| Section 左右 padding | `24px` |
| Hero 最小高度 | `90vh` |

### 4.2 常用间距

| 间距 | 值 | 用途 |
|------|------|------|
| 大间距 | `48px` | Grid gap、Section 标题 margin-bottom |
| 中间距 | `28~32px` | 元素间距、padding |
| 小间距 | `12~20px` | 卡片内边距、标签间距 |
| 微间距 | `4~8px` | 行内元素间距 |

---

## 5. 圆角系统（核心特色）

本站最显著的视觉特色 — **不规则/手绘圆角**：

### 5.1 Wobbly 圆角变量

```css
/* 大面积不规则圆角 */
--radius-wobbly: 255px 15px 225px 15px / 15px 225px 15px 255px;

/* 中等面积不规则圆角 */
--radius-wobbly-md: 30px 8px 28px 8px / 8px 28px 8px 30px;
```

### 5.2 各组件圆角

| 组件 | border-radius | 说明 |
|------|---------------|------|
| Hero Tag / Contact Chip / CTA 按钮 | `255px 15px 225px 15px / 15px 225px 15px 255px` | 大面积 wobbly |
| 卡片（Hero / Edu / Project） | `30px 8px 28px 8px / 8px 28px 8px 30px` | 中等 wobbly |
| Section Label | `4px 16px 4px 16px / 16px 4px 16px 4px` | 小标签 wobbly |
| 工具卡片 | `20px 6px 18px 6px / 6px 18px 6px 20px` | 工具卡 wobbly |
| YouTube 卡片 | `16px 4px 14px 4px / 4px 14px 4px 16px` | 列表卡 wobbly |
| Stat Box | `8px 20px 8px 20px / 20px 8px 20px 8px` | 统计框 wobbly |
| 普通标签/Badge | `20px` / `4px` | 圆角胶囊 / 小标签 |
| 圆点/图钉 | `50%` | 纯圆形 |

---

## 6. 阴影系统

实色偏移阴影（**Hard Shadow**），无模糊，模拟手绘投影效果：

| Token | 值 | 用途 |
|-------|------|------|
| `--shadow` | `4px 4px 0px 0px #2D2D2D` | 默认卡片阴影 |
| `--shadow-lg` | `8px 8px 0px 0px #2D2D2D` | hover 增强阴影 |
| 标签阴影 | `3px 3px 0 #2D2D2D` | 小标签/chip |
| Stat 框阴影 | `2px 2px 0 #2D2D2D` | 统计数据框 |

### 交互阴影动画

```css
/* hover: 阴影缩小 + 位移，模拟"按下"效果 */
:hover {
  transform: translate(2px, 2px);
  box-shadow: 1px 1px 0 var(--border);  /* 或 2px 2px */
}
:active {
  transform: translate(4px, 4px);
  box-shadow: 0 0 0 var(--border);
}
```

---

## 7. 边框系统

| 类型 | 样式 | 用途 |
|------|------|------|
| 卡片边框 | `2~3px solid #2D2D2D` | 所有卡片 |
| 虚线分隔 | `2px dashed #E5E0D8` | Nav 底部、卡片内行分隔 |
| 标签边框 | `1~1.5px solid #2D2D2D` | 小标签、Badge |
| 时间线轴 | `2px dashed #2D2D2D` | 左侧虚线时间轴 |

---

## 8. 装饰元素

### 8.1 倾斜/旋转

几乎所有卡片都有微小旋转角度（`-1.5deg ~ 1.5deg`），模拟便利贴随意摆放效果：

```css
transform: rotate(-0.5deg);  /* 教育卡片 */
transform: rotate(0.5deg);   /* 项目卡片 */
transform: rotate(1.5deg);   /* Hero 右侧卡片 */
transform: rotate(-1deg);    /* Section label */
```

### 8.2 图钉元素

```css
.tack {
  width: 14px; height: 14px;
  background: var(--accent);
  border: 2px solid var(--border);
  border-radius: 50%;
}
```

### 8.3 胶带条（卡片顶部）

```css
.hero-card::before {
  content: '';
  width: 60px; height: 14px;
  background: rgba(180,180,180,0.45);
  border-radius: 3px;
  border: 1px solid rgba(0,0,0,0.12);
}
```

### 8.4 波浪线分隔

SVG 虚线波浪分隔符，stroke 颜色 `#E5E0D8`，`stroke-dasharray: 8,4`。

### 8.5 Emoji 图标

全站使用原生 Emoji 作为图标系统（✏️ 📱 📧 🎓 👋 📚 🚀 🛠️ 📺 🌙 等），不依赖外部图标库。

---

## 9. 动效规范

### 9.1 过渡时间

| 类型 | 时间 | 缓动 |
|------|------|------|
| 颜色/透明度 | `0.15s` | ease (默认) |
| 位移/缩放 | `0.1~0.15s` | ease (默认) |
| 滚动淡入 | `0.55s` | ease |

### 9.2 滚动淡入动画

```css
.fade-in {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.55s ease, transform 0.55s ease;
}
.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}
```
使用 `IntersectionObserver` (threshold: 0.08) 触发，元素进入视口 8% 时激活。

### 9.3 卡片 Hover 效果

- **位移+缩放**：`transform: rotate(-1deg) scale(1.02)` + 增大阴影
- **按下效果**：`translate(2px,2px)` + 缩小阴影
- **导航下划线**：宽度从 0 → 100% 展开，颜色 `--accent`
- **Footer 链接**：hover 加删除线（`text-decoration: line-through`）

---

## 10. 页面结构 & 组件

### 10.1 整体页面结构

```
Nav（粘性顶部导航）
  └─ Logo + 导航链接

Hero Section（首屏，90vh）
  ├─ 左侧：标签 + 名字 + 副标题 + 联系方式 + CTA
  └─ 右侧：个人概要卡片（带胶带条装饰）

波浪线分隔符

About Section（关于我）
  ├─ 左列：教育背景（edu-card × 2）
  └─ 右列：实习经历时间线（timeline）

Projects Section（AI 作品）
  └─ 三列项目卡片网格

Tools Section（AI 工具箱）
  └─ 四列工具卡片网格（8个工具）

YouTube Section（学习足迹）
  └─ 两列：技术向 + 产品向视频卡片

Footer（深色页脚）
```

### 10.2 核心组件清单

| 组件 | 说明 | 特征 |
|------|------|------|
| `nav` | 粘性顶部导航 | Logo + 链接列表，虚线底边 |
| `section-label` | Section 小标签 | 黄底 + 手写体 + 旋转 |
| `section-title` | Section 大标题 | 手写体，span 内文字高亮红色 |
| `hero-tag` | Hero 标签 | 红底白字，wobbly 圆角 |
| `contact-chip` | 联系信息芯片 | 白底 + 阴影 + wobbly 圆角 |
| `hero-cta` | 主 CTA 按钮 | 深色底 + 大 wobbly 圆角 |
| `hero-card` | Hero 概要卡片 | 胶带条装饰 + 信息行 + 统计格 |
| `edu-card` | 教育背景卡片 | wobbly 圆角 + 微旋转 |
| `timeline` | 时间线 | 虚线轴 + 圆点 + 内容块 |
| `project-card` | 项目卡片 | 顶部标签 + emoji + 技术栈 + 箭头 |
| `tool-card` | 工具卡片 | 顶部标签 + emoji + 频率圆点 |
| `yt-card` | YouTube 视频卡片 | 缩略图 + 播放覆盖层 + 元信息 |
| `footer` | 页脚 | 深色反白 + 链接 |

---

## 11. 栅格/网格布局

| 区域 | 桌面端 | 移动端 (≤768px) |
|------|--------|----------------|
| Hero | `1fr 1fr` 两列 | 单列 |
| About | `1fr 1fr` 两列 | 单列 |
| Projects | `repeat(3, 1fr)` 三列 | 单列 |
| Tools | `repeat(4, 1fr)` 四列 | `repeat(2, 1fr)` 两列 |
| YouTube | `1fr 1fr` 两列 | 单列 |

Grid gap 统一为 `20~48px`，具体看模块。

---

## 12. 响应式断点

| 断点 | 调整内容 |
|------|---------|
| `≤ 768px` | Hero 名字 3rem，所有多列→单列/两列，Nav padding 缩小，链接间距缩小 |
| `≥ 768px` | 显示装饰箭头元素 |

---

## 13. 设计规则速查

1. **边框必加**：所有卡片都有 `2~3px solid #2D2D2D` 边框
2. **阴影无模糊**：纯偏移阴影 `Npx Npx 0 #2D2D2D`
3. **圆角不规则**：使用 wobbly border-radius 模拟手绘
4. **微旋转**：卡片带 `-1.5~1.5deg` 旋转
5. **Emoji 做图标**：不引入图标库
6. **手写字体做标题**：Kalam 字体用于所有标题
7. **黄色=高亮**：`#FFF9C4` 用于标签、强调
8. **红色=行动**：`#FF4D4D` 用于 CTA、强调文字
9. **点阵底纹**：米白背景 + 24px 间隔灰色圆点
10. **虚线分隔**：用 dashed 而非 solid 做分隔线
