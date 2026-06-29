# 🎮 تمرین ۵: stash، reset و rebase

<div dir="rtl">

## 📌 هدف تمرین

در این تمرین با چند ابزار پیشرفته‌تر گیت کار می‌کنی: تغییرات نیمه‌تمام را stash می‌کنی، آخرین کامیت را اصلاح می‌کنی، reset را می‌بینی و یک rebase ساده انجام می‌دهی.

## ⏱ زمان پیشنهادی

۳۰ دقیقه

## نکته مهم

این تمرین را داخل یک پروژه جدا انجام بده. بعضی دستورهای این فصل می‌توانند تغییرات را برگردانند یا حذف کنند، پس بهتر است روی پروژه واقعی اجرا نشوند.

## مراحل تمرین

### ۱. پروژه تمرینی بساز

</div>

```bash
mkdir advanced-git-practice
cd advanced-git-practice
git init
echo "نسخه اول" > app.txt
git add app.txt
git commit -m "ایجاد نسخه اول"
```

<div dir="rtl">

### ۲. stash را تمرین کن

یک تغییر نیمه‌تمام بساز:

</div>

```bash
echo "کار نیمه‌تمام" >> app.txt
git status
```

<div dir="rtl">

حالا تغییر را موقتاً کنار بگذار:

</div>

```bash
git stash push -m "تغییر نیمه‌تمام app"
git status
git stash list
```

<div dir="rtl">

تغییر را برگردان:

</div>

```bash
git stash pop
git status
```

<div dir="rtl">

حالا آن را commit کن:

</div>

```bash
git add app.txt
git commit -m "اضافه کردن کار نیمه‌تمام"
```

<div dir="rtl">

### ۳. restore را تمرین کن

یک تغییر بساز که نمی‌خواهی نگه داری:

</div>

```bash
echo "این خط را نمی‌خواهم" >> app.txt
git status
git restore app.txt
git status
```

<div dir="rtl">

### ۴. reset نرم را تمرین کن

یک کامیت بساز:

</div>

```bash
echo "خط مخصوص reset" >> app.txt
git add app.txt
git commit -m "کامیت برای تمرین reset"
git log --oneline
```

<div dir="rtl">

حالا آخرین کامیت را با حالت soft برگردان:

</div>

```bash
git reset --soft HEAD~1
git status
```

<div dir="rtl">

می‌بینی تغییرات هنوز آماده کامیت هستند. دوباره کامیت کن:

</div>

```bash
git commit -m "کامیت اصلاح‌شده بعد از reset soft"
```

<div dir="rtl">

### ۵. rebase ساده را تمرین کن

یک شاخه جدید بساز:

</div>

```bash
git switch -c feature-message
echo "پیام شاخه feature" > message.txt
git add message.txt
git commit -m "اضافه کردن پیام feature"
```

<div dir="rtl">

به `main` برگرد و آن را جلو ببر:

</div>

```bash
git switch main
echo "تغییر جدید در main" >> app.txt
git add app.txt
git commit -m "به‌روزرسانی main"
```

<div dir="rtl">

حالا شاخه feature را روی آخرین نسخه main دوباره بچین:

</div>

```bash
git switch feature-message
git rebase main
git log --graph --oneline --all
```

<div dir="rtl">

### ۶. شاخه را merge کن

</div>

```bash
git switch main
git merge feature-message
git branch -d feature-message
```

<div dir="rtl">

## چالش اضافه

با `git commit --amend` پیام آخرین کامیت را اصلاح کن:

</div>

```bash
git commit --amend -m "پیام نهایی تمرین پیشرفته"
git log --oneline
```

<div dir="rtl">

## نتیجه مورد انتظار

در پایان باید بتوانی توضیح بدهی:

- `stash` چه زمانی استفاده می‌شود
- `restore` چه چیزی را برمی‌گرداند
- `reset --soft` چه فرقی با `reset --hard` دارد
- `rebase` چرا تاریخچه را مرتب‌تر می‌کند

</div>
