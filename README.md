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
        :root { 
            --primary: #00b4d8; 
            --secondary: #03045e; 
            --accent: #25d366;
            --white: #ffffff;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; transition: all 0.3s ease; }
        
        body { background-color: #f0f9ff; color: var(--secondary); overflow-x: hidden; min-height: 100vh; }

        /* حاوية الخلفية المتحركة */
        #particles-js { position: fixed; width: 100%; height: 100%; z-index: -1; top: 0; left: 0; }

        /* الهيدر */
        nav { 
            background: rgba(255, 255, 255, 0.9); 
            backdrop-filter: blur(10px); 
            padding: 15px 8%; 
            display: flex; 
            justify-content: space-between; 
            align-items: center; 
            position: sticky; 
            top: 0; 
            z-index: 1000; 
            box-shadow: 0 2px 15px rgba(0,0,0,0.1); 
        }

        .logo { font-weight: 900; font-size: 1.6rem; color: var(--primary); display: flex; align-items: center; gap: 8px; text-decoration: none; }
        
        .lang-switcher button { 
            cursor: pointer; border: 1px solid var(--primary); background: transparent; 
            padding: 5px 10px; border-radius: 8px; font-weight: bold; font-size: 0.8rem; color: var(--primary);
        }
        .lang-switcher button:hover { background: var(--primary); color: white; }

        /* حالة العيادة (مفتوح/مغلق) */
        .status-badge { 
            display: inline-block; padding: 6px 15px; border-radius: 20px; 
            font-weight: bold; font-size: 0.9rem; margin-top: 15px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.05);
        }

        .container { padding: 40px 8%; text-align: center; }
        
        h1 { font-size: clamp(1.8rem, 5vw, 3rem); font-weight: 900; margin-bottom: 10px; }
        .subtitle { color: #555; font-size: 1.1rem; margin-bottom: 30px; }

        /* كرت الحجز */
        .booking-card { 
            background: white; max-width: 550px; margin: auto; padding: 35px; 
            border-radius: 30px; box-shadow: 0 20px 50px rgba(0,0,0,0.1); 
            border: 1px solid rgba(0, 180, 216, 0.2); 
        }

        .input-group { text-align: right; margin-bottom: 20px; }
        label { display: block; margin-bottom: 8px; font-weight: 700; font-size: 0.95rem; }
        input, select { 
            width: 100%; padding: 14px; border: 1.5px solid #eef2f3; 
            border-radius: 12px; font-family: 'Cairo'; background: #fdfdfd; 
            font-size: 1rem; 
        }
        input:focus { border-color: var(--primary); outline: none; background: white; }

        .btn-wa { 
            background: var(--accent); color: white; width: 100%; padding: 18px; 
            border: none; border-radius: 15px; font-weight: 900; font-size: 1.2rem; 
            cursor: pointer; display: flex; align-items: center; justify-content: center; 
            gap: 12px; margin-top: 10px; box-shadow: 0 10px 20px rgba(37, 211, 102, 0.2);
        }
        .btn-wa:hover { background: #1eb956; transform: translateY(-3px); }

        /* قسم روابط التواصل */
        .contacts-grid { 
            display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); 
            gap: 20px; max-width: 1000px; margin: 40px auto; 
        }

        .contact-item { 
            background: rgba(255, 255, 255, 0.8); padding: 20px; border-radius: 20px; 
            display: flex; align-items: center; gap: 15px; text-decoration: none; 
            color: var(--secondary); border: 1px solid white; box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        .contact-item:hover { background: white; transform: scale(1.05); border-color: var(--primary); }
        .contact-item i { font-size: 1.5rem; color: var(--primary); width: 40px; }
        .contact-item div { text-align: right; }
        .contact-item h4 { font-size: 0.8rem; color: #777; }
        .contact-item p { font-weight: 700; }

        footer { padding: 40px; color: #aaa; font-size: 0.9rem; }

        /* لغات أخرى - قلب الاتجاه */
        [lang="en"] body, [lang="fr"] body { text-align: left; }
        [lang="en"] .input-group, [lang="fr"] .input-group { text-align: left; }
        [lang="en"] .contact-item div, [lang="fr"] .contact-item div { text-align: left; }
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
        <p class="subtitle" id="mainSubtitle">نخبة من الاستشاريين السعوديين بجميع التخصصات</p>
        
        <div id="statusBadge" class="status-badge"></div>

        <div class="booking-card" data-aos="zoom-in">
            <h2 id="bookTitle" style="margin-bottom: 25px;">حجز موعد جديد</h2>
            
            <div class="input-group">
                <label id="lblLevel1">الاسم الكامل</label>
                <input type="text" id="nameInput" placeholder="...">
            </div>

            <div class="input-group">
                <label id="lblLevel2">رقم الجوال</label>
                <input type="tel" id="phoneInput" placeholder="05xxxxxxxx">
            </div>

            <div class="input-group">
                <label id="lblLevel3">نوع الخدمة</label>
                <select id="serviceInput">
                    <option value="استشارة">استشارة عامة</option>
                    <option value="تنظيف">تنظيف وتلميع</option>
                    <option value="تبييض">تبييض أسنان</option>
                    <option value="تقويم">تقويم أسنان</option>
                </select>
            </div>

            <button class="btn-wa" onclick="sendToWA()">
                <span id="btnText">تأكيد عبر واتساب</span> <i class="fab fa-whatsapp"></i>
            </button>
        </div>

        <div class="contacts-grid">
            <a href="https://maps.google.com/?q=DentoCare+Clinics+Riyadh" target="_blank" class="contact-item" data-aos="fade-up">
                <i class="fas fa-map-marked-alt"></i>
                <div>
                    <h4 id="cTitle1">موقعنا</h4>
                    <p id="cText1">الرياض - حي العارض</p>
                </div>
            </a>

            <a href="instagram://user?username=dentocare_1" onclick="window.location.href='https://www.instagram.com/dentocare_1'; return false;" class="contact-item" data-aos="fade-up" data-aos-delay="100">
                <i class="fab fa-instagram" style="color: #e1306c;"></i>
                <div>
                    <h4>Instagram</h4>
                    <p>@dentocare_1</p>
                </div>
            </a>

            <a href="mailto:dentocareclinics1@gmail.com" class="contact-item" data-aos="fade-up" data-aos-delay="200">
                <i class="fas fa-envelope"></i>
                <div>
                    <h4 id="cTitle3">البريد الإلكتروني</h4>
                    <p>dentocareclinics1@gmail.com</p>
                </div>
            </a>
            
            <a href="tel:+966112043386" class="contact-item" data-aos="fade-up" data-aos-delay="300">
                <i class="fas fa-phone-alt"></i>
                <div>
                    <h4 id="cTitle4">الهاتف الثابت</h4>
                    <p>011 204 3386</p>
                </div>
            </a>
        </div>
    </div>

    <footer>
        &copy; 2026 DentoCare Clinics - Kingdom of Saudi Arabia
    </footer>

    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init();

        // 1. تشغيل الخلفية المتحركة
        particlesJS("particles-js", {
            "particles": {
                "number": { "value": 70 },
                "color": { "value": "#00b4d8" },
                "shape": { "type": "circle" },
                "opacity": { "value": 0.4 },
                "size": { "value": 3 },
                "line_linked": { "enable": true, "color": "#00b4d8", "opacity": 0.3 },
                "move": { "enable": true, "speed": 1.5 }
            }
        });

        // 2. تحديث حالة العيادة
        function checkStatus() {
            const hr = new Date().getHours();
            const badge = document.getElementById('statusBadge');
            const isAr = document.documentElement.lang === 'ar';
            
            if(hr >= 14 && hr < 22) { // من 2 ظهراً لـ 10 مساءً
                badge.style.background = "#d1fae5"; badge.style.color = "#065f46";
                badge.innerText = isAr ? "● مفتوح الآن - نستقبلكم" : "● Open Now - Accepting Patients";
            } else {
                badge.style.background = "#fee2e2"; badge.style.color = "#991b1b";
                badge.innerText = isAr ? "● مغلق حالياً - احجز للموعد القادم" : "● Closed Now - Book for tomorrow";
            }
        }
        checkStatus();

        // 3. نظام الترجمة
        const dict = {
            ar: {
                title: "عيادات دنتوكير المتخصصة",
                sub: "نخبة من الاستشاريين السعوديين بجميع التخصصات",
                book: "حجز موعد جديد",
                n: "الاسم الكامل",
                p: "رقم الجوال",
                s: "نوع الخدمة",
                btn: "تأكيد عبر واتساب",
                c1: "موقعنا",
                c1t: "الرياض - حي العارض",
                c3: "البريد الإلكتروني",
                c4: "الهاتف الثابت",
                dir: "rtl"
            },
            en: {
                title: "DentoCare Specialized Clinics",
                sub: "Elite Saudi Consultants in all specialties",
                book: "Book New Appointment",
                n: "Full Name",
                p: "Phone Number",
                s: "Service Type",
                btn: "Confirm via WhatsApp",
                c1: "Our Location",
                c1t: "Riyadh - Al Arid Dist.",
                c3: "Email Address",
                c4: "Landline Phone",
                dir: "ltr"
            },
            fr: {
                title: "Cliniques DentoCare",
                sub: "Consultants Saoudiens d'élite",
                book: "Prendre un RDV",
                n: "Nom Complet",
                p: "Numéro de Mobile",
                s: "Type de Service",
                btn: "Confirmer par WhatsApp",
                c1: "Notre Emplacement",
                c1t: "Riyad - Quartier Al Arid",
                c3: "E-mail",
                c4: "Téléphone Fixe",
                dir: "ltr"
            }
        };

        function changeLang(l) {
            document.documentElement.lang = l;
            document.documentElement.dir = dict[l].dir;
            
            document.getElementById('mainTitle').innerText = dict[l].title;
            document.getElementById('mainSubtitle').innerText = dict[l].sub;
            document.getElementById('bookTitle').innerText = dict[l].book;
            document.getElementById('lblLevel1').innerText = dict[l].n;
            document.getElementById('lblLevel2').innerText = dict[l].p;
            document.getElementById('lblLevel3').innerText = dict[l].s;
            document.getElementById('btnText').innerText = dict[l].btn;
            document.getElementById('cTitle1').innerText = dict[l].c1;
            document.getElementById('cText1').innerText = dict[l].c1t;
            document.getElementById('cTitle3').innerText = dict[l].c3;
            document.getElementById('cTitle4').innerText = dict[l].c4;
            checkStatus();
        }

        // 4. وظيفة الحجز
        function sendToWA() {
            const name = document.getElementById('nameInput').value;
            const phone = document.getElementById('phoneInput').value;
            const service = document.getElementById('serviceInput').value;
            
            if(name && phone) {
                const wp = "966560502760";
                const msg = `طلب حجز من الموقع:%0Aالاسم: ${name}%0Aالجوال: ${phone}%0Aالخدمة: ${service}`;
                window.open(`https://wa.me/${wp}?text=${msg}`, '_blank');
            } else {
                alert(document.documentElement.lang === 'ar' ? "يرجى تعبئة الاسم والجوال" : "Please fill name and phone");
            }
        }
    </script>
</body>
</html>
