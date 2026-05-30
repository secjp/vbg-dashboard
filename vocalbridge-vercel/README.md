# VocalBridge Global — Vercel Deployment

## 部署步骤 / Pasos de despliegue

### 方法一：拖拽部署（最快，1分钟）

1. 打开 https://vercel.com → 登录
2. 点击 **"Add New Project"** → **"Deploy without a repository"**  
   或直接访问：https://vercel.com/new
3. 将整个 `vocalbridge-vercel` 文件夹**拖入**上传区
4. 点击 **Deploy** → 等待30秒 → 获得你的URL ✅

---

### 方法二：GitHub + Vercel（推荐长期维护）

1. 将此文件夹上传到 GitHub 仓库
2. 打开 https://vercel.com → Import Git Repository
3. 选择你的仓库 → Deploy
4. 之后每次 push 代码自动更新 ✅

---

## 文件结构

```
vocalbridge-vercel/
├── public/
│   ├── index.html      ← 首页 + 导航
│   └── dashboard.html  ← 系统操作面板（matching系统）
├── vercel.json         ← 路由配置
├── package.json
└── README.md
```

## 路由

| URL | 页面 |
|-----|------|
| `/` | 首页（导航 + Hero + Dashboard预览）|
| `/dashboard` | 完整操作系统（KPI + Matching系统）|

## 接入真实数据（下一步）

在 `dashboard.html` 的 CONFIG 区块替换：
```js
SUPABASE_URL:      'https://你的项目.supabase.co'
SUPABASE_ANON_KEY: '你的anon key'
EMAILJS_SERVICE_ID:  'service_xxx'
EMAILJS_TEMPLATE_ID: 'template_xxx'
EMAILJS_PUBLIC_KEY:  'xxx'
NOTIFY_EMAIL: 'ops@vocalbridge.com'
```

## 测试 Matching 系统

在 `/dashboard` 页面，切换到"sistema de matching"标签，
输入以下测试ID：
- `VBG-001` — Sofía Ramírez（narración, voz en off）
- `VBG-002` — Carlos Mendez（doblaje, animación）
- `VBG-003` — Ana Torres（tiene orden activa — bloqueada）
- `122454`  — Luis Herrera（narración, locución comercial）
