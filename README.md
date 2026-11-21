# Week3-Projects-NETWWORKWALKS
Here is a professional GitHub README for your **Networkwalks Cybersecurity Internship – Password Cracking Lab**. It documents both John the Ripper (Kali Linux) and the Networkwalks browser-based tools.

# Password Cracking with John the Ripper & Networkwalks Tools

## 📌 Project Overview

This project is part of my **Cybersecurity Internship at Networkwalks (Batch B084)**.

The objective of this lab is to understand how password-protected PDF files can be tested for password recovery using password-cracking tools. The lab explores hash extraction, dictionary-based password attacks, and browser-based password recovery tools.

The practical exercise uses three password-protected PDF files provided as part of the Networkwalks lab.

## 🎯 Objectives

- Understand password-protected PDF files and password hashes.
- Learn how PDF password hashes are extracted.
- Perform dictionary-based password testing using John the Ripper.
- Understand the role of wordlists such as RockYou.
- Explore browser-based password recovery tools.
- Compare command-line and web-based approaches.

## 🛠️ Tools & Technologies

| Tool                          | Purpose                           |
| ----------------------------- | --------------------------------- |
| Kali Linux                    | Cybersecurity testing environment |
| John the Ripper               | Password recovery                 |
| pdf2john                      | PDF hash extraction               |
| RockYou Wordlist              | Dictionary-based password testing |
| Networkwalks Hash Calculator  | Online hash extraction            |
| Networkwalks Password Cracker | Browser-based password recovery   |

## 📂 Lab Files

The lab provides the following files:

- `Password-Cracking-with-NW-Tools-v1.pdf` – Lab task sheet
- `My Locked PDF1.pdf` – Password-protected PDF 1
- `My Locked PDF2.pdf` – Password-protected PDF 2
- `My Locked PDF3.pdf` – Password-protected PDF 3

## 💻 Method 1: Password Recovery Using Kali Linux

### Step 1: Install John the Ripper

```
sudo apt update
sudo apt install john -y
```

### Step 2: Locate pdf2john

```
locate pdf2john
```

### Step 3: Navigate to the PDF directory

```
cd ~/Downloads
```

### Step 4: Extract the PDF hash

```
pdf2john "My Locked PDF1.pdf" > pdfhash.txt
```

### Step 5: Prepare the RockYou wordlist

Check the available wordlists:

```
ls /usr/share/wordlists/
```

Extract the compressed RockYou wordlist:

```
sudo gzip -dk /usr/share/wordlists/rockyou.txt.gz
```

### Step 6: Perform dictionary-based password testing

```
john --wordlist=/usr/share/wordlists/rockyou.txt pdfhash.txt
```

### Step 7: Display the recovered password

```
john --show pdfhash.txt
```

**Note:** Password recovery depends on whether the correct password is present in the selected wordlist. A successful hash extraction does not guarantee password recovery.

## 🌐 Method 2: Using Networkwalks Online Tools

This method uses browser-based tools without requiring local installation.

### Step 1: Open the Hash Calculator

[Networkwalks Hash Calculator](https://networkwalks.com/hash-calculator/)

Upload the password-protected PDF and obtain its hash using the supported functionality.

### Step 2: Open the Password Cracker

[Networkwalks Password Cracker](https://networkwalks.com/password-cracker/)

Submit the extracted hash using the tool's supported input format.

### Step 3: Test Password Recovery

Run the password recovery process and observe whether the tool successfully identifies the password.

### Step 4: Record the Results

Document the outcome of each PDF recovery attempt.

## 📊 Learning Outcomes

Through this practical exercise, I learned:

- How password-protected PDF files use password verification mechanisms.
- How to extract PDF hashes using pdf2john.
- How John the Ripper performs dictionary-based password testing.
- How to use the RockYou wordlist in Kali Linux.
- How browser-based password recovery tools work.
- The differences between command-line and browser-based approaches.

## 🔐 Ethical Considerations

This lab was performed for educational purposes using files provided as part of the Networkwalks internship.

Password recovery and security testing should only be performed on files and systems that you own or have explicit permission to test.

## 👨‍💻 Internship Information

**Program:** Cybersecurity Internship\
**Organization:** Networkwalks\
**Batch:** B084\
**Project:** Password Cracking with Networkwalks Tools

---

*This repository documents my practical learning and hands-on experience with password recovery techniques as part of my cybersecurity training.*

### **Recommended GitHub folder structure**

```
Password-Cracking-Lab/
│
├── README.md
├── Lab-Task-Sheet.pdf
│
├── PDFs/
│   ├── My Locked PDF1.pdf
│   ├── My Locked PDF2.pdf
│   └── My Locked PDF3.pdf
│
├── Screenshots/
│   ├── 01-john-installation.png
│   ├── 02-pdf-hash-extraction.png
│   ├── 03-rockyou-wordlist.png
│   ├── 04-john-execution.png
│   └── 05-password-recovery-result.png
│
└── Documentation/
    └── Lab-Observations.md
```

