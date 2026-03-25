# 零成本搭建你的个人网站

不需要自己写任何代码。AI 助手帮你写 — 你只需要用中文描述你想要什么。

**[English](./README.md)**

> **注意：** 本教程基于 macOS 编写。大部分步骤在 Windows/Linux 上也能用，但终端命令和快捷键是 Mac 的。如果你用的是 Windows 或 Linux，可以让 AI 助手帮你翻译对应命令。

---

## 这个教程适合谁？

- 想有自己的网站或作品集，但不会写代码
- 设计师、作家、学生，或者任何一直说"有空搭个网站"的人
- 试过 Wix / Squarespace 之类的建站工具，但想要一个自己完全可控的网站
- 听说过 AI 写代码，但不知道怎么用

## 最终效果

一个真正的网站，全世界都能访问，完全属于你。不是改不动的模板，也不用按月付费才能保持上线。你用中文描述想要什么，AI 助手帮你写代码。

**使用工具：** 任选一个 AI 编程助手 + GitHub（存放代码） + Vercel（免费托管）

**用时：** 第一个网站大约 1 小时

**费用：** 托管和部署 $0。AI 助手费用因工具而异（部分有免费额度）。域名可选（约 $10-15/年）。

## 整体流程

```
阶段 1：安装你的 AI 编程助手
阶段 2：在自己电脑上做出网站（AI 帮你写代码）
阶段 3：把网站放到网上
阶段 4：绑定自己的域名（可选）
```

---

## 阶段 1：安装你的 AI 编程助手

目标：装好一个 AI 助手。装好之后，后面每一步遇到问题都可以直接问它。

### 选一个工具

选一个就行，都能用于这个教程。

