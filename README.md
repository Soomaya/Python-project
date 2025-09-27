# 📧 Automated Email Reporting for Finance Team

**Overview**
I built this project to automatically send finance reports by email. Instead of attaching files and sending them manually each week, the script handles everything automatically, ensuring reports are delivered on time.

**Technology**

* Python
* smtplib
* email
* schedule

**Code Example**

```python
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
```

**Steps**

1. Update the script with your email credentials and recipient list.
2. Place the finance report file in the same folder.
3. Run the script — it will send emails automatically based on the schedule.

**What I Learned**

* Automating repetitive email tasks with Python
* Using `smtplib` and `email` libraries to send attachments
* Creating a reliable workflow to save time in finance reporting

---

## Contact

[![Contact Me](https://img.shields.io/badge/📧-Email-blue?style=for-the-badge)](mailto:soumayaelfadili@gmail.com)
