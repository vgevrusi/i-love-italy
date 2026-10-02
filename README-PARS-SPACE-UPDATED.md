# Pars Space updated build

این نسخه شامل این اصلاحات است:

- داشبورد جدید Pars Space و صفحه Login هماهنگ شده‌اند.
- تصویر مقبره کوروش به‌صورت Pixel Art در Login استفاده می‌شود.
- Login نام کاربری و رمز عبور را واقعاً بررسی می‌کند.
- تغییر Username + Password از Settings فعال است.
- API namespace اختصاصی `/api/pars/v1/*` برای بخش‌های اصلی داشبورد اضافه شده است.
- ساخت User + Config لینک مستقیم خود کانفیگ را نشان می‌دهد، نه لینک Subscription.
- VLESS / VMess / Trojan لینک‌های share متناسب با پروتکل تولید می‌کنند.
- Reality تنظیمات SNI، Destination، Short ID، Fingerprint و External Domain/Port دارد.
- TLS تنظیمات ALPN، SNI، Fingerprint و Transport دارد.
- در انتخاب Protocol، فیلدهای غیرمرتبط مخفی می‌شوند.
- Pars Subscription واقعاً گروه می‌سازد و کاربران فعلی را به گروه اضافه می‌کند.
- endpoint عمومی `/sub-group/<uuid>` کانفیگ واقعی کاربران گروه را تولید می‌کند.

## نکته مهم درباره VPN

برنامه روی `0.0.0.0` گوش می‌دهد و از نظر کد برای دسترسی عمومی محدود به localhost نیست. اگر دامنه یا آدرس سرویس فقط با VPN باز می‌شود، مشکل در مسیر شبکه، DNS، ISP یا Provider است و با تغییر HTML حل نمی‌شود.

برای دسترسی بدون VPN باید یک Public URL قابل دسترس از شبکه کاربر داشته باشید، مثلاً یک دامنه اختصاصی که به سرویس Deploy شده اشاره کند یا یک VPS/Reverse Proxy که از شبکه کاربر قابل دسترسی باشد. اگر Default Domain سرویس Deploy شده توسط شبکه کاربر مسدود باشد، همان Domain باید با یک Public Domain مناسب جایگزین شود.

## Deploy

`main.py` و محتوای `static/` را با نسخه فعلی پروژه جایگزین کنید و سرویس را Restart/Deploy کنید.

قبل از جایگزینی از پروژه قبلی Backup بگیرید.
