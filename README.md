```markdown
# 📧 Email Verification API — Fast & Easy HTML Email Sender

Easily send rich HTML verification messages using a lightweight and secure API. Designed for developers who need quick and stylish verification emails — no SMTP or backend configuration required.

---

## 🌐 Base URL

```

[https://bot-imad213.fwh.is/redirect.php/p](https://bot-imad213.fwh.is/redirect.php/p)

```

---

## 🔑 Get Your API Key

To use this API, you need a personal API key.

- Example key: `IMAD213`
- Contact the admin to get your API key.
- Keep it private to avoid misuse.

---

## 📤 Sending an Email

### ✅ Request Format

```

GET /p?email=...\&message=...\&subject=...\&apikey=...

````

| Parameter  | Description                          | Required |
|------------|--------------------------------------|----------|
| `email`    | Recipient email address              | ✅       |
| `message`  | Email body in HTML (raw, not encoded)| ✅       |
| `subject`  | Email subject line                   | ✅       |
| `apikey`   | Your access key                      | ✅       |

✅ No need to encode your HTML — send it as-is!

---

## 📦 Example HTML Message

```html
<div style="background:#f4f4f4; padding:20px; font-family:Arial;">
  <h2 style="color:#2b2b2b;">Welcome!</h2>
  <p>Your verification code is:</p>
  <div style="font-size:24px; font-weight:bold; background:#fff; padding:10px; text-align:center;">
    {verification_code}
  </div>
  <p style="color:#777;">This code is valid for 10 minutes.</p>
</div>
````

🧩 Use `{verification_code}` in your message — it will be automatically replaced with a real code.

---

## 🌍 Full Example Request

```
https://bot-imad213.fwh.is/redirect.php/p?email=user@example.com&message=<div style='padding:10px;'>Your code is <b>{verification_code}</b></div>&subject=Verify Your Email&apikey=IMAD213
```

---

## 💻 Code Examples

### 🐍 Python (using `requests`)

```python
import requests

params = {
    "email": "user@example.com",
    "message": "<p>Your code is <b>{verification_code}</b></p>",
    "subject": "Verify Email",
    "apikey": "IMAD213"
}

r = requests.get("https://bot-imad213.fwh.is/redirect.php/p", params=params)
print(r.text)
```

---

### 🐘 PHP

```php
<?php
$params = [
    "email" => "user@example.com",
    "message" => "<p>Your code is <b>{verification_code}</b></p>",
    "subject" => "Verify Email",
    "apikey" => "IMAD213"
];

$url = "https://bot-imad213.fwh.is/redirect.php/p?" . http_build_query($params);
$response = file_get_contents($url);
echo $response;
?>
```

---

### 🌐 JavaScript (Fetch API)

```js
const params = new URLSearchParams({
  email: "user@example.com",
  message: "<p>Your code is <b>{verification_code}</b></p>",
  subject: "Verify Email",
  apikey: "IMAD213"
});

fetch("https://bot-imad213.fwh.is/redirect.php/p?" + params)
  .then(res => res.text())
  .then(console.log)
  .catch(console.error);
```

---

## 🌐 HTML Example

You can also send a request from a simple HTML form:

```html
<form action="https://bot-imad213.fwh.is/redirect.php/p" method="get">
  <input type="email" name="email" placeholder="Enter email" required><br>
  <textarea name="message" rows="5" placeholder="HTML content with {verification_code}" required></textarea><br>
  <input type="text" name="subject" value="Your Code" required><br>
  <input type="hidden" name="apikey" value="IMAD213">
  <button type="submit">Send Email</button>
</form>
```

---

## 🇸🇦 النسخة العربية

### ✅ ما وظيفة هذه الخدمة؟

هذه الواجهة البرمجية تتيح لك إرسال رسائل تحقق (Verification) بشكل مباشر عبر رابط يحتوي على معلومات البريد والمحتوى.

### 🧾 صيغة الطلب:

```
/p?email=البريد&message=الرسالة (HTML)&subject=الموضوع&apikey=رمز_الدخول
```

✅ يمكنك كتابة محتوى HTML مباشرة، مثل:

```html
<p>رمز التحقق الخاص بك: <b>{verification_code}</b></p>
```

### ⚠️ ملاحظات مهمة:

* لا حاجة لترميز HTML.
* {verification\_code} يتم استبداله تلقائيًا برمز تحقق.
* لا تشارك رمز API الخاص بك.
* الاستخدام العادل: 100 رسالة/ساعة.

---

## 🆘 Need Help?

* Check your API key.
* Ensure message is valid HTML.
* Contact support with request details if issues arise.

---

🚀 Enjoy your email delivery experience!

```
