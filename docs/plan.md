---

## 项目概述

codex-shop 是一个基于 **Vite + Vue 3** 的餐厅单页展示网站（Landing Page），名为「烟火厨房」。页面包含导航栏、首屏 Banner、特色介绍、菜单推荐、关于我们、食客评价、在线预订和页脚共 8 个区块，采用纯 CSS 响应式设计，无第三方 UI 框架依赖。

---

## 技术栈

| 层级 | 技术 |
|------|------|
| 构建工具 | Vite 6.x |
| 前端框架 | Vue 3.5+（Composition API, `<script setup>`） |
| 样式 | 原生 CSS（CSS Variables, clamp, Grid, Flexbox） |
| 部署 | SPA 静态托管（Nginx / Vercel / Netlify 等） |

---

## 项目结构

```
codex-shop/
├── index.html              # SPA 入口 HTML
├── package.json            # 依赖 & 脚本
├── vite.config.js          # Vite 配置（端口 5173, host 0.0.0.0）
├── src/
│   ├── main.js             # Vue 应用挂载
│   ├── App.vue             # 根组件（8 个子组件拼接）
│   ├── assets/
│   │   └── styles.css      # 全局样式（所有 CSS 集中在此）
│   └── components/
│       ├── NavBar.vue              # 顶部固定导航
│       ├── HeroSection.vue         # 首屏全屏 Banner
│       ├── FeaturesSection.vue     # 四大特色卡片
│       ├── MenuSection.vue         # 本季菜单推荐（3 道菜）
│       ├── AboutSection.vue        # 品牌故事 + 统计数据
│       ├── TestimonialsSection.vue # 用户评价（3 条）
│       ├── ReservationSection.vue  # 在线预订表单
│       └── FooterSection.vue       # 页脚信息（地址/营业/联系）
```

---

## 当前状态

- **版本**: v1.0.0
- **状态**: 前端页面已搭建完成，数据均为硬编码常量
- **已知问题**: 见下方待办

---

## 待办事项（按优先级排序）

### 🔴 高优先级

1. **预订表单对接后端**
   - 文件: `src/components/ReservationSection.vue`
   - 当前 `handleReserve()` 仅弹出 alert，数据丢失
   - 方案: 接入 API（如 Supabase / Firebase / 自有后端），添加 loading 状态和成功/失败反馈

2. **手机号格式校验**
   - 文件: `src/components/ReservationSection.vue`
   - `type="tel"` 不提供强校验
   - 方案: 添加正则校验（中国大陆 11 位手机号），或引入 `vee-validate` / `async-validator`

### 🟡 中优先级

3. **移动端汉堡菜单**
   - 文件: `src/components/NavBar.vue` + `styles.css`
   - 当前 `@media (max-width: 768px)` 直接隐藏 `.nav-links`，无替代方案
   - 方案: 添加汉堡按钮 + 展开/收起动画

4. **导航高亮当前 Section**
   - 文件: `src/components/NavBar.vue`
   - 方案: 使用 IntersectionObserver 监听各 section，高亮对应导航链接

5. **修复 Footer 图标**
   - 文件: `src/components/FooterSection.vue:9`
   - `🕲`（Ankh）应为时间图标 `🕐`

6. **修复菜单 emoji 匹配**
   - 文件: `src/components/MenuSection.vue`
   - 牛排骨 `🍅` → `🥩`；烤鱼 `🍳` → `🐟`

### 🟢 低优先级

7. **添加 aria 无障碍属性**
   - 所有 `<a>`, `<input>`, `<button>` 补充 `aria-label`

8. **优化 key 稳定性**
   - `v-for` 的 key 建议使用 `index` 或添加唯一 ID

9. **清理空 script 块**
   - `HeroSection.vue` 的 `<script setup>` 为空，可删除

10. **样式模块化**
    - 当前所有 CSS 集中在 `styles.css`，可扩展时按组件拆分

---

## 开发命令

```bash
npm run dev      # 启动开发服务器（localhost:5173）
npm run build    # 生产构建（输出到 dist/）
npm run preview  # 预览生产构建
```

## 设计系统

| 变量 | 色值 | 用途 |
|------|------|------|
| `--warm` | `#1a1208` | 深色背景 |
| `--cream` | `#faf6f0` | 浅色背景 |
| `--gold` | `#c8a45a` | 强调文字、标签 |
| `--red` | `#a63d2f` | 按钮、价格、hover |
| `--charcoal` | `#2c2c2c` | 正文文字 |
| `--muted` | `#6b6560` | 辅助说明文字 |