| 工具 | 使用方式 | 价格 | 适合人群 |
|------|---------|------|---------|
| [Claude Code](https://docs.anthropic.com/en/docs/claude-code) | 在终端里对话，它帮你写代码 | 按量计费（约 $5/月） | 不怕终端的人 |
| [Cursor](https://cursor.com) | 类似 VS Code 的编辑器，内置 AI | 免费版 + $20/月专业版 | 想要可视化编辑器的人 |
| [GitHub Copilot](https://github.com/features/copilot) | VS Code 里的 AI 插件 | 学生免费，$10/月 | VS Code 用户 |
| [Windsurf](https://windsurf.com) | AI 优先的代码编辑器 | 有免费版 | 想要图形界面的新手 |

> **别纠结选哪个。** 如果没有偏好，装 **Cursor** — 有免费版，有图形界面，开箱即用。如果你不怕终端，**Claude Code** 非常强。

### 安装你选的工具

<details>
<summary><strong>选项 A：Claude Code（终端版）</strong></summary>

1. **打开终端：** 按 **Command + 空格**，输入 `Terminal`，按回车
2. **安装 Homebrew**（Mac 的软件包管理器，装东西用的）：
   ```
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
   按提示操作。如果要求输入 Mac 密码，直接打（屏幕不会显示字符，正常的）。

   **重要（Apple Silicon 芯片的 Mac — M1/M2/M3/M4）：** Homebrew 装完后会提示你运行两行命令来配置 PATH。把它显示的两行命令复制粘贴运行。如果跳过这一步，终端会识别不了 `brew` 命令。
3. **安装 Node.js：**
   ```
   brew install node
   ```
4. **安装 Claude Code：**
   ```
   npm install -g @anthropic-ai/claude-code
   ```
   如果报"权限不够"（Permission denied）：
   ```
   sudo npm install -g @anthropic-ai/claude-code
   ```
5. **启动：**
   ```
   claude
   ```
6. 会打开浏览器让你注册/登录 Anthropic 账号，按提示操作。
7. 测试一下 — 输入：`你好！帮我解释一下什么是网站`
8. 如果它回答了，说明一切正常。输入 `/exit` 退出。

</details>

<details>
<summary><strong>选项 B：Cursor（可视化编辑器）</strong></summary>

1. 打开 [cursor.com](https://cursor.com)，下载应用
2. 打开下载的 `.dmg` 文件，拖到 Applications
3. 打开 Cursor，注册免费账号
4. 完成 — Cursor 自带 AI 功能，阶段 2 直接用。

</details>

<details>
<summary><strong>选项 C：VS Code + GitHub Copilot</strong></summary>

1. 下载 [VS Code](https://code.visualstudio.com)
2. 安装（打开 `.dmg`，拖到 Applications）
3. 打开 VS Code → 点左侧扩展图标 → 搜 "GitHub Copilot" → 安装
4. 用 GitHub 账号登录（没有的话去 [github.com](https://github.com) 注册）
5. Copilot 会在你写代码时提供建议，也可以通过聊天窗口对话

</details>

<details>
<summary><strong>选项 D：Windsurf（AI 编辑器）</strong></summary>

1. 打开 [windsurf.com](https://windsurf.com)，下载应用
2. 安装并打开
3. 注册免费账号
4. 完成 — Windsurf 内置 AI 聊天和代码生成。

</details>

> **从现在开始，后面任何步骤看不懂、报错了、不知道怎么办，都可以打开你的 AI 助手问它。什么都可以问。它是你的全程教练。**

---

## 阶段 2：在自己电脑上做出网站

目标：先在自己电脑上把网站做出来，在浏览器里看到效果。别人还看不到 — 先做到自己满意再上线。

### 第 1 步：创建项目文件夹

**如果用终端（Claude Code）：**
```
mkdir -p ~/Developer/my-website
cd ~/Developer/my-website
```

**如果用 Cursor / VS Code / Windsurf：**
1. 在电脑上随便一个地方建一个叫 `my-website` 的文件夹
2. 打开编辑器 → 文件 → 打开文件夹 → 选 `my-website`

### 第 2 步：告诉 AI 你想要什么

打开你的 AI 助手，用中文描述你想要的网站。比如：

> "帮我创建一个个人网站首页。我叫[你的名字]，是一个[你的职业]。
>  风格要简洁现代，需要有：自我介绍、工作经历、联系方式。"

AI 会自动在你的文件夹里创建文件。

继续提要求：
- "配色换成暖色调"
- "字体大一点"
- "加一个放照片的区域"
- "加一个深色模式切换按钮"
- "手机上看起来怎么样？帮我优化一下"

不需要懂代码。你只管描述效果，它来写。如果不对，直接说"这不是我想要的，我想要的是..."

### 第 3 步：在浏览器里预览

**让 AI 帮你打开：**

> "帮我在浏览器里打开这个网站看看效果"

**或者手动打开：**
1. 打开 **访达（Finder）**
2. 找到你的 `my-website` 文件夹
3. 双击 `index.html`，浏览器会自动打开

### 第 4 步：反复调整到满意

预览之后，继续跟 AI 提要求：

- "标题太大了，小一点"
- "背景色换成浅灰色"
- "联系方式旁边加一个邮箱图标"
- "帮我照着这个网站的风格改：[粘贴你喜欢的网站网址]"

每次改完，刷新浏览器（**Command + R**）就能看到最新效果。

不着急，慢慢来。

> **到这里，你的网站在自己电脑上已经做好了。但只有你能看到。下一步我们把它放到网上。**

---

## 阶段 3：把网站放到网上

目标：让全世界都能通过网址访问你的网站。大部分操作可以让 AI 助手帮你完成。

### 第 5 步：安装 Git 并注册 GitHub

**Git** 管理你的代码，**GitHub** 把代码存到网上，**Vercel**（下一步）从 GitHub 读代码来发布。

**安装 Git**（Mac 通常自带）：

打开终端，输入：
```
git --version
```
- 如果显示 `git version 2.x.x`，说明已经有了
- 如果弹窗要你安装"Command Line Tools"，点"安装"，等几分钟

**注册 GitHub：**
1. 打开 **github.com** → "Sign up"
2. 选一个用户名，输入邮箱，设置密码
3. 验证邮箱
4. 记住你的用户名

### 第 6 步：在 GitHub 上创建项目，然后推送代码

**先在 GitHub 网页上创建一个空项目：**
1. 登录 github.com → 点右上角 **"+"** → **"New repository"**
2. 名字填 `my-website`（和你电脑上的文件夹名一致）
3. 其他都不要勾，保持默认（不要勾"Add a README"）
4. 点 **"Create repository"**

**然后让 AI 帮你推送代码：**

告诉你的 AI 助手：

> "帮我把这个项目推送到 GitHub。我的用户名是[你的用户名]，repository 叫 my-website。我已经在 GitHub 上创建好了空的 repository。"

AI 会帮你配置 Git 并推送代码。过程中可能弹出 GitHub 登录页面，登录授权即可。

遇到报错不用慌，直接把错误信息粘贴给 AI，它会帮你解决。

### 第 7 步：注册 Vercel，一键部署

Vercel 把你 GitHub 上的代码变成真正能访问的网站。免费。

1. 打开 **vercel.com** → **"Sign Up"** → **"Continue with GitHub"**
2. 授权 Vercel 访问你的 GitHub
3. 点 **"Add New..."** → **"Project"**
4. 找到 `my-website`，点 **"Import"**
5. 保持默认设置，点 **"Deploy"**
6. 等十几秒，完成！

> 找不到项目？点 **"Adjust GitHub App Permissions"** 授权即可。

### 第 8 步：你的网站上线了！

部署完成后，Vercel 会给你一个网址，类似：
```
https://my-website-xxxxx.vercel.app
```

打开它 — 这就是你的网站，全世界都能访问了！

以后每次改完代码推送到 GitHub（让 AI 帮你推就行），Vercel 会在几秒内自动更新。

---

## 阶段 4：绑定自己的域名（可选）

`.vercel.app` 的网址完全能用。如果你想要自己的域名（比如 `yourname.com`），随时可以来做这一步。

### 第 9 步：购买域名

推荐平台：
- **Namecheap**（namecheap.com）— 便宜，界面简单
- **Cloudflare**（cloudflare.com/products/registrar）— 成本价，无额外费用

搜索你想要的域名，注册账号，付款（`.com` 大约 $10-15/年）。

不知道选什么域名？问 AI 助手："帮我想几个适合[你的职业]的个人网站域名"

### 第 10 步：在 Vercel 里连接域名

1. 打开 vercel.com → 进入你的项目 → **Settings** → **Domains**
2. 输入你的域名 → 点 **Add**
3. Vercel 会告诉你需要添加的 DNS 记录：
   - **A 记录：** `76.76.21.21`
   - **CNAME 记录：** `www` → `cname.vercel-dns.com`
4. 回到域名商网站，找到 DNS 设置页面，添加这两条记录
5. 等几分钟到几小时

Vercel 会自动配好 HTTPS，不需要你操心。

> DNS 设置看不懂？问你的 AI 助手，它会一步步教你。

---

## 日常使用流程

以后每次想改网站：

1. 打开你的 AI 助手，进入项目文件夹
2. 用中文描述你想改什么
3. 浏览器里预览效果（Command + R 刷新）
4. 满意后说"帮我推送到 GitHub"
5. 几秒后网站自动更新

---

## 常见问题

**Q: 终端里命令输错了怎么办？**
按 **Control + C** 取消，重新输入。

**Q: 忘记上次做到哪了？**
问 AI 助手："帮我看看这个项目现在是什么状态。"

**Q: 想加功能但不知道怎么描述？**
直接说你想实现的效果："我想让别人能在网站上给我留言"、"我想看有多少人访问了我的网站"。

**Q: 改了网站但浏览器还是旧的？**
按 **Command + Shift + R** 强制刷新。

**Q: 其他任何问题？**
问你的 AI 助手。真的，什么都可以问。

---

## 费用明细

| 工具 | 费用 | 用途 |
|------|------|------|
| GitHub | 免费 | 存放代码 |
| Vercel | 免费 | 托管网站 |
| AI 助手 | 因工具而异（部分有免费版） | 帮你写代码 |
| 域名 | ~$10-15/年 | 可选 |

**最低上线成本：$0**（如果使用有免费额度的 AI 工具）

---

## License

MIT — 随便用。

---

*作者：[@che-3](https://github.com/che-3)。如果这个教程帮到了你，欢迎给个 star。*
