# 🏠 Home Assistant Blueprints by Ryan McCullough

A collection of custom **Home Assistant blueprints** designed for smart homes that use integrations like **Miele**, **Omada**, **Home Assistant mobile notifications**, and more.

This repository is intended to make automation setup simple, maintainable, and versioned — with each blueprint fully documented and updatable directly from Home Assistant’s UI.

---

## 🔔 Blueprint: Miele Program Phase Finished Notification

### 📄 File
[`miele_program_phase_finished.yaml`](blueprints/automation/ryanmccullough/miele_program_phase_finished.yaml)

### 🧩 Description
Sends a push notification when a Miele appliance (washer, dryer, dishwasher, etc.) completes its cycle — by detecting when its **program-phase sensor** changes to the `"End"` state.

This blueprint automatically filters entity selection to only show sensors from the Miele integration that match `sensor.*_program_phase*`.

---

### ⚙️ Features
✅ Works with **any Miele program-phase sensor**  
✅ Supports **multiple appliances** in one automation  
✅ Customizable **target state** (`End` by default)  
✅ Optional **hold time** to confirm completion before notifying  
✅ Custom **notify service** (mobile, group, or Telegram, etc.)  
✅ Versioned and self-updating from GitHub

---

## 🪄 How to Import into Home Assistant

To add this blueprint directly to your Home Assistant:

1. Open **Settings → Automations & Scenes → Blueprints → Import Blueprint**
2. Paste the following URL into the import box:

https://raw.githubusercontent.com/ryanmccullough/home-assistant-blueprints/main/blueprints/automation/ryanmccullough/miele_program_phase_finished.yaml


3. Click **Preview Blueprint → Import Blueprint**.
4. Select your Miele `*_program_phase_*` sensors.
5. Choose your `notify` service (e.g., `notify.mobile_app_ryans_iphone` or `notify.family`).
6. (Optional) Adjust the “Hold time” (e.g., `00:01:00` = 1 minute).

---

## 🧾 Versioning & Changelog

This repository uses **semantic versioning** (`MAJOR.MINOR.PATCH`) for blueprints.  
Each release includes auto-generated notes and attaches the YAML file for direct download.

### 🏷️ Current Release
**v1.0.0 — Initial Release**

- Added filtering for Miele `*_program_phase*` sensors  
- Added customizable target state (`End` by default)  
- Added duration input (`HH:MM:SS`) instead of time-of-day  
- Added `version` and `source_url` for update tracking  

### 🔮 Planned
- **v1.1.0** — Add optional sound/vibration pattern per device  
- **v1.2.0** — Add multi-language message templates  
- **v1.3.0** — Add “program started” optional notification  

---

## 🔁 Updating the Blueprint in Home Assistant

Whenever a new version is pushed to GitHub:

1. In Home Assistant, go to **Settings → Blueprints**.
2. Click the **⋮ (three dots)** next to this blueprint.
3. Choose **Update from source**.
4. Home Assistant fetches the latest version (based on `source_url:`).

> Tip: When an update is available, Home Assistant shows  
> “⚡ Update available — vX.X.X on GitHub”

---

## 🧰 Folder Structure

home-assistant-blueprints/
├── README.md
├── .github/
│ ├── workflows/
│ │ └── release.yml
│ └── changelog-config.json
└── blueprints/
└── automation/
└── ryanmccullough/
└── miele_program_phase_finished.yaml


---

## 🚀 GitHub Automation

This repository uses **GitHub Actions** to automatically create a release whenever you push a tag such as `v1.0.1`.  
Each release will:
- Build a changelog from recent commits
- Create a GitHub Release entry
- Attach your YAML blueprint as a downloadable asset
- Update the `version:` field inside the YAML

### 🧱 Workflow files
- `.github/workflows/release.yml`
- `.github/changelog-config.json`

To publish a new release:

```bash
git add .
git commit -m "v1.0.1 – Tweak entity filter and notification message"
git tag -a v1.0.1 -m "v1.0.1 – Tweak entity filter and notification message"
git push origin main --tags
```

GitHub will automatically:

Generate a changelog

Create a new Release

Attach the blueprint file

Show it as “Update available” inside Home Assistant

🧩 Future Blueprints (Planned)

🧺 Miele Status Finished Alert – for sensors like sensor.washing_machine_status

💡 Adaptive Lighting Scenes – time-based ambient adjustments

📱 Family Group Notifications – unified notify group management

🚨 Device Offline Watchdog – alerts if critical entities go unavailable

🤝 Contributing

Pull requests and improvements are welcome!
If you build your own blueprints based on these, feel free to open an issue or PR to include them here.

Please follow:

Semantic versioning (v1.0.0, v1.0.1, etc.)

Clear, single-purpose commits

Descriptive changelog messages

📄 License

MIT License © Ryan McCullough
