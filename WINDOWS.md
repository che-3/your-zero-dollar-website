# Your Zero Dollar Website — Windows Guide

This is the Windows version of the guide. If you're on Mac, go to [README.md](./README.md).

The overall process is the same — only the installation steps and keyboard shortcuts differ.

**[Windows 中文版](./WINDOWS_ZH.md)**

---

## 🛠 Phase 1: Set Up Your AI Coding Assistant

### Choose Your Tool

Same options as the Mac guide. Pick one:

| Tool | How It Works | Pricing | Best For |
|------|-------------|---------|----------|
| [Claude Code](https://docs.anthropic.com/en/docs/claude-code) | Terminal-based. You type, it codes. | Pay-as-you-go | People comfortable with Terminal |
| [Cursor](https://cursor.com) | VS Code-like editor with built-in AI | Free tier + $20/mo Pro | People who want a visual editor |
| [GitHub Copilot](https://github.com/features/copilot) | AI inside VS Code | Free for students, $10/mo | VS Code users |
| [Windsurf](https://windsurf.com) | AI-first code editor | Free tier available | Beginners who want a GUI |

### Install Your Chosen Tool

<details>
<summary><strong>Option A: Claude Code (Terminal-based)</strong></summary>

1. **Open PowerShell:** Press **Windows key**, type `PowerShell`, click **"Windows PowerShell"**

2. **Install Node.js:** Go to [nodejs.org](https://nodejs.org), download the **LTS** Windows installer (.msi), run it, click "Next" through all the prompts.

   After installation, **close and reopen PowerShell**, then verify:
   ```powershell
   node --version
   ```
   You should see something like `v22.x.x`.

3. **Install Claude Code:**
   ```powershell
   npm install -g @anthropic-ai/claude-code
   ```

4. **Launch it:**
   ```powershell
   claude
   ```

5. It opens your browser to sign up / log in to Anthropic. Follow the prompts.
6. Test it — type: `Hello! Explain what a website is in one sentence.`
7. If it responds, you're set. Type `/exit` to quit for now.

</details>

<details>
<summary><strong>Option B: Cursor (Visual editor)</strong></summary>

1. Go to [cursor.com](https://cursor.com) and download the Windows installer
2. Run the `.exe` file, follow the prompts
3. Open Cursor, sign up for a free account
4. That's it — Cursor has AI built in.

</details>

<details>
<summary><strong>Option C: VS Code + GitHub Copilot</strong></summary>

1. Download [VS Code](https://code.visualstudio.com) for Windows
2. Run the installer
3. Open VS Code → click Extensions icon (left sidebar) → search "GitHub Copilot" → Install
4. Sign in with your GitHub account (create one at [github.com](https://github.com) if needed)
5. Copilot will be available as you type code, and via the chat sidebar

</details>

<details>
<summary><strong>Option D: Windsurf (AI-first editor)</strong></summary>

1. Go to [windsurf.com](https://windsurf.com) and download the Windows installer
2. Run the installer
3. Sign up for a free account
4. Ready to go.

</details>

> **From this point on, if you get stuck on ANY step, ask your AI assistant.**

---

## 🎨 Phase 2: Build Your Site Locally

### Step 1: Create a Project Folder

**If using PowerShell (Claude Code):**
```powershell
mkdir -Force ~\Developer\my-website
cd ~\Developer\my-website
```

**If using Cursor / VS Code / Windsurf:**
1. Create a folder called `my-website` anywhere (e.g. in Documents)
2. Open your editor → File → Open Folder → select `my-website`

### Step 2: Tell the AI What You Want

Same as the Mac guide — describe your website in plain language:

> "Create a personal website for me. My name is [your name], I'm a [your job]. I want a clean, modern design with: an intro section, my work experience, and contact info."

Keep refining: "Make the font bigger", "Add a dark mode toggle", etc.

### Step 3: Preview in Your Browser

Ask your AI assistant:

> "Open this website in my browser so I can see it"

Or manually: open File Explorer, navigate to your `my-website` folder, double-click `index.html`.

### Step 4: Iterate Until You're Happy

After each change, refresh your browser (**Ctrl + R** or **F5**) to see the update.

---

## 🚀 Phase 3: Put It Online

### Step 5: Install Git and Sign Up for GitHub

**Install Git:**

1. Go to [git-scm.com](https://git-scm.com) and download Git for Windows
2. Run the installer — **keep all default settings**, just click "Next" through everything
3. After installation, **close and reopen PowerShell**, then verify:
   ```powershell
   git --version
   ```
   You should see `git version 2.x.x`.

**Sign up for GitHub:**
1. Go to **github.com** → "Sign up"
2. Pick a username, enter email, set a password
3. Verify your email
4. Done. Remember your username.

### Step 6: Create a GitHub Repository and Push Your Code

**First, create an empty project on GitHub:**
1. Log in to github.com → click **"+"** → **"New repository"**
2. Name it `my-website` (match your folder name)
3. Don't check any boxes (do NOT check "Add a README")
4. Click **"Create repository"**

**Then push your code.** Ask your AI assistant:

> "Push this project to GitHub. My username is [your username], the repository is my-website. I already created an empty repository."

You may see a GitHub login popup — log in and authorize.

### Step 7: Deploy with Vercel

Same as the Mac guide — this is all done in your browser:

1. Go to **vercel.com** → **"Sign Up"** → **"Continue with GitHub"**
2. Authorize Vercel to access your GitHub
3. Click **"Add New..."** → **"Project"**
4. Find `my-website` → click **"Import"**
5. If Vercel asks about a "Framework Preset", select **Other** or leave it blank.
6. Leave defaults → click **"Deploy"**
7. Wait ~10 seconds. Done!

### Step 8: Your Site Is Live!

Vercel gives you a URL like `https://my-website-xxxxx.vercel.app`. That's your website.

---

## 🌐 Phase 4: Custom Domain (Optional)

Identical to the Mac guide:

1. Buy a domain from **Namecheap** or **Cloudflare** (~$10-15/year)
2. In Vercel → Settings → Domains → add your domain
3. Add the DNS records Vercel tells you to at your registrar. Copy these exactly — they are unique to your project.
4. Wait a few minutes to a few hours

---

## Daily Workflow

Whenever you want to update your site:

1. Open PowerShell
2. `cd ~\Developer\my-website`
3. Open your AI assistant
4. Describe what you want to change
5. Preview in browser (Ctrl + R to refresh)
6. Say "Push to GitHub"
7. Site updates in seconds

---

## Windows vs Mac — Quick Reference

| Action | Mac | Windows |
|--------|-----|---------|
| Open terminal | Command + Space → "Terminal" | Windows key → "PowerShell" |
| Create folder | `mkdir -p ~/Developer/my-website` | `mkdir -Force ~\Developer\my-website` |
| Refresh browser | Command + R | Ctrl + R or F5 |
| Force refresh | Command + Shift + R | Ctrl + Shift + R |
| Cancel a command | Control + C | Ctrl + C |
| Install Node.js | `brew install node` | Download .msi from nodejs.org |
| Install Git | Usually pre-installed | Download from git-scm.com |

---

## FAQ

**Q: PowerShell says "running scripts is disabled."**
Run this command, then try again:
```powershell
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```
Type `Y` to confirm.

**Q: `node` or `git` command not found after installing.**
Close PowerShell and reopen it. Windows needs a fresh terminal to pick up new installs.

**Q: I forgot where I left off.**
Ask your AI assistant: "Check the current state of this project."

**Q: The browser shows the old version after changes.**
Press **Ctrl + Shift + R** to force refresh.

**Q: Any other question?**
Ask your AI assistant. It can help with anything.

---

## What Does It Actually Cost?

| Tool | Cost | What It Does |
|------|------|-------------|
| GitHub | Free | Stores your code |
| Vercel | Free | Hosts your website |
| AI Assistant | Varies (free tiers available) | Writes code for you |
| Domain name | ~$10-15/year | Optional |

**Minimum cost to get a site live: $0** if you use an AI tool with a free tier.

---

## Prefer Talking Over Reading?

Install the **[zero-dollar-website-skill](https://github.com/che-3/zero-dollar-website-skill)** for Claude Code — it walks you through the entire process interactively.

```bash
git clone https://github.com/che-3/zero-dollar-website-skill.git ~/.claude/skills/zero-dollar-website
```

---

*Back to [main guide (Mac)](./README.md)*
