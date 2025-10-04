<<<<<<< HEAD
# 📧 Automated Email Reporting for Finance Team

**Overview**
I built this project to automatically send finance reports by email. Instead of attaching files and sending them manually each week, the script handles everything automatically, ensuring reports are delivered on time.
=======
# 📄 Bulk PDF Automation Tool

**Overview**
I created this project to open all PDF files in a selected folder with one click. Instead of opening documents manually one by one, the script utilizes Python to automate the process through a simple graphical interface.
>>>>>>> bulk-branch

**Technology**

* Python
<<<<<<< HEAD
* smtplib
* email
* schedule
=======
* os
* tkinter
* webbrowser
>>>>>>> bulk-branch

**Code Example**

```python
<<<<<<< HEAD
import smtplib
from email.message import EmailMessage
import schedule
import time

def send_finance_report():
    msg = EmailMessage()
    msg['Subject'] = 'Weekly Finance Report'
    msg['From'] = 'your_email@example.com'
    msg['To'] = 'finance_team@example.com'
    msg.set_content('Please find the attached finance report.')

    # Attach a file
    with open('report.xlsx', 'rb') as f:
        file_data = f.read()
        file_name = f.name
    msg.add_attachment(file_data, maintype='application', subtype='octet-stream', filename=file_name)

    # Send email
    with smtplib.SMTP_SSL('smtp.example.com', 465) as smtp:
        smtp.login('your_email@example.com', 'password')
        smtp.send_message(msg)
    print("Email sent successfully!")

# Example scheduling
schedule.every().monday.at("09:00").do(send_finance_report)

while True:
    schedule.run_pending()
    time.sleep(60)
=======
import os
import tkinter as tk
from tkinter import filedialog, messagebox
import webbrowser

def open_all_pdfs():
    folder_selected = filedialog.askdirectory(title="Select Folder with PDFs")
    if not folder_selected:
        return  # User canceled

    pdf_files = [f for f in os.listdir(folder_selected) if f.endswith(".pdf")]

    if not pdf_files:
        messagebox.showinfo("No PDFs", "No PDF files found in the selected folder.")
        return

    for pdf in pdf_files:
        pdf_path = os.path.join(folder_selected, pdf)
        print(f"Opening: {pdf_path}")
        webbrowser.open_new(pdf_path)

# GUI setup
root = tk.Tk()
root.title("PDF Opener")
root.geometry("300x150")

label = tk.Label(root, text="Open All PDFs in a Folder", font=("Arial", 12))
label.pack(pady=20)

open_button = tk.Button(root, text="Open All PDFs", command=open_all_pdfs, bg="#4CAF50", fg="white", padx=10, pady=5)
open_button.pack()

root.mainloop()
>>>>>>> bulk-branch
```

**Steps**

<<<<<<< HEAD
1. Update the script with your email credentials and recipient list.
2. Place the finance report file in the same folder.
3. Run the script — it will send emails automatically based on the schedule.

**What I Learned**

* Automating repetitive email tasks with Python
* Using `smtplib` and `email` libraries to send attachments
* Creating a reliable workflow to save time in finance reporting
=======
1. Run the script.
2. Select the folder that contains your PDF files.
3. The script will scan and open all PDFs automatically.
4. Each file is opened in the system’s default PDF viewer.

**What I Learned**

* Building simple GUIs with Python’s `tkinter`
* Automating repetitive file-handling tasks
* Practical applications of Python in office workflows
>>>>>>> bulk-branch

---

## Contact

[![Contact Me](https://img.shields.io/badge/📧-Email-blue?style=for-the-badge)](mailto:soumayaelfadili@gmail.com)
