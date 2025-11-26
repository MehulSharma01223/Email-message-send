import os
import smtplib
import ssl
from email.message import EmailMessage
import mimetypes


def send_email_with_attachment(
    sender_email: str,
    app_password: str,
    receiver_email: str,
    subject: str,
    body: str,
    attachment_path: str = None,
) -> None:
    """
    Send an email using Gmail SMTP (SSL) with optional file attachment.

    Parameters:
        sender_email (str): Your Gmail address.
        app_password (str): App password generated from Google Account.
        receiver_email (str): The recipient's email address.
        subject (str): Email subject line.
        body (str): Email body text.
        attachment_path (str): Path to the attachment file. Optional.
    """

    msg = EmailMessage()
    msg["From"] = sender_email
    msg["To"] = receiver_email
    msg["Subject"] = subject
    msg.set_content(body)

    # If attachment is provided
    if attachment_path:
        if not os.path.exists(attachment_path):
            print("Attachment not found:", attachment_path)
            return

        mime_type, _ = mimetypes.guess_type(attachment_path)
        mime_type = mime_type or "application/octet-stream"
        main_type, sub_type = mime_type.split("/", 1)

        with open(attachment_path, "rb") as file:
            file_data = file.read()
            file_name = os.path.basename(attachment_path)
            msg.add_attachment(
                file_data,
                maintype=main_type,
                subtype=sub_type,
                filename=file_name,
            )

        print(f"Attached file: {file_name}")

    context = ssl.create_default_context()

    try:
        with smtplib.SMTP_SSL("smtp.gmail.com", 465, context=context) as server:
            server.login(sender_email, app_password)
            server.send_message(msg)

        print("Email sent successfully.")

    except Exception as e:
        print("An error occurred:", str(e))


if __name__ == "__main__":
    EMAIL = os.getenv("GMAIL_ADDRESS")         # Your Gmail
    APP_PASSWORD = os.getenv("GMAIL_APP_PASSWORD")  # Google App Password

    if not EMAIL or not APP_PASSWORD:
        print("Environment variables are not set.")
    else:
        RECEIVER = "ghanshyamseervi1296@gmail.com"
        SUBJECT = "Test Email With Attachment"
        BODY = "This email contains an attachment sent through Python."

        # Set your file path here
        ATTACHMENT = "sample.pdf"    # Example: 'image.jpg', 'file.zip', etc.

        send_email_with_attachment(
            sender_email=EMAIL,
            app_password=APP_PASSWORD,
            receiver_email=RECEIVER,
            subject=SUBJECT,
            body=BODY,
            attachment_path=ATTACHMENT,
        )
import os
import smtplib
import ssl
from email.message import EmailMessage
import mimetypes


def send_email_with_attachment(
    sender_email: str,
    app_password: str,
    receiver_email: str,
    subject: str,
    body: str,
    attachment_path: str = None,
) -> None:
    """
    Send an email using Gmail SMTP (SSL) with optional file attachment.

    Parameters:
        sender_email (str): Your Gmail address.
        app_password (str): App password generated from Google Account.
        receiver_email (str): The recipient's email address.
        subject (str): Email subject line.
        body (str): Email body text.
        attachment_path (str): Path to the attachment file. Optional.
    """

    msg = EmailMessage()
    msg["From"] = sender_email
    msg["To"] = receiver_email
    msg["Subject"] = subject
    msg.set_content(body)

    # If attachment is provided
    if attachment_path:
        if not os.path.exists(attachment_path):
            print("Attachment not found:", attachment_path)
            return

        mime_type, _ = mimetypes.guess_type(attachment_path)
        mime_type = mime_type or "application/octet-stream"
        main_type, sub_type = mime_type.split("/", 1)

        with open(attachment_path, "rb") as file:
            file_data = file.read()
            file_name = os.path.basename(attachment_path)
            msg.add_attachment(
                file_data,
                maintype=main_type,
                subtype=sub_type,
                filename=file_name,
            )

        print(f"Attached file: {file_name}")

    context = ssl.create_default_context()

    try:
        with smtplib.SMTP_SSL("smtp.gmail.com", 465, context=context) as server:
            server.login(sender_email, app_password)
            server.send_message(msg)

        print("Email sent successfully.")

    except Exception as e:
        print("An error occurred:", str(e))


if __name__ == "__main__":
    EMAIL = os.getenv("GMAIL_ADDRESS")         # Your Gmail
    APP_PASSWORD = os.getenv("GMAIL_APP_PASSWORD")  # Google App Password

    if not EMAIL or not APP_PASSWORD:
        print("Environment variables are not set.")
    else:
        RECEIVER = "ghanshyamseervi1296@gmail.com"
        SUBJECT = "Test Email With Attachment"
        BODY = "This email contains an attachment sent through Python."

        # Set your file path here
        ATTACHMENT = "sample.pdf"    # Example: 'image.jpg', 'file.zip', etc.

        send_email_with_attachment(
            sender_email=EMAIL,
            app_password=APP_PASSWORD,
            receiver_email=RECEIVER,
            subject=SUBJECT,
            body=BODY,
            attachment_path=ATTACHMENT,
        )
