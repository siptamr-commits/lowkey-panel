# ⚡ Lowkey Panel

پنل مدیریت پروکسی VLESS — سرورلس روی Cloudflare Workers

![Lowkey Panel](https://img.shields.io/badge/Lowkey-Panel-yellow?style=for-the-badge&logo=cloudflare&logoColor=white)
![Workers](https://img.shields.io/badge/Cloudflare-Workers-orange?style=for-the-badge&logo=cloudflare&logoColor=white)
![D1](https://img.shields.io/badge/D1-Database-blue?style=for-the-badge)

---

## ✨ ویژگی‌ها

- 🚀 **سرورلس** — نیازی به سرور جداگانه نداره
- 🤖 **ربات تلگرام** — مدیریت کاربران از تلگرام
- 📊 **پنل ادمین** — داشبورد وب مدیریتی
- 🔐 **VLESS Proxy** — پروکسی پرسرعت و امن
- 📱 **صفحه وضعیت** — مشاهده وضعیت اتصال با QR Code
- 🔄 **چرخش خودکار IP** — جایگزینی خودکار پروکسی‌ها
- ⏰ **ریست خودکار** — ریست حجم و درخواست‌ها
- 🎨 **رابط کاربری فارسی** — RTL و طراحی زیبا

## 🛠️ نصب

### پیش‌نیازها
- اکانت [Cloudflare](https://dash.cloudflare.com)
- [Wrangler CLI](https://developers.cloudflare.com/workers/wrangler/install-and-update/)

### مراحل نصب

```bash
# 1. کلون کردن پروژه
git clone https://github.com/siptamr-commits/lowkey-panel.git
cd lowkey-panel

# 2. نصب وابستگی‌ها
npm install

# 3. تنظیم متغیرهای محیطی
# wrangler.toml را ویرایش کنید

# 4. ایجاد پایگاه داده D1
wrangler d1 create lowkey-db

# 5. استقرار
wrangler deploy
```

## ⚙️ تنظیمات

### wrangler.toml

```toml
name = "lowkey-panel"
main = "worker.js"
compatibility_date = "2024-01-01"

[[d1_databases]]
binding = "DB"
database_name = "lowkey-db"
database_id = "YOUR_D1_DATABASE_ID"

[vars]
ADMIN_PASSWORD = "your-admin-password"
TELEGRAM_BOT_TOKEN = "your-telegram-bot-token"
TELEGRAM_ADMIN_IDS = "your-telegram-user-id"
TELEGRAM_CHANNEL = "@YourChannel"
```

### متغیرهای محیطی

| متغیر | توضیح |
|--------|--------|
| `ADMIN_PASSWORD` | رمز عبور پنل ادمین |
| `TELEGRAM_BOT_TOKEN` | توکن ربات تلگرام |
| `TELEGRAM_ADMIN_IDS` | شناسه کاربران ادمین (با کاما) |
| `TELEGRAM_CHANNEL` | آیدی کانال تلگرام (اختیاری) |

## 🤖 ربات تلگرام

ربات تلگرام امکانات زیر را فراهم می‌کند:

- ➕ ساخت کانفیگ جدید
- 📄 مشاهده کانفیگ‌های من
- ℹ️ درباره لوکی
- 🔧 پنل مدیریت (ادمین)
  - 📋 لیست کاربران
  - ➕ افزودن کاربر
  - 🔍 جستجوی کاربر

## 📱 اپلیکیشن‌های سازگار

| پلتفرم | اپلیکیشن |
|---------|----------|
| iOS/macOS | Streisand, V2Box, Shadowrocket |
| اندروید | v2rayNG, NekoBox, sing-box |
| ویندوز | Clash Verge, sing-box |

## 📂 ساختار پروژه

```
lowkey-panel/
├── worker.js          # فایل اصلی Worker
├── wrangler.toml      # تنظیمات Cloudflare
├── package.json       # اطلاعات پروژه
├── README.md          # راهنما (فارسی)
└── LICENSE            # مجوز
```

## 🔒 امنیت

- رمز عبور ادمین در متغیرهای محیطی ذخیره میشه
- اطلاعات کاربران در D1 database رمزنگاری شده ذخیره میشه
- اتصال‌ها از طریق TLS رمزنگاری میشن

## 📄 مجوز

MIT License — آزاد برای استفاده و تغییر

## 💬 پشتیبانی

- تلگرام: [@lowkey878](https://t.me/lowkey878)
- کانال: [@Lowkey_Configs878](https://t.me/Lowkey_Configs878)

---

⚡ ساخته شده با ❤️ توسط **Lowkey**
