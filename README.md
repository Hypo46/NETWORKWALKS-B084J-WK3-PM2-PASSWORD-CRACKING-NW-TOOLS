# Week 3 – Project Module 2: Password Cracking with NetworkWalks Tools

![Platform](https://img.shields.io/badge/Platform-Browser--Based-0A66C2)
![Tool](https://img.shields.io/badge/Tool-NetworkWalks%20Hash%20Calculator-black)
![Tool](https://img.shields.io/badge/Tool-NetworkWalks%20Password%20Cracker-red)
![Status](https://img.shields.io/badge/Status-Educational%20Lab-success)

A browser-based password-auditing lab from the **NetworkWalks Cybersecurity & Ethical Hacking Program (Batch B084J)**: recovering the password of a protected PDF using NetworkWalks' own online **Hash Calculator** and **Password Cracker**, with no local tooling required.

> 🔗 Video demo: [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7529280644565250048/)

---

<details>
<summary><strong>📌 Documentation notes (click to expand)</strong></summary>

- Screenshots are grouped into workflow stages and ordered by filename timestamp; captions describe the *expected* action at that point — confirm against the actual images.
- The `PDF/` folder contains `My Locked PDF1.pdf`, `My Locked PDF2.pdf`, `My Locked PDF3.pdf`, and a variant labeled for NW Tools use — this README documents the workflow against `My Locked PDF1.pdf` per the lab task; adjust if a different file was actually used in the screenshots.
- The lab manual's root filename is shown truncated in GitHub's file list (`W3-PM2 - Week3 - Project Module2 - Passwor...`) — complete the exact filename once visible.

</details>

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Lab Objective](#lab-objective)
3. [Lab Information](#lab-information)
4. [Tools & Technologies](#tools--technologies)
5. [Lab Environment](#lab-environment)
6. [Repository Structure](#repository-structure)
7. [Lab Workflow](#lab-workflow)
8. [Technical Concepts](#technical-concepts)
9. [Screenshot Evidence](#screenshot-evidence)
10. [Result](#result)
11. [Learning Outcomes](#learning-outcomes)
12. [Security Lessons](#security-lessons)
13. [Ethical Disclaimer](#ethical-disclaimer)
14. [References](#references)
15. [Related Week 3 Module](#related-week-3-module)
16. [Author](#author)

---

## Project Overview

This project demonstrates password recovery and password-security auditing of a password-protected PDF using NetworkWalks' own browser-based security tools, rather than a locally installed cracking tool. The task was to recover the password of the provided file `My Locked PDF1.pdf` by extracting its hash with the **NetworkWalks Hash Calculator** and feeding that hash into the **NetworkWalks Password Cracker**.

As the original lab task frames it, this exercise covers the same underlying concept as the John the Ripper lab (see [Related Week 3 Module](#related-week-3-module)), but through a tool stack that works from any computer with a web browser — no installation required.

## Lab Objective

Recover the password of the provided protected PDF file (`My Locked PDF1.pdf`) using the NetworkWalks Hash Calculator and Password Cracker, and document the full workflow with screenshot evidence.

## Lab Information

| Field | Detail |
|---|---|
| Program | Cybersecurity & Ethical Hacking Internship / Practical Training |
| Organization | NetworkWalks Academy |
| Batch | B084J |
| Week | Week 3 |
| Module | Project Module 2 |
| Source Task | [Password Cracking with NetworkWalks Tools](https://networkwalks.com/project-task-lab-password-cracking-with-networkwalks-tools/) |

## Tools & Technologies

| Tool / Concept | Role |
|---|---|
| [NetworkWalks Hash Calculator](https://networkwalks.com/hash-calculator/) | Extracts the password hash from the protected PDF |
| [NetworkWalks Password Cracker](https://networkwalks.com/password-cracker/) | Attempts to recover the plaintext password from the extracted hash |
| PDF Password Hash Extraction | Core technique: turning file-level protection into an attackable hash |
| Password Security Auditing | The overall practice this lab exercises |
| Web Browser | Only client-side requirement — no local install |

## Lab Environment

This lab is intentionally browser-based — per the task page, it "does the same job as the JTR lab" but is designed to suit beginners on any computer, with no VM, Linux distribution, or local tool installation required. The screenshots in this repository were captured from a standard Windows desktop browser session.

## Repository Structure

```text
NETWORKWALKS-B084J-WK3-PASSWORD-CRACKING-NW-TOOLS/
│
├── README.md
│
├── NW Web/
│   ├── Screenshot 2026-11-16 024811.png
│   ├── Screenshot 2026-11-16 024857.png
│   ├── ... (13 screenshots total — see Screenshot Evidence below)
│   └── Screenshot 2026-11-16 025641.png
│
├── PDF/
│   ├── My Locked PDF1 (for NW Tools)....pdf   (confirm exact filename)
│   ├── My Locked PDF1.pdf
│   ├── My Locked PDF2.pdf
│   └── My Locked PDF3.pdf
│
└── W3-PM2 - Week3 - Project Module2 - Passwor....pdf   (lab manual)
```

## Lab Workflow

**Step 1 — Obtain the protected PDF**
Downloaded `My Locked PDF1.pdf` from the [original NetworkWalks lab page](https://networkwalks.com/project-task-lab-password-cracking-with-networkwalks-tools/), which also provides the lab task sheet and two additional locked PDFs for further practice.

**Step 2 — Access the Hash Calculator**
Opened the [NetworkWalks Hash Calculator](https://networkwalks.com/hash-calculator/).

**Step 3 — Extract the PDF hash**
Uploaded the protected PDF to the Hash Calculator, which generated the file's password hash in the `$pdf$...` format.

**Step 4 — Copy the hash**
Copied the complete extracted hash value, taking care to preserve it in full.

**Step 5 — Open the Password Cracker**
Opened the [NetworkWalks Password Cracker](https://networkwalks.com/password-cracker/).

**Step 6 — Submit the hash**
Pasted the extracted hash into the Password Cracker and started the recovery process.

**Step 7 — Password recovery**
The tool worked through candidate passwords against the hash — recovery time depends on password complexity and the tool's own approach.

**Step 8 — Test the recovered password**
Used the recovered password to attempt opening the original protected PDF.

**Step 9 — Verify the result**
Confirmed the PDF opened successfully with the recovered password.

## Technical Concepts

- **Password-protected PDF:** a PDF encrypted so that opening it requires a password; the protection is enforced by the PDF's own security handler, not by a separate wrapper file.
- **PDF password hash extraction:** converting that PDF-level protection into a hash value that a cracking tool can test candidate passwords against, without needing to repeatedly open the actual file.
- **The `$pdf$` format:** the hash notation produced by PDF-hash extraction tools (including the one used here), encoding the PDF's encryption parameters alongside the hash itself so a cracking tool knows how to test candidates against it.
- **Password recovery vs. auditing:** "recovery" here means successfully determining the password through this process; the same process doubles as a security "audit" — if a password falls quickly, it was weak.
- **Hashing is not the same as encryption:** the PDF's content is encrypted (reversible with the right key — the password), but the extracted hash used for cracking is a one-way representation suited to *testing* candidate passwords, not to decrypting the file directly. A cracking tool finds the password by hashing guesses and comparing, not by reversing the hash itself.

## Screenshot Evidence

*(Grouped by workflow stage, ordered by capture timestamp. Captions describe the expected action — confirm against the actual images.)*

### 1. Original Lab / Task Reference

<a href="NW%20Web/Screenshot%202026-11-16%20024811.png"><img src="NW%20Web/Screenshot%202026-11-16%20024811.png" alt="NetworkWalks lab task page" width="700"></a>

*The original NetworkWalks lab page, listing the downloadable locked PDFs and the tools to use.*

### 2. Hash Extraction

<a href="NW%20Web/Screenshot%202026-11-16%20024857.png"><img src="NW%20Web/Screenshot%202026-11-16%20024857.png" alt="NetworkWalks Hash Calculator" width="700"></a>

*Opening the NetworkWalks Hash Calculator and uploading the locked PDF to generate its hash.*

<details>
<summary>Additional hash-extraction screenshots (4)</summary>

[![Step](NW%20Web/Screenshot%202026-11-16%20024929.png)](NW%20Web/Screenshot%202026-11-16%20024929.png)
[![Step](NW%20Web/Screenshot%202026-11-16%20024944.png)](NW%20Web/Screenshot%202026-11-16%20024944.png)
[![Step](NW%20Web/Screenshot%202026-11-16%20024954.png)](NW%20Web/Screenshot%202026-11-16%20024954.png)
[![Step](NW%20Web/Screenshot%202026-11-16%20025017.png)](NW%20Web/Screenshot%202026-11-16%20025017.png)

</details>

### 3. Password Cracker Usage

<a href="NW%20Web/Screenshot%202026-11-16%20025112.png"><img src="NW%20Web/Screenshot%202026-11-16%20025112.png" alt="NetworkWalks Password Cracker" width="700"></a>

*Opening the NetworkWalks Password Cracker and submitting the extracted hash.*

<details>
<summary>Additional password-cracker screenshots (2)</summary>

[![Step](NW%20Web/Screenshot%202026-11-16%20025422.png)](NW%20Web/Screenshot%202026-11-16%20025422.png)
[![Step](NW%20Web/Screenshot%202026-11-16%20025442.png)](NW%20Web/Screenshot%202026-11-16%20025442.png)

</details>

### 4. Password Recovery Result

<a href="NW%20Web/Screenshot%202026-11-16%20025509.png"><img src="NW%20Web/Screenshot%202026-11-16%20025509.png" alt="Password recovery result" width="700"></a>

*The Password Cracker returning the recovered password.*

<details>
<summary>Additional result screenshot (1)</summary>

[![Step](NW%20Web/Screenshot%202026-11-16%20025526.png)](NW%20Web/Screenshot%202026-11-16%20025526.png)

</details>

### 5. PDF Verification

<a href="NW%20Web/Screenshot%202026-11-16%20025615.png"><img src="NW%20Web/Screenshot%202026-11-16%20025615.png" alt="Testing recovered password on the PDF" width="700"></a>

*Using the recovered password to reopen the original locked PDF.*

<details>
<summary>Additional verification screenshot (1)</summary>

[![Step](NW%20Web/Screenshot%202026-11-16%20025641.png)](NW%20Web/Screenshot%202026-11-16%20025641.png)

</details>

## Result

The password for `My Locked PDF1.pdf` was successfully recovered entirely through NetworkWalks' browser-based Hash Calculator and Password Cracker, and verified by reopening the PDF with the recovered password. The following flags were captured from this module:

```text
nw{networkwalks_flag_260821_1}
nw{cybersecurity_flag_captured_2608}
```

## Learning Outcomes

- Understanding how password-protected PDF files enforce access control.
- Understanding the role of password hash extraction in enabling offline-style password testing.
- Recognizing the `$pdf$` hash format produced by PDF hash-extraction tools.
- Exploring password recovery through a fully browser-based security tool, with no local installation.
- Reinforced understanding of why password complexity directly affects recovery time.
- Seeing how weak passwords can be exposed through routine password auditing.
- Practical experience documenting a security exercise in an authorized training environment.

## Security Lessons

- A password that a browser-based cracker recovers quickly is a password that would fail in production just as fast.
- Hash extraction tools make password auditing accessible without specialized local tooling — which cuts both ways: accessible to defenders auditing their own systems, and to anyone testing password strength more broadly.
- Strong, unique passwords and additional protections like multi-factor authentication remain essential even when the underlying file-level encryption itself is sound.

## Ethical Disclaimer

This practical was conducted for educational purposes within an authorized NetworkWalks training environment. Password auditing and password-recovery tools demonstrated here should only be used against files, systems, and data for which you have explicit permission. This repository does not present or endorse unauthorized password cracking of any kind.

## References

- Original NetworkWalks Lab Task: [https://networkwalks.com/project-task-lab-password-cracking-with-networkwalks-tools/](https://networkwalks.com/project-task-lab-password-cracking-with-networkwalks-tools/)
- NetworkWalks Hash Calculator: [https://networkwalks.com/hash-calculator/](https://networkwalks.com/hash-calculator/)
- NetworkWalks Password Cracker: [https://networkwalks.com/password-cracker/](https://networkwalks.com/password-cracker/)
- NetworkWalks Academy: [https://networkwalks.com/](https://networkwalks.com/)

## Related Week 3 Module

This project pairs with **Week 3 – Project Module 1: Password Cracking with John the Ripper (JTR) and Johnny**, which explores the same underlying task — recovering the password of a locked PDF — through a different tool stack:

- **Module 1:** Local password auditing with John the Ripper and Johnny (installed tooling, Windows). Repo: [NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT](https://github.com/Hypo46/NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT)
- **Module 2 (this repo):** Browser-based password auditing with NetworkWalks' own Hash Calculator and Password Cracker — no local installation required.

## Author

**Rajatava Ghosh**
Cybersecurity Student — NetworkWalks Cybersecurity & Ethical Hacking Program (Batch B084J)

- GitHub: [RaxingR](https://github.com/RaxingR) (this lab repository is hosted under [Hypo46](https://github.com/Hypo46))
- LinkedIn: [rajatava-ghosh](https://www.linkedin.com/in/rajatava-ghosh-265aa6316/)
- Video demo: [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7529280644565250048/)
