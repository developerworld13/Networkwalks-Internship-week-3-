# Networkwalks-Internship-week-3

# 🔐 Password Cracking with Networkwalks Tools & John the Ripper (JTR)

> **Target file:** `My Locked PDF1.pdf` | **Cracked password:** `password1`

**Recovering a password-protected PDF's password using hash extraction and dictionary attacks**

![Skill](https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000)
![Ver](https://img.shields.io/badge/Week-03-0070C0?style=flat-square&labelColor=000000)
![Tool](https://img.shields.io/badge/Tool-JohnTheRipper-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white)
![Tool](https://img.shields.io/badge/Tool-NetworkwalksCracker-404040?style=flat-square&labelColor=C00000)
![Ethical](https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white)

---

## 📌 Project Overview

This project focuses on **password cracking fundamentals** — recovering the password of a locked PDF file using two different approaches:

1. **Networkwalks Hash Calculator + Password Cracker** — free browser-based tools that extract a crackable (`$pdf$...`) hash from a locked PDF and run a dictionary attack against it.
2. **John the Ripper (JTR) + Johnny GUI** — the industry-standard offline password-cracking tool, used with a PDF hash extracted via an online `pdf2john` tool.

The goal was to understand how file-level password hashes are extracted and cracked, and why weak passwords are a serious security risk.

---

## 🎯 Objectives

- Extract a crackable hash (`$pdf$...`) from a password-protected PDF.
- Use the Networkwalks Hash Calculator and Password Cracker to recover the password via dictionary attack.
- Install and configure John the Ripper (JTR) and Johnny GUI on Windows.
- Use JTR/Johnny to recover the same PDF's password from its extracted hash.
- Understand the difference between encryption (two-way) and hashing (one-way).
- Document the full process, screenshots, and findings.

---

## 🛡️ Why This Matters

Password cracking is a core penetration-testing and security-awareness skill. Security professionals use it to:

- Test the real-world strength of passwords used in an organization.
- Demonstrate why short/common passwords are cracked in minutes.
- Justify password policy and MFA requirements to stakeholders.

⚠️ **This lab was performed only on a file provided for the exercise. Password cracking must only be done on systems/files you own or are explicitly authorized to test.**

---

# 🪜 Module 2 — Password Cracking with JTR & Johnny

## Step 1. Download the locked file

Downloaded `My Locked PDF1.pdf` from the Networkwalks lab page.

## Step 2. Extract the hash

Opened the **[Networkwalks Hash Calculator] <img width="927" height="862" alt="image" src="https://github.com/user-attachments/assets/b2c3a2b4-2f7b-4aff-904e-d65bfc6de652" />**  , uploaded the locked PDF under the **PDF** tab. The tool parsed the file locally in-browser and returned a crackable hash starting with `$pdf$...`.

## Step 3. Crack the hash

Pasted the full hash into the **[Networkwalks Password Cracker]  <img width="1902" height="962" alt="Screenshot 2026-11-20 210105" src="https://github.com/user-attachments/assets/3a0ac03b-3d59-42de-80aa-83e0ae3a325c" />**
  and ran the built-in dictionary attack (100-word list).

**✅ Cracked password:** `password1`

## Step 4. Unlock the PDF

Opened the PDF and entered the cracked password — file opened successfully.

![Unlocked PDF] <img width="1897" height="910" alt="Screenshot 2026-11-20 210119" src="https://github.com/user-attachments/assets/965a4cfc-ea82-4322-999b-1ba128857eee" />
---

# 🪜 Module 1 — Password Cracking with Networkwalks Tools


## Step 1. Install John the Ripper + Johnny GUI

Downloaded JTR (jumbo build) from openwall.com and Johnny GUI, installed on Windows.

## Step 2. Extract the hash

Used the online **[PDF Hash Extractor] <img width="1915" height="970" alt="Screenshot 2026-11-20 211754" src="https://github.com/user-attachments/assets/985eaa95-5d74-4613-924c-ee64a54141f3" />** (pdf2john-based) to extract the hash from the same locked PDF, saved it as `hash1.txt`.

## Step 3. Point Johnny to John the Ripper

In Johnny → Settings → browsed to `john.exe` inside the JTR `run` folder.


## Step 4. Load the hash and attack

Opened `hash1.txt` via **Open password file**, then clicked **Start new attack**.


<!-- PASTE SCREENSHOT: johnny-attack-result.png -->  <img width="870" height="685" alt="Screenshot 2026-11-20 212806" src="https://github.com/user-attachments/assets/53f6c0c1-e3c9-46b5-92a8-99a9c68ba742" />


**✅ Cracked password:** `password1`

## Step 5. Unlock the PDF

Entered the cracked password in Adobe Acrobat — file opened successfully.
<img width="675" height="881" alt="Screenshot 2026-11-20 213343" src="https://github.com/user-attachments/assets/e606a520-c6ab-43b6-9415-5abee72bde04" />

---

# 💡 What I Learned

### 1. Hashing vs Encryption
Encryption is reversible with the right key; hashing is one-way — a password is never stored directly, only its hash, which is why attackers must *guess and hash* rather than *decrypt*.

### 2. Dictionary Attacks
A dictionary/wordlist attack only succeeds if the real password is in (or derivable from) the wordlist — this is why weak/common passwords like `password1` are cracked almost instantly, while random 12+ character passwords can resist cracking for years.

### 3. Multiple Tools, Same Concept
Both the Networkwalks browser tools and John the Ripper rely on the same underlying idea: extract the hash (`pdf2john`-style), then brute-force/dictionary-attack it. JTR is the industry-standard CLI/GUI tool used in real pentests; the Networkwalks tools are a fast browser-based way to learn the same workflow.

### 4. Password Hygiene
This exercise reinforced why strong, unique, 12+ character passwords (and MFA where possible) are essential — a weak password is a single point of failure.

---

# 🔐 Security & Ethical Use

This lab was performed strictly for educational purposes on a file provided for the exercise. Password-cracking techniques must never be used against systems or files without explicit authorization.

---

# 🔗 Tools & Resources

- **Networkwalks Hash Calculator:** https://networkwalks.com/hash-calculator/
- **Networkwalks Password Cracker:** https://networkwalks.com/password-cracker/
- **John the Ripper:** https://www.openwall.com/john/
- **Johnny GUI:** https://openwall.info/wiki/john/johnny
- **Online PDF Hash Extractor:** https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php

---

## 📌 Project Information
**Name** : Sneha Malyal
**Program Name:** Cybersecurity at Networkwalks | **Week:** 03 | **Project:** Password Cracking with Networkwalks Tools & JTR | **Repository:** GitHub
````[cite: 1]

