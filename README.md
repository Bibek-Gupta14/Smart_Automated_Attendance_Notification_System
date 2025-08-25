# 📊 Smart Automated Attendance Notification System

Welcome to the **Smart Automated Attendance Notification System**! 🚀 This project automates attendance management and notification processes using UiPath workflows, streamlining how absences are tracked and communicated to both students and departments.

---

## 🗂️ Project Structure

This repository mainly contains two UiPath workflow files:

- **Main.xaml**  
- **NEW_MAJOR_PROJECT(FINAL VERSION).xaml**
- attendance sheet.xlsx	
- email.html

---

## ⚙️ How It Works

### 1. **Attendance Extraction from Excel**
Both workflows use the **Excel Application Scope** activity to read attendance data from Excel files:
- `attendance sheet original.xlsx` (used in Main.xaml)
- `attendance sheet.xlsx` (used in NEW_MAJOR_PROJECT(FINAL VERSION).xaml)

The attendance data is loaded into a DataTable for processing.

### 2. **Dynamic Column Creation**
The workflow checks if a column for tracking email notifications (e.g., `EmailSent_<Date>`) exists for the latest date:
- If absent, it dynamically creates this column in the DataTable.

### 3. **Absence Detection & Notification**
For each row (student) in the DataTable:
- If the student is marked **"A"** (Absent) for the latest date and hasn't received an email yet:
  - **Email Notification** is sent to the student using SMTP.
    - 📧 Personalized message: "You were marked ABSENT on <Date>. Please contact your professor if you have any questions."
    - The `EmailSent_<Date>` column is updated to "Sent" for that student, preventing duplicate notifications.

#### **HTML Email Support** (NEW_MAJOR_PROJECT)
- In the final version, emails use a customizable HTML template (`email.html`) for more visually engaging notifications! ✨

### 4. **Weekly Report Generation**
- A weekly summary email is generated for the department, attaching the updated attendance sheet.
- Ensures all absentees are notified and records are up-to-date.

### 5. **Process Cleanup**
- The workflow ensures any running Excel processes are killed after execution for clean resource management. 🧹

---

## 🔐 Security & Configuration

- SMTP credentials and email addresses are currently specified in the workflow.
- For production use, consider moving sensitive details (like passwords) to secure assets or environment variables!

---

## 📁 Key Files

| File                               | Description                                  |
|-------------------------------------|----------------------------------------------|
| `Main.xaml`                        | Initial workflow for attendance notification |
| `NEW_MAJOR_PROJECT(FINAL VERSION).xaml` | Advanced workflow with HTML email support and improved reporting |
| `attendance sheet.xlsx`             | Sample attendance data (Excel format)        |
| `email.html`                        | HTML template for personalized emails        |

---

## 📝 Summary

This project automates the tedious process of attendance tracking and absent student notification, ensuring timely communication and efficient reporting—all with minimal manual intervention!  
**Highlights:**
- Automated detection & notification of absentees
- Dynamic data management in Excel
- Personalized email notifications (plain text & HTML)
- Weekly summary reporting to the department
- Clean and maintainable UiPath workflows

---
**CONTRIBUTORS ❤️**

- *__Bibek Gupta__*	🚀
- *__Baibhab Majumder__* 🌟
- *__Aditya Dasgupta__* 🎓
- *__Akash Paul__* 💡
- *__Buvanesh Kavuru__* 🎉

---
