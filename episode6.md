جلسه ششم
========

فرم‌ها و پردازش فرم‌ها
----------------------

**فرم‌ها (Forms) :** فرم‌ها (Forms) یک قسمت مهم از توسعه وب در PHP و دیگر زبان‌های برنامه‌نویسی وب هستند. از آنجایی که PHP یک زبان برنامه‌نویسی سمت سرور است، می‌توانید از آن برای ایجاد و پردازش فرم‌ها در وب‌سایت‌های خود استفاده کنید. در ادامه توضیحات کاملی در مورد فرم‌ها و پردازش آنها در PHP ارائه می‌دهم:

**1\. ایجاد فرم** یک فرم در HTML با استفاده از تگ **<form>** ایجاد می‌شود. این تگ معمولاً در بخشی از صفحه وب قرار داده می‌شود که باید اطلاعات ورودی از کاربر را دریافت کند. مثال:

         <html>
         <head>
             <title>فرم ورود </title>
         </head>
         <body>
         <form method="post" action="process.php">
             <label for="username">نام کاربری: </label>
             <input type="text" id="username" name="username"> <br>

             <label for="password">رمز عبور: </label>
             <input type="password" id="password" name="password"> <br>

             <input type="submit" value="ورود">
         </form>
         </body>
         </html>


**2\. ویژگی‌های فرم**

*   **method:** مشخص می‌کند که اطلاعات فرم باید با چه روشی **(GET یا POST)** به سمت سرور ارسال شود.
*   **action:** مسیری است که فرم بعد از ارسال اطلاعات به آن منتقل می‌شود.

**3\. دریافت داده‌ها در PHP** بعد از ارسال فرم، اطلاعات ورودی توسط PHP دریافت می‌شوند. این اطلاعات در متغیر **$\_POST (برای روش POST)** یا **$\_GET (برای روش GET)** در دسترس قرار می‌گیرند. مثال:

            if ($\_SERVER\["REQUEST\_METHOD"\] == "POST") {
                $username = $\_POST\["username"\];
                $password = $\_POST\["password"\];
            }elseif($\_SERVER\["REQUEST\_METHOD"\] == "GET") {
                $username = $\_GET\["username"\];
                $password = $\_GET\["password"\];
            }else{
                die("مقادیر فرم ارسال نشده است");
            }



**4\. اعتبارسنجی داده‌ها** به منظور افزایش امنیت و دقت، داده‌های ورودی باید اعتبارسنجی شوند. این اعتبارسنجی ممکن است شامل بررسی نحوه و نوع داده‌ها، حداقل و حداکثر طول و ... باشد.

**5\. پردازش داده‌ها** بعد از دریافت داده‌ها و اعتبارسنجی، می‌توانید این داده‌ها را برای انجام عملیات مورد نیاز (مثلاً ثبت در پایگاه داده یا اجرای محاسبات) استفاده کنید.

**6\. نمایش خروجی** در نهایت، معمولاً یک صفحه خروجی به کاربر نمایش داده می‌شود تا او بتواند نتیجه عملیات را ببیند.

**7\. امنیت** حتماً باید توجه داشته باشید که فرم‌های شما باید از نقاط ضعف امنیتی محافظت شوند. از توابع مربوط به امنیت مانند **htmlspecialchars()** برای جلوگیری از حملات XSS (Cross-Site Scripting) و از پارامترهای محافظتی برای جلوگیری از حملات تزریق SQL استفاده کنید.

مثال: پردازش یک فرم ورود در ادامه یک مثال ساده برای پردازش یک فرم ورود در PHP آورده شده است:

        if ($\_SERVER\["REQUEST\_METHOD"\] == "POST") {
            $username = $\_POST\["username"\];
            $password = $\_POST\["password"\];

            // اعتبارسنجی و بررسی مدخلات کاربر
            if ($username == "admin" && $password == "password") {
                echo "ورود موفقیت‌آمیز!";
            } else {
                echo "نام کاربری یا رمز عبور اشتباه است.";
            }
        }


این تمامی مراحل مربوط به ایجاد و پردازش یک فرم بسیار ساده در PHP را به صورت خلاصه نشان می‌دهد.

مثال
----

**1\. مثال: فرم تماس با ما** در این مثال، یک فرم تماس با ما ایجاد می‌کنیم. کاربران نام، ایمیل و پیام خود را وارد می‌کنند و اطلاعات به یک صفحه پردازش ارسال می‌شود.

        <!DOCTYPE html>
        <html>
        <head>
            <title>فرم تماس با ما</title>
        </head>
        <body>
        <h1>تماس با ما</h1>
        <form method="post" action="process\_contact.php">
            <label for="name">نام:</label>
            <input type="text" id="name" name="name" required><br>

            <label for="email">ایمیل:</label>
            <input type="email" id="email" name="email" required><br>

            <label for="message">پیام:</label>
            <textarea id="message" name="message" rows="4" required></textarea><br>

            <input type="submit" value="ارسال">
        </form>
        </body>
        </html>


