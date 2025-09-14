<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Menu Naruto H5GG</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: Arial, sans-serif;
    }
    .menu {
      width: 320px;
      background: rgba(0,0,0,0.8);
      border-radius: 12px;
      padding: 20px;
      color: white;
      backdrop-filter: blur(5px);
      box-shadow: 0 4px 15px rgba(0,0,0,0.6);
    }
    .menu h2 {
      text-align: center;
      margin-bottom: 15px;
      color: #ffcc00;
      text-shadow: 0 0 5px #ff6600;
    }
    .login-box {
      display: flex;
      gap: 5px;
      margin-bottom: 15px;
    }
    .login-box input {
      flex: 1;
      padding: 6px;
      border-radius: 5px;
      border: none;
      outline: none;
    }
    .login-box button {
      padding: 6px 10px;
      border: none;
      border-radius: 5px;
      background: #ff6600;
      color: white;
      cursor: pointer;
    }
    .login-box button:hover {
      background: #ff3300;
    }
    .hidden {
      display: none;
    }
    .item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin: 10px 0;
    }
    .toggle {
      width: 40px;
      height: 20px;
      border-radius: 20px;
      background: #555;
      position: relative;
      cursor: pointer;
    }
    .toggle::before {
      content: "";
      position: absolute;
      top: 2px;
      left: 2px;
      width: 16px;
      height: 16px;
      border-radius: 50%;
      background: white;
      transition: all 0.3s;
    }
    .toggle.active {
      background: #ff6600;
    }
    .toggle.active::before {
      transform: translateX(20px);
    }
  </style>
</head>
<body>
  <div class="menu">
    <h2>H5GG Naruto Menu</h2>

    <!-- Key đăng nhập -->
    <div id="loginSection">
      <div class="login-box">
        <input type="text" id="keyInput" placeholder="Nhập key...">
        <button id="loginBtn">OK</button>
      </div>
    </div>

    <!-- Các chức năng (ẩn mặc định) -->
    <div id="featuresSection" class="hidden">
      <div class="item"><span>Nhẹ tâm</span><div class="toggle"></div></div>
      <div class="item"><span>Aim lock</span><div class="toggle"></div></div>
      <div class="item"><span>Data</span><div class="toggle"></div></div>
      <div class="item"><span>Config</span><div class="toggle"></div></div>
      <div class="item"><span>Bám tâm</span><div class="toggle"></div></div>
      <div class="item"><span>Fix lố</span><div class="toggle"></div></div>
    </div>
  </div>

  <script>
    // Toggle switch
    document.querySelectorAll('.toggle').forEach(toggle => {
      toggle.addEventListener('click', () => {
        toggle.classList.toggle('active');
      });
    });

    // Check key đăng nhập
    document.getElementById("loginBtn").addEventListener("click", function() {
      let key = document.getElementById("keyInput").value.trim();
      if (key === "naruto123") {
        alert("✅ Đăng nhập thành công!");
        document.getElementById("loginSection").classList.add("hidden");
        document.getElementById("featuresSection").classList.remove("hidden");
      } else {
        alert("❌ Key sai, vui lòng thử lại.");
      }
    });
  </script>
</body>
</html>
