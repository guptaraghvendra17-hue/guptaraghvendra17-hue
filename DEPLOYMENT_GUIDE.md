# 🚀 Animated GitHub Profile — Deployment & Setup Guide

This guide walks you through deploying your animated GitHub profile portfolio, recreating the exact layout, animations, visuals, 3D contribution city, and automation of the reference profile.

---

## 📁 Repository Structure Overview

Your profile repository contains the following files in `C:\Users\gupta\OneDrive\Desktop\GitHub`:

```text
├── README.md                              # Main profile document rendering on your GitHub
├── hero.svg                               # Viewfinder hero with glowing gradient name, cycling roles, live status
├── ninja-way.svg                          # What I build card featuring character art & capability rows
├── jutsu-stack.svg                        # Technology arsenal with spotlight beam & grouped tech chips
├── ninja-id.svg                           # Swinging lanyard ID badge + counting-up dashboard & bar chart
├── connect.svg                            # Pointing avatar with neon sign & interactive link cards
├── about-life.svg                         # Companion 2-panel card (browser UI + hobbies carousel with daily rings)
├── stack.svg                              # Companion 3-orbit atom tech stack with orbiting moons
├── id-dashboard.svg                       # Companion developer dashboard version
├── team7-dance.gif                        # Chibi animation divider
├── rasengan-run.gif                       # Chibi running animation above contribution city
├── chibi-walk.gif                         # Chibi walking animation at profile footer
├── profile-3d-contrib/                    # 3D isometric contribution city SVGs (pre-seeded + auto-updated)
│   ├── profile-night-view.svg
│   ├── profile-green-animate.svg
│   └── ...
└── .github/
    └── workflows/
        ├── profile-3d.yml                 # Daily workflow that generates your 3D night skyline
        └── github-snake.yml               # Daily workflow that generates the contribution snake
```

---

## 🔑 Username & Account Note

- If your active GitHub username is `raghvendra-gupta-46b20837b`, create the repository `raghvendra-gupta-46b20837b/raghvendra-gupta-46b20837b`.
- If your active GitHub username is `guptaraghvendra17-hue`, create the repository `guptaraghvendra17-hue/guptaraghvendra17-hue`.
- The workflows and SVGs have been designed with `${{ github.repository_owner }}` and adaptable links so everything works seamlessly.

---

## 🛠️ Step-by-Step Deployment Instructions

### Step 1: Create the Special "Magic" Repository
1. Log in to [GitHub](https://github.com).
2. Click the **+** icon in the top-right corner and select **New repository**.
3. In the **Repository name** field, type your exact GitHub username (e.g. `raghvendra-gupta-46b20837b` or `guptaraghvendra17-hue`).
4. GitHub will show a banner: *"You found a secret! [username]/[username] is a special repository that provides a README.md on your profile."*
5. Set visibility to **Public**.
6. Leave "Initialize this repository with a README" unchecked (since you already have the complete set of files ready locally).
7. Click **Create repository**.

---

### Step 2: Push the Files to GitHub
Open your terminal (PowerShell or Command Prompt) in `C:\Users\gupta\OneDrive\Desktop\GitHub`:

```powershell
cd "C:\Users\gupta\OneDrive\Desktop\GitHub"

# Initialize git repository
git init

# Add all generated files and workflows
git add .

# Commit
git commit -m "feat: initial animated profile portfolio"

# Set branch to main
git branch -M main

# Add your remote (replace with your repo URL)
git remote add origin https://github.com/<YOUR-USERNAME>/<YOUR-USERNAME>.git

# Push to GitHub
git push -u origin main
```

---

### Step 3: Configure GitHub Actions Permissions
For the 3D contribution city and snake workflows to automatically commit their generated SVGs back to your repository:

1. In your profile repository on GitHub, navigate to **Settings** (top tab).
2. In the left sidebar, click **Actions** ➔ **General**.
3. Scroll down to **Workflow permissions**.
4. Select **Read and write permissions**.
5. Check the box for **Allow GitHub Actions to approve pull requests** (if available).
6. Click **Save**.

---

### Step 4: Run the 3D Contribution Workflow
1. Go to the **Actions** tab in your repository.
2. In the left sidebar, click **3D contribution city 🌃**.
3. Click the **Run workflow** dropdown button on the right, and select **Run workflow**.
4. The workflow will run (~1 minute). Once finished, it generates and commits your latest 3D commit city into the `profile-3d-contrib/` folder.
5. The workflow is scheduled to run automatically every night at 18:00 UTC (`0 18 * * *`).

---

### Step 5: Verify Your Live GitHub Profile
1. Navigate to your GitHub profile URL: `https://github.com/<YOUR-USERNAME>`.
2. Inspect each section:
   - **Hero:** Check the typing title, cycling roles, and viewfinder frame.
   - **What I Build:** Check the capability rows and character floating animation.
   - **Tech Arsenal:** Check the spotlight beam and grouped tech chips.
   - **Registration & Dashboard:** Check the swinging lanyard, counting numbers, and project bar chart.
   - **S-Rank Missions:** Check the project table links.
   - **Contribution Village:** Check the isometric 3D city buildings.
   - **Connect:** Check the pointing character and clickable social links.

---

## ⚡ Troubleshooting & Pro Tips

### 1. The GitHub Image Cache Trap (`?v=1` Trick)
- **Problem:** You update an SVG, push the commit, but GitHub continues showing the previous version.
- **Cause:** GitHub's Camo proxy caches README images aggressively.
- **Solution:** Bump the version query parameter in `README.md` (e.g. `hero.svg?v=1` ➔ `hero.svg?v=2`). Commit and push the SVG first, then commit and push `README.md`. Hard refresh your browser (`Ctrl + Shift + R`).

### 2. Workflow Failed with "Permission Denied"
- Verify that **Settings ➔ Actions ➔ General ➔ Workflow permissions** is set to **Read and write permissions**.

### 3. Switching Between Themes
- If you ever prefer the companion two-panel layout from the PDF guide, simply change `./ninja-way.svg?v=1` to `./about-life.svg?v=1`, `./jutsu-stack.svg?v=1` to `./stack.svg?v=1`, and `./ninja-id.svg?v=1` to `./id-dashboard.svg?v=1` in `README.md`. Both complete versions are pre-built and ready in your repository!

