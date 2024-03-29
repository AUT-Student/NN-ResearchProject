# قسمت اول
![[Pasted image 20220630180655.png]]
![[Pasted image 20220630180728.png]]
چهارچوب کلی شامل سه جز است که در تصویر ۱ نشان داده شده است:
* بانک حافظه خارجی برای ادغام با شبکه‌های عصبی سنتی
* شبکه عصبی کنترل‌گر
* بازیابی حافظه و بروز کردن با عملیات مشتق

بانک حافظه خارجی اطلاعات ترتیبی استخراج‌شده از فعالیت‌های یادگیری را ذخیره می‌کند. عملیات خواندن با مکانیسم توجه مبتنی بر محتوا با حافظه تعامل برقرار می‌کند تا به شکل انتخابی اطلاعات مفید را به عنوان اطلاعات کمکی انتخاب کند. 

![[Pasted image 20220630182045.png]]
![[Pasted image 20220630182100.png]]
وظیفه کنترل‌گر گرفتن ورودی و اطلاعات خوانده‌شده از حافظه به واسطه عملیات خواندن، دادن به شبکه عصبی با توجه چندسر، محاسبه خطا و انتشار به عقب آن است. 
عملیات نوشتن با مکانیسم توجه آدرس‌دهی وابسته به مکان، حافظه را با عملیات پاک‌کردن و جمع‌زدن مشتقی بروز می‌کند. حافظه بروز‌شده برای عملیات خواندن در گام پیش‌بینی بعدی در دسترس خواهد بود.

# بازیابی حافظه با مکانیسم توجه برپایه محتوا
![[Pasted image 20220702170800.png]]
در روش پیشنهادی حافظه با یک مکانیسم آدرس‌دهی وابسته به محتوا بازیابی می‌شود. آدرس‌دهی برپایه محتوا به صروت ضروری یک گام محاسبه شباهت میان بردار خروجی کنترل‌گر $C_t$ و بردارهای حافظه موجود $M_t$ است. وزن توجه در خواندن با رابطه ۱ تولید می‌شود:
![[Pasted image 20220630183335.png]]
![[Pasted image 20220630183541.png]]
در رابطه ۱ $\beta$ متغیر شدت است که می‌تواند دقت تمرکز را افزایش یا کاهش دهد. معیار شباهت، شباهت کسینوسی است.

# کنترل‌گر برپایه توجه چندسره
![[Pasted image 20220630183637.png]]
کنترل‌گر می‌تواند با هر شبکه عصبی مصنوعی طراحی شود. ما از یک لایه توجه چندسر استفاده کرده‌ایم تا روابط بین دنباله‌های ورودی و خروجی را مدل کنیم. مقایسه تفاوت بین طراحی‌های شبکه‌های عصبی متفاوت در بخش نتایج آورده شده است.

![[Pasted image 20220702173720.png]]
![[Pasted image 20220630184508.png]]

ما از توجه نرمال‌شده ضرب داخلی دار مطابق رابطه ۲ استفاده می‌کنیم. در این رابطه Q، K و V به ترتیب ماتریس کوئری، کلید و مقدار هستند و n تعداد ابعاد است. توجه بر دنباله ورودی I اعمال می‌شود تا یک جمع وزن‌دار برای هر $i_t$ بر پایه $i_1$ تا $i_t$ اعمال شود که t زمان فعلی است. 

به عنوان خروجی مدل یک بردار وزن مرتبط با هر تلاش را یاد می‌گیرد و برداز وزن یادگرفته‌شده برای محاسبه پیش‌بینی خروجی $i_t$ استفاده می‌شود. از تابع خطا میانگین مربعات خطا مطابق رابطه ۳ استفاده می‌شود.

![[Pasted image 20220630184537.png]]
![[Pasted image 20220630184549.png]]
در رابطه ۳ $a_t^k$ پیش‌بینی و $gt_t^k$ اطلاعات برچسب، b اندازه دسته، k طول دنباله و t زمان است.

# بروز کردن حافظه با مکانیسم توجه
![[Pasted image 20220630200910.png]]
در روش پیشنهادی حافظه با مکانیسم آدرس‌دهی برپایه موقعیت بروز می‌شود. مکانیسم آدرس‌دهی برپایه موقعیت برای چندین گام طراحی شده است تا تکرار بر روی خانه‌های حافظه و پرش‌های دسترسی تصادفی را امکان‌پذیر کند. 

گام اول محاسبه درون‌یابی (interpolation) بین بردار وزن نوشتن پیشین $w_{t-1}$ و بردار وزن محتوا تولیدشده توسط مکانیسم آدرس‌دهی محتوا $w_t^c$ در گام زمانی فعلی با استفاده از گیت درون‌یابی $w_t^g$ است: رابطه ۴

![[Pasted image 20220630201049.png]]
بعد از درون‌یابی یک وزن‌دهی جابجایی $s_t$ بر ماتریس وزن دروازه‌دار با یک کانولوشن دایره‌ای برای تنظیم حافظه اعمال می‌شود: <رابطه ۵> در این رابطه N برابر با اندازه حافظه است.

![[Pasted image 20220630201317.png]]
در گام آخر یک عمل تیزکردن برای وزن نهایی اعمال می‌شود: رابطه 6