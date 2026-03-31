# Portfolio Website Fix Design

Date: 2026-03-31

## Requirements

1. **Images missing** - placeholder images need to be replaced with actual screenshots
2. **404 error on click** - project links not working correctly
3. **Projects executable** - demo pages accessible via iframe + external link
4. **Accessible from other computers** - deploy to GitHub Pages

## Current State Analysis

### 404 Error Root Cause
- `src/pages/index.astro` line 44: uses `project.slug`
- Astro 6 content collection: `slug` property doesn't exist → returns `undefined`
- Featured Projects section (line 22): uses `project.id` → works correctly
- All Projects section: generates `/projects/undefined` links → 404

### Image State
- `public/images/*.png` files are 259 bytes (placeholder)
- User will capture and provide actual screenshots

### Project Hosting State
- All projects in `C:\Users\admin\Desktop\HI\`:
  - DefenceGame, GameDevToolkit, GreedDungeon, Pathfinder, ShotUp (Unity)
  - TestWebPage (Express.js server)
  - TestWebText (simple folder)
  - Test0330 (simple folder)
  - WebMake/community-board (Next.js)
- No GitHub deployment yet
- GitHub username: `rlaehdduf`

### GitHub Pages Workflow
- `.github/workflows/deploy.yml` exists
- Trigger: push to `main` branch
- Current branch: `master` (needs rename)
- `astro.config.mjs`: site set to `yourusername.github.io` (needs update)

## Solution Design

### 1. Fix 404 Error
**Change:** `src/pages/index.astro` line 44
```diff
- slug={project.slug}
+ slug={project.id}
```

**Additional:** Fix base path for links
- Current links: `/projects/[slug]`
- With base `/portfolio`: should be `/portfolio/projects/[slug]`
- Astro handles this automatically when `Astro.url` is used

### 2. Image Replacement
- Keep current folder structure: `public/images/[project-name].png`
- User captures screenshots → saves to matching filenames
- No code changes needed

### 3. Project Demo Deployment

#### Unity Projects (5 projects)
- DefenceGame, GreedDungeon, Pathfinder, ShotUp: WebGL build → GitHub Pages
- GameDevToolkit: Unity Package → no demo, GitHub repo link only
- **Method:** Use unity-cli skill to build WebGL automatically
- **Output:** Build to `Builds/WebGL/[ProjectName]` folder
- **Deploy:** Create separate GitHub repo for each, push WebGL build, enable Pages

#### Web Projects
| Project | Type | Demo Solution |
|---------|------|---------------|
| TestWebPage | Express.js server | No demo (server required), GitHub repo link only |
| WebMake/community-board | Next.js | Static export → GitHub Pages |
| Test0330 | Static files | Check content → GitHub Pages if static |
| TestWebText | Static files | Check content → GitHub Pages if static |

#### Demo URLs (after deployment)
- Unity WebGL: `https://rlaehdduf.github.io/[project-name]`
- Next.js static: `https://rlaehdduf.github.io/community-board`

### 4. Portfolio GitHub Pages Deployment

**Steps:**
1. Rename branch: `master` → `main`
2. Update `astro.config.mjs`: change `yourusername` to `rlaehdduf`
3. Push to GitHub: `https://github.com/rlaehdduf/portfolio`
4. Enable GitHub Pages in repo settings
5. Other computers access: `https://rlaehdduf.github.io/portfolio`

### 5. Project Content Updates

Update each project's `.md` file with `demo` URL:
```yaml
demo: https://rlaehdduf.github.io/[project-name]
```

## Implementation Plan

### Phase 1: Code Fixes
1. Fix `index.astro` slug → id
2. Update `astro.config.mjs` username
3. Rename branch master → main
4. Update project md files with demo URLs

### Phase 2: Unity WebGL Builds
1. Use unity-cli skill to build each Unity project
2. Create GitHub repos for each build
3. Push WebGL builds
4. Enable GitHub Pages

### Phase 3: Web Project Deployment
1. Export Next.js project as static
2. Deploy static web projects to GitHub Pages
3. Update demo URLs in portfolio

### Phase 4: Portfolio Deployment
1. Push portfolio to GitHub
2. Enable GitHub Pages
3. Test accessibility from other computers

### Phase 5: Images
1. User captures project screenshots
2. Save to `public/images/` folder
3. Rebuild portfolio

## User Responsibilities

1. Provide project screenshots
2. Enable GitHub Pages in each repo (GitHub web UI)
3. Provide GitHub token if needed for automated push

## Automation Scope

**Automated by tool:**
- 404 fix (code edit)
- Config updates
- Branch rename
- Unity WebGL builds
- Static exports
- Git operations (with token)

**Manual by user:**
- Screenshot capture
- GitHub Pages activation in web UI
- GitHub token provision