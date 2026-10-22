

<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sophia ✦</title>

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
  padding: 20px;
  font-family: Arial, sans-serif;
  color: white;
  background:
    radial-gradient(circle at 15% 15%, #632c91, transparent 40%),
    radial-gradient(circle at 85% 85%, #8d286c, transparent 40%),
    #090711;
}

.card {
  width: 100%;
  max-width: 430px;
  padding: 38px 24px;
  text-align: center;
  border: 1px solid #a66bd566;
  border-radius: 28px;
  background: #ffffff0c;
  backdrop-filter: blur(20px);
  box-shadow: 0 0 60px #a855f722;
  animation: appear .5s ease;
}

.tag {
  color: #e1b8ff;
  font-size: 12px;
  letter-spacing: 4px;
  margin-bottom: 25px;
}

h1 {
  font-size: 43px;
  letter-spacing: 5px;
  background: linear-gradient(90deg, #fff, #dca6ff, #ffb9e9);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 24px;
}

.line {
  width: 65px;
  height: 3px;
  margin: 0 auto 25px;
  border-radius: 5px;
  background: linear-gradient(90deg, #a855f7, #ff8bd8);
}

.message {
  font-size: 24px;
  font-weight: bold;
  line-height: 1.6;
}

.highlight {
  color: #ddaaff;
}

.info {
  display: none;
}

.info.show {
  display: block;
  animation: appear .4s ease;
}

.home.hide {
  display: none;
}

.info-text {
  margin: 25px 0;
  padding: 23px 12px;
  border: 1px solid #c084fc55;
  border-radius: 18px;
  background: #a855f718;
  font-size: 23px;
  font-weight: bold;
  line-height: 1.5;
}

button {
  margin-top: 28px;
  padding: 15px 24px;
  width: 100%;
  border: none;
  border-radius: 15px;
  color: white;
  font-size: 15px;
  font-weight: bold;
  cursor: pointer;
  background: linear-gradient(100deg, #853bea, #d34db7);
  box-shadow: 0 5px 25px #a855f744;
  transition: transform .2s, box-shadow .2s;
}

button:active {
  transform: scale(.97);
}

.footer {
  margin-top: 25px;
  color: #b9a8ca;
  font-size: 10px;
  letter-spacing: 3px;
}

@keyframes appear {
  from { opacity: 0; transform: translateY(12px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>
</head>

<body>
<div class="card">

  <section class="home" id="home">
    <div class="tag">✦ PERSONAL PAGE ✦</div>
    <h1>SOPHIA</h1>
    <div class="line"></div>

    <div class="message">
      Sophia ist 14,<br>
      verhält sich aber<br>
      wie eine <span class="highlight">7-Jährige.</span>
    </div>

    <p class="footer">MEHR ÜBER SOPHIA</p>

    <button onclick="showInfo()">
      ✨ Informationen über sie →
    </button>
  </section>

  <section class="info" id="info">
    <div class="tag">✦ ÜBER SOPHIA ✦</div>
    <h1>INFO</h1>
    <div class="line"></div>

    <div class="info-text">
      Sie ist klein<br>
      und frech 😜
    </div>

    <p style="color:#c7b5d8; line-height:1.6;">
      Das ist Sophia –<br>
      immer mit ihrem eigenen Kopf!
    </p>

    <button onclick="showHome()">
      ← Zurück zur Startseite
    </button>
  </section>

</div>

<script>
function showInfo() {
  document.getElementById("home").classList.add("hide");
  document.getElementById("info").classList.add("show");
}

function showHome() {
  document.getElementById("info").classList.remove("show");
  document.getElementById("home").classList.remove("hide");
}
</script>

</body>
</html>
