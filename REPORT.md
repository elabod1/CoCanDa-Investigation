# 📋 Full Investigation Report — CoCanDa Case

**Case ID:** COCANDA-2021-01-26
**Analyst:** Major on Earth (CTF Player)
**Date:** 26 Jan 2021
**Status:** ✅ SOLVED

---

## 1. Executive Summary

A suspicious email was received by `themajoronearth@gmail.com`
claiming to hold abducted CoCanDians, including the President's daughter.
The email demanded **1 Billion CoCanDs + a spaceship**.

Investigation revealed that:

- The email was **spoofed** via `emkei.cz` (SPF fail).
- The ransom demand was **fake** — the real intention is **war**.
- The real location is the **Martian Colony, beside the Interplanetary Spaceport**.
- The distance hint *"12.8 light-minutes from the Sun"* points to **Mars orbit**.

---

## 2. Evidence Chain

| # | Evidence | Source |
|---|----------|--------|
| 1 | Raw email header | `evidence/01-email-raw.txt` |
| 2 | Base64 body | `evidence/02-email-body.txt` |
| 3 | Base64 attachment | `evidence/03-attachment-original.txt` |
| 4 | Extracted ZIP | `evidence/extracted/PuzzleToCoCanDa.zip` |
| 5 | Money.xlsx | `evidence/extracted/Money.xlsx` |
| 6 | GoodJobMajor.pdf | `evidence/extracted/GoodJobMajor.pdf` |
| 7 | DaughtersCrown.png | `evidence/extracted/DaughtersCrown.png` |

---

## 3. Phase-by-Phase Findings

### Phase 1 — Email Header
- **From:** `billjobs@microapple.com` (spoofed)
- **Reply-To:** `negeja3921@pashter.com` (attacker's real inbox)
- **SPF:** `fail` — sender not authorized
- **Origin:** `emkei.cz` (anonymous email service)
- **Conclusion:** Fake sender, real Reply-To.

### Phase 2 — Body (Base64)
Decoded message reveals:
- Ransom: **1 Billion CoCanDs + spaceship**
- Location hint: **12.8 light-minutes from the Sun** (≈ Mars)
- Puzzle hint: **"Don't Trust Your Eyes"**

### Phase 3 — Attachment Disguise
- File named `PuzzleToCoCanDa.pdf`
- Magic bytes: `50 4B` (`PK`) → actually a **ZIP archive**
- Contains:
  - `DaughtersCrown`
  - `GoodJobMajor`
  - `Money.xlsx`

### Phase 4 — Money.xlsx
- **Sheet1:** *"Whatever you have seen or read till now is fake.
  Our intention was not for money. It is the beginning of the
  WAR WITH CoCanDians."*
- **Sheet3:** Base64 → **"The Martian Colony, Beside Interplanetary Spaceport."**

### Phase 5 — GoodJobMajor.pdf
- Confirms hostages are safe.
- Points to `DaughtersCrown` as proof.
- Visual hints: `$` + `📌`.

### Phase 6 — DaughtersCrown.png
- Golden crown image (proof of life).
- Warning *"Don't Trust Your Eyes"* suggests possible steganography.

---

## 4. Final Conclusion

| Question | Answer |
|----------|--------|
| Who is the attacker? | Unknown, uses `pashter.com` inbox |
| Why? | To start a **war** with CoCanDians |
| Where? | **Martian Colony, beside Interplanetary Spaceport** |
| Is the President's daughter safe? | ✅ Yes (proof in DaughtersCrown) |
| Was money the goal? | ❌ No — decoy |

---

## 5. Recommendations

1. Send a reconnaissance mission to the Martian Colony.
2. Analyze `DaughtersCrown.png` for hidden steganographic data.
3. Block `pashter.com` and `emkei.cz` domains.
4. Trace `93.99.104.210` (emkei.cz IP).
5. Prepare defensive measures against the announced war.

---

**End of Report.**
