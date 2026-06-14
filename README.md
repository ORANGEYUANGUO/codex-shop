# 烟火厨房 · 地道本味

一个专注于美食体验的餐厅品牌展示页面，使用 Vue 3 + Vite 构建的单页应用。

## 技术栈

- **框架** Vue 3（Composition API + `<script setup>`）
- **构建工具** Vite 6
- **样式** 原生 CSS
- **语言** JavaScript

## 本地开发

```bash
# 安装依赖
npm install

# 启动开发服务器
npm run dev
# 默认访问 http://localhost:5173

# 构建生产版本
npm run build

# 预览构建结果
npm run preview
```

## 项目结构

```
codex-shop/
├── index.html               # 入口 HTML
├── package.json
├── vite.config.js           # Vite 配置
├── styles.css               # 全局样式
├── public/                  # 静态资源
└── src/
    ├── App.vue              # 根组件，组合所有页面区块
    ├── main.js              # Vue 应用入口
    ├── assets/
    │   └── styles.css       # 组件级样式
    └── components/
        ├── NavBar.vue
        ├── HeroSection.vue
        ├── FeaturesSection.vue
        ├── MenuSection.vue
        ├── AboutSection.vue
        ├── TestimonialsSection.vue
        ├── ReservationSection.vue
        └── FooterSection.vue
```

## 页面区块

| 区块 | 说明 |
|------|------|
| **导航栏** | 响应式顶部导航，含锚点跳转 |
| **首屏** | 品牌标语与行动号召按钮 |
| **特色** | 核心卖点展示 |
| **菜单** | 招牌菜品推荐卡片 |
| **关于** | 品牌故事与理念 |
| **评价** | 顾客好评展示 |
| **预订** | 在线预约入口 |
| **页脚** | 联系信息与版权 |

## 部署

构建后 `dist/` 目录可直接部署到任何静态托管服务（如 Nginx、Vercel、Netlify 等）。

## License

MIT
