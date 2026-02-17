<!DOCTYPE html>
<html lang="fa">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dragon Roleplay - Shop</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Press+Start+2P&display=swap" rel="stylesheet">
<style>
body {
  margin: 0;
  font-family: 'Orbitron', sans-serif;
  color: #FF0000;
  overflow-x: hidden;
  background:
    radial-gradient(circle at 25% 25%, #0ff 15%, transparent 40%),
    radial-gradient(circle at 75% 75%, #f0f 15%, transparent 40%),
    linear-gradient(135deg, #111 0%, #1a1a1a 100%);
}
.navbar {
  display: flex;
  justify-content: center;
  gap: 20px;
  padding: 15px;
  background: rgba(0,0,0,0.8);
}
.navbar a {
  text-decoration: none;
  color: #0ff;
  padding: 4px 6px;
  font-size: 12px;
  font-weight: 500;
  border-radius: 4px;
  transition: 0.3s;
} 
.navbar a:hover {
  background: #0ff;
  color: #000;
  box-shadow: 0 0 15px #0ff;
}
.section {
  display: none;
  padding: 40px 20px;
  max-width: 1200px;
  margin: 20px auto;
  border-radius: 12px;
  background: rgba(0,0,0,0.6);
  box-shadow: 0 0 25px #0ff inset;
}
.section.active {
  display: block;
}
.cards {
  display: flex;
  justify-content: center;
  gap: 25px;
  flex-wrap: wrap;
  margin-top: 20px;
}
.card {
  background: rgba(0,0,0,0.7);
  padding: 15px;
  width: 220px;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 0 15px #0ff;
  transition: 0.3s;
  cursor: pointer;
}
.card img {
  width: 100%;
  border-radius: 10px;
  box-shadow: 0 0 10px #0ff;
}
.card:hover {
  transform: scale(1.05);
  box-shadow: 0 0 25px #f0f;
}
.price {
  color: #0ff;
  font-weight: bold;
  margin-top: 5px;
}
footer {
  text-align: center;
  padding: 20px;
  color: #0ff;
}
.modal {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.85);
  justify-content: center;
  align-items: center;
  z-index: 9999;
}
.modal-content {
  background: #111;
  padding: 25px;
  border-radius: 15px;
  width: 350px;
  box-shadow: 0 0 25px #0ff;
}
.modal-content input {
  width: 100%;
  padding: 8px;
  margin: 8px 0;
  border-radius: 8px;
  border: none;
}
.modal-content button {
  width: 100%;
  padding: 10px;
  background: #0ff;
  border: none;
  border-radius: 8px;
  font-weight: bold;
  cursor: pointer;
}
.modal-content button:hover {
  background: #ff00ff;
  color: #fff;
}
.close {
  text-align: right;
  cursor: pointer;
  color: red;
}
.admin-order {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: rgba(0,255,255,0.1);
  padding: 8px;
  margin-bottom: 5px;
  border-radius: 6px;
}
.admin-order button {
  background: #ff0055;
  border: none;
  color: #fff;
  padding: 2px 6px;
  border-radius: 5px;
  cursor: pointer;
}
.admin-order button:hover {
  background: #ff00ff;
}
#music-player {
  position: fixed;
  bottom: 20px;
  left: 20px;
  z-index: 999999;
}
</style>
</head>
<body>

<nav class="navbar">
  <a href="#" data-target="home">خانه</a>
  <a href="#" data-target="skin">اسکین</a>
  <a href="#" data-target="car">ماشین</a>
  <a href="#" data-target="donate">دونیت</a>
  <a href="#" data-target="money">پول</a>
  <a href="#" data-target="premium">پرمیوم</a>
  <a href="#" data-target="adminPanel">پنل مدیر</a>
</nav>

<!-- خانه -->
<section id="home" class="section active">
  <h2>خانه‌ها</h2>
  <div class="cards">
    <div class="card" onclick="openModal('خانه ویژه - 80T')">
      <img src="https://uploadkon.ir/uploads/028415_26IMG-20251104-140619-038.jpg">
      <h3>خانه ویژه</h3>
      <p class="price">80T</p>
    </div>
    <div class="card" onclick="openModal('خانه لاکچری - 100T')">
      <img src="https://uploadkon.ir/uploads/91c615_26IMG-20251104-140622-920.jpg">
      <h3>خانه لاکچری</h3>
      <p class="price">100T</p>
    </div>
  </div>
</section>

<!-- اسکین -->
<section id="skin" class="section">
  <h2>اسکین‌ها</h2>
  <div class="cards">
    <div class="card" onclick="openModal('Skin ID 93 - 40T')"><img src="https://uploadkon.ir/uploads/bd6a16_26InShot-20260213-234136209.jpg"><p class="price">40T</p></div>
    <div class="card" onclick="openModal('Skin ID 108 - 80T')"><img src="https://uploadkon.ir/uploads/2fb116_26InShot-20260213-234440178.jpg"><p class="price">80T</p></div>
    <div class="card" onclick="openModal('Skin ID 179 - 60T')"><img src="https://uploadkon.ir/uploads/76dc16_26InShot-20260213-234506872.jpg"><p class="price">60T</p></div>
    <div class="card" onclick="openModal('Skin ID 116 - 100T')"><img src="https://uploadkon.ir/uploads/9b1516_26InShot-20260213-233137226.jpg"><p class="price">100T</p></div>
    <div class="card" onclick="openModal('Skin ID 247 - 120T')"><img src="https://uploadkon.ir/uploads/ae3e16_261000147916.png"><p class="price">120T</p></div>
    <div class="card" onclick="openModal('Skin ID 195 - 50T')"><img src="https://uploadkon.ir/uploads/06ad16_261000147917.png"><p class="price">50T</p></div>
    <div class="card" onclick="openModal('Skin ID 123 - 70T')"><img src="https://uploadkon.ir/uploads/083d16_261000147918.png"><p class="price">70T</p></div>
    <div class="card" onclick="openModal('Skin ID 107 - 120T')"><img src="https://uploadkon.ir/uploads/65a716_261000147919.png"><p class="price">120T</p></div>
    <div class="card" onclick="openModal('Skin ID 100 - 80T')"><img src="https://uploadkon.ir/uploads/a13416_261000147920.png"><p class="price">80T</p></div>
    <div class="card" onclick="openModal('Skin ID 68 - 90T')"><img src="https://uploadkon.ir/uploads/618216_261000147921.png"><p class="price">90T</p></div>
  </div>
</section>

<!-- ماشین -->
<section id="car" class="section">
  <h2>ماشین</h2>
  <p>بعداً پر می‌کنی</p>
</section>

<!-- دونیت -->
<section id="donate" class="section">
  <h2>دونیت</h2>
  <div class="cards">
    <div class="card" onclick="openModal('دونیت 2000 - 170T')"><h3>2000 دونیت</h3><p class="price">170T</p></div>
    <div class="card" onclick="openModal('دونیت 1000 - 90T')"><h3>1000 دونیت</h3><p class="price">90T</p></div>
    <div class="card" onclick="openModal('دونیت 500 - 50T')"><h3>500 دونیت</h3><p class="price">50T</p></div>
    <div class="card" onclick="openModal('دونیت 300 - 30T')"><h3>300 دونیت</h3><p class="price">30T</p></div>
    <div class="card" onclick="openModal('دونیت 100 - 20T')"><h3>100 دونیت</h3><p class="price">20T</p></div>
  </div>
</section>

<!-- پول -->
<section id="money" class="section">
  <h2>پول گیم</h2>
  <div class="cards">
    <div class="card" onclick="openModal('50KK پول - 100T')"><h3>50KK پول</h3><p class="price">100T</p></div>
    <div class="card" onclick="openModal('10KK پول - 70T')"><h3>10KK پول</h3><p class="price">70T</p></div>
    <div class="card" onclick="openModal('5KK پول - 40T')"><h3>5KK پول</h3><p class="price">40T</p></div>
    <div class="card" onclick="openModal('2KK پول - 20T')"><h3>2KK پول</h3><p class="price">20T</p></div>
    <div class="card" onclick="openModal('1KK پول - 10T')"><h3>1KK پول</h3><p class="price">10T</p></div>
  </div>
</section>

<!-- پرمیوم -->
<section id="premium" class="section">
  <h2>پرمیوم</h2>
  <div class="cards">
    <div class="card" onclick="openModal('پرمیوم 1 ماهه - 30T')"><h3>1 ماه پرمیوم</h3><p class="price">30T</p></div>
    <div class="card" onclick="openModal('پرمیوم 2 ماهه - 56T')"><h3>2 ماه پرمیوم</h3><p class="price">56T</p></div>
    <div class="card" onclick="openModal('پرمیوم 3 ماهه - 67T')"><h3>3 ماه پرمیوم</h3><p class="price">67T</p></div>
    <div class="card" onclick="openModal('پرمیوم 5 ماهه - 156T')"><h3>5 ماه پرمیوم</h3><p class="price">156T</p></div>
  </div>
</section>

<!-- پنل مدیر -->
<section id="adminPanel" class="section">
  <h2>پنل مدیرتی</h2>
  <input type="password" id="adminPass" placeholder="رمز عبور مدیر">
  <button onclick="checkAdminPass()">ورود</button>
  <div id="adminContent" style="display:none; margin-top:20px;">
    <h3>سفارش‌های ثبت شده</h3>
    <div id="orderList"></div>
  </div>
</section>

<footer>
  Tavsot Tim Dragon Rp | @DraGon_RolePlay
</footer>

<!-- Modal پرداخت -->
<div class="modal" id="paymentModal">
  <div class="modal-content">
    <div class="close" onclick="closeModal()">✖</div>
    <h3>پرداخت</h3>
    <p><b>شماره کارت:</b> 
    6037997528008247</p>
    عزیزی
    <p><b>محصول انتخاب شده:</b></p>
    <p id="selectedProduct"></p>
    <input type="text" id="accountName" placeholder="نام اکانت شما">
    <button onclick="submitOrder()">ثبت سفارش</button>
  </div>
</div>

<script>
// ذخیره سفارش‌ها در LocalStorage
let orders = JSON.parse(localStorage.getItem('orders') || '[]');

// ناوبری بین بخش‌ها
const links = document.querySelectorAll('.navbar a');
const sections = document.querySelectorAll('.section');

links.forEach(link => {
  link.addEventListener('click', e => {
    e.preventDefault();
    const target = link.getAttribute('data-target');
    sections.forEach(sec => sec.classList.remove('active'));
    const section = document.getElementById(target);
    if(section) section.classList.add('active');

    if(target === 'adminPanel' && document.getElementById('adminPass').value === '123321'){
      renderOrders();
    }
  });
});

// باز و بسته کردن Modal
function openModal(product){
  document.getElementById("paymentModal").style.display = "flex";
  document.getElementById("selectedProduct").innerText = product;
}
function closeModal(){
  document.getElementById("paymentModal").style.display = "none";
}

// ثبت سفارش
function submitOrder(){
  const product = document.getElementById("selectedProduct").innerText;
  const account = document.getElementById("accountName").value || "بدون نام";
  orders.push({product, account});
  localStorage.setItem('orders', JSON.stringify(orders));
  alert("سفارش ثبت شد و بعد از بررسی فعال می‌شود.");
  closeModal();
  document.getElementById("accountName").value = "";
}

// ورود مدیر
function checkAdminPass(){
  const pass = document.getElementById("adminPass").value;
  const content = document.getElementById("adminContent");
  if(pass === "123321"){
    content.style.display = "block";
    renderOrders();
  } else {
    alert("رمز اشتباه است!");
    content.style.display = "none";
  }
}

// رندر سفارش‌ها در پنل مدیر با دکمه حذف
function renderOrders(){
  const container = document.getElementById("orderList");
  container.innerHTML = "";
  orders.forEach((o,index)=>{
    const div = document.createElement("div");
    div.className = "admin-order";
    div.innerHTML = `<span>${o.account} - ${o.product}</span>
                     <button onclick="deleteOrder(${index})">حذف</button>`;
    container.appendChild(div);
  });
}

// حذف سفارش
function deleteOrder(index){
  orders.splice(index,1);
  localStorage.setItem('orders', JSON.stringify(orders));
  renderOrders();
}
</script>

</body>
</html>
