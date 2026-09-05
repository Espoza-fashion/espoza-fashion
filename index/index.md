<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Espoza Admin</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

  <link
    href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;600;700;800&display=swap"
    rel="stylesheet"
  >

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: "Tajawal", sans-serif;
      background: #f6f6f6;
      color: #222;
    }

    .hidden {
      display: none !important;
    }

    /* LOGIN */

    #loginPage {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 20px;
      background: linear-gradient(135deg, #111, #292929);
    }

    .login-box {
      width: 100%;
      max-width: 400px;
      background: white;
      padding: 35px 25px;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 20px 60px rgba(0,0,0,.25);
    }

    .logo {
      font-size: 32px;
      font-weight: 800;
      letter-spacing: 3px;
      margin-bottom: 10px;
    }

    .gold {
      color: #d4af37;
    }

    .login-box h1 {
      margin-bottom: 8px;
    }

    .login-box p {
      color: #777;
      margin-bottom: 25px;
    }

    .login-box input {
      width: 100%;
      padding: 15px;
      border: 1px solid #ddd;
      border-radius: 12px;
      outline: none;
      font-family: inherit;
      font-size: 16px;
      margin-bottom: 12px;
      text-align: center;
    }

    .login-box input:focus {
      border-color: #d4af37;
    }

    .login-box button {
      width: 100%;
      padding: 15px;
      border: 0;
      border-radius: 12px;
      background: #111;
      color: white;
      font-family: inherit;
      font-size: 16px;
      font-weight: 700;
      cursor: pointer;
    }

    .login-box button:hover {
      background: #d4af37;
      color: #111;
    }

    #loginError {
      color: #d00;
      margin-top: 12px;
      min-height: 20px;
    }


    /* ADMIN */

    #adminPage {
      min-height: 100vh;
    }

    .topbar {
      background: #111;
      color: white;
      padding: 18px 25px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 15px;
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .topbar-logo {
      font-size: 25px;
      font-weight: 800;
      letter-spacing: 2px;
    }

    .topbar small {
      display: block;
      color: #bbb;
      margin-top: 3px;
    }

    .logout {
      background: #d4af37;
      color: #111;
      border: 0;
      padding: 10px 16px;
      border-radius: 10px;
      font-family: inherit;
      font-weight: 700;
      cursor: pointer;
    }

    .container {
      width: 100%;
      max-width: 1200px;
      margin: auto;
      padding: 25px 18px 50px;
    }

    .welcome {
      margin-bottom: 25px;
    }

    .welcome h1 {
      font-size: 28px;
      margin-bottom: 5px;
    }

    .welcome p {
      color: #777;
    }


    /* STATS */

    .stats {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 15px;
      margin-bottom: 25px;
    }

    .stat {
      background: white;
      padding: 20px;
      border-radius: 16px;
      box-shadow: 0 4px 15px rgba(0,0,0,.06);
    }

    .stat span {
      color: #777;
      font-size: 14px;
    }

    .stat strong {
      display: block;
      font-size: 28px;
      margin-top: 8px;
    }


    /* MENU */

    .section-title {
      font-size: 21px;
      margin-bottom: 15px;
    }

    .menu {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 15px;
    }

    .menu button {
      background: white;
      border: 0;
      border-radius: 16px;
      padding: 25px 15px;
      text-align: right;
      font-family: inherit;
      cursor: pointer;
      box-shadow: 0 4px 15px rgba(0,0,0,.06);
      transition: .2s;
    }

    .menu button:hover {
      transform: translateY(-3px);
      box-shadow: 0 8px 25px rgba(0,0,0,.1);
    }

    .menu-icon {
      font-size: 32px;
      display: block;
      margin-bottom: 12px;
    }

    .menu strong {
      display: block;
      font-size: 18px;
      margin-bottom: 5px;
    }

    .menu small {
      color: #777;
    }


    /* CONTENT */

    #content {
      margin-top: 25px;
      background: white;
      border-radius: 18px;
      padding: 25px;
      min-height: 250px;
      box-shadow: 0 4px 15px rgba(0,0,0,.06);
    }

    .empty {
      text-align: center;
      padding: 45px 10px;
      color: #777;
    }

    .empty-icon {
      font-size: 45px;
      margin-bottom: 10px;
    }


    /* MOBILE */

    @media (max-width: 700px) {

      .topbar {
        padding: 15px;
      }

      .container {
        padding: 20px 12px 40px;
      }

      .stats {
        grid-template-columns: repeat(2, 1fr);
      }

      .menu {
        grid-template-columns: repeat(2, 1fr);
      }

      .menu button {
        padding: 20px 12px;
      }

      .menu-icon {
        font-size: 27px;
      }

      .menu strong {
        font-size: 16px;
      }

      .welcome h1 {
        font-size: 24px;
      }
    }

    @media (max-width: 400px) {

      .menu {
        grid-template-columns: 1fr;
      }

      .topbar-logo {
        font-size: 20px;
      }

      .logout {
        padding: 8px 12px;
      }
    }

  </style>
</head>


<body>


  <!-- LOGIN -->

  <div id="loginPage">

    <div class="login-box">

      <div class="logo">
        ESPOZA <span class="gold">ADMIN</span>
      </div>

      <h1>لوحة التحكم</h1>

      <p>
        أدخل كلمة السر للدخول
      </p>

      <input
        type="password"
        id="password"
        placeholder="كلمة السر"
        autocomplete="off"
        onkeydown="if(event.key === 'Enter') login()"
      >

      <button onclick="login()">
        دخول
      </button>

      <div id="loginError"></div>

    </div>

  </div>



  <!-- ADMIN -->

  <div id="adminPage" class="hidden">

    <header class="topbar">

      <div>
        <div class="topbar-logo">
          ESPOZA <span class="gold">ADMIN</span>
        </div>

        <small>
          لوحة التحكم الخاصة بالمتجر
        </small>
      </div>

      <button class="logout" onclick="logout()">
        تسجيل الخروج
      </button>

    </header>


    <main class="container">

      <div class="welcome">

        <h1>
          أهلاً بك 👋
        </h1>

        <p>
          من هنا رح تتحكم بكل شيء في متجر Espoza Fashion.
        </p>

      </div>


      <!-- STATS -->

      <div class="stats">

        <div class="stat">
          <span>المنتجات</span>
          <strong id="productsCount">0</strong>
        </div>

        <div class="stat">
          <span>الطلبات</span>
          <strong id="ordersCount">0</strong>
        </div>

        <div class="stat">
          <span>العروض</span>
          <strong id="offersCount">0</strong>
        </div>

        <div class="stat">
          <span>المتجر</span>
          <strong>فعال</strong>
        </div>

      </div>


      <h2 class="section-title">
        إدارة المتجر
      </h2>


      <!-- MENU -->

      <div class="menu">

        <button onclick="openSection('products')">

          <span class="menu-icon">👗</span>

          <strong>
            المنتجات
          </strong>

          <small>
            إضافة وتعديل وحذف المنتجات
          </small>

        </button>


        <button onclick="openSection('orders')">

          <span class="menu-icon">🛍️</span>

          <strong>
            الطلبات
          </strong>

          <small>
            مشاهدة وإدارة طلبات الزبائن
          </small>

        </button>


        <button onclick="openSection('slider')">

          <span class="menu-icon">🖼️</span>

          <strong>
            السلايدر
          </strong>

          <small>
            تغيير صور الواجهة الرئيسية
          </small>

        </button>


        <button onclick="openSection('announcement')">

          <span class="menu-icon">📢</span>

          <strong>
            الإعلان العلوي
          </strong>

          <small>
            تعديل الشريط الموجود أعلى الموقع
          </small>

        </button>


        <button onclick="openSection('settings')">

          <span class="menu-icon">⚙️</span>

          <strong>
            إعدادات المتجر
          </strong>

          <small>
            الواتساب والتوصيل والمعلومات
          </small>

        </button>


        <button onclick="openSection('social')">

          <span class="menu-icon">📱</span>

          <strong>
            السوشيال ميديا
          </strong>

          <small>
            الروابط وأعداد المتابعين
          </small>

        </button>

      </div>


      <!-- CONTENT -->

      <div id="content">

        <div class="empty">

          <div class="empty-icon">
            ⚙️
          </div>

          <h2>
            لوحة تحكم Espoza
          </h2>

          <p>
            اختر قسمًا من الأعلى للبدء.
          </p>

        </div>

      </div>

    </main>

  </div>



  <script>

    /* =========================
       PASSWORD
    ========================= */

    const ADMIN_PASSWORD = "Espoza202900$";


    /* =========================
       LOGIN
    ========================= */

    function login() {

      const password =
        document.getElementById("password").value;

      const error =
        document.getElementById("loginError");


      if (password === ADMIN_PASSWORD) {

        localStorage.setItem(
          "espoza_admin_logged",
          "true"
        );

        document
          .getElementById("loginPage")
          .classList.add("hidden");

        document
          .getElementById("adminPage")
          .classList.remove("hidden");

        error.textContent = "";

      } else {

        error.textContent =
          "كلمة السر غير صحيحة ❌";

      }

    }


    /* =========================
       LOGOUT
    ========================= */

    function logout() {

      localStorage.removeItem(
        "espoza_admin_logged"
      );

      location.reload();

    }


    /* =========================
       CHECK LOGIN
    ========================= */

    function checkLogin() {

      const logged =
        localStorage.getItem(
          "espoza_admin_logged"
        );

      if (logged === "true") {

        document
          .getElementById("loginPage")
          .classList.add("hidden");

        document
          .getElementById("adminPage")
          .classList.remove("hidden");

      }

    }


    /* =========================
       SECTIONS
    ========================= */

    function openSection(section) {

      const content =
        document.getElementById("content");


      if (section === "products") {

        content.innerHTML = `

          <h2>👗 إدارة المنتجات</h2>

          <p style="margin-top:10px;color:#777;">
            هون رح نضيف إضافة وتعديل وحذف المنتجات.
          </p>

          <button
            onclick="alert('قسم المنتجات رح يتم ربطه بقاعدة البيانات بالخطوة القادمة.')"
            style="
              margin-top:20px;
              padding:12px 18px;
              border:0;
              border-radius:10px;
              background:#111;
              color:white;
              font-family:inherit;
            "
          >
            إضافة منتج
          </button>

        `;

      }


      else if (section === "orders") {

        content.innerHTML = `

          <h2>🛍️ الطلبات</h2>

          <p style="margin-top:10px;color:#777;">
            هون رح تظهر طلبات الزبائن.
          </p>

        `;

      }


      else if (section === "slider") {

        content.innerHTML = `

          <h2>🖼️ السلايدر</h2>

          <p style="margin-top:10px;color:#777;">
            هون رح تقدر تغير صور السلايدر.
          </p>

        `;

      }


      else if (section === "announcement") {

        content.innerHTML = `

          <h2>📢 الإعلان العلوي</h2>

          <p style="margin-top:10px;color:#777;">
            هون رح تقدر تغير الإعلان الموجود أعلى الموقع.
          </p>

        `;

      }


      else if (section === "settings") {

        content.innerHTML = `

          <h2>⚙️ إعدادات المتجر</h2>

          <p style="margin-top:10px;color:#777;">
            هون رح نضع إعدادات الواتساب والتوصيل وباقي إعدادات المتجر.
          </p>

        `;

      }


      else if (section === "social") {

        content.innerHTML = `

          <h2>📱 السوشيال ميديا</h2>

          <p style="margin-top:10px;color:#777;">
            هون رح تقدر تعدل روابط وأعداد المتابعين.
          </p>

        `;

      }

    }


    /* =========================
       START
    ========================= */

    checkLogin();

  </script>

</body>
</html>
