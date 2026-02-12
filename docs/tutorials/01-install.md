# 📥 فصل ۱: نصب و راه‌اندازی

<div dir="rtl">

**🎯 تو این فصل چی یاد می‌گیرم؟**

- نصب گیت روی ویندوز، مک و لینوکس

- تنظیمات اولیه و معرفی خودم به گیت

- ✅ مهمترین بخش: درک مفهوم مخزن (Repository) و دستور git init

- ساختن اولین مخزن گیت
 

## نصب گیت

</div>

**ویندوز:**

```bash
https://git-scm.com/download/win
```
<div dir="rtl">

✅ بعد از دانلود، فایل رو اجرا کن و همه مراحل رو Next بزن! 

</div>


**مک:**
```bash
brew install git
یا
https://git-scm.com/install/mac
```
<div dir="rtl"> 
✅ اگه Homebrew نداری، از سایت رسمی دانلود کن 
</div>



**🐧 لینوکس (اوبونتو/دبیان):**
```bash
sudo apt install git
یا
https://git-scm.com/install/linux

```
<div dir="rtl">
✅ برای توزیع‌های دیگه مثل Fedora: `sudo dnf install git`
</div>

**تنظیمات اولیه**
<div dir="rtl">
بعد از نصب، باید خودت رو به گیت معرفی کنی. این کار فقط یه بار انجام میشه: 
</div>

```bash
git config --global user.name "اسم تو"
git config --global user.email "ایمیلت"
```

<div dir="rtl">
💡 نکته طلایی: از همون ایمیل گیت‌هابت استفاده کن تا کامیت‌هات به حساب کاربری‌ت متصل بشن!

</div>

**🏁 اولین دستور - تست نصب**

```bash
git --version
```
<div dir="rtl">

✅ اگه چیزی مثل git version 2.40.0 دیدی، یعنی نصب موفق بوده! 🎉


# **🎬 قسمت اصلی: آشنایی با مخزن (Repository) و git init**

**📦 مخزن (Repository) چیه؟**

به زبان ساده: مخزن یا همون Repository، یه پوشه‌ست که گیت داره تمام تاریخچه تغییراتش رو زیر نظر می‌گیره.


</div>

<div dir="rtl">

**🎯 git init دقیقاً چیکار می‌کنه؟**

دستور git init یه پوشه معمولی رو تبدیل می‌کنه به مخزن گیت.

وقتی این دستور رو اجرا می‌کنی:

1. یه پوشه مخفی به اسم .git توی پروژه‌ات ساخته میشه

2. این پوشه .git مثل جعبه سیاه هواپیما می‌مونه!

3. همه تاریخچه، همه شاخه‌ها، همه نسخه‌ها اونجا ذخیره میشن

4. اگه این پوشه رو پاک کنی، تمام تاریخچه پروژه از بین میره!
 

</div>


```bash
# ساختن یه پوشه جدید
mkdir my-awesome-project
cd my-awesome-project

# تبدیل به مخزن گیت
git init
# Initialized empty Git repository in /my-awesome-project/.git/

# حالا ببین چه خبره!
ls -la
# total 0
# drwxr-xr-x   3 user  staff   96 Jan 15 10:30 .
# drwxr-xr-x   4 user  staff  128 Jan 15 10:30 ..
# drwxr-xr-x  10 user  staff  320 Jan 15 10:30 .git   ← اینو ببین!
```

<div dir="rtl">

**📖 داستان واقعی: چرا git init مهمه؟**

فرض کن داری یه رمان می‌نویسی.

**بدون گیت:**
```bash
هر بار یه نسخه جدید ذخیره می‌کنی

رمان_نهایی.docx

رمان_نهایی_۲.docx

رمان_نهایی_۳_آخر.docx

رمان_نهایی_۳_آخر_نه_این_یکی.docx 😫
```

**با گیت و git init:**


```bash
یه بار git init می‌زنی

گیت میاد و یه دستیار هوشمند کنارت می‌ذاره

هر بار که نوشتی، می‌گی git commit

دستیار تاریخچه رو نگه می‌داره

هر وقت خواستی بری به نسخه قبلی، می‌گی git checkout
```


</div>

**🚨 مشکلات رایج و راه‌حل‌ها**

<div dir="rtl">
> [!CAUTION]
> ❌ مشکل ۱: پیغام "git is not recognized"
> 
> ❌ مشکل ۲: git init رو اشتباهی زدم!
> 
> ❌ مشکل ۳: ایمیل رو اشتباه زدم
> 

