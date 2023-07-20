# جلسه اول

## معرفی PHP و نحوه کارکرد آن


**PHP** (مخفف Hypertext Preprocessor) یک زبان برنامه‌نویسی سمت سرور است که ابتدا در سال ۱۹۹۴ توسط راسموس لِردورف [Rasmus Lerdorf](https://de.wikipedia.org/wiki/Rasmus_Lerdorf) ایجاد شد. PHP ابتدا برای ایجاد صفحات وب پویا بکار گرفته می‌شد، اما به تدریج به یک زبان برنامه‌نویسی کامل و پرکاربرد تبدیل شد.

یکی از ویژگی‌های مهم PHP این است که اجرای کدهای آن بر روی سرور صورت می‌گیرد و نتیجه برای کاربر در قالب یک صفحه HTML ارسال می‌شود. به این ترتیب، PHP می‌تواند اطلاعاتی را از پایگاه داده دریافت کرده، آن‌ها را پردازش کرده و نتیجه را به صورت پویا به کاربر نمایش دهد.

PHP یک زبان برنامه‌نویسی قابل تفسیر است، یعنی کدهای PHP به زبان ماشین تبدیل نمی‌شوند و برنامه نوشته شده بر روی سرور در هر درخواست از مرورگر اجرا می‌شود. این ویژگی باعث می‌شود PHP بسیار قابل انعطاف و قدرتمند در برنامه‌نویسی وب باشد.

نحوه کارکرد PHP به این صورت است که کدهای PHP درون برچسب‌های `<?php` و `?>` قرار می‌گیرند و سپس توسط موتور PHP بر روی سرور پردازش می‌شوند. در طول پردازش، PHP قادر است با استفاده از توابع و دستورات خاص خود، اطلاعات را از فرم‌ها، پارامترها و پایگاه داده دریافت کرده، آن‌ها را پردازش کند و نتیجه را به صفحه HTML تولید کند.

به عنوان یک زبان برنامه‌نویسی، PHP قابلیت‌های زیادی را در اختیار برنامه‌نویسان قرار می‌دهد، از جمله مدیریت فایل، ارسال ایمیل، تولید PDF، کار با پایگاه داده‌ها، ایجاد سیستم‌های مدیریت محتوا و بسیاری از وظایف دیگر.

همچنین، PHP یک زبان متن باز است و به رایگان در دسترس است، بنابراین افراد بسیاری از آن استفاده می‌کنند و جامعه فعالی از برنامه‌نویسان PHP وجود دارد که ابزارها، کتابخانه‌ها و راهنماهای مفیدی را برای توسعه دهندگان فراهم می‌کنند.



## نصب و پیکربندی PHP با استفاده از XAMPP

 (XAMPP) یک بسته نرم‌افزاری رایگان است که شامل نرم‌افزارهای Apache، MySQL/MariaDB و PHP است و برای توسعه و تست برنامه‌های وب به کار می‌رود. این بسته برای سه سیستم‌عامل Windows، macOS و Linux در دسترس است. نصب و پیکربندی PHP با استفاده از XAMPP به صورت زیر انجام می‌شود:
 
### برای سیستم‌عامل Windows:

1. دانلود XAMPP: به وب‌سایت Apache Friends (apachefriends.org) بروید و نسخه XAMPP مناسب برای سیستم‌عامل Windows را دانلود کنید.
2. نصب XAMPP: پس از دانلود، برنامه نصب XAMPP را اجرا کنید و به دستورالعمل‌های نصب پیروی کنید.
3. راه‌اندازی XAMPP: پس از نصب، برنامه XAMPP Control Panel را اجرا کنید. از طریق این پنل، سرویس‌های Apache و MySQL را راه‌اندازی کنید.
4. پیکربندی PHP: فایل php.ini را در پوشه نصب XAMPP (معمولاً C:\xampp) پیدا کنید و باز کنید. در این فایل، می‌توانید تنظیمات مورد نیاز PHP را اعمال کنید.
5. تست PHP: برای تست نصب و پیکربندی صحیح PHP، می‌توانید یک فایل PHP ساده با پسوند .php ایجاد کنید و کد زیر را در آن قرار دهید:

`<?php phpinfo(); ?>`

سپس فایل را در پوشه `htdocs` که در پوشه نصب XAMPP قرار دارد، ذخیره کنید. در مرورگر خود `http://localhost/نام_فایل.php` را وارد کنید و باید اطلاعات مربوط به PHP و پیکربندی‌های آن را مشاهده کنید.

### برای سیستم‌عامل macOS:

1. دانلود XAMPP: به وب‌سایت Apache Friends (apachefriends.org) بروید و نسخه XAMPP مناسب برای سیستم‌عامل macOS را دانلود کنید.
2. نصب XAMPP: پس از دانلود، بسته نرم‌افزاری XAMPP را دو بار کلیک کنید و به دستورالعمل‌های نصب پیروی کنید.
3. راه‌اندازی XAMPP: پس از نصب، XAMPP Control Panel را اجرا کنید. از طریق این پنل، سرویس‌های Apache و MySQL را راه‌اندازی کنید.
4. پیکربندی PHP: فایل php.ini را در پوشه نصب XAMPP (معمولاً /Applications/XAMPP) پیدا کنید و باز کنید. در این فایل، می‌توانید تنظیمات مورد نیاز PHP را اعمال کنید.
5. تست PHP: برای تست نصب و پیکربندی صحیح PHP، می‌توانید یک فایل PHP ساده با پسوند .php ایجاد کنید و کد زیر را در آن قرار دهید:

`<?php phpinfo(); ?>`

سپس فایل را در پوشه `/Applications/XAMPP/htdocs` ذخیره کنید. در مرورگر خود `http://localhost/نام_فایل.php` را وارد کنید و باید اطلاعات مربوط به PHP و پیکربندی‌های آن را مشاهده کنید.

### برای سیستم‌عامل Linux:

1. دانلود XAMPP: به وب‌سایت Apache Friends (apachefriends.org) بروید و نسخه XAMPP مناسب برای سیستم‌عامل Linux را دانلود کنید.
2. نصب XAMPP: پس از دانلود، فایل نصب XAMPP را از حالت فشرده خارج کنید و به دستورالعمل‌های نصب پیروی کنید.
3. راه‌اندازی XAMPP: پس از نصب، ترمینال را باز کنید و دستور زیر را اجرا کنید تا به پوشه نصب XAMPP بروید:

`cd /opt/lampp`

سپس دستور زیر را برای راه‌اندازی سرویس‌های Apache و MySQL وارد کنید:

`sudo ./xampp start`

4. پیکربندی PHP: فایل php.ini را در پوشه نصب XAMPP (معمولاً /opt/lampp) پیدا کنید و باز کنید. در این فایل، می‌توانید تنظیمات مورد نیاز PHP را اعمال کنید.
5. تست PHP: برای تست نصب و پیکربندی صحیح PHP، می‌توانید یک فایل PHP ساده با پسوند .php ایجاد کنید و کد زیر را در آن قرار دهید:

`<?php phpinfo(); ?>`

سپس فایل را در پوشه `/opt/lampp/htdocs` ذخیره کنید. در مرورگر خود `http://localhost/نام_فایل.php` را وارد کنید و باید اطلاعات مربوط به PHP و پیکربندی‌های آن را مشاهده کنید.

با نصب و پیکربندی XAMPP، شما می‌توانید PHP را روی سرور خود اجرا کنید و برنامه‌های PHP خود را توسعه دهید و تست کنید.



## ساختار یک برنامه PHP ساده

ساختار یک برنامه PHP ساده شامل چند قسمت اصلی است که در ادامه به طور خلاصه توضیح داده می‌شود:

1. تعریف تگ PHP: یک برنامه PHP با تعریف تگ PHP آغاز می‌شود. شما باید تمام کد PHP خود را بین تگ‌های `<?php` و `?>` قرار دهید. به عنوان مثال:

`<?php // کدهای PHP در اینجا قرار می‌گیرند ?>`

2. متغیرها و نمایش داده‌ها: در برنامه PHP، شما می‌توانید متغیرها را تعریف کرده و از آن‌ها برای ذخیره و نمایش داده‌ها استفاده کنید. به عنوان مثال:

`<?php $name = "John"; echo "Hello, " . $name . "!"; ?>`

در این مثال، متغیر `$name` تعریف شده و مقدار "John" به آن اختصاص داده شده است. سپس با استفاده از تابع `echo`، مقدار متغیر `$name` نمایش داده می‌شود.

3. ساختار شرطی: شما می‌توانید بر اساس شرایط مختلف، بخشی از کد را اجرا یا رد کنید. این به شما امکان می‌دهد تصمیم بگیرید که کد چه عملیاتی را انجام دهد. به عنوان مثال:

`<?php $age = 20; if ($age >= 18) {     echo "شما مجاز به ورود هستید."; } else {     echo "شما مجاز به ورود نیستید."; } ?>`

در این مثال، بر اساس مقدار متغیر `$age`، برنامه تصمیم می‌گیرد که پیام مناسب را نمایش دهد.

4. حلقه‌ها: حلقه‌ها به شما امکان می‌دهند تا یک قسمت از کد را تکرار کنید تا زمانی که یک شرط خاص برقرار باشد. این برای پردازش مجموعه‌ای از داده‌ها یا انجام یک عملیات تکراری مفید است. به عنوان مثال:

`<?php for ($i = 1; $i <= 5; $i++) {     echo $i . " "; } ?>`

در این مثال، یک حلقه `for` برای تکرار عدد 1 تا 5 ایجاد شده است و هر عدد در هر بار تکرار نمایش داده می‌شود.

این فقط یک مثال ساده از ساختار یک برنامه PHP است. بسته به نیازهای شما، می‌توانید از سایر عناصر مانند توابع، آرایه‌ها و کلاس‌ها نیز استفاده کنید. ساختار کدها و تنوع قابلیت‌های PHP با توجه به پروژه و نیازهای شما متفاوت خواهد بود.