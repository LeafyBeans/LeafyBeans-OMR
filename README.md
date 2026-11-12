# LeafyBeans OMR — Instant Bubble Sheet Scanner & DepEd Item Analysis

[![Launch App](https://img.shields.io/badge/Launch_Web_App-LeafyBeans_OMR-4f46e5?style=for-the-badge&logo=googlechrome&logoColor=white)](https://kyeligoyo.pythonanywhere.com/OMR/)
[![Developer Portfolio](https://img.shields.io/badge/Developer-Engr._Kyle_Eligoyo,_ECE,_ECT-0f172a?style=for-the-badge)](https://kyeligoyo.pythonanywhere.com/)
[![Platform](https://img.shields.io/badge/Platform-Web_%7C_PWA_(Android,_iOS,_Desktop)-10b981?style=for-the-badge)](#)

**LeafyBeans OMR** is a privacy-first, browser-based Optical Mark Recognition (OMR) scanner and installable Progressive Web App (PWA) built for Philippine educators. 

Designed as a flexible, teacher-friendly **ZipGrade alternative**, it grades custom 1-to-200 item bubble sheets in under a second using your phone camera, automatically computes **DepEd-ready Mean Percentage Score (MPS)** and item analysis, and syncs all grading records directly to your personal **Google Drive**.

👉 **Live Application:** [https://kyeligoyo.pythonanywhere.com/OMR/](https://kyeligoyo.pythonanywhere.com/OMR/)  
👉 **Author Portfolio:** [https://kyeligoyo.pythonanywhere.com/](https://kyeligoyo.pythonanywhere.com/)

---

## ✨ Key Features

* **Custom Printable Answer Sheets (1–200 Items):** Never get locked into fixed 20, 50, or 100-item templates. Generate custom sheets with **2 to 5 choices (A–E)**, **Horizontal or Vertical** layouts, and choice letters placed either **inside** or **on top of bubbles**.
* **DepEd-Ready Item Analysis & MPS:** Automatically computes **Mean Percentage Score (MPS)**, Standard Deviation, Median, Percentile Ranks, and **Point-Biserial Discriminant Factors** (`r`) to flag problematic test questions.
* **Live & Post-Scan Re-Grading:** Spotted a typo in your Answer Key or Student List after scanning 45 papers? Edit or replace the key or roster anytime — every student's score, graded image overlay, and Excel report recalculates automatically without re-scanning.
* **Partial Credit, Custom Weights & Bonus Items:** Assign custom point values per option, allow multiple correct answers (*No incorrect allowed*, *Exact match*, or *Ignore incorrect*), or configure bonus items that credit points without inflating the test's perfect score.
* **Multi-Section Cross-Batch Reports:** Combine active and archived class batches into a consolidated grade-level analytics report and export formatted **Excel (`.xlsx`)** spreadsheets with Male/Female and missing-student toggles.
* **100% Client-Side Privacy & Google Drive Sync:** Powered locally by **OpenCV.js** in your browser. Zero student names, test papers, or grades are ever uploaded to a central server — everything is saved directly inside your own Google Drive (`LeafyBeans OMR Workspace`) with one-tap **ZIP backup & restore**.

---

## 🚀 Quick-Start Guide for Teachers

### 1. Generate & Print Your Sheet
1. Open [LeafyBeans OMR](https://kyeligoyo.pythonanywhere.com/OMR/) and sign in with Google.
2. Under **Print Sheet**, set your **Total Items** (1–200), **Choices** (`A–B` up to `A–E`), **Layout** (`Horizontal` or `Vertical`), and **Choice Labels** (`Inside Bubbles` or `Top of Bubbles`).
3. Click **Generate Sheet**, download the PNG, and print on standard bond paper.

### 2. Prepare Your Student List (`.txt`)
The Student List maps shaded Gender (`M`/`F`) and 2-digit ID bubbles (`01`–`99`) to actual student names:
* List **Male** students first, add **one blank line**, then list **Female** students:
  ```text
  Dela Cruz, Juan A.
  Santos, Mateo B.

  Reyes, Maria C.
  Gomez, Sofia D.
  ```
* **Female-only sections:** Put `NULL` on the first line, followed by a blank line, then the Female names.

### 3. Build Your Answer Key (`.json`)

Tap **+** under **Answer Key**, enter your item count, and tap the correct bubble letters (`A`–`E`). Click the gear icon on any question to configure custom option weights, multiple-answer rules, or bonus items.

### 4. Scan & Export

Select your Answer Key, Student List, and Sheet Layout, then tap **Start Scanning**. Align the 4 black corner squares inside the camera guide for instant grading, then export your **Summary.xlsx** or **Batch ZIP**.

---

## 🔒 Privacy & Stateless Architecture

LeafyBeans OMR complies with the **Philippine Data Privacy Act of 2012 (RA 10173)**:

* **Zero Server-Side Grading Storage:** Image warping, bubble evaluation, Excel generation, and ZIP compression execute 100% locally in your device's browser memory.
* **Restricted Google Drive Scope (`drive.file`):** The app can only access files and folders it creates inside your `LeafyBeans OMR Workspace` folder and cannot view any of your personal Google Drive files.

---

## 📬 Support & Feedback

Developed by **Engr. Kyle Eligoyo, ECE, ECT**

* Website: [https://kyeligoyo.pythonanywhere.com/](https://kyeligoyo.pythonanywhere.com/)
* Email: [eligoyokyleofficial@gmail.com](mailto:eligoyokyleofficial@gmail.com)

*Disclaimer: ZipGrade® is a registered trademark of ZipGrade LLC. LeafyBeans OMR is an independent application and is not affiliated with, endorsed by, or sponsored by ZipGrade LLC, Google LLC, or the Department of Education (DepEd).*
