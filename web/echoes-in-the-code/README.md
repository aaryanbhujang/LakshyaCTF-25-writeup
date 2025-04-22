## 🌐 Echoes in the Code

**Challenge Name:** Echoes in the Code  
**Category:** Web Security  
**Points:** 150  
**Difficulty:** Easy

---

### 🧠 Challenge Description

A web application with a file downloading functionality. The goal was to retrieve a hidden flag from the server.

---

### 📁 Files Provided

    URL to hosted web challenge (no static files provided)

---

### 🧩 Solution Overview

- Opened the site and inspected the **source code**.
- ![image](https://github.com/user-attachments/assets/cc7ca6d8-d54f-428b-881d-137e65f8120f)

- Found a file named `public.txt` — accessed it directly via `public.txt`.
- The file hinted that other files could be in the same `files/` directory.
- ![image](https://github.com/user-attachments/assets/ce881637-199b-4565-a9ba-2080030c4e93)

- Tried interacting with the **download endpoint** which accepted filenames as parameters.
  
- Tested for **Path Traversal** by passing a payload like:  
  `../../../../../etc/passwd`
  ![image](https://github.com/user-attachments/assets/e61e0790-542c-4981-8ee3-40da23f17379)

  It successfully downloaded the file, confirming the vulnerability.
- Knowing the flag was likely in a restricted file, attempted to access `files/secret.txt` using the same traversal exploit.
- Payload used:  
  `../files/secret.txt`
  
- This successfully returned the contents of `secret.txt`, which included the flag.
![image](https://github.com/user-attachments/assets/91cb8fd0-ac52-49d1-b261-f36a3a885a73)

---

### 🛠️ Tools Used

- Manual Payload Testing
- Path Traversal Payloads
- Basic Recon via Source Inspection
