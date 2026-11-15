<!DOCTYPE html>
<html lang="de" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grand Theft Auto VI — Offizieller Countdown | Rockstar Games</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        rockstar: ['"Helvetica Neue"', 'Helvetica', 'Arial', 'sans-serif'],
                        display: ['"Archivo Black"', '"Helvetica Neue"', 'sans-serif'],
                        mono: ['"Barlow Condensed"', 'sans-serif']
                    },
                    colors: {
                        rockstarYellow: '#fcaf17',
                        rockstarDark: '#09060d'
                    }
                }
            }
        }
    </script>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Archivo+Black&family=Barlow+Condensed:wght@700;900&family=Plus+Jakarta+Sans:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background-color: #050308;
            color: #ffffff;
            overflow-x: hidden;
        }
        .rockstar-font {
            font-family: 'Archivo Black', sans-serif;
            letter-spacing: -0.03em;
        }
        .countdown-num {
            font-family: 'Barlow Condensed', sans-serif;
            font-weight: 950;
            font-variant-numeric: tabular-nums;
            letter-spacing: -0.02em;
        }
        @keyframes subtleZoom {
            0% { transform: scale(1); }
            50% { transform: scale(1.04); }
            100% { transform: scale(1); }
        }
        .animate-artwork {
            animation: subtleZoom 25s ease-in-out infinite;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col bg-rockstarDark text-white relative selection:bg-[#fcaf17] selection:text-black">

    <!-- HINTERGRUND: Offizielles Rockstar Games Artwork von Lucia & Jason (nach unten verschoben) -->
    <div id="vice-bg" class="fixed inset-0 z-0 overflow-hidden">
        <img 
            id="official-lucia-jason-bg"
            src="https://media-rockstargames-com.akamaized.net/rockstargames-newsite/img/global/downloads/wallpapers/games/gta-vi-key-2160x2160.jpg"
            alt="Lucia und Jason — Grand Theft Auto VI Offizielles Rockstar Games Artwork"
            referrerpolicy="no-referrer"
            onerror="this.onerror=null; this.src='https://media-rockstargames-com.akamaized.net/rockstargames-newsite/img/global/games/fob/640/VI.jpg';"
            class="w-full h-full object-cover object-bottom opacity-85 animate-artwork select-none"
        />

        <!-- Kino-Vignette für perfekten Kontrast -->
        <div class="absolute inset-0 bg-gradient-to-b from-black/80 via-black/40 to-black/95"></div>
        <div class="absolute inset-0 bg-[radial-gradient(circle_at_center,transparent_20%,rgba(5,3,8,0.92)_100%)]"></div>
    </div>

    <!-- FIXIERTE ROCKSTAR GAMES TOP NAVIGATION BAR -->
    <header class="fixed top-0 left-0 right-0 z-50 bg-[#09060d]/90 backdrop-blur-md border-b border-white/10 px-4 sm:px-8 py-3 flex items-center justify-between transition-all">
        <div class="flex items-center space-x-6">
            <span class="font-bold tracking-widest text-xs uppercase text-white">Grand Theft Auto VI</span>
        </div>

        <!-- Mitte: Rockstar Navigation -->
        <nav class="hidden md:flex items-center space-x-8 text-[12px] font-extrabold tracking-[0.18em] uppercase text-zinc-300">
            <a href="#countdown" class="text-white border-b-2 border-[#fcaf17] py-6">Countdown</a>
            <button onclick="openInfoModal('leonida')" class="hover:text-white transition-colors uppercase py-6">Leonida</button>
            <button onclick="openInfoModal('characters')" class="hover:text-white transition-colors uppercase py-6">Lucia &amp; Jason</button>
            <button onclick="openInfoModal('release')" class="hover:text-white transition-colors uppercase py-6">Release</button>
        </nav>

        <!-- Rechts: Release Datum Badge -->
        <div class="flex items-center space-x-3">
            <button onclick="openInfoModal('release')" class="px-4 py-2 rounded-md bg-white text-black hover:bg-[#fcaf17] font-black text-[11px] tracking-[0.14em] uppercase transition shadow">
                19. NOV 2026
            </button>
        </div>
    </header>

    <!-- ZENTRALE HERO-SEKTION: COUNTDOWN -->
    <main id="countdown" class="relative z-20 flex-1 flex flex-col items-center justify-center px-4 sm:px-6 py-12 sm:py-16 text-center max-w-6xl mx-auto w-full pt-24 sm:pt-28">
        
        <!-- Headline -->
        <h1 class="text-3xl sm:text-5xl md:text-6xl rockstar-font uppercase tracking-tight text-white mb-8 drop-shadow-lg">
            Willkommen in Leonida
        </h1>

        <!-- COUNTDOWN-CONTAINER (Optimierte Breiten und feste Spalten gegen Ineinandergreifen) -->
        <div class="grid grid-cols-2 lg:grid-cols-4 gap-4 sm:gap-6 w-full max-w-5xl mb-12">
            <!-- Tage -->
            <div class="relative group">
                <div class="absolute -inset-0.5 bg-gradient-to-r from-[#fcaf17] to-pink-600 rounded-2xl blur opacity-30 group-hover:opacity-75 transition duration-500"></div>
                <div class="relative bg-black/85 backdrop-blur-2xl border border-white/20 rounded-2xl p-6 shadow-2xl flex flex-col items-center justify-center min-h-[160px]">
                    <div id="days" class="countdown-num text-7xl sm:text-8xl text-transparent bg-clip-text bg-gradient-to-b from-white via-zinc-100 to-zinc-400 text-center w-full">0</div>
                    <div class="text-[11px] sm:text-xs font-black tracking-[0.3em] text-[#fcaf17] uppercase mt-2">Tage</div>
                </div>
            </div>
            <!-- Stunden -->
            <div class="relative group">
                <div class="absolute -inset-0.5 bg-gradient-to-r from-[#fcaf17] to-pink-600 rounded-2xl blur opacity-30 group-hover:opacity-75 transition duration-500"></div>
                <div class="relative bg-black/85 backdrop-blur-2xl border border-white/20 rounded-2xl p-6 shadow-2xl flex flex-col items-center justify-center min-h-[160px]">
                    <div id="hours" class="countdown-num text-7xl sm:text-8xl text-transparent bg-clip-text bg-gradient-to-b from-white via-zinc-100 to-zinc-400 text-center w-full">0</div>
                    <div class="text-[11px] sm:text-xs font-black tracking-[0.3em] text-[#fcaf17] uppercase mt-2">Stunden</div>
                </div>
            </div>
            <!-- Minuten -->
            <div class="relative group">
                <div class="absolute -inset-0.5 bg-gradient-to-r from-[#fcaf17] to-pink-600 rounded-2xl blur opacity-30 group-hover:opacity-75 transition duration-500"></div>
                <div class="relative bg-black/85 backdrop-blur-2xl border border-white/20 rounded-2xl p-6 shadow-2xl flex flex-col items-center justify-center min-h-[160px]">
                    <div id="minutes" class="countdown-num text-7xl sm:text-8xl text-transparent bg-clip-text bg-gradient-to-b from-white via-zinc-100 to-zinc-400 text-center w-full">0</div>
                    <div class="text-[11px] sm:text-xs font-black tracking-[0.3em] text-[#fcaf17] uppercase mt-2">Minuten</div>
                </div>
            </div>
            <!-- Sekunden -->
            <div class="relative group">
                <div class="absolute -inset-0.5 bg-gradient-to-r from-[#fcaf17] to-pink-600 rounded-2xl blur opacity-30 group-hover:opacity-75 transition duration-500"></div>
                <div class="relative bg-black/85 backdrop-blur-2xl border border-white/20 rounded-2xl p-6 shadow-2xl flex flex-col items-center justify-center min-h-[160px]">
                    <div id="seconds" class="countdown-num text-7xl sm:text-8xl text-transparent bg-clip-text bg-gradient-to-b from-white via-zinc-100 to-zinc-400 text-center w-full">0</div>
                    <div class="text-[11px] sm:text-xs font-black tracking-[0.3em] text-[#fcaf17] uppercase mt-2">Sekunden</div>
                </div>
            </div>
        </div>

        <!-- Action Buttons -->
        <div class="flex flex-wrap justify-center gap-4">
            <button onclick="openInfoModal('leonida')" class="px-8 py-3.5 rounded-lg bg-[#fcaf17] text-black font-black text-xs tracking-[0.18em] uppercase hover:bg-white transition shadow-lg">
                Über Leonida
            </button>
            <button onclick="openInfoModal('characters')" class="px-8 py-3.5 rounded-lg bg-white/10 backdrop-blur-md border border-white/20 text-white font-black text-xs tracking-[0.18em] uppercase hover:bg-white/20 transition shadow-lg">
                Lucia &amp; Jason
            </button>
        </div>
    </main>

    <!-- FOOTER -->
    <footer class="relative z-20 py-8 px-6 text-center text-zinc-500 text-xs border-t border-white/10 bg-black/80 backdrop-blur-md">
        <p>&copy; 2026 Rockstar Games, Inc. Alle Rechte vorbehalten. Offizieller Countdown-Hub.</p>
    </footer>

    <!-- MODAL POPUP -->
    <div id="infoModal" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/80 backdrop-blur-md hidden">
        <div class="bg-[#120c1a] border border-white/20 rounded-2xl max-w-lg w-full p-6 sm:p-8 relative shadow-2xl">
            <button onclick="closeInfoModal()" class="absolute top-4 right-4 text-zinc-400 hover:text-white text-xl font-bold">&times;</button>
            <h2 id="modalTitle" class="text-2xl rockstar-font mb-4 text-[#fcaf17]"></h2>
            <p id="modalText" class="text-zinc-300 text-sm leading-relaxed mb-6"></p>
            <button onclick="closeInfoModal()" class="w-full py-3 bg-white text-black font-black rounded-lg text-xs tracking-widest uppercase hover:bg-[#fcaf17] transition">Schließen</button>
        </div>
    </div>

        <!-- SCRIPT -->
        <script>
        // Zielzeitpunkt: 19. November 2026, 00:00:00 Uhr
        const targetDate = new Date('2026-11-19T00:00:00').getTime();

        function updateCountdown() {
            const now = new Date().getTime();
            const difference = targetDate - now;

            if (difference > 0) {
                const days = Math.floor(difference / (1000 * 60 * 60 * 24));
                const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((difference % (1000 * 60)) / 1000);

                // Live-Aktualisierung der Ziffern ohne führende Nullen
                document.getElementById('days').innerText = days;
                document.getElementById('hours').innerText = hours;
                document.getElementById('minutes').innerText = minutes;
                document.getElementById('seconds').innerText = seconds;
            } else {
                document.getElementById('days').innerText = '0';
                document.getElementById('hours').innerText = '0';
                document.getElementById('minutes').innerText = '0';
                document.getElementById('seconds').innerText = '0';
            }
        }

        setInterval(updateCountdown, 1000);
        updateCountdown();

        // Modal Content
        const modals = {
            leonida: {
                title: "Der Staat Leonida",
                text: "Grand Theft Auto VI führt die Spieler in den pulsierenden und sonnendurchfluteten Staat Leonida, Heimat der Neon-Straßen von Vice City und darüber hinaus – die bisher größte und immersive Spielwelt in der Geschichte von Rockstar Games."
            },
            characters: {
                title: "Lucia & Jason",
                text: "Im Zentrum der Geschichte stehen Lucia und Jason. Als kriminelles Duo schlagen sie sich im Herzen von Leonida durch, geprägt von Vertrauen, Verrat und dem ultimativen Raubzug."
            },
            release: {
                title: "Release-Information",
                text: "Grand Theft Auto VI erscheint offiziell am 19. November 2026 für PlayStation 5 und Xbox Series X|S."
            }
        };

        function openInfoModal(type) {
            const data = modals[type];
            if (data) {
                document.getElementById('modalTitle').innerText = data.title;
                document.getElementById('modalText').innerText = data.text;
                document.getElementById('infoModal').classList.remove('hidden');
            }
        }

        function closeInfoModal() {
            document.getElementById('infoModal').classList.add('hidden');
        }
    </script>
</body>
</html>
