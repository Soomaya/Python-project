# 📄 Bulk PDF Automation Tool

**Overview**
I created this project to open all PDF files in a selected folder with one click. Instead of opening documents manually one by one, the script utilizes Python to automate the process through a simple graphical interface.

**Technology**

* Python
* os
* tkinter
* webbrowser

**Code Example**

```python
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
```

**Steps**

1. Run the script.
2. Select the folder that contains your PDF files.
3. The script will scan and open all PDFs automatically.
4. Each file is opened in the system’s default PDF viewer.

**What I Learned**

* Building simple GUIs with Python’s `tkinter`
* Automating repetitive file-handling tasks
* Practical applications of Python in office workflows

---

## Contact

[![Contact Me](https://img.shields.io/badge/📧-Email-blue?style=for-the-badge)](mailto:soumayaelfadili@gmail.com)
