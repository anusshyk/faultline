# Faultline

**An interactive map of publicly disclosed bug bounty reports, plus live programs from four bounty platforms.**

Live site: **https://anusshyk.github.io/faultline/**

Made by **Muhammad Anas Shaikh**.

---

## What it is

Faultline turns more than 15,000 public HackerOne disclosures into something you can explore. Reports are grouped by how the bug worked, so you can open a vulnerability class, pick a weakness, and read the real reports behind it. It also lists live public programs on HackerOne, Bugcrowd, Intigriti and YesWeHack, with payouts and in-scope targets.

| | |
|---|---|
| Disclosed reports | 15,219 |
| Programs with reports | 428 |
| Vulnerability classes | 18 |
| Weakness types | 215 |
| Disclosed bounties | $4,934,915 |
| CVEs named in report titles | 471 |
| Live programs (4 platforms) | 939 |
| In-scope targets | 48,314 |

## Features

- **Map**: every vulnerability class drawn as a band, with each weakness as a block sized by its report count. Click any block to open its reports.
- **Reports**: search all reports by title, program or weakness. Filter by class, weakness or program, and sort by bounty, upvotes or date. Every title links to the full write-up on HackerOne.
- **Classes**: all 18 classes with their weaknesses, report counts and bounties paid.
- **Programs**: every HackerOne program with disclosed reports, its total paid out and its most common bug class.
- **CVEs**: every CVE ID that appears in a report title, linked to the US National Vulnerability Database.
- **Platforms**: 939 public programs across HackerOne, Bugcrowd, Intigriti and YesWeHack, with payout ranges and in-scope targets. Search by program or domain, filter by platform, or show paying programs only.
- **Top bounties**: the 50 biggest payouts.
- **Animation**: a moving trace where each spike is a paid report, map bars that grow in, counting stats, page transitions and a drifting animated background. All motion turns off for visitors who have turned on their device's reduce-motion setting.
- **Shortcuts**: press `/` anywhere to jump to search.
- Works on phones, tablets and desktops.

## Files

| File | What it holds |
|---|---|
| `index.html` | The whole site: layout, styles and scripts |
| `data.json` | The 15,219 HackerOne reports, with title, program, weakness, bounty and upvotes for each |
| `programs.json` | The 939 platform programs with payouts and in-scope targets |

There's nothing to install or build. It's a plain static site.

## Run it locally

Browsers block the data files when `index.html` is opened directly from disk, so serve the folder instead:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Deploy on GitHub Pages

1. Put the three files in the root of a public repository.
2. Go to **Settings > Pages**, set the source to **Deploy from a branch**, then choose **main** and **/ (root)**.
3. Click **Save**. The site goes live at `https://<username>.github.io/<repo>/` within a minute or two.

## Change the colours

Open `index.html` and edit the colour settings near the top, in the `:root` block:

| Setting | Colours |
|---|---|
| `--bg` | Page background |
| `--panel` | Cards, boxes and inputs |
| `--line` | Borders |
| `--ink` | Main text |
| `--mute` | Secondary text |
| `--acc` | Highlights such as bounty amounts |
| `--sup` | Second colour: logo, lines and accents |

To change the map bar colours, search the file for `function hue`. To change the platform badge colours, search for `const PCOL`.

## Data sources and credits

- **Reports**: [reddelexc/hackerone-reports](https://github.com/reddelexc/hackerone-reports), an open list of publicly disclosed HackerOne reports. Full write-ups belong to their authors and are hosted on [HackerOne](https://hackerone.com/hacktivity).
- **Programs and scopes**: [arkadiyt/bounty-targets-data](https://github.com/arkadiyt/bounty-targets-data), which is refreshed from HackerOne, Bugcrowd, Intigriti and YesWeHack every 30 minutes. The copy in this repository is a snapshot from 21 November 2026.
- **CVE links**: [NIST National Vulnerability Database](https://nvd.nist.gov/).

## Limitations

- **Report contents**: report text isn't part of the public data. Faultline shows titles and links each one to the full write-up on HackerOne.
- **Bounty totals**: these count only bounties disclosed publicly. Many programs pay privately, so real totals are higher.
- **CVE coverage**: the CVE page lists only CVEs whose ID appears in a report title.
- **Missing reports**: other platforms don't publish disclosed reports openly, so the report map covers HackerOne only.
- **Missing programs**: private, invite-only programs aren't included.
- **Updates**: the program list is a snapshot and doesn't update itself. Replace `programs.json` to refresh it.

## Disclaimer

Faultline is an independent project. It is not affiliated with or endorsed by HackerOne, Bugcrowd, Intigriti or YesWeHack. Every report shown was publicly disclosed by its program.

---

Made by **Muhammad Anas Shaikh**.
