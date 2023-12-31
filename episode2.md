جلسه دوم
========

متغیرها و نوع داده‌ها
---------------------

**تعریف متغیرها:** در PHP، می‌توانید متغیرها را با استفاده از علامت دلار **($)** تعریف کنید، مانند `$name` یا `$age`. **متغیرها در PHP حساس به بزرگی و کوچکی حروف هستند**، بنابراین $name و $Name دو متغیر متفاوت هستند.

**نوع داده‌ها:** در PHP، متغیرها می‌توانند نوع داده‌های مختلفی داشته باشند. **برخی از نوع داده‌های پایه شامل اعداد صحیح (integer)، اعداد اعشاری (float یا double)، رشته‌ها (string) و بولین (boolean) هستند.** برای تعریف نوع داده‌ی متغیرها، شما نیازی به تعیین آن ندارید، زیرا PHP یک زبان برنامه‌نویسی بدون نیاز به تعیین نوع **(dynamically typed)** است.

**تعیین مقدار به متغیرها:** برای تعیین مقدار به یک متغیر در PHP، شما می‌توانید از عملگر = استفاده کنید. به عنوان مثال:

                $name = "John";
                $age = 25;
                $isStudent = true;


**نمایش مقدار متغیرها:** برای نمایش مقدار متغیرها در PHP، می‌توانید از تابع **echo** استفاده کنید. به عنوان مثال:

                $name = "John";
                echo "نام: " . $name; // نمایش "نام: John"


**تغییر مقدار متغیرها:** در طول اجرای برنامه، می‌توانید مقدار متغیرها را تغییر دهید. برای این کار، به سادگی مقدار جدید را به متغیر اختصاص دهید. به عنوان مثال:

                $age = 25;
                $age = $age + 1; // تغییر مقدار متغیر $age به 26



**تایپ متغیرها:** در PHP، نوع داده متغیرها می‌تواند در طول زمان تغییر کند. به عنوان مثال، می‌توانید یک متغیر را ابتدا به عدد صحیح تعریف کنید و سپس به یک رشته تغییر دهید.

عبارات شرطی
-----------

**عبارات شرطی:** عبارات شرطی **(Conditional Statements)** در PHP امکان بررسی شرایط و اجرای بخش‌های مختلف کد بر اساس این شرایط را فراهم می‌کنند. این عبارات با استفاده از کلمات کلیدی مخصوصی مانند  
`if، else if و else` بیان می‌شوند. در ادامه، نحوه استفاده از عبارات شرطی در PHP را مشاهده می‌کنید:

**عبارت if:** این عبارت برای اجرای یک بخش از کد مشروط به برقراری شرطی خاص استفاده می‌شود. اگر شرط برقرار باشد (true)، بخش کد داخل بلاک if اجرا می‌شود. در غیر این صورت، بلاک if نادیده گرفته می‌شود.

            $age = 25;
            if ($age >= 18) {
            echo "شما مجاز به ورود هستید.";
            }


**عبارت if و else:** با استفاده از else، می‌توانیم یک بلاک دیگر را تعیین کنیم که اجرا می‌شود اگر شرط if برقرار نباشد.

            $age = 15;
            if ($age >= 18) {
            echo "شما مجاز به ورود هستید.";
            } else {
            echo "شما مجاز به ورود نیستید.";
            }


**عبارت if و else if:** else if (یا elseif) برای افزودن شرایط بیشتر در عبارات شرطی استفاده می‌شود. در صورتی که شرط if برقرار نباشد، شرایط elseif بررسی می‌شوند و اگر یکی از شرایط elseif برقرار باشد، بلاک مرتبط با آن اجرا می‌شود.

            $grade = 85;
            if ($grade >= 90) {
            echo "عالی!";
            } elseif ($grade >= 70) {
            echo "خوب!";
            } else {
            echo "نیاز به بهبود دارید.";
            }


**عبارت switch:** switch یک روش دیگر برای انجام شرط‌بندی‌ها است که برای بررسی یک متغیر در مقابل مقادیر مختلف استفاده می‌شود. اگر مقدار متغیر با یکی از مقادیر case تطابق داشته باشد، بلاک مربوط به آن case اجرا می‌شود. همچنین، می‌توانیم default را برای اجرای یک بلاک دیفالت تعیین کنیم اگر هیچ یک از case‌ها برقرار نباشند.

            $day = "سه‌شنبه";
            switch ($day) {
            case "شنبه":
            case "یک‌شنبه":
            case "دو‌شنبه":
            echo "حوصله کار کردن نیست!";
            break;
            case "سه‌شنبه":
            echo "دوس دارم کار کنم!";
            break;
            default:
            echo "باید کار کنم!";
            }


این عبارات شرطی می‌توانند به شما کمک کنند تا برنامه‌های پویا و متناسب با شرایط مختلف اجرا شوند و به مدیریت بهتر جریان اجرای برنامه کمک کنند.