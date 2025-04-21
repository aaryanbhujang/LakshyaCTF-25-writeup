## 🧠 Hello World

**Challenge Name:** Hello World  
**Category:** Reverse Engineering  
**Points:** 250  
**Difficulty:** Easy

---

### 🧠 Challenge Description

A basic binary file. The goal? Extract the flag. No inputs, no tricks — just RE.

---

### 📁 Files Provided

    hello_world (binary executable)

---

### 🧩 Solution Overview

- Opened the binary in **IDA Freeware** for static analysis.
- Navigated to the **Strings** window to check for any flag-related outputs.
![image](https://github.com/user-attachments/assets/fe463be4-344a-41fd-8cf6-4d36db48ef8e)
- Found a formatted string: `Flag: %s` — a solid hint.
- Followed the reference to the line in the disassembled code that uses this string.
![image](https://github.com/user-attachments/assets/74db875f-5086-43ea-8f70-97a84fcf430d)
- Noticed that a variable or memory location was passed as the argument for the `%s` placeholder.
- IDA showed:  
  `; DATA XREF: _hiddenFlag+81↑o`
- Jumped to the `_hiddenFlag` label to investigate.
![image](https://github.com/user-attachments/assets/058880be-0386-4fcf-a5d1-fdcefbc7561b)

- Found the flag clearly stored in this function.
- Flag was visible and did not require further decoding or deobfuscation.

---

### 🛠️ Tools Used

- IDA Freeware
- Strings view
- XREF navigation
- Static reverse engineering


