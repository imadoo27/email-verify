# 📧 Verification Message Sending API

Welcome to the documentation for the API used to send verification messages via email.

مرحبًا بك في وثائق استخدام واجهة API الخاصة بإرسال رسائل التحقق عبر البريد الإلكتروني.

---

## 🔐 How to Get Your API Key

1. Contact the administrator to request your API key.
2. You will receive a key like:
   ```
   IMAD123456
   ```
3. Store your key securely.

1. تواصل مع المسؤول للحصول على مفتاح API الخاص بك.
2. سيتم تزويدك بمفتاح مثل: `IMAD123456`
3. احتفظ بالمفتاح في مكان آمن.

---

## 🌐 Base API URL

```txt
https://yourdomain.com/api
```

---

## 🚀 How to Send a Verification Message

### ✅ Basic Request

```http
GET /p?email=EMAIL&message=MESSAGE&code=CODE&apikey=YOUR_API_KEY
```

### 🔧 Required Parameters

| Parameter   | Description                             | Example                    |
|-------------|-----------------------------------------|----------------------------|
| `email`     | Target user's email address             | user@example.com           |
| `message`   | Message content (HTML format)           | `<p>Your code: {verification_code}</p>` |
| `code`      | Actual verification code to be replaced | 123456                     |
| `apikey`    | Your personal API key                   | IMAD123456                 |

---

### 🧪 Sample Request

```http
https://yourdomain.com/p?email=user@example.com&message=%3Cdiv%3EYour%20code%20is%3A%20%7Bverification_code%7D%3C/div%3E&code=123456&apikey=IMAD123456
```

---

## 💻 Usage Examples in Code

### 🐍 Python

```python
import requests

url = "https://yourdomain.com/p"
params = {
    "email": "user@example.com",
    "message": "<p>Your verification code is: {verification_code}</p>",
    "code": "123456",
    "apikey": "IMAD123456"
}

response = requests.get(url, params=params)
print(response.text)
```

### 🐘 PHP

```php
<?php
$url = "https://yourdomain.com/p";
$params = http_build_query([
    "email" => "user@example.com",
    "message" => "<p>Your verification code is: {verification_code}</p>",
    "code" => "123456",
    "apikey" => "IMAD123456"
]);

$response = file_get_contents($url . "?" . $params);
echo $response;
?>
```

### 🌐 JavaScript (Fetch API)

```javascript
const params = new URLSearchParams({
  email: "user@example.com",
  message: "<p>Your verification code is: {verification_code}</p>",
  code: "123456",
  apikey: "IMAD123456"
});

fetch("https://yourdomain.com/p?" + params)
  .then(res => res.text())
  .then(data => console.log(data))
  .catch(err => console.error(err));
```

---

## ⚠️ Important Notes

- Encode your HTML content properly (use URL encoding).
- Do not share your API key publicly.
- Max message size: **100KB**
- Rate limit: **100 requests/hour**

---

## 🛠️ Troubleshooting

If you encounter issues, check:

- ✅ API key validity
- ✅ Email format correctness
- ✅ `{verification_code}` exists in the message

### 🆘 Support

Please provide the following when contacting support:

- Your (partially hidden) API key: `IMAD****`
- Target email address
- Full issue description

---

🎉 Thank you for using our service!