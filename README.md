

<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GTA VI – Countdown</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Montserrat:wght@400;500;600&display=swap" rel="stylesheet">

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    min-height: 100vh;
    background:
        radial-gradient(ellipse at 50% 10%, #171923 0%, #090a0f 55%, #050609 100%);
    color: white;
    font-family: 'Bebas Neue', sans-serif;
    text-align: center;
    overflow-x: hidden;
}

.container {
    width: 100%;
    max-width: 900px;
    margin: auto;
    padding: 45px 20px 35px;
}

.logo-area {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 15px 0 35px;
    isolation: isolate;
}

.logo-area::before {
    content: "";
    position: absolute;
    z-index: -1;
    width: 420px;
    height: 190px;
    max-width: 90vw;
    background: linear-gradient(
        to bottom,
        rgba(66, 201, 233, 0.42),
        rgba(240, 90, 171, 0.32) 55%,
        rgba(245, 211, 91, 0.35)
    );
    filter: blur(65px);
    border-radius: 50%;
}

.logo {
    width: 290px;
    max-width: 75vw;
    height: auto;
    filter: drop-shadow(0 5px 15px rgba(0,0,0,0.5));
}

.eyebrow {
    font-family: 'Montserrat', sans-serif;
    font-size: 10px;
    letter-spacing: 5px;
    color: #a5a5ad;
    margin-top: 5px;
    text-transform: uppercase;
}

h1 {
    font-size: clamp(34px, 7vw, 52px);
    font-weight: normal;
    letter-spacing: 3px;
    margin: 12px 0 8px;
}

.description {
    font-family: 'Montserrat', sans-serif;
    font-size: 12px;
    color: #8d8e99;
    letter-spacing: 1px;
    margin-bottom: 35px;
}

.countdown {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 14px;
    max-width: 680px;
    margin: 0 auto;
}

.time-box {
    background: linear-gradient(145deg, #171920, #101116);
    border: 1px solid #292b35;
    border-radius: 12px;
    padding: 24px 10px 20px;
    box-shadow: 0 12px 35px rgba(0,0,0,0.25);
}

.number {
    font-size: clamp(38px, 7vw, 54px);
    line-height: 1;
    color: #fff;
    font-variant-numeric: tabular-nums;
}

.label {
    font-family: 'Montserrat', sans-serif;
    font-size: 10px;
    font-weight: 500;
    letter-spacing: 2px;
    color: #858792;
    margin-top: 12px;
    text-transform: uppercase;
}

.bottom-line {
    width: 55px;
    height: 2px;
    background: linear-gradient(to right, #42c9e9, #f05aab, #f5d35b);
    margin: 35px auto 18px;
}

.release {
    font-size: 22px;
    letter-spacing: 3px;
    color: #d7d7dc;
}

.location {
    font-family: 'Montserrat', sans-serif;
    color: #737580;
    font-size: 10px;
    letter-spacing: 3px;
    margin-top: 9px;
}

@media (max-width: 550px) {
    .container {
        padding-top: 35px;
    }

    .logo {
        width: 245px;
    }

    .countdown {
        grid-template-columns: repeat(2, 1fr);
        gap: 12px;
        max-width: 360px;
    }

    .time-box {
        padding: 21px 8px 17px;
    }

    .number {
        font-size: 43px;
    }
}
</style>
</head>

<body>

<main class="container">

    <div class="logo-area">
        <img
            class="logo"
            src="https://upload.wikimedia.org/wikipedia/commons/9/94/Grand_Theft_Auto_VI_logo.svg"
            alt="Grand Theft Auto VI Logo">
    </div>

    <div class="eyebrow">The countdown has begun</div>

    <h1>GRAND THEFT AUTO VI</h1>

    <div class="description">
        DIE RÜCKKEHR NACH VICE CITY
    </div>

    <section class="countdown">
        <div class="time-box">
            <div class="number" id="days">000</div>
            <div class="label">Tage</div>
        </div>

        <div class="time-box">
            <div class="number" id="hours">00</div>
            <div class="label">Stunden</div>
        </div>

        <div class="time-box">
            <div class="number" id="minutes">00</div>
            <div class="label">Minuten</div>
        </div>

        <div class="time-box">
            <div class="number" id="seconds">00</div>
            <div class="label">Sekunden</div>
        </div>
    </section>

    <div class="bottom-line"></div>

    <div class="release">19. NOVEMBER 2026</div>
    <div class="location">VICE CITY • LEONIDA</div>

</main>

<script>
const releaseDate = new Date(2026, 10, 19, 0, 0, 0).getTime();

function updateCountdown() {
    const now = Date.now();
    const distance = releaseDate - now;

    if (distance <= 0) {
        document.querySelector(".countdown").innerHTML =
            '<div class="release">GTA VI IST DA!</div>';
        return;
    }

    document.getElementById("days").textContent =
        Math.floor(distance / 86400000);

    document.getElementById("hours").textContent =
        String(Math.floor(distance / 3600000) % 24).padStart(2, "0");

    document.getElementById("minutes").textContent =
        String(Math.floor(distance / 60000) % 60).padStart(2, "0");

    document.getElementById("seconds").textContent =
        String(Math.floor(distance / 1000) % 60).padStart(2, "0");
}

updateCountdown();
setInterval(updateCountdown, 1000);
</script>

</body>
</html>
