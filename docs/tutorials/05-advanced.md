# 📙 فصل ۵: دستورات پیشرفته‌تر گیت

<div dir="rtl">

**🎯 تو این فصل چی یاد می‌گیریم؟**

- کنار گذاشتن موقت تغییرات با `stash`
- برگشت دادن فایل‌ها و کامیت‌ها با `restore` و `reset`
- تفاوت reset نرم، mixed و hard
- مرتب کردن تاریخچه با `rebase`
- چند قانون امن برای کار با دستورهای حساس

## قبل از شروع

دستورهای این فصل قدرتمند هستند. یعنی هم خیلی کمک می‌کنند، هم اگر بی‌دقت استفاده شوند می‌توانند تغییراتت را سخت‌تر قابل بازیابی کنند.

قانون ساده:

- قبل از دستورهای خطرناک، `git status` بزن
- اگر مطمئن نیستی، اول یک شاخه پشتیبان بساز
- روی کامیت‌هایی که قبلاً push شده‌اند با احتیاط rebase یا reset انجام بده

</div>

```bash
git status
git switch -c backup-before-reset
```

<div dir="rtl">

## stash یعنی چی؟

گاهی وسط کار هستی، چند فایل را تغییر داده‌ای، اما هنوز آماده commit نیستند. ناگهان باید سریع به شاخه دیگری بروی. اینجا `stash` به درد می‌خورد.

`stash` تغییرات فعلی را موقتاً کنار می‌گذارد و working directory را تمیز می‌کند.

</div>

```bash
git stash
```

<div dir="rtl">

برای دیدن stashها:

</div>

```bash
git stash list
```

<div dir="rtl">

برای برگرداندن آخرین stash:

</div>

```bash
git stash pop
```

<div dir="rtl">

اگر می‌خواهی stash برگردد اما از لیست stashها حذف نشود:

</div>

```bash
git stash apply
```

<div dir="rtl">

برای گذاشتن پیام روی stash:

</div>

```bash
git stash push -m "کار نیمه‌تمام روی فرم ثبت‌نام"
```

<div dir="rtl">

## restore: برگرداندن فایل

اگر یک فایل را تغییر داده‌ای و می‌خواهی تغییراتش را دور بریزی:

</div>

```bash
git restore index.html
```

<div dir="rtl">

اگر فایلی را add کرده‌ای و می‌خواهی فقط از staging area خارج شود:

</div>

```bash
git restore --staged index.html
```

<div dir="rtl">

این دستور فایل را پاک نمی‌کند؛ فقط آن را از لیست آماده کامیت بیرون می‌آورد.

## reset: برگشت دادن کامیت‌ها

`reset` شاخه فعلی را به یک نقطه قبلی می‌برد. سه حالت مهم دارد:

### reset --soft

کامیت را برمی‌گرداند، ولی تغییرات را در staging area نگه می‌دارد.

</div>

```bash
git reset --soft HEAD~1
```

<div dir="rtl">

کاربرد: پیام کامیت را بد نوشتی یا می‌خواهی آخرین کامیت را دوباره بسازی.

### reset --mixed

حالت پیش‌فرض reset است. کامیت را برمی‌گرداند و تغییرات را از staging خارج می‌کند، اما فایل‌ها را نگه می‌دارد.

</div>

```bash
git reset HEAD~1
```

<div dir="rtl">

### reset --hard

کامیت را برمی‌گرداند و تغییرات فایل‌ها را هم دور می‌ریزد.

</div>

```bash
git reset --hard HEAD~1
```

<div dir="rtl">

⚠️ این دستور حساس است. اگر تغییرات مهم داری و کامیت نشده‌اند، ممکن است از دست بروند.

## rebase یعنی چی؟

`rebase` تاریخچه شاخه تو را روی آخرین نسخه یک شاخه دیگر دوباره می‌چیند. معمولاً برای تمیز نگه داشتن تاریخچه استفاده می‌شود.

فرض کن روی شاخه `feature-login` کار می‌کنی و در همین مدت شاخه `main` جلو رفته است. برای آوردن تغییرات جدید main روی شاخه خودت:

</div>

```bash
git switch feature-login
git rebase main
```

<div dir="rtl">

اگر تعارض پیش آمد:

1. فایل‌های دارای conflict را اصلاح کن
2. فایل‌ها را add کن
3. rebase را ادامه بده

</div>

```bash
git add .
git rebase --continue
```

<div dir="rtl">

اگر پشیمان شدی:

</div>

```bash
git rebase --abort
```

<div dir="rtl">

## merge یا rebase؟

- `merge`: ساده‌تر و امن‌تر برای شروع
- `rebase`: تاریخچه تمیزتر، اما نیازمند دقت بیشتر

برای پروژه‌های تیمی، قبل از rebase کردن شاخه‌هایی که push شده‌اند، با تیم هماهنگ کن.

## amend: اصلاح آخرین commit

اگر فقط می‌خواهی آخرین کامیت را اصلاح کنی، لازم نیست reset کنی:

</div>

```bash
git add .
git commit --amend -m "پیام اصلاح‌شده کامیت"
```

<div dir="rtl">

برای تغییرات کوچک مثل اصلاح پیام یا اضافه کردن یک فایل فراموش‌شده، `amend` خیلی کاربردی است.

## دستورهای مهم این فصل

</div>

```bash
git stash
git stash list
git stash pop
git restore file.txt
git restore --staged file.txt
git reset --soft HEAD~1
git reset HEAD~1
git reset --hard HEAD~1
git rebase main
git rebase --continue
git rebase --abort
git commit --amend
```

<div dir="rtl">

## جمع‌بندی

این فصل جعبه ابزار نجات و مرتب‌سازی گیت است. `stash` برای نگه داشتن موقت کارهای نیمه‌تمام، `restore` و `reset` برای برگشت دادن تغییرات، و `rebase` برای تمیز کردن تاریخچه استفاده می‌شوند.

</div>
