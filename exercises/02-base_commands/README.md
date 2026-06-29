# 🎮 تمرین ۲: دستورات پایه (add, commit, status, log)

<div dir="rtl">

## 📌 هدف تمرین

در این تمرین یاد می‌گیری چطور فایل بسازی، وضعیت پروژه را ببینی، فایل‌ها را وارد Staging Area کنی، کامیت بسازی و تاریخچه را بررسی کنی.

## ⏱ زمان پیشنهادی

۱۵ دقیقه

## پیش‌نیاز

فصل ۱ و فصل ۲ را خوانده باشی و گیت روی سیستم نصب باشد.

## مراحل تمرین

### ۱. یک پروژه جدید بساز

</div>

```bash
mkdir basic-commands-practice
cd basic-commands-practice
git init
```

<div dir="rtl">

### ۲. وضعیت اولیه را ببین

</div>

```bash
git status
```

<div dir="rtl">

### ۳. دو فایل ساده بساز

</div>

```bash
echo "# پروژه تمرینی من" > README.md
echo "body { font-family: sans-serif; }" > style.css
```

<div dir="rtl">

### ۴. دوباره وضعیت را بررسی کن

</div>

```bash
git status
```

<div dir="rtl">

باید ببینی فایل‌ها هنوز track نشده‌اند.

### ۵. فقط یک فایل را add کن

</div>

```bash
git add README.md
git status
```

<div dir="rtl">

حالا `README.md` آماده کامیت است، اما `style.css` هنوز آماده نیست.

### ۶. فایل دوم را هم add کن

</div>

```bash
git add style.css
git status
```

<div dir="rtl">

### ۷. اولین کامیت را بساز

</div>

```bash
git commit -m "ایجاد فایل‌های اولیه پروژه"
```

<div dir="rtl">

### ۸. تاریخچه را ببین

</div>

```bash
git log --oneline
```

<div dir="rtl">

## چالش اضافه

یک فایل جدید به نام `notes.txt` بساز، داخلش یک جمله بنویس، سپس آن را add و commit کن.

</div>

```bash
echo "امروز دستورات پایه گیت را تمرین کردم." > notes.txt
git add notes.txt
git commit -m "اضافه کردن یادداشت تمرین"
git log --oneline
```

<div dir="rtl">

## نتیجه مورد انتظار

در پایان باید حداقل دو commit در خروجی `git log --oneline` ببینی.

</div>
