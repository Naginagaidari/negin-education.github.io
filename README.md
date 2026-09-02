from pathlib import Path
import zipfile, textwrap

root = Path("/mnt/data/negin-github-pages")
root.mkdir(parents=True, exist_ok=True)

html = r'''<!doctype html>
<html lang="fa" dir="rtl">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
  <meta name="theme-color" content="#073b4c">
  <meta name="description" content="مرکز آموزشی و توانبخشی نگین؛ آموزش، توانبخشی و حمایت از کودکان دارای معلولیت در افغانستان.">
  <title>مرکز آموزشی و توانبخشی نگین</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Arabic:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="style.css">
</head>
<body>
<header class="site-header">
  <div class="nav wrap">
    <a class="brand" href="#home" aria-label="صفحه اصلی">
      <span class="brand-mark">◆</span><span><small data-i18n="brandSmall">مؤسسه‌ی خدماتی و حرفوی زنان بی‌بضاعت</small><strong data-i18n="brand">مرکز آموزشی و توانبخشی نگین</strong></span>
    </a>
    <nav class="desktop-nav" aria-label="ناوبری اصلی">
      <a href="#about" data-i18n="about">درباره ما</a><a href="#services" data-i18n="services">خدمات</a><a href="#education" data-i18n="education">آموزش</a><a href="#games" data-i18n="games">هنر و بازی</a><a href="#register" data-i18n="register">ثبت‌نام</a><a href="#contact" data-i18n="contact">تماس</a>
    </nav>
    <div class="tools">
      <button class="icon-btn" id="langBtn" title="تغییر زبان" aria-label="تغییر زبان">🌐</button>
      <button class="icon-btn" id="accessBtn" title="تنظیمات دسترس‌پذیری" aria-label="تنظیمات دسترس‌پذیری">◐</button>
      <button class="icon-btn menu-btn" id="menuBtn" aria-label="باز کردن منو">☰</button>
    </div>
  </div>
  <div id="mobileNav" class="mobile-nav">
    <a href="#about" data-i18n="about">درباره ما</a><a href="#services" data-i18n="services">خدمات</a><a href="#education" data-i18n="education">آموزش</a><a href="#games" data-i18n="games">هنر و بازی</a><a href="#register" data-i18n="register">ثبت‌نام</a><a href="#contact" data-i18n="contact">تماس</a>
  </div>
</header>

<main id="home">
  <section class="hero">
    <div class="hero-slides" id="slides"></div>
    <div class="hero-overlay"></div>
    <div class="hero-content wrap glass">
      <div class="eyebrow">🧩 <span data-i18n="eyebrow">آموزش • توانبخشی • حمایت</span></div>
      <h1 data-i18n="heroTitle">مرکز آموزشی و توانبخشی نگین</h1>
      <p data-i18n="heroText">خانه‌ای امن برای آموزش و توانمندسازی کودکان دارای معلولیت در افغانستان</p>
      <div class="hero-slogan">✨ <span data-i18n="slogan">هر کودک یک نگین است</span> ✨</div>
      <div class="hero-actions"><a class="btn primary" href="#register" data-i18n="register">ثبت‌نام شاگردان</a><a class="btn light" href="#services" data-i18n="viewServices">مشاهده خدمات</a></div>
      <div class="dots" id="dots" aria-label="اسلایدها"></div>
    </div>
  </section>

  <section class="quick wrap">
    <button class="quick-card" data-target="#about"><span>🏠</span><b data-i18n="about">درباره مرکز نگین</b><small>آشنایی با اهداف و چشم‌انداز مرکز</small></button>
    <button class="quick-card" data-target="#education"><span>📚</span><b data-i18n="education">آموزش ویژه</b><small>برنامه متناسب با توانایی هر کودک</small></button>
    <button class="quick-card" data-target="#services"><span>🧑‍🦽</span><b data-i18n="rehab">توانبخشی</b><small>فیزیوتراپی، کاردرمانی و گفتاردرمانی</small></button>
    <button class="quick-card" data-target="#register"><span>📝</span><b data-i18n="register">ثبت‌نام</b><small>درخواست دریافت خدمات مرکز</small></button>
  </section>

  <section id="about" class="section wrap">
    <div class="section-title"><span>❤️</span><div><p class="eyebrow">درباره ما</p><h2 data-i18n="aboutHeading">هر کودک شایسته فرصت برابر است</h2></div><button class="speak" data-speak="#about" aria-label="خواندن این بخش">🔊</button></div>
    <div class="about-grid">
      <article class="card"><h3>معرفی کوتاه مرکز</h3><p>سلام، ما نگین هستیم. مرکز آموزشی و توانبخشی نگین با هدف ایجاد خانه‌ای امن برای آموزش، توانبخشی و توانمندسازی کودکان دارای معلولیت در کابل فعالیت می‌کند.</p><p>ما باور داریم هیچ کودکی نباید به خاطر تفاوت‌هایش از آموزش و فرصت‌های زندگی محروم بماند.</p></article>
      <article class="card"><h3>داستان نگین</h3><p>این مرکز حاصل سال‌ها آرزوی اسدالله حیدری و ساحل حیدری و تلاش برای ساختن فضایی فراگیر برای کودکان است و با همراهی اجمیر خان میرزاد و دیگر نیکوکاران به مسیر خود ادامه می‌دهد.</p><p>هدف ما ساختن آینده‌ای است که در آن هر کودک بتواند توانایی‌های خود را بشناسد و با کرامت در خانواده و جامعه مشارکت کند.</p></article>
    </div>
    <div class="quote">«با اراده می‌توان، با همت می‌سازیم»<span>— اجمیر خان میرزاد</span></div>
  </section>

  <section id="services" class="section alt">
    <div class="wrap">
      <div class="section-title"><span>🧩</span><div><p class="eyebrow">خدمات</p><h2>سه محور اصلی و خدمات تخصصی</h2></div><button class="speak" data-speak="#services" aria-label="خواندن این بخش">🔊</button></div>
      <div class="service-grid">
        <article class="service card"><span>📚</span><h3>آموزش ویژه</h3><p>برنامه‌های آموزشی فردی‌سازی‌شده برای تقویت مهارت‌های آموزشی، ارتباطی، اجتماعی و زندگی روزمره.</p></article>
        <article class="service card"><span>💪</span><h3>فیزیوتراپی</h3><p>حمایت از حرکت، تعادل، قدرت، کنترل بدن و استقلال کودک بر اساس ارزیابی تخصصی.</p></article>
        <article class="service card"><span>🗣️</span><h3>گفتاردرمانی</h3><p>تقویت گفتار، زبان و ارتباط؛ با توجه به نیاز کودک و در صورت نیاز استفاده از روش‌های ارتباط جایگزین.</p></article>
        <article class="service card"><span>🖐️</span><h3>کاردرمانی</h3><p>تقویت مهارت‌های حرکتی ظریف، شناختی، خودمراقبتی، بازی و مشارکت در فعالیت‌های روزمره.</p></article>
        <article class="service card"><span>🧠</span><h3>مشاوره خانواده</h3><p>راهنمایی و آموزش خانواده برای حمایت بهتر از رشد و مشارکت کودک در خانه و جامعه.</p></article>
        <article class="service card"><span>🤝</span><h3>مددکاری و حمایت</h3><p>ارتباط خانواده‌ها با منابع حمایتی و ایجاد فرصت همکاری، داوطلبی و کمک به کودکان.</p></article>
      </div>
    </div>
  </section>

  <section id="education" class="section wrap">
    <div class="section-title"><span>📚</span><div><p class="eyebrow">آموزش ویژه</p><h2>آموزش متناسب با توانایی‌های هر کودک</h2></div><button class="speak" data-speak="#education" aria-label="خواندن این بخش">🔊</button></div>
    <div class="content-card card"><p>در نگین، مسیر یادگیری برای همه کودکان یکسان نیست. برنامه می‌تواند بر اساس ارزیابی اولیه و اهداف فردی تنظیم شود.</p>
      <div class="pill-grid"><span>🔤 حروف و اعداد</span><span>✏️ خواندن و نوشتن</span><span>🧠 تمرکز و حافظه</span><span>💬 ارتباط</span><span>🤝 مهارت اجتماعی</span><span>🧒 خودمراقبتی</span><span>🎯 حل مسئله</span><span>🌱 استقلال</span></div>
      <h3>اصول ما</h3><p>احترام به کودک، فرصت برابر، کودک‌محوری، همکاری با خانواده، تمرکز بر پیشرفت خود کودک و حفظ محرمانگی اطلاعات.</p>
    </div>
  </section>

  <section id="games" class="section alt">
    <div class="wrap">
      <div class="section-title"><span>🎨</span><div><p class="eyebrow">هنر و خلاقیت</p><h2>یادگیری از راه بازی</h2></div><button class="speak" data-speak="#games" aria-label="خواندن این بخش">🔊</button></div>
      <div class="games-grid">
        <div class="game card"><h3>🎨 بوم نقاشی</h3><canvas id="canvas" width="600" height="330"></canvas><div class="game-controls"><button id="clearCanvas">پاک کردن</button><input id="brush" type="range" min="2" max="30" value="8" aria-label="اندازه قلم"></div></div>
        <div class="game card"><h3>🔢 بازی اعداد</h3><p>عدد <b id="numberTarget">۵</b> را پیدا کن.</p><div class="number-buttons" id="numbers"></div><p id="gameMessage" class="success"></p></div>
        <div class="game card"><h3>🔤 حروف الفبا</h3><p id="letter" class="big-letter">آ</p><p id="letterMeaning">آ مثل آب</p><button class="btn primary" id="nextLetter">حرف بعدی</button></div>
        <div class="game card"><h3>🎹 پیانوی تعاملی</h3><div class="piano" id="piano"></div><small>روی کلیدها بزنید.</small></div>
      </div>
    </div>
  </section>

  <section id="register" class="section wrap">
    <div class="section-title"><span>📝</span><div><p class="eyebrow">ثبت‌نام</p><h2>درخواست دریافت خدمات</h2></div><button class="speak" data-speak="#register" aria-label="خواندن این بخش">🔊</button></div>
    <form class="form card" id="regForm">
      <label>نام کودک<input required name="child" autocomplete="name"></label>
      <label>نام والد/سرپرست<input required name="guardian"></label>
      <label>شماره تماس<input required name="phone" inputmode="tel"></label>
      <label>نوع خدمات<select name="service"><option>آموزش ویژه</option><option>فیزیوتراپی</option><option>گفتاردرمانی</option><option>کاردرمانی</option><option>مشاوره</option></select></label>
      <label class="full">توضیحات<textarea name="note" rows="4"></textarea></label>
      <button class="btn primary full" type="submit">ارسال درخواست</button>
      <p id="formStatus" class="success full" role="status"></p>
    </form>
  </section>

  <section class="section team alt">
    <div class="wrap"><div class="section-title"><span>👥</span><div><p class="eyebrow">تیم ما</p><h2>انسان‌هایی در کنار کودکان</h2></div><button class="speak" data-speak=".team" aria-label="خواندن این بخش">🔊</button></div>
      <div class="team-grid"><article class="person card"><div class="avatar">ا</div><h3>اسدالله حیدری</h3><p>بنیان‌گذار و مدیر اجرایی</p></article><article class="person card"><div class="avatar">س</div><h3>ساحل حیدری</h3><p>بنیان‌گذار و مدیر آموزشی</p></article><article class="person card"><div class="avatar">ا</div><h3>اجمیر خان میرزاد</h3><p>مشاور ارشد و حامی کلیدی</p></article></div>
    </div>
  </section>

  <section class="section wrap">
    <div class="stories card"><h2>❤️ نظرات خانواده‌ها</h2><blockquote>«وقتی دیدم بچّه‌ام با ویلچر وارد کلاس شد و با لبخند از من خداحافظی کرد، فهمیدم که نگین همان جایی است که سال‌ها دنبالش می‌گشتم.»<cite>— پدر یکی از دانش‌آموزان</cite></blockquote></div>
  </section>

  <section id="contact" class="section contact-section">
    <div class="wrap"><div class="section-title"><span>📞</span><div><p class="eyebrow">تماس با ما</p><h2>همراه نگین باشید</h2></div><button class="speak" data-speak="#contact" aria-label="خواندن این بخش">🔊</button></div>
      <div class="contact-grid">
        <div class="card contact-card"><p>📞 <b>۰۷۸۶۸۳۸۰۰۲</b></p><p>✉️ <b>negineducationcenter@gmail.com</b></p><p>📍 سرک ۳۷، پروژه وزیر آباد، کابل، افغانستان</p><p>🕐 شنبه تا چهارشنبه: ۸ صبح تا ۴ بعدازظهر<br>پنجشنبه: ۸ صبح تا ۱۲ ظهر</p><div class="contact-actions"><a class="whatsapp" href="https://wa.me/93786838002" target="_blank" rel="noopener">🟢 واتس‌اپ</a><a class="map" href="https://maps.app.goo.gl/UTwdrbUfqR6ewS9D9" target="_blank" rel="noopener">📍 مشاهده در نقشه گوگل</a></div></div>
        <div class="map-box card"><div>📍</div><h3>موقعیت مرکز</h3><p>برای مشاهده موقعیت دقیق مرکز روی نقشه، دکمه زیر را انتخاب کنید.</p><a class="btn primary" href="https://maps.app.goo.gl/UTwdrbUfqR6ewS9D9" target="_blank" rel="noopener">باز کردن Google Maps</a></div>
      </div>
    </div>
  </section>
</main>

<footer class="footer"><div class="wrap footer-grid"><div><div class="footer-logo">◆ مرکز آموزشی و توانبخشی نگین</div><p>هر کودک، یک نگین.</p></div><div><h3>لینک‌های سریع</h3><a href="#about">درباره ما</a><a href="#services">خدمات</a><a href="#register">ثبت‌نام</a><a href="#contact">تماس با ما</a></div><div><h3>رسانه‌های اجتماعی</h3><div class="socials"><a aria-label="Facebook" href="#">f</a><a aria-label="Instagram" href="#">◎</a><a aria-label="YouTube" href="#">▶</a><a aria-label="Telegram" href="#">➤</a></div></div></div><div class="copyright">© ۱۴۰۵ مرکز آموزشی و توانبخشی نگین</div></footer>

<a class="float-whatsapp" href="https://wa.me/93786838002" target="_blank" rel="noopener" aria-label="واتس‌اپ">◔</a>
<button class="chat-fab" id="chatFab" aria-label="چت بات">💬</button>
<div class="chat" id="chat" aria-hidden="true"><div class="chat-head">💬 دستیار نگین <button id="chatClose">×</button></div><div class="chat-body" id="chatBody"><div class="bot">سلام! من دستیار نگین هستم. درباره خدمات، ثبت‌نام، تماس یا بخش‌های سایت بپرسید.</div></div><div class="chat-input"><input id="chatInput" placeholder="سوال خود را بنویسید..."><button id="chatSend">➤</button></div></div>

<div class="access-modal" id="accessModal" aria-hidden="true"><div class="access-box"><button class="close" id="accessClose">×</button><h2>تنظیمات دسترس‌پذیری</h2><div class="access-row"><span>اندازه متن</span><div><button id="fontDown">A−</button><button id="fontReset">A</button><button id="fontUp">A+</button></div></div><div class="access-row"><span>حالت شب</span><button id="darkBtn">🌙</button></div><div class="access-row"><span>کنتراست بالا</span><button id="contrastBtn">◐</button></div><button class="btn primary" id="resetAccess">↻ بازگردانی تنظیمات</button></div></div>

<script src="script.js"></script>
</body>
</html>'''

