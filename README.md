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