**صفحه پردازش PHP (process\_contact.php):**

        if ($\_SERVER\["REQUEST\_METHOD"\] == "POST") {
            $name = $\_POST\["name"\];
            $email = $\_POST\["email"\];
            $message = $\_POST\["message"\];

            // اعتبارسنجی داده‌ها (مثلاً برای جلوگیری از حملات SQL Injection)
            $name = htmlspecialchars($name);
            $email = htmlspecialchars($email);
            $message = htmlspecialchars($message);

            // در اینجا می‌توانید اطلاعات را به پایگاه داده ذخیره کنید یا به ایمیل ارسال کنید.

            // نمایش پیام موفقیت‌آمیز به کاربر
            echo "پیام شما با موفقیت ارسال شد. با تشکر از تماس شما!";
        }


**2\. مثال: فرم ثبت نام** در این مثال، یک فرم ثبت نام ایجاد می‌کنیم که کاربران نام، ایمیل، رمز عبور و تأیید رمز عبور را وارد می‌کنند. فرم HTML:

            <!DOCTYPE html>
            <html>
            <head>
                <title>فرم ثبت نام</title>
            </head>
            <body>
            <h1>ثبت نام</h1>
            <form method="post" action="process\_registration.php">
                <label for="name">نام:</label>
                <input type="text" id="name" name="name" required><br>

                <label for="email">ایمیل:</label>
                <input type="email" id="email" name="email" required><br>

                <label for="password">رمز عبور:</label>
                <input type="password" id="password" name="password" required><br>

                <label for="confirm\_password">تأیید رمز عبور:</label>
                <input type="password" id="confirm\_password" name="confirm\_password" required><br>

                <input type="submit" value="ثبت نام">
            </form>
            </body>
            </html>


**صفحه پردازش PHP (process\_registration.php):**

        if ($\_SERVER\["REQUEST\_METHOD"\] == "POST") {
            $name = $\_POST\["name"\];
            $email = $\_POST\["email"\];
            $password = $\_POST\["password"\];
            $confirm\_password = $\_POST\["confirm\_password"\];

            // اعتبارسنجی داده‌ها
            $name = htmlspecialchars($name);
            $email = htmlspecialchars($email);

            if ($password != $confirm\_password) {
                echo "رمز عبور و تأیید رمز عبور مطابقت ندارند.";
            } else {
                // در اینجا می‌توانید اطلاعات را به پایگاه داده ذخیره کنید و یا اقدامات دیگری انجام دهید.

                // نمایش پیام موفقیت‌آمیز به کاربر
                echo "ثبت نام شما با موفقیت انجام شد. به سیستم وارد شوید!";
            }
        }


**3\. مثال: فرم آپلود فایل** در این مثال، یک فرم آپلود فایل ایجاد می‌کنیم که به کاربران امکان آپلود تصاویر را می‌دهد.

        <!DOCTYPE html>
        <html>
        <head>
            <title>فرم آپلود فایل</title>
        </head>
        <body>
        <h1>آپلود تصویر</h1>
        <form method="post" action="process\_upload.php" enctype="multipart/form-data">
            <label for="file">فایل تصویر:</label>
            <input type="file" id="file" name="file" accept="image/\*" required><br>

            <input type="submit" value="آپلود">
        </form>
        </body>
        </html>



**صفحه پردازش PHP (process\_upload.php):**

        if ($\_SERVER\["REQUEST\_METHOD"\] == "POST") {
            // اعتبارسنجی و آپلود تصویر
            $file\_name = $\_FILES\["file"\]\["name"\];
            $file\_tmp = $\_FILES\["file"\]\["tmp\_name"\];
            $file\_size = $\_FILES\["file"\]\["size"\];

            // اعتبارسنجی و محدودیت‌های مربوط به فرمت و اندازه تصویر را اعمال کنید.

            if (move\_uploaded\_file($file\_tmp, "uploads/" . $file\_name)) {
                echo "تصویر با موفقیت آپلود شد!";
            } else {
                echo "خطا در آپلود تصویر.";
            }
        }


در این مثال‌ها، شما می‌توانید با ایجاد فرم‌ها در HTML و پردازش آنها در PHP، تعامل کاربران با وب‌سایت خود را بهبود ببخشید. همچنین باید به امنیت و اعتبارسنجی داده‌ها توجه کافی داشته باشید تا از حملات مخرب جلوگیری کنید.

تمرین
-----

**تمرین 1: فرم تماس با ما بهبود یافته** ایجاد یک فرم تماس با ما با فیلدهای دیگری مانند تلفن، موضوع پیام و تعداد کاراکترهای محدودیت پیام. اعتبارسنجی تلفن و ایمیل با استفاده از ابزارهای PHP. اعتبارسنجی محتوای پیام بر اساس تعداد کاراکترهای محدودیتی که تعیین کرده‌اید.

**تمرین 2: سیستم ثبت نام و ورود کاربران** ایجاد یک فرم ثبت نام کاربران با فیلدهای نام، ایمیل، رمز عبور و تأیید رمز عبور. پیاده‌سازی یک صفحه ورود کاربران که از ایمیل و رمز عبور استفاده می‌کند. اعتبارسنجی مطابقت رمز عبور و تأیید رمز عبور.

**تمرین 3: آپلود و نمایش تصاویر** ایجاد یک فرم آپلود تصاویر که تصاویر را در پوشه‌ای در سرور ذخیره می‌کند. نمایش لیست تصاویر آپلود شده به کاربران با استفاده از PHP و HTML.