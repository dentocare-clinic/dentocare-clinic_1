<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DentoCare Specialized Clinics</title>
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap" rel="stylesheet">

    <style>
        /* إخفاء أي نص تائه يظهر في أعلى الصفحة */
        html { visibility: visible; }
        body > *:first-child:not(nav):not(#particles-js):not(style):not(script) { display: none !important; }

        :root { --primary: #00b4d8; --secondary: #03045e; --accent: #25d366; }
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; transition: 0.3s ease; }
        
        body { background-color: #f0f9ff; color: var(--secondary); overflow-x: hidden; }
        #particles-js { position: fixed; width: 100%; height: 100%; z-index: -1; top: 0; left: 0; }
        
        /* الهيدر بالعرض */
        nav { 
            background: rgba(255, 255, 255, 0.9); 
            backdrop-filter: blur(10px); 
            padding: 10px 5%; 
            display: flex; 
            justify-content: space-between; 
            align-items: center; 
            position: sticky; top: 0; z-index: 1000; 
            box-shadow: 0 2px 15px rgba(0,0,0,0.05); 
        }

        .logo { font-weight: 900; font-size: 1.5rem; color: var(--primary); text-decoration: none; display: flex; align-items: center; gap: 8px; }
        .lang-switcher { display: flex; gap: 5px; flex-wrap: wrap; justify-content: flex-end; max-width: 60%; }
        .lang-btn { cursor: pointer; border: 1px solid var(--primary); background: white; padding: 4px 8px; border-radius: 6px; font-size: 0.75rem; font-weight: bold; color: var(--primary); }

        .container { padding: 40px 5%; text-align: center; }
        h1 { font-size: 2.2rem; font-weight: 900; margin-bottom: 10px; }
        .status-badge { display: inline-block; padding: 6px 15px; border-radius: 20px; font-weight: bold; margin-bottom: 30px; }

        /* كرت الحجز بالعرض */
        .booking-card { 
            background: white; max-width: 600px; margin: auto; padding: 30px; 
            border-radius: 25px; box-shadow: 0 15px 35px rgba(0,0,0,0.07); 
        }

        .input-group { text-align: right; margin-bottom: 15px; }
        label { display: block; margin-bottom: 5px; font-weight: 700; }
        input, select { width: 100%; padding: 12px; border: 1px solid #eef2f3; border-radius: 12px; font-size: 1rem; background: #fafafa; }

        .btn-wa { 
            background: var(--accent); color: white; width: 100%; padding: 16px; 
            border: none; border-radius: 15px; font-weight: 900; font-size: 1.2rem; 
            cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 10px;
        }

        /* روابط التواصل بالعرض (Grid) */
        .contacts-grid { 
            display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); 
            gap: 20px; max-width: 1000px; margin: 40px auto; 
        }

        .contact-item { 
            background: white; padding: 20px; border-radius: 20px; 
            display: flex; align-items: center; gap: 15px; text-decoration: none; 
            color: var(--secondary); border: 1px solid #f0f0f0; 
        }
        .contact-item i { font-size: 1.6rem; color: var(--primary); }
        .contact-item div { text-align: right; }

        /* قلب الاتجاه للغات الأجنبية */
        [lang]:not([lang="ar"]):not([lang="ur"]) body, 
        [lang]:not([lang="ar"]):not([lang="ur"]) .input-group,
        [lang]:not([lang="ar"]):not([lang="ur"]) .contact-item div { text-align: left; }
    </style>
</head>
<body>

    <div id="particles-js"></div>

    <nav>
        <a href="#" class="logo">DentoCare <i class="fas fa-tooth"></i></a>
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
            <div class="input-group"><label id="l1">الاسم الكامل</label><input type="text" id="nIn"></div>
            <div class="input-group"><label id="l2">رقم الجوال</label><input type="tel" id="pIn"></div>
            <div class="input-group">
                <label id="l3">الخدمة</label>
                <select id="sIn"><option>استشارة</option><option>تنظيف</option><option>تبييض</option></select>
            </div>
            <button class="btn-wa" onclick="sendWA()"><span id="bt">تأكيد عبر واتساب</span> <i class="fab fa-whatsapp"></i></button>
        </div>

        <div class="contacts-grid">
            <a href="https://www.instagram.com/dentocare_1/" target="_blank" class="contact-item">
                <i class="fab fa-instagram" style="color: #e1306c;"></i>
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
        particlesJS("particles-js", {"particles":{"number":{"value":50},"color":{"value":"#00b4d8"},"line_linked":{"enable":true,"opacity":0.2},"move":{"speed":1.2}}});

        const dict = {
            ar: {t1:"عيادات دنتوكير المتخصصة", l1:"الاسم الكامل", l2:"رقم الجوال", l3:"الخدمة", bt:"تأكيد عبر واتساب", dir:"rtl"},
            en: {t1:"DentoCare Specialized Clinics", l1:"Full Name", l2:"Mobile Number", l3:"Service", bt:"Confirm via WhatsApp", dir:"ltr"},
            fr: {t1:"Cliniques DentoCare", l1:"Nom Complet", l2:"Mobile", l3:"Service", bt:"Confirmer", dir:"ltr"},
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
            if(h >= 14 && h < 22) { b.style.background="#d1fae5"; b.style.color="#065f46"; b.innerText= isRtl ? "● مفتوح الآن" : "● Open Now"; }
            else { b.style.background="#fee2e2"; b.style.color="#991b1b"; b.innerText= isRtl ? "● مغلق الآن" : "● Closed Now"; }
        }
        updateStatus();

        function sendWA() {
            const n = document.getElementById('nIn').value;
            const p = document.getElementById('pIn').value;
            const s = document.getElementById('sIn').value;
            if(n && p) {
                const msg = encodeURIComponent(`حجز جديد:\nالاسم: ${n}\nالجوال: ${p}\nالخدمة: ${s}`);
                window.open(`https://wa.me/966560502760?text=${msg}`, '_blank');
            } else {
                alert(document.documentElement.dir === 'rtl' ? "يرجى ملء البيانات" : "Please fill all fields");
            }
        }
    </script>
</body>
</html>
