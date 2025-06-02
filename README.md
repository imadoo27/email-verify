```markdown
# 📧 API Documentation — Verification Message Sender

This API allows you to send HTML-based verification emails using a secure token.

---

## 🔑 How to Get Your API Key

1. Contact the administrator to obtain your unique API key.
2. You’ll receive a key like: `IMAD123456`
3. Keep your key safe and do not share it.

---

## 🌐 Base API Endpoint

```
https://bot-imad213.fwh.is/redirect.php
```

---

## 📤 How to Send a Verification Email

### 🧾 Basic Request Format

```
GET /p?email=EMAIL&message=MESSAGE&subject=SUBJECT&apikey=YOUR_API_KEY
```

### 📌 Required Parameters

| Parameter | Description |
|----------|-------------|
| `email`   | Recipient's email address |
| `message` | Email content (HTML, URL-encoded) |
| `subject` | Subject of the email |
| `apikey`  | Your API key |

---

## 💡 Example Message Content (HTML)

### 👇 Simple & Clean HTML

```html
<div dir="rtl" style="font-family: Tahoma, Arial; background-color: #f9f9f9; padding: 20px; border: 1px solid #ddd;">
  <h2 style="color: #333;">مرحبا!</h2>
  <p>رمز التحقق الخاص بك هو:</p>
  <div style="font-size: 24px; font-weight: bold; background: #eee; padding: 15px; text-align: center; margin: 15px 0;">
    {verification_code}
  </div>
  <p style="color: #888;">هذا الرمز صالح لمدة 10 دقائق فقط.</p>
</div>
```

> Use `{verification_code}` inside your message; it will be replaced automatically by the actual code.

---

## 🌍 Full Example (URL-encoded)

```
https://bot-imad213.fwh.is/redirect.php/p?email=user@example.com&message=%3Cdiv%20dir%3D%22rtl%22%20style%3D%22font-family%3A%20Tahoma%2C%20Arial%3B%20background-color%3A%20%23f9f9f9%3B%20padding%3A%2020px%3B%20border%3A%201px%20solid%20%23ddd%3B%22%3E%3Ch2%20style%3D%22color%3A%20%23333%3B%22%3E%D9%85%D8%B1%D8%AD%D8%A8%D8%A7!%3C/h2%3E%3Cp%3E%D8%B1%D9%85%D8%B2%20%D8%A7%D9%84%D8%AA%D8%AD%D9%82%D9%82%20%D8%A7%D9%84%D8%AE%D8%A7%D8%B5%20%D8%A8%D9%83%20%D9%87%D9%88%3A%3C/p%3E%3Cdiv%20style%3D%22font-size%3A%2024px%3B%20font-weight%3A%20bold%3B%20background%3A%20%23eee%3B%20padding%3A%2015px%3B%20text-align%3A%20center%3B%20margin%3A%2015px%200%3B%22%3E%7Bverification_code%7D%3C/div%3E%3Cp%20style%3D%22color%3A%20%23888%3B%22%3E%D9%87%D8%B0%D8%A7%20%D8%A7%D9%84%D8%B1%D9%85%D8%B2%20%D8%B5%D8%A7%D9%84%D8%AD%20%D9%84%D9%85%D8%AF%D8%A9%2010%20%D8%AF%D9%82%D8%A7%D8%A6%D9%82%20%D9%81%D9%82%D8%B7.%3C/p%3E%3C/div%3E&subject=رمز%20التحقق&apikey=IMAD123456
```

---

## 🧪 Code Examples

### 🐍 Python (requests)
```python
import requests
params = {
    "email": "user@example.com",
    "message": "<p>Your verification code is: {verification_code}</p>",
    "subject": "Verification Code",
    "apikey": "IMAD123456"
}
r = requests.get("https://bot-imad213.fwh.is/redirect.php/p", params=params)
print(r.text)
```

---

### 🐘 PHP (file_get_contents)
```php
<?php
$email = "user@example.com";
$message = urlencode("<p>Your verification code is: {verification_code}</p>");
$subject = "Verification Code";
$apikey = "IMAD123456";

$url = "https://bot-imad213.fwh.is/redirect.php/p?email=$email&message=$message&subject=$subject&apikey=$apikey";
$response = file_get_contents($url);
echo $response;
?>
```

---

### 🌐 JavaScript (Fetch API)
```js
const params = new URLSearchParams({
  email: "user@example.com",
  message: "<p>Your verification code is: {verification_code}</p>",
  subject: "Verification Code",
  apikey: "IMAD123456"
});

fetch("https://bot-imad213.fwh.is/redirect.php/p?" + params)
  .then(res => res.text())
  .then(console.log)
  .catch(console.error);
```

---

## ⚠️ Important Notes

- Make sure your message is **URL encoded**.
- Do **not share** your API key.
- Maximum message size: `100KB`
- API limit: `100 requests/hour`

---

## 📘 الترجمة إلى العربية

- لطلب إرسال بريد تحقق:
  ```
  GET /p?email=البريد&message=الرسالة&subject=العنوان&apikey=رمز_API
  ```
- استخدم `{verification_code}` ليتم تعويضه بالرمز فعليًا.
- أدخل الرسالة بصيغة HTML، مع ترميز URL.

---

## 🆘 Need Help?

If something isn’t working:
- Check if the API key is valid.
- Ensure the email is correct.
- Use `{verification_code}` properly in your message.

For support, contact admin with:
- Partially masked API key (e.g. `IMAD****`)
- Target email
- Full request or error
```
