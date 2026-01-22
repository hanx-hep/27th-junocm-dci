# 项目概览

这是一个用于展示 DIRAC+X 状态的Slidev幻灯片项目，为第11届DIRAC用户研讨会（DUW11）准备。主要展示从DIRAC v8到v9以及DiracX 0.0.1的迁移进展、新特性以及未来规划。

## 技术栈

- **Slidev**: 用于创建幻灯片的框架
- **slidev-theme-neversink**: 幻灯片使用的主题
- **Netlify**: 用于部署和托管幻灯片
- **GitHub Actions**: 用于自动化构建和部署到GitHub Pages

## 目录结构

```
.
├── slides.md              # 幻灯片内容
├── package.json           # 项目配置和脚本
├── netlify.toml           # Netlify部署配置
├── public/                # 静态资源目录
│   └── images/            # 图片资源
├── .github/               # GitHub配置和工作流
│   └── workflows/         # GitHub Actions工作流
│       └── create.yml     # GitHub Pages部署工作流
└── IFLOW.md               # 本说明文件
```

## 构建和运行

### 构建幻灯片

```bash
npm run build
```

此命令会使用Slidev构建幻灯片，并下载所需资源到`dist`目录。

### 本地开发

要启动本地开发服务器，可以使用Slidev的默认命令（虽然未在package.json中明确指定）：

```bash
npx slidev
```

## 部署

该项目支持两种部署方式：

### 1. Netlify部署

该项目配置为通过Netlify自动部署。Netlify构建命令为：

```bash
npm install unplugin-icons @iconify-json/logos @iconify-json/devicon @iconify-json/devicon-plain @slidev/cli @slidev/theme-default slidev-theme-neversink playwright-chromium && npm run build
```

配置文件：`netlify.toml`

### 2. GitHub Pages部署

通过GitHub Actions自动化部署到GitHub Pages：

- **触发条件**: 推送代码到`main`分支或手动触发工作流
- **构建命令**: 自动安装依赖并构建项目
- **部署配置**: 在`.github/workflows/create.yml`中定义
- **环境要求**: 需要在仓库设置中启用GitHub Pages，并选择"GitHub Actions"作为source

配置文件：`.github/workflows/create.yml`

## 使用说明

1. **编辑内容**: 编辑 `slides.md` 文件来修改幻灯片内容
2. **管理资源**: 将图片等静态资源放在 `public/images/` 目录下
3. **构建项目**: 使用 `npm run build` 构建项目
4. **部署选择**:
   - **Netlify**: 通过Netlify服务部署 `dist` 目录中的内容
   - **GitHub Pages**: 推送代码到GitHub仓库，GitHub Actions会自动构建并部署

## 关键文件说明

- **slides.md**: 包含所有幻灯片内容，使用Markdown格式和Slidev特定的YAML frontmatter
- **package.json**: 定义项目依赖和构建脚本
- **netlify.toml**: 配置Netlify部署设置，包括构建命令和重定向规则
- **.github/workflows/create.yml**: GitHub Actions工作流配置，用于自动化构建和部署到GitHub Pages

## 图片资源

`public/images/`目录包含以下图片文件：
- `architecture.png` - 架构图
- `code_structure.png` - 代码结构图
- `DIRAC-logo-extended.png` - DIRAC扩展logo
- `diracx-logo-square.png` - DiracX方形logo
- `LHCb_everywhere.jpg` - LHCb相关图片
- `LHCb.png` - LHCb logo