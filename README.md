# 🚀 AWS S3 Static Website Hosting

This project is about hosting a static website on **Amazon S3**.  
Final Result: [http://my-website-mohamed.s3-website-us-east-1.amazonaws.com/](http://my-website-mohamed.s3-website-us-east-1.amazonaws.com/)

---

## 📂 1. Create an S3 Bucket

- Go to the [AWS S3 Console](https://s3.console.aws.amazon.com/s3/).
- Click on **Create bucket**.
- Enter a unique bucket name (`my-website-mohamed`).
- **Uncheck "Block all public access"** under permissions.
- Click **Create bucket**.

---

## 🌐 2. Enable Static Website Hosting

- Go to your bucket > **Properties** tab.
- Scroll down to **Static website hosting**.
- Click **Edit** and:
  - Enable static website hosting.
  - Enter `index.html` for **Index document**.
  - Enter `error.html` for **Error document**.

---

## 🔓 3. Enable Public Access

- Go to the **Permissions** tab .
- Scroll to **Block public access**.
- Click **Edit**, uncheck **Block all public access**, and save.

---

## 🛡️ 4. Add a Bucket Policy

- Still under the **Permissions** tab, scroll to **Bucket policy**.
- Add the following policy (replace with your bucket name if different):

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-website-mohamed/*"
    }
  ]
}
```