css = r'''*{box-sizing:border-box}html{scroll-behavior:smooth}body{margin:0;font-family:"Noto Sans Arabic",Tahoma,sans-serif;color:#17323b;background:#f7fbfc;line-height:1.9;font-size:16px}body.dark{background:#0c1b20;color:#e8f4f5}body.high-contrast{filter:contrast(1.18)}a{color:inherit;text-decoration:none}button,input,textarea,select{font:inherit}button{cursor:pointer}.wrap{width:min(1120px,calc(100% - 32px));margin:auto}.site-header{position:sticky;top:0;z-index:100;background:rgba(255,255,255,.86);backdrop-filter:blur(14px);box-shadow:0 2px 18px #00000010}.dark .site-header{background:rgba(9,28,34,.9)}.nav{min-height:74px;display:flex;align-items:center;gap:22px}.brand{display:flex;align-items:center;gap:10px;margin-left:auto}.brand-mark{display:grid;place-items:center;width:40px;height:40px;border-radius:13px;background:#0a7380;color:white;font-size:21px}.brand small,.brand strong{display:block;line-height:1.35}.brand small{font-size:11px;color:#527078}.brand strong{font-size:17px}.desktop-nav{display:flex;gap:18px;font-size:14px}.desktop-nav a:hover{color:#078c72}.tools{display:flex;gap:6px}.icon-btn,.speak{border:1px solid #d5e6e8;background:#fff;border-radius:12px;width:40px;height:40px}.dark .icon-btn,.dark .speak{background:#132d34;color:white;border-color:#31525a}.menu-btn{display:none}.mobile-nav{display:none}.hero{height:650px;position:relative;overflow:hidden}.hero-slides,.hero-slide{position:absolute;inset:0}.hero-slide{background-size:cover;background-position:center;opacity:0;transition:opacity 1s}.hero-slide.active{opacity:1}.hero-overlay{position:absolute;inset:0;background:linear-gradient(90deg,rgba(2,34,44,.2),rgba(2,34,44,.68))}.hero-content{position:relative;z-index:2;top:50%;transform:translateY(-50%);padding:38px;max-width:790px;margin-right:max(16px,calc((100% - 1120px)/2));margin-left:auto}.glass{background:rgba(255,255,255,.2);border:1px solid rgba(255,255,255,.4);backdrop-filter:blur(12px);color:#fff;border-radius:28px}.eyebrow{font-weight:800;color:#078c72;margin:0 0 5px}.hero .eyebrow{color:#d6fff2}.hero h1{font-size:clamp(30px,5vw,56px);margin:5px 0 10px;line-height:1.25}.hero p{font-size:20px;margin:0 0 8px}.hero-slogan{font-size:22px;font-weight:800}.hero-actions{display:flex;gap:10px;margin-top:22px}.btn{display:inline-flex;justify-content:center;align-items:center;min-height:48px;padding:8px 20px;border-radius:13px;border:0;font-weight:800}.primary{background:#078c72;color:#fff}.light{background:#fff;color:#075267}.dots{display:flex;gap:7px;margin-top:20px}.dots button{width:9px;height:9px;padding:0;border:0;border-radius:50%;background:#fff8}.dots button.active{background:#fff;width:26px;border-radius:8px}.quick{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-top:-45px;position:relative;z-index:4}.quick-card{border:0;background:white;border-radius:20px;padding:20px;text-align:right;box-shadow:0 12px 30px #123c4615}.dark .quick-card,.dark .card{background:#132d34;color:#e8f4f5}.quick-card span{font-size:28px}.quick-card b,.quick-card small{display:block}.quick-card small{color:#678087}.section{padding:82px 0}.alt{background:#eaf5f5}.dark .alt{background:#10282e}.section-title{display:flex;align-items:center;gap:14px;margin-bottom:28px}.section-title>span{font-size:34px}.section-title h2{margin:0;font-size:30px}.section-title .speak{margin-right:auto}.card{background:#fff;border-radius:20px;padding:25px;box-shadow:0 8px 28px #123c4610}.about-grid,.contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:18px}.quote{margin-top:20px;background:#075267;color:#fff;padding:25px;border-radius:20px;font-size:20px;text-align:center;font-weight:700}.quote span{display:block;font-size:14px;margin-top:7px;font-weight:400}.service-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}.service span{font-size:35px}.service h3{margin:8px 0}.pill-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;margin:22px 0}.pill-grid span{padding:12px;border-radius:12px;background:#eaf5f5;font-weight:600}.dark .pill-grid span{background:#1d3a41}.games-grid{display:grid;grid-template-columns:1.3fr 1fr 1fr 1fr;gap:15px}.game h3{margin-top:0}.game canvas{width:100%;height:auto;border:2px dashed #9bbabd;border-radius:14px;touch-action:none;background:#fff}.game-controls{display:flex;align-items:center;gap:10px;margin-top:10px}.game-controls button,.number-buttons button,.access-row button{border:1px solid #c8dcdf;background:#f4fafb;border-radius:10px;padding:7px 12px}.number-buttons{display:grid;grid-template-columns:repeat(3,1fr);gap:8px}.number-buttons button{min-height:50px}.big-letter{text-align:center;font-size:70px;font-weight:800;margin:10px}.piano{display:flex;gap:3px;height:150px;align-items:stretch}.piano button{flex:1;border:1px solid #789398;background:white;border-radius:0 0 8px 8px}.piano button:active{transform:translateY(3px)}.form{display:grid;grid-template-columns:1fr 1fr;gap:15px}.form label{font-weight:700}.form input,.form textarea,.form select{display:block;width:100%;margin-top:6px;border:1px solid #c9dde0;border-radius:12px;padding:12px;background:#fff}.dark .form input,.dark .form textarea,.dark .form select{background:#0d242a;color:#fff}.full{grid-column:1/-1}.success{color:#078c72;font-weight:700}.team-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}.person{text-align:center}.avatar{width:72px;height:72px;margin:auto;border-radius:50%;display:grid;place-items:center;background:#078c72;color:#fff;font-size:30px;font-weight:800}.stories blockquote{margin:0;font-size:19px}.stories cite{display:block;margin-top:12px;font-size:14px}.contact-section{background:#075267;color:white}.contact-section .eyebrow{color:#80e1c7}.contact-card,.map-box{color:#17323b}.contact-actions{display:flex;gap:9px;flex-wrap:wrap;margin-top:18px}.whatsapp,.map{padding:10px 15px;border-radius:12px;background:#eaf8f2}.map{background:#eaf5f5}.map-box{text-align:center;display:grid;place-items:center;align-content:center}.map-box>div{font-size:45px}.footer{background:#062b36;color:#cde1e5;padding:45px 0 15px}.footer-grid{display:grid;grid-template-columns:2fr 1fr 1fr;gap:30px}.footer-logo{font-weight:800;color:white;font-size:19px}.footer-grid h3{color:white}.footer-grid>div>a{display:block;margin:5px 0}.socials{display:flex;gap:8px}.socials a{display:grid!important;place-items:center;width:40px;height:40px;border:1px solid #527982;border-radius:50%}.copyright{text-align:center;border-top:1px solid #31545d;margin-top:30px;padding-top:15px;font-size:13px}.float-whatsapp,.chat-fab{position:fixed;z-index:120;border:0;color:white;border-radius:50%;width:58px;height:58px;display:grid;place-items:center;box-shadow:0 8px 25px #0003;font-size:25px}.float-whatsapp{left:20px;bottom:20px;background:#25d366}.chat-fab{right:20px;bottom:20px;background:#075267}.chat{position:fixed;right:20px;bottom:90px;width:min(370px,calc(100% - 40px));z-index:119;background:white;border-radius:18px;box-shadow:0 15px 50px #0004;overflow:hidden;display:none}.chat.open{display:block}.chat-head{background:#075267;color:white;padding:13px 15px;font-weight:800;display:flex;justify-content:space-between}.chat-head button{background:none;border:0;color:white;font-size:24px}.chat-body{height:290px;overflow:auto;padding:13px}.bot,.user{padding:9px 12px;border-radius:13px;margin-bottom:8px;max-width:88%;background:#edf7f7}.user{margin-right:auto;background:#d7f1e8}.chat-input{display:flex;padding:8px;border-top:1px solid #ddd}.chat-input input{flex:1;border:0;padding:9px;outline:0}.chat-input button{border:0;background:#078c72;color:white;border-radius:10px;width:42px}.access-modal{position:fixed;inset:0;background:#0007;z-index:200;display:none;align-items:center;justify-content:center;padding:20px}.access-modal.open{display:flex}.access-box{background:white;color:#17323b;width:min(430px,100%);border-radius:20px;padding:25px;position:relative}.dark .access-box{background:#132d34;color:#fff}.close{position:absolute;left:15px;top:10px;border:0;background:none;font-size:28px}.access-row{display:flex;justify-content:space-between;align-items:center;padding:13px 0;border-bottom:1px solid #ddd}.access-row button{margin-right:5px}.dark .access-row button{background:#0d242a;color:white}.font-large{font-size:19px}.font-xl{font-size:22px}@media(max-width:900px){.desktop-nav{display:none}.menu-btn{display:block}.mobile-nav{padding:10px 16px;display:none;gap:8px;flex-wrap:wrap}.mobile-nav.open{display:flex}.mobile-nav a{padding:8px 12px;background:#eaf5f5;border-radius:10px}.dark .mobile-nav a{background:#132d34}.hero{height:590px}.hero-content{margin:0 16px;padding:25px}.quick{grid-template-columns:repeat(2,1fr);margin-top:-25px}.service-grid,.games-grid{grid-template-columns:repeat(2,1fr)}.pill-grid{grid-template-columns:repeat(2,1fr)}.team-grid{grid-template-columns:1fr 1fr}.footer-grid{grid-template-columns:1fr 1fr}}@media(max-width:600px){.wrap{width:min(100% - 22px,1120px)}.nav{min-height:65px}.brand small{display:none}.brand strong{font-size:14px}.hero{height:620px}.hero h1{font-size:31px}.hero p{font-size:16px}.hero-slogan{font-size:18px}.hero-content{top:54%;padding:22px}.hero-actions{flex-direction:column}.quick,.about-grid,.contact-grid,.service-grid,.games-grid,.team-grid,.form{grid-template-columns:1fr}.section{padding:58px 0}.section-title h2{font-size:24px}.pill-grid{grid-template-columns:1fr 1fr}.footer-grid{grid-template-columns:1fr}.float-whatsapp{left:13px;bottom:13px;width:52px;height:52px}.chat-fab{right:13px;bottom:13px;width:52px;height:52px}.chat{right:11px;bottom:76px;width:calc(100% - 22px)}}'''

js = r'''const slides=[
"https://images.unsplash.com/photo-1488521787991-ed7bbaae773c?auto=format&fit=crop&w=1800&q=80",
"https://images.unsplash.com/photo-1509099836639-18ba1795216d?auto=format&fit=crop&w=1800&q=80",
"https://images.unsplash.com/photo-1542810634-71277d95dcbb?auto=format&fit=crop&w=1800&q=80",
"https://images.unsplash.com/photo-1504159506876-f8338247a14a?auto=format&fit=crop&w=1800&q=80"
];
const slidesEl=document.getElementById("slides"),dots=document.getElementById("dots");
slides.forEach((src,i)=>{const s=document.createElement("div");s.className="hero-slide"+(i===0?" active":"");s.style.backgroundImage=`url("${src}")`;slidesEl.appendChild(s);const d=document.createElement("button");d.className=i===0?"active":"";d.setAttribute("aria-label",`اسلاید ${i+1}`);d.onclick=()=>showSlide(i);dots.appendChild(d)});
let current=0;
function showSlide(i){const ss=document.querySelectorAll(".hero-slide"),ds=dots.children;ss[current].classList.remove("active");ds[current].classList.remove("active");current=i%ss.length;ss[current].classList.add("active");ds[current].classList.add("active")}
setInterval(()=>showSlide(current+1),5000);

document.querySelectorAll("[data-target]").forEach(b=>b.onclick=()=>document.querySelector(b.dataset.target)?.scrollIntoView({behavior:"smooth"}));
document.getElementById("menuBtn").onclick=()=>document.getElementById("mobileNav").classList.toggle("open");

const translations={
fa:{brandSmall:"مؤسسه‌ی خدماتی و حرفوی زنان بی‌بضاعت",brand:"مرکز آموزشی و توانبخشی نگین",about:"درباره ما",services:"خدمات",education:"آموزش",games:"هنر و بازی",register:"ثبت‌نام",contact:"تماس",rehab:"توانبخشی",eyebrow:"آموزش • توانبخشی • حمایت",heroTitle:"مرکز آموزشی و توانبخشی نگین",heroText:"خانه‌ای امن برای آموزش و توانمندسازی کودکان دارای معلولیت در افغانستان",slogan:"هر کودک یک نگین است",viewServices:"مشاهده خدمات",aboutHeading:"هر کودک شایسته فرصت برابر است"},
ps:{brandSmall:"د بې وزلو ښځو د خدماتو او حرفوي چارو مؤسسه",brand:"د نگین د ښوونې او بیارغونې مرکز",about:"زموږ په اړه",services:"خدمتونه",education:"ښوونه",games:"هنر او لوبې",register:"نوم‌لیکنه",contact:"اړیکه",rehab:"بیارغونه",eyebrow:"ښوونه • بیارغونه • ملاتړ",heroTitle:"د نگین د ښوونې او بیارغونې مرکز",heroText:"په افغانستان کې د معلولیت لرونکو ماشومانو لپاره د ښوونې او پیاوړتیا خوندي کور",slogan:"هر ماشوم یو نگین دی",viewServices:"خدمتونه وګورئ",aboutHeading:"هر ماشوم د برابر فرصت وړ دی"}
};
let lang="fa";
function setLanguage(l){lang=l;document.documentElement.lang=l==="ps"?"ps":"fa";document.documentElement.dir="rtl";document.querySelectorAll("[data-i18n]").forEach(el=>{const k=el.dataset.i18n;if(translations[l][k])el.textContent=translations[l][k]});document.getElementById("langBtn").title=l==="fa"?"پشتو":"دری";localStorage.lang=l}
document.getElementById("langBtn").onclick=()=>setLanguage(lang==="fa"?"ps":"fa");setLanguage(localStorage.lang||"fa");

const modal=document.getElementById("accessModal");
document.getElementById("accessBtn").onclick=()=>{modal.classList.add("open");modal.setAttribute("aria-hidden","false")};
document.getElementById("accessClose").onclick=()=>modal.classList.remove("open");
document.getElementById("fontDown").onclick=()=>document.body.classList.add("font-large");
document.getElementById("fontUp").onclick=()=>{document.body.classList.remove("font-large");document.body.classList.add("font-xl")};
document.getElementById("fontReset").onclick=()=>document.body.classList.remove("font-large","font-xl");
document.getElementById("darkBtn").onclick=()=>document.body.classList.toggle("dark");
document.getElementById("contrastBtn").onclick=()=>document.body.classList.toggle("high-contrast");
document.getElementById("resetAccess").onclick=()=>document.body.classList.remove("dark","high-contrast","font-large","font-xl");

document.querySelectorAll(".speak").forEach(b=>b.onclick=()=>{const el=document.querySelector(b.dataset.speak);if(!el)return;const text=el.innerText.replace(/🔊/g," ");speechSynthesis.cancel();const u=new SpeechSynthesisUtterance(text);u.lang=lang==="ps"?"ps-AF":"fa-AF";u.rate=.88;speechSynthesis.speak(u)});

const canvas=document.getElementById("canvas"),ctx=canvas.getContext("2d");let drawing=false,last=null;
function pos(e){const r=canvas.getBoundingClientRect(),p=e.touches?.[0]||e;return{x:(p.clientX-r.left)*canvas.width/r.width,y:(p.clientY-r.top)*canvas.height/r.height}}
function draw(e){if(!drawing)return;const p=pos(e);ctx.beginPath();ctx.moveTo(last.x,last.y);ctx.lineTo(p.x,p.y);ctx.lineWidth=+document.getElementById("brush").value;ctx.lineCap="round";ctx.stroke();last=p;e.preventDefault()}
canvas.addEventListener("pointerdown",e=>{drawing=true;last=pos(e)});canvas.addEventListener("pointermove",draw);window.addEventListener("pointerup",()=>drawing=false);
document.getElementById("clearCanvas").onclick=()=>ctx.clearRect(0,0,canvas.width,canvas.height);

const nums=document.getElementById("numbers"),targetEl=document.getElementById("numberTarget"),msg=document.getElementById("gameMessage");
function newNumberGame(){const target=Math.floor(Math.random()*9)+1;targetEl.textContent=target;nums.innerHTML="";for(let i=1;i<=9;i++){const b=document.createElement("button");b.textContent=i;b.onclick=()=>{msg.textContent=i===target?"آفرین! درست پیدا کردی.":"دوباره تلاش کن.";if(i===target)setTimeout(newNumberGame,700)};nums.appendChild(b)}}newNumberGame();

const letters=[["آ","آب"],["ب","باد"],["پ","پرنده"],["ت","توپ"],["ج","جاده"],["د","درخت"],["ر","رود"],["س","ستاره"]];let li=0;
document.getElementById("nextLetter").onclick=()=>{li=(li+1)%letters.length;document.getElementById("letter").textContent=letters[li][0];document.getElementById("letterMeaning").textContent=`${letters[li][0]} مثل ${letters[li][1]}`};

const piano=document.getElementById("piano");[261.63,293.66,329.63,349.23,392,440,493.88].forEach((freq,i)=>{const b=document.createElement("button");b.textContent=["دو","ر","می","فا","سل","لا","سی"][i];b.onclick=()=>tone(freq);piano.appendChild(b)});
function tone(freq){const A=new AudioContext(),o=A.createOscillator(),g=A.createGain();o.frequency.value=freq;o.connect(g);g.connect(A.destination);g.gain.setValueAtTime(.18,A.currentTime);g.gain.exponentialRampToValueAtTime(.001,A.currentTime+.45);o.start();o.stop(A.currentTime+.45)}

document.getElementById("regForm").onsubmit=e=>{e.preventDefault();document.getElementById("formStatus").textContent="درخواست شما در این نسخه نمایشی ثبت شد. برای ارسال واقعی، فرم را به یک سرویس فرم یا بک‌اند متصل کنید.";e.target.reset()};

const chat=document.getElementById("chat"),body=document.getElementById("chatBody");
document.getElementById("chatFab").onclick=()=>{chat.classList.toggle("open");chat.setAttribute("aria-hidden",String(!chat.classList.contains("open")))};
document.getElementById("chatClose").onclick=()=>chat.classList.remove("open");
function botAnswer(q){q=q.toLowerCase();if(q.includes("ثبت")||q.includes("نام"))return"برای ثبت‌نام، به بخش «ثبت‌نام» بروید و نام کودک، سرپرست، شماره تماس و خدمت مورد نیاز را وارد کنید.";if(q.includes("تماس")||q.includes("شماره"))return"شماره تماس مرکز: ۰۷۸۶۸۳۸۰۰۲ و ایمیل: negineducationcenter@gmail.com است.";if(q.includes("آدرس")||q.includes("کابل"))return"مرکز در سرک ۳۷، پروژه وزیر آباد، کابل، افغانستان قرار دارد.";if(q.includes("فیزی")||q.includes("کاردرمانی")||q.includes("گفتار"))return"نگین خدمات فیزیوتراپی، کاردرمانی و گفتاردرمانی را معرفی و ارائه می‌کند؛ نیاز هر کودک باید توسط متخصص ارزیابی شود.";if(q.includes("ساعت"))return"شنبه تا چهارشنبه از ۸ صبح تا ۴ بعدازظهر و پنجشنبه از ۸ صبح تا ۱۲ ظهر.";return"من در این نسخه اطلاعات صفحات وب‌سایت نگین را پاسخ می‌دهم. درباره ثبت‌نام، خدمات، تماس، آدرس یا ساعات کاری بپرسید."}
function sendChat(){const inp=document.getElementById("chatInput"),q=inp.value.trim();if(!q)return;body.innerHTML+=`<div class="user">${q}</div><div class="bot">${botAnswer(q)}</div>`;inp.value="";body.scrollTop=body.scrollHeight}
document.getElementById("chatSend").onclick=sendChat;document.getElementById("chatInput").onkeydown=e=>{if(e.key==="Enter")sendChat()};
'''

