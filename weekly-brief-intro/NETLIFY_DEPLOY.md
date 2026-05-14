# AI 自动化周简报搭建指南 - Netlify 部署说明

## 📦 部署准备

确保您的项目文件夹包含以下文件：
- `ai-presentation.html` - 主页面文件
- `netlify.toml` - Netlify 配置文件（已创建）
- 相关图片文件（运维看板.jpg、项目进度看板.png、工单分析报告.png 等）

## 🚀 部署方法（三种任选其一）

### 方法一：通过 Netlify 界面部署（最简单）

1. **访问 Netlify**
   - 打开 https://app.netlify.com/
   - 登录或注册账号（支持 GitHub/GitLab 账号）

2. **创建新站点**
   - 点击 "Add new site" → "Deploy manually"
   - 将整个项目文件夹拖拽到上传区域
   - 等待上传完成（通常几秒到几十秒）

3. **配置域名（可选）**
   - 点击 "Domain settings"
   - 使用默认的随机域名，或绑定自定义域名

4. **完成！**
   - 部署成功后会生成访问链接
   - 格式：`https://your-site-name.netlify.app`

---

### 方法二：通过 Netlify CLI 部署（推荐开发者）

1. **安装 Netlify CLI**
   ```bash
   npm install -g netlify-cli
   ```

2. **登录 Netlify**
   ```bash
   netlify login
   ```

3. **初始化项目**
   ```bash
   cd d:/Users/zhangf31/CodeBuddy/weekly-brief-intro
   netlify init
   ```
   - 选择 "Create & configure a new site"
   - 选择您的团队
   - 输入站点名称（可选，不填则随机生成）

4. **部署**
   ```bash
   netlify deploy --prod
   ```
   - 按提示确认发布目录为 `.` 或当前目录

5. **完成！**
   - 部署成功后会显示访问链接

---

### 方法三：通过 Git 自动部署（持续集成）

1. **将代码推送到 Git 仓库**
   ```bash
   cd d:/Users/zhangf31/CodeBuddy/weekly-brief-intro
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin <your-repo-url>
   git push -u origin main
   ```

2. **连接 Netlify**
   - 访问 https://app.netlify.com/
   - 点击 "Add new site" → "Import an existing project"
   - 选择 Git 服务商（GitHub/GitLab/Bitbucket）
   - 选择您的仓库

3. **配置构建设置**
   - Build command: 留空（或填 `echo 'No build'`）
   - Publish directory: `.`
   - 点击 "Deploy site"

4. **自动部署**
   - 之后每次推送到 main 分支都会自动部署
   - 可在 Netlify 界面查看部署历史和日志

---

## 📝 部署后配置

### 自定义域名（可选）

1. 在 Netlify 站点设置中点击 "Add custom domain"
2. 输入您的域名
3. 按照提示配置 DNS 记录

### 启用 HTTPS（自动）

- Netlify 默认为所有站点提供免费 SSL 证书
- 绑定域名后自动启用 HTTPS

### 部署预览（如果使用 Git）

- 每次 Pull Request 都会生成预览链接
- 可在预览环境中测试修改

---

## 🔧 常见问题

### Q: 图片不显示？
A: 确保图片文件与 HTML 文件在同一目录，且文件名完全匹配（包括大小写）

### Q: 如何更新部署？
A: 
- 手动部署：重新拖拽文件夹或运行 `netlify deploy --prod`
- Git 部署：推送代码后自动更新

### Q: 如何回滚到旧版本？
A: 在 Netlify 站点的 "Deploys" 页面，找到目标版本点击 "Publish deploy"

### Q: 访问速度慢？
A: Netlify 使用全球 CDN 加速，通常速度很快。如需优化，可压缩图片文件大小

---

## 📊 项目文件清单

```
weekly-brief-intro/
├── ai-presentation.html      # 主页面（必须）
├── netlify.toml              # Netlify 配置（已创建）
├── 运维看板.jpg               # 运维看板截图
├── 项目进度看板.png           # 项目进度看板截图
├── 工单分析报告.png           # 工单分析报告截图
├── 搭建数据流.png             # 数据流图
├── 价值速览.png               # 价值速览图
├── 实施路径.png               # 实施路径图
└── README.md                 # 本说明文件
```

---

## ✨ 部署成功标志

部署成功后，您将能够：
- ✅ 通过 Netlify 提供的域名访问演示文稿
- ✅ 使用左右箭头键或按钮切换幻灯片
- ✅ 在移动设备上正常浏览
- ✅ 享受全球 CDN 加速访问

**祝您部署顺利！** 🎉

如有问题，请访问 Netlify 官方文档：https://docs.netlify.com/
