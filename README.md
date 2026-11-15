







<!DOCTYPE html>
<html lang="de" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grand Theft Auto VI — Rockstar Games</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">

    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        'sans': ['Inter', 'sans-serif'],
                        'display': ['Bebas Neue', 'sans-serif'],
                    },
                    colors: {
                        'rstar-gold': '#fcaf17',
                        'rstar-black': '#0b0b0b',
                        'rstar-surface': '#141414',
                        'vice-pink': '#ff2e93',
                        'vice-purple': '#7c2ae8',
                        'vice-orange': '#ff7a00',
                    }
                }
            }
        }
    </script>

    <style>
        body {
            background-color: #0b0b0b;
            color: #ffffff;
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
            margin: 0;
        }

        /* Subtiles Kino-Filmkorn wie auf rockstargames.com/VI */
        .rstar-grain {
            position: fixed;
            inset: 0;
            pointer-events: none;
            z-index: 40;
            opacity: 0.035;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.8' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
        }

        /* Rockstar Games Countdown Module */
        .rstar-unit-card {
            position: relative;
            background: linear-gradient(180deg, rgba(22, 22, 28, 0.85) 0%, rgba(10, 10, 14, 0.94) 100%);
            backdrop-filter: blur(22px);
            -webkit-backdrop-filter: blur(22px);
            border: 1px solid rgba(255, 255, 255, 0.16);
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.85), inset 0 1px 0 rgba(255, 255, 255, 0.15);
            transition: transform 0.25s cubic-bezier(0.22, 1, 0.36, 1), border-color 0.25s ease, box-shadow 0.25s ease;
            overflow: hidden;
        }

        .rstar-unit-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 2px;
            background: linear-gradient(90deg, transparent, rgba(255, 46, 147, 0.8), rgba(255, 122, 0, 0.8), transparent);
            opacity: 0.75;
        }

        /* Horizontale Split-Flap-Linie wie bei echten Studio-Countdowns */
        .rstar-unit-card::after {
            content: '';
            position: absolute;
            left: 0;
            right: 0;
            top: 50%;
            height: 1px;
            background: rgba(0, 0, 0, 0.55);
            box-shadow: 0 1px 0 rgba(255, 255, 255, 0.06);
            pointer-events: none;
        }

        .rstar-unit-card:hover {
            transform: translateY(-4px) scale(1.015);
            border-color: rgba(255, 46, 147, 0.75);
            box-shadow: 0 28px 60px rgba(255, 46, 147, 0.28), inset 0 1px 0 rgba(255, 255, 255, 0.25);
        }

        @keyframes digitPulse {
            0% { transform: scale(1.06); filter: brightness(1.3); }
            100% { transform: scale(1); filter: brightness(1); }
        }
        .digit-tick {
            animation: digitPulse 0.28s ease-out;
        }

        /* Langsamer Ken-Burns-Zoom auf dem offiziellen Key-Art */
        @keyframes slowPan {
            0% { transform: scale(1.03) translate(0%, 0%); }
            50% { transform: scale(1.09) translate(-1%, -0.5%); }
            100% { transform: scale(1.03) translate(0%, 0%); }
        }
        .animate-keyart {
            animation: slowPan 28s ease-in-out infinite;
        }

        /* Sanftes Schweben des offiziellen Logos */
        @keyframes logoFloat {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-6px); }
        }
        .animate-logo {
            animation: logoFloat 6s ease-in-out infinite;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between relative selection:bg-vice-pink selection:text-white">

    <!-- Filmkorn Overlay -->
    <div class="rstar-grain"></div>

    <!-- HINTERGRUND: Offizielles Rockstar Games GTA VI Key-Artwork (Lucia & Jason) -->
    <div class="fixed inset-0 z-0 overflow-hidden bg-[#0b0b0b]">
        <img
            id="keyart-bg"
            src="https://media-rockstargames-com.akamaized.net/rockstargames-newsite/img/global/downloads/wallpapers/games/gta-vi-key-3840x2160.jpg"
            onerror="this.onerror=null; this.src='https://media-rockstargames-com.akamaized.net/rockstargames-newsite/img/global/downloads/wallpapers/games/gta-vi-key-2160x2160.jpg';"
            alt="Grand Theft Auto VI — Lucia & Jason Key Artwork"
            referrerpolicy="no-referrer"
            class="w-full h-full object-cover object-center animate-keyart transition-all duration-700"
            style="filter: brightness(0.72) contrast(1.06) saturate(1.12);"
        />
        <!-- Kino-Vignette im Rockstar-Stil für gestochen scharfen Kontrast -->
        <div class="absolute inset-0 bg-gradient-to-b from-black/80 via-black/35 to-black/95"></div>
        <div class="absolute inset-0 bg-[radial-gradient(circle_at_center,transparent_25%,rgba(11,11,11,0.88)_100%)]"></div>
    </div>

    <!-- OFFIZIELLE ROCKSTAR GAMES TOP NAVIGATION BAR -->
    <header class="relative z-30 w-full bg-[#0b0b0b]/90 backdrop-blur-md border-b border-white/10">
        <div class="max-w-[1440px] mx-auto px-4 sm:px-8 h-16 sm:h-20 flex items-center justify-between">
            
            <!-- Links: Rockstar Logo & GTA VI Logo -->
            <div class="flex items-center space-x-4 sm:space-x-6">
                <!-- Rockstar R* Logo -->
                <div class="flex items-center space-x-1.5 bg-[#fcaf17] text-black px-2.5 py-1.5 rounded font-black text-xs tracking-wider select-none shadow-md">
                    <span>R★</span>
                </div>

                <!-- Offizielles GTA VI Logo direkt aus deinem Bild -->
                <div class="flex items-center">
                    <img src="data:image/jpeg;base64,<img width="3840" height="2916" alt="image" src="https://github.com/user-attachments/assets/8eaf4195-fe37-434c-9664-00c291fbecbf" />
 alt="GTA VI Logo" class="h-10 sm:h-12 w-auto object-contain drop-shadow-[0_2px_10px_rgba(0,0,0,0.9)]" />
                </div>
            </div>

            <!-- Mitte: Rockstar Games Navigation -->
            <nav class="hidden md:flex items-center space-x-8 text-[12px] font-bold tracking-[0.16em] uppercase text-gray-300">
                <a href="#countdown" class="text-white border-b-2 border-white py-5">Countdown</a>
                <button onclick="openInfoModal('leonida')" class="hover:text-white transition-colors uppercase py-5">Leonida</button>
                <button onclick="openInfoModal('characters')" class="hover:text-white transition-colors uppercase py-5">Lucia &amp; Jason</button>
                <button onclick="openInfoModal('release')" class="hover:text-white transition-colors uppercase py-5">Release Info</button>
            </nav>

            <!-- Rechts: Rockstar CTA & Hintergrund-Helligkeit -->
            <div class="flex items-center space-x-3">
                <button onclick="toggleArtworkFocus()" id="focus-btn" class="hidden sm:inline-flex items-center px-3.5 py-2 rounded-md border border-white/20 hover:border-white/50 bg-white/5 text-[11px] font-bold tracking-[0.14em] uppercase text-gray-200 transition">
                    Artwork Fokus
                </button>
                <button onclick="openInfoModal('release')" class="px-4 sm:px-5 py-2 rounded-md bg-white text-black hover:bg-[#fcaf17] font-extrabold text-[11px] sm:text-xs tracking-[0.14em] uppercase transition">
                    19. NOV 2026
                </button>
            </div>
        </div>
    </header>

    <!-- HAUPTBEREICH: OFFIZIELLES GTA VI LOGO & COUNTDOWN -->
    <main id="countdown" class="relative z-20 flex-1 flex flex-col items-center justify-center px-4 sm:px-6 py-8 sm:py-12 text-center max-w-6xl mx-auto w-full">

        <!-- Offizielles Grand Theft Auto VI Logo im Zentrum -->
        <div class="mb-5 sm:mb-7 animate-logo select-none flex flex-col items-center justify-center min-h-[160px] sm:min-h-[220px]">
            <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEASABIAAD/2wBDAP//////////////////////////////////////////////////////////////////////////////////////wgALCAABAAEBAREA/8QAFBABAAAAAAAAAAAAAAAAAAAAAP/aAAgBAQABPxA=" alt="Grand Theft Auto VI Logo" class="w-[280px] sm:w-[380px] md:w-[460px] h-auto object-contain drop-shadow-[0_20px_45px_rgba(0,0,0,0.95)]" />
        </div>

        <!-- Rockstar Games Release Headline -->
        <div class="mb-7 sm:mb-9">
            <div class="inline-flex items-center space-x-2.5 px-4 py-1.5 rounded-full bg-black/65 border border-vice-pink/40 backdrop-blur-md mb-3 shadow-[0_0_25px_rgba(255,46,147,0.25)]">
                <span class="w-2 h-2 rounded-full bg-[#fcaf17] animate-ping"></span>
                <span class="text-[11px] sm:text-xs font-extrabold tracking-[0.22em] uppercase text-white">
                    Finale Countdown-Phase &bull; Vice City
                </span>
            </div>
            <h1 class="text-2xl sm:text-4xl md:text-5xl font-black tracking-[0.06em] uppercase text-white drop-shadow-[0_4px_20px_rgba(0,0,0,0.9)]">
                19. November 2026 &bull; 00:00 Uhr
            </h1>
        </div>

        <!-- ROCKSTAR COUNTDOWN GRID (INKL. LIVE-MILLISEKUNDEN) -->
        <div class="grid grid-cols-2 sm:grid-cols-5 gap-3 sm:gap-4 md:gap-5 w-full max-w-5xl mb-8 sm:mb-10">
            <!-- Tage -->
            <div class="rstar-unit-card rounded-2xl p-4 sm:p-6 flex flex-col items-center justify-center">
                <span id="cd-days" class="font-display text-5xl sm:text-6xl md:text-7xl lg:text-8xl tracking-wide text-white tabular-nums leading-none drop-shadow-[0_4px_12px_rgba(0,0,0,0.8)]">
                    00
                </span>
                <span class="mt-2.5 text-[10px] sm:text-xs font-extrabold tracking-[0.25em] uppercase text-gray-300">
                    Tage
                </span>
            </div>

            <!-- Stunden -->
            <div class="rstar-unit-card rounded-2xl p-4 sm:p-6 flex flex-col items-center justify-center">
                <span id="cd-hours" class="font-display text-5xl sm:text-6xl md:text-7xl lg:text-8xl tracking-wide text-white tabular-nums leading-none drop-shadow-[0_4px_12px_rgba(0,0,0,0.8)]">
                    00
                </span>
                <span class="mt-2.5 text-[10px] sm:text-xs font-extrabold tracking-[0.25em] uppercase text-gray-300">
                    Stunden
                </span>
            </div>

            <!-- Minuten -->
            <div class="rstar-unit-card rounded-2xl p-4 sm:p-6 flex flex-col items-center justify-center">
                <span id="cd-minutes" class="font-display text-5xl sm:text-6xl md:text-7xl lg:text-8xl tracking-wide text-white tabular-nums leading-none drop-shadow-[0_4px_12px_rgba(0,0,0,0.8)]">
                    00
                </span>
                <span class="mt-2.5 text-[10px] sm:text-xs font-extrabold tracking-[0.25em] uppercase text-gray-300">
                    Minuten
                </span>
            </div>

            <!-- Sekunden -->
            <div class="rstar-unit-card rounded-2xl p-4 sm:p-6 flex flex-col items-center justify-center">
                <span id="cd-seconds" class="font-display text-5xl sm:text-6xl md:text-7xl lg:text-8xl tracking-wide text-white tabular-nums leading-none drop-shadow-[0_4px_12px_rgba(0,0,0,0.8)]">
                    00
                </span>
                <span class="mt-2.5 text-[10px] sm:text-xs font-extrabold tracking-[0.25em] uppercase text-gray-300">
                    Sekunden
                </span>
            </div>

            <!-- Millisekunden -->
            <div class="col-span-2 sm:col-span-1 rstar-unit-card rounded-2xl p-4 sm:p-6 flex flex-col items-center justify-center">
                <span id="cd-ms" class="font-display text-5xl sm:text-6xl md:text-7xl lg:text-8xl tracking-wide text-white tabular-nums leading-none drop-shadow-[0_4px_12px_rgba(0,0,0,0.8)]">
                    00
                </span>
                <span class="mt-2.5 text-[10px] sm:text-xs font-extrabold tracking-[0.25em] uppercase text-gray-300">
                    Hundertstel
                </span>
            </div>
        </div>

        <!-- Release erreicht Banner -->
        <div id="launch-complete" class="hidden w-full max-w-3xl mb-8 p-6 sm:p-8 rounded-xl bg-gradient-to-r from-vice-orange via-vice-pink to-vice-purple text-white shadow-2xl border border-white/40">
            <p class="text-xs font-black tracking-[0.25em] uppercase mb-1">Grand Theft Auto VI</p>
            <h2 class="text-3xl sm:text-5xl font-black uppercase tracking-tight">Jetzt Verfügbar</h2>
            <p class="mt-2 text-sm sm:text-base font-medium text-white/90">Willkommen zurück in Vice City &amp; dem Bundesstaat Leonida.</p>
        </div>

        <!-- Rockstar Fortschrittsbalken & Aktionsleiste -->
        <div class="w-full max-w-2xl space-y-5">
            <div class="bg-[#0e0e10]/80 border border-white/10 rounded-xl p-4 backdrop-blur-md">
                <div class="flex items-center justify-between text-[11px] font-bold tracking-[0.16em] uppercase text-gray-400 mb-2">
                    <span>Trailer 1 Reveal</span>
                    <span id="cd-progress-label" class="text-white">99.9%</span>
                    <span>Launch: 19.11.2026</span>
                </div>
                <div class="w-full h-1.5 bg-white/10 rounded-full overflow-hidden">
                    <div id="cd-progress-bar" class="h-full rounded-full bg-gradient-to-r from-vice-purple via-vice-pink to-vice-orange transition-all duration-700" style="width: 99.8%;"></div>
                </div>
            </div>

            <div class="flex flex-wrap items-center justify-center gap-3.5">
                <button onclick="openInfoModal('leonida')" class="px-6 py-3.5 rounded-lg bg-white text-black hover:bg-[#fcaf17] font-extrabold text-xs tracking-[0.16em] uppercase transition shadow-lg">
                    Erkunde Leonida
                </button>
                <button onclick="copyCountdownText()" class="px-6 py-3.5 rounded-lg bg-[#141416]/90 hover:bg-white/15 border border-white/20 text-white font-bold text-xs tracking-[0.16em] uppercase transition backdrop-blur-md">
                    <span id="copy-label">Countdown Kopieren</span>
                </button>
            </div>
        </div>
    </main>

    <!-- ROCKSTAR GAMES OFFIZIELLER FOOTER -->
    <footer class="relative z-30 w-full bg-[#080809]/95 border-t border-white/10 py-6 px-4 sm:px-8">
        <div class="max-w-[1440px] mx-auto flex flex-col md:flex-row items-center justify-between gap-6">
            
            <!-- Plattformen -->
            <div class="flex items-center space-x-4 text-xs font-extrabold tracking-[0.18em] uppercase text-gray-300">
                <span class="px-3 py-1.5 rounded bg-white/5 border border-white/15">PlayStation 5</span>
                <span class="px-3 py-1.5 rounded bg-white/5 border border-white/15">Xbox Series X|S</span>
            </div>

            <!-- Rockstar Games Branding -->
            <div class="flex flex-col items-center text-center">
                <div class="flex items-center space-x-2 mb-1">
                    <span class="px-1.5 py-0.5 rounded-[4px] bg-[#fcaf17] text-black font-black text-[10px]">R★</span>
                    <span class="text-xs font-extrabold tracking-[0.2em] uppercase text-white">Rockstar Games</span>
                </div>
                <p class="text-[11px] text-gray-500">
                    ©2026 Rockstar Games, Inc. Grand Theft Auto, Grand Theft Auto VI und das R*-Logo sind Marken von Take-Two Interactive.
                </p>
            </div>

            <!-- USK 18 Badge -->
            <div class="flex items-center space-x-3">
                <div class="w-11 h-11 rounded bg-[#d9232e] border border-white/80 flex flex-col items-center justify-center text-white select-none">
                    <span class="text-[8px] font-extrabold uppercase leading-none">USK</span>
                    <span class="text-lg font-black leading-none mt-0.5">18</span>
                </div>
                <div class="text-[10px] font-semibold uppercase tracking-wider text-gray-400 leading-tight">
                    <div>Keine Jugendfreigabe</div>
                    <div class="text-gray-500">gemäß § 14 JuSchG</div>
                </div>
            </div>
        </div>
    </footer>

    <!-- INFO MODAL IM ROCKSTAR GAMES STIL -->
    <div id="rstar-modal" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-black/85 backdrop-blur-md">
        <div class="relative w-full max-w-lg rounded-xl bg-[#121214] border border-white/15 p-6 sm:p-8 shadow-2xl text-left">
            <button onclick="closeInfoModal()" class="absolute top-4 right-4 w-9 h-9 rounded-lg bg-white/10 hover:bg-white/20 text-white flex items-center justify-center text-sm font-bold transition">
                ✕
            </button>
            <div class="flex items-center space-x-2 mb-3">
                <span class="px-1.5 py-0.5 rounded bg-[#fcaf17] text-black font-black text-[10px]">R★</span>
                <span id="modal-kicker" class="text-[11px] font-extrabold tracking-[0.2em] uppercase text-vice-pink">Grand Theft Auto VI</span>
            </div>
            <h2 id="modal-heading" class="text-2xl sm:text-3xl font-black uppercase tracking-tight text-white mb-3">
                Willkommen in Leonida
            </h2>
            <p id="modal-text" class="text-sm sm:text-base text-gray-300 leading-relaxed mb-6">
                Grand Theft Auto VI spielt im Bundesstaat Leonida, Heimat der neongetränkten Straßen von Vice City und darüber hinaus – in der bislang größten und immersivsten Evolution der Grand Theft Auto-Reihe.
            </p>
            <div class="flex justify-end">
                <button onclick="closeInfoModal()" class="px-5 py-2.5 rounded-lg bg-white text-black hover:bg-[#fcaf17] font-extrabold text-xs tracking-[0.14em] uppercase transition">
                    Schließen
                </button>
            </div>
        </div>
    </div>

    <script>
        // Exakter Release-Zeitpunkt: 19. November 2026 um 00:00:00 Uhr
        const RELEASE_TIMESTAMP = new Date(2026, 10, 19, 0, 0, 0, 0).getTime();
        // Startpunkt für Fortschrittsbalken: Ankündigung / Trailer 1 (5. Dezember 2023)
        const START_TIMESTAMP = new Date(2023, 11, 5, 0, 0, 0, 0).getTime();

        const elDays = document.getElementById('cd-days');
        const elHours = document.getElementById('cd-hours');
        const elMinutes = document.getElementById('cd-minutes');
        const elSeconds = document.getElementById('cd-seconds');
        const elMs = document.getElementById('cd-ms');
        const elProgressBar = document.getElementById('cd-progress-bar');
        const elProgressLabel = document.getElementById('cd-progress-label');
        const elLaunchComplete = document.getElementById('launch-complete');

        let lastSecond = -1;

        function formatTwoDigits(value) {
            return value < 10 ? '0' + value : String(value);
        }

        function tickCountdown() {
            const now = Date.now();
            const remaining = RELEASE_TIMESTAMP - now;

            // Fortschritt berechnen
            const totalDuration = RELEASE_TIMESTAMP - START_TIMESTAMP;
            const elapsedDuration = now - START_TIMESTAMP;
            const pct = Math.min(100, Math.max(0, (elapsedDuration / totalDuration) * 100));
            elProgressBar.style.width = pct.toFixed(4) + '%';
            elProgressLabel.textContent = pct.toFixed(4) + '%';

            if (remaining <= 0) {
                elDays.textContent = '00';
                elHours.textContent = '00';
                elMinutes.textContent = '00';
                elSeconds.textContent = '00';
                elMs.textContent = '00';
                elLaunchComplete.classList.remove('hidden');
                elProgressBar.style.width = '100%';
                elProgressLabel.textContent = '100%';
                return;
            }

            const days = Math.floor(remaining / (1000 * 60 * 60 * 24));
            const hours = Math.floor((remaining % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((remaining % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((remaining % (1000 * 60)) / 1000);
            const centiseconds = Math.floor((remaining % 1000) / 10);

            elDays.textContent = formatTwoDigits(days);
            elHours.textContent = formatTwoDigits(hours);
            elMinutes.textContent = formatTwoDigits(minutes);
            elSeconds.textContent = formatTwoDigits(seconds);
            elMs.textContent = formatTwoDigits(centiseconds);

            // Sanfter Pulse-Effekt bei jedem Sekundensprung
            if (seconds !== lastSecond) {
                lastSecond = seconds;
                elSeconds.classList.remove('digit-tick');
                void elSeconds.offsetWidth;
                elSeconds.classList.add('digit-tick');
            }

            requestAnimationFrame(tickCountdown);
        }

        // Flüssige 60-FPS Echtzeit-Aktualisierung starten
        requestAnimationFrame(tickCountdown);

        // Hintergrund-Fokus umschalten (helleres Lucia & Jason Artwork)
        let brightArt = false;
        function toggleArtworkFocus() {
            brightArt = !brightArt;
            const img = document.getElementById('keyart-bg');
            const btn = document.getElementById('focus-btn');
            if (brightArt) {
                img.style.filter = 'brightness(0.92) contrast(1.08) saturate(1.2)';
                btn.textContent = 'Standard Fokus';
            } else {
                img.style.filter = 'brightness(0.72) contrast(1.06) saturate(1.12)';
                btn.textContent = 'Artwork Fokus';
            }
        }

        // Modal-Inhalte
        const MODAL_DATA = {
            leonida: {
                kicker: 'Bundesstaat Leonida',
                heading: 'Vice City & Beyond',
                text: 'Von den sonnigen Stränden von Vice City über die Sümpfe der Grassrivers bis hin zu den Florida Keys – erlebe die bislang lebendigste und detailreichste Open World von Rockstar Games.'
            },
            characters: {
                kicker: 'Protagonisten',
                heading: 'Lucia & Jason',
                text: 'Folge Lucia und Jason durch eine fesselnde Geschichte voller Vertrauen, Überfälle und Überlebenskampf quer durch die Unterwelt von Leonida.'
            },
            release: {
                kicker: 'Offizieller Launch',
                heading: '19. November 2026 • 00:00 Uhr',
                text: 'Grand Theft Auto VI erscheint am 19. November 2026 für PlayStation 5 und Xbox Series X|S. Der Countdown zählt exakt bis Mitternacht.'
            }
        };

        function openInfoModal(key) {
            const info = MODAL_DATA[key] || MODAL_DATA.leonida;
            document.getElementById('modal-kicker').textContent = info.kicker;
            document.getElementById('modal-heading').textContent = info.heading;
            document.getElementById('modal-text').textContent = info.text;
            const modal = document.getElementById('rstar-modal');
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        function closeInfoModal() {
            const modal = document.getElementById('rstar-modal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        // Countdown-Text in Zwischenablage kopieren
        function copyCountdownText() {
            const text = `GTA VI Countdown: Noch ${elDays.textContent} Tage, ${elHours.textContent} Std, ${elMinutes.textContent} Min und ${elSeconds.textContent} Sek bis zum 19. November 2026 (00:00 Uhr)!`;
            const area = document.createElement('textarea');
            area.value = text;
            document.body.appendChild(area);
            area.select();
            document.execCommand('copy');
            document.body.removeChild(area);

            const label = document.getElementById('copy-label');
            label.textContent = 'Kopiert!';
            setTimeout(() => {
                label.textContent = 'Countdown Kopieren';
            }, 2200);
        }
    </script>
</body>
</html>★
￼
Countdown Leonida Lucia & Jason Release Info
Artwork Fokus 19. NOV 2026
￼
Finale Countdown-Phase • Vice City
19. November 2026 • 00:00 Uhr
00 Tage
00 Stunden
00 Minuten
00 Sekunden
00 Hundertstel
Grand Theft Auto VI
Jetzt Verfügbar
Willkommen zurück in Vice City & dem Bundesstaat Leonida.
Trailer 1 Reveal 99.9% Launch: 19.11.2026

Erkunde Leonida Countdown Kopieren
PlayStation 5 Xbox Series X|S
R★ Rockstar Games
©2026 Rockstar Games, Inc. Grand Theft Auto, Grand Theft Auto VI und das R*-Logo sind Marken von Take-Two Interactive.
USK 18
Keine Jugendfreigabe
gemäß § 14 JuSchG
✕
R★ Grand Theft Auto VI
Willkommen in Leonida
Grand Theft Auto VI spielt im Bundesstaat Leonida, Heimat der neongetränkten Straßen von Vice City und darüber hinaus – in der bislang größten und immersivsten Evolution der Grand Theft Auto-Reihe.
Schließen
