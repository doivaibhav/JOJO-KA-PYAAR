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
      font-family: system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
      text-align: center;
      color: #333;
      overflow: hidden;
    }

    .card {
      background: white;
      padding: 36px 28px;
      border-radius: 18px;
      max-width: 420px;
      box-shadow: 0 25px 50px rgba(0,0,0,0.12);
    }

    h1 {
      font-size: 28px;
      margin-bottom: 12px;
    }

    p {
      font-size: 16px;
      line-height: 1.6;
      margin-bottom: 24px;
    }

    button {
      font-size: 16px;
      padding: 12px 22px;
      border-radius: 999px;
      border: none;
      cursor: pointer;
      margin: 8px;
      position: relative;
    }

    .yes {
      background: #ff4d6d;
      color: white;
    }

    .hell {
      background: #ffd166;
      color: #333;
      font-weight: 600;
    }

    .runaway {
      transition: transform 0.12s ease;
    }

    img {
      max-width: 100%;
      border-radius: 12px;
      margin-top: 16px;
    }

    .hidden {
      display: none;
    }
  </style>
</head>
<body>

  <!-- AUDIO FILES -->
  <audio id="yesSong" preload="auto">
    <source src="hasi-ban-gaye.mp3" type="audio/mpeg">
  </audio>

  <audio id="hellSong" preload="auto">
    <source src="make-you-mine.mp3" type="audio/mpeg">
  </audio>

  <!-- QUESTION -->
  <div class="card" id="question">
    <h1>JOJO Ka SACCHA PYAAR ❤️</h1>

    <p>
      JOJO KA SACCHA PYAAR KAUN HAI?
    </p>

    <h1>Think before you choose</h1>

    <button class="yes" onclick="yesClick()">Anupriya</button>
    <button class="SHUBHI runaway" id="runawayBtn" onclick="SUBHI()">
      SUBHI BKL 😌
    </button>
  </div>

  <!-- Anupriya SCREEN -->
  <div class="card hidden" id="yesCard">
    <h1>Kamino Saalo</h1>
    <p>
  </div>

  <!-- Subhi BKL SCREEN -->
  <div class="card hidden" id="gifCard">
    <h1>10 crore ruppe </h1>
    <p>Asli kamine dost tum hi ho</p>

    <img src="celebrate3.gif" alt="Celebration GIF" />

    <p>JOJO ko Shaadi mubarak</p>
  </div>

  <script>
    const runawayBtn = document.getElementById("runawayBtn");
    let unlocked = false;

    // Unlock SuBHI BKL after 40 seconds
    setTimeout(() => {
      unlocked = true;
      runawayBtn.classList.remove("runaway");
      runawayBtn.style.transform = "translate(0,0)";
    }, 30000);

    document.addEventListener("mousemove", (e) => {
      if (unlocked) return;

      const rect = runawayBtn.getBoundingClientRect();
      const btnX = rect.left + rect.width / 2;
      const btnY = rect.top + rect.height / 2;

      const distance = Math.hypot(e.clientX - btnX, e.clientY - btnY);

      if (distance < 160) {
        const moveX = (Math.random() - 0.5) * window.innerWidth * 0.8;
        const moveY = (Math.random() - 0.5) * window.innerHeight * 0.6;
        runawayBtn.style.transform = `translate(${moveX}px, ${moveY}px)`;
      }
    });

    function yesClick() {
      document.getElementById("question").classList.add("hidden");
      document.getElementById("yesCard").classList.remove("hidden");

      const song = document.getElementById("yesSong");

      song.onloadedmetadata = () => {
        song.currentTime = 44; // 🎵 YES SONG START TIME
        song.play();
      };

      if (song.readyState >= 1) {
        song.currentTime = 44;
        song.play();
      }
    }

    function hellYes() {
      if (!unlocked) return;

      document.getElementById("question").classList.add("hidden");
      document.getElementById("gifCard").classList.remove("hidden");

      const song = document.getElementById("hellSong");

      song.onloadedmetadata = () => {
        song.currentTime = 47; // 🎵 HELL YEAH SONG START TIME
        song.play();
      };

      if (song.readyState >= 1) {
        song.currentTime = 47;
        song.play();
      }
    }
  </script>

</body>
</html>
