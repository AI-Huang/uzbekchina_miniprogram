# UzbekChina Miniprogram

乌兹别克斯坦-中国合作项目微信小程序

## 项目简介

本项目是基于 **uni-app** 框架开发的跨端小程序，支持微信小程序、H5 及其他主流小程序平台。

## 技术栈

- **框架**: uni-app 3.0
- **语言**: Vue 3 + TypeScript
- **构建工具**: Vite 5
- **国际化**: vue-i18n 9

## 功能特性

- ✅ 多端兼容：微信小程序、H5、支付宝、百度、京东等
- ✅ 响应式设计，适配多种屏幕尺寸
- ✅ 国际化支持，支持多语言切换

## 快速开始

### 环境要求

- Node.js >= 18.0.0
- npm >= 9.0.0

### 安装依赖

```bash
npm install
```

### 开发调试

```bash
# 微信小程序开发
npm run dev:mp-weixin

# H5 开发
npm run dev:h5

# 支付宝小程序开发
npm run dev:mp-alipay
```

### 构建打包

```bash
# 微信小程序构建
npm run build:mp-weixin

# H5 构建
npm run build:h5

# 支付宝小程序构建
npm run build:mp-alipay
```

## 项目结构

```
├── dist/                 # 构建产物目录
│   └── dev/mp-weixin/    # 微信小程序开发构建
├── node_modules/         # 依赖包
├── package.json          # 项目配置
└── README.md             # 项目说明
```

## 支持的平台

| 平台 | 开发命令 | 构建命令 |
|------|----------|----------|
| 微信小程序 | `dev:mp-weixin` | `build:mp-weixin` |
| H5 | `dev:h5` | `build:h5` |
| 支付宝小程序 | `dev:mp-alipay` | `build:mp-alipay` |
| 百度小程序 | `dev:mp-baidu` | `build:mp-baidu` |
| QQ 小程序 | `dev:mp-qq` | `build:mp-qq` |
| 头条小程序 | `dev:mp-toutiao` | `build:mp-toutiao` |
| 京东小程序 | `dev:mp-jd` | `build:mp-jd` |
| 小红书小程序 | `dev:mp-xhs` | `build:mp-xhs` |
| 快手小程序 | `dev:mp-kuaishou` | `build:mp-kuaishou` |
| HarmonyOS | `dev:mp-harmony` | `build:mp-harmony` |
| 飞书小程序 | `dev:mp-lark` | `build:mp-lark` |

## 微信开发者工具调试

1. 运行 `npm run dev:mp-weixin`
2. 打开微信开发者工具
3. 导入项目，选择 `dist/dev/mp-weixin` 目录
4. 开始调试

## License

MIT License
