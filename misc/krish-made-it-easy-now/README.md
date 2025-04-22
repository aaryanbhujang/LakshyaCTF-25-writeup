## 🕵️‍♂️ Krish Made it EASY
**Category:** Misc  
**Points:** 200  
**Difficulty:** Medium

---

### 🧠 Challenge Summary

This challenge started off like a rabbit hole — layers of misdirection, obscure references, and clever OSINT twists. Here’s how we uncovered the flag:

---

### 🔍 Step-by-Step Walkthrough

#### 1. **Hidden Text on the Challenge Page**

- The challenge page contained invisible white text.
- Upon highlighting, a math-based probability question appeared.
- Solving it yielded: `0.15`  
> Keep this number in mind — it became crucial later.

---

#### 2. **The Google Drive Diversion**

- The same hidden text also linked to a **Google Drive**.
- Inside was a file named `FlagLink.txt`, which looked important.
- But the file redirected to a **Rickroll video** — a false lead.

---

#### 3. **Cryptic Reference to Shaye**

- The Drive description had a line:
  > “Ever felt the urge to do the 'Hand Thing'? Dive into the surreal and let Shaye guide you.”
- Searching **"Shaye hand thing"** led to a creepy, surreal video.

---

#### 4. **Following the Comments**

- Among the YouTube comments was one that read:
  > “i was here”
- Clicking on the commenter’s profile revealed a **channel description**.

---

#### 5. **The Hexadecimal Lead**

- The YouTube profile description contained a **hex string**.
- Decoding the string revealed a **Proton Drive link**:

[https://drive.proton.me
](https://drive.proton.me/urls/RN41PTM7PG#bwglQBPAhFGX)

---

#### 6. **Password-Protected Vault**

- The Proton Drive folder was **locked** with a password.
- Recalling the earlier math solution — `0.15` — we tried it.
- The folder **unlocked**.

---

#### 7. **Final Clue — The Image**

- Inside the Proton Drive was an image file: `InsideImage`.
- A careful look, combined with the cryptic puzzle theme, hinted toward the answer.
- Guessed the final flag based on thematic cues:
  Cicada 3301
  ![InsideImage](https://github.com/user-attachments/assets/c50a9ef9-c1be-4e68-8fdd-db0f00f539be)

