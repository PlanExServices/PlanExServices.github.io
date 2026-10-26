# 🛠️ The App Workshop

A mobile-first React Native + Expo app that walks **4th graders (ages ~9–10)** through designing the **complete foundation of a real app** — starting from a problem *they* have seen in their own world.

A robot buddy named **Bit** guides kids through 11 short "missions" (the command prompts) — built **originality-first**: a "✏️ My Own Answer" input always comes *before* the quick picks, and after every pick Bit asks a 🔥 micro-question ("When did you SEE it happen — even 3 words?") whose answer feeds the final script. At the end they earn a saved **App Portfolio**: blueprint + sketched first screen + 30-second pitch + test plan + a **Final Script** in a professional format — with badges, an inventor to-do list, and a **money & time budget plan**, because real builders plan for it.

Built following the operating rules of the *Master Build Agent Script v14.3.0* (smallest complete vertical slice, no fake controls, honest evidence, on-device-only data for kids).

---

## 🎯 What a kid experiences

| # | Mission | Prompt style |
|---|---------|--------------|
| 1 | 🐛 **Spot the Problem** | Tap a real problem (forgotten homework, left-out classmates, messy supplies, unsafe crossings…) or type their own |
| 2 | 🦸 **Find Your Heroes** | Who does this app help? (me, my class, my family, my team, my town…) |
| 3 | 💡 **The Big Idea** | A mad-lib "superpower sentence": *When someone ___, my app ___, so that ___* — built from tappable word tiles |
| 4 | 🧠 **Brain Check** | What does the app remember? (nothing / notes / scores / drawings) |
| 5 | 📶 **Where & When** | Offline (like at school), online, or both |
| 6 | 🚀 **Sharing Plan** | Demo on my device → class expo → **the whole world (app store someday)** |
| 7 | 💰 **Money & Time Plan** | **The budget prompt**: $0 free tools, ~$25, ~$100/yr, find a sponsor, or type an amount — plus minutes-per-week time chips |
| 8 | 🏷️ **Name It!** | Three original name suggestions (reshuffle for more) or invent your own |
| 9 | 🎨 **Sketch Your Screen!** | **Draw the first screen in-app** on a sticker-style phone frame — 6 pen colors, 3 brush sizes, 12 emoji stickers, undo & clear (skippable for paper lovers) |
| 10 | 🎤 **Build Your Pitch** | Tap-to-build 30-second pitch (best part + "the ask"), previewed live; practice mode with a 30-second countdown |
| 11 | 🧪 **Test Squad Plan** | Plan a real user test: pick a tester, the mission, what to watch for, and what "it worked" means |

**Finish line:** 🎉 an **App Portfolio** — every answer (including all the micro-details) in sticker-style cards, the sketched screen rendered back inside a phone frame, the full pitch with a practice timer, the test plan, 9 badges, confetti, and the **🏁 Final Script**: Name · Tag Line · Description (hard-capped at 120 words, unit-tested) · Stack · What sets it apart — auto-assembled from the kid's own words, plus a grown-up spec in the Master Build intake field format. Portfolios are saved on the device under **My Portfolios** (view or delete anytime).

**Navigation:** every screen has a big, chunky **⬅️ back button** top-left (52×52 target): the mission screen steps back one mission at a time (then home), a portfolio returns to wherever it was opened from, and the saved list returns home. No dead ends, no stack pile-ups.

### 📱 Mobile-only product
The App Workshop targets phones only (React Native + Expo). The browser build (`npm run web`) is a labeled **dev preview** — the home screen says so — used for testing and this workspace's live preview; it is not a product surface.

### 📤 Export & share (from the portfolio screen)
- **🖨️ Print my worksheet** — an ink-friendly, self-contained printable: the full portfolio in boxes, **the sketched screen as vector SVG**, the pitch, the test plan, badge stickers, a to-do checklist, an *Inventor: ____* line, and a **"Draw your app's first screen!"** box for paper sketching. Works on phones (native print dialog) and web (print dialog — pick "Save as PDF" there to make a file).
- **📄 Save as PDF** (phone only) — generates a real PDF of the worksheet and opens the native share sheet (save to Files, Photos, AirDrop, messages…).
- **📋 Share the words** — the whole portfolio as friendly text (incl. pitch and test plan) via the native share sheet (phone) or copy-to-clipboard (web), with a visible-selectable-text fallback when a preview window blocks the clipboard.
- Kid-typed text is HTML-escaped before entering any export; blocked preview windows get honest, plain-language messages — never silent failures.

