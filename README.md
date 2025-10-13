---

## 🧾 Versioning & Changelog

This repository follows **semantic versioning** (`MAJOR.MINOR.PATCH`) for blueprints.

### 🏷️ Current Release
**v1.0.0 – Initial Release**

- Added filtering for Miele `*_program_phase*` sensors  
- Added customizable target state (`End` by default)  
- Added duration field with `HH:MM:SS` support  
- Added version and `source_url` metadata for auto-update support  

### 🔮 Planned
- v1.1.0 – Add optional sound/vibration pattern per device
- v1.2.0 – Add optional multi-language message templates

---

### 💡 Updating in Home Assistant

When you push a new version:
1. Commit and tag your update on GitHub:
   ```bash
   git add .
   git commit -m "v1.0.1 – Improve state check and duplicate handling"
   git tag -a v1.0.1 -m "Improved state handling"
   git push origin main --tags
