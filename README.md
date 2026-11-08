# 🚀 CoCanDa Investigation — The Martian Colony

> A complete digital forensics walkthrough of the CoCanDa CTF challenge:
> from a spoofed email to the discovery of the Martian Colony.

![Status](https://img.shields.io/badge/status-solved-brightgreen)
![Type](https://img.shields.io/badge/type-CTF-blue)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 📖 Story

CoCanDa, *"The Heaven of the Universe"*, suffers a wave of abductions.
The President's daughter is among the missing. On the third day,
**Major on Earth** receives a suspicious email from *"Bill"*...

---

## 🔍 Investigation Phases

| # | Phase | Finding |
|---|-------|---------|
| 1 | [Email Header Analysis](analysis/01-email-header.md) | SPF fail, spoofed via `emkei.cz` |
| 2 | [Body Decoding](analysis/02-base64-body.md) | Ransom demand + *"Don't Trust Your Eyes"* |
| 3 | [Attachment Disguise](analysis/03-zip-disguise.md) | `PDF` is actually a `ZIP` archive |
| 4 | [Money.xlsx](analysis/04-money-xlsx.md) | *"It's a WAR"* + Base64 location |
| 5 | [GoodJobMajor.pdf](analysis/05-goodjob-major.md) | Proof of life + visual hints |
| 6 | [DaughtersCrown](analysis/06-daughters-crown.md) | The final proof |

---

## 🎯 Key Findings

- ❌ **Fake ransom** — money was a decoy.
- ✅ **Real intention** — beginning of a **WAR** with CoCanDians.
- 📍 **Real location** — `The Martian Colony, Beside Interplanetary Spaceport.`
- 🌞 **Distance hint** — 12.8 light-minutes from the Sun ≈ **Mars orbit**.
- 👁️ **Warning** — *"Don't Trust Your Eyes"* — nothing is what it seems.

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| **HxD** | Hex editor — magic number verification |
| **CyberChef** | Base64 decoding |
| **7-Zip** | Archive extraction |
| **Excel / LibreOffice** | XLSX inspection |

---

## 📂 Repository Structure

evidence/ → original files (as received)
evidence/extracted/→ decoded artifacts
analysis/ → step-by-step markdown reports
screenshots/ → visual evidence
REPORT.md → full consolidated report


---

## ⚖️ Disclaimer

For **educational and CTF purposes only**. All entities are fictional.

## 📜 License

MIT — see [LICENSE](LICENSE).



## 📂 Repository Structure
