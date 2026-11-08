# Phase 3 — Attachment Disguise (PDF → ZIP)

**Source:** `evidence/03-attachment-original.txt`

---

## Attachment Metadata
Content-Type: application/pdf; name="PuzzleToCoCanDa.pdf"
Content-Transfer-Encoding: base64
Content-Disposition: attachment; filename="PuzzleToCoCanDa.pdf"


## The Trick

Base64-decoded content begins with:
UEsDBBQAAAAI...

After decoding, the first bytes are:
50 4B 03 04 → "PK.."

- `50 4B` = **PK** (Phil Katz) → ZIP file signature.
- A real PDF starts with `25 50 44 46` (`%PDF`).
- **Conclusion:** The file is a **ZIP archive disguised as PDF**.

---

## Archive Contents
PuzzleToCoCanDa/DaughtersCrown
PuzzleToCoCanDa/GoodJobMajor
PuzzleToCoCanDa/Money.xlsx

---

## Extraction Steps

```bash
# 1. Decode Base64
base64 -d 03-attachment-original.txt > PuzzleToCoCanDa.zip

# 2. Extract
unzip PuzzleToCoCanDa.zip
```

Conclusion
The attacker disguised a ZIP as a PDF to bypass simple filters.

Extracted 3 files → analyzed in Phases 4–6.


---

## 📄 الخطوة 9: ملف `analysis/04-money-xlsx.md`

**المسار:** `CoCanDa-Investigation/analysis/04-money-xlsx.md`

```markdown
# Phase 4 — Money.xlsx

**Source:** `evidence/extracted/Money.xlsx`

---

## Sheet1 — The Twist

> *"Whatever you have seen or read till now is fake.
> Our intension was not for money.
> It is the beginning of the WAR WITH CoCanDians"*

> **Location:** *"It's not that easy to find this Majorr!!
> I will also stay in the same location but I bet
> CoCanDian's cant do anything in my planet 😂"*

> *"Find and come ASAP I'm Waiting!"*

### Analysis

- **Ransom was a decoy.**
- Real goal: **war** with CoCanDians.
- Attacker stays in the **same location**.

---

## Sheet3 — The Real Location

Encoded string:
VGhlIE1hcnRpYW4gQ29sb255LCBCZXNpZGUgSW50ZXJwbGFuZXRhcnkgU3BhY2Vwb3J0Lg==

Decoded (Base64):

> **The Martian Colony, Beside Interplanetary Spaceport.**

---

## Conclusion

| Item | Finding |
|------|---------|
| Ransom | ❌ Fake |
| Intention | ✅ War |
| Location | ✅ Martian Colony, beside Interplanetary Spaceport |
| Consistency | ✅ Matches 12.8 light-min from Sun |
```
