# 🌎 Realmheart 🌎
### (Formerly UBIS — Ultimate Banking Inventory System)

## Banking, Inventory & World-State Engine for AI Dungeon

![Realmheart Banner](https://i.postimg.cc/gkwmkG5n/AI-Dungeon-(2).png)

### Realmheart brings structure, immersion, and world-simulation to your AI Dungeon adventures.
It handles currency, inventory, bills, income, time progression, weather, holidays, events, price references, and story card syncing — all automatically. Designed for players who want deeper worlds, consistent rules, and a smooth quality-of-life experience.

---

## ✨ Features

| Feature | Description |
| --- | --- |
| **Automated Currency System** | 💵 Wallet tracking that automatically adds, deducts, converts, and declines purchases when funds are insufficient. |
| **Smart Inventory Tracking** | 🎒 Auto-detects item gains and losses using expanded keyword triggers for seamless inventory updates. |
| **Time Progression Engine** | 🕰️ Automatically advances time based on narration cues or player commands, including hours, days, weeks, and months. |
| **Bills & Income Automation** | 💳 Recurring expenses and income with automatic ledger logging and time-based scheduling. |
| **Preset System** | 🌐 Choose from Fantasy, Modern, or Sci-Fi presets. Each preset comes with appropriate default holidays, price lists, inventory, currency, and board labels out of the box. |
| **Holidays Story Card** | 🎊 Built-in holidays synced to Realmheart time. Fantasy, Modern, and Sci-Fi each have their own default sets. Fully editable in-game. |
| **Events Story Card** | 📆 Create one-time or repeating events with optional lead-time reminders. Resolved single-day events no longer repeat until the following day. |
| **Seasonal Weather System** | 🌦️ Configurable weather tables for Fantasy, Modern, and Sci-Fi settings, automatically injected into AI context. |
| **Prices & Goods Card** | 📦 Cost-of-living reference for realistic NPC pricing. Preset-appropriate categories for each setting. Edit values directly on the card — no template required. |
| **Bounty Board** | 🎯 Story card for defining minimum and maximum payouts for quests, jobs, and contracts. Labeled as Job Board (modern) or Contract Board (sci-fi) automatically. Edit payout values directly on the card. |
| **Ledger** | 📒 Stores up to 50 transactions internally. The story card displays the 20 most recent. Use `/ledger` to view the full history. |
| **Narrator Mode** | 🧭 Toggle to prevent the AI from narrating or deciding actions for your character. Can be set in the config block at script setup or toggled in-game. |
| **Story Card Syncing** | 🔄 Inventory, wallet, bills, time, and config cards stay perfectly updated every turn. |
| **Slash Commands** | ⌨️ Full command suite including `/help`, `/keywords`, `/rh enable\|disable\|toggle`, and more. Both `/rh` and `/ubis` prefixes are supported. |

---

## 📦 Installation Guide

#### 1. Open AI Dungeon on your computer (or switch your mobile browser to Desktop Mode).

#### 2. Create a new scenario or open one you want to edit.

#### 3. At the top of the editor, go to the **DETAILS** tab.

#### 4. Scroll down until you find **Scripting**, then toggle Scripts **ON**.

#### 5. Click **EDIT SCRIPTS**.

#### 6. In the left sidebar, select the **Input** script tab.

#### 7. Remove any existing code inside that tab.

#### 8. Paste the following into the Input section:
```javascript
// ============================================================
//  REALMHEART INPUT MODIFIER
// ============================================================
const modifier = (text) => {
  text = onInput_UBIS(text);
  return { text };
};

modifier(text);
```

#### 9. Select the **Context** tab on the left. Delete all existing code and paste this:
```javascript
// ============================================================
//  REALMHEART CONTEXT MODIFIER
// ============================================================
const modifier = (text) => {
  text = onContext_UBIS(text);
  return { text };
};

modifier(text);
```

#### 10. Select the **Output** tab. Delete all existing code and paste this:
```javascript
// ============================================================
//  REALMHEART OUTPUT MODIFIER
// ============================================================
const modifier = (text) => {
  text = onOutput_UBIS(text);
  return { text };
};

modifier(text);
```

#### 11. Go to your **Library** tab. Delete everything inside it.

#### 12. Open the link below, copy the entire Library script, and paste it into your Library tab:
[Realmheart Library V2.1](https://github.com/Itsbrazyyy/-Realmheart-Banking-Inventory-World-State-Engine/blob/4e974c35e9e07ba80e51560d74fbca1e7675ae43/Realmheart-Library-Script-V2.2txt)

#### 13. Click **SAVE** in the top right corner.

### 🥳 You've successfully installed Realmheart! All adventures from this scenario will now have the script active.

---

## 🎮 Gameplay Tips

1. If you don't see the script upon loading the scenario, ensure that Scripts are enabled in your gameplay settings.
2. If you're planning to customize currency, preset, or starting settings, it's recommended to do so before progressing in your scenario. These changes can be made in the **Configure Realmheart** story card or directly in the Library config block.
3. Use `/help` for a full overview of features and commands. Use `/keywords` to see every word and phrase Realmheart detects automatically.
4. When you want currency to be tracked, avoid adding extra words between the amount and currency name. For example: "I received a single gold coin" 🚫 vs "I received a gold coin" ✅
5. Different AI models may behave differently with detection and narrator mode.
6. If you use `/rh disable` to disable the script and want to re-enable it, type `/rh enable` or `/ubis enable` directly in Story mode. You can also switch Script from OFF to ON in the **Configure Realmheart** story card.
7. Slash commands only work in **Story** mode — not Do, Say, or See mode.
8. For multi-day events with slow time progression (e.g. 5 minutes per turn), consider manually toggling the event off once it has been resolved. Single-day events now automatically suppress after firing once and clear the following day.

---

## 👩‍💻 Creator Information

- The Library script contains a fully annotated config block at the top. Adjust preset, starting balance, time settings, bills, and feature toggles here to match your world before play.
- I would appreciate credit when sharing scenarios using this script 💗 (Example: *"Script by ItsBrazyyy"*)

---

## 🔗 Useful Links

- [AI Dungeon](https://play.aidungeon.com/)
- [Script on AI Dungeon](https://play.aidungeon.com/scenario/4MSdmu6UWa_-/ultimate-banking-inventory-system-v11?share=true&published=true)
- [AI Dungeon Official Discord](https://discord.gg/HpuNBKSb)

---

## 📜 Changelog

<details>
<summary><strong>Click to expand</strong></summary>

### V2.1 — Realmheart
- Modern and Sci-Fi presets now have their own default holidays, price lists, and starting inventory. Previous versions used fantasy defaults across all presets.
- The Prices & Goods and Holidays cards now display preset-appropriate content on first load.
- The Bounty Board is now labeled **Job Board** (modern) or **Contract Board** (sci-fi) automatically.
- The Copper/Silver/Gold notation line no longer appears in modern or sci-fi scenarios.
- Custom preset removed.
- Ledger internal history expanded to 50 entries. Story card displays the 20 most recent. `/ledger` command shows the full 50.
- Fixed a bug where single-day events would persist and repeat for the entire day after being resolved. Events now fire once and suppress until the following day.
- Narrator mode instruction strengthened for more consistent enforcement. Can now be set in the config block at script setup.
- Config block reorganized into clearly labeled sections: Starting State, Feature Toggles, Label Overrides, Card Visibility, and World Data.
- Bills and income templates moved to the top of the config alongside other starting state settings.
- Included `/rh` commands alongside `/ubis` for the Realmheart name integration. Both prefixes now fully supported.
- Fixed a bug where `/rh enable` and `/ubis enable` could not re-enable the script once disabled.
- `/help` fully rewritten with a welcoming introduction and detailed descriptions of every feature.
- `/keywords` fully rewritten with a complete and accurate reference of every detected word and phrase.
- The Bounty Board and Prices & Goods cards now support direct inline value editing. No template required — edit values on the card directly and changes apply next turn.
- Basic dead code cleanup and a duplicate variable declaration resolved.

### V2.0 — UBIS
- Added Holidays Story Card (festivals, solstices, birthdays, religious days)
- Added Events Story Card with lead-time reminders and auto-clearing
- Added Seasonal Weather System with configurable tables
- Added Bounty Board for quest/job payout ranges
- Added Narration Switch to stop AI auto-decision making
- Expanded currency and inventory keyword detection
- Improved bills & income interval parsing and automation
- Expanded Price List categories for consistent world pricing
- Enhanced story card syncing and slash command reliability
- General code cleanup, optimization, and stability improvements

### V1.1
**Fixes:**
- The year can now be edited within the Configure Time Settings story card along with the month, day, and hour.

**New Features:**
- Script now has a boilerplate at the top for easy default adjustments.
- Added Price List story card. Allows adjustment of cost-of-living for your world. Information is fed to the AI for consistent NPC pricing.
- Added Currency Context feature to the Configure card. Turning this off stops feeding cost-of-living knowledge to the AI.

### V1.1.0
- Initial release

</details>
