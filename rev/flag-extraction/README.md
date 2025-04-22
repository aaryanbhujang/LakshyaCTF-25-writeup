## 🧬 Flag Extraction

**Challenge Name:** Flag Extraction  
**Category:** Reverse Engineering  
**Points:** 600  
**Difficulty:** Hard

---

### 🧠 Challenge Description

A self-contained executable crafted in .NET. The mission: uncover the hidden flag from deep within the binary.

---

### 📁 Files Provided

    REV.exe

---

### 🧩 Solution Overview

- Opened the binary in **IDA** to begin static analysis.
![image](https://github.com/user-attachments/assets/8974efed-628c-472a-a966-8c6af5b8a918)

- Observed numerous function calls tied to `hostfxr`, a known component used to launch .NET Core apps — a clue that this was a **self-contained .NET app**.
- Such executables often embed additional DLLs.
- To dig deeper, switched over to **x64dbg** and launched the executable with a breakpoint set right at the start.
- Once execution hit the entry point, paused and navigated to:
  ```plaintext
  %TEMP%/.net/RE/
  ![image](https://github.com/user-attachments/assets/0b70441d-e960-4cd8-aba5-a60f7abfaf40)
Opening in iLSpy
![image](https://github.com/user-attachments/assets/be76aee3-5037-422a-8523-d606e25bd9cb)

