# 🎮 تمرین ۰۲: دستورات پایه (add, commit, status, log)

**بر اساس فصل ۲ که قبلاً نوشتیم، حالا تمرین عملیش رو می‌سازیم:**

**📁 مسیر فایل:**

```bash
GitTale/exercises/02-basic-commands/README.md
```
# 🎮 تمرین ۲: دستورات پایه (add, commit, status, log)

<div dir="rtl">

## 📌 هدف تمرین
یادگیری عملی دستورات پایه گیت و کار با Staging Area

## ⏱ زمان پیشنهادی
۱۵ دقیقه

---

## 📝 **مراحل تمرین**

### **۱️⃣ یک پروژه جدید بساز**

</div>

```bash
# یه پوشه جدید برای تمرین بساز
cd ~/Desktop
mkdir my-git-practice
cd my-git-practice

# تبدیل به مخزن گیت
git init
```

<div dir="rtl">
**نصب nano**

یک برنامه ی ویرایش و ساخت متن

```bash
لینوکس:
bash
sudo apt install nano
مک:
bash
brew install nano
ویندوز (Git Bash):
bash
# معمولاً همراه Git نصب میشه
nano --version

```
</div>

```bash
cd any where

mkdir -p basic-commands

cd basic-commands

nano sample.txt
```


حالا توی nano این رو بنویس:


```c
یادگیری عملی دستورات پایه گیت
```

<div dir="rtl">

**۳️⃣ وضعیت رو ببین**
</div>

```bash

git status
```

<div dir="rtl">

**۴️⃣ فایل‌ها رو add کن**

</div>


```bash
git add index.html
git status
git add style.css
git status
```

<div dir="rtl">

**۵️⃣ کامیت کن**

</div>

```bash
git commit -m "اولین کامیت: فایل‌های اصلی"
```
<div dir="rtl">

**۶️⃣ تاریخچه رو ببین**


</div>


```bash
git log 
```
