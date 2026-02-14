<style>
    /* حيلة لإخفاء أي نص يظهر قبل بداية الموقع */
    html { visibility: hidden; }
    body { visibility: visible; }
</style>

<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DentoCare | عيادات دنتوكير</title>
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap" rel="stylesheet">

    <style>
        :root { --primary: #00b4d8; --secondary: #03045e; --accent: #25d366; }
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; }
        body { background-color: #f0f9ff; color: var(--secondary); overflow-x: hidden; min-height: 100vh; text-align: center; }
        #particles-js { position: fixed; width: 100%; height: 100%; z-index: -1; top: 0; left: 0; }
        
        nav { background: white; padding: 15px 5%; display: flex; justify-content: space-between; align-items: center; box-shadow: 0 2px 10px rgba(0,0,0,0.1); position: sticky; top: 0; z-index: 1000; }
        .logo { font-weight: 900; font-size: 1.4rem; color: var(--primary); text-decoration: none; display: flex; align-items: center; gap: 8px; }
        
        .lang-btn { cursor: pointer; border: 1px solid var(--primary); background: white; padding: 3px 8px; border-radius: 5px; color: var(--primary); font-weight: bold; font-size: 0.8rem; margin: 0 2px; }

        .container { padding: 30px 5%; }
        .booking-card { background: white; max-width: 450px; margin: 20px auto; padding: 25px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.1); }
        
        .input-group { text-align: right; margin-bottom: 15px; }
        label { display: block; margin-bottom: 5px; font-weight: bold; }
        input, select { width: 100%; padding: 12px; border: 1px solid #ddd; border-radius: 10px; font-family: 'Cairo'; }
        
        .btn-wa { background: var(--accent); color: white; width: 100%; padding: 15px; border: none; border-radius: 12px; font-weight: 900; font-size: 1.1rem; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 10px; }

        .contacts-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; max-width: 900px; margin: 30px auto; }
        .contact-item { background: white; padding: 15px; border-radius: 15px; display: flex; align-items: center; gap: 12px; text-decoration: none; color: var(--secondary); border: 1px solid #eee; }
        .contact-item i { font-size: 1.4rem; color: var(--primary); }
        .contact-item div { text-align: right; }
        
        [lang="en"] body { text-align: left; }
        [lang="en"] .input-group, [lang="en"] .contact-item div { text-align: left; }
    </style>
</head>
<body>
    <div id="particles-js"></div>

    <nav>
        <div class="logo">DentoCare <i class="fas fa-tooth"></i></div>
        <div>
            <button class="lang-btn" onclick="changeLang('ar')">AR</button>
            <button class="lang-btn" onclick="changeLang('en')">EN</button>
        </div>
    </nav>

    <div class="container">
        <h1 id="t1">عيادات دنتوكير المتخصصة</h1>
        <p id="t2" style="color: #666;">نخبة من الاستشاريين السعوديين</p>

        <div class="booking-card">
            <div class="input-group">
                <label id="l1">الاسم الكامل</label>
                <input type="text" id="nameIn" placeholder="...">
            </div>
            <div class="input-group">
                <label id="l2">رقم الجوال</label>
                <input type="tel" id="phoneIn" placeholder="05xxxxxxxx">
            </div>
            <div class="input-group">
                <label id="l3">الخدمة</label>
                <select id="servIn">
                    <option>استشارة عامة</option>
                    <option>تنظيف وتلميع</option>
                    <option>تبييض أسنان</option>
                </select>
            </div>
            <button class="btn-wa" onclick="sendWA()">
                <span id="bt">تأكيد عبر واتساب</span> <i class="fab fa-whatsapp"></i>
            </button>
        </div>

        <div class="contacts-grid">
            <a href="https://www.instagram.com/dentocare_1/" target="_blank" class="contact-item">
                <i class="fab fa-instagram" style="color: #e1306c;"></i>
                <div><h4 style="font-size: 0.7rem; color: #888;">Instagram</h4><p>@dentocare_1</p></div>
            </a>
            <a href="mailto:dentocareclinics1@gmail.com" class="contact-item">
                <i class="fas fa-envelope"></i>
                <div><h4 style="font-size: 0.7rem; color: #888;">Email</h4><p>dentocareclinics1@gmail.com</p></div>
            </a>
            <a href="tel:+966112043386" class="contact-item">
                <i class="fas fa-phone-alt"></i>
                <div><h4 style="font-size: 0.7rem; color: #888;">Phone</h4><p>011 204 3386</p></div>
            </a>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script>
        particlesJS("particles-js", {"particles":{"number":{"value":60},"color":{"value":"#00b4d8"},"line_linked":{"enable":true,"opacity":0.2},"move":{"speed":1}}});

        const strings = {
            ar: {t1:"عيادات دنتوكير المتخصصة", t2:"نخبة من الاستشاريين السعوديين", l1:"الاسم الكامل", l2:"رقم الجوال", l3:"الخدمة", bt:"تأكيد عبر واتساب", dir:"rtl"},
            en: {t1:"DentoCare Specialized Clinics", t2:"Elite Saudi Consultants", l1:"Full Name", l2:"Phone Number", l3:"Service Type", bt:"Confirm via WhatsApp", dir:"ltr"}
        };

        function changeLang(l) {
            document.documentElement.lang = l;
            document.documentElement.dir = strings[l].dir;
            document.getElementById('t1').innerText = strings[l].t1;
            document.getElementById('t2').innerText = strings[l].t2;
            document.getElementById('l1').innerText = strings[l].l1;
            document.getElementById('l2').innerText = strings[l].l2;
            document.getElementById('l3').innerText = strings[l].l3;
            document.getElementById('bt').innerText = strings[l].bt;
        }

        function sendWA() {
            const n = document.getElementById('nameIn').value;
            const p = document.getElementById('phoneIn').value;
            const s = document.getElementById('servIn').value;
            if(n && p) {
                window.open(`https://wa.me/966560502760?text=حجز جديد:%0Aالاسم: ${n}%0Aالجوال: ${p}%0Aالخدمة: ${s}`, '_blank');
            } else {
                alert("يرجى ملء البيانات");
            }
        }
    </script>
</body>
</html>
