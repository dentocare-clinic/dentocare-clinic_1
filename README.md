<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DentoCare</title>
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap" rel="stylesheet">

    <style>
        /* الحل الجذري لإخفاء أي نص يظهر فوق الموقع */
        body > *:first-child:not(nav):not(#particles-js):not(style) { display: none !important; opacity: 0 !important; position: absolute; top: -1000px; }

        :root { --primary: #00b4d8; --secondary: #03045e; --accent: #25d366; }
        
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; }
        
        body { background-color: #f0f9ff; color: var(--secondary); overflow-x: hidden; line-height: 1.6; }

        #particles-js { position: fixed; width: 100%; height: 100%; z-index: -1; top: 0; left: 0; }

        /* تصميم عمودي للهيدر */
        nav { 
            background: white; padding: 15px; 
            display: flex; flex-direction: column; /* جعل الشعار واللغات فوق بعض */
            align-items: center; gap: 10px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1); 
        }

        .lang-switcher { display: flex; flex-wrap: wrap; justify-content: center; gap: 5px; }
        .lang-btn { cursor: pointer; border: 1px solid var(--primary); background: white; padding: 5px 8px; border-radius: 8px; font-size: 0.7rem; font-weight: bold; }

        /* تصميم عمودي للمحتوى */
        .container { 
            display: flex; flex-direction: column; /* ترتيب العناصر عمودياً */
            align-items: center; padding: 20px; text-align: center; 
        }

        h1 { font-size: 1.8rem; font-weight: 900; margin: 15px 0; }
        .status-badge { padding: 8px 20px; border-radius: 20px; font-weight: bold; margin-bottom: 20px; font-size: 0.9rem; }

        /* كرت الحجز العمودي */
        .booking-card { 
            background: white; width: 100%; max-width: 400px; padding: 25px; 
            border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.05); 
        }

        .input-group { text-align: right; margin-bottom: 15px; width: 100%; }
        label { display: block; margin-bottom: 5px; font-weight: 700; }
        input, select { width: 100%; padding: 12px; border: 1px solid #ddd; border-radius: 12px; font-size: 1rem; }

        .btn-wa { 
            background: var(--accent); color: white; width: 100%; padding: 15px; 
            border: none; border-radius: 15px; font-weight: 900; font-size: 1.1rem; 
            cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 10px;
        }

        /* جعل روابط التواصل عمودية بالكامل */
        .contacts-column { 
            display: flex; flex-direction: column; 
            gap: 15px; width: 100%; max-width: 400px; margin-top: 30px; 
        }

        .contact-item { 
            background: white; padding: 15px; border-radius: 15px; 
            display: flex; align-items: center; gap: 15px; text-decoration: none; 
            color: var(--secondary); border: 1px solid #eee;
        }
        .contact-item i { font-size: 1.4rem; color: var(--primary); }
        .contact-item div { text-align: right; }

        [lang]:not([lang="ar"]):not([lang="ur"]) .input-group, 
        [lang]:not([lang="ar"]):not([lang="ur"]) .contact-item div { text-align: left; }
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
        <div id="statusBadge" class="status-badge"></div>

        <div class="booking-card">
            <div class="input-group"><label id="l1">الاسم</label><input type="text" id="nIn"></div>
            <div class="input-group"><label id="l2">الجوال</label><input type="tel" id="pIn"></div>
            <div class="input-group">
                <label id="l3">الخدمة</label>
                <select id="sIn"><option>استشارة</option><option>تنظيف</option><option>تبييض</option></select>
            </div>
            <button class="btn-wa" onclick="sendWA()"><span id="bt">تأكيد</span> <i class="fab fa-whatsapp"></i></button>
        </div>

        <div class="contacts-column">
            <a href="https://www.instagram.com/dentocare_1/" target="_blank" class="contact-item">
                <i class="fab fa-instagram" style="color:#e1306c"></i>
                <div><h4>Instagram</h4><p>@dentocare_1</p></div>
            </a>
            <a href="mailto:dentocareclinics1@gmail.com" class="contact-item">
                <i class="fas fa-envelope"></i>
                <div><h4>Email</h4><p>dentocareclinics1@gmail.com</p></div>
            </a>
            <a href="tel:+966112043386" class="contact-item">
                <i class="fas fa-phone-alt"></i>
                <div><h4>Phone</h4><p>011 204 3386</p></div>
            </a>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script>
        particlesJS("particles-js", {"particles":{"number":{"value":50},"color":{"value":"#00b4d8"},"line_linked":{"enable":true,"opacity":0.2},"move":{"speed":1}}});

        const dict = {
            ar: {t1:"عيادات دنتوكير المتخصصة", l1:"الاسم", l2:"الجوال", l3:"الخدمة", bt:"تأكيد عبر واتساب", dir:"rtl"},
            en: {t1:"DentoCare Clinics", l1:"Name", l2:"Mobile", l3:"Service", bt:"Confirm", dir:"ltr"},
            fr: {t1:"Cliniques DentoCare", l1:"Nom", l2:"Mobile", l3:"Service", bt:"Confirmer", dir:"ltr"},
            es: {t1:"Clínicas DentoCare", l1:"Nombre", l2:"Móvil", l3:"Servicio", bt:"Confirmar", dir:"ltr"},
            it: {t1:"Cliniche DentoCare", l1:"Nome", l2:"Telefono", l3:"Servizio", bt:"Conferma", dir:"ltr"},
            pt: {t1:"Clínicas DentoCare", l1:"Nome", l2:"Telemóvel", l3:"Serviço", bt:"Confirmar", dir:"ltr"},
            ru: {t1:"Клиники DentoCare", l1:"Имя", l2:"Телефон", l3:"Услуга", bt:"Подтвердить", dir:"ltr"},
            hi: {t1:"डेंटोकेयर क्लीनिक", l1:"नाम", l2:"मोबाइल", l3:"सेवा", bt:"पुष्टि करें", dir:"ltr"},
            ur: {t1:"ڈینٹو کیئر کلینک", l1:"نام", l2:"موبائل", l3:"سروس", bt:"تصدیق کریں", dir:"rtl"}
        };

        function changeLang(l) {
            document.documentElement.lang = l;
            document.documentElement.dir = dict[l].dir;
            document.getElementById('t1').innerText = dict[l].t1;
            document.getElementById('l1').innerText = dict[l].l1;
            document.getElementById('l2').innerText = dict[l].l2;
            document.getElementById('l3').innerText = dict[l].l3;
            document.getElementById('bt').innerText = dict[l].bt;
            updateStatus();
        }

        function updateStatus() {
            const h = new Date().getHours();
            const b = document.getElementById('statusBadge');
            const isRtl = document.documentElement.dir === 'rtl';
            if(h >= 14 && h < 22) { b.style.background="#d1fae5"; b.innerText= isRtl ? "● مفتوح الآن" : "● Open Now"; }
            else { b.style.background="#fee2e2"; b.innerText= isRtl ? "● مغلق الآن" : "● Closed Now"; }
        }
        updateStatus();

        function sendWA() {
            const n = document.getElementById('nIn').value;
            const p = document.getElementById('pIn').value;
            const s = document.getElementById('sIn').value;
            if(n && p) { window.open(`https://wa.me/966560502760?text=حجز:%20${n}%20-%20${p}%20-%20${s}`, '_blank'); }
            else { alert("Fill all info"); }
        }
    </script>
</body>
</html>
