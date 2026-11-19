# NetworkWalks – PDF Password Cracking 

## 📌 Lab Overview

This repository documents my hands-on experience completing a Week 3 project. The exercise involved extracting password hashes from password-protected PDF documents, performing dictionary-based password cracking, and capturing flags.

The lab helped me understand how password-protected PDF files can be assessed and how password recovery tools can be used during security testing.

## 🎯 Objectives

- Understand password-protected PDF files.
- Extract crackable password hashes from encrypted PDF documents.
- Identify PDF encryption details.
- Perform dictionary-based password cracking.
- Use John the Ripper with the RockYou wordlist.
- Successfully recover PDF passwords and capture lab flags.

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Kali Linux | Penetration testing environment |
| NetworkWalks Hash Calculator | PDF hash extraction |
| John the Ripper | Password cracking |
| RockYou Wordlist | Dictionary-based password attack |
| Terminal | Executing commands and analyzing results |

## 🔬 Practical Walkthrough

### 1. Flag Capture

Successfully completed the initial flag-capture exercise on NetworkWalks.

**Captured Flag:**
`nw{cybersecurity_flag_captured_2608}`


### 2. Persistence Flag Capture

Continued the lab and successfully captured another flag.

**Captured Flag:**
`nw{networkwalks_persistence_itr_270521}`



### 3. PDF Hash Extraction

Used the NetworkWalks Hash Calculator to extract a crackable hash from a password-protected PDF document.

The tool generated a hash compatible with PDF password-cracking utilities such as John the Ripper and Hashcat.

The extracted hash contained information about the PDF encryption configuration.

**Observed configuration:**
- PDF Encryption: PDF 1.4
- Hash Format: PDF
- Revision: R4
- Key Length: 128-bit



### 4. Password Cracking Using John the Ripper

After extracting the PDF hashes, I used John the Ripper with the RockYou wordlist to perform dictionary-based password cracking.

**Command:**

```bash
john hash1.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

**Result:** Password successfully recovered.



Repeated the process with the second hash:

```bash
john hash2.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

**Result:** Password successfully recovered.



Performed the same operation against the third hash:

```bash
john hash3.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

**Result:** Password successfully recovered.



### 5. Password Recovery Verification

The NetworkWalks Hash Calculator also demonstrated successful password recovery.

The password was identified through dictionary matching.



### 6. Additional Flag Capture

Successfully completed another flag-capture exercise.

**Captured Flag:**
`nw{networkwalks_flag1_itr_270521_1}`



## 💡 Key Learnings

Through this practical exercise, I gained experience with:

- Understanding PDF password encryption.
- Extracting password hashes from encrypted PDF documents.
- Identifying PDF hash formats and encryption parameters.
- Performing dictionary attacks using John the Ripper.
- Working with the RockYou password wordlist.
- Understanding the importance of strong passwords.
- Analyzing password-cracking results.

## 🏁 Conclusion

Successfully completed the NetworkWalks PDF password-cracking exercise and captured the associated lab flags.

This exercise provided practical exposure to password security assessment, hash extraction, and dictionary-based password recovery using industry-standard security tools.

Author: Mukund Ugale
Program: Cybersecurity & Ethical Hacking Internship
Organization: Networkwalks
Modules: W3-PM1 (JohnTheRipper) | W3-PM2 (Networkwalks-tool)

---

⚠️ **Disclaimer:** This exercise was performed in an authorized cybersecurity training environment for educational purposes. All testing was restricted to lab-provided files and resources.
