<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DentoCare | عيادات دنتوكير</title>
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap" rel="stylesheet">

    <style>
        :root { --primary: #00b4d8; --secondary: #03045e; }
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; }
        body { background: linear-gradient(135deg, #f0f9ff 0%, #cbebff 100%); color: var(--secondary); min-height: 100vh; text-align: center; }
        nav { background: white; padding: 10px 5%; display: flex; justify-content: space-between; align-items: center; box-shadow: 0 2px 10px rgba(0,0,0,0.05); }
        .logo { font-weight: 900; font-size: 1.4rem; color: var(--primary); display: flex; align-items: center; gap: 5px; }
        .booking-card { background: white; max-width: 450px; margin: 40px auto; padding: 25px; border-radius: 20px; box-shadow: 0 15px 35px rgba(0,0,0,0.1); }
        .input-group { text-align: right; margin-bottom: 15px; }
        label { display: block; margin-bottom: 5px; font-weight: bold; }
        input { width: 100%; padding: 12px; border: 1px solid #ddd; border-radius: 10px; font-family: 'Cairo'; }
        .btn-wa { background: #25d366; color: white; width: 100%; padding: 15px; border: none; border-radius: 12px; font-weight: 900; font-size: 1.1rem; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 10px; }
        .contacts { display: flex; flex-direction: column; gap: 12px; max-width: 450px; margin: 20px auto; }
        .contact-link { background: rgba(255,255,255,0.6); padding: 12px; border-radius: 12px; display: flex; align-items: center; gap: 15px; text-decoration: none; color: var(--secondary); border: 1px solid white; transition: 0.3s; }
        .contact-link:hover { background: white; transform: scale(1.02); }
    </style>
</head>
<body>

    <nav>
        <div class="logo">DentoCare <i class="fas fa-tooth"></i></div>
        <div style="font-size: 0.8rem; font-weight: bold;">الرياض - حي العارض</div>
    </nav>

    <div style="padding: 20px;">
        <h1 style="font-weight: 900; margin-top: 20px;">عيادات دنتوكير المتخصصة</h1>
        <p style="color: #555;">نخبة من الاستشاريين السعوديين</p>

        <div class="booking-card">
            <div class="input-group">
                <label>الاسم الكامل</label>
                <input type="text" id="nameInput" placeholder="أدخل اسمك">
            </div>
            <div class="input-group">
                <label>رقم الجوال</label>
                <input type="tel" id="phoneInput" placeholder="05xxxxxxxx">
            </div>
            <button class="btn-wa" onclick="sendToWA()">تأكيد عبر واتساب <i class="fab fa-whatsapp"></i></button>
        </div>

        <div class="contacts">
            <a href="mailto:dentocareclinics1@gmail.com" class="contact-link">
                <i class="fas fa-envelope"></i> <span>dentocareclinics1@gmail.com</span>
            </a>
            <a href="https://www.instagram.com/dentocare_1" target="_blank" class="contact-link">
                <i class="fab fa-instagram"></i> <span>@dentocare_1</span>
            </a>
            <a href="tel:+966112043386" class="contact-link">
                <i class="fas fa-phone-alt"></i> <span>011 204 3386</span>
            </a>
        </div>
    </div>

    <script>
        function sendToWA() {
            const n = document.getElementById('nameInput').value;
            const p = document.getElementById('phoneInput').value;
            if(n && p) {
                window.open(`https://wa.me/966560502760?text=حجز جديد:%0Aالاسم: ${n}%0Aالجوال: ${p}`, '_blank');
            } else { alert("يرجى إكمال البيانات"); }
        }
    </script>
</body>
</html>
<script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
<script>
    /* إنشاء حاوية للخلفية */
    var div = document.createElement('div');
    div.id = 'particles-js';
    div.style.position = 'fixed';
    div.style.width = '100%';
    div.style.height = '100%';
    div.style.top = '0';
    div.style.left = '0';
    div.style.zIndex = '-1'; // لتبقى خلف المحتوى
    document.body.prepend(div);

    /* تشغيل التأثير */
    particlesJS("particles-js", {
        "particles": {
            "number": { "value": 80 },
            "color": { "value": "#00b4d8" },
            "shape": { "type": "circle" },
            "opacity": { "value": 0.5 },
            "size": { "value": 3 },
            "line_linked": { "enable": true, "distance": 150, "color": "#00b4d8", "opacity": 0.4, "width": 1 },
            "move": { "enable": true, "speed": 2 }
        },
        "interactivity": {
            "events": { "onhover": { "enable": true, "mode": "repulse" } }
        }
    });
</script>
<a href="instagram://user?username=dentocare_1" onclick="window.location.href='https://www.instagram.com/dentocare_1'; return false;" class="contact-link">
    <i class="fab fa-instagram"></i>
    <span>@dentocare_1</span>
</a>
<a href="https://maps.google.com/?q=DentoCare+Clinics+حي+العارض" target="_blank" class="contact-link">
    <i class="fas fa-map-marker-alt" style="color: #ff4757;"></i>
    <span>موقع العيادة (خرائط جوجل)</span>
</a>
<div id="status-badge" style="display:inline-block; padding:5px 15px; border-radius:20px; font-weight:bold; margin-top:10px;">
    </div>

<script>
    function updateStatus() {
        const hour = new Date().getHours();
        const badge = document.getElementById('status-badge');
        // إذا كان الوقت بين 2 ظهراً و 10 مساءً
        if(hour >= 14 && hour < 22) {
            badge.style.background = "#d1fae5"; badge.style.color = "#065f46";
            badge.innerHTML = "● مفتوح الآن - نستقبل حجوزاتكم";
        } else {
            badge.style.background = "#fee2e2"; badge.style.color = "#991b1b";
            badge.innerHTML = "● مغلق الآن - يمكنك الحجز للموعد القادم";
        }
    }
    updateStatus();
</script>
<div class="input-group">
    <label>نوع الخدمة</label>
    <select id="serviceType" style="width:100%; padding:12px; border-radius:10px; border:1px solid #ddd; font-family:'Cairo';">
        <option>استشارة عامة</option>
        <option>تنظيف وتلميع</option>
        <option>تبييض أسنان</option>
        <option>تقويم أسنان</option>
    </select>
</div>

<script>
    // داخل دالة sendToWA أضف:
    // const service = document.getElementById('serviceType').value;
    // ثم أضفها لنص الرسالة: `الخدمة: ${service}`
</script>
<nav>
    <div class="logo">DentoCare <i class="fas fa-tooth"></i></div>
    <div class="lang-switcher">
        <button onclick="changeLang('ar')" style="cursor:pointer; border:none; background:none; font-family:'Cairo'; font-weight:bold;">AR</button> | 
        <button onclick="changeLang('en')" style="cursor:pointer; border:none; background:none; font-family:'Cairo'; font-weight:bold;">EN</button> | 
        <button onclick="changeLang('fr')" style="cursor:pointer; border:none; background:none; font-family:'Cairo'; font-weight:bold;">FR</button>
    </div>
</nav>

<script>
    const translations = {
        ar: {
            title: "عيادات دنتوكير المتخصصة",
            subtitle: "نخبة من الاستشاريين السعوديين بجميع التخصصات",
            book: "طلب حجز موعد",
            namePl: "الاسم الكامل",
            btn: "تأكيد عبر واتساب",
            dir: "rtl"
        },
        en: {
            title: "DentoCare Specialized Clinics",
            subtitle: "Elite Saudi Consultants in all specialties",
            book: "Book an Appointment",
            namePl: "Full Name",
            btn: "Confirm via WhatsApp",
            dir: "ltr"
        },
        fr: {
            title: "Cliniques Spécialisées DentoCare",
            subtitle: "Consultants Saoudiens d'élite dans toutes les spécialités",
            book: "Prendre un RDV",
            namePl: "Nom Complet",
            btn: "Confirmer via WhatsApp",
            dir: "ltr"
        }
    };

    function changeLang(lang) {
        // تغيير اتجاه الموقع (من اليمين لليسار أو العكس)
        document.documentElement.dir = translations[lang].dir;
        document.documentElement.lang = lang;

        // تغيير النصوص (يجب إضافة id لكل نص تريد ترجمته)
        document.querySelector('h1').innerText = translations[lang].title;
        document.querySelector('.subtitle').innerText = translations[lang].subtitle;
        document.querySelector('h3').innerText = translations[lang].book;
        document.querySelector('label').innerText = translations[lang].namePl;
        document.querySelector('.btn-wa').childNodes[0].textContent = translations[lang].btn + " ";
    }
</script>

<div class="lang-switcher">
    <button class="lang-btn" onclick="changeLang('ar')">🇸🇦 AR</button>
    <button class="lang-btn" onclick="changeLang('en')">🇺🇸 EN</button>
    <button class="lang-btn" onclick="changeLang('fr')">🇫🇷 FR</button>
    <button class="lang-btn" onclick="changeLang('ru')">🇷🇺 RU</button>
    <button class="lang-btn" onclick="changeLang('hi')">🇮🇳 HI</button>
    <button class="lang-btn" onclick="changeLang('ur')">🇵🇰 UR</button>
</div>
const strings = {
    ar: {t1:"عيادات دنتوكير المتخصصة", t2:"نخبة من الاستشاريين السعوديين", l1:"الاسم الكامل", l2:"رقم الجوال", l3:"الخدمة", bt:"تأكيد عبر واتساب", dir:"rtl"},
    en: {t1:"DentoCare Specialized Clinics", t2:"Elite Saudi Consultants", l1:"Full Name", l2:"Phone Number", l3:"Service Type", bt:"Confirm via WhatsApp", dir:"ltr"},
    fr: {t1:"Cliniques DentoCare", t2:"Consultants d'élite", l1:"Nom Complet", l2:"Mobile", l3:"Service", bt:"Confirmer par WhatsApp", dir:"ltr"},
    ru: {t1:"Клиники DentoCare", t2:"Элитные саудовские консультанты", l1:"Полное имя", l2:"Номер телефона", l3:"Тип услуги", bt:"Подтвердить в WhatsApp", dir:"ltr"},
    hi: {t1:"डेंटोकेयर स्पेशलाइज्ड क्लीनिक", t2:"एलीट सऊदी सलाहकार", l1:"पूरा नाम", l2:"फोन नंबर", l3:"सेवा का प्रकार", bt:"व्हाट्सएप के माध्यम से पुष्टि करें", dir:"ltr"},
    ur: {t1:"ڈینٹو کیئر سپیشلائزڈ کلینک", t2:"ایلیٹ سعودی کنسلٹنٹس", l1:"پورا نام", l2:"فون نمبر", l3:"سروس کی قسم", bt:"واٹس ایپ کے ذریعے تصدیق کریں", dir:"rtl"}
};
<button class="lang-btn" onclick="changeLang('es')">🇪🇸 ES</button>
<button class="lang-btn" onclick="changeLang('it')">🇮🇹 IT</button>
<button class="lang-btn" onclick="changeLang('pt')">🇵🇹 PT</button>
es: {t1:"Clínicas DentoCare", t2:"Consultores saudíes de élite", l1:"Nombre completo", l2:"Teléfono", l3:"Servicio", bt:"Confirmar por WhatsApp", dir:"ltr"},
it: {t1:"Cliniche DentoCare", t2:"Consulenti sauditi d'élite", l1:"Nome completo", l2:"Telefono", l3:"Servizio", bt:"Conferma via WhatsApp", dir:"ltr"},
pt: {t1:"Clínicas DentoCare", t2:"Consultores sauditas de elite", l1:"Nome completo", l2:"Telemóvel", l3:"Serviço", bt:"Confirmar via WhatsApp", dir:"ltr"}
<button onclick="shareClinic()" style="background:#0077b6; color:white; padding:10px 20px; border:none; border-radius:30px; cursor:pointer; margin-top:15px; font-weight:bold;">
    <i class="fas fa-share-alt"></i> مشاركة موقع العيادة
</button>

<script>
function shareClinic() {
    if (navigator.share) {
        navigator.share({ title: 'عيادات دنتوكير', text: 'احجز موعدك في أفضل عيادات الأسنان بالرياض', url: window.location.href });
    }
}
</script>
<button onclick="toggleDarkMode()" style="background:none; border:none; cursor:pointer; font-size:1.2rem;">🌓</button>

<script>
function toggleDarkMode() {
    document.body.style.backgroundColor = document.body.style.backgroundColor === 'rgb(30, 30, 30)' ? '#f0f9ff' : '#1e1e1e';
    document.body.style.color = document.body.style.color === 'white' ? '#03045e' : 'white';
}
</script>
<div style="color:#f1c40f; margin-bottom:15px;">
    <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
    <span style="color:#555; font-size:0.9rem; margin-right:5px;">(4.9/5 تقييم مراجعينا)</span>
</div>
<button id="topBtn" onclick="window.scrollTo(0,0)" style="display:none; position:fixed; bottom:20px; left:20px; background:var(--primary); color:white; border-radius:50%; width:45px; height:45px; border:none; cursor:pointer; z-index:1000;">
    <i class="fas fa-arrow-up"></i>
</button>

<script>
window.onscroll = function() {
    document.getElementById("topBtn").style.display = (window.scrollY > 300) ? "block" : "none";
};
</script>
<div class="fab-container" style="position:fixed; bottom:20px; right:20px; z-index:999;">
    <button onclick="toggleFab()" style="width:60px; height:60px; border-radius:50%; background:var(--primary); color:white; border:none; font-size:24px; cursor:pointer; box-shadow:0 10px 20px rgba(0,0,0,0.2);">
        <i class="fas fa-plus" id="fab-icon"></i>
    </button>
    <div id="fab-menu" style="display:none; flex-direction:column; gap:10px; margin-bottom:10px; position:absolute; bottom:70px; right:5px;">
        <a href="tel:+966112043386" style="background:#3498db; width:50px; height:50px; border-radius:50%; display:flex; justify-content:center; align-items:center; color:white;"><i class="fas fa-phone"></i></a>
        <a href="https://wa.me/966560502760" style="background:#25d366; width:50px; height:50px; border-radius:50%; display:flex; justify-content:center; align-items:center; color:white;"><i class="fab fa-whatsapp"></i></a>
    </div>
</div>

<script>
function toggleFab() {
    const menu = document.getElementById('fab-menu');
    const icon = document.getElementById('fab-icon');
    menu.style.display = menu.style.display === 'none' ? 'flex' : 'none';
    icon.style.transform = menu.style.display === 'none' ? 'rotate(0deg)' : 'rotate(45deg)';
}
</script>
