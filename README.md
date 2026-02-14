<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DentoCare</title>
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap" rel="stylesheet">

    <style>
        /* إخفاء أي نصوص زائدة خارج الكود */
        html { visibility: visible; }
        body > div:first-of-type:not(#particles-js):not(.container) { display: none !important; }

        :root { --primary: #00b4d8; --secondary: #03045e; --accent: #25d366; }
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; }
        body { background-color: #f0f9ff; color: var(--secondary); overflow-x: hidden; text-align: center; }
        #particles-js { position: fixed; width: 100%; height: 100%; z-index: -1; top: 0; left: 0; }
        
        nav { background: white; padding: 15px; display: flex; flex-direction: column; align-items: center; gap: 10px; box-shadow: 0 2px 10px rgba(0,0,0,0.1); position: sticky; top: 0; z-index: 1000; }
        .lang-switcher { display: flex; flex-wrap: wrap; justify-content: center; gap: 5px; }
        .lang-btn { cursor: pointer; border: 1px solid var(--primary); background: white; padding: 5px 8px; border-radius: 8px; font-size: 0.7rem; font-weight: bold; color: var(--primary); }

        .container { padding: 20px; display: flex; flex-direction: column; align-items: center; }
        .booking-card { background: white; width: 100%; max-width: 400px; padding: 25px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.05); margin-top: 20px; }
        
        .input-group { text-align: right; margin-bottom: 15px; width: 100%; }
        label { display: block; margin-bottom: 5px; font-weight: 700; }
        input, select { width: 100%; padding: 12px; border: 1px solid #ddd; border-radius: 12px; font-size: 1rem; }
        
        .btn-wa { background: var(--accent); color: white; width: 100%; padding: 15px; border: none; border-radius: 15px; font-weight: 900; font-size: 1.1rem; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 10px; }

        .contacts-column { display: flex; flex-direction: column; gap: 12px; width: 100%; max-width: 400px; margin-top: 25px; }
        .contact-item { background: white; padding: 15px; border-radius: 15px; display: flex; align-items: center; gap: 15px; text-decoration: none; color: var(--secondary); border: 1px solid #eee; }
        .contact-item i { font-size: 1.4rem; color: var(--primary); }
        .contact-item div { text-align: right; }

        [lang]:not([lang="ar"]):not([lang="ur"]) .input-group, [lang]:not([lang="ar"]):not([lang="ur"]) .contact-item div { text-align: left; }
    </style>
</head>
<body>
    <div id="particles-js"></div>
    <nav>
        <div style="font-weight: 900; font-size: 1.5rem; color: var(--primary);">DentoCare <i class="fas fa-tooth"></i></div>
        <div class="lang-switcher">
            <button class="lang-btn" onclick="changeLang('ar')">🇸🇦 AR</button>
            <button class="lang-btn" onclick="changeLang('en')">🇺🇸 EN</button>
            <button class="lang-btn" onclick="changeLang('fr')">🇫🇷 FR</button>
            <button class="lang-btn" onclick="changeLang('es')">🇪🇸 ES</button>
            <button class="lang-btn" onclick="changeLang('it')">🇮🇹 IT</button>
            <button class="lang-btn" onclick="changeLang('pt')">🇵🇹 PT</button>
            <button class="lang-btn" onclick="changeLang('ru')">🇷🇺 RU</button>
            <button class="lang-btn" onclick="changeLang('hi')">🇮🇳 HI</button>
            <button class="lang-btn" onclick="changeLang('ur')">🇵🇰 UR</button>
        </div>
    </nav>

    <div class="container">
        <h1 id="t1">عيادات دنتوكير المتخصصة</h1>
        <div id="statusBadge" style="padding: 8px 20px; border-radius: 20px; font-weight: bold; margin: 10px 0; font-size: 0.9rem;"></div>

        <div class="booking-card">
            <div class="input-group"><label id="l1">الاسم الكامل</label><input type="text" id="nameInput" placeholder="..."></div>
            <div class="input-group"><label id="l2">رقم الجوال</label><input type="tel" id="phoneInput" placeholder="05xxxxxxxx"></div>
            <div class="input-group">
                <label id="l3">الخدمة</label>
                <select id="serviceInput"><option>استشارة</option><option>تنظيف</option><option>تبييض</option></select>
            </div>
            <button class="btn-wa" onclick="sendToWhatsApp()"><span id="btText">تأكيد الحجز</span> <i class="fab fa-whatsapp"></i></button>
        </div>

        <div class="contacts-column">
            <a href="https://www.instagram.com/dentocare_1/" target="_blank" class="contact-item"><i class="fab fa-instagram" style="color:#e1306c"></i><div><h4>Instagram</h4><p>@dentocare_1</p></div></a>
            <a href="mailto:dentocareclinics1@gmail.com" class="contact-item"><i class="fas fa-envelope"></i><div><h4>Email</h4><p>dentocareclinics1@gmail.com</p></div></a>
            <a href="tel:+966112043386" class="contact-item"><i class="fas fa-phone-alt"></i><div><h4>Phone</h4><p>011 204 3386</p></div></a>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script>
        particlesJS("particles-js", {"particles":{"number":{"value":40},"color":{"value":"#00b4d8"},"line_linked":{"enable":true,"opacity":0.1},"move":{"speed":1}}});

        const translations = {
            ar: {t1:"عيادات دنتوكير المتخصصة", l1:"الاسم الكامل", l2:"رقم الجوال", l3:"الخدمة", bt:"تأكيد الحجز", dir:"rtl"},
            en: {t1:"DentoCare Clinics", l1:"Full Name", l2:"Mobile Number", l3:"Service", bt:"Confirm Booking", dir:"ltr"},
            fr: {t1:"Cliniques DentoCare", l1:"Nom Complet", l2:"Mobile", l3:"Service", bt:"Confirmer", dir:"ltr"},
            es: {t1:"Clínicas DentoCare", l1:"Nombre", l2:"Móvil", l3:"Servicio", bt:"Confirmar", dir:"ltr"},
            it: {t1:"Cliniche DentoCare", l1:"Nome", l2:"Telefono", l3:"Servizio", bt:"Conferma", dir:"ltr"},
            pt: {t1:"Clínicas DentoCare", l1:"Nome", l2:"Telemóvel", l3:"Serviço", bt:"Confirmar", dir:"ltr"},
            ru: {t1:"Клиники DentoCare", l1:"Имя", l2:"Телефон", l3:"Услуга", bt:"Подтвердить", dir:"ltr"},
            hi: {t1:"डेंटोकेयर क्लीनिक", l1:"नाम", l2:"मोबाइल", l3:"सेवा", bt:"पुष्टि करें", dir:"ltr"},
            ur: {t1:"ڈینٹو کیئر کلینک", l1:"نام", l2:"موبائل", l3:"سروس", bt:"تصدیق کریں", dir:"rtl"}
        };

        function changeLang(lang) {
            document.documentElement.lang = lang;
            document.documentElement.dir = translations[lang].dir;
            document.getElementById('t1').innerText = translations[lang].t1;
            document.getElementById('l1').innerText = translations[lang].l1;
            document.getElementById('l2').innerText = translations[lang].l2;
            document.getElementById('l3').innerText = translations[lang].l3;
            document.getElementById('btText').innerText = translations[lang].bt;
            updateClinicStatus();
        }

        function updateClinicStatus() {
            const hour = new Date().getHours();
            const badge = document.getElementById('statusBadge');
            const isRtl = document.documentElement.dir === 'rtl';
            if(hour >= 14 && hour < 22) { badge.style.background="#d1fae5"; badge.innerText= isRtl ? "● مفتوح الآن" : "● Open Now"; }
            else { badge.style.background="#fee2e2"; badge.innerText= isRtl ? "● مغلق الآن" : "● Closed Now"; }
        }
        updateClinicStatus();

        function sendToWhatsApp() {
            const name = document.getElementById('nameInput').value;
            const phone = document.getElementById('phoneInput').value;
            const service = document.getElementById('serviceInput').value;
            if(name && phone) {
                const message = encodeURIComponent(`حجز جديد من الموقع:\nالاسم: ${name}\nالجوال: ${phone}\nالخدمة: ${service}`);
                window.open(`https://api.whatsapp.com/send?phone=966560502760&text=${message}`, '_blank');
            } else {
                alert(document.documentElement.dir === 'rtl' ? "يرجى كتابة الاسم ورقم الجوال" : "Please enter name and phone");
            }
        }
    </script>
</body>
</html>
