# پاراگراف اول
![[Pasted image 20220630210049.png]]
شبکه‌های عصبی با حافظه یک بهبود اخیر بر شبکه‌های عصبی مصنوعی هستند که امکان حل وظایف ترتیبی نیازمند حافظه طولانی‌مدت را فراهم کرده‌اند. در اینجا ما به طور خاص به NTM علاقه‌مند هستیم که به شبکه اجازه می‌دهند تا از یک نوار حافظه خارجی برای خواندن و نوشتن اطلاعات در حین اجرا استفاده کند. این بهبود امکان آموزش شبکه‌های عصبی در تعداد تکرار کم‌تر برای وظایف خاص را فراهم می‌کند و همچنین به شبکه اجازه می‌دهد تا رفتار خود را در حین اجرا تغییر دهد.
![[Pasted image 20220630210500.png]]
اگرچه افزایش مقیاس اندازه حافظه و طول دنباله چالش بر انگیز است. به علاوه الگوریتم‌های فعلی برون‌یابی (extrapolating) اطلاعات آموخته‌شده در مسائل با اندازه کوچک به مسائل بزرگ را دشوار می‌کنند. به عنوان مثال در وظیفه رونوشت‌گیری هدف ذخیره و بعدا به خاطر آوردن دنباله‌ای از بردارهای بیتی با طول مشخصی است. 

این مطلوب است که شبکه آموزش‌یافته با یک اندازه بردار بیتی خاص بتواند بر روی اندازه‌های بردار بزرگ‌تر بدون آموزش بیشتر مقیاس پذیر شود. اگرچه روش‌های یادگیری ماشین فعلی اغلب نمی‌تواند چنین دانشی را منتقل کنند.

# پاراگراف دوم
![[Pasted image 20220630213117.png]]
![[Pasted image 20220630213159.png]]
اخیرا یک نسخه قابل تکامل از NTM‌ به نام ENTM ارائه شده است که بر تمایز متکی نبود و مزایای منحصر به فردی را معرفی کرده است:
* اولا علاوه بر وزن‌های شبکه، معماری شبکه بهینه نیز می‌تواند در همان لحظه یادگرفته شود.
* دوما یک مکانیسم توجه سخت مستقیما پشتیبانی شد و کل حافظه نیاز به دسترسی در هر لحظه نداشت.
* سوما یک حافظه در حال رشد و از نظر تئوری با اندازه بی‌نهایت امکان‌پذیر شد.
* به علاوه بر خلاف NTM اصلی شبکه قادر است تا به خوبی با دنباله‌های با طول خیلی زیاد سازگار شود.

اگرچه آن به طور مستقیم کدگذاری ژنتیکی NEAT استفاده کرده است که معنایش آن است که هر پارامتر از شبکه به صورت مجزا در ژنوتایپ آن توصیف می‌شود که این روش مقیاس‌پذیری برای وظیفه رونوشت‌گیری با بردار‌های با اندازه بیت بیشتر از ۸ دارد.

# پاراگراف سوم
![[Pasted image 20220701082305.png]]
برای غلبه به این چالش‌ها در این مقاله ما ENTM‌ را با کدگذاری Hypercube-based NeuroEvolution of Augmenting Topologies ادغام کرده‌ایم.

HyperNEAT یک دید جدید بر روی شبکه‌های عصبی تکاملی با نشان دادن اینکه الگوی وزن‌ها در اتصالات یک شبکه عصبی می‌تواند به عنوان تابعی از هندسه آن تولید شود ارائه کرده است. HyperNEAT یک کدگذاری غیرمستقیم به نام شبکه‌های مولد الگوی ترکیبی (CPPN) به کار بسته است که می‌تواند به صورت فشرده الگوها با قوانین تقارن، تکرار و تکرار با تغییر کدکند. 

HyperNEAT‌ در معرض این حقیقت است که تکامل عصبی از نورون‌هایی که در جایگاه‌های درون فضای مغز وجود دارند و قراردادن نورون‌ها در مکان‌ها به منظور امکان بهره‌برداری از توپوگرافی  بهره می‌ببرد. این باعث می‌شود که اصلاح هندسه سنسورها با هندسه مغز ممکن باشد.

درحالی که چنین چیزی در خیلی از شبکه‌های عصبی نیست اما هندسه یک جنبه ضروری از مغزهای طبیعی است. این دید امکان استفاده از شبکه‌های عصبی بزرگی با منظم‌سازی در اتصالات برای تکامل مسائل با ابعاد بالا را فراهم می‌کند.

# پاراگراف چهارم
![[Pasted image 20220701084038.png]]
در روش جدید معرفی‌شده در این مقاله که HyperENTM نامیده می‌شود یک شبکه عصبی تکامل یافته وزن‌های مدل اصلی شامل چگونگی اتصال به حافظه خارجی را تولید می‌کند. به دلیل آن‌که HyperNEAT می‌تواند هندسه چگونگی اتصال شبکه به حافظه خارجی را یاد بگیرد، این امکان وجود دارد که یک CPPN بر روی اندازه‌های بردار بیتی کوچک آموزش ببیند و سپس به اندازه‌های بردار بیتی بزرگ‌تر بدون آموزش بیشتر مقیاس پذیر شود.

# پاراگراف پنجم
![[Pasted image 20220701084443.png]]
![[Pasted image 20220701084457.png]]
اگرچه وظیفه‌ای که در این مقاله به آن اشاره است که دسترسی به حافظه خارجی می‌تواند به صورت غیر مستقیم کد شود به نظر ساده می‌آید. اما با یک بینش دقیق که می‌توان مزایای کدگذری غیرمستقیم شبکه‌های هایپر را به صورت مستقیم با گرادیان نزولی آموزش داد و سپس آن را با استفاده از پیشرفت‌های اخیر استراتژی‌های تکاملی بر مسائل با الگو‌های پیچیده‌تر اعمال کرد.  