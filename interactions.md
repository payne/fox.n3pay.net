# Interactions Log

## 2026-06-06

**User Request:**
- Create an 11ty website that easily deploys to CloudFlare
- Index page should state N3PAY has a PicoFOX with link to https://store.ai6ym.radio/pages/picofox
- Contact info: Matt.N3PAY@gmail.com, cell: 402-208-8787
- Current PicoFOX deployment location: storage drawer

**Actions Taken:**
- Created interactions.md to record all interactions
- Created 11ty project structure:
  - `package.json` - project configuration with 11ty dependency
  - `.eleventy.js` - 11ty configuration
  - `src/index.njk` - main index page
  - `src/_includes/base.njk` - base layout template
  - `src/css/style.css` - basic styling
  - `.gitignore` - excludes node_modules and _site
- Installed dependencies and verified build works

---

## 2026-06-06 (Update 2)

**User Request:**
- Use fox1-location.json from GitHub to determine if fox is in storage
- If deployed, show deployment time and Google Maps link (opens in new window)
- JSON URL: https://raw.githubusercontent.com/payne/fox1-location/refs/heads/main/fox1-location.json

**JSON Structure:**
```json
{
  "storage": false,
  "latitude": 40.7128,
  "longitude": -74.0060,
  "timeLocationUpdated": "2026-06-06T14:00:18.914Z"
}
```

**Actions Taken:**
- Updated index.njk to fetch JSON client-side
- If `storage: true` - shows "Storage drawer" with yellow styling
- If `storage: false` - shows deployment date/time and Google Maps link (target="_blank")
- Updated CSS with distinct styling for storage vs deployed states

---

**CloudFlare Pages Deployment:**
1. Push this repo to GitHub/GitLab
2. Go to CloudFlare Pages dashboard
3. Connect your repository
4. Build settings:
   - Build command: `npm run build`
   - Build output directory: `_site`
5. Deploy
