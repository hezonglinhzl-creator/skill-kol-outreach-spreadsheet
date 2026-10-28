# KOL Collector and Outreach Tracker / KOL 采集器与建联台账

[简体中文](README.md) | **English**

Record visible creator-profile data in a local 16-column Excel tracker and maintain outreach status.

[Download complete project ZIP](https://github.com/hezonglinhzl-creator/varla-electric-mobility-skills-and-tools/raw/main/packages/skill-kol-outreach-spreadsheet.zip) · [All projects](https://github.com/hezonglinhzl-creator/varla-electric-mobility-skills-and-tools)

## Features

- KOL recorder and Chrome extension
- Collector services and blank-workbook setup
- Follower, view, contact and progress checks

## What is included

| Part | Location |
| --- | --- |
| KOL and Viral Video Collector Kit | [varla-kol-collector](apps/varla-kol-collector/README.en.md) |
| KOL Recorder Chrome Extension | [kol-recorder-extension](apps/kol-recorder-extension/README.en.md) |
| Skill instructions | [SKILL.md](skill/kol建联数据表格skill/SKILL.md) |

## Download and extract

1. Open this repository, choose **Code → Download ZIP**, or use the complete-project download above.
2. Right-click the downloaded ZIP and choose **Extract All**. Open the extracted folder containing this README.
3. Keep the whole folder together. Start the program first using the next section, then install/use its skill.

Installation also writes PACKAGE-LOCATION.json beside the installed SKILL.md, mapping the bundled programs to their actual extracted directories. Keep the full extracted folder; rerun the installer after moving it. Existing Skill content is preserved by default while paths are refreshed.

## 1. Set up the program first

Recommended: run only the complete varla-kol-collector kit. The standalone KOL recorder is an alternative, not a second service to start on the same 8765 port. Load one collector extension variant at a time.

### KOL and Viral Video Collector Kit (`varla-kol-collector`)

Windows, Python 3.10+, Chrome/Edge; network access for initial dependencies.

Open `apps/varla-kol-collector` first. Start the KOL recorder and video center together with the floating Varla browser panel.

1. Run `Install_Environment.bat` to install dependencies.
2. Inside `KOL_recorder`, run `python create_blank_workbook.py` to create your blank tracker.
3. Return here and run `Start_Varla_Collector.bat`.
4. Leave both service windows running: KOL on 8765 and video center on 8766.
5. Load `chrome_extension`, open a target page, review the panel and record the data.

Local URL: `http://127.0.0.1:8766`

[Full program / browser-extension guide](apps/varla-kol-collector/README.en.md)

No real contacts or result workbooks are preloaded; initialize your own tracker first. Collection alone defaults to not-contacted; contacted status must be explicit.

### KOL Recorder Chrome Extension (`kol-recorder-extension`)

Windows, Python 3.10+, Chrome/Edge and openpyxl.

Open `apps/kol-recorder-extension` first. Read visible Instagram/TikTok creator fields and write a local Excel tracker.

1. Open PowerShell here and run `python -m pip install -r requirements.txt`.
2. Run `python create_blank_workbook.py` to create a blank 16-column tracker only if none exists.
3. Run `start_kol_recorder.bat` and leave its service window open.
4. Load the extension below, open a creator profile, review parsed fields and record the result.

Local URL: `http://127.0.0.1:8765`

[Full program / browser-extension guide](apps/kol-recorder-extension/README.en.md)

Use only visible page data; hidden emails and unavailable metrics remain blank. Collection alone defaults to not-contacted; contacted status must be explicit.

## 2. Install the Skill

1. At the extracted project's root, double-click `安装Skill.cmd` on Windows.
2. The installer copies `skill/kol建联数据表格skill` to `%USERPROFILE%\.codex\skills\kol建联数据表格skill`. Existing same-name skills are skipped; check the displayed result.
3. Reopen Codex and start a new chat. Use the exact skill name shown below.
4. If scripts cannot run under your organization policy, open install.ps1 for review or copy the skill directory manually to the same destination.

## 3. First task

| Prepare | Details |
| --- | --- |
| Input | Public creator profiles and your own blank or existing tracker. |
| Output | Your local outputs/varla_kol_tracker.xlsx; no contacts are preloaded in the repository. |

```text
Use kol建联数据表格skill to verify this creator's visible followers and recent views, show evidence, then record them locally; leave unavailable values blank.
```


## Limits and troubleshooting

Platform changes may affect parsing. Leave hidden emails/views blank and close Excel/WPS before writing.

| Problem | Next step |
| --- | --- |
| Skill not visible | Check the installer output and destination SKILL.md, reopen Codex and start a new chat. |
| Program fails to start | Open its directory in PowerShell and run the documented command so the error remains visible; check that program's README. |
| Browser panel missing | Select the exact folder containing manifest.json, check supported websites and refresh the website tab. |
| External service unavailable | Supply your own authorization/settings and verify access. Keep local output rather than claiming a sync/send succeeded. |

## Privacy and status

This is a source/skill distribution. No real accounts, OAuth tokens, customer/KOL lists, contracts, orders, mailbox exports or business media are included. You configure your own services. Documentation and package paths were checked; live orders, sends and publications were not executed as part of documentation validation.
