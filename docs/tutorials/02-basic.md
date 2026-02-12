# 📗 فصل ۲: دستورات پایه (add, commit, status, log)

<div style="text-align: right; direction: rtl;">

**🎯 چرا این تمرین اول اومد؟**

اگه یادت باشه تو فصل ۱ فقط گیت رو نصب کردیم و تنظیمات اولیه رو انجام دادیم.
حالا وقتشه ببینیم گیت واقعاً چیکار می‌کنه!

**🎬 داستان درس**

فرض کن داری یه کتاب می‌نویسی.

**📝 صحنه ۱ - قبل از گیت:**

```dax

**۲۰ تا نسخه مختلف از کتابت داری!

کتاب_نهایی.docx

کتاب_نهایی_آخر.docx

کتاب_نهایی_آخر_نه_این_یکی.docx**
```


🤯 گیج شدی؟

**🎬 صحنه ۲ - بعد از گیت:**

```dax
**هر بار که یه بخش رو تموم می‌کنی، یه مهر می‌زنی روش

همیشه می‌دونی کی چی نوشته

می‌تونی به هر نسخه قبلی برگردی**
```


**📦 مفهوم Staging Area (انبار موقت)**
گیت سه تا جا داره:

</div>

```html
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│    Working      │────▶│    Staging      │────▶│   Repository    │
│   Directory     │ add │      Area       │commit│   (History)     │
└─────────────────┘     └─────────────────┘     └─────────────────┘
        │                                                  │
        └──────────────────────────────────────────────────┘
                         git status                       git log
```


<div style="text-align: right; direction: rtl;">

**📌 به زبان ساده:**

- Working Directory: میز کارت - فایل‌ها رو اینجا ویرایش می‌کنی

- Staging Area: سبد خرید - فایل‌هایی که آماده کامیت شدن

- Repository: انبار - تاریخچه همه کامیت‌ها

**🛠️ دستور git add**

</div>

```bash
# یه فایل خاص رو اضافه کن
git add index.html

# همه فایل‌ها رو اضافه کن
git add .

# یه پوشه رو اضافه کن
/git add src
```

<div style="text-align: right; direction: rtl;">

**🎮 مثال عملی:**


</div>

<div dir="ltr">

```bash
# یه فایل جدید بساز
echo "<h1>Hello world</h1>" > index.html

# ببین گیت چی می‌گه
git status
# می‌گه: "index.html قرمزه!" یعنی اضافه نشده

# اضافه‌اش کن به سبد خرید
git add index.html

# دوباره وضعیت رو ببین
git status
# می‌گه: "index.html سبزه!" یعنی آماده کامیت
```

</div>
<div style="text-align: right; direction: rtl;">

**💾 دستور git commit**

</div>

```bash
git commit -m "پیام کامیت"
```

<div style="text-align: right; direction: rtl;">

📝 پیام کامیت خوب:

```bash
❌ update
❌ change
✅ اضافه کردن progress bar به صفحه اصلی
✅ رفع باگ 404 در صفحه محصول
```

🎮 مثال عملی:

</div>

```bash

git commit -m "ایجاد صفحه اصلی وبسایت"

# خروجی:
# [main (root-commit) a1b2c3d] ایجاد صفحه اصلی وبسایت
# 1 file changed, 1 insertion(+)
```

<div style="text-align: right; direction: rtl;">

**👀 دستور git status**
دستوری که همیشه باید بزنی!

</div>

```bash
git status
```

<div style="text-align: right; direction: rtl;">

چیزایی که نشون میده:

```bash
🟢 فایل‌های سبز = آماده کامیت
🔴 فایل‌های قرمز = ویرایش شدن ولی اضافه نشدن
⚪ فایل‌های سفید = track نشدن (جدید هستن)
```


**📜 دستور git log**
تاریخچه کامل پروژه!

</div>

```bash
# تاریخچه کامل
git log

# یه نسخه خلاصه
git log --oneline

# با گراف قشنگ
git log --graph --oneline
```

<div style="text-align: right; direction: rtl;">

خروجی:

</div>


```c
a1b2c3d ایجاد صفحه اصلی وبسایت
f4e5d6a اضافه کردن استایل به navbar
g7h8i9j رفع باگ در فرم تماس
```
