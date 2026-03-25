# Your Zero Dollar Website

I built my personal website in one afternoon. I didn't write a single line of code — I just told an AI what I wanted, and it built the whole thing. Then I put it online for free.

This guide is exactly how I did it, step by step. If I can do it, you can too.

**[中文版](./README_ZH.md)**

> **On Windows?** Read the [Windows guide](./WINDOWS.md) instead — same process, Windows-specific commands.

> **On Linux?** This Mac guide mostly applies. Your AI assistant can translate any Mac-specific commands for your distro.

---

## Who Is This For?

- You want a personal site or portfolio but don't know how to code
- You're a designer, writer, student, or anyone who's been meaning to make a site "someday"
- You tried website builders (Wix, Squarespace) but want something you actually own
- You've heard of AI coding tools but don't know where to start

## What You'll End Up With

A real website, live on the internet, that you fully own and control. No templates you can't modify. No monthly subscription to keep it online. You describe what you want in plain English (or any language), and an AI assistant writes the code for you.

**Tools used:** An AI coding assistant of your choice + GitHub (code storage) + Vercel (free hosting)

**Time:** ~1 hour for your first site

**Cost:** $0 for hosting and deployment. AI assistant pricing varies by tool (some have free tiers). Domain name is optional (~$10-15/year).

## How It Works

```
🛠 Phase 1: Set up your AI coding assistant
🎨 Phase 2: Build the site on your computer (AI does the coding)
🚀 Phase 3: Put it on the internet
🌐 Phase 4: Connect a custom domain (optional)
```

---

## 🛠 Phase 1: Set Up Your AI Coding Assistant

The goal: get an AI assistant running so it can write code for you and help you through every step of this guide.

### Choose Your Tool

Pick one. They all work for this guide. You only need one.

