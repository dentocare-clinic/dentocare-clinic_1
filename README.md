<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DentoCare | عيادات دنتوكير المتخصصة</title>
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;700;900&display=swap" rel="stylesheet">
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">

    <style>
        :root {
            --primary: #00b4d8;
            --secondary: #03045e;
            --accent: #00f2ff;
            --bg-light: #f0f9ff;
            --glass: rgba(255, 255, 255, 0.85);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; scroll-behavior: smooth; }

        body { background-color: var(--bg-light); overflow-x: hidden; color: var(--secondary); line-height: 1.6; }

        #particles-js { position: fixed; width: 100%; height: 100%; z-index: -1; background: linear-gradient(135deg, #f0f9ff 0%, #cbebff 100%); }

        nav {
            background: var(--glass); backdrop-filter: blur(15px); padding: 15px 8%;
            display: flex; justify-content: space-between; align-items: center;
            position: fixed; width: 100%; top: 0; z-index: 1000;
            border-bottom: 1px solid rgba(255,255,255,0.3);
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
        }

        .logo-container { display: flex; align-items: center; gap: 10px; }
        .logo-text { font-size: 1.6rem; font-weight: 900; color: var(--secondary); }

        .hero { height: 90vh; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; padding: 0 10%; }
        .hero h1 { font-size: clamp(2.2rem, 8vw, 4.5rem); font-weight: 900; margin-bottom: 15px; }
        .badge { background: white; padding: 10px 25px; border-radius: 50px; box-shadow: 0 10px 20px rgba(0,0,0,0.05); font-weight: bold; margin-top: 10px; }

        .booking-section { padding: 80px 8%; max-width: 900px; margin: 0 auto; }
        .booking-card { background: white; padding: 40px; border-radius: 30px; box-shadow: 0 30px 60px rgba(0,0,0,0.1); border: 1px solid var(--accent); }

        .grid-inputs { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 20px; text-align: right; }
        .input-box label { display: block; margin-bottom: 8px; font-weight: 700; color: var(--secondary); }
        .input-box input, .input-box select { width: 100%; padding: 14px; border-radius: 12px; border: 1px solid #e0e0e0; background: #fafafa; font-family: 'Cairo'; font-size: 1rem; }

        .btn-booking { 
            background: linear-gradient(45deg, #25d366, #128c7e); color: white; padding: 18px; 
            border-radius: 15px; width: 100%; margin-top: 30px; border: none; font-size: 1.2rem; 
            font-weight: 900; cursor: pointer; transition: 0.3s; box-shadow: 0 10px 20px rgba(37, 211, 102, 0.2);
        }
        .btn-booking:hover { transform: translateY(-3px); box-shadow: 0 15px 30px rgba(37, 211, 102, 0.3); }

        .contact-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; padding: 40px 8%; }
        .contact-card { background: white; padding: 25px; border-radius: 20px; text-align: center; transition: 0.3s; text-decoration: none; color: inherit; display: block; }
        .contact-card i { font-size: 2rem; color: var(--primary); margin-bottom: 15px; }
        .contact-card:hover { transform: scale(1.05); border: 1px solid var(--primary); }

        .whatsapp-float { position: fixed; bottom: 30px; left: 30px; background: #25d366; color: white; width: 65px; height: 65px; border-radius: 50%; display: flex; justify-content: center; align-items: center; font-size: 35px; z-index: 1000; box-shadow: 0 10px 25px rgba(0,0,0,0.2); text-decoration: none; }
    </style>
</head>
<body>

    <div id="particles-js"></div>

    <nav>
        <div class="logo-container">
            <i class="fas fa-tooth" style="font-size: 2rem; color: var(--primary);"></i>
            <span class="logo-text">DentoCare</span>
        </div>
        <a href="tel:+966112043386" style="text-decoration:none; color:var(--primary); font-weight:900;">اتصل بالعيادة</a>
    </nav>

    <section class="hero" data-aos="zoom-out">
        <h1>نخبة من <span style="color:var(--primary)">الاستشاريين السعوديين</span><br>في خدمتك</h1>
        <p style="max-width: 600px;">بجميع التخصصات وبشهادات وخبرات محلية وعالمية - الرياض، حي العارض.</p>
        <div class="badge"><i class="fas fa-star" style="color:#ffbe0b"></i> 4.8 | 704 مراجعة موثقة</div>
    </section>

    <section class="booking-section" id="booking" data-aos="fade-up">
        <div class="booking-card">
            <h2 style="text-align:center; margin-bottom:30px;">احجز موعدك الآن</h2>
            <form id="clinicForm">
                <div class="grid-inputs">
                    <div class="input-box">
                        <label>الاسم بالكامل</label>
                        <input type="text" id="name" placeholder="أدخل اسمك" required>
                    </div>
                    <div class="input-box">
                        <label>رقم الجوال</label>
                        <input type="tel" id="phone" placeholder="05xxxxxxxx" required>
                    </div>
                    <div class="input-box">
                        <label>اليوم المطلوب</label>
                        <input type="date" id="date" required>
                    </div>
                    <div class="input-box">
                        <label>الفترة</label>
                        <select id="time">
                            <option>المسائية (2-10 مساءً)</option>
                            <option>الصباحية (حسب التوفر)</option>
                        </select>
                    </div>
                </div>
                <button type="button" onclick="bookingNow()" class="btn-booking">
                    تأكيد عبر WhatsApp <i class="fab fa-whatsapp"></i>
                </button>
            </form>
        </div>
    </section>

    <div class="contact-grid">
        <a href="mailto:dentocareclinics1@gmail.com" class="contact-card" data-aos="fade-up">
            <i class="fas fa-envelope"></i>
            <h3>البريد الإلكتروني</h3>
            <p>dentocareclinics1@gmail.com</p>
        </a>
        <a href="https://maps.app.goo.gl/9yG6m9Yq9pXy7Z8E7" target="_blank" class="contact-card" data-aos="fade-up" data-aos-delay="100">
            <i class="fas fa-map-marker-alt"></i>
            <h3>موقعنا في الرياض</h3>
            <p>حي العارض - طريق الملك عبدالعزيز</p>
        </a>
        <a href="https://www.instagram.com/dentocare_1" target="_blank" class="contact-card" data-aos="fade-up" data-aos-delay="200">
            <i class="fab fa-instagram"></i>
            <h3>تابعنا</h3>
            <p>@dentocare_1</p>
        </a>
    </div>

    <a href="https://wa.me/966560502760" class="whatsapp-float" target="_blank"><i class="fab fa-whatsapp"></i></a>

    <footer style="text-align:center; padding:50px; background:var(--secondary); color:white;">
        <h2>DentoCare Clinics</h2>
        <p style="opacity:0.7; margin-top:10px;">جميع الحقوق محفوظة 2026</p>
    </footer>

    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init();
        particlesJS("particles-js", {"particles":{"number":{"value":60},"color":{"value":"#00b4d8"},"shape":{"type":"circle"},"opacity":{"value":0.3},"size":{"value":3},"line_linked":{"enable":true,"color":"#00b4d8"},"move":{"enable":true,"speed":1.5}}});

        function bookingNow() {
            const name = document.getElementById('name').value;
            const phone = document.getElementById('phone').value;
            const date = document.getElementById('date').value;
            const time = document.getElementById('time').value;

            if(name && phone && date) {
                const whatsappNumber = "966560502760";
                const text = `طلب حجز جديد من الموقع:%0Aالاسم: ${name}%0Aالجوال: ${phone}%0Aالتاريخ: ${date}%0Aالوقت: ${time}`;
                window.open(`https://wa.me/${whatsappNumber}?text=${text}`, '_blank');
            } else {
                alert("يرجى إكمال جميع البيانات الأساسية");
            }
        }
    </script>
</body>
</html>
