# 📕 فصل ۴: کار با گیت‌هاب و Remote Repository

<div dir="rtl">

**🎯 تو این فصل چی یاد می‌گیریم؟**

- تفاوت Git و GitHub
- ساخت مخزن روی GitHub
- اتصال مخزن محلی به مخزن remote
- فرستادن تغییرات با `push`
- گرفتن تغییرات با `pull`
- کپی گرفتن از پروژه با `clone`
- آشنایی با Fork و Pull Request

## Git با GitHub چه فرقی دارد؟

`Git` ابزاری است که روی سیستم تو نصب می‌شود و تاریخچه پروژه را مدیریت می‌کند.

`GitHub` یک سایت است که مخزن‌های گیت را آنلاین نگه می‌دارد تا بتوانی از چند سیستم کار کنی، با دیگران همکاری کنی، و پروژه‌ات را منتشر کنی.

به زبان ساده:

- Git: موتور کنترل نسخه
- GitHub: خانه آنلاین پروژه‌های Git

## Remote Repository چیست؟

مخزن محلی همان پوشه پروژه روی سیستم توست. مخزن remote نسخه آنلاین همان پروژه است.

وقتی روی سیستم خودت کامیت می‌کنی، تغییرات فقط محلی هستند. برای فرستادن آن‌ها به GitHub باید از `push` استفاده کنی.

## ساخت مخزن در GitHub

1. وارد حساب GitHub شو
2. روی دکمه `New repository` بزن
3. یک نام برای پروژه انتخاب کن
4. اگر پروژه را قبلاً روی سیستم ساخته‌ای، گزینه README را در GitHub فعال نکن
5. روی `Create repository` بزن

بعد از ساخت مخزن، GitHub یک آدرس به تو می‌دهد. نمونه:

</div>

```bash
https://github.com/username/my-project.git
```

<div dir="rtl">

## اتصال پروژه محلی به GitHub

اگر پروژه را از قبل روی سیستم داری، وارد پوشه پروژه شو و remote را اضافه کن:

</div>

```bash
git remote add origin https://github.com/username/my-project.git
```

<div dir="rtl">

برای بررسی remoteها:

</div>

```bash
git remote -v
```

<div dir="rtl">

خروجی شبیه این است:

</div>

```bash
origin  https://github.com/username/my-project.git (fetch)
origin  https://github.com/username/my-project.git (push)
```

<div dir="rtl">

## اولین push

قبل از push باید حداقل یک commit داشته باشی:

</div>

```bash
git add .
git commit -m "اولین کامیت پروژه"
```

<div dir="rtl">

حالا تغییرات را به GitHub بفرست:

</div>

```bash
git push -u origin main
```

<div dir="rtl">

گزینه `-u` ارتباط شاخه محلی `main` را با شاخه `main` روی GitHub ذخیره می‌کند. از دفعه‌های بعد معمولاً همین کافی است:

</div>

```bash
git push
```

<div dir="rtl">

## گرفتن تغییرات با pull

اگر روی GitHub یا یک سیستم دیگر تغییری ایجاد شده باشد، با این دستور آن را می‌گیری:

</div>

```bash
git pull
```

<div dir="rtl">

پیشنهاد خوب: قبل از شروع کار روزانه، `git pull` بزن تا با آخرین نسخه پروژه کار کنی.

## Clone کردن پروژه

اگر پروژه روی GitHub هست و می‌خواهی یک نسخه کامل از آن روی سیستم داشته باشی:

</div>

```bash
git clone https://github.com/username/my-project.git
cd my-project
```

<div dir="rtl">

وقتی پروژه را clone می‌کنی، remote به صورت خودکار با نام `origin` تنظیم می‌شود.

## Fork چیست؟

Fork یعنی یک کپی از پروژه شخص دیگری را داخل حساب GitHub خودت بسازی. این کار برای مشارکت در پروژه‌های متن‌باز خیلی رایج است.

روند کلی:

1. پروژه اصلی را Fork می‌کنی
2. Fork خودت را clone می‌کنی
3. تغییرات را روی یک شاخه جدید انجام می‌دهی
4. تغییرات را push می‌کنی
5. Pull Request می‌فرستی

## Pull Request چیست؟

Pull Request یعنی به صاحب پروژه می‌گویی: «من این تغییرات را آماده کرده‌ام، لطفاً بررسی کن و اگر خوب بود وارد پروژه اصلی کن.»

یک Pull Request خوب معمولاً این ویژگی‌ها را دارد:

- فقط یک موضوع مشخص را حل می‌کند
- توضیح کوتاه و روشن دارد
- اگر لازم است، عکس یا نمونه خروجی دارد
- با شاخه `main` پروژه اصلی به‌روز است

## مشکلات رایج

### خطای Authentication

اگر GitHub رمز عبور معمولی را قبول نکرد، باید از Personal Access Token یا روش SSH استفاده کنی. برای شروع، HTTPS ساده‌تر است؛ برای کار حرفه‌ای، SSH راحت‌تر می‌شود.

### خطای non-fast-forward

یعنی روی GitHub تغییراتی هست که تو هنوز نداری. اول pull بزن:

</div>

```bash
git pull
git push
```

<div dir="rtl">

اگر تعارض پیش آمد، مثل فصل شاخه‌ها آن را حل کن.

## دستورهای مهم این فصل

</div>

```bash
git remote add origin URL
git remote -v
git push -u origin main
git push
git pull
git clone URL
```

<div dir="rtl">

## جمع‌بندی

با GitHub پروژه تو فقط روی یک سیستم زندانی نمی‌ماند. می‌توانی کدت را آنلاین نگه داری، از هر جایی ادامه بدهی، و با دیگران همکاری کنی.

</div>
