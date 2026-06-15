# AGENTS.md — 项目上下文

## 我是谁

我叫郭远，很懒，喜欢新技术。

---

## 项目概览

| 属性 | 值 |
|------|------|
| 项目名称 | codex-shop |
| 项目类型 | 餐厅展示型单页网站（纯前端，无后端） |
| 品牌名称 | 烟火厨房 |
| 定位 | 中高端私房菜/家常菜，强调地道本味 |
| 起始年份 | 2006 |
| 技术栈 | Vue 3.5 + Vite 6.3 + 纯 CSS |

---

## 技术细节

- **框架**: Vue 3（Composition API，`<script setup>` 语法）
- **构建工具**: Vite 6.3，插件 `@vitejs/plugin-vue`
- **开发服务器**: 端口 5173，host 0.0.0.0
- **入口文件**: `index.html` → `src/main.js` → `src/App.vue`
- **样式**: 手写 CSS，无 UI 框架，全局样式位于 `src/assets/styles.css`
- **包管理**: npm（`package-lock.json`）
- **输出目录**: `dist/`

---

## 视觉设计规范

### 色彩系统（CSS 变量）

| 变量 | 色值 | 用途 |
|------|------|------|
| `--warm` | `#1a1208` | 深色背景（预留位、深色板块） |
| `--cream` | `#faf6f0` | 页面底色 |
| `--gold` | `#c8a45a` | 强调色（标签、星级、Logo） |
| `--red` | `#a63d2f` | 主按钮、价格（悬停变 `#8a3326`） |
| `--charcoal` | `#2c2c2c` | 正文文字 |
| `--muted` | `#6b6560` | 辅助说明文字 |

### 字体

`PingFang SC` / `Noto Sans SC` / `Microsoft YaHei`，无衬线。

### 风格关键词

暖色调、木质质感、简洁克制、中式雅致、留白、卡片圆角 8px。

---

## 页面结构（从上到下）

每个 section 都是一个独立的 Vue 组件：

| 顺序 | 组件 | 文件 | 说明 |
|------|------|------|------|
| 1 | NavBar | `src/components/NavBar.vue` | 固定顶部导航，品牌名 + 锚点链接（特色/菜单/关于/评价）+ "立即预订" 红色按钮 |
| 2 | HeroSection | `src/components/HeroSection.vue` | 首屏全屏，标语"用一道菜，讲一个家的故事"，徽章"始于 2006 · 匠心烹饪"，两个 CTA 按钮 |
| 3 | FeaturesSection | `src/components/FeaturesSection.vue` | 四格特色卡片：当日鲜采、主厨匠心、雅致空间、精选酒单 |
| 4 | MenuSection | `src/components/MenuSection.vue` | 三张人气菜品卡片：慢炖牛排骨(¥168)、时令沙拉·和牛塔塔(¥128)、炭烤青花鱼(¥98) |
| 5 | AboutSection | `src/components/AboutSection.vue` | 左图右文布局，品牌故事 + 三项数据（8+年/50+道菜/4.9分） |
| 6 | TestimonialsSection | `src/components/TestimonialsSection.vue` | 三栏用户评价：林先生(常客)、王女士(家庭聚餐)、张先生(商务宴请) |
| 7 | ReservationSection | `src/components/ReservationSection.vue` | 预订表单（姓名/电话/日期/人数），纯前端 alert 确认，无后端提交 |
| 8 | FooterSection | `src/components/FooterSection.vue` | 三栏页脚：地址（北京朝阳建国路88号SOHO现代城B座11层）、营业时间、联系方式（电话010-8888-6666，微信YHKitchen） |

---

## 项目约束与约定

- 所有中文文案统一使用 UTF-8 编码。
- 组件之间通过锚点链接 (`#features`, `#menu`, `#about`, `#reviews`, `#reserve`) 实现单页滚动。
- `scroll-behavior: smooth` 全局开启平滑滚动。
- 导航栏 `z-index: 100`，毛玻璃背景 `backdrop-filter: blur(12px)`。
- 响应式断点：`768px`（移动端隐藏导航链接，About 区域改为单列）。
- 没有路由、没有状态管理、没有 API 调用——纯静态展示站。
- `.gitignore` 排除 `node_modules/`、`dist/`、`.env.local`、IDE 配置、OS 临时文件、`.vite/` 缓存。

---

## 开发命令

```bash
npm run dev       # 启动开发服务器（localhost:5173）
npm run build     # 生产构建到 dist/
npm run preview   # 本地预览生产构建
```

---

## 最近更新

- 2026-06-15: Codex 扫描全项目并生成此 AGENTS.md，便于后续 AI 协作上下文不丢失。
