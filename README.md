# LeafyBeans OMR — Instant Bubble Sheet Scanner & DepEd Item Analysis

[![Launch App](https://img.shields.io/badge/Launch_Web_App-LeafyBeans_OMR-4f46e5?style=for-the-badge&logo=googlechrome&logoColor=white)](https://kyeligoyo.pythonanywhere.com/OMR/)
[![Developer Portfolio](https://img.shields.io/badge/Developer-Engr._Kyle_Eligoyo,_ECE,_ECT-0f172a?style=for-the-badge)](https://kyeligoyo.pythonanywhere.com/)
[![Platform](https://img.shields.io/badge/Platform-Web_%7C_PWA_(Android,_iOS,_Desktop)-10b981?style=for-the-badge)](#)

**LeafyBeans OMR** is a privacy-first, browser-based Optical Mark Recognition (OMR) scanner and installable Progressive Web App (PWA) built for Philippine educators.

Designed as a flexible, teacher-friendly **ZipGrade alternative**, it grades custom 1-to-200 item bubble sheets in under a second using a phone camera, automatically computes **DepEd-ready Mean Percentage Score (MPS)** and item analysis, and syncs all grading records directly to your personal **Google Drive**.

👉 **Live Application:** [https://kyeligoyo.pythonanywhere.com/OMR/](https://kyeligoyo.pythonanywhere.com/OMR/)  
👉 **Author Portfolio:** [https://kyeligoyo.pythonanywhere.com/](https://kyeligoyo.pythonanywhere.com/)

---

## ✨ Key Features

* **Custom Printable Answer Sheets (1–200 Items):** Never get locked into fixed 20, 50, or 100-item templates. Generate **Pre-designed** (with customizable school/exam headers and saved local preferences) or **Plain** sheets with **2 to 5 choices (A–E)**, **Horizontal or Vertical** layouts, and labels **inside** or **on top of bubbles**. Print directly from the browser or export as **PNG, JPG, or print-ready PDF** in paper-saving **1-Up, 2-Up, or 4-Up** layouts with cutting guides for A4, Short (Letter), Long (PH Folio), Legal, and A5 paper.
* **DepEd-Ready Item Analysis & MPS:** Automatically computes **Mean Percentage Score (MPS)**, Standard Deviation, Median, Percentile Ranks, and **Point-Biserial Discriminant Factors** (`r`) to flag problematic test questions.
* **Live & Post-Scan Re-Grading:** Spotted a typo in an Answer Key or Student List after scanning 45 papers? Edit or replace the key or roster anytime — every student's score, graded image overlay, and Excel report recalculates automatically without re-scanning.
* **Crash-Safe Local Draft Recovery (`IndexedDB`):** Unsaved batch and append sessions are automatically persisted locally on your device as binary Blobs inside browser `IndexedDB` storage, with cross-device conflict checks so accidental tab closes, crashes, or connection drops won't wipe active work before saving to Google Drive.
* **Partial Credit, Custom Weights & Bonus Items:** Assign custom point values per option, allow multiple correct answers (*No incorrect allowed*, *Exact match*, or *Ignore incorrect*), or configure bonus items that credit points without inflating the test's perfect score.
* **Multi-Section Cross-Batch Reports:** Combine active and archived class batches into a consolidated grade-level analytics report and export formatted **Excel (`.xlsx`)** spreadsheets with Male/Female and missing-student toggles.
* **100% Client-Side Privacy & Google Drive Sync:** Powered locally by **OpenCV.js** in your browser. Zero student names, test papers, or grades are ever uploaded to the backend server — everything is saved directly inside your own Google Drive (`LeafyBeans OMR Workspace`) with one-tap **ZIP backup & restore**.

---

## 🚀 Quick-Start Guide for Teachers

### 1. Generate & Print Your Sheet
1. Open [LeafyBeans OMR](https://kyeligoyo.pythonanywhere.com/OMR/) and sign in with Google.
2. Under **Print Sheet**, set your **Total Items** (1–200), **Choices** (`A–B` up to `A–E`), **Layout** (`Horizontal` or `Vertical`), and **Choice Labels** (`Inside Bubbles` or `Top of Bubbles`).
3. Click **Generate Sheet**, customize your **Pre-designed** exam header (or switch to **Plain Sheet**), then print directly or export a **1-Up, 2-Up, or 4-Up** PDF, PNG, or JPG on A4, Short, or Long (Folio) bond paper.

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

### 4. Scan, Verify & Export
Select your Answer Key, Student List, and Sheet Layout, then tap **Start Scanning**. Align the 4 black corner squares inside the camera guide for instant grading, visually inspect detected marks and student IDs, and export your **Summary.xlsx** or **Batch ZIP**.

---

## 💳 Pricing & Plans (No Recurring Fees)

LeafyBeans OMR uses a **prepaid, pay-only-when-you-need-it** model — there are **no recurring fees, no auto-renewals, and no cancellation steps required**:

* **Basic (Free Forever):** Includes **200 free scans every month**, custom sheet generation (1–200 items), full DepEd MPS & item analysis, Excel export, and Google Drive sync.
* **1-Month Unlimited Free Trial:** Available once per eligible account with instant activation — **no card or payment info needed**, and it automatically reverts to the Basic free tier when it ends without charging you.
* **Prepaid Premium Passes (`₱30 / 30 days` or `₱300 / 1 year`):** Unlocks unlimited monthly scans and appending late/make-up scans to saved batches (**Add Scans**). Paid via one-time **GCash or Maya** QR transfer with in-app receipt tracking — extend anytime, and remaining days automatically stack. *(Personal-use digital access passes only; official BIR sales invoices or institutional MOOE procurement documents are not issued.)*

---

## 🔒 Privacy & Client-Side Architecture

LeafyBeans OMR is designed for compliance with the **Philippine Data Privacy Act of 2012 (RA 10173)**:

* **Zero Server-Side Grading Storage:** Image warping, bubble evaluation, Excel generation, and ZIP compression execute 100% locally in your device's browser. No student names, test papers, or grades are ever transmitted to or stored on the backend server.
* **Local Crash-Recovery Drafts (`IndexedDB`):** Unsaved batch scanning sessions are temporarily cached only on your own device inside browser `IndexedDB` (`LeafyBeansOMR_Drafts`) until the batch is finished, aborted, discarded, or replaced. Local auto-save is a convenience feature (browsers may clear local storage under Private/Incognito mode or low-storage conditions); on shared devices, delete any unsaved drafts and clear browser site data after use.
* **Restricted Google Drive Scope (`drive.file`):** The app can only access files and folders it creates inside your `LeafyBeans OMR Workspace` folder and cannot view any other files in your Google Drive. Educators act as the sole Personal Information Controller (PIC) for student records processed locally or saved in their Google Drive.
* **No Stored Payment Credentials:** Because upgrades are manual one-time QR transfers, no credit/debit card details or auto-debit tokens are ever collected. Uploaded receipt screenshots are processed strictly in volatile server memory (RAM) for verification email forwarding and are never saved to server disk; verification emails in the Developer's inbox are automatically scheduled for deletion after **12 months** unless held for an active payment dispute.

---

## 📬 Support, Legal & Disclaimers

Independently developed and operated by **Engr. Kyle Eligoyo, ECE, ECT**

* Website: [https://kyeligoyo.pythonanywhere.com/](https://kyeligoyo.pythonanywhere.com/)
* Email: [eligoyokyleofficial@gmail.com](mailto:eligoyokyleofficial@gmail.com)
* Legal: [Terms & Conditions](https://kyeligoyo.pythonanywhere.com/OMR/?show=terms) • [Privacy Policy](https://kyeligoyo.pythonanywhere.com/OMR/?show=privacy)

*Disclaimer: LeafyBeans OMR is provided "as-is" as a grading aid; because lighting, camera focus, print quality, and shading affect optical recognition, educators remain solely responsible for visually verifying all detected marks and scores before official recording or release. ZipGrade® is a registered trademark of ZipGrade LLC. LeafyBeans OMR is an independent application and is not affiliated with, endorsed by, or sponsored by ZipGrade LLC, Google LLC, GCash (G-Xchange, Inc.), Maya Philippines, Inc., or the Department of Education (DepEd).*
