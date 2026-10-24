<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Rummikub Turn Timer</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@500;600;700&family=Inter:wght@500;600;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --rummi-ivory: #fdfaf3;
            --rummi-ivory-dark: #e6dec8;
            --rummi-red: #d92b2b;
            --rummi-blue: #0066cc;
            --rummi-yellow: #e59400;
            --rummi-black: #1e2229;
            --rack-blue: #162447;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: radial-gradient(circle at center, #1f4068 0%, #162447 65%, #0f172a 100%);
            user-select: none;
            -webkit-user-select: none;
            touch-action: manipulation;
        }

        .font-tile {
            font-family: 'Fredoka', sans-serif;
        }

        /* Authentic Rummikub 3D Tile Styling */
        .rummi-tile {
            background-color: var(--rummi-ivory);
            border: 2px solid #f2ece1;
            box-shadow: 
                0 8px 0 var(--rummi-ivory-dark),
                0 12px 24px rgba(0, 0, 0, 0.45),
                inset 0 2px 4px rgba(255, 255, 255, 0.9);
            transition: transform 0.12s cubic-bezier(0.34, 1.56, 0.64, 1), box-shadow 0.12s ease;
        }

        .rummi-tile-btn {
            background-color: var(--rummi-ivory);
            border: 2px solid #f2ece1;
            box-shadow: 
                0 5px 0 var(--rummi-ivory-dark),
                0 7px 14px rgba(0, 0, 0, 0.35),
                inset 0 1px 2px rgba(255, 255, 255, 0.9);
            transition: all 0.1s ease;
        }

        .rummi-tile-btn:active:not(:disabled) {
            transform: translateY(4px);
            box-shadow: 
                0 1px 0 var(--rummi-ivory-dark),
                0 2px 5px rgba(0, 0, 0, 0.3);
        }

        /* Tile Engraved Indentation */
        .tile-recess {
            box-shadow: inset 0 3px 6px rgba(0, 0, 0, 0.08), 0 1px 1px rgba(255, 255, 255, 0.8);
        }

        /* Progress Ring Animation */
        .progress-ring-circle {
            transition: stroke-dashoffset 0.1s linear, stroke 0.35s ease;
            transform: rotate(-90deg);
            transform-origin: 50% 50%;
        }

        /* Urgency Animations */
        @keyframes pulse-urgent {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.03); }
        }

        @keyframes shake-expired {
            0%, 100% { transform: translateX(0); }
            20%, 60% { transform: translateX(-6px) rotate(-1deg); }
            40%, 80% { transform: translateX(6px) rotate(1deg); }
        }

        .urgent-pulse {
            animation: pulse-urgent 0.7s infinite ease-in-out;
        }

        .expired-shake {
            animation: shake-expired 0.45s infinite ease-in-out;
        }

        /* Screen Edge Warning Flash */
        .screen-alert-overlay {
            pointer-events: none;
            transition: opacity 0.25s ease;
        }
    </style>