| Tool | How It Works | Pricing | Best For |
|------|-------------|---------|----------|
| [Claude Code](https://docs.anthropic.com/en/docs/claude-code) | Terminal-based. You type, it codes. | Pay-as-you-go | People comfortable with Terminal |
| [Cursor](https://cursor.com) | VS Code-like editor with built-in AI | Free tier + $20/mo Pro | People who want a visual editor |
| [GitHub Copilot](https://github.com/features/copilot) | AI inside VS Code | Free for students, $10/mo | VS Code users |
| [Windsurf](https://windsurf.com) | AI-first code editor | Free tier available | Beginners who want a GUI |

> **Don't overthink it.** If you have no preference, install **Cursor** — it has a free tier, a visual interface, and works out of the box. If you're comfortable with Terminal, **Claude Code** is extremely capable.

### Install Your Chosen Tool

<details>
<summary><strong>Option A: Claude Code (Terminal-based)</strong></summary>

1. **Open Terminal:** Press **Command + Space**, type `Terminal`, hit Enter
2. **Install Homebrew** (Mac's package manager — makes installing tools easy):
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
   Follow the prompts. If it asks for your Mac password, type it (nothing shows on screen — that's normal). If Homebrew is already installed, the script will tell you — just skip to the next step.

   **Important (Apple Silicon Macs — M1/M2/M3/M4):** After Homebrew finishes, it will tell you to run two commands to add it to your PATH. Copy and run both lines it shows you. If you skip this, `brew` won't be recognized.
3. **Install Node.js:**
   ```bash
   brew install node
   ```
4. **Install Claude Code:**
   ```bash
   npm install -g @anthropic-ai/claude-code
   ```
   If you get "Permission denied":
   ```bash
   sudo npm install -g @anthropic-ai/claude-code
   ```
5. **Launch it:**
   ```bash
   claude
   ```
6. It opens your browser to sign up / log in to Anthropic. Follow the prompts.
7. Test it — type: `Hello! Explain what a website is in one sentence.`
8. If it responds, you're set. Type `/exit` to quit for now.

</details>

<details>
<summary><strong>Option B: Cursor (Visual editor)</strong></summary>

1. Go to [cursor.com](https://cursor.com) and download the app
2. Open the downloaded `.dmg` file, drag Cursor to Applications
3. Open Cursor, sign up for a free account
4. That's it — Cursor has AI built in. You'll use it in Phase 2.

</details>

<details>
<summary><strong>Option C: VS Code + GitHub Copilot</strong></summary>

1. Download [VS Code](https://code.visualstudio.com)
2. Install it (open `.dmg`, drag to Applications)
3. Open VS Code → click Extensions icon (left sidebar) → search "GitHub Copilot" → Install
4. Sign in with your GitHub account (create one at [github.com](https://github.com) if needed)
5. Copilot will be available as you type code, and via the chat sidebar

</details>

<details>
<summary><strong>Option D: Windsurf (AI-first editor)</strong></summary>

1. Go to [windsurf.com](https://windsurf.com) and download the app
2. Install and open it
3. Sign up for a free account
4. Ready to go — Windsurf has AI chat and code generation built in.

</details>

> **From this point on, if you get stuck on ANY step, ask your AI assistant.** Open it, describe the problem, and it will help. It's your personal coach through this entire guide.

---

## 🎨 Phase 2: Build Your Site Locally

The goal: create your website on your own computer and preview it in your browser. Nobody else can see it yet — get it right first.

### Step 1: Create a Project Folder

**If using Terminal (Claude Code):**
```bash
mkdir -p ~/Developer/my-website
cd ~/Developer/my-website
```

**If using Cursor / VS Code / Windsurf:**
1. Create a folder called `my-website` anywhere you like (e.g. in Documents)
2. Open your editor → File → Open Folder → select `my-website`

### Step 2: Tell the AI What You Want

Open your AI assistant and describe your website in plain language. For example:

> "Create a personal website for me. My name is [your name], I'm a [your job]. I want a clean, modern design with: an intro section, my work experience, and contact info."

The AI will create HTML and CSS files in your project folder.

Keep going — ask for changes:
- "Make the color scheme warmer"
- "Make the font bigger"
- "Add a section for my photo"
- "Add a dark mode toggle"
- "How does this look on mobile? Optimize it"

You don't need to understand the code. Just describe what you want. If the result isn't right, say "That's not what I meant, I want..."

### Step 3: Preview in Your Browser

**Ask your AI assistant:**

> "Open this website in my browser so I can see it"

**Or do it manually:**
1. Open **Finder**
2. Navigate to your `my-website` folder
3. Double-click `index.html` — it opens in your browser

### Step 4: Iterate Until You're Happy

Preview, then go back to the AI and keep refining:

- "The title is too big, make it smaller"
- "Change the background to light gray"
- "Add an email icon next to the contact info"
- "Make it look like this site: [paste a URL you like]"

After each change, refresh your browser (**Command + R**) to see the update.

Take your time. No rush.

> **Tip:** If your project folder has files you don't want online (like `.DS_Store`), ask your AI assistant to create a `.gitignore` file.

> **At this point, your site is done on your computer. But only you can see it. Next, we'll put it on the internet.**

---

## 🚀 Phase 3: Put It Online

The goal: make your website accessible to everyone via a URL. Your AI assistant can help with most of this.

### Step 5: Install Git and Sign Up for GitHub

**Git** manages your code. **GitHub** stores it online. **Vercel** (next step) reads from GitHub to publish your site.

**Install Git** (Mac usually has it):

Open Terminal and type:
```bash
git --version
```
- If you see `git version 2.x.x` — you're good
- If a popup asks to install "Command Line Tools" — click Install, wait a few minutes

**Sign up for GitHub:**
1. Go to **github.com** → "Sign up"
2. Pick a username, enter your email, set a password
3. Verify your email
4. Done. Remember your username.

### Step 6: Create a GitHub Repository and Push Your Code

**First, create an empty project on GitHub:**
1. Log in to github.com → click **"+"** → **"New repository"**
2. Name it `my-website` (match your folder name)
3. Don't check any boxes — leave everything default (do NOT check "Add a README")
4. Click **"Create repository"**

**Then push your code.** Ask your AI assistant:

> "Push this project to GitHub. My username is [your username], the repository is my-website. I already created an empty repository."

It will configure Git and push for you. You may see a GitHub login popup — log in and authorize.

> If Git asks for a username and password instead of showing a popup, tell your AI assistant: "Help me set up GitHub authentication." It will walk you through it.

If anything goes wrong, paste the error to your AI assistant. It will fix it.

### Step 7: Deploy with Vercel

Vercel turns your GitHub code into a live website. Free.

1. Go to **vercel.com** → **"Sign Up"** → **"Continue with GitHub"**
2. Authorize Vercel to access your GitHub
3. Click **"Add New..."** → **"Project"**
4. Find `my-website` in the list → click **"Import"**
5. Leave settings as default → click **"Deploy"**
   If Vercel asks about a "Framework Preset", select **Other** or leave it blank.
6. Wait ~10 seconds. Done!

> Can't find your project? Click **"Adjust GitHub App Permissions"** and grant access.

### Step 8: Your Site Is Live!

Vercel gives you a URL like:
```
https://my-website-xxxxx.vercel.app
```

Open it. That's your website. The whole world can see it.

From now on, whenever you push code to GitHub, Vercel updates your site automatically within seconds.

---

## 🌐 Phase 4: Custom Domain (Optional)

The `.vercel.app` URL works fine. But if you want your own domain (like `yourname.com`), follow these steps whenever you're ready.

### Step 9: Buy a Domain

Recommended registrars:
- **Namecheap** (namecheap.com) — affordable, simple
- **Cloudflare** (cloudflare.com/products/registrar) — at-cost, no markup

Search for your domain, create an account, pay (~$10-15/year for .com).

### Step 10: Connect It in Vercel

1. Go to your project on vercel.com → **Settings** → **Domains**
2. Type your domain → click **Add**
3. Vercel shows DNS records to add. Copy these exactly — they are unique to your project. They will look something like:
   - **A record:** `76.76.21.21`
   - **CNAME:** `www` → `cname.vercel-dns.com`
4. Add these records in your domain registrar's DNS settings
5. Wait a few minutes to a few hours

Vercel handles HTTPS automatically.

> DNS confusing? Ask your AI assistant to walk you through it.

---

## Daily Workflow

Whenever you want to update your site:

1. Open your AI assistant in the project folder
2. Describe what you want to change
3. Preview in browser (Command + R to refresh)
4. Say "Push to GitHub"
5. Site updates in seconds

---

## FAQ

**Q: I messed up a command in Terminal.**
Press **Control + C** and try again.

**Q: I forgot where I left off.**
Ask your AI assistant: "Check the current state of this project."

**Q: The browser shows the old version after changes.**
Press **Command + Shift + R** to force refresh.

**Q: How do I quit my AI assistant?**
Claude Code: type `/exit`. Cursor/VS Code/Windsurf: just close the app.

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

Install the **[zero-dollar-website-skill](https://github.com/che-3/zero-dollar-website-skill)** for Claude Code — it walks you through the entire process interactively. Just say "I want to build a website" and it handles everything.

```bash
git clone https://github.com/che-3/zero-dollar-website-skill.git ~/.claude/skills/zero-dollar-website
```

---

## License

MIT — do whatever you want with this.

---

*Built by [@che-3](https://github.com/che-3). If this helped you, consider giving it a star.*
