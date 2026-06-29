# 🎮 تمرین ۳: شاخه‌ها و merge

<div dir="rtl">

## 📌 هدف تمرین

در این تمرین یک شاخه جدید می‌سازی، روی آن تغییر انجام می‌دهی، آن را به `main` برمی‌گردانی و در پایان شاخه را حذف می‌کنی.

## ⏱ زمان پیشنهادی

۲۰ دقیقه

## مراحل تمرین

### ۱. پروژه تمرینی بساز

</div>

```bash
mkdir branch-practice
cd branch-practice
git init
echo "# سایت تمرینی" > README.md
git add README.md
git commit -m "ایجاد پروژه تمرینی"
```

<div dir="rtl">

### ۲. شاخه جدید بساز

</div>

```bash
git switch -c feature-about
```

<div dir="rtl">

### ۳. روی شاخه جدید تغییر بده

</div>

```bash
echo "این صفحه درباره پروژه است." > about.txt
git add about.txt
git commit -m "اضافه کردن صفحه درباره"
```

<div dir="rtl">

### ۴. شاخه‌ها را ببین

</div>

```bash
git branch
```

<div dir="rtl">

باید کنار `feature-about` علامت `*` ببینی.

### ۵. به main برگرد و merge کن

</div>

```bash
git switch main
git merge feature-about
```

<div dir="rtl">

### ۶. شاخه تمام‌شده را حذف کن

</div>

```bash
git branch -d feature-about
git branch
```

<div dir="rtl">

## چالش اضافه: یک تعارض کوچک بساز

این بخش اختیاری است، اما برای یادگیری conflict خیلی مفید است.

اول روی `main` یک فایل بساز:

</div>

```bash
echo "رنگ اصلی سایت: آبی" > theme.txt
git add theme.txt
git commit -m "اضافه کردن رنگ اصلی سایت"
```

<div dir="rtl">

یک شاخه جدید بساز و همان خط را تغییر بده:

</div>

```bash
git switch -c feature-theme
echo "رنگ اصلی سایت: سبز" > theme.txt
git add theme.txt
git commit -m "تغییر رنگ سایت به سبز"
```

<div dir="rtl">

برگرد به `main` و همان خط را جور دیگری تغییر بده:

</div>

```bash
git switch main
echo "رنگ اصلی سایت: قرمز" > theme.txt
git add theme.txt
git commit -m "تغییر رنگ سایت به قرمز"
```

<div dir="rtl">

حالا merge کن:

</div>

```bash
git merge feature-theme
```

<div dir="rtl">

گیت conflict نشان می‌دهد. فایل `theme.txt` را باز کن، یک رنگ را انتخاب کن، علامت‌های conflict را حذف کن و بعد:

</div>

```bash
git add theme.txt
git commit -m "حل تعارض رنگ سایت"
```

<div dir="rtl">

## نتیجه مورد انتظار

در پایان باید بتوانی با این دستور تاریخچه شاخه‌ها و merge را ببینی:

</div>

```bash
git log --graph --oneline --all
```
