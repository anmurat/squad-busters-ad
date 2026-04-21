# Squad Busters - Playable Ad

A self-contained HTML5 playable advertisement for **Squad Busters** by Supercell.  
No dependencies, no build step - open `squad-busters-ad.html` in any modern browser.

---

##  Screens

| Screen | Description |
|--------|-------------|
| **Hook** | Animated map preview with chest, enemies, and hero. Tap anywhere or press **PLAY** to start. |
| **Gameplay** | Joystick-controlled hero, two enemies to defeat, collectible gold coins, and a chest reward. |
| **Character Selection** | Detailed character selection overlay with stats and abilities. |
| **End Card** | Character unlock reveal with CTA to install the game. |

---

##  Gameplay Flow

```
Hook ? [Tap / PLAY] ? Gameplay ? [Defeat enemies] ? Chest ? Character Selection ? End Card
```

1. **Move** - drag the joystick at the bottom of the screen  
2. **Attack** - walk near a ? enemy; auto-attack triggers on proximity  
3. **Collect coins** - gold coins drop from defeated enemies and can be collected  
4. **Open chest** - once both enemies are defeated the chest glows; tap it to open  
5. **Pick a character** - choose from detailed character selection screen with stats  
6. **End Card** - tap **PLAY NOW - FREE** to install (demo: shows alert)

The presenter bar at the bottom lets you jump directly to any screen during development.

---

##  Key Features

- **Gold Coin System**: Enemies drop collectible gold coins on defeat
- **Proximity Combat**: Auto-attack when hero gets close to enemies  
- **Character Selection**: Detailed overlay with character stats, abilities, and rarity
- **Chest Rewards**: Animated chest opening with gold burst effects
- **Responsive Controls**: Touch and mouse joystick controls
- **Visual Feedback**: Particle effects, screen shake, and smooth animations

---

##  Technical Implementation

- **Single HTML File**: All CSS and JavaScript inlined
- **No Dependencies**: Only Google Fonts CDN for typography
- **Modern JavaScript**: ES6+ features with fallback compatibility
- **CSS Animations**: Hardware-accelerated transforms and keyframes
- **Touch Support**: Full mobile and desktop compatibility

---

## 📂 File Structure

```
squad-busters-ad.html   ← single self-contained file (HTML + CSS + JS)
README.md
```

Everything is inlined — fonts load from Google Fonts CDN, no other external assets required.

---

## 🚀 Usage

```bash
# Just open in browser
open squad-busters-ad.html

# Or serve locally
npx serve .
python3 -m http.server 8080
```

---

## ✏️ Customisation

| What | Where |
|------|-------|
| Hero emoji | `#heroEmoji` element + `hook-hero-body` |
| Enemy count / HP | `G.enemyHP` object in JS state |
| Auto-chest timer (fallback) | `G.autoTimer` timeout in `initGameplay()` (default 13s) |
| End card CTA | `installAlert()` function — replace `alert()` with your store deep-link |
| Coin values | `grabCoin()` → `addCoins(3, ...)` and `pickupCoin()` → `addCoins(2, ...)` |

---

## 🛠 Browser Support

Chrome 90+, Safari 15+, Firefox 90+, Edge 90+.  
Touch and mouse input both supported.

---

*This is a demo/prototype playable ad. Squad Busters and all related assets are property of Supercell.*
