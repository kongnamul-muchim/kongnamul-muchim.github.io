# Portfolio Website Fix Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Fix 404 errors, deploy projects to GitHub Pages, make portfolio accessible from other computers.

**Architecture:** Portfolio site (Astro) + Unity WebGL builds + Next.js static export → all deployed to GitHub Pages with iframe embedding.

**Tech Stack:** Astro 6, Unity WebGL, Next.js static export, GitHub Pages

---

## File Structure

### Modified Files
- `src/pages/index.astro:44` - Fix slug → id
- `astro.config.mjs:6` - Update username
- `src/content/projects/*.md` - Add demo URLs

### Created Files (Unity WebGL Builds)
- `C:\Users\admin\Desktop\HI\DefenceGame\Builds\WebGL\DefenceGame\`
- `C:\Users\admin\Desktop\HI\GreedDungeon\Builds\WebGL\GreedDungeon\`
- `C:\Users\admin\Desktop\HI\Pathfinder\Builds\WebGL\Pathfinder\`
- `C:\Users\admin\Desktop\HI\ShotUp\Builds\WebGL\ShotUp\`

### Created Files (Web Projects)
- `C:\Users\admin\Desktop\HI\WebMake\community-board\out\` - Next.js static export

---

## Task 1: Fix 404 Error (slug → id)

**Files:**
- Modify: `C:\Users\admin\Desktop\HI\Projects\portfolio\src\pages\index.astro:44`

- [ ] **Step 1: Edit index.astro**

Change line 44 from `project.slug` to `project.id`:

```diff
- slug={project.slug}
+ slug={project.id}
```

- [ ] **Step 2: Build and verify**

Run: `npm run build`
Expected: Build succeeds, no errors

- [ ] **Step 3: Check dist output**

Run: `grep "href=\"/projects/undefined\"" dist/index.html`
Expected: No matches (undefined links fixed)

- [ ] **Step 4: Commit**

```bash
git add src/pages/index.astro
git commit -m "fix: change project.slug to project.id for All Projects section"
```

---

## Task 2: Update Astro Config

**Files:**
- Modify: `C:\Users\admin\Desktop\HI\Projects\portfolio\astro.config.mjs:6`

- [ ] **Step 1: Edit astro.config.mjs**

Change line 6:

```diff
- site: 'https://yourusername.github.io',
+ site: 'https://rlaehdduf.github.io',
```

- [ ] **Step 2: Build and verify**

Run: `npm run build`
Expected: Build succeeds

- [ ] **Step 3: Commit**

```bash
git add astro.config.mjs
git commit -m "config: update GitHub username to rlaehdduf"
```

---

## Task 3: Rename Branch (master → main)

**Files:**
- Git branch operation

- [ ] **Step 1: Rename local branch**

Run: `git branch -m master main`
Expected: Branch renamed successfully

- [ ] **Step 2: Verify branch name**

Run: `git branch`
Expected: Shows `main` as current branch

---

## Task 4: Build Unity WebGL (DefenceGame)

**Files:**
- Create: `C:\Users\admin\Desktop\HI\DefenceGame\Builds\WebGL\DefenceGame\`

**Requires:** @skill:unity-cli

- [ ] **Step 1: Build WebGL using unity-cli**

Use unity-cli skill to build DefenceGame to WebGL:

```bash
# unity-cli command for WebGL build
# Project path: C:\Users\admin\Desktop\HI\DefenceGame
# Output: Builds/WebGL/DefenceGame
```

Expected: WebGL build created in `Builds/WebGL/DefenceGame/`

- [ ] **Step 2: Verify build output**

Run: `ls Builds/WebGL/DefenceGame/`
Expected: Contains `index.html` and Build files

---

## Task 5: Build Unity WebGL (GreedDungeon)

**Files:**
- Create: `C:\Users\admin\Desktop\HI\GreedDungeon\Builds\WebGL\GreedDungeon\`

**Requires:** @skill:unity-cli

- [ ] **Step 1: Build WebGL using unity-cli**

Project path: `C:\Users\admin\Desktop\HI\GreedDungeon`
Output: `Builds/WebGL/GreedDungeon`

- [ ] **Step 2: Verify build output**

Run: `ls Builds/WebGL/GreedDungeon/`
Expected: Contains `index.html` and Build files

---

## Task 6: Build Unity WebGL (Pathfinder)

**Files:**
- Create: `C:\Users\admin\Desktop\HI\Pathfinder\Builds\WebGL\Pathfinder\`

**Requires:** @skill:unity-cli

- [ ] **Step 1: Build WebGL using unity-cli**

Project path: `C:\Users\admin\Desktop\HI\Pathfinder`
Output: `Builds/WebGL/Pathfinder`

- [ ] **Step 2: Verify build output**

Run: `ls Builds/WebGL/Pathfinder/`
Expected: Contains `index.html` and Build files

---

## Task 7: Build Unity WebGL (ShotUp)

**Files:**
- Create: `C:\Users\admin\Desktop\HI\ShotUp\Builds\WebGL\ShotUp\`

**Requires:** @skill:unity-cli

- [ ] **Step 1: Build WebGL using unity-cli**

Project path: `C:\Users\admin\Desktop\HI\ShotUp`
Output: `Builds/WebGL/ShotUp`

- [ ] **Step 2: Verify build output**

Run: `ls Builds/WebGL/ShotUp/`
Expected: Contains `index.html` and Build files

---

## Task 8: Export Next.js Static (community-board)

**Files:**
- Create: `C:\Users\admin\Desktop\HI\WebMake\community-board\out\`

- [ ] **Step 1: Update next.config.mjs for static export**

Modify `C:\Users\admin\Desktop\HI\WebMake\community-board\next.config.mjs`:

```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  output: 'export',
  trailingSlash: true,
}