</head>
<body class="min-h-screen text-slate-800 flex flex-col justify-between p-3 sm:p-5 overflow-x-hidden">

    <!-- Visual Screen Flash Overlay for Warnings & Expiration -->
    <div id="alertOverlay" class="screen-alert-overlay fixed inset-0 z-50 opacity-0 border-[10px] border-red-500 bg-red-600/15"></div>

    <!-- Top Navigation & Brand Header -->
    <header class="w-full max-w-md mx-auto flex items-center justify-between gap-2 z-10">
        <!-- Mini Tile Brand Logo -->
        <div class="flex items-center gap-2.5 bg-slate-900/50 backdrop-blur-md px-3.5 py-2 rounded-2xl border border-white/10 shadow-lg">
            <div class="flex -space-x-1.5">
                <span class="w-6 h-8 rounded-md bg-[#fdfaf3] border border-[#e6dec8] shadow flex items-center justify-center font-tile font-bold text-sm text-[#1e2229]">R</span>
                <span class="w-6 h-8 rounded-md bg-[#fdfaf3] border border-[#e6dec8] shadow flex items-center justify-center font-tile font-bold text-sm text-[#d92b2b] -translate-y-0.5">1</span>
                <span class="w-6 h-8 rounded-md bg-[#fdfaf3] border border-[#e6dec8] shadow flex items-center justify-center font-tile font-bold text-sm text-[#0066cc]">2</span>
                <span class="w-6 h-8 rounded-md bg-[#fdfaf3] border border-[#e6dec8] shadow flex items-center justify-center font-tile font-bold text-sm text-[#e59400] -translate-y-0.5">0</span>
            </div>
            <div class="ml-1">
                <h1 class="text-white font-tile font-bold text-base sm:text-lg leading-none tracking-tight">RUMMIKUB</h1>
                <span class="text-[10px] text-amber-300/90 font-semibold tracking-widest uppercase block mt-0.5">Turn Timer</span>
            </div>
        </div>

        <!-- Turn Counter & Sound Controls -->
        <div class="flex items-center gap-2">
            <!-- Turn Badge -->
            <div class="bg-slate-900/50 backdrop-blur-md px-3 py-1.5 rounded-2xl border border-white/10 text-center">
                <span class="text-[10px] uppercase tracking-wider text-slate-400 font-semibold block leading-tight">Turn</span>
                <span id="turnCounter" class="font-tile font-bold text-white text-base leading-none">#1</span>
            </div>

            <!-- Sound Toggle Button -->
            <button id="soundToggleBtn" onclick="toggleSound()" aria-label="Toggle Sound" class="rummi-tile-btn w-11 h-11 rounded-2xl flex items-center justify-center text-[#0066cc] hover:bg-amber-50/90">
                <svg id="soundOnIcon" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.2">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M15.536 8.464a5 5 0 010 7.072m2.828-9.9a9 9 0 010 12.728M5.586 15H4a1 1 0 01-1-1v-4a1 1 0 011-1h1.586l4.707-4.707C10.923 3.663 12 4.109 12 5v14c0 .891-1.077 1.337-1.707.707L5.586 15z" />
                </svg>
                <svg id="soundOffIcon" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 hidden text-[#d92b2b]" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.2">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M5.586 15H4a1 1 0 01-1-1v-4a1 1 0 011-1h1.586l4.707-4.707C10.923 3.663 12 4.109 12 5v14c0 .891-1.077 1.337-1.707.707L5.586 15z" />
                    <path stroke-linecap="round" stroke-linejoin="round" d="M17 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2" />
                </svg>
            </button>
        </div>
    </header>

    <!-- Main Centerpiece: Giant Rummikub Tile Countdown & Next Turn Tap Zone -->
    <main class="w-full max-w-md mx-auto my-auto py-3 flex flex-col items-center gap-3.5 z-10">
        
        <!-- Primary Interactive Tile Card (Tap anywhere on tile for Next Player / Reset) -->
        <div id="mainTileCard" onclick="handleNextTurnTap()" role="button" tabindex="0" aria-label="Next Player and Reset Timer"
             class="rummi-tile w-full rounded-[2rem] p-4 sm:p-6 flex flex-col items-center justify-between relative cursor-pointer select-none active:translate-y-1.5 transition-all">
            
            <!-- Top Tile Header Bar: Authentic Rummikub Color Dots & Status Pill -->
            <div class="w-full flex items-center justify-between px-2 mb-1">
                <div class="flex items-center gap-1.5">
                    <span class="w-3 h-3 rounded-full bg-[#d92b2b] inline-block shadow-sm"></span>
                    <span class="w-3 h-3 rounded-full bg-[#0066cc] inline-block shadow-sm"></span>
                    <span class="w-3 h-3 rounded-full bg-[#e59400] inline-block shadow-sm"></span>
                    <span class="w-3 h-3 rounded-full bg-[#1e2229] inline-block shadow-sm"></span>
                </div>
                
                <div id="statusBadge" class="px-3 py-0.5 rounded-full text-xs font-bold uppercase tracking-wider bg-emerald-100 text-emerald-800 border border-emerald-300 transition-colors">
                    Ready • 120s
                </div>

                <!-- Display Format Toggle (120s vs 02:00) -->
                <button type="button" onclick="toggleFormat(event)" title="Switch Time Format"
                        class="text-xs font-bold px-2.5 py-1 rounded-lg bg-amber-900/10 hover:bg-amber-900/20 text-slate-700 transition">
                    <span id="formatLabel">SEC</span>
                </button>
            </div>

            <!-- Circular Countdown Progress Ring + Recessed Tile Center -->
            <div class="relative w-60 h-60 sm:w-68 sm:h-68 flex items-center justify-center my-1">
                <svg class="w-full h-full -rotate-90 transform" viewBox="0 0 240 240">
                    <!-- Recessed Inner Circle Background -->
                    <circle cx="120" cy="120" r="98" fill="#f5efe2" />
                    
                    <!-- Background Track Ring -->
                    <circle cx="120" cy="120" r="104" stroke="#e5dec9" stroke-width="14" fill="transparent" />
                    
                    <!-- Dynamic Progress Ring -->
                    <circle id="progressRing"
                            class="progress-ring-circle"
                            cx="120" cy="120" r="104"
                            stroke="#16a34a"
                            stroke-width="14"
                            stroke-linecap="round"
                            fill="transparent"
                            stroke-dasharray="653.45"
                            stroke-dashoffset="0" />
                </svg>

                <!-- Center Digital Readout -->
                <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4">
                    <!-- Primary Countdown Number -->
                    <div id="primaryTimeDisplay" class="font-tile font-bold text-6xl sm:text-7xl tracking-tight text-[#1e2229] leading-none transition-colors">
                        120
                    </div>
                    
                    <!-- Secondary Sub-Readout (e.g., 02:00 or Seconds remaining) -->
                    <div id="secondaryTimeDisplay" class="font-bold text-sm sm:text-base text-slate-500 mt-1 tracking-wide">
                        02:00
                    </div>

                    <!-- Milestone Alert Indicators (30s / 10s badges) -->
                    <div class="flex items-center gap-1.5 mt-2.5">
                        <span id="badge30s" class="px-2 py-0.5 text-[10px] font-extrabold uppercase rounded bg-slate-200/80 text-slate-500 transition-all">30s Alert</span>
                        <span id="badge10s" class="px-2 py-0.5 text-[10px] font-extrabold uppercase rounded bg-slate-200/80 text-slate-500 transition-all">10s Alert</span>
                    </div>
                </div>
            </div>

            <!-- Prominent "NEXT PLAYER / RESET" Action Banner inside the Main Tap Area -->
            <div id="nextPlayerBanner" class="w-full mt-2 bg-gradient-to-r from-[#0066cc] to-[#0052a3] hover:from-[#005bb8] hover:to-[#00468c] text-white rounded-2xl py-3.5 px-4 shadow-md flex items-center justify-center gap-3 transition-all">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15" />
                </svg>
                <div class="text-left leading-tight">
                    <span id="mainActionText" class="font-tile font-bold text-lg sm:text-xl tracking-wide block">
                        START / NEXT PLAYER
                    </span>
                    <span id="mainActionSubtext" class="text-[11px] text-blue-100 font-medium block">
                        Tap anywhere on tile to reset to <strong id="resetTargetLabel">120s</strong> &amp; start
                    </span>
                </div>
            </div>
        </div>

        <!-- Secondary Controls Row: Pause/Resume & Penalty/Add +15s -->
        <div class="w-full grid grid-cols-3 gap-2.5">
            <!-- Pause / Resume Button (Spans 2 columns) -->
            <button id="pauseResumeBtn" onclick="togglePause()"
                    class="col-span-2 rummi-tile-btn rounded-2xl py-3.5 px-4 flex items-center justify-center gap-2.5 font-tile font-bold text-lg text-[#1e2229] hover:bg-amber-50">
                <span id="pauseResumeIcon">
                    <!-- Play Icon Default -->
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-emerald-600" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M8 5v14l11-7z" />
                    </svg>
                </span>
                <span id="pauseResumeText">START</span>
            </button>

            <!-- Stop / Reset without starting -->
            <button onclick="resetAndStandby()" title="Reset to standby without auto-starting"
                    class="rummi-tile-btn rounded-2xl py-3.5 px-3 flex flex-col items-center justify-center font-tile font-bold text-[#d92b2b] hover:bg-amber-50">
                <div class="flex items-center gap-1">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.3">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
                    </svg>
                    <span class="text-base">CLEAR</span>
                </div>
                <span class="text-[10px] font-sans font-semibold text-slate-500">Standby</span>
            </button>
        </div>

    </main>

    <!-- Bottom Rack: Preset Time Tiles & Custom Duration Selector -->
    <footer class="w-full max-w-md mx-auto z-10">
        <div class="bg-slate-950/60 backdrop-blur-md p-3 rounded-3xl border border-white/10 shadow-2xl">
            <div class="flex items-center justify-between px-1 mb-2">
                <span class="text-[11px] font-bold uppercase tracking-wider text-amber-200/80 flex items-center gap-1.5">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-3.5 h-3.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
                    </svg>
                    Turn Duration Presets
                </span>
                <span class="text-[11px] text-slate-400 font-medium">Spacebar = Next Turn</span>
            </div>

            <!-- Rummikub Number Tile Preset Buttons -->
            <div class="grid grid-cols-4 gap-2">
                <!-- 60s Tile (Blue) -->
                <button onclick="selectPreset(60)" id="preset-60"
                        class="preset-tile rummi-tile-btn rounded-xl py-2 px-1 flex flex-col items-center justify-center relative">
                    <span class="font-tile font-bold text-xl sm:text-2xl text-[#0066cc] leading-none">60s</span>
                    <span class="text-[10px] font-bold text-slate-500 mt-0.5">Blitz</span>
                </button>

                <!-- 90s Tile (Yellow/Amber) -->
                <button onclick="selectPreset(90)" id="preset-90"
                        class="preset-tile rummi-tile-btn rounded-xl py-2 px-1 flex flex-col items-center justify-center relative">
                    <span class="font-tile font-bold text-xl sm:text-2xl text-[#e59400] leading-none">90s</span>
                    <span class="text-[10px] font-bold text-slate-500 mt-0.5">Fast</span>
                </button>

                <!-- 120s Default Tile (Red) -->
                <button onclick="selectPreset(120)" id="preset-120"
                        class="preset-tile rummi-tile-btn rounded-xl py-2 px-1 flex flex-col items-center justify-center relative ring-2 ring-amber-400 bg-amber-50">
                    <span class="font-tile font-bold text-xl sm:text-2xl text-[#d92b2b] leading-none">120s</span>
                    <span class="text-[10px] font-bold text-[#d92b2b] mt-0.5">Standard</span>
                </button>

                <!-- Custom +/- Fine Adjust Tile (Black) -->
                <div class="rummi-tile-btn rounded-xl p-1 flex flex-col items-center justify-between">
                    <span class="text-[10px] font-extrabold text-[#1e2229] uppercase tracking-tighter">Adjust</span>
                    <div class="flex items-center justify-between w-full px-1 my-auto">
                        <button onclick="adjustCustomTime(-15)" aria-label="Subtract 15 seconds"
                                class="w-6 h-6 rounded-lg bg-slate-200 hover:bg-slate-300 active:bg-slate-400 text-[#1e2229] font-bold text-sm flex items-center justify-center">-15</button>
                        <button onclick="adjustCustomTime(15)" aria-label="Add 15 seconds"
                                class="w-6 h-6 rounded-lg bg-slate-200 hover:bg-slate-300 active:bg-slate-400 text-[#1e2229] font-bold text-sm flex items-center justify-center">+15</button>
                    </div>
                    <span class="text-[9px] font-semibold text-slate-500">Seconds</span>
                </div>
            </div>
        </div>
    </footer>

    <script>
        /**
         * Rummikub Turn Timer Logic & Web Audio API Synthesizer
         * Self-contained single-file architecture
         */

        // --- State Variables ---
        let totalDuration = 120;         // Default 120 seconds per Rummikub rules
        let remainingMs = 120 * 1000;    // High-precision tracking in milliseconds
        let isRunning = false;
        let isExpired = false;
        let timerInterval = null;
        let lastFrameTime = null;
        let turnCount = 1;
        let soundEnabled = true;
        let showMinutesPrimary = false;  // false = "120" primary & "02:00" secondary; true = "02:00" primary

        // Track which audio alerts have fired during the current turn
        let alertsTriggered = {
            thirtySec: false,
            tenSec: false,
            countdownTicks: new Set(), // Tracks 5, 4, 3, 2, 1 final ticks
            expired: false
        };

        // SVG Ring Constants (r = 104 => circumference = 2 * PI * 104 ≈ 653.45)
        const RING_CIRCUMFERENCE = 2 * Math.PI * 104;

        // --- Web Audio API Synthesizer (No External Sound Files Required) ---
        let audioCtx = null;

        function getAudioContext() {
            if (!audioCtx) {
                const AudioContextClass = window.AudioContext || window.webkitAudioContext;
                if (AudioContextClass) {
                    audioCtx = new AudioContextClass();
                }
            }
            if (audioCtx && audioCtx.state === 'suspended') {
                audioCtx.resume();
            }
            return audioCtx;
        }

        /**
         * Plays synthesized tones using Web Audio API
         * @param {string} type - 'start' | 'warning30' | 'warning10' | 'tick' | 'expired' | 'click'
         */
        function playSoundAlert(type) {
            if (!soundEnabled) return;
            const ctx = getAudioContext();
            if (!ctx) return;

            const now = ctx.currentTime;

            if (type === 'start') {
                // Crisp Rummikub tile clack + upbeat start chime
                playTone(ctx, 523.25, now, 0.08, 'triangle', 0.2);       // C5
                playTone(ctx, 659.25, now + 0.07, 0.14, 'triangle', 0.25); // E5
            } 
            else if (type === 'warning30') {
                // 30 Seconds Remaining: Double Amber Chime
                playTone(ctx, 587.33, now, 0.14, 'sine', 0.3);           // D5
                playTone(ctx, 880.00, now + 0.16, 0.22, 'sine', 0.35);   // A5
            } 
            else if (type === 'warning10') {
                // 10 Seconds Remaining: Urgent Triple Staccato Beep
                playTone(ctx, 880.00, now, 0.09, 'sawtooth', 0.22);
                playTone(ctx, 880.00, now + 0.12, 0.09, 'sawtooth', 0.25);
                playTone(ctx, 1046.50, now + 0.24, 0.15, 'sawtooth', 0.3);
            } 
            else if (type === 'tick') {
                // Final 5-second countdown woodblock tick
                playTone(ctx, 784.00, now, 0.05, 'triangle', 0.2);
            } 
            else if (type === 'expired') {
                // Time Expired: Game buzzer chord + descending penalty horn
                playTone(ctx, 349.23, now, 0.22, 'sawtooth', 0.35);       // F4
                playTone(ctx, 311.13, now + 0.24, 0.22, 'sawtooth', 0.35); // D#4
                playTone(ctx, 261.63, now + 0.48, 0.55, 'sawtooth', 0.4);  // C4
            }
            else if (type === 'click') {
                // Subtle UI tile tap
                playTone(ctx, 440, now, 0.03, 'sine', 0.12);
            }
        }

        function playTone(ctx, freq, startTime, duration, waveType = 'sine', maxGain = 0.25) {
            const osc = ctx.createOscillator();
            const gain = ctx.createGain();

            osc.type = waveType;
            osc.frequency.setValueAtTime(freq, startTime);

            gain.gain.setValueAtTime(0.001, startTime);
            gain.gain.exponentialRampToValueAtTime(maxGain, startTime + 0.015);
            gain.gain.exponentialRampToValueAtTime(0.0001, startTime + duration);

            osc.connect(gain);
            gain.connect(ctx.destination);

            osc.start(startTime);
            osc.stop(startTime + duration + 0.02);
        }

        // --- Visual Flash Helper ---
        function triggerScreenFlash(colorClass = 'border-red-500 bg-red-600/20', durationMs = 450) {
            const overlay = document.getElementById('alertOverlay');
            overlay.className = `screen-alert-overlay fixed inset-0 z-50 border-[10px] ${colorClass} opacity-100`;
            setTimeout(() => {
                overlay.classList.remove('opacity-100');
                overlay.classList.add('opacity-0');
            }, durationMs);
        }

        // --- Formatting Helpers ---
        function formatMMSS(seconds) {
            const s = Math.max(0, Math.ceil(seconds));
            const mins = Math.floor(s / 60);
            const secs = s % 60;
            return `${String(mins).padStart(2, '0')}:${String(secs).padStart(2, '0')}`;
        }

        // --- Core Timer Update & UI Rendering ---
        function updateUI() {
            const secondsLeft = Math.ceil(remainingMs / 1000);
            const exactFraction = Math.max(0, Math.min(1, remainingMs / (totalDuration * 1000)));

            const primaryEl = document.getElementById('primaryTimeDisplay');
            const secondaryEl = document.getElementById('secondaryTimeDisplay');
            const progressRing = document.getElementById('progressRing');
            const statusBadge = document.getElementById('statusBadge');
            const mainTileCard = document.getElementById('mainTileCard');
            const badge30s = document.getElementById('badge30s');
            const badge10s = document.getElementById('badge10s');
            const pauseResumeText = document.getElementById('pauseResumeText');
            const pauseResumeIcon = document.getElementById('pauseResumeIcon');
            const mainActionText = document.getElementById('mainActionText');
            const mainActionSubtext = document.getElementById('mainActionSubtext');

            // 1. Update Numeric Readouts
            if (isExpired) {
                primaryEl.textContent = "0";
                secondaryEl.textContent = "TIME'S UP! DRAW A TILE";
            } else if (showMinutesPrimary) {
                primaryEl.textContent = formatMMSS(secondsLeft);
                secondaryEl.textContent = `${secondsLeft} seconds remaining`;
            } else {
                primaryEl.textContent = `${secondsLeft}`;
                secondaryEl.textContent = formatMMSS(secondsLeft);
            }

            // 2. Update Circular SVG Ring Offset
            const offset = RING_CIRCUMFERENCE * (1 - exactFraction);
            progressRing.style.strokeDasharray = `${RING_CIRCUMFERENCE}`;
            progressRing.style.strokeDashoffset = `${offset}`;

            // 3. Dynamic Color & Urgency States (Green -> Yellow/Amber at <=30s -> Red at <=10s)
            mainTileCard.classList.remove('urgent-pulse', 'expired-shake');

            if (isExpired) {
                progressRing.style.stroke = '#dc2626'; // Red-600
                primaryEl.className = 'font-tile font-bold text-6xl sm:text-7xl tracking-tight text-[#d92b2b] leading-none';
                statusBadge.className = 'px-3 py-0.5 rounded-full text-xs font-extrabold uppercase tracking-wider bg-red-600 text-white animate-bounce';
                statusBadge.textContent = "Time Expired!";
                mainTileCard.classList.add('expired-shake');
            } else if (secondsLeft <= 10) {
                // Critical Red Phase (<= 10s)
                progressRing.style.stroke = '#d92b2b'; // Rummikub Red
                primaryEl.className = 'font-tile font-bold text-6xl sm:text-7xl tracking-tight text-[#d92b2b] leading-none';
                statusBadge.className = 'px-3 py-0.5 rounded-full text-xs font-bold uppercase tracking-wider bg-red-100 text-red-800 border border-red-300';
                statusBadge.textContent = isRunning ? "Final 10 Seconds!" : "Paused (Critical)";
                if (isRunning) mainTileCard.classList.add('urgent-pulse');
            } else if (secondsLeft <= 30) {
                // Caution Yellow/Amber Phase (<= 30s)
                progressRing.style.stroke = '#e59400'; // Rummikub Yellow/Amber
                primaryEl.className = 'font-tile font-bold text-6xl sm:text-7xl tracking-tight text-[#d97706] leading-none';
                statusBadge.className = 'px-3 py-0.5 rounded-full text-xs font-bold uppercase tracking-wider bg-amber-100 text-amber-900 border border-amber-300';
                statusBadge.textContent = isRunning ? "30s Warning" : "Paused";
            } else {
                // Safe Green Phase (> 30s)
                progressRing.style.stroke = '#16a34a'; // Emerald Green
                primaryEl.className = 'font-tile font-bold text-6xl sm:text-7xl tracking-tight text-[#1e2229] leading-none';
                statusBadge.className = 'px-3 py-0.5 rounded-full text-xs font-bold uppercase tracking-wider bg-emerald-100 text-emerald-800 border border-emerald-300';
                statusBadge.textContent = isRunning ? "In Play" : (remainingMs === totalDuration * 1000 ? `Ready • ${totalDuration}s` : "Paused");
            }

            // 4. Milestone Pill Highlight States
            if (secondsLeft <= 30 && totalDuration > 30) {
                badge30s.className = 'px-2 py-0.5 text-[10px] font-extrabold uppercase rounded bg-amber-500 text-white shadow-sm transition-all';
            } else {
                badge30s.className = 'px-2 py-0.5 text-[10px] font-extrabold uppercase rounded bg-slate-200/80 text-slate-500 transition-all';
            }

            if (secondsLeft <= 10) {
                badge10s.className = 'px-2 py-0.5 text-[10px] font-extrabold uppercase rounded bg-red-600 text-white shadow-sm transition-all';
            } else {
                badge10s.className = 'px-2 py-0.5 text-[10px] font-extrabold uppercase rounded bg-slate-200/80 text-slate-500 transition-all';
            }

            // 5. Update Button Labels
            if (isRunning) {
                pauseResumeText.textContent = "PAUSE";
                pauseResumeIcon.innerHTML = `
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-amber-600" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M6 19h4V5H6v14zm8-14v14h4V5h-4z" />
                    </svg>`;
                mainActionText.textContent = `NEXT PLAYER (${totalDuration}s)`;
                mainActionSubtext.innerHTML = `Tap tile to finish turn &amp; restart <strong>${totalDuration}s</strong>`;
            } else if (isExpired) {
                pauseResumeText.textContent = "NEW TURN";
                pauseResumeIcon.innerHTML = `
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-emerald-600" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M8 5v14l11-7z" />
                    </svg>`;
                mainActionText.textContent = `NEXT PLAYER (${totalDuration}s)`;
                mainActionSubtext.innerHTML = `Tap tile to start next player's turn`;
            } else if (remainingMs < totalDuration * 1000) {
                pauseResumeText.textContent = "RESUME";
                pauseResumeIcon.innerHTML = `
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-emerald-600" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M8 5v14l11-7z" />
                    </svg>`;
                mainActionText.textContent = `NEXT PLAYER (${totalDuration}s)`;
                mainActionSubtext.innerHTML = `Tap tile to reset to <strong>${totalDuration}s</strong> &amp; start immediately`;
            } else {
                pauseResumeText.textContent = "START";
                pauseResumeIcon.innerHTML = `
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-emerald-600" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M8 5v14l11-7z" />
                    </svg>`;
                mainActionText.textContent = `START TURN (${totalDuration}s)`;
                mainActionSubtext.innerHTML = `Tap anywhere on tile to start <strong>${totalDuration}s</strong> countdown`;
            }
        }

        // --- High-Accuracy Tick Loop ---
        function tick() {
            if (!isRunning) return;

            const now = performance.now();
            const delta = now - lastFrameTime;
            lastFrameTime = now;

            remainingMs = Math.max(0, remainingMs - delta);
            const secondsLeft = Math.ceil(remainingMs / 1000);

            // Check 30-second milestone alert
            if (secondsLeft === 30 && totalDuration > 30 && !alertsTriggered.thirtySec) {
                alertsTriggered.thirtySec = true;
                playSoundAlert('warning30');
                triggerScreenFlash('border-amber-400 bg-amber-500/15', 400);
            }

            // Check 10-second milestone alert
            if (secondsLeft === 10 && totalDuration > 10 && !alertsTriggered.tenSec) {
                alertsTriggered.tenSec = true;
                playSoundAlert('warning10');
                triggerScreenFlash('border-red-500 bg-red-600/20', 500);
            }

            // Check final 5-second ticks (5, 4, 3, 2, 1)
            if (secondsLeft <= 5 && secondsLeft >= 1 && !alertsTriggered.countdownTicks.has(secondsLeft)) {
                alertsTriggered.countdownTicks.add(secondsLeft);
                playSoundAlert('tick');
            }

            // Check Expiration (0s)
            if (remainingMs <= 0) {
                remainingMs = 0;
                isRunning = false;
                isExpired = true;
                clearInterval(timerInterval);
                timerInterval = null;

                if (!alertsTriggered.expired) {
                    alertsTriggered.expired = true;
                    playSoundAlert('expired');
                    triggerScreenFlash('border-red-600 bg-red-600/30', 900);
                }
            }

            updateUI();
        }

        // --- User Actions ---

        /**
         * Prominent Next Player / Reset Tap Handler:
         * Immediately resets timer to full preset duration (e.g., 120s) and starts counting down.
         */
        function handleNextTurnTap() {
            // If timer was already used or running, increment turn counter
            if (isRunning || isExpired || remainingMs < totalDuration * 1000) {
                turnCount++;
                document.getElementById('turnCounter').textContent = `#${turnCount}`;
            }

            resetInternalState();
            isRunning = true;
            lastFrameTime = performance.now();
            playSoundAlert('start');

            if (timerInterval) clearInterval(timerInterval);
            timerInterval = setInterval(tick, 50);
            updateUI();
        }

        /**
         * Toggles Pause / Resume without resetting the current turn
         */
        function togglePause() {
            if (isExpired) {
                handleNextTurnTap();
                return;
            }

            if (isRunning) {
                // Pause
                isRunning = false;
                if (timerInterval) {
                    clearInterval(timerInterval);
                    timerInterval = null;
                }
                playSoundAlert('click');
            } else {
                // Start or Resume
                isRunning = true;
                lastFrameTime = performance.now();
                playSoundAlert('start');
                if (timerInterval) clearInterval(timerInterval);
                timerInterval = setInterval(tick, 50);
            }
            updateUI();
        }

        /**
         * Resets timer to standby without auto-starting
         */
        function resetAndStandby() {
            playSoundAlert('click');
            resetInternalState();
            updateUI();
        }

        function resetInternalState() {
            if (timerInterval) {
                clearInterval(timerInterval);
                timerInterval = null;
            }
            isRunning = false;
            isExpired = false;
            remainingMs = totalDuration * 1000;
            alertsTriggered = {
                thirtySec: false,
                tenSec: false,
                countdownTicks: new Set(),
                expired: false
            };
        }

        /**
         * Selects a preset duration (60s, 90s, 120s)
         */
        function selectPreset(seconds) {
            totalDuration = seconds;
            playSoundAlert('click');

            // Highlight active preset tile
            document.querySelectorAll('.preset-tile').forEach(btn => {
                btn.classList.remove('ring-2', 'ring-amber-400', 'bg-amber-50');
            });
            const activeBtn = document.getElementById(`preset-${seconds}`);
            if (activeBtn) {
                activeBtn.classList.add('ring-2', 'ring-amber-400', 'bg-amber-50');
            }

            resetInternalState();
            updateUI();
        }

        /**
         * Adjusts time by -15s or +15s (between 15s and 600s)
         */
        function adjustCustomTime(deltaSeconds) {
            const newDuration = Math.min(600, Math.max(15, totalDuration + deltaSeconds));
            totalDuration = newDuration;
            playSoundAlert('click');

            // Update preset highlight if it matches 60, 90, or 120
            document.querySelectorAll('.preset-tile').forEach(btn => {
                btn.classList.remove('ring-2', 'ring-amber-400', 'bg-amber-50');
            });
            const matchingPreset = document.getElementById(`preset-${newDuration}`);
            if (matchingPreset) {
                matchingPreset.classList.add('ring-2', 'ring-amber-400', 'bg-amber-50');
            }

            resetInternalState();
            updateUI();
        }

        /**
         * Switches primary readout between total Seconds (120) and MM:SS (02:00)
         */
        function toggleFormat(event) {
            if (event) event.stopPropagation(); // Prevent triggering the main tile tap
            showMinutesPrimary = !showMinutesPrimary;
            document.getElementById('formatLabel').textContent = showMinutesPrimary ? 'MM:SS' : 'SEC';
            playSoundAlert('click');
            updateUI();
        }

        /**
         * Toggles synthesized audio alerts on/off
         */
        function toggleSound() {
            soundEnabled = !soundEnabled;
            const onIcon = document.getElementById('soundOnIcon');
            const offIcon = document.getElementById('soundOffIcon');

            if (soundEnabled) {
                onIcon.classList.remove('hidden');
                offIcon.classList.add('hidden');
                playSoundAlert('click');
            } else {
                onIcon.classList.add('hidden');
                offIcon.classList.remove('hidden');
            }
        }

        // --- Keyboard Shortcuts for Tabletop Convenience ---
        window.addEventListener('keydown', (e) => {
            if (e.code === 'Space') {
                e.preventDefault();
                handleNextTurnTap();
            } else if (e.key === 'p' || e.key === 'P') {
                e.preventDefault();
                togglePause();
            } else if (e.key === 'r' || e.key === 'R') {
                e.preventDefault();
                resetAndStandby();
            }
        });

        // Initialize UI on load
        window.onload = function () {
            updateUI();
        };
    </script>
</body>
</html>