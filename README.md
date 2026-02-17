<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dragon RP Shop</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        /* ===== Reset ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Vazirmatn', 'Orbitron', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background: linear-gradient(135deg, #0b1020, #FF0000);
            color: #fff;
            overflow-x: hidden;
            min-height: 100vh;
        }

        /* ===== Navbar ===== */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 12px 20px;
            background: rgba(0, 0, 0, 0.95);
            z-index: 1000;
            box-shadow: 0 0 15px #00f7ff;
        }

        .navbar .logo {
            font-size: 26px;
            font-weight: 900;
            color: #0ff;
            text-shadow: 0 0 10px #00f7ff, 0 0 20px #0ff;
        }

        .navbar ul {
            list-style: none;
            display: flex;
            gap: 15px;
        }

        .navbar ul li a {
            text-decoration: none;
            color: #0ff;
            padding: 8px 12px;
            border-radius: 8px;
            transition: 0.3s;
            font-weight: 700;
        }

        .navbar ul li a:hover {
            background: #00f7ff;
            color: #000;
            box-shadow: 0 0 10px #0ff, 0 0 20px #00f7ff;
        }

        .menu-toggle {
            display: none;
            flex-direction: column;
            gap: 5px;
            cursor: pointer;
        }

        .menu-toggle div {
            width: 30px;
            height: 4px;
            background: #0ff;
            border-radius: 2px;
        }

        .menu-toggle:hover div {
            box-shadow: 0 0 10px #0ff, 0 0 20px #00f7ff;
        }

        @media (max-width: 900px) {
            .menu-toggle {
                display: flex;
            }

            .navbar ul {
                display: none;
                flex-direction: column;
                background: rgba(0, 0, 0, 0.95);
                position: absolute;
                top: 60px;
                left: 20px;
                padding: 15px 20px;
                border-radius: 12px;
                min-width: 200px;
            }

            .navbar ul.show {
                display: flex;
            }
        }

        /* ===== Hero ===== */
        .hero {
            height: 80vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: radial-gradient(circle at center, rgba(0, 255, 255, 0.1), transparent 70%), linear-gradient(135deg, #0b1020, #FF0000);
        }

        .hero h1 {
            font-size: 50px;
            color: #0ff;
            text-shadow: 0 0 20px #00f7ff, 0 0 35px #0ff;
            font-weight: 900;
        }

        .hero p {
            margin-top: 15px;
            font-size: 20px;
            color: #fff;
            font-weight: 700;
        }

        .hero .btn {
            margin-top: 25px;
            padding: 15px 40px;
            background: #00f7ff;
            color: #000;
            font-weight: 900;
            border: none;
            border-radius: 12px;
            box-shadow: 0 0 15px #00f7ff, 0 0 30px #0ff;
            transition: 0.3s;
            cursor: pointer;
            font-size: 18px;
        }

        .hero .btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 20px #0ff, 0 0 40px #00f7ff;
        }

        /* ===== Sections ===== */
        .section {
            margin: 50px auto;
            width: 95%;
            max-width: 1200px;
            display: none;
            flex-direction: column;
        }

        .section h2 {
            text-align: center;
            margin-bottom: 25px;
            color: #0ff;
            text-shadow: 0 0 10px #00f7ff;
            font-weight: 900;
            font-size: 32px;
        }

        .cards {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
        }

        .card {
            background: rgba(0, 0, 0, 0.6);
            border-radius: 12px;
            padding: 12px;
            width: 200px;
            text-align: center;
            box-shadow: 0 0 12px #0ff;
            transition: 0.3s;
            cursor: pointer;
        }

        .card img {
            width: 100%;
            border-radius: 8px;
            margin-bottom: 8px;
        }

        .card h3 {
            color: #0ff;
            margin-bottom: 6px;
            font-weight: 700;
        }

        .price {
            font-weight: 900;
            color: #0ff;
        }

        .card:hover {
            box-shadow: 0 0 20px #00f7ff, 0 0 35px #0ff;
            transform: scale(1.05);
        }

        /* ===== Cart ===== */
        .cart {
            position: fixed;
            top: 100px;
            left: 20px;
            background: rgba(0, 0, 0, 0.85);
            padding: 20px;
            border-radius: 12px;
            width: 300px;
            box-shadow: 0 0 15px #0ff;
            max-height: 70vh;
            overflow-y: auto;
        }

        .cart h3 {
            text-align: center;
            color: #0ff;
            margin-bottom: 15px;
            font-weight: 900;
            font-size: 24px;
        }

        .cart-items {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(0, 255, 255, 0.1);
            padding: 8px 10px;
            border-radius: 8px;
        }

        .cart-item span {
            font-weight: 700;
        }

        .cart-item button {
            background: #ff004c;
            color: #fff;
            border: none;
            padding: 4px 8px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 12px;
            font-weight: 700;
        }

        .cart-item button:hover {
            background: #ff3377;
        }

        #cart-total {
            font-weight: 900;
            font-size: 18px;
            margin-top: 15px;
        }

        /* ===== Cart Warning ===== */
        .cart-warning {
            background: rgba(255, 0, 0, 0.2);
            border: 2px solid #ff004c;
            border-radius: 8px;
            padding: 10px;
            margin: 10px 0;
            text-align: center;
            font-weight: 700;
            color: #ff004c;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { opacity: 1; }
            50% { opacity: 0.7; box-shadow: 0 0 15px #ff004c; }
            100% { opacity: 1; }
        }

        /* ===== Admin Panel ===== */
        .admin-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 2000;
            display: none;
            justify-content: center;
            align-items: center;
        }

        .admin-panel {
            background: rgba(0, 0, 0, 0.95);
            padding: 30px;
            border-radius: 20px;
            width: 90%;
            max-width: 500px;
            max-height: 80vh;
            overflow-y: auto;
            box-shadow: 0 0 30px #ff00ff;
            border: 3px solid #ff00ff;
            position: relative;
            animation: glow 2s infinite;
        }

        @keyframes glow {
            0% { box-shadow: 0 0 20px #ff00ff; }
            50% { box-shadow: 0 0 40px #ff00ff; }
            100% { box-shadow: 0 0 20px #ff00ff; }
        }

        .admin-panel h3 {
            color: #ff00ff;
            text-align: center;
            margin-bottom: 20px;
            font-weight: 900;
            font-size: 28px;
            text-shadow: 0 0 15px #ff00ff;
        }

        .admin-panel input {
            width: 100%;
            padding: 12px;
            margin-bottom: 20px;
            border: none;
            border-radius: 10px;
            background: rgba(255, 255, 255, 0.1);
            color: #fff;
            font-weight: 700;
            border: 2px solid #ff00ff;
            font-size: 16px;
        }

        .admin-panel input:focus {
            outline: none;
            box-shadow: 0 0 20px #ff00ff;
        }

        .admin-panel button {
            width: 100%;
            padding: 12px;
            background: #ff00ff;
            color: #000;
            border: none;
            border-radius: 10px;
            font-weight: 900;
            cursor: pointer;
            box-shadow: 0 0 20px #ff00ff;
            transition: 0.3s;
            font-size: 16px;
            margin-bottom: 10px;
        }

        .admin-panel button:hover {
            transform: scale(1.02);
            box-shadow: 0 0 30px #ff00ff;
        }

        .purchases-list {
            max-height: 400px;
            overflow-y: auto;
            margin-top: 20px;
            padding: 10px;
            background: rgba(255, 0, 255, 0.05);
            border-radius: 10px;
        }

        .purchase-item {
            background: rgba(255, 0, 255, 0.1);
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 15px;
            border: 1px solid #ff00ff;
            position: relative;
        }

        .purchase-item p {
            font-weight: 700;
            margin-bottom: 8px;
            font-size: 14px;
        }

        .purchase-item img {
            max-width: 100%;
            border-radius: 8px;
            margin-top: 10px;
            border: 2px solid #ff00ff;
        }

        .delete-purchase {
            position: absolute;
            top: 10px;
            left: 10px;
            background: #ff004c;
            color: #fff;
            border: none;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            cursor: pointer;
            font-weight: 900;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
            box-shadow: 0 0 10px #ff004c;
        }

        .delete-purchase:hover {
            background: #ff3377;
            transform: scale(1.1);
        }

        .close-admin {
            position: absolute;
            top: 15px;
            right: 15px;
            background: #ff004c;
            color: #fff;
            border: none;
            width: 35px;
            height: 35px;
            border-radius: 50%;
            cursor: pointer;
            font-weight: 900;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            box-shadow: 0 0 15px #ff004c;
        }

        .close-admin:hover {
            background: #ff3377;
            transform: scale(1.1);
        }

        /* ===== Receipt Image Upload ===== */
        .receipt-upload {
            margin-top: 15px;
            padding: 15px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            border: 1px solid #0ff;
        }

        .receipt-upload label {
            display: block;
            margin-bottom: 8px;
            color: #0ff;
            font-weight: 700;
            font-size: 16px;
        }

        .receipt-upload input[type="file"] {
            width: 100%;
            padding: 10px;
            background: rgba(0, 255, 255, 0.1);
            border: 2px solid #0ff;
            border-radius: 8px;
            color: #fff;
            cursor: pointer;
            font-weight: 700;
        }

        .receipt-upload input[type="file"]:hover {
            box-shadow: 0 0 15px #0ff;
        }

        .preview-image {
            max-width: 100%;
            max-height: 150px;
            margin-top: 15px;
            border-radius: 8px;
            border: 3px solid #0ff;
            box-shadow: 0 0 15px #0ff;
        }

        /* ===== Footer ===== */
        footer {
            text-align: center;
            color: #0ff;
            padding: 30px;
            font-weight: 900;
            margin-top: 50px;
            box-shadow: 0 -5px 15px #0ff;
        }

        @media (max-width: 900px) {
            .cart {
                position: static;
                width: 90%;
                margin: 20px auto;
            }
            
            .admin-panel {
                width: 95%;
                padding: 20px;
            }
        }
    </style>
</head>
<body>

    <!-- Navbar -->
    <nav class="navbar">
        <div class="logo">Dragon RP Shop</div>
        <div class="menu-toggle" id="menu-toggle">
            <div></div>
            <div></div>
            <div></div>
        </div>
        <ul id="nav-links">
            <li><a href="#home">خانه</a></li>
            <li><a href="#donate">دونیت</a></li>
            <li><a href="#money">پول</a></li>
            <li><a href="#premium">پرمیوم</a></li>
            <li><a href="#skin">اسکین</a></li>
            <li><a href="#" onclick="openAdminPanel()">پنل مدیریت</a></li>
        </ul>
    </nav>

    <!-- Hero -->
    <section class="hero">
        <h1>خوش آمدید به Dragon RP Shop</h1>
        <p>بهترین فروشگاه آیتم‌های GTA SA</p>
        <button class="btn" id="viewProductsBtn">مشاهده محصولات</button>
    </section>

    <!-- Section: خانه -->
    <section id="home" class="section">
        <h2>خانه‌ها</h2>
        <div class="cards">
            <div class="card" onclick="addToCart('خانه ویژه',80)">
                <img src="https://uploadkon.ir/uploads/028415_26IMG-20251104-140619-038.jpg" alt="خانه ویژه">
                <h3>خانه ویژه</h3>
                <p class="price">80T</p>
            </div>
            <div class="card" onclick="addToCart('خانه لاکچری',100)">
                <img src="https://uploadkon.ir/uploads/91c615_26IMG-20251104-140622-920.jpg" alt="خانه لاکچری">
                <h3>خانه لاکچری</h3>
                <p class="price">100T</p>
            </div>
        </div>
    </section>

    <!-- Section: دونیت -->
    <section id="donate" class="section">
        <h2>دونیت</h2>
        <div class="cards">
            <div class="card" onclick="addToCart('2000 دونیت',170)"><h3>2000 دونیت</h3><p class="price">170T</p></div>
            <div class="card" onclick="addToCart('1000 دونیت',90)"><h3>1000 دونیت</h3><p class="price">90T</p></div>
            <div class="card" onclick="addToCart('500 دونیت',50)"><h3>500 دونیت</h3><p class="price">50T</p></div>
            <div class="card" onclick="addToCart('300 دونیت',30)"><h3>300 دونیت</h3><p class="price">30T</p></div>
            <div class="card" onclick="addToCart('100 دونیت',20)"><h3>100 دونیت</h3><p class="price">20T</p></div>
        </div>
    </section>

    <!-- Section: پول -->
    <section id="money" class="section">
        <h2>پول گیم</h2>
        <div class="cards">
            <div class="card" onclick="addToCart('50KK پول',100)"><h3>50KK پول</h3><p class="price">100T</p></div>
            <div class="card" onclick="addToCart('10KK پول',70)"><h3>10KK پول</h3><p class="price">70T</p></div>
            <div class="card" onclick="addToCart('5KK پول',40)"><h3>5KK پول</h3><p class="price">40T</p></div>
            <div class="card" onclick="addToCart('2KK پول',20)"><h3>2KK پول</h3><p class="price">20T</p></div>
            <div class="card" onclick="addToCart('1KK پول',10)"><h3>1KK پول</h3><p class="price">10T</p></div>
        </div>
    </section>

    <!-- Section: پرمیوم -->
    <section id="premium" class="section">
        <h2>پرمیوم</h2>
        <div class="cards">
            <div class="card" onclick="addToCart('پرمیوم 1 ماهه',30)"><h3>1 ماه پرمیوم</h3><p class="price">30T</p></div>
            <div class="card" onclick="addToCart('پرمیوم 2 ماهه',56)"><h3>2 ماه پرمیوم</h3><p class="price">56T</p></div>
            <div class="card" onclick="addToCart('پرمیوم 3 ماهه',67)"><h3>3 ماه پرمیوم</h3><p class="price">67T</p></div>
            <div class="card" onclick="addToCart('پرمیوم 5 ماهه',156)"><h3>5 ماه پرمیوم</h3><p class="price">156T</p></div>
        </div>
    </section>

    <!-- Section: اسکین -->
    <section id="skin" class="section">
        <h2>اسکین‌ها</h2>
        <div class="cards">
            <div class="card" onclick="addToCart('Skin ID 93',40)"><img src="https://uploadkon.ir/uploads/bd6a16_26InShot-20260213-234136209.jpg" alt="Skin 93"><p class="price">40T</p></div>
            <div class="card" onclick="addToCart('Skin ID 108',80)"><img src="https://uploadkon.ir/uploads/2fb116_26InShot-20260213-234440178.jpg" alt="Skin 108"><p class="price">80T</p></div>
            <div class="card" onclick="addToCart('Skin ID 179',60)"><img src="https://uploadkon.ir/uploads/76dc16_26InShot-20260213-234506872.jpg" alt="Skin 179"><p class="price">60T</p></div>
            <div class="card" onclick="addToCart('Skin ID 116',100)"><img src="https://uploadkon.ir/uploads/9b1516_26InShot-20260213-233137226.jpg" alt="Skin 116"><p class="price">100T</p></div>
            <div class="card" onclick="addToCart('Skin ID 247',120)"><img src="https://uploadkon.ir/uploads/ae3e16_261000147916.png" alt="Skin 247"><p class="price">120T</p></div>
            <div class="card" onclick="addToCart('Skin ID 195',50)"><img src="https://uploadkon.ir/uploads/06ad16_261000147917.png" alt="Skin 195"><p class="price">50T</p></div>
            <div class="card" onclick="addToCart('Skin ID 123',70)"><img src="https://uploadkon.ir/uploads/083d16_261000147918.png" alt="Skin 123"><p class="price">70T</p></div>
            <div class="card" onclick="addToCart('Skin ID 107',120)"><img src="https://uploadkon.ir/uploads/65a716_261000147919.png" alt="Skin 107"><p class="price">120T</p></div>
            <div class="card" onclick="addToCart('Skin ID 100',80)"><img src="https://uploadkon.ir/uploads/a13416_261000147920.png" alt="Skin 100"><p class="price">80T</p></div>
            <div class="card" onclick="addToCart('Skin ID 68',90)"><img src="https://uploadkon.ir/uploads/618216_261000147921.png" alt="Skin 68"><p class="price">90T</p></div>
        </div>
    </section>

    <!-- Cart -->
    <div class="cart" id="cart">
        <h3>سبد خرید</h3>
        <div class="cart-items" id="cart-items"></div>
        <p id="cart-total">جمع کل: 0 تومان</p>
        
        <!-- Receipt Image Upload -->
        <div class="receipt-upload">
            <label>⚠️ ارسال رسید پرداخت (اجباری)</label>
            <input type="file" id="receiptImage" accept="image/*" onchange="previewReceipt(event)">
            <img id="receiptPreview" class="preview-image" style="display:none;">
        </div>
        
        <!-- Warning Message -->
        <div class="cart-warning" id="receiptWarning">
            ⚠️ برای تکمیل خرید باید رسید پرداخت را آپلود کنید
        </div>
        
        <button onclick="checkout()" style="margin-top:10px;padding:10px 20px;border:none;border-radius:8px;background:#0ff;color:#000;cursor:pointer;box-shadow:0 0 10px #0ff;font-weight:900;">پرداخت کل</button>
    </div>

    <!-- Admin Panel Overlay -->
    <div id="adminOverlay" class="admin-overlay">
        <div class="admin-panel">
            <button class="close-admin" onclick="closeAdminPanel()">×</button>
            <h3>پنل مدیریت</h3>
            <input type="password" id="adminPassword" placeholder="رمز عبور را وارد کنید">
            <button onclick="verifyAdmin()">ورود به پنل</button>
            <div id="adminContent" style="display:none;">
                <h4 style="color:#ff00ff;margin:15px 0;text-align:center;font-size:20px;">لیست خریدها</h4>
                <div id="purchasesList" class="purchases-list"></div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <p>تمامی حقوق برای Dragon RP Shop محفوظ است.</p>
    </footer>

    <script>
        // Hamburger Menu Toggle
        const menuToggle = document.getElementById('menu-toggle');
        const navLinks = document.getElementById('nav-links');

        menuToggle.addEventListener('click', () => {
            navLinks.classList.toggle('show');
        });

        // Open menu when clicking "View Products" button
        document.getElementById('viewProductsBtn').addEventListener('click', () => {
            navLinks.classList.add('show');
            document.getElementById('home').scrollIntoView({ behavior: 'smooth' });
        });

        // Cart Logic
        let cart = [];
        let purchases = JSON.parse(localStorage.getItem('purchases')) || [];
        let currentReceiptImage = null;

        function addToCart(name, price) {
            cart.push({ name, price });
            renderCart();
        }

        function removeFromCart(index) {
            cart.splice(index, 1);
            renderCart();
        }

        function renderCart() {
            const cartItems = document.getElementById('cart-items');
            const totalEl = document.getElementById('cart-total');
            cartItems.innerHTML = '';
            let total = 0;
            
            cart.forEach((item, index) => {
                total += item.price;
                const div = document.createElement('div');
                div.className = 'cart-item';
                div.innerHTML = `<span>${item.name} - ${item.price}T</span>
                                <button onclick="removeFromCart(${index})">حذف</button>`;
                cartItems.appendChild(div);
            });
            
            totalEl.textContent = 'جمع کل: ' + total + ' تومان';
        }

        function previewReceipt(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    const preview = document.getElementById('receiptPreview');
                    preview.src = e.target.result;
                    preview.style.display = 'block';
                    currentReceiptImage = e.target.result;
                    
                    // Hide warning if receipt is uploaded
                    document.getElementById('receiptWarning').style.display = 'none';
                };
                reader.readAsDataURL(file);
            }
        }

        function checkout() {
            if (cart.length === 0) {
                alert('سبد خرید شما خالی است!');
                return;
            }
            
            // Check if receipt is uploaded
            if (!currentReceiptImage) {
                alert('⚠️ لطفا ابتدا رسید پرداخت را آپلود کنید!');
                document.getElementById('receiptWarning').style.display = 'block';
                return;
            }
            
            let name = prompt("نام اکانت خود را وارد کنید:");
            if (!name) return;
            
            let card = prompt("شماره کارت را وارد کنید:", "6037997528008247");
            if (!card) return;
            
            // Create purchase record
            const purchase = {
                id: Date.now(),
                account: name,
                card: card,
                items: [...cart],
                total: cart.reduce((sum, item) => sum + item.price, 0),
                receipt: currentReceiptImage,
                date: new Date().toLocaleString('fa-IR')
            };
            
            purchases.push(purchase);
            localStorage.setItem('purchases', JSON.stringify(purchases));
            
            alert("✅ پرداخت با موفقیت انجام شد.\nاکانت: " + name + 
                  "\nمبلغ: " + document.getElementById('cart-total').textContent + 
                  "\nشماره کارت: " + card);
            
            cart = [];
            currentReceiptImage = null;
            document.getElementById('receiptImage').value = '';
            document.getElementById('receiptPreview').style.display = 'none';
            document.getElementById('receiptWarning').style.display = 'block';
            renderCart();
        }

        // Admin Panel
        function openAdminPanel() {
            document.getElementById('adminOverlay').style.display = 'flex';
        }

        function closeAdminPanel() {
            document.getElementById('adminOverlay').style.display = 'none';
            document.getElementById('adminPassword').value = '';
            document.getElementById('adminContent').style.display = 'none';
        }

        function verifyAdmin() {
            const password = document.getElementById('adminPassword').value;
            if (password === '123321') {
                document.getElementById('adminContent').style.display = 'block';
                displayPurchases();
            } else {
                alert('❌ رمز عبور اشتباه است!');
            }
        }

        function deletePurchase(id) {
            if (confirm('آیا از حذف این سفارش اطمینان دارید؟')) {
                purchases = purchases.filter(p => p.id !== id);
                localStorage.setItem('purchases', JSON.stringify(purchases));
                displayPurchases(); // Refresh the list
            }
        }

        function displayPurchases() {
            const purchasesList = document.getElementById('purchasesList');
            purchasesList.innerHTML = '';
            
            if (purchases.length === 0) {
                purchasesList.innerHTML = '<p style="color:#fff;text-align:center;">هیچ خریدی ثبت نشده است</p>';
                return;
            }
            
            purchases.reverse().forEach(purchase => {
                const div = document.createElement('div');
                div.className = 'purchase-item';
                
                let itemsList = '';
                purchase.items.forEach(item => {
                    itemsList += `${item.name} - ${item.price}T<br>`;
                });
                
                div.innerHTML = `
                    <button class="delete-purchase" onclick="deletePurchase(${purchase.id})">×</button>
                    <p><strong>📅 تاریخ:</strong> ${purchase.date}</p>
                    <p><strong>👤 اکانت:</strong> ${purchase.account}</p>
                    <p><strong>💳 کارت:</strong> ${purchase.card}</p>
                    <p><strong>🛒 محصولات:</strong><br>${itemsList}</p>
                    <p><strong>💰 جمع کل:</strong> ${purchase.total}T</p>
                    ${purchase.receipt ? `<img src="${purchase.receipt}" alt="رسید پرداخت">` : ''}
                `;
                purchasesList.appendChild(div);
            });
        }

        // Section Navigation
        const sections = document.querySelectorAll('.section');
        const menuLinks = document.querySelectorAll('.navbar ul li a:not([href="#"])');

        function showSection(sectionId) {
            sections.forEach(section => {
                if (section.id === sectionId) {
                    section.style.display = 'flex';
                } else {
                    section.style.display = 'none';
                }
            });
        }

        menuLinks.forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                const targetId = link.getAttribute('href').substring(1);
                
                showSection(targetId);
                document.getElementById(targetId).scrollIntoView({ behavior: 'smooth' });

                if (navLinks.classList.contains('show')) {
                    navLinks.classList.remove('show');
                }
            });
        });

        // Show home section on page load
        showSection('home');

        // Close mobile menu when clicking outside
        document.addEventListener('click', (e) => {
            if (!menuToggle.contains(e.target) && !navLinks.contains(e.target)) {
                navLinks.classList.remove('show');
            }
        });
    </script>
</body>
</html>
