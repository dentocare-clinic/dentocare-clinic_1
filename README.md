<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DentoCare | عيادات دنتوكير المتخصصة</title>
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap" rel="stylesheet">
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">

    <style>
        :root { 
            --primary: #00b4d8; 
            --secondary: #03045e; 
            --accent: #25d366;
            --glass: rgba(255, 255, 255, 0.8);
        }

        /* منع ظهور أي نص تائه في الأعلى */
        html { visibility: visible; } 

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; transition: 0.3s ease; }
        
        body { background-color: #f0f9ff; color: var(--secondary); overflow-x: hidden; min-height: 100vh; }
        
        /* الخلفية المتحركة */
        #particles-js { position: fixed; width: 100%; height: 100%; z-index: -1; top: 0; left: 0; }

        /* الهيدر الزجاجي العصري */
        nav { 
            background: var(--glass); 
            backdrop-filter: blur(15px); 
            -webkit-backdrop-filter: blur(15px);
            padding: 10px 5%; 
            display: flex; 
            justify-content: space-between; 
            align-items: center; 
            position: sticky; 
            top: 0; 
            z-index: 1000; 
            box-shadow: 0 4px 20px rgba(0,0,0,0.05); 
        }

        .logo { font-weight: 900; font-size: 1.4rem; color: var(--primary); text-decoration: none; display: flex; align-items: center; gap: 8px; }
        
        /* حاوية اللغات - متجاوبة */
        .lang-switcher { display: flex; gap: 5px; flex-wrap: wrap; max-width: 60%; justify-content: flex-end; }
        .lang-btn { cursor: pointer; border: 1px solid var(--primary); background: white; padding: 4px 8px; border-radius: 8px; font-size: 0.7rem; font-weight: bold; color: var(--primary); }
        .lang-btn:hover { background: var(--primary); color: white; }

        .container { padding: 30px 5%; text-align: center; }
        
        /* النجوم والتقييم */
        .rating { color: #f1c40f; margin-bottom: 10px; font-size: 0.9rem; }

        h1 { font-size: 2.2rem; font-weight: 900; margin-bottom: 10px; color: var(--secondary); }
        .subtitle { color: #666; font-size: 1.1rem; margin-bottom: 20px; }

        /* حالة العيادة */
        .status-badge { display: inline-block; padding: 6px 15px; border-radius: 20px; font-weight: bold; font-size: 0.85rem; margin-bottom: 25px; box-shadow: 0 4px 10px rgba(0,0,0,0.05); }

        /* كرت الحجز المطوّر */
        .booking-card { 
            background: white; max-width: 500px; margin: auto; padding: 30px; 
            border-radius: 25px; box-shadow: 0 20px 40px rgba(0,0,0,0.08); 
            border: 1px solid rgba(0, 180, 216, 0.1); 
        }

        .input-group { text-align: right; margin-bottom: 15px; }
        label { display: block; margin-bottom: 6px; font-weight: 700; font-size: 0.9rem; color: var(--secondary); }
        input, select { width: 100%; padding: 12px; border: 1.5px solid #eef2f3; border-radius: 12px; font-size: 1rem; outline: none; }
        input:focus { border-color: var(--primary); }

        .btn-wa { 
            background: var(--accent); color: white; width: 100%; padding: 16px; 
            border: none; border-radius: 15px; font-weight: 900; font-size: 1.2rem; 
            cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 10px;
            box-shadow: 0 10px 20px rgba(37, 211, 102, 0.2); margin-top: 10px;
        }

        /* المميزات العصرية (FAB) */
        .fab-container { position: fixed; bottom: 25px; right: 25px; z-index: 1000; }
        .fab-main { width: 60px; height: 60px; border-radius: 50%; background: var(--primary); color: white; border: none; font-size: 24px; cursor: pointer; box-shadow: 0 10px 20px rgba(0,0,0,0.2); }
        .fab-menu { display: none; flex-direction: column; gap: 10px; position: absolute; bottom: 75px; right: 5px; }
        .fab-item { width: 50px; height: 50px; border-radius: 50%; display: flex; justify-content: center; align-items: center; color: white; text-decoration: none; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }

        /* شبكة التواصل */
        .contacts-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 15px; max-width: 1000px; margin: 40px auto; }
        .contact-item { background: white; padding: 20px; border-radius: 20px; display: flex; align-items: center; gap: 15px; text-decoration: none; color: var(--secondary); border: 1px solid #f0f0f0; box-shadow: 0 5px 15px rgba(0,0,0,0.03); }
        .contact-item:hover { transform: translateY(-5px); border-color: var(--primary); }
        .contact-item i { font-size: 1.5rem; color: var(--primary); }
        .contact-item div { text-align: right; }
        .contact-item h4 { font-size: 0.75rem; color: #888; margin-bottom: 2px; }
        .contact-item p { font-weight: 700; font-size: 0.95rem; }

        /* تعديلات الاتجاه للغات الأجنبية */
        [lang]:not([lang="ar"]):not([lang="ur"]) body { text-align: left; }
        [lang]:not([lang="ar"]):not([lang="ur"]) .input-group, 
        [lang]:not([lang="ar"]):not([lang="ur"]) .contact-item div { text-align: left; }

        #topBtn { display: none; position: fixed; bottom: 25px; left: 25px; background: white; color: var(--primary); width: 50px; height: 50px; border-radius: 50%; border: 1px solid var(--primary); cursor: pointer; z-index: 1000; font-size: 20px; }
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
        <div class="rating" data-aos="fade-down">
            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
            <span id="ratingText"> (4.9/5 تقييم مراجعينا)</span>
        </div>

        <h1 id="t1">عيادات دنتوكير المتخصصة</h1>
        <p id="t2" class="subtitle">نخبة من الاستشاريين السعوديين بجميع التخصصات</p>
        
        <div id="statusBadge" class="status-badge"></div>

        <div class="booking-card" data-aos="zoom-in">
            <h2 id="tBook" style="margin-bottom: 20px;">حجز موعد</h2>
            <div class="input-group">
                <label id="l1">الاسم الكامل</label>
                <input type="text" id="nameIn" placeholder="...">
            </div>
            <div class="input-group">
                <label id="l2">رقم الجوال</label>
                <input type="tel" id="phoneIn" placeholder="05xxxxxxxx">
            </div>
            <div class="input-group">
                <label id="l3">الخدمة المطلوبة</label>
                <select id="servIn">
                    <option id="opt1">استشارة عامة</option>
                    <option id="opt2">تنظيف وتلميع</option>
                    <option id="opt3">تبييض أسنان</option>
                </select>
            </div>
            <button class="btn-wa" onclick="sendWA()">
                <span id="btnText">تأكيد عبر واتساب</span> <i class="fab fa-whatsapp"></i>
            </button>
        </div>

        <div class="contacts-grid">
            <a href="https://www.google.com/maps/search/?api=1&query=DentoCare+Riyadh" target="_blank" class="contact-item">
                <i class="fas fa-map-marker-alt"></i>
                <div><h4 id="ct1">موقعنا</h4><p id="ct1sub">الرياض - حي العارض</p></div>
            </a>
            <a href="https://www.instagram.com/dentocare_1/" target="_blank" class="contact-item">
                <i class="fab fa-instagram" style="color: #e1306c;"></i>
                <div><h4>Instagram</h4><p>@dentocare_1</p></div>
            </a>
            <a href="mailto:dentocareclinics1@gmail.com" class="contact-item">
                <i class="fas fa-envelope"></i>
                <div><h4 id="ct2">البريد الإلكتروني</h4><p>dentocareclinics1@gmail.com</p></div>
            </a>
            <a href="tel:+966112043386" class="contact-item">
                <i class="fas fa-phone-alt"></i>
                <div><h4 id="ct3">الهاتف الثابت</h4><p>011 204 3386</p></div>
            </a>
        </div>
    </div>

    <div class="fab-container">
        <div class="fab-menu" id="fabMenu">
            <a href="tel:+966112043386" class="fab-item" style="background:#3498db;"><i class="fas fa-phone"></i></a>
            <a href="https://wa.me/966560502760" class="fab-item" style="background:#25d366;"><i class="fab fa-whatsapp"></i></a>
        </div>
        <button class="fab-main" onclick="toggleFab()"><i class="fas fa-plus" id="fabIcon"></i></button>
    </div>

    <button id="topBtn" onclick="window.scrollTo(0,0)"><i class="fas fa-arrow-up"></i></button>

    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init();

        // 1. الخلفية
        particlesJS("particles-js", {"particles":{"number":{"value":60},"color":{"value":"#00b4d8"},"line_linked":{"enable":true,"opacity":0.2},"move":{"speed":1}}});

        // 2. القاموس الضخم (9 لغات)
        const dict = {
            ar: {t1:"عيادات دنتوكير المتخصصة", t2:"نخبة من الاستشاريين السعوديين", tb:"حجز موعد", l1:"الاسم الكامل", l2:"رقم الجوال", l3:"الخدمة المطلوبة", bt:"تأكيد عبر واتساب", r:"(4.9/5 تقييم مراجعينا)", c1:"موقعنا", c1s:"الرياض - حي العارض", c2:"البريد الإلكتروني", c3:"الهاتف", dir:"rtl"},
            en: {t1:"DentoCare Specialized Clinics", t2:"Elite Saudi Consultants", tb:"Book Appointment", l1:"Full Name", l2:"Phone Number", l3:"Service Type", bt:"Confirm via WhatsApp", r:"(4.9/5 Our Rating)", c1:"Location", c1s:"Riyadh - Al Arid", c2:"Email", c3:"Phone", dir:"ltr"},
            fr: {t1:"Cliniques DentoCare", t2:"Consultants Saoudiens d'élite", tb:"Prendre RDV", l1:"Nom Complet", l2:"Téléphone", l3:"Service", bt:"Confirmer sur WhatsApp", r:"(4.9/5 Note)", c1:"Emplacement", c1s:"Riyad", c2:"E-mail", c3:"Fixe", dir:"ltr"},
            es: {t1:"Clínicas DentoCare", t2:"Consultores saudíes de élite", tb:"Reservar cita", l1:"Nombre completo", l2:"Teléfono", l3:"Servicio", bt:"Confirmar por WhatsApp", r:"(4.9/5 Calificación)", c1:"Ubicación", c1s:"Riad", c2:"Correo", c3:"Teléfono", dir:"ltr"},
            it: {t1:"Cliniche DentoCare", t2:"Consulenti sauditi d'élite", tb:"Prenota", l1:"Nome completo", l2:"Telefono", l3:"Servizio", bt:"Conferma via WhatsApp", r:"(4.9/5 Voto)", c1:"Posizione", c1s:"Riad", c2:"Email", c3:"Telefono", dir:"ltr"},
            pt: {t1:"Clínicas DentoCare", t2:"Consultores sauditas de elite", tb:"Marcar Consulta", l1:"Nome completo", l2:"Telemóvel", l3:"Serviço", bt:"Confirmar no WhatsApp", r:"(4.9/5 Nota)", c1:"Localização", c1s:"Riade", c2:"E-mail", c3:"Telefone", dir:"ltr"},
            ru: {t1:"Клиники DentoCare", t2:"Элитные специалисты", tb:"Запись на прием", l1:"Полное имя", l2:"Телефон", l3:"Услуга", bt:"Подтвердить в WhatsApp", r:"(4.9/5 Рейтинг)", c1:"Локация", c1s:"Эр-Рияд", c2:"Почта", c3:"Телефон", dir:"ltr"},
            hi: {t1:"डेंटोकेयर स्पेशलाइज्ड क्लीनिक", t2:"एलीट सऊदी सलाहकार", tb:"अपॉइंटमेंट लें", l1:"पूरा नाम", l2:"फोन नंबर", l3:"सेवा प्रकार", bt:"व्हाट्सएप से पुष्टि करें", r:"(4.9/5 रेटिंग)", c1:"स्थान", c1s:"रियाद", c2:"ईमेल", c3:"फोन", dir:"ltr"},
            ur: {t1:"ڈینٹو کیئر اسپیشلائزڈ کلینک", t2:"ایلیٹ سعودی کنسلٹنٹس", tb:"بکنگ کریں", l1:"پورا نام", l2:"فون نمبر", l3:"سروس کی قسم", bt:"واٹس ایپ سے تصدیق کریں", r:"(4.9/5 ریٹنگ)", c1:"مقام", c1s:"ریاض", c2:"ای میل", c3:"فون", dir:"rtl"}
        };

        function changeLang(l) {
            document.documentElement.lang = l;
            document.documentElement.dir = dict[l].dir;
            document.getElementById('t1').innerText = dict[l].t1;
            document.getElementById('t2').innerText = dict[l].t2;
            document.getElementById('tBook').innerText = dict[l].tb;
            document.getElementById('l1').innerText = dict[l].l1;
            document.getElementById('l2').innerText = dict[l].l2;
            document.getElementById('l3').innerText = dict[l].l3;
            document.getElementById('btnText').innerText = dict[l].bt;
            document.getElementById('ratingText').innerText = dict[l].r;
            document.getElementById('ct1').innerText = dict[l].c1;
            document.getElementById('ct1sub').innerText = dict[l].c1s;
            document.getElementById('ct2').innerText = dict[l].c2;
            document.getElementById('ct3').innerText = dict[l].c3;
            updateStatus();
        }

        // 3. حالة العيادة
        function updateStatus() {
            const h = new Date().getHours();
            const b = document.getElementById('statusBadge');
            const isAr = document.documentElement.lang === 'ar' || document.documentElement.lang === 'ur';
            if(h >= 14 && h < 22) {
                b.style.background = "#d1fae5"; b.style.color = "#065f46";
                b.innerText = isAr ? "● مفتوح الآن - نستقبلكم" : "● Open Now - Welcoming You";
            } else {
                b.style.background = "#fee2e2"; b.style.color = "#991b1b";
                b.innerText = isAr ? "● مغلق حالياً" : "● Closed Now";
            }
        }
        updateStatus();

        // 4. FAB & Scroll
        function toggleFab() {
            const m = document.getElementById('fabMenu');
            const i = document.getElementById('fabIcon');
            m.style.display = m.style.display === 'flex' ? 'none' : 'flex';
            i.style.transform = m.style.display === 'flex' ? 'rotate(45deg)' : 'rotate(0deg)';
        }

        window.onscroll = function() {
            document.getElementById('topBtn').style.display = window.scrollY > 400 ? 'block' : 'none';
        };

        // 5. إرسال الواتساب
        function sendWA() {
            const n = document.getElementById('nameIn').value;
            const p = document.getElementById('phoneIn').value;
            const s = document.getElementById('servIn').value;
            if(n && p) {
                window.open(`https://wa.me/966560502760?text=حجز جديد من الموقع:%0Aالاسم: ${n}%0Aالجوال: ${p}%0Aالخدمة: ${s}`, '_blank');
            } else {
                alert(document.documentElement.dir === 'rtl' ? "يرجى ملء البيانات" : "Please fill all fields");
            }
        }
    </script>
</body>
</html>
