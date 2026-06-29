# 🎮 تمرین ۴: اتصال پروژه به GitHub

<div dir="rtl">

## 📌 هدف تمرین

در این تمرین یک پروژه محلی را به GitHub وصل می‌کنی، تغییرات را push می‌کنی، و با `pull` و `clone` آشنا می‌شوی.

## ⏱ زمان پیشنهادی

۲۵ دقیقه

## پیش‌نیاز

- حساب GitHub داشته باشی
- Git روی سیستم نصب باشد
- فصل ۴ را خوانده باشی

## مراحل تمرین

### ۱. یک پروژه محلی بساز

</div>

```bash
mkdir github-practice
cd github-practice
git init
echo "# تمرین GitHub" > README.md
git add README.md
git commit -m "ایجاد پروژه تمرینی GitHub"
```

<div dir="rtl">

### ۲. در GitHub مخزن جدید بساز

در GitHub یک repository جدید بساز. اسم پیشنهادی:

</div>

```text
github-practice
```

<div dir="rtl">

اگر پروژه را قبلاً روی سیستم ساخته‌ای، هنگام ساخت مخزن در GitHub گزینه‌های README، gitignore و license را فعال نکن.

### ۳. remote را اضافه کن

آدرس مخزن خودت را جای `URL` بگذار:

</div>

```bash
git remote add origin URL
git remote -v
```

<div dir="rtl">

نمونه:

</div>

```bash
git remote add origin https://github.com/username/github-practice.git
```

<div dir="rtl">

### ۴. اولین push را انجام بده

</div>

```bash
git push -u origin main
```

<div dir="rtl">

حالا صفحه repository را در GitHub refresh کن. باید فایل `README.md` را ببینی.

### ۵. یک تغییر جدید push کن

</div>

```bash
echo "این خط از سیستم من اضافه شد." >> README.md
git add README.md
git commit -m "به‌روزرسانی README"
git push
```

<div dir="rtl">

### ۶. pull را تمرین کن

در سایت GitHub فایل `README.md` را ویرایش کن و یک خط جدید اضافه کن. بعد روی سیستم خودت اجرا کن:

</div>

```bash
git pull
```

<div dir="rtl">

حالا فایل را باز کن و ببین تغییر GitHub وارد پروژه محلی شده است.

### ۷. clone را تمرین کن

از پوشه پروژه بیرون برو و یک نسخه تازه clone کن:

</div>

```bash
cd ..
git clone URL github-practice-copy
cd github-practice-copy
git log --oneline
```

<div dir="rtl">

## چالش اضافه

یک شاخه جدید بساز، تغییر بده، push کن و در GitHub Pull Request بساز:

</div>

```bash
git switch -c update-title
echo "عنوان جدید تمرین" >> README.md
git add README.md
git commit -m "اضافه کردن عنوان جدید"
git push -u origin update-title
```

<div dir="rtl">

بعد از push، GitHub معمولاً پیشنهاد ساخت Pull Request را نشان می‌دهد.

## نتیجه مورد انتظار

در پایان باید بتوانی پروژه‌ات را در GitHub ببینی، تغییرات محلی را push کنی، تغییرات آنلاین را pull کنی و یک نسخه تازه clone بگیری.

</div>
