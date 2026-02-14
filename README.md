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
        :root { --primary: #00b4d8; --secondary: #03045e; --bg: #f0f9ff; }
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; }
        body { background-color: var(--bg); overflow-x: hidden; color: var(--secondary); }
        #particles-js { position: fixed; width: 100%; height: 100%; z-index: -1; background: linear-gradient(135deg, #f0f9ff 0%, #cbebff 100%); }
        nav { background: rgba(255,255,255,0.8); backdrop-filter: blur(10px); padding: 15px 8%; display: flex; justify-content: space-between; align-items: center; position: fixed; width: 100%; top: 0; z-index: 1000; box-shadow: 0 2px 10px rgba(0,0,0,0.05); }
        .hero { height: 80vh; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; padding: 0 10%; }
        .booking-card { background: white; padding: 30px; border-radius: 25px; box-shadow: 0 20px 40px rgba(0,0,0,0.1); max-width: 800px; margin: -50px auto 50px; position: relative; z-index: 10; border: 1px solid var(--primary); }
        .grid-inputs { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin-top: 20px; }
        input, select { width: 100%; padding: 12px; border-radius: 10px; border: 1px solid #ddd; font-family: 'Cairo'; }
        .btn-booking { background: #25d366; color: white; padding: 15px; border-radius: 12px; width: 100%; border: none; font-weight: bold; font-size: 1.1rem; cursor: pointer; margin-top: 20px; transition: 0.3s; }
        .btn-booking:hover { transform: scale(1.02); background: #128c7e; }
        .contact-info { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 20px; padding: 40px 8%; text-align: center; }
        .whatsapp-float { position: fixed; bottom: 30px; left: 30px; background: #25d366; color: white; width: 60px; height: 60px; border-radius: 50%; display: flex; justify-content: center; align-items: center; font-size: 30px; z-index: 1000; text-decoration: none; box-shadow: 0 5px 15px rgba(0,0,0,0.2); }
    </style>
</head>
<body>
    <div id="particles-js"></div>
    <nav>
        <div style="font-weight:900; font-size:1.5rem; color:var(--primary);"><i class="fas fa-tooth"></i> DentoCare</div>
        <a href="tel:+966112043386" style="text-decoration:none; color:var(--secondary); font-weight:bold;">اتصل بنا: 0112043386</a>
    </nav>

    <section class="hero" data-aos="fade-up">
        <h1 style="font-size: 3rem; margin-bottom: 10px;">عيادات دنتوكير المتخصصة</h1>
        <p>نخبة من الاستشاريين السعوديين بجميع التخصصات</p>
        <p style="margin-top:10px;"><i class="fas fa-map-marker-alt"></i> حي العارض، الرياض</p>
    </section>

    <div class="booking-card" data-aos="zoom-in">
        <h2 style="text-align:center;">احجز موعدك الآن</h2>
        <form id="bookingForm">
            <div class="grid-inputs">
                <input type="text" id="name" placeholder="الاسم الكامل" required>
                <input type="tel" id="phone" placeholder="رقم الجوال" required>
                <input type="date" id="date" required>
                <select id="time">
                    <option>الفترة المسائية (2-10 مساءً)</option>
                    <option>الفترة الصباحية</option>
                </select>
            </div>
            <button type="button" onclick="sendToWhatsApp()" class="btn-booking">تأكيد الحجز عبر واتساب <i class="fab fa-whatsapp"></i></button>
        </form>
    </div>

    <div class="contact-info">
        <div><i class="fas fa-envelope"></i><p>dentocareclinics1@gmail.com</p></div>
        <div><i class="fab fa-instagram"></i><p>@dentocare_1</p></div>
        <div><i class="fas fa-phone"></i><p>011 204 3386</p></div>
    </div>

    <a href="https://wa.me/966560502760" class="whatsapp-float" target="_blank"><i class="fab fa-whatsapp"></i></a>

    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init();
        particlesJS("particles-js", {"particles":{"number":{"value":50},"color":{"value":"#00b4d8"},"shape":{"type":"circle"},"opacity":{"value":0.5},"size":{"value":3},"line_linked":{"enable":true,"color":"#00b4d8"},"move":{"enable":true,"speed":1.5}}});

        function sendToWhatsApp() {
            const name = document.getElementById('name').value;
            const phone = document.getElementById('phone').value;
            const date = document.getElementById('date').value;
            const time = document.getElementById('time').value;
            
            if(name && phone && date) {
                // الرقم الصحيح للواتساب المستخرج من معلومات التواصل (0560502760)
                const wpNumber = "966560502760";
                const text = `طلب حجز جديد من الموقع:%0Aالاسم: ${name}%0Aالجوال: ${phone}%0Aالتاريخ: ${date}%0Aالوقت: ${time}`;
                window.open(`https://wa.me/${wpNumber}?text=${text}`, '_blank');
            } else { alert("يرجى ملء البيانات"); }
        }
    </script>
</body>
</html>
