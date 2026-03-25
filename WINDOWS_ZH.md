# 零成本搭建你的个人网站 — Windows 版

这是 Windows 版教程。如果你用 Mac，请看 [README_ZH.md](./README_ZH.md)。

整体流程一样 — 只有安装步骤和快捷键不同。

**[English (Windows)](./WINDOWS.md)**

---

## 阶段 1：安装你的 AI 编程助手

### 选一个工具

和 Mac 版一样，选一个就行：

| 工具 | 使用方式 | 价格 | 适合人群 |
|------|---------|------|---------|
| [Claude Code](https://docs.anthropic.com/en/docs/claude-code) | 在终端里对话，它帮你写代码 | 按量计费（约 $5/月） | 不怕终端的人 |
| [Cursor](https://cursor.com) | 类似 VS Code 的编辑器，内置 AI | 免费版 + $20/月专业版 | 想要可视化编辑器的人 |
| [GitHub Copilot](https://github.com/features/copilot) | VS Code 里的 AI 插件 | 学生免费，$10/月 | VS Code 用户 |
| [Windsurf](https://windsurf.com) | AI 优先的代码编辑器 | 有免费版 | 想要图形界面的新手 |

### 安装你选的工具

<details>
<summary><strong>选项 A：Claude Code（终端版）</strong></summary>

1. **打开 PowerShell：** 按 **Windows 键**，输入 `PowerShell`，点 **"Windows PowerShell"**

2. **安装 Node.js：** 打开 [nodejs.org](https://nodejs.org)，下载 **LTS** 版本的 Windows 安装包（.msi），运行安装，一路点"Next"。

   装完后，**关掉 PowerShell 重新打开**，然后验证：
   ```
   node --version
   ```
   应该显示类似 `v22.x.x`。

3. **安装 Claude Code：**
   ```
   npm install -g @anthropic-ai/claude-code
   ```

4. **启动：**
   ```
   claude
   ```

5. 会打开浏览器让你注册/登录 Anthropic 账号，按提示操作。
6. 测试一下 — 输入：`你好！帮我解释一下什么是网站`
7. 如果它回答了，说明一切正常。输入 `/exit` 退出。

</details>

<details>
<summary><strong>选项 B：Cursor（可视化编辑器）</strong></summary>

1. 打开 [cursor.com](https://cursor.com)，下载 Windows 安装包
2. 运行 `.exe` 文件，按提示安装
3. 打开 Cursor，注册免费账号
4. 完成 — Cursor 自带 AI 功能。

</details>

<details>
<summary><strong>选项 C：VS Code + GitHub Copilot</strong></summary>

1. 下载 [VS Code](https://code.visualstudio.com) Windows 版
2. 运行安装包
3. 打开 VS Code → 点左侧扩展图标 → 搜 "GitHub Copilot" → 安装
4. 用 GitHub 账号登录（没有的话去 [github.com](https://github.com) 注册）
5. Copilot 会在你写代码时提供建议，也可以通过聊天窗口对话

</details>

<details>
<summary><strong>选项 D：Windsurf（AI 编辑器）</strong></summary>

1. 打开 [windsurf.com](https://windsurf.com)，下载 Windows 安装包
2. 运行安装
3. 注册免费账号
4. 完成。

</details>

> **从现在开始，后面任何步骤看不懂、报错了，都可以打开你的 AI 助手问它。**

---

## 阶段 2：在自己电脑上做出网站

### 第 1 步：创建项目文件夹

**如果用 PowerShell（Claude Code）：**
```powershell
mkdir ~\Developer\my-website
cd ~\Developer\my-website
```

**如果用 Cursor / VS Code / Windsurf：**
1. 在电脑上随便一个地方建一个叫 `my-website` 的文件夹
2. 打开编辑器 → 文件 → 打开文件夹 → 选 `my-website`

### 第 2 步：告诉 AI 你想要什么

和 Mac 版一样 — 用中文描述你想要的网站：

> "帮我创建一个个人网站首页。我叫[你的名字]，是一个[你的职业]。
>  风格要简洁现代，需要有：自我介绍、工作经历、联系方式。"

继续提要求："字体大一点"、"加深色模式"等等。

### 第 3 步：在浏览器里预览

让 AI 助手帮你打开：

> "帮我在浏览器里打开这个网站看看效果"

或者手动：打开文件资源管理器，找到 `my-website` 文件夹，双击 `index.html`。

### 第 4 步：反复调整到满意

每次改完，刷新浏览器（**Ctrl + R** 或 **F5**）看最新效果。

---

## 阶段 3：把网站放到网上

### 第 5 步：安装 Git 并注册 GitHub

**安装 Git：**

1. 打开 [git-scm.com](https://git-scm.com)，下载 Git for Windows
2. 运行安装包 — **所有设置保持默认**，一路点"Next"
3. 装完后，**关掉 PowerShell 重新打开**，验证：
   ```
   git --version
   ```
   应该显示 `git version 2.x.x`。

**注册 GitHub：**
1. 打开 **github.com** → "Sign up"
2. 选用户名，输入邮箱，设置密码
3. 验证邮箱
4. 记住你的用户名

### 第 6 步：在 GitHub 上创建项目，然后推送代码

**先在 GitHub 网页上创建空项目：**
1. 登录 github.com → 点右上角 **"+"** → **"New repository"**
2. 名字填 `my-website`（和文件夹名一致）
3. 不要勾任何选项（不要勾"Add a README"）
4. 点 **"Create repository"**

**然后让 AI 帮你推送：**

> "帮我把这个项目推送到 GitHub。我的用户名是[你的用户名]，repository 叫 my-website。我已经在 GitHub 上创建好了空的 repository。"

可能会弹出 GitHub 登录页面，登录授权即可。

### 第 7 步：注册 Vercel，一键部署

和 Mac 版一样 — 全在浏览器里操作：

1. 打开 **vercel.com** → **"Sign Up"** → **"Continue with GitHub"**
2. 授权 Vercel 访问你的 GitHub
3. 点 **"Add New..."** → **"Project"**
4. 找到 `my-website`，点 **"Import"**
5. 保持默认，点 **"Deploy"**
6. 等十几秒，完成！

### 第 8 步：你的网站上线了！

Vercel 给你的网址类似 `https://my-website-xxxxx.vercel.app`，全世界都能访问。

---

## 阶段 4：绑定自己的域名（可选）

和 Mac 版完全一样：

1. 在 **Namecheap** 或 **Cloudflare** 买域名（约 $10-15/年）
2. Vercel → Settings → Domains → 添加你的域名
3. 在域名商 DNS 设置里添加：
   - **A 记录：** `76.76.21.21`
   - **CNAME：** `www` → `cname.vercel-dns.com`
4. 等几分钟到几小时

---

## Windows vs Mac 快捷对照

| 操作 | Mac | Windows |
|------|-----|---------|
| 打开终端 | Command + 空格 → "Terminal" | Windows 键 → "PowerShell" |
| 创建文件夹 | `mkdir -p ~/Developer/my-website` | `mkdir ~\Developer\my-website` |
| 刷新浏览器 | Command + R | Ctrl + R 或 F5 |
| 强制刷新 | Command + Shift + R | Ctrl + Shift + R |
| 取消命令 | Control + C | Ctrl + C |
| 安装 Node.js | `brew install node` | 从 nodejs.org 下载安装包 |
| 安装 Git | 通常自带 | 从 git-scm.com 下载安装包 |

---

## 常见问题

**Q: PowerShell 提示"禁止运行脚本"？**
运行这个命令，然后重试：
```powershell
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```
输入 `Y` 确认。

**Q: 装完 `node` 或 `git` 后命令找不到？**
关掉 PowerShell 重新打开。Windows 需要新的终端窗口才能识别刚安装的程序。

**Q: 其他任何问题？**
问你的 AI 助手。什么都可以问。

---

*返回 [Mac 中文版](./README_ZH.md)*
