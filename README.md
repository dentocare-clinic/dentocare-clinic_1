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
        :root { --primary: #00b4d8; --secondary: #03045e; --bg: #f8fbff; }
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; }
        body { background-color: var(--bg); color: var(--secondary); line-height: 1.6; }
        
        nav { background: white; padding: 15px 8%; display: flex; justify-content: space-between; align-items: center; box-shadow: 0 2px 10px rgba(0,0,0,0.05); position: sticky; top: 0; z-index: 1000; }
        .logo { font-weight: 900; font-size: 1.5rem; color: var(--primary); }

        .hero { padding: 60px 8%; text-align: center; background: linear-gradient(135deg, #f0f9ff 0%, #cbebff 100%); }
        .hero h1 { font-size: 2.5rem; margin-bottom: 10px; }

        .booking-card { background: white; padding: 30px; border-radius: 25px; box-shadow: 0 15px 40px rgba(0,0,0,0.1); max-width: 600px; margin: -40px auto 40px; border-top: 5px solid var(--primary); }
        .input-group { margin-bottom: 15px; text-align: right; }
        label { display: block; margin-bottom: 5px; font-weight: bold; }
        input, select { width: 100%; padding: 12px; border-radius: 10px; border: 1px solid #ddd; font-family: 'Cairo'; }

        .btn-wa { background: #25d366; color: white; padding: 15px; border-radius: 12px; width: 100%; border: none; font-weight: bold; font-size: 1.2rem; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 10px; transition: 0.3s; }
        .btn-wa:hover { background: #128c7e; transform: scale(1.02); }

        .contact-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; padding: 40px 8%; }
        .info-item { background: white; padding: 20px; border-radius: 15px; text-align: center; box-shadow: 0 5px 15px rgba(0,0,0,0.05); }
        .info-item i { font-size: 1.5rem; color: var(--primary); margin-bottom: 10px; }
    </style>
</head>
<body>

    <nav>
        <div class="logo"><i class="fas fa-tooth"></i> DentoCare</div>
        <div style="font-weight: bold;">حي العارض، الرياض</div>
    </nav>

    <section class="hero" data-aos="fade-down">
        <h1>عيادات دنتوكير المتخصصة</h1>
        <p>نخبة من الاستشاريين السعوديين بجميع التخصصات</p>
    </section>

    <div class="booking-card" data-aos="zoom-in">
        <h2 style="text-align: center; margin-bottom: 20px;">طلب حجز موعد</h2>
        <div class="input-group">
            <label>الاسم الكامل</label>
            <input type="text" id="cust_name" placeholder="أدخل اسمك هنا">
        </div>
        <div class="input-group">
            <label>رقم الجوال</label>
            <input type="tel" id="cust_phone" placeholder="05xxxxxxxx">
        </div>
        <div class="input-group">
            <label>التاريخ المفضل</label>
            <input type="date" id="cust_date">
        </div>
        <button class="btn-wa" onclick="triggerWhatsApp()">
            إرسال الطلب عبر الواتساب <i class="fab fa-whatsapp"></i>
        </button>
    </div>

    <div class="contact-grid">
        <div class="info-item">
            <i class="fas fa-phone-alt"></i>
            <h3>للاتصال المباشر</h3>
            <p>0112043386</p>
        </div>
        <div class="info-item">
            <i class="fab fa-instagram"></i>
            <h3>تابعنا</h3>
            <p>@dentocare_1</p>
        </div>
        <div class="info-item">
            <i class="fas fa-envelope"></i>
            <h3>البريد الإلكتروني</h3>
            <p>dentocareclinics1@gmail.com</p>
        </div>
    </div>

    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init();
        function triggerWhatsApp() {
            const name = document.getElementById('cust_name').value;
            const phone = document.getElementById('cust_phone').value;
            const date = document.getElementById('cust_date').value;

            if(name && phone && date) {
                // الرقم الصحيح المستخرج من معلومات التواصل (0560502760)
                const whatsappNumber = "966560502760"; 
                const text = `مرحباً دنتوكير، أرغب في حجز موعد:%0A- الاسم: ${name}%0A- الجوال: ${phone}%0A- التاريخ: ${date}`;
                window.open(`https://wa.me/${whatsappNumber}?text=${text}`, '_blank');
            } else {
                alert("يرجى ملء جميع الخانات المطلوبة");
            }
        }
    </script>
</body>
</html>
