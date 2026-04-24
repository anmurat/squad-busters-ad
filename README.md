# Squad Busters — Playable Ad

A fully self-contained, single-file HTML5 playable advertisement for **Squad Busters** by Supercell. No build tools, no dependencies, no backend — just open the file and play.

---

## Demo

Open `squad_busters_ad.html` in any modern browser.

| URL parameter | Effect |
|---|---|
| *(none)* | Preview mode — presenter bar visible for QA |
| `?preview=false` | Production mode — presenter bar hidden |
| `?screen=0` | Jump to Hook screen |
| `?screen=1` | Jump to Gameplay screen |
| `?screen=2` | Jump to End Card |

---

## Features

### Gameplay
- 🕹️ **Joystick drag-to-move** — works on touch and mouse; full-width drag zone
- ⚔️ **Proximity auto-attack** — walk near enemies to hit them automatically
- 👾 **Wave system** — defeat Wave 1 → Wave 2 banner → new enemies spawn
- 🧲 **Coin magnet** — walk near dropped coins, they fly to you
- 💥 **Combo counter** — chain hits for DOUBLE / TRIPLE / RAMPAGE badges
- 🔴 **Danger aura** — enemy ring pulses red when hero is close
- 📉 **HP bar color shift** — green → yellow → red as enemy weakens
- 🪙 **Gold chest** — tap to open after clearing all enemies; triggers character select
- 🎭 **Character select** — choose Shelly, Goblin, or Barbarian
- 🏆 **End card** — personalized with your character name + gold score

### Polish
- 🔊 **Web Audio API sound effects** — hit, death, coin, chest, wave, CTA
- 📳 **Haptic feedback** — `navigator.vibrate()` on compatible devices
- ✨ **Particle system** — sparkles, emoji bursts on hits and pickups
- 🎊 **Confetti** — end card celebration
- 👈 **Hero direction flip** — character faces the direction it's moving
- 📱 **Mobile fullscreen** — automatically fills screen on devices < 420px wide

### Ad Network Ready
- ✅ Single `.html` file — no external assets required (fonts via Google Fonts CDN)
- ✅ `?preview=false` hides presenter bar for clean ad delivery
- ✅ Platform-aware CTA — detects iOS/Android and routes to correct store
- ✅ Real store deep links (App Store + Google Play)
- ✅ OG / meta tags for link previews

---

## File Structure

```
squad_busters_ad.html   ← entire project lives here
README.md
```

All CSS, JavaScript, and SVG assets are inline. The only external request is the **Nunito** font from Google Fonts — the UI falls back to `system-ui` while fonts load.

---

## URL Scheme

| App | URL |
|---|---|
| App Store | `https://apps.apple.com/app/squad-busters/id6443442702` |
| Google Play | `https://play.google.com/store/apps/details?id=com.supercell.squadbusters` |

To change the destination, update the `installAlert()` and `openStore()` functions in the `<script>` block.

---

## Screens

```
[Screen 0] Hook
   └─ Tap anywhere or kill both enemies → auto-advance

[Screen 1] Gameplay
   ├─ Drag joystick to move hero
   ├─ Walk near enemies to attack (auto-hit at proximity)
   ├─ Wave 1 (2 enemies) → Wave 2 (2 more enemies)
   ├─ Enemies drop coins — walk over to collect
   └─ All enemies defeated → chest activates → tap chest

[Overlay] Character Select
   └─ Choose a character → End Card

[Screen 2] End Card
   ├─ Shows selected character name + gold score
   ├─ App Store / Google Play badges
   └─ "Play Again" restarts from Hook
```

---

## Browser Support

| Browser | Support |
|---|---|
| Chrome / Edge 90+ | ✅ Full |
| Safari 15+ (iOS) | ✅ Full |
| Firefox 90+ | ✅ Full |
| Samsung Internet 14+ | ✅ Full |

Web Audio API is used for sound. On iOS, audio starts on first user gesture (standard browser policy).

---

## Production Checklist

- [ ] Replace App Store / Play Store URLs with your MMP attribution links (AppsFlyer / Adjust)
- [ ] Set `?preview=false` in your ad tag or strip the presenter bar entirely
- [ ] Test on real iOS + Android devices for touch and haptic feel
- [ ] Verify font loads over CDN; optionally self-host Nunito for offline environments
- [ ] Add your ad network's MRAID or VAST wrapper if required

---

## License

This is a prototype / concept build. Squad Busters and all related intellectual property belong to **Supercell**. Not for commercial distribution.
