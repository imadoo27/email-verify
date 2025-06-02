```markdown
# 💌 HTML Email Verification API — Smart, Simple & Instant

Easily send beautiful verification or notification emails using just a URL. No backend, no SMTP, just fast HTML-based delivery via a secure proxy.

---

## 🚀 API Endpoint

```

[https://bot-imad213.fwh.is/proxy.php/p](https://bot-imad213.fwh.is/proxy.php/p)

````

---

## 🔑 Authentication

You'll need an API key to use this service:

- Example: `IMAD213`
- Provided by the service admin.
- Must be included in each request.

---

## ✨ Features

- ✅ Supports HTML content (no encoding required!)
- ✅ Replace `{verification_code}` automatically
- ✅ Works with any platform: browser, mobile, backend
- ✅ Fast delivery via proxy
- ✅ No SMTP or third-party setup

---

## 📤 Request Format

**GET Parameters:**

| Parameter  | Description                          | Required |
|------------|--------------------------------------|----------|
| `email`    | Recipient email address              | ✅       |
| `message`  | Email content (supports full HTML)   | ✅       |
| `subject`  | Subject of the email                 | ✅       |
| `apikey`   | Your personal API key                | ✅       |

🔒 HTML is sent **as-is** — no need to encode it.  
🧩 The placeholder `{verification_code}` will be replaced with a real code on delivery.

---

## 🌍 Example Request

```url
https://bot-imad213.fwh.is/proxy.php/p?email=user@example.com&message=<p>Your code is <b>{verification_code}</b></p>&subject=Email Verification&apikey=IMAD213
````

---

## 💻 Code Integration Examples

### 🐍 Python (requests)

```python
import requests

params = {
    "email": "user@example.com",
    "message": "<p>Your code is <b>{verification_code}</b></p>",
    "subject": "Verify Email",
    "apikey": "IMAD213"
}

response = requests.get("https://bot-imad213.fwh.is/proxy.php/p", params=params)
print(response.text)
```

---

### 🐘 PHP

```php
<?php
$url = "https://bot-imad213.fwh.is/proxy.php/p";
$params = [
    "email" => "user@example.com",
    "message" => "<p>Your code is <b>{verification_code}</b></p>",
    "subject" => "Your Code",
    "apikey" => "IMAD213"
];
echo file_get_contents($url . '?' . http_build_query($params));
?>
```

---

### 🌐 JavaScript (Fetch API)

```js
const params = new URLSearchParams({
  email: "user@example.com",
  message: "<p>Your code is <b>{verification_code}</b></p>",
  subject: "Verification Email",
  apikey: "IMAD213"
});

fetch("https://bot-imad213.fwh.is/proxy.php/p?" + params)
  .then(res => res.text())
  .then(console.log);
```

---

### 🧾 HTML Form Example

```html
<form action="https://bot-imad213.fwh.is/proxy.php/p" method="get">
  <input type="email" name="email" placeholder="Recipient Email" required><br>
  <textarea name="message" rows="5" placeholder="Your HTML Message (e.g. include {verification_code})" required></textarea><br>
  <input type="text" name="subject" value="Verify Your Email" required><br>
  <input type="hidden" name="apikey" value="IMAD213">
  <button type="submit">Send Email</button>
</form>
```

---

## 🌐 Arabic Description | الوصف العربي

### ✅ ما هذه الخدمة؟

هي واجهة برمجية لإرسال رسائل تحقق عبر البريد الإلكتروني بصيغة HTML، دون أي إعدادات SMTP، فقط عبر رابط واحد.

### 🧩 مثال:

```
https://bot-imad213.fwh.is/proxy.php/p?email=you@example.com&message=<p>رمزك: <b>{verification_code}</b></p>&subject=التحقق&apikey=IMAD213
```

### 💡 الميزات:

* تدعم HTML مباشرة (بدون ترميز)
* يتم استبدال `{verification_code}` تلقائيًا
* مناسبة لأي تطبيق: ويب، بايثون، PHP، جافاسكريبت
* لا حاجة لسيرفر أو SMTP
* إرسال سريع عبر خادم Proxy

---

## ⚠️ Important Notes

* Use `{verification_code}` only once per message.
* Avoid sharing your `apikey` publicly.
* Do not abuse the system (rate limited).

---

## 💬 Need Help?

If you're stuck, reach out to the admin or open an issue on GitHub (if available).

---

🎉 Enjoy seamless email delivery!

```
