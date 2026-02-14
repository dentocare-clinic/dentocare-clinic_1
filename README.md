<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DentoCare | عيادات دنتوكير</title>
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap" rel="stylesheet">

    <style>
        :root { --primary: #00b4d8; --secondary: #03045e; --text: #2d3436; }
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; }
        body { background-color: #f0f9ff; color: var(--text); line-height: 1.6; }

        /* الهيدر */
        nav { background: white; padding: 15px 5%; display: flex; justify-content: space-between; align-items: center; box-shadow: 0 2px 10px rgba(0,0,0,0.05); position: sticky; top: 0; z-index: 1000; }
        .logo { color: var(--primary); font-weight: 900; font-size: 1.5rem; text-decoration: none; }
        .nav-phone { font-weight: bold; color: var(--secondary); text-decoration: none; font-size: 0.9rem; }

        /* القسم الرئيسي */
        .hero { padding: 40px 5%; text-align: center; background: linear-gradient(180deg, #fff 0%, #e0f2fe 100%); }
        .hero h1 { font-size: 2.2rem; color: var(--secondary); margin-bottom: 10px; }
        .hero p { color: #636e72; font-size: 1.1rem; }

        /* كرت الحجز */
        .booking-card { background: white; max-width: 500px; margin: -30px auto 40px; padding: 30px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.1); border: 1px solid #e0f2fe; }
        .booking-card h2 { text-align: center; margin-bottom: 20px; color: var(--secondary); font-size: 1.4rem; }
        
        .input-group { margin-bottom: 15px; }
        .input-group label { display: block; margin-bottom: 5px; font-weight: bold; font-size: 0.9rem; }
        input, select { width: 100%; padding: 12px; border-radius: 10px; border: 1px solid #dfe6e9; font-family: 'Cairo'; font-size: 1rem; transition: 0.3s; }
        input:focus { border-color: var(--primary); outline: none; }

        .btn-send { background: #25d366; color: white; width: 100%; padding: 15px; border: none; border-radius: 12px; font-weight: 900; font-size: 1.1rem; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 10px; transition: 0.3s; }
        .btn-send:hover { background: #128c7e; transform: translateY(-2px); }

        /* قسم الخانات (الإيميل، الهاتف، انستجرام) كما طلبت */
        .contact-grid { display: grid; grid-template-columns: 1fr; gap: 15px; padding: 0 5% 60px; max-width: 500px; margin: auto; }
        .contact-item { background: white; padding: 15px; border-radius: 15px; display: flex; align-items: center; gap: 15px; text-decoration: none; color: inherit; box-shadow: 0 4px 6px rgba(0,0,0,0.02); transition: 0.3s; border: 1px solid #f0f0f0; }
        .contact-item:hover { transform: scale(1.02); border-color: var(--primary); }
        .contact-item i { width: 45px; height: 45px; background: #f0f9ff; color: var(--primary); display: flex; align-items: center; justify-content: center; border-radius: 10px; font-size: 1.2rem; }
        .contact-item div h4 { font-size: 0.9rem; color: #636e72; }
        .contact-item div p { font-weight: bold; font-size: 1rem; color: var(--secondary); }

        footer { text-align: center; padding: 30px; font-size: 0.8rem; color: #b2bec3; }
    </style>
</head>
<body>

    <nav>
        <a href="#" class="logo">DentoCare <i class="fas fa-tooth"></i></a>
        <a href="tel:+966112043386" class="nav-phone">اتصل بنا: 0112043386</a>
    </nav>

    <section class="hero">
        <h1>عيادات دنتوكير المتخصصة</h1>
        <p>نخبة من الاستشاريين السعوديين بجميع التخصصات</p>
    </section>

    <div class="booking-card">
        <h2>احجز موعدك الآن</h2>
        <div class="input-group">
            <label>الاسم الكامل</label>
            <input type="text" id="name" placeholder="أدخل اسمك">
        </div>
        <div class="input-group">
            <label>رقم الجوال</label>
            <input type="tel" id="phone" placeholder="05xxxxxxxx">
        </div>
        <div class="input-group">
            <label>تاريخ الموعد</label>
            <input type="date" id="date">
        </div>
        <button class="btn-send" onclick="sendBooking()">
            تأكيد الحجز عبر واتساب <i class="fab fa-whatsapp"></i>
        </button>
    </div>

    <div class="contact-grid">
        <a href="mailto:dentocareclinics1@gmail.com" class="contact-item">
            <i class="fas fa-envelope"></i>
            <div>
                <h4>البريد الإلكتروني</h4>
                <p>dentocareclinics1@gmail.com</p>
            </div>
        </a>

        <a href="https://www.instagram.com/dentocare_1" target="_blank" class="contact-item">
            <i class="fab fa-instagram"></i>
            <div>
                <h4>الإنستجرام</h4>
                <p>@dentocare_1</p>
            </div>
        </a>

        <a href="tel:+966112043386" class="contact-item">
            <i class="fas fa-phone-alt"></i>
            <div>
                <h4>الهاتف الثابت</h4>
                <p>011 204 3386</p>
            </div>
        </a>
    </div>

    <footer>
        &copy; 2026 عيادات دنتوكير - الرياض، حي العارض
    </footer>

    <script>
        function sendBooking() {
            const name = document.getElementById('name').value;
            const phone = document.getElementById('phone').value;
            const date = document.getElementById('date').value;

            if(name && phone && date) {
                // رقم الواتساب الصحيح 0560502760
                const whatsappNum = "966560502760"; 
                const msg = `طلب حجز جديد من الموقع:%0Aالاسم: ${name}%0Aالجوال: ${phone}%0Aالتاريخ: ${date}`;
                window.open(`https://wa.me/${whatsappNum}?text=${msg}`, '_blank');
            } else {
                alert("لطفاً أكمل بيانات الحجز");
            }
        }
    </script>
</body>
</html>
