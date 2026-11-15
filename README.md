
<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Countdown</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #090909, #1b1b1b);
      color: white;
    }

    .container {
      text-align: center;
      padding: 30px;
    }

    h1 {
      font-size: 38px;
      margin-bottom: 15px;
    }

    p {
      color: #aaa;
      margin-bottom: 35px;
    }

    .countdown {
      display: flex;
      gap: 15px;
      justify-content: center;
      flex-wrap: wrap;
    }

    .time-box {
      background: #151515;
      border: 1px solid #333;
      border-radius: 15px;
      width: 130px;
      padding: 25px 10px;
      box-shadow: 0 0 25px rgba(255,255,255,0.08);
    }

    .number {
      display: block;
      font-size: 45px;
      font-weight: bold;
    }

    .label {
      display: block;
      margin-top: 8px;
      color: #999;
      font-size: 14px;
      text-transform: uppercase;
    }

    #finished {
      display: none;
      font-size: 30px;
      font-weight: bold;
    }
  </style>
</head>

<body>

  <div class="container">
    <h1>COUNTDOWN</h1>
    <p>Der Countdown endet am 19. November um 00:00 Uhr.</p>

    <div class="countdown" id="countdown">
      <div class="time-box">
        <span class="number" id="days">00</span>
        <span class="label">Tage</span>
      </div>

      <div class="time-box">
        <span class="number" id="hours">00</span>
        <span class="label">Stunden</span>
      </div>

      <div class="time-box">
        <span class="number" id="minutes">00</span>
        <span class="label">Minuten</span>
      </div>

      <div class="time-box">
        <span class="number" id="seconds">00</span>
        <span class="label">Sekunden</span>
      </div>
    </div>

    <div id="finished">
      🎉 Der Countdown ist vorbei!
    </div>
  </div>

  <script>
    // Ziel: 19. November 2026, 00:00 Uhr
    const targetDate = new Date("November 19, 2026 00:00:00").getTime();

    function updateCountdown() {
      const now = new Date().getTime();
      const difference = targetDate - now;

      if (difference <= 0) {
        document.getElementById("countdown").style.display = "none";
        document.getElementById("finished").style.display = "block";
        return;
      }

      const days = Math.floor(difference / (1000 * 60 * 60 * 24));
      const hours = Math.floor(
        (difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
      );
      const minutes = Math.floor(
        (difference % (1000 * 60 * 60)) / (1000 * 60)
      );
      const seconds = Math.floor(
        (difference % (1000 * 60)) / 1000
      );

      document.getElementById("days").textContent =
        String(days).padStart(2, "0");

      document.getElementById("hours").textContent =
        String(hours).padStart(2, "0");

      document.getElementById("minutes").textContent =
        String(minutes).padStart(2, "0");

      document.getElementById("seconds").textContent =
        String(seconds).padStart(2, "0");
    }

    updateCountdown();
    setInterval(updateCountdown, 1000);
  </script>

</body>
</html>
