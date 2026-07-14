# HIPAA
HIPAA Compliance Dashboard
# HIPAA Guard 🛡️
### Interactive Security Risk Assessment (SRA) & OCR Audit Protocol Guide

**HIPAA Guard** is an offline-first, client-side web application designed to help healthcare organizations, compliance officers, and software developers navigate the complexities of the Health Insurance Portability and Accountability Act (HIPAA) Security Risk Assessment (SRA) and the HHS Office for Civil Rights (OCR) Audit Protocol guidelines.

---

## 🔒 Crucial Privacy & Security Architecture
HIPAA Guard is designed to operate under the strictest data privacy constraints, making it fully compliant with clinical data environments:
* **100% Client-Side Processing**: The application runs entirely within your web browser. There is no backend server, database, or external API integration. 
* **Zero Remote Data Transmission**: Absolutely no data (including your answers, notes, compliance percentage, or session statistics) is transmitted to or stored on any external servers, cloud providers, or telemetry services.
* **Local Browser Storage**: Your assessment progress, notes, and flags are stored securely on your local computer using the browser's sandbox environment (`localStorage`).
* **Offline Import/Export**: You can export your progress to a localized `.json` report file to clear your browser session or back up your audit progress. This file can be imported back into the tool to resume work later.
* **Air-Gapped Safe**: Since it does not require an active internet connection to function, this application can be hosted and run on secure, air-gapped networks.

---

## 🚀 Key Features

1. **Interactive SRA Questionnaire**: Contains 7 sections mapping to the ONC/HHS Security Risk Assessment guidelines (SRA Basics, Policies & Procedures, Management & Roles, Workforce & Access, Physical Safeguards, Vendor Security, and Contingency Plans).
2. **OCR Audit Protocol Reference Tool**: Search, filter, and browse all 180 official HHS Office for Civil Rights (OCR) audit inquiry standards categorized under Privacy, Security, and Breach Notification rules.
3. **Dynamic Cross-Referencing**: Selecting any question in the SRA questionnaire automatically references and displays corresponding federal HIPAA OCR Audit Protocol criteria side-by-side.
4. **Interactive Dashboard**: Keep track of overall compliance percentages, question completion rates, and flagged risk areas in real-time.
5. **Assessment Reporting**: Generate local, readable reports in JSON format to document your findings and action plans.

---

## 📁 File Structure

The project directory consists of the following components:

### Standalone Application
* [index.html](file:///d:/AI-Projs/AntiGravity/HIPAA/index.html): The **fully self-contained** HTML application containing all markup, visual styling, database question definitions, and interactive logic. This is the **only** file a user needs to open to run the complete guide.

### Source Files (For Development Reference Only)
* [style.css](file:///d:/AI-Projs/AntiGravity/HIPAA/style.css): The CSS source stylesheet.
* [app.js](file:///d:/AI-Projs/AntiGravity/HIPAA/app.js): The core JavaScript logic source code.
* [hipaa_data.js](file:///d:/AI-Projs/AntiGravity/HIPAA/hipaa_data.js) & [hipaa_data.json](file:///d:/AI-Projs/AntiGravity/HIPAA/hipaa_data.json): The source JavaScript and JSON database objects.

### Reference Documents
* `HIPAA Audit protocol.xlsx`: HHS Office for Civil Rights (OCR) HIPAA Audit Protocol worksheet.
* `SRA_Tool_3_6_1-Excel_Workbook1.xlsx`: Official Security Risk Assessment (SRA) Tool Excel sheet.
* `NIST.SP.800-66r2.pdf`: NIST Special Publication 800-66 Revision 2 guide: *Implementing the Health Insurance Portability and Accountability Act (HIPAA) Security Rule*.

---

## 🌐 Deployment & Execution Guide

Running ad-hoc local servers or executing local script files (such as PowerShell scripts) is not considered secure for managing HIPAA assessments or handling potential Protected Health Information (PHI). 

To ensure security and compliance, HIPAA Guard should be run or deployed using one of the following methods:

### Option 1: Direct Sandboxed Execution (Offline Mode)
For individual assessments, open [index.html](file:///d:/AI-Projs/AntiGravity/HIPAA/index.html) directly in a modern, secure web browser:
1. Open your browser in Private/Incognito mode (to prevent persistent caching or cross-origin access by other tabs).
2. Open [index.html](file:///d:/AI-Projs/AntiGravity/HIPAA/index.html) directly by dragging it into the browser window or using the browser's File Open dialog.
3. Since [index.html](file:///d:/AI-Projs/AntiGravity/HIPAA/index.html) is fully self-contained, no other files or external folder resources are required to load or run the application.

### Option 2: Secure Enterprise Web Hosting (Recommended)
For organizational audits and collaborative assessments, deploy the single static [index.html](file:///d:/AI-Projs/AntiGravity/HIPAA/index.html) file to a secure, HIPAA-compliant web server (such as an internal intranet server managed by IIS, Apache, or Nginx). Ensure the hosting environment implements the following security safeguards:
* **HTTPS/TLS Enforced**: Secure all communications using TLS 1.3 or 1.2 to encrypt data in transit.
* **Access Controls**: Require authentication (e.g., Active Directory / Single Sign-On) to ensure only authorized compliance personnel can load the page.
* **Security Headers**: Enforce HTTP security headers, including a strict Content Security Policy (CSP) to prevent cross-site scripting (XSS) and unauthorized data leakage.

---

## 🛠️ Data Management

### Saving Progress
Your progress is automatically saved to `localStorage` every time you:
* Choose a status response (Yes, No, In Progress, N/A) for an SRA question.
* Edit custom comments or notes.
* Toggle the "Flag for Review" checkbox on risk items.

### Backup and Export
1. Click the **📥 Export Report** button in the header.
2. A `.json` report file containing your metadata, compliance score, and answers will download to your local machine.

### Restoring Progress
1. Click the **📤 Import State** button in the header.
2. Drag and drop your previously exported `.json` file into the dialog box, or click the zone to browse and select it.
3. Your local browser session will immediately update with the imported state.

### Resetting Session
Click the red **🔄 Reset** button in the header to wipe the in-memory state and clear the `localStorage` keys, returning the SRA tool to a blank assessment.