readme = r'''# مرکز آموزشی و توانبخشی نگین — GitHub Pages

این پروژه یک وب‌سایت استاتیک و واکنش‌گرا برای «مرکز آموزشی و توانبخشی نگین» است.

## فایل‌ها
- `index.html` — ساختار کامل سایت
- `style.css` — طراحی واکنش‌گرا، Glassmorphism، حالت شب و کنتراست
- `script.js` — زبان، اسلایدر، خواندن متن، بازی‌ها، فرم و چت‌بات

## انتشار در GitHub Pages
1. یک Repository جدید در GitHub بسازید.
2. هر سه فایل را در ریشه Repository آپلود کنید.
3. از مسیر **Settings → Pages** گزینه **Deploy from a branch** را انتخاب کنید.
4. Branch را روی `main` و Folder را روی `/ (root)` بگذارید.
5. Save را بزنید.

## نکات مهم
- تصاویر اسلایدر در این نسخه از Unsplash بارگذاری می‌شوند. برای نسخه نهایی بهتر است تصاویر دارای مجوز یا تصاویر مورد تأیید مرکز را در پوشه `assets/images` قرار دهید و آدرس‌های `script.js` را با آن‌ها جایگزین کنید.
- فرم ثبت‌نام فعلاً نمایشی است و اطلاعات را به سرور ارسال نمی‌کند. برای ثبت واقعی باید به یک Backend یا سرویس فرم متصل شود.
- چت‌بات فعلاً آفلاین و مبتنی بر پاسخ‌های از پیش تعریف‌شده است. برای پاسخ‌گویی هوشمند و دقیق به پرسش‌های آزاد، باید یک API امن سمت سرور به آن متصل شود. کلید API را داخل `script.js` قرار ندهید.
- آیکن‌های شبکه‌های اجتماعی در Footer جایگاه آماده دارند و باید لینک‌های رسمی صفحات مرکز در آن‌ها قرار داده شود.
- خواندن متن با SpeechSynthesis مرورگر انجام می‌شود و پشتیبانی صدای دری/پشتو به صداهای نصب‌شده روی دستگاه وابسته است.
'''

(root/"index.html").write_text(html,encoding="utf-8")
(root/"style.css").write_text(css,encoding="utf-8")
(root/"script.js").write_text(js,encoding="utf-8")
(root/"README.md").write_text(readme,encoding="utf-8")

zip_path=Path("/mnt/data/negin-github-pages.zip")
with zipfile.ZipFile(zip_path,"w",zipfile.ZIP_DEFLATED) as z:
    for p in root.iterdir():
        z.write(p,p.name)
print(zip_path, [p.name for p in root.iterdir()])
