<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>JOJO KI SHAADI ❤️</title>

  <style>
    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(135deg, #ffdde1, #fff1f4);
      font-family: system-ui, sans-serif;
      text-align: center;
      overflow: hidden;
    }

    .card {
      background: white;
      padding: 36px 28px;
      border-radius: 18px;
      width: 420px;
      box-shadow: 0 25px 50px rgba(0,0,0,0.12);
      position: relative;
    }

    button {
      padding: 12px 22px;
      border-radius: 999px;
      border: none;
      cursor: pointer;
      margin: 8px;
      font-size: 16px;
    }

    .yes {
      background: #ff4d6d;
      color: white;
    }

    .subhi {
      background: #ffd166;
      font-weight: 600;
      position: absolute;
    }

    .hidden {
      display: none;
    }
  </style>
</head>
<body>

  <!-- AUDIO -->
  <audio id="yesSong" src="hasi-ban-gaye.mp3"></audio>
  <audio id="hellSong" src="make-you-mine.mp3"></audio>

  <!-- QUESTION -->
  <div class="card" id="question">
    <h2>JOJO Ka SACCHA PYAAR ❤️</h2>
    <p>JOJO KA SACCHA PYAAR KAUN HAI?</p>

    <button class="yes" onclick="chooseAnupriya()">Anupriya</button>
    <button class="subhi" id="subhiBtn" onclick="chooseSubhi()">SUBHI BKL 😌</button>
  </div>

  <!-- ANUPRIYA -->
  <div class="card hidden" id="anuCard">
    <h2>Kamino Saalo 😌</h2>
    <p>Soft choice. Safe choice.</p>
  </div>

  <!-- SUBHI -->
  <div class="card hidden" id="subhiCard">
    <h2>10 crore rupaye 💸</h2>
    <p>Asli kamine dost tum hi ho</p>
    <img src="celebrate3.gif" width="100%" />
    <p>JOJO ko Shaadi mubarak 🎉</p>
  </div>

  <script>
    const subhiBtn = document.getElementById("subhiBtn");
    const card = document.getElementById("question");

    let unlocked = false;
    let handler;

    function moveButton() {
      if (unlocked) return;

      const maxX = card.clientWidth - subhiBtn.offsetWidth;
      const maxY = card.clientHeight - subhiBtn.offsetHeight;

      const x = Math.random() * maxX;
      const y = Math.random() * maxY;

      subhiBtn.style.left = x + "px";
      subhiBtn.style.top = y + "px";
    }

    // Initial position
    moveButton();

    handler = () => moveButton();
    card.addEventListener("mousemove", handler);

    // Unlock after 40 seconds
    setTimeout(() => {
      unlocked = true;
      card.removeEventListener("mousemove", handler);

      subhiBtn.style.left = "50%";
      subhiBtn.style.top = "75%";
      subhiBtn.style.transform = "translateX(-50%)";
    }, 40000);

    function chooseAnupriya() {
      question.classList.add("hidden");
      anuCard.classList.remove("hidden");

      const song = document.getElementById("yesSong");
      song.currentTime = 44;
      song.play();
    }

    function chooseSubhi() {
      if (!unlocked) return;

      question.classList.add("hidden");
      subhiCard.classList.remove("hidden");

      const song = document.getElementById("hellSong");
      song.currentTime = 47;
      song.play();
    }
  </script>

</body>
</html>
