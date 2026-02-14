<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DentoCare Clinics</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        :root { --primary: #00b4d8; --secondary: #03045e; --accent: #25d366; }
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; }
        body { background-color: #f0f9ff; color: var(--secondary); overflow-x: hidden; text-align: center; }
        #particles-js { position: fixed; width: 100%; height: 100%; z-index: -1; top: 0; left: 0; }
        nav { background: white; padding: 10px 5%; display: flex; justify-content: space-between; align-items: center; position: sticky; top: 0; z-index: 1000; box-shadow: 0 2px 10px rgba(0,0,0,0.1); }
        .lang-switcher { display: flex; gap: 4px; flex-wrap: wrap; justify-content: flex-end; }
        .lang-btn { cursor: pointer; border: 1px solid var(--primary); background: white; padding: 4px 6px; border-radius: 6px; font-size: 0.7rem; font-weight: bold; color: var(--primary); }
        .container { padding: 20px; display: flex; flex-direction: column; align-items: center; }
        .booking-card { background: white; width: 100%; max-width: 450px; padding: 25px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.05); margin-top: 20px; }
        .input-group { text-align: right; margin-bottom: 15px; width: 100%; }
        label { display: block; margin-bottom: 5px; font-weight: 700; font-size: 0.9rem; }
        input, select { width: 100%; padding: 12px; border: 1px solid #eef2f3; border-radius: 12px; font-size: 1rem; appearance: none; background: #fff; }
        .btn-wa { background: var(--accent); color: white; width: 100%; padding: 15px; border: none; border-radius: 12px; font-weight: 900; font-size: 1.1rem; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 10px; }
        .contacts-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; max-width: 900px; margin: 30px auto; width: 100%; }
        .contact-item { background: white; padding: 15px; border-radius: 15px; display: flex; align-items: center; gap: 12px; text-decoration: none; color: var(--secondary); border: 1px solid #f0f0f0; }
        .contact-item div { text-align: right; }
        [lang]:not([lang="ar"]):not([lang="ur"]) .input-group, [lang]:not([lang="ar"]):not([lang="ur"]) .contact-item div { text-align: left; }
    </style>
</head>
<body>
    <div id="particles-js"></div>
    <nav>
        <div style="font-weight: 900; font-size: 1.3rem; color: var(--primary);">DentoCare <i class="fas fa-tooth"></i></div>
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
        <div id="statusBadge" style="padding: 5px 15px; border-radius: 20px; font-weight: bold; font-size: 0.8rem; margin-bottom: 10px;"></div>

        <div class="booking-card">
            <div class="input-group"><label id="l1">الاسم الكامل</label><input type="text" id="nameIn" placeholder="..."></div>
            <div class="input-group"><label id="l2">رقم الجوال</label><input type="tel" id="phoneIn" placeholder="05xxxxxxxx"></div>
            <div class="input-group">
                <label id="l3">الخدمة</label>
                <select id="servIn">
                    <option id="opt1">استشارة عامة</option>
                    <option id="opt2">تنظيف وتلميع</option>
                    <option id="opt3">تبييض أسنان</option>
                </select>
            </div>
            <button class="btn-wa" onclick="sendWA()"><span id="bt">تأكيد عبر واتساب</span> <i class="fab fa-whatsapp"></i></button>
        </div>

        <div class="contacts-grid">
            <a href="https://www.instagram.com/dentocare_1/" target="_blank" class="contact-item"><i class="fab fa-instagram" style="color:#e1306c; font-size:1.5rem;"></i><div><h4>Instagram</h4><p>@dentocare_1</p></div></a>
            <a href="mailto:dentocareclinics1@gmail.com" class="contact-item"><i class="fas fa-envelope" style="color:var(--primary); font-size:1.5rem;"></i><div><h4>Email</h4><p>dentocareclinics1@gmail.com</p></div></a>
            <a href="tel:+966112043386" class="contact-item"><i class="fas fa-phone-alt" style="color:var(--primary); font-size:1.5rem;"></i><div><h4>Phone</h4><p>011 204 3386</p></div></a>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script>
        particlesJS("particles-js", {"particles":{"number":{"value":40},"color":{"value":"#00b4d8"},"line_linked":{"enable":true,"opacity":0.1},"move":{"speed":1}}});

        const dict = {
            ar: {t1:"عيادات دنتوكير المتخصصة", l1:"الاسم الكامل", l2:"رقم الجوال", l3:"الخدمة", bt:"تأكيد عبر واتساب", o1:"استشارة عامة", o2:"تنظيف وتلميع", o3:"تبييض أسنان", dir:"rtl"},
            en: {t1:"DentoCare Specialized Clinics", l1:"Full Name", l2:"Phone Number", l3:"Service", bt:"Confirm via WhatsApp", o1:"General Consultation", o2:"Cleaning & Polishing", o3:"Teeth Whitening", dir:"ltr"},
            fr: {t1:"Cliniques DentoCare", l1:"Nom Complet", l2:"Mobile", l3:"Service", bt:"Confirmer", o1:"Consultation Générale", o2:"Nettoyage & Polissage", o3:"Blanchiment", dir:"ltr"},
            es: {t1:"Clínicas DentoCare", l1:"Nombre", l2:"Teléfono", l3:"Servicio", bt:"Confirmar", o1:"Consulta General", o2:"Limpieza", o3:"Blanqueamiento", dir:"ltr"},
            it: {t1:"Cliniche DentoCare", l1:"Nome", l2:"Telefono", l3:"Servizio", bt:"Conferma", o1:"Consultazione", o2:"Pulizia", o3:"Sbiancamento", dir:"ltr"},
            pt: {t1:"Clínicas DentoCare", l1:"Nome", l2:"Telemóvel", l3:"Serviço", bt:"Confirmar", o1:"Consulta Geral", o2:"Limpeza", o3:"Branqueamento", dir:"ltr"},
            ru: {t1:"Клиники DentoCare", l1:"Имя", l2:"Телефон", l3:"Услуга", bt:"Подтвердить", o1:"Консультация", o2:"Чистка", o3:"Отбеливание", dir:"ltr"},
            hi: {t1:"डेंटोकेयर क्लीनिक", l1:"नाम", l2:"फोन", l3:"सेवा", bt:"पुष्टि करें", o1:"परामर्श", o2:"सफाई", o3:"सफेद करना", dir:"ltr"},
            ur: {t1:"ڈینٹو کیئر کلینک", l1:"نام", l2:"موبائل", l3:"سروس", bt:"تصدیق کریں", o1:"مشورہ", o2:"صفائی", o3:"سفیدی", dir:"rtl"}
        };

        function changeLang(l) {
            document.documentElement.lang = l;
            document.documentElement.dir = dict[l].dir;
            document.getElementById('t1').innerText = dict[l].t1;
            document.getElementById('l1').innerText = dict[l].l1;
            document.getElementById('l2').innerText = dict[l].l2;
            document.getElementById('l3').innerText = dict[l].l3;
            document.getElementById('bt').innerText = dict[l].bt;
            document.getElementById('opt1').innerText = dict[l].o1;
            document.getElementById('opt2').innerText = dict[l].o2;
            document.getElementById('opt3').innerText = dict[l].o3;
            updateStatus();
        }

        function updateStatus() {
            const h = new Date().getHours();
            const b = document.getElementById('statusBadge');
            const isAr = document.documentElement.dir === 'rtl';
            if(h >= 14 && h < 22) { b.style.background="#d1fae5"; b.style.color="#065f46"; b.innerText= isAr ? "● مفتوح الآن" : "● Open Now"; }
            else { b.style.background="#fee2e2"; b.style.color="#991b1b"; b.innerText= isAr ? "● مغلق الآن" : "● Closed Now"; }
        }
        updateStatus();

        function sendWA() {
            const n = document.getElementById('nameIn').value, p = document.getElementById('phoneIn').value, s = document.getElementById('servIn').value;
            if(n && p) {
                window.open(`https://wa.me/966560502760?text=${encodeURIComponent('حجز جديد:\nالاسم: '+n+'\nالجوال: '+p+'\nالخدمة: '+s)}`, '_blank');
            } else { alert(document.documentElement.dir === 'rtl' ? "يرجى ملء البيانات" : "Please fill fields"); }
        }
    </script>
</body>
</html>
