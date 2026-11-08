# Phase 1 — Email Header Analysis

**Source:** `evidence/01-email-raw.txt`

---

## Key Fields

| Field | Value | Meaning |
|-------|-------|---------|
| `From` | "Bill" `<billjobs@microapple.com>` | Fake sender |
| `To` | `themajoronearth@gmail.com` | The Major |
| `Subject` | `A Hope to CoCanDa` | The hook |
| `Reply-To` | `negeja3921@pashter.com` | ⚠️ Attacker's real inbox |
| `Date` | Tue, 26 Jan 2021 01:41:18 -0500 | Timestamp |
| `Message-Id` | `<...@localhost>` | Generated locally |

---

## Authentication Results

spf=fail (google.com: domain of billjobs@microapple.com
does not designate 93.99.104.210 as permitted sender)


- **SPF failed** → sender not authorized.
- **Originating IP:** `93.99.104.210` → `emkei.cz` (anonymous email service).
- **Return-Path:** `billjobs@microapple.com` (spoofed domain).

---

## Conclusion

- The email was sent via **emkei.cz** (anonymous SMTP).
- The `From` domain `microapple.com` is **spoofed**.
- The real attacker inbox is `negeja3921@pashter.com`.
- `pashter.com` is a disposable email provider — likely the attacker's C2.

> **Red flag:** `Reply-To` differs from `From`.
