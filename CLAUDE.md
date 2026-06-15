# CLAUDE.md

## 项目概述
codex-shop 是一个基于 Vite + Vue 3 的餐厅单页展示网站（Landing Page），名为「烟火厨房」。页面由 8 个独立区块组件拼接而成，采用纯 CSS 响应式设计。

## 关键约定
- **框架**: Vue 3 Composition API + `<script setup>` 语法，无 `<template>` 外的 `setup()` 调用
- **数据**: 所有业务数据（菜单、评价、特色等）硬编码为组件内常量数组，不使用外部 API
- **样式**: 全局 CSS 集中在 `src/assets/styles.css`，使用 CSS Variables 定义设计系统
- **路由**: 单页应用，无 Vue Router，通过锚点 `#menu`、`#about` 等实现页面内导航
- **构建**: Vite 6.x，开发端口 5173，host 绑定 `0.0.0.0`

## 目录结构
```
src/
├── main.js                  # 挂载入口
├── App.vue                  # 根组件（8 个子组件顺序排列）
├── assets/styles.css        # 全局样式（所有 CSS 集中在此）
└── components/
    ├── NavBar.vue                   # 顶部固定导航
    ├── HeroSection.vue              # 首屏 Banner
    ├── FeaturesSection.vue          # 特色卡片
    ├── MenuSection.vue              # 菜单推荐
    ├── AboutSection.vue             # 品牌故事
    ├── TestimonialsSection.vue      # 用户评价
    ├── ReservationSection.vue       # 在线预订表单
    └── FooterSection.vue            # 页脚信息
```

## 常见任务
- **修改文案**: 直接在对应组件的 `<script setup>` 常量数组中编辑文本
- **调整配色**: 修改 `src/assets/styles.css` 中的 `:root` CSS Variables
- **新增区块**: 创建 `src/components/xxxSection.vue`，在 `App.vue` 中 import 并加入模板
- **添加路由**: 当前为锚点导航，如需改为 Vue Router 请先更新 plan.md 中的架构决策

## 已知问题（详见 docs/plan.md）
- 预订表单无后端对接，仅弹出 alert
- 手机号无格式校验
- 移动端无汉堡菜单
- Footer 图标拼写错误（`🕲` → `🕐`）
- 菜单 emoji 与内容不完全匹配
