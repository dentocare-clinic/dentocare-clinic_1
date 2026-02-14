<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DentoCare | تجربة طب الأسنان المستقبلية</title>
    
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
            --shadow: 0 15px 35px rgba(0,0,0,0.1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; scroll-behavior: smooth; }

        body { background-color: var(--bg-light); overflow-x: hidden; color: var(--secondary); }

        /* 1. ميزة: جزيئات الخلفية المتحركة */
        #particles-js {
            position: fixed;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(135deg, #f0f9ff 0%, #cbebff 100%);
        }

        /* 2. نوار علوي زجاجي */
        nav {
            background: var(--glass);
            backdrop-filter: blur(15px);
            padding: 15px 8%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(255,255,255,0.3);
            box-shadow: var(--shadow);
        }

        .logo { font-size: 1.8rem; font-weight: 900; color: var(--primary); display: flex; align-items: center; gap: 10px; }

        /* 3. قسم الواجهة الرئيسي (Hero Section) */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 10%;
            position: relative;
        }

        .hero h1 { font-size: clamp(2rem, 7vw, 4.5rem); line-height: 1.2; margin-bottom: 20px; font-weight: 900; }
        .highlight { color: var(--primary); }

        /* 4. زر الواتساب العائم */
        .whatsapp-float {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: #25d366;
            color: white;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 30px;
            box-shadow: 0 10px 25px rgba(37, 211, 102, 0.4);
            z-index: 999;
            transition: 0.3s;
            text-decoration: none;
        }
        .whatsapp-float:hover { transform: scale(1.1) rotate(15deg); }

        /* 5. بطاقات المعلومات */
        .info-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            padding: 50px 8%;
            margin-top: -80px;
            position: relative;
            z-index: 10;
        }

        .card {
            background: white;
            padding: 35px;
            border-radius: 25px;
            box-shadow: var(--shadow);
            border: 1px solid rgba(0, 180, 216, 0.1);
            transition: 0.4s;
            text-align: center;
        }
        .card:hover { transform: translateY(-10px); border-color: var(--primary); }

        .icon-box {
            width: 70px; height: 70px;
            background: var(--accent);
            border-radius: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 28px;
            color: var(--secondary);
            margin: 0 auto 20px;
        }

        .work-day { display: flex; justify-content: space-between; padding: 12px 0; border-bottom: 1px solid #f0f0f0; font-weight: bold; }
        .closed { color: #ff4d4d; }

        .btn-main {
            background: var(--primary);
            color: white;
            padding: 15px 40px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            box-shadow: 0 10px 20px rgba(0, 180, 216, 0.3);
            display: inline-block;
            transition: 0.3s;
            border: none;
            cursor: pointer;
        }
        .btn-main:hover { background: var(--secondary); transform: scale(1.05); }

        footer { padding: 40px 8%; text-align: center; background: var(--secondary); color: white; margin-top: 50px; }

    </style>
</head>
<body>

    <div id="particles-js"></div>

    <nav>
        <div class="logo"><i class="fas fa-tooth"></i> DentoCare</div>
        <a href="tel:+966112043386" class="btn-main" style="padding: 10px 20px; font-size: 0.9rem;">إتصال مباشر</a>
    </nav>

    <section class="hero">
        <div data-aos="fade-up">
            <h1>عيادة <span class="highlight">DentoCare</span><br>نصنع لك ابتسامة تليق بك</h1>
            <p style="font-size: 1.2rem; margin-bottom: 30px; opacity: 0.8;">التقنية الأحدث في عالم طب الأسنان بين يديك في الرياض</p>
            
            <div style="background: white; padding: 12px 25px; border-radius: 100px; display: inline-flex; align-items: center; gap: 12px; box-shadow: var(--shadow);">
                <span style="color: #ffbe0b;"><i class="fas fa-star"></i> 4.8</span>
                <span style="color: #ddd;">|</span>
                <span>704 مراجعة من عملاء فخورين</span>
            </div>
        </div>
    </section>

    <div class="info-container">
        <div class="card" data-aos="fade-up" data-aos-delay="100">
            <div class="icon-box"><i class="far fa-clock"></i></div>
            <h3 style="margin-bottom: 15px;">أوقات العمل</h3>
            <div class="work-day"><span>السبت - الأربعاء</span> <span>2:00 PM – 10:00 PM</span></div>
            <div class="work-day"><span>الخميس</span> <span>1:00 PM – 9:00 PM</span></div>
            <div class="work-day"><span>الجمعة</span> <span class="closed">مغلق</span></div>
        </div>

        <div class="card" data-aos="fade-up" data-aos-delay="200">
            <div class="icon-box"><i class="fas fa-location-dot"></i></div>
            <h3 style="margin-bottom: 15px;">موقعنا</h3>
            <p style="margin-bottom: 20px; font-size: 0.9rem;">4720 طريق الملك عبدالعزيز، حي العارض، الرياض 13337</p>
            <a href="https://www.google.com/maps/search/?api=1&query=24.8967,46.6344" target="_blank" class="btn-main" style="width: 100%;">فتح الخرائط</a>
        </div>

        <div class="card" data-aos="fade-up" data-aos-delay="300">
            <div class="icon-box"><i class="fab fa-instagram"></i></div>
            <h3 style="margin-bottom: 15px;">إنستجرام</h3>
            <p style="margin-bottom: 20px; font-size: 0.9rem;">تابع حالاتنا اليومية واستشاراتنا الطبية</p>
            <a href="https://www.instagram.com/dentocare_1" target="_blank" class="btn-main" style="width: 100%; background: linear-gradient(45deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888);">زيارة الحساب</a>
        </div>
    </div>

    <a href="https://wa.me/966112043386" class="whatsapp-float" target="_blank">
        <i class="fab fa-whatsapp"></i>
    </a>

    <footer>
        <h3>DentoCare Clinic</h3>
        <p style="margin: 15px 0; opacity: 0.7;">نلتزم بأعلى معايير الجودة والتعقيم</p>
        <p>© 2026 جميع الحقوق محفوظة</p>
    </footer>

    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        // زر تفعيل الأنيميشن عند التمرير
        AOS.init({ duration: 1000, once: true });

        // زر تفعيل ذرات الخلفية التفاعلية (Particles)
        particlesJS("particles-js", {
            "particles": {
                "number": { "value": 80, "density": { "enable": true, "value_area": 800 } },
                "color": { "value": "#00b4d8" },
                "shape": { "type": "circle" },
                "opacity": { "value": 0.5 },
                "size": { "value": 3 },
                "line_linked": { "enable": true, "distance": 150, "color": "#00b4d8", "opacity": 0.4, "width": 1 },
                "move": { "enable": true, "speed": 2 }
            },
            "interactivity": {
                "events": { "onhover": { "enable": true, "mode": "grab" }, "onclick": { "enable": true, "mode": "push" } }
            }
        });
    </script>
</body>
</html>

