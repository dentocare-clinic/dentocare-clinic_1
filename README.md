<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DentoCare | عيادات دنتوكير</title>
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap" rel="stylesheet">
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">

    <style>
        :root { --primary: #00b4d8; --secondary: #03045e; --accent: #25d366; }
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; transition: 0.3s; }
        body { background-color: #f0f9ff; color: var(--secondary); overflow-x: hidden; min-height: 100vh; }
        #particles-js { position: fixed; width: 100%; height: 100%; z-index: -1; top: 0; left: 0; }
        nav { background: rgba(255, 255, 255, 0.9); backdrop-filter: blur(10px); padding: 15px 5%; display: flex; justify-content: space-between; align-items: center; position: sticky; top: 0; z-index: 1000; box-shadow: 0 2px 10px rgba(0,0,0,0.1); }
        .logo { font-weight: 900; font-size: 1.4rem; color: var(--primary); display: flex; align-items: center; gap: 8px; text-decoration: none; }
        .lang-switcher button { cursor: pointer; border: 1px solid var(--primary); background: transparent; padding: 4px 8px; border-radius: 5px; font-weight: bold; font-size: 0.7rem; color: var(--primary); }
        .status-badge { display: inline-block; padding: 5px 12px; border-radius: 20px; font-weight: bold; font-size: 0.8rem; margin: 15px 0; }
        .container { padding: 20px 5%; text-align: center; }
        .booking-card { background: white; max-width: 450px; margin: auto; padding: 25px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.1); border: 1px solid #e0f2fe; }
        .input-group { text-align: right; margin-bottom: 15px; }
        label { display: block; margin-bottom: 5px; font-weight: 700; font-size: 0.9rem; }
        input, select { width: 100%; padding: 12px; border: 1px solid #eef2f3; border-radius: 10px; font-family: 'Cairo'; font-size: 1rem; }
        .btn-wa { background: var(--accent); color: white; width: 100%; padding: 15px; border: none; border-radius: 12px; font-weight: 900; font-size: 1.1rem; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 10px; box-shadow: 0 5px 15px rgba(37, 211, 102, 0.2); }
        .contacts-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; max-width: 900px; margin: 30px auto; }
        .contact-item { background: white; padding: 15px; border-radius: 15px; display: flex; align-items: center; gap: 12px; text-decoration: none; color: var(--secondary); border: 1px solid #f0f0f0; }
        .contact-item i { font-size: 1.3rem; color: var(--primary); }
        .contact-item div { text-align: right; }
        .contact-item h4 { font-size: 0.7rem; color: #888; }
        .contact-item p { font-weight: 700; font-size: 0.9rem; }
        [lang="en"] body, [lang="fr"] body { text-align: left; }
        [lang="en"] .input-group, [lang="fr"] .input-group { text-align: left; }
    </style>
</head>
<body>
    <div id="particles-js"></div>
    <nav>
        <a href="#" class="logo">DentoCare <i class="fas fa-tooth"></i></a>
        <div class="lang-switcher">
            <button onclick="changeLang('ar')">AR</button>
            <button onclick="changeLang('en')">EN</button>
            <button onclick="changeLang('fr')">FR</button>
        </div>
    </nav>
    <div class="container">
        <h1 id="mainTitle">عيادات دنتوكير المتخصصة</h1>
        <p id="mainSubtitle" style="color:#666; margin-bottom:10px;">نخبة من الاستشاريين السعوديين</p>
        <div id="statusBadge" class="status-badge"></div>
        <div class="booking-card">
            <h3 id="bookTitle" style="margin-bottom:15px;">حجز موعد</h3>
            <div class="input-group"><label id="lbl1">الاسم</label><input type="text" id="nameIn" placeholder="..."></div>
            <div class="input-group"><label id="lbl2">الجوال</label><input type="tel" id="phoneIn" placeholder="05xxxxxxxx"></div>
            <div class="input-group"><label id="lbl3">الخدمة</label><select id="servIn"><option>استشارة</option><option>تنظيف</option><option>تبييض</option></select></div>
            <button class="btn-wa" onclick="sendWA()"><span id="btnT">تأكيد</span> <i class="fab fa-whatsapp"></i></button>
        </div>
        <div class="contacts-grid">
            <a href="https://www.instagram.com/dentocare_1/" target="_blank" class="contact-item">
                <i class="fab fa-instagram" style="color:#e1306c"></i>
                <div><h4>Instagram</h4><p>@dentocare_1</p></div>
            </a>
            <a href="mailto:dentocareclinics1@gmail.com" class="contact-item">
                <i class="fas fa-envelope"></i>
                <div><h4>E-mail</h4><p>dentocareclinics1@gmail.com</p></div>
            </a>
            <a href="tel:+966112043386" class="contact-item">
                <i class="fas fa-phone-alt"></i>
                <div><h4>Phone</h4><p>011 204 3386</p></div>
            </a>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script>
        particlesJS("particles-js", {"particles":{"number":{"value":50},"color":{"value":"#00b4d8"},"line_linked":{"enable":true,"color":"#00b4d8","opacity":0.2},"move":{"speed":1}}});
        function checkStatus() {
            const hr = new Date().getHours();
            const b = document.getElementById('statusBadge');
            if(hr >= 14 && hr < 22) { b.style.background="#d1fae5"; b.innerText="● مفتوح الآن"; }
            else { b.style.background="#fee2e2"; b.innerText="● مغلق الآن"; }
        }
        checkStatus();
        const dict = {
            ar: {t:"عيادات دنتوكير", s:"نخبة من الاستشاريين", b:"حجز موعد", l1:"الاسم", l2:"الجوال", l3:"الخدمة", btn:"تأكيد", dir:"rtl"},
            en: {t:"DentoCare Clinics", s:"Elite Consultants", b:"Book Appointment", l1:"Name", l2:"Mobile", l3:"Service", btn:"Confirm", dir:"ltr"},
            fr: {t:"Cliniques DentoCare", s:"Consultants d'élite", b:"Prendre RDV", l1:"Nom", l2:"Mobile", l3:"Service", btn:"Confirmer", dir:"ltr"}
        };
        function changeLang(l) {
            document.documentElement.dir = dict[l].dir;
            document.getElementById('mainTitle').innerText = dict[l].t;
            document.getElementById('mainSubtitle').innerText = dict[l].s;
            document.getElementById('bookTitle').innerText = dict[l].b;
            document.getElementById('lbl1').innerText = dict[l].l1;
            document.getElementById('lbl2').innerText = dict[l].l2;
            document.getElementById('lbl3').innerText = dict[l].l3;
            document.getElementById('btnT').innerText = dict[l].btn;
        }
        function sendWA() {
            const n = document.getElementById('nameIn').value;
            const p = document.getElementById('phoneIn').value;
            const s = document.getElementById('servIn').value;
            if(n && p) { window.open(`https://wa.me/966560502760?text=حجز:%0Aالاسم:${n}%0Aالجوال:${p}%0Aالخدمة:${s}`, '_blank'); }
            else { alert("يرجى ملء البيانات"); }
        }
    </script>
</body>
</html>
