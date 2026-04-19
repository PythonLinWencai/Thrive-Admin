# Thrive-Admin

> Vue.js 管理后台界面

## 项目简介

Thrive-Admin 是 Thrive 博客管理系统的管理后台，基于 Vue 3 + TypeScript 开发，提供直观的管理界面，支持文章管理、用户管理、评论审核、系统配置等功能。

## 技术栈

- **框架**: Vue 3
- **语言**: TypeScript
- **状态管理**: Pinia
- **UI 组件**: Element Plus
- **样式**: SCSS
- **构建工具**: Vite
- **图表**: ECharts

## 环境要求

- Node.js 16+
- npm 7+

## 快速开始

### 1. 克隆项目

```bash
git clone https://github.com/LiuYuYang01/Thrive-Admin.git
cd Thrive-Admin
```

### 2. 安装依赖

```bash
npm install
```

### 3. 配置后端地址

编辑 `src/utils/Request.ts` 中的 baseURL：

```typescript
private static readonly baseURL: string = "http://127.0.0.1:5000/";
```

### 4. 启动开发服务器

```bash
npm run dev
```

应用将在 `http://127.0.0.1:6173` 启动。

## 构建生产版本

```bash
npm run build
```

## 项目结构

```
Thrive-Admin/
├── src/
│   ├── api/              # API 接口
│   ├── components/       # 公共组件
│   ├── router/           # 路由配置
│   ├── stores/           # Pinia 状态管理
│   ├── styles/           # 样式文件
│   ├── types/            # TypeScript 类型定义
│   ├── utils/            # 工具函数
│   ├── views/            # 页面组件
│   ├── App.vue           # 根组件
│   └── main.ts           # 入口文件
├── public/               # 静态资源
├── index.html            # HTML 模板
├── vite.config.ts        # Vite 配置
├── tsconfig.json         # TypeScript 配置
└── package.json          # 项目配置
```

## 主要功能

- ✅ 用户登录认证
- ✅ 文章管理 (发布、编辑、删除)
- ✅ 分类管理
- ✅ 评论审核
- ✅ 用户管理
- ✅ 系统配置
- ✅ 数据统计图表

## 开发说明

### 代码规范

- 使用 TypeScript 进行类型检查
- 遵循 Vue 3 Composition API
- 使用 ESLint 进行代码检查

### 添加新页面

1. 在 `src/views/` 下创建页面组件
2. 在 `src/router/index.ts` 中添加路由配置
3. 如需要，在 `src/api/` 中添加 API 接口

### 环境变量

创建 `.env` 文件：

```env
VITE_API_BASE_URL=http://127.0.0.1:5000/
VITE_APP_TITLE=Thrive Admin
```

## 部署

### 使用 Nginx

```nginx
server {
    listen 80;
    server_name admin.yourdomain.com;
    root /path/to/dist;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }

    location /api {
        proxy_pass http://127.0.0.1:5000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```

### 使用 Docker

```dockerfile
FROM node:16-alpine as build
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf
```

## 浏览器支持

- Chrome 70+
- Firefox 70+
- Safari 12+
- Edge 79+

## 贡献指南

1. Fork 项目
2. 创建功能分支: `git checkout -b feature/AmazingFeature`
3. 提交更改: `git commit -m 'Add some AmazingFeature'`
4. 推送分支: `git push origin feature/AmazingFeature`
5. 发起 Pull Request

## 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 联系方式

- 项目主页: https://github.com/LiuYuYang01/Thrive-Admin
- 邮箱: liuyuyang1024@yeah.net

---

**开源不易，如果这个项目对你有帮助，请给个 Star ⭐ 支持一下！**

环境：Nodejs16、18

```
npm i
npm run dev
```



后端

Python3.9、10

```python
# 创建虚拟环境
virtualenv venv

# 进入虚拟环境
venv/Scripts/activate

# 在虚拟环境中安装对应的依赖
pip3 install -r requirements.txt

# 在虚拟环境中运行项目，python app.py的相对路径
python C:\Thrive\Thrive_API-2.0\app.py
```


🏷️ **开源地址：**

前端：[LiuYuYang01/Thrive-Blog (github.com)](https://github.com/LiuYuYang01/Thrive-Blog)

控制端：[LiuYuYang01/Thrive-Admin (github.com)](https://github.com/LiuYuYang01/Thrive-Admin)

后端：[LiuYuYang01/Thrive-Server (github.com)](https://github.com/LiuYuYang01/Thrive-Server)



这个项目从前端到后端都是我从0到1敲出来的，所以刚开始一定会有很多隐藏的 `BUG`，希望大家能够及时在 `GitHub` 反馈，这样我也好加以改正，不断改善，成为最佳！当然如果大家能够提交 `PR` 那再好不过了
