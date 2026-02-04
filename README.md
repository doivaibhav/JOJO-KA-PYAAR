<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>JOJO KI SHAADI ❤️</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(135deg, #ffe0e6, #fff);
      font-family: system-ui, sans-serif;
      text-align: center;
    }

    .card {
      background: white;
      padding: 30px;
      border-radius: 16px;
      width: 360px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.15);
      position: relative;
    }

    h1 {
      margin-bottom: 10px;
    }

    p {
      margin-bottom: 20px;
    }

    button {
      padding: 12px 20px;
      border-radius: 999px;
      border: none;
      font-size: 16px;
      cursor: pointer;
      margin: 8px;
    }

    .anu {
      background: #ff4d6d;
      color: white;
    }

    .shubhi {
      background: #ffd166;
      position: absolute;
    }

    img {
      width: 100%;
      border-radius: 12px;
      margin-top: 15px;
    }

    .hidden {
      display: none;
    }
  </style>
</head>
<body>

  <!-- QUESTION CARD -->
  <div class="card" id="questionCard">
    <h1>JOJO KI SHAADI ❤️</h1>
    <p>JOJO ko sabse zyada kaun pasand hai?</p>

    <button class="anu" onclick="chooseAnu()">Anupriya</button>
    <button class="shubhi" id="shubhiBtn" onclick="chooseShubhi()">
      Shubhi BKL 😌
    </button>
  </div>

  <!-- ANUPRIYA RESULT -->
  <div class="card hidden" id="anuCard">
    <h1>😏</h1>
    <p>Ek baar aur sooch le</p>
    <img src="Anupriya1.gif" />
  </div>

  <!-- SHUBHI RESULT -->
  <div class="card hidden" id="shubhiCard">
    <h1>😂</h1>
    <p>Asli kamine dost tum hi ho</p>
    <img src="celebrate3.gif" />
  </div>

  <script>
    const shubhiBtn = document.getElementById("shubhiBtn");
    const questionCard = document.getElementById("questionCard");

    let running = true;

    function moveShubhi() function moveShubhi() {
  if (!running) return;

  const maxX = window.innerWidth - shubhiBtn.offsetWidth;
  const maxY = window.innerHeight - shubhiBtn.offsetHeight;

  const x = Math.random() * maxX;
  const y = Math.random() * maxY;

  shubhiBtn.style.left = x + "px";
  shubhiBtn.style.top = y + "px";
}

    }

    // Initial position
    moveShubhi();

    // Move on hover
    shubhiBtn.addEventListener("mouseenter", moveShubhi);

    // Stop running after 40 seconds
    setTimeout(() => {
      running = false;
      shubhiBtn.style.left = "50%";
      shubhiBtn.style.top = "70%";
      shubhiBtn.style.transform = "translateX(-50%)";
    }, 40000);

    function chooseAnu() {
      document.getElementById("questionCard").classList.add("hidden");
      document.getElementById("anuCard").classList.remove("hidden");
    }

    function chooseShubhi() {
      if (running) return;

      document.getElementById("questionCard").classList.add("hidden");
      document.getElementById("shubhiCard").classList.remove("hidden");
    }
  </script>

</body>
</html>
