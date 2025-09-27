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