export default nextConfig
```

- [ ] **Step 2: Build static export**

Run: `npm run build` (in community-board directory)
Expected: `out/` folder created with static files

- [ ] **Step 3: Verify export**

Run: `ls out/`
Expected: Contains `index.html` and static assets

---

## Task 9: Update Project Content Files (Demo URLs)

**Files:**
- Modify: `src/content/projects/*.md`

- [ ] **Step 1: Update defencegame.md**

Add demo URL:

```yaml
---
title: DefenceGame
type: unity
description: Unity로 개발한 디펜스 게임. 적들의 공격을 방어하는 타워 디펜스 스타일 게임.
image: /images/defencegame.png
technologies:
  - Unity
  - C#
  - Tower Defense Mechanics
github: https://github.com/rlaehdduf/DefenceGame
demo: https://rlaehdduf.github.io/DefenceGame
featured: true
---
```

- [ ] **Step 2: Update greeddungeon.md**

Add demo URL:

```yaml
demo: https://rlaehdduf.github.io/GreedDungeon
```

- [ ] **Step 3: Update pathfinder.md**

Add demo URL:

```yaml
demo: https://rlaehdduf.github.io/Pathfinder
```

- [ ] **Step 4: Update shotup.md**

Add demo URL:

```yaml
demo: https://rlaehdduf.github.io/ShotUp
```

- [ ] **Step 5: Verify gamedevtoolkit.md**

Verify file has no `demo` field (Unity Package, not executable).
No changes needed.

- [ ] **Step 6: Verify testwebpage.md**

Verify file has no `demo` field (Express.js server).
No changes needed.

- [ ] **Step 7: Update webmake.md**

Add demo URL for community-board:

```yaml
demo: https://rlaehdduf.github.io/community-board
```

- [ ] **Step 8: Verify test0330.md, testwebtext.md**

Verify files have no `demo` field (non-web projects).
No changes needed.

- [ ] **Step 9: Commit**

```bash
git add src/content/projects/*.md
git commit -m "content: add demo URLs to project content files"
```

---

## Task 10: Prepare Git Remote for Portfolio

**Files:**
- Git remote configuration

**User Action Required:** Create GitHub repo `rlaehdduf/portfolio` on GitHub web UI

- [ ] **Step 1: Check existing remotes**

Run: `git remote -v`
Expected: Empty or no origin

- [ ] **Step 2: Add remote URL (after user creates repo)**

Run: `git remote add origin https://github.com/rlaehdduf/portfolio.git`
Expected: Remote added successfully

- [ ] **Step 3: Verify remote**

Run: `git remote -v`
Expected: Shows origin URL

---

## Task 11: Push Portfolio to GitHub

**Files:**
- Git push operation

**Requires:** User provides GitHub PAT or has authentication configured

- [ ] **Step 1: Push to GitHub**

Run: `git push -u origin main`
Expected: All commits pushed successfully

- [ ] **Step 2: Verify push**

Run: `git log origin/main --oneline -5`
Expected: Shows recent commits

---

## Task 12: Final Build and Verify

**Files:**
- Verify final portfolio build

- [ ] **Step 1: Build portfolio**

Run: `npm run build`
Expected: Build succeeds with all demo URLs

- [ ] **Step 2: Preview locally**

Run: `npm run preview`
Expected: Site preview works at localhost:4321/portfolio

- [ ] **Step 3: Verify all project links**

Check that:
- Featured Projects links work
- All Projects links work (no `/projects/undefined`)
- Demo URLs are correct

---

## User Manual Tasks

After implementation, user must:

1. **Create GitHub repositories:**
   - `rlaehdduf/portfolio` (for portfolio site)
   - `rlaehdduf/DefenceGame` (for WebGL build)
   - `rlaehdduf/GreedDungeon` (for WebGL build)
   - `rlaehdduf/Pathfinder` (for WebGL build)
   - `rlaehdduf/ShotUp` (for WebGL build)
   - `rlaehdduf/community-board` (for Next.js static)
   - `rlaehdduf/GameDevToolkit` (Unity Package, source only)
   - `rlaehdduf/TestWebPage` (Express.js, source only)

2. **Enable GitHub Pages** (in each repo Settings > Pages):
   - Portfolio: `https://rlaehdduf.github.io/portfolio`
   - DefenceGame: `https://rlaehdduf.github.io/DefenceGame`
   - GreedDungeon: `https://rlaehdduf.github.io/GreedDungeon`
   - Pathfinder: `https://rlaehdduf.github.io/Pathfinder`
   - ShotUp: `https://rlaehdduf.github.io/ShotUp`
   - community-board: `https://rlaehdduf.github.io/community-board`

3. **Push WebGL builds to GitHub:**
   - Copy each `Builds/WebGL/[ProjectName]` contents to respective repo
   - Push to GitHub

4. **Capture screenshots:**
   - Save to `public/images/[project-name].png`

---

## Notes

- Test0330, TestWebText are not web projects → no demo
- GameDevToolkit is Unity Package → no demo
- TestWebPage is Express.js server → no demo on GitHub Pages
- Unity WebGL builds take significant time (5-15 minutes per project)
- GitHub Pages activation is manual (user must do in web UI)