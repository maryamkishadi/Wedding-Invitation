# Noor Alam Wedding Invitation: GitHub Pages Handoff

## 1. Overview
A single-page animated wedding invitation (closed envelope → opens → card with hero video, Mehndi / Barat & Nikkah / Walima tabs, timeline, countdown, location).
Status: final, approved by the owner (design lock v9 plus later approved edits). **Do not change visuals, text, animations or effects.**

## 2. Folder contents (verified)
```
Noor-Alam-Invitation-Site/
├── index.html        ← the invitation (entry point)
├── support.js        ← required runtime, loaded by index.html (do not edit)
├── assets/           ← 19 files, all referenced by index.html
│   ├── hero-bride2.mp4, hero.png
│   ├── envelope-ivory.png, envelope-noseal-ivory2.png, seal-wax2-ivory.png, glow-outline2.png
│   ├── invite-mehndi2-thu.png, invite-barat-alt.png, invite-walima-final.png
│   ├── mehndi-venue-decor2.png, barat-venue.png, walima-venue2.png, bride2.png
│   ├── butterfly-gold4.png, butterfly-pink.png
│   └── breeze-mask2/-m/-b/-w.png
└── Wedding_Invitation_GitHub_Handoff.md
```
All asset paths are **relative** (`assets/...`, `./support.js`), so it works under a GitHub Pages sub-path (`/repo-name/`). All 19 referenced assets were checked to exist.

## 3. Technology
- Plain static site: HTML + inline CSS + JavaScript. **No build step, no npm, no framework install.**
- `support.js` is the bundled runtime that renders `index.html` (it contains the page's `<x-dc>` markup).
- Only external dependency: Google Fonts (Cormorant Garamond, Pinyon Script, Amiri), loaded from `fonts.googleapis.com`. Needs internet; falls back to system serif if blocked.
- External links: Google Maps (Mehndi/Barat/Walima venue buttons; Walima uses `maps.app.goo.gl/YQBCSzR7KAMyQspw9`).

## 4. Repository setup
1. Create a **public** GitHub repo (e.g. `noor-alam-invitation`).
2. Upload the **contents** of `Noor-Alam-Invitation-Site/` to the repo root, so `index.html`, `support.js` and `assets/` sit at the top level (not inside an extra folder).
3. Keep the `assets` folder name and file names exactly (names are case-sensitive on GitHub).
4. Total size is about 25 MB; each file is under GitHub's 100 MB limit.

## 5. Deploy to GitHub Pages
1. Repo → **Settings → Pages**.
2. Source: **Deploy from a branch**; Branch: `main`, folder `/ (root)`; Save.
3. Wait 1–3 minutes. URL format: `https://<github-username>.github.io/<repo-name>/`
4. No build command or config file is needed.

## 6. Assets, video, fonts, animation
- The hero video `hero-bride2.mp4` (~3.3 MB) is muted, plays once after the envelope opens, and holds its last frame. `hero.png` is its poster.
- Images are loaded by relative path; do not rename or move.
- Animations are CSS and JavaScript inside `index.html`; nothing extra to host.

## 7. Testing checklist (desktop and mobile)
- [ ] Closed envelope shows with wax seal; tap opens slowly, card appears.
- [ ] Hero video plays once and fades into the cream background.
- [ ] Both butterflies fly; gold faces up, pink is smaller.
- [ ] Mehndi / Barat & Nikkah / Walima tabs switch; each card image shows.
- [ ] Scratch date cards reveal; countdown runs.
- [ ] Timeline reveals as you scroll (bride picture has no box behind it).
- [ ] Each Location button opens the right Google Maps link.
- [ ] No red errors in the browser console (F12).
- [ ] Test on iPhone Safari and Android Chrome.

## 8. Troubleshooting
- **Blank screen:** `support.js` or `assets/` was not uploaded at the repo root, or the page was opened as a downloaded single file out of its folder. Check that `index.html` and `support.js` are in the same folder; open the console for 404s.
- **Missing images / video:** file name case mismatch or wrong folder. Compare with section 2.
- **Fonts look plain:** Google Fonts blocked or offline.
- **Video won't autoplay on some phones:** it starts after the user taps the envelope, which counts as a gesture; low-power mode can still block it.
- **Old version shows after update:** hard refresh (Ctrl+Shift+R) or wait for Pages to rebuild.

## 9. Update and redeploy
1. Replace only the changed file(s) in the repo (commit to `main`).
2. Pages redeploys automatically in 1–3 minutes.
3. Keep a copy of the previous `index.html` before editing.

## 10. Known limitations / not verified
- **Not deployed:** this package has not been published to GitHub Pages by me; deployment and the live URL are untested.
- A background `{{ r.art }}` message appears when packing a single-file copy; it is a template placeholder, not a missing file.
- A browser console message "use failed to load" from the timeline SVG art was seen earlier; it did not stop rendering.
- Tested only in the design tool's preview, not on real phones.
- Opening `index.html` by double-click (file://) should work, but video and fonts are most reliable when served by Pages or a local server.

## Deployment checklist
- [ ] Repo created, public
- [ ] Folder contents uploaded to repo root
- [ ] Pages enabled (main, /root)
- [ ] Live URL opened; checklist in section 7 passed

Expected URL: `https://<github-username>.github.io/<repo-name>/`
