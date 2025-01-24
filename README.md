# Valid-form-Notifier

ValidForm Notifier is a Python script designed to read and validate personal data from a file, then send an email notification to valid entries. It ensures that the data follows a specific format using regular expressions and notifies users via email if their data is correct.

Features
Data Validation: Validates the following fields using regular expressions:

First Name (alphabetic characters and spaces only)
Last Name (uppercase alphabets only)
Mobile Number (10-digit number)
Date of Birth (in DD-MM-YYYY format)
Gender (either MALE or FEMALE)
Email Address (must be a Gmail address)
Email Notification: Sends a personalized email to valid entries with their details (e.g., name, DOB, gender, etc.).

Error Handling: Skips sending emails to entries with invalid data and notifies the user in the console.

Requirements
Python 3.x
smtplib (Standard Library)
email.mime.multipart, email.mime.text (Standard Library)
A Gmail account with access to SMTP (ensure "Less secure app access" is enabled in your Gmail account)
How It Works
Reading Data: The script reads personal details from a text file (details.txt). Each line in the file contains comma-separated values for an individual entry.

Data Validation: It validates each entry based on the following criteria:

First Name: Only alphabetic characters and spaces.
Last Name: Uppercase alphabets only.
Mobile Number: A valid 10-digit number.
Date of Birth: Should follow the format DD-MM-YYYY.
Gender: Must be either MALE or FEMALE.
Email Address: Must be a valid Gmail address.
Email Sending: If all data fields are valid, an email is sent to the provided Gmail address. The email contains the user's personal information.

Error Handling: If any data field is invalid, the script will skip that entry and print a message indicating which user's data was incorrect.

How to Run the Script
Clone or download the repository to your local machine.

Update the send_mail() function with your Gmail credentials:

python
Copy
server.login("your-email@gmail.com", "your-email-password")
Prepare a details.txt file with the following format:

mathematica
Copy
First Name,Last Name,Mobile Number,Date of Birth,Gender,Email Address
Example:

css
Copy
John,Doe,1234567890,12-05-1990,MALE,john.doe@gmail.com
Place the details.txt file in the same directory as the script.

Run the script:

bash
Copy
python validform_notifier.py
Check the console output for email notifications and validation results.

Security Notice
Ensure that sensitive information like email credentials is stored securely. Consider using environment variables or more secure methods (such as OAuth2) for authentication instead of hardcoding your credentials in the script.