### Why kids will gravitate to it
- **Bit the robot** — bobbing mascot with speech bubbles, never a dry form label
- **Sticker-style design** — chunky outlines, offset shadows, bold gradient background, giant rounded emoji buttons (68px+ touch targets)
- **Game framing** — missions, a rocket progress bar, word tiles, badges, one-shot confetti
- **Mad-lib sentence builder** that assembles live on screen as they tap
- **Real-world budget talk, kid-sized** — including honest notes that store fees change and a grown-up should check

---

## 🗺️ How the missions map to a professional build intake

The prompts are kid-friendly versions of a real product intake spec (in-app: **For grown-ups 🔒** on the home screen):

| Mission (kid language) | Master Build intake field |
|---|---|
| Spot the Problem | Core-outcome seed (the issue worth fixing) |
| Find Your Heroes | Primary user & surface |
| The Big Idea sentence | Input → transformation → observable result |
| Brain Check | Data classification (default: anonymous / on-device) |
| Where & When | Connectivity / operating mode |
| Sharing Plan | Delivery target |
| Money & Time Plan | Cost & delivery budgets (§1.7) |
| Name It | Project naming |
| Sketch Your Screen | First-screen wireframing (saved as vector strokes) |
| Build Your Pitch | Value proposition / 30-second elevator pitch |
| Test Squad Plan | User-testing plan (tester, task, observation, success criteria) |

**Budget facts note:** the fee hints shown to kids (~$25 one-time Google Play, ~$99/yr Apple) are rounded, volatile facts — verify current prices before any real submission.

---

## 🔒 Privacy by design (kids' app)

- **No accounts. No ads. No analytics. No network calls. Nothing collected.**
- All blueprints live in on-device storage (`AsyncStorage`) and can be deleted in-app.
- If storage is unavailable (e.g. a sandboxed preview window), the app degrades to a clearly-labeled in-memory "preview mode" instead of failing or pretending to save.
- COPPA-conscious: because nothing is collected or transmitted, there is no children's data to protect in the cloud.

---

## 🚀 Run it

```bash
cd app-workshop
npm install

# Phone (iOS/Android) with Expo Go:
npm start          # then scan the QR code

# Web dev companion:
npm run web

# Static web export + local preview server:
npm run export:web
npm run preview:web   # serves on 0.0.0.0:8080
```

**Verify:**
```bash
npm run typecheck   # tsc --noEmit
npm test            # 15 domain unit tests (vitest)
```

## 📁 Structure

```
src/
  app/            expo-router screens: index (home), mission (the 8-prompt
                  wizard), blueprint (result), blueprints (saved list), +not-found
  components/     Bit, BigButton, ChoiceCard, Pill, ProgressBar, Confetti,
                  Card, ScreenBg, GrownUpsModal, ConfirmDialog
  lib/
    domain/       pure TS, no RN imports (port boundary): steps catalog,
                  blueprint builder, name generator, kid-input sanitizer
    storage.ts    on-device persistence w/ honest memory fallback
    theme.ts      sticker-style design tokens
tests/            vitest domain tests
scripts/          serve-web.mjs (static preview server)
```

## ✅ Verification snapshot (this build)

| Gate | Result |
|---|---|
| Install (npm) | ✅ clean dependency set (template extras removed) |
| `tsc --noEmit` | ✅ PASS |
| Unit tests (vitest) | ✅ 34/34 PASS (missions, sparks, tagline, **120-word description cap**, differentiator, grown-up spec, **typing-safe space handling**, sketch SVG, export escaping) |
| Web export (static, dev-only surface) | ✅ 6 routes |
| Web preview smoke | ✅ 200 on `/`, per-route HTML, JS bundle, favicon |
| Browser E2E (Playwright, Chromium) | ✅ 13/13 — incl. the creativity nudge (Next stays locked until the kid writes their own detail) in normal + sandboxed contexts |
| Full-flow E2E (Playwright) | ✅ 50/50 — all 11 missions incl. **keystroke-level typing with spaces preserved**, back navigation, drawing + sticker, live pitch, practice countdown, portfolio with **Final Script card**, clipboard-verified share text, reload persistence, delete; 0 console/page errors |
| Contrast pass | ✅ gradient darkened so white-on-background text ≥ 4.5:1 (AA); no white-on-white placeholders; small pink labels ≥ 5:1 on white |
| Native device/simulator gates | ⛔ not run in this workspace (no simulator/device) — run `npm start` + Expo Go, or EAS build, on your machine |

Reproduce the browser gates: `npm run e2e:web` (needs `npm i -D playwright` + `npx playwright install chromium`).

**Honest limitations:** store-fee numbers are rounded and volatile; VoiceOver/TalkBack and physical-device testing still need a pass on real hardware.

## 🌱 Roadmap ideas
- Teacher mode / class gallery (would require a privacy review before any data leaves the device)
- "Build it" level that scaffolds an actual screens-from-blueprint exercise
- Grown-up data backup: export/import all blueprints as a single JSON file
