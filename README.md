# DevShastra — Site

The public web files for **DevShastra**, the DSA and placement-prep Android app by Mythic Bharat Studios.

Served by GitHub Pages at **<https://mythicbharatstudios.github.io/DevShastra-Site/>**

| File | What it is | Live at |
|---|---|---|
| `index.html` | The privacy policy. Required by Google Play, and linked from inside the app. | [/](https://mythicbharatstudios.github.io/DevShastra-Site/) |
| `config.json` | The switches the installed app reads on every start. **This file is the control panel.** | [/config.json](https://mythicbharatstudios.github.io/DevShastra-Site/config.json) |

## How the app is controlled from here

Every DevShastra install fetches `config.json` when it opens. Editing it changes the app on every phone
within a minute — no new version, no Play Store review, no waiting for people to update.

| Field | Effect |
|---|---|
| `ads` | `false` removes banners, interstitials and rewarded ads |
| `premium` | `false` hides the Premium page and its entry points |
| `contests` | `false` removes the contests section from Today |
| `contentUpdates` | `false` pauses downloading new questions |
| `minVersionCode` | versions below this see "Please update DevShastra" — a kill switch for a broken release |
| `announcement` | a dismissible message card above the tabs |

**Who can change it:** anyone can *read* these files — they are public and contain nothing secret. Only
people with write access to this repository can *change* them. That is the access control: the CEO and the
co-founder.

## Rules the app follows

- A switch can only turn a feature **off**. Setting `"ads": true` cannot add ads to a build compiled
  without them.
- The app never waits for this file. It uses the last copy it saw, and ships with sensible defaults, so it
  works fully offline.
- A missing or broken file means "behave exactly as shipped" — unknown fields are ignored, so an older app
  survives a config written for a newer one.

## Do not

- **Do not make this repository private.** GitHub Pages would stop serving it, the privacy-policy URL would
  break, and Google can flag a listing whose policy link is dead.
- **Do not rename or move `config.json` or `index.html`.** Installed apps look for them at these exact
  addresses.

Full description: `docs/CONSOLE.md` in the main DevShastra repository.

---

© 2026 Mythic Bharat Studios
