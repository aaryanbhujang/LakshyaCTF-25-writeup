![burp3](https://github.com/user-attachments/assets/2240803a-528c-4768-9f76-8456f54a1ae0)## 🔐 Silent Vault

**Challenge Name:** Silent Vault  
**Category:** Web Security  
**Points:** 200  
**Difficulty:** Medium

---

### 🧠 Challenge Description

A minimal login-protected vault system. The objective: find the flag hidden behind access control and token-based authentication.

---

### 📁 Files Provided

    URL to hosted web challenge (no source code or hints provided)

---

### 🧩 Solution Overview

- Challenge began with a **login page** — tried default creds:  
  `admin:admin` — and it worked.
  
- Got a **Bearer access token** upon successful login.
  ![burp1](https://github.com/user-attachments/assets/b38c40ce-760f-45b1-878e-3d0760e96070)

- Checked `robots.txt` — found:
  ![robots](https://github.com/user-attachments/assets/bf40f87c-07a7-4a12-a93a-396e9ca7ceac)

  
- Tried accessing `/flag` directly with the token — got **403 Forbidden**.
  ![burp2](https://github.com/user-attachments/assets/9fe2d80a-bf85-4fa0-b632-c518c44974d3)

- Time to **enumerate hidden directories**. Used `gobuster` and found:

- Accessed `/admin` using the same Bearer token — response confirmed:  
![burp3](https://github.com/user-attachments/assets/0f4fc55c-1f37-48c7-a3e9-8b350314d2ed)

- Next, hit `/dump` with the same token — revealed **3 different tokens**, each labeled
![burp4](https://github.com/user-attachments/assets/5a9b8dbd-ca27-42ff-8cba-e329ea8ad92a)

- Noticed one was labeled for **flag access**.
- Replaced the old token with the "flag" token and accessed `/flag` again.
  
- Boom 💥 — flag revealed.
![burp5](https://github.com/user-attachments/assets/b795d307-94dc-451c-8974-1abbacf74256)

---


### 🛠️ Tools Used

- Gobuster
- Default Credential Testing
- JWT / Bearer Token Manipulation
- Manual API Testing (with Burp or curl)
- robots.txt enumeration
