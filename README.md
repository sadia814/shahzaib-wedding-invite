<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shahzaib Majeed weds Afifa Maryam | Dreamy Wedding Invitation</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Playfair Display, Great Vibes & Montserrat -->
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Montserrat:wght@300;400;500;600;700&family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400&display=swap" rel="stylesheet">
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        dreamy: {
                            950: '#1a0b2e', // Deep starlight purple
                            900: '#26123b',
                            800: '#3d1b59',
                        },
                        sunset: {
                            gold: '#ffd700',
                            rose: '#ffb7c5',
                            lavender: '#e6e6fa',
                            champagne: '#f7e7ce',
                            peach: '#ffdab9',
                        }
                    },
                    fontFamily: {
                        serif: ['"Playfair Display"', 'serif'],
                        script: ['"Great Vibes"', 'cursive'],
                        sans: ['Montserrat', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            font-family: 'Montserrat', sans-serif;
            background-color: #1a0b2e;
            color: #f7e7ce;
            overflow-x: hidden;
        }
        .serif-font {
            font-family: 'Playfair Display', serif;
        }
        .script-font {
            font-family: 'Great Vibes', cursive;
        }
        .dreamy-gradient {
            background: linear-gradient(135deg, #ffb7c5 0%, #ffd700 50%, #e6e6fa 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .glass-card {
            background: rgba(61, 27, 89, 0.45);
            backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 183, 197, 0.3);
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
        }
        .glass-card:hover {
            border-color: rgba(255, 215, 0, 0.6);
            box-shadow: 0 12px 40px -10px rgba(255, 183, 197, 0.3);
        }
        /* Scanner laser line animation */
        @keyframes scanLaser {
            0% { top: 0%; opacity: 0.8; }
            50% { opacity: 1; }
            100% { top: 100%; opacity: 0.8; }
        }
        .scanner-beam {
            animation: scanLaser 2s ease-in-out infinite alternate;
        }
        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #1a0b2e;
        }
        ::-webkit-scrollbar-thumb {
            background: #ffb7c5;
            border-radius: 4px;
        }
    </style>
</head>
<body class="selection:bg-pink-400 selection:text-purple-950">

    <!-- Ambient Audio & Sound FX Controller -->
    <div class="fixed bottom-5 right-5 z-50 flex items-center gap-3">
        <button onclick="toggleAudio()" id="audio-btn" class="glass-card text-sunset-rose p-3.5 rounded-full shadow-2xl hover:scale-110 transition-all flex items-center justify-center group" title="Toggle Dreamy Ambient Melody">
            <i id="audio-icon" class="fa-solid fa-volume-xmark text-lg"></i>
            <span class="max-w-0 overflow-hidden whitespace-nowrap group-hover:max-w-xs transition-all duration-300 ease-in-out text-xs text-sunset-champagne pl-0 group-hover:pl-2">Dreamy Melody</span>
        </button>
    </div>

    <!-- Success Modal Notification -->
    <div id="toast-modal" class="fixed inset-0 z-50 flex items-center justify-center bg-black/80 backdrop-blur-md hidden p-4">
        <div class="glass-card rounded-2xl p-8 max-w-md w-full text-center shadow-2xl transform transition-all border-2 border-pink-400">
            <div class="w-16 h-16 bg-pink-500/20 rounded-full flex items-center justify-center mx-auto mb-4 border border-pink-400 animate-bounce">
                <i class="fa-solid fa-heart text-pink-300 text-2xl"></i>
            </div>
            <h3 id="toast-title" class="serif-font text-3xl font-bold dreamy-gradient mb-2">RSVP Confirmed!</h3>
            <p id="toast-message" class="text-sunset-champagne/90 text-sm mb-6">Your response has been successfully registered. We are thrilled to celebrate with you!</p>
            <button onclick="closeModal()" class="bg-gradient-to-r from-pink-400 to-yellow-400 hover:opacity-90 text-purple-950 font-bold px-8 py-3 rounded-full transition-all shadow-lg uppercase tracking-widest text-xs">
                Continue
            </button>
        </div>
    </div>

    <!-- Location Scanner Modal / Simulation -->
    <div id="scanner-modal" class="fixed inset-0 z-50 flex items-center justify-center bg-black/85 backdrop-blur-md hidden p-4">
        <div class="glass-card rounded-2xl p-6 md:p-8 max-w-lg w-full text-center shadow-2xl relative overflow-hidden border-2 border-pink-400">
            <!-- Laser scanning overlay -->
            <div class="absolute inset-x-0 h-1 bg-pink-400 shadow-[0_0_15px_#ffb7c5] scanner-beam pointer-events-none"></div>
            
            <div class="w-16 h-16 bg-purple-950/80 rounded-full flex items-center justify-center mx-auto mb-4 border border-pink-400">
                <i class="fa-solid fa-satellite-dish text-pink-300 text-2xl animate-pulse"></i>
            </div>
            <span class="text-[10px] uppercase tracking-[0.3em] text-pink-300 font-bold block mb-1">Dreamy GPS Starlight Scanner</span>
            <h3 id="scanner-venue-title" class="serif-font text-2xl font-bold dreamy-gradient mb-2">Scanning Venue...</h3>
            <p id="scanner-status" class="text-sunset-champagne/80 text-xs font-mono mb-6">Acquiring starlight coordinates &amp; optimal route...</p>
            
            <div class="bg-purple-950/80 rounded-xl p-4 border border-pink-400/20 text-left font-mono text-xs text-sunset-champagne space-y-2 mb-6">
                <div class="flex justify-between"><span>LAT/LONG:</span> <span id="scan-lat" class="text-pink-300">31.5204° N, 74.3587° E</span></div>
                <div class="flex justify-between"><span>SIGNAL SECURE:</span> <span class="text-emerald-400">STARLIGHT ENCRYPTED</span></div>
                <div class="flex justify-between"><span>STATUS:</span> <span id="scan-progress" class="text-yellow-300">READY FOR NAVIGATION</span></div>
            </div>

            <div class="flex gap-3">
                <button onclick="launchDirections()" class="flex-1 bg-gradient-to-r from-pink-400 to-yellow-400 hover:opacity-90 text-purple-950 font-bold py-3 rounded-xl transition-all shadow-lg uppercase tracking-wider text-xs flex items-center justify-center gap-2">
                    <i class="fa-solid fa-diamond-turn-right"></i> Launch GPS Route
                </button>
                <button onclick="closeScanner()" class="px-5 bg-purple-900/60 hover:bg-purple-900 text-sunset-champagne border border-pink-400/40 font-medium py-3 rounded-xl transition-all uppercase tracking-wider text-xs">
                    Close
                </button>
            </div>
        </div>
    </div>

    <!-- Background Particle Canvas -->
    <canvas id="particle-canvas" class="fixed inset-0 pointer-events-none z-0"></canvas>

    <!-- Header / Navbar -->
    <header class="fixed top-0 left-0 right-0 z-40 bg-dreamy-950/70 backdrop-blur-md border-b border-pink-500/20">
        <div class="max-w-6xl mx-auto px-4 py-4 flex justify-between items-center">
            <a href="#home" class="serif-font text-2xl font-bold dreamy-gradient tracking-wider">S &amp; A</a>
            <nav class="hidden md:flex space-x-8 text-xs uppercase tracking-[0.2em] text-sunset-champagne font-medium">
                <a href="#home" class="hover:text-pink-300 transition-colors">Home</a>
                <a href="#couple" class="hover:text-pink-300 transition-colors">The Couple</a>
                <a href="#events" class="hover:text-pink-300 transition-colors">Events &amp; Scanner</a>
                <a href="#rsvp" class="hover:text-pink-300 transition-colors">RSVP</a>
                <a href="#wishes" class="hover:text-pink-300 transition-colors">Wishes Wall</a>
            </nav>
            <button onclick="toggleMobileMenu()" class="md:hidden text-pink-300 text-xl focus:outline-none">
                <i class="fa-solid fa-bars"></i>
            </button>
        </div>
        <!-- Mobile Navigation Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-dreamy-950 border-b border-pink-500/20 px-4 pt-3 pb-6 space-y-3 text-center">
            <a href="#home" onclick="toggleMobileMenu()" class="block text-sunset-champagne hover:text-pink-300 text-sm py-1">Home</a>
            <a href="#couple" onclick="toggleMobileMenu()" class="block text-sunset-champagne hover:text-pink-300 text-sm py-1">The Couple</a>
            <a href="#events" onclick="toggleMobileMenu()" class="block text-sunset-champagne hover:text-pink-300 text-sm py-1">Events &amp; Scanner</a>
            <a href="#rsvp" onclick="toggleMobileMenu()" class="block text-sunset-champagne hover:text-pink-300 text-sm py-1">RSVP</a>
            <a href="#wishes" onclick="toggleMobileMenu()" class="block text-sunset-champagne hover:text-pink-300 text-sm py-1">Wishes Wall</a>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="relative min-h-screen flex items-center justify-center pt-24 pb-16 px-4 text-center z-10 overflow-hidden">
        <div class="absolute w-[600px] h-[600px] bg-pink-500/10 rounded-full blur-[140px] pointer-events-none"></div>
        <div class="absolute w-[400px] h-[400px] bg-yellow-500/10 rounded-full blur-[120px] pointer-events-none right-10 bottom-10"></div>
        
        <div class="max-w-4xl mx-auto space-y-6">
            <div class="inline-block border border-pink-400/40 rounded-full px-6 py-2 bg-purple-950/60 backdrop-blur-md shadow-lg animate-pulse">
                <p class="text-xs uppercase tracking-[0.3em] text-pink-300 font-semibold">With the Grace of Almighty Allah</p>
            </div>
            
            <h2 class="script-font text-4xl md:text-5xl text-pink-200">Bismillah-ir-Rahman-ir-Rahim</h2>
            
            <h1 class="serif-font text-5xl md:text-8xl font-bold dreamy-gradient tracking-wide py-2 leading-tight">
                Shahzaib Majeed <br class="hidden sm:inline">
                <span class="script-font text-4xl md:text-6xl text-pink-300 font-normal">&amp;</span> 
                Afifa Maryam
            </h1>

            <p class="text-sunset-champagne/90 text-sm md:text-base max-w-xl mx-auto font-light leading-relaxed">
                Together with our families, we cordially invite you to celebrate the joyous union of our hearts and lives.
            </p>

            <!-- Live Countdown Timer -->
            <div class="pt-2 pb-4">
                <p class="text-xs uppercase tracking-[0.25em] text-pink-300 font-semibold mb-4">Countdown to Mehndi Celebration</p>
                <div class="grid grid-cols-4 gap-3 max-w-md mx-auto">
                    <div class="glass-card rounded-2xl p-3 shadow-xl">
                        <span id="days" class="serif-font text-3xl md:text-4xl font-bold dreamy-gradient block">00</span>
                        <span class="text-[9px] md:text-[10px] uppercase tracking-widest text-sunset-champagne/70">Days</span>
                    </div>
                    <div class="glass-card rounded-2xl p-3 shadow-xl">
                        <span id="hours" class="serif-font text-3xl md:text-4xl font-bold dreamy-gradient block">00</span>
                        <span class="text-[9px] md:text-[10px] uppercase tracking-widest text-sunset-champagne/70">Hours</span>
                    </div>
                    <div class="glass-card rounded-2xl p-3 shadow-xl">
                        <span id="minutes" class="serif-font text-3xl md:text-4xl font-bold dreamy-gradient block">00</span>
                        <span class="text-[9px] md:text-[10px] uppercase tracking-widest text-sunset-champagne/70">Minutes</span>
                    </div>
                    <div class="glass-card rounded-2xl p-3 shadow-xl">
                        <span id="seconds" class="serif-font text-3xl md:text-4xl font-bold dreamy-gradient block">00</span>
                        <span class="text-[9px] md:text-[10px] uppercase tracking-widest text-sunset-champagne/70">Seconds</span>
                    </div>
                </div>
            </div>

            <div class="pt-4 flex flex-col sm:flex-row justify-center gap-4">
                <a href="#events" onclick="playClickSound()" class="bg-gradient-to-r from-pink-400 to-yellow-400 hover:opacity-90 text-purple-950 font-bold px-8 py-3.5 rounded-full transition-all shadow-xl tracking-wider text-xs uppercase flex items-center justify-center gap-2">
                    <i class="fa-solid fa-calendar-days"></i> View Events &amp; Locations
                </a>
                <a href="#rsvp" onclick="playClickSound()" class="glass-card hover:bg-pink-500/10 text-sunset-champagne font-bold px-8 py-3.5 rounded-full transition-all tracking-wider text-xs uppercase flex items-center justify-center gap-2">
                    <i class="fa-solid fa-envelope-open-text"></i> RSVP Now
                </a>
            </div>
        </div>
    </section>

    <!-- The Couple Section -->
    <section id="couple" class="py-20 px-4 relative z-10 bg-purple-950/30 border-y border-pink-500/20">
        <div class="max-w-5xl mx-auto text-center space-y-12">
            <div class="space-y-2">
                <span class="text-xs uppercase tracking-[0.3em] text-pink-300 font-semibold">The Bride &amp; Groom</span>
                <h2 class="serif-font text-4xl md:text-5xl font-bold dreamy-gradient">Destined in Starlight</h2>
            </div>

            <div class="grid md:grid-cols-2 gap-8 items-center">
                <!-- Groom Card -->
                <div class="glass-card rounded-3xl p-6 md:p-8 space-y-4 shadow-2xl relative overflow-hidden group">
                    <div class="absolute -right-10 -top-10 w-40 h-40 bg-pink-500/10 rounded-full blur-2xl"></div>
                    <div class="w-32 h-32 rounded-full border-2 border-pink-400 mx-auto overflow-hidden shadow-xl">
                        <img src="https://placehold.co/400x400/26123b/f7e7ce?text=Shahzaib" alt="Shahzaib Majeed" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <h3 class="serif-font text-3xl font-bold dreamy-gradient">Shahzaib Majeed</h3>
                    <p class="text-pink-300/80 text-xs uppercase tracking-widest">Son of Mr. &amp; Mrs. Majeed</p>
                    <p class="text-sunset-champagne/90 text-sm font-light leading-relaxed px-4">
                        "Ready to embark on the most beautiful dreamy journey of faith, love, and partnership."
                    </p>
                </div>

                <!-- Bride Card -->
                <div class="glass-card rounded-3xl p-6 md:p-8 space-y-4 shadow-2xl relative overflow-hidden group">
                    <div class="absolute -left-10 -top-10 w-40 h-40 bg-yellow-500/10 rounded-full blur-2xl"></div>
                    <div class="w-32 h-32 rounded-full border-2 border-pink-400 mx-auto overflow-hidden shadow-xl">
                        <img src="https://placehold.co/400x400/26123b/f7e7ce?text=Afifa" alt="Afifa Maryam" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <h3 class="serif-font text-3xl font-bold dreamy-gradient">Afifa Maryam</h3>
                    <p class="text-pink-300/80 text-xs uppercase tracking-widest">Daughter of Mr. &amp; Mrs. Samiullah</p>
                    <p class="text-sunset-champagne/90 text-sm font-light leading-relaxed px-4">
                        "Looking forward to a lifetime of shared laughter, magical moments, and unwavering support."
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Events & Location Scanner Section -->
    <section id="events" class="py-20 px-4 max-w-6xl mx-auto relative z-10">
        <div class="text-center space-y-2 mb-16">
            <span class="text-xs uppercase tracking-[0.3em] text-pink-300 font-semibold">Festivities &amp; GPS Radar</span>
            <h2 class="serif-font text-4xl md:text-5xl font-bold dreamy-gradient">Wedding Events &amp; Locations</h2>
            <p class="text-sunset-champagne/70 text-sm max-w-lg mx-auto">Explore our dreamy wedding itinerary and use our futuristic Location Scanner for precise GPS navigation.</p>
        </div>

        <div class="grid md:grid-cols-3 gap-8">
            <!-- Event 1: Mehndi -->
            <div class="glass-card rounded-3xl p-6 md:p-8 flex flex-col justify-between shadow-2xl group transition-all duration-300">
                <div class="space-y-4">
                    <div class="w-14 h-14 bg-pink-500/10 rounded-2xl flex items-center justify-center border border-pink-400/40 group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-music text-pink-300 text-xl"></i>
                    </div>
                    <span class="text-[10px] uppercase tracking-[0.25em] text-pink-300 font-bold block">Function 01</span>
                    <h3 class="serif-font text-3xl font-bold dreamy-gradient">The Mehndi</h3>
                    <div class="space-y-2.5 text-xs text-sunset-champagne/90 font-light pt-2">
                        <p class="flex items-center gap-2">
                            <i class="fa-regular fa-calendar text-pink-300 w-4"></i> 29-Oct-2026
                        </p>
                        <p class="flex items-center gap-2">
                            <i class="fa-regular fa-clock text-pink-300 w-4"></i> Time: 7 PM onward
                        </p>
                        <p class="flex items-center gap-2 pt-1">
                            <i class="fa-solid fa-location-dot text-pink-300 w-4"></i> Location: Nazir Garden
                        </p>
                    </div>
                </div>
                <div class="pt-8">
                    <button onclick="openScannerModal('Nazir Garden', '31.5497° N, 74.3436° E', 'https://www.google.com/maps/search/?api=1&query=Nazir+Garden')" class="w-full bg-pink-500/10 hover:bg-pink-500 text-pink-200 hover:text-purple-950 border border-pink-400/40 font-semibold py-3 rounded-xl transition-all text-xs uppercase tracking-wider flex items-center justify-center gap-2">
                        <i class="fa-solid fa-radar"></i> Location Scanner
                    </button>
                </div>
            </div>

            <!-- Event 2: Barat -->
            <div class="glass-card rounded-3xl p-6 md:p-8 flex flex-col justify-between shadow-2xl group transition-all duration-300 transform md:-translate-y-3 border-pink-400/80">
                <div class="space-y-4">
                    <div class="w-14 h-14 bg-pink-500/20 rounded-2xl flex items-center justify-center border border-pink-400 group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-ring text-pink-300 text-xl"></i>
                    </div>
                    <span class="text-[10px] uppercase tracking-[0.25em] text-pink-300 font-bold block">Function 02 (Main Event)</span>
                    <h3 class="serif-font text-3xl font-bold dreamy-gradient">The Barat</h3>
                    <div class="space-y-2.5 text-xs text-sunset-champagne/90 font-light pt-2">
                        <p class="flex items-center gap-2">
                            <i class="fa-regular fa-calendar text-pink-300 w-4"></i> 30 Oct 2026
                        </p>
                        <p class="flex items-center gap-2">
                            <i class="fa-solid fa-crown text-pink-300 w-4"></i> Sehra Bandi: 4 PM
                        </p>
                        <p class="flex items-center gap-2">
                            <i class="fa-regular fa-clock text-pink-300 w-4"></i> Timing: 6 PM to 9 PM
                        </p>
                        <p class="flex items-center gap-2 pt-1">
                            <i class="fa-solid fa-location-dot text-pink-300 w-4"></i> Location: Samiullah Associates Gazi Road
                        </p>
                    </div>
                </div>
                <div class="pt-8">
                    <button onclick="openScannerModal('Samiullah Associates Gazi Road', '31.4821° N, 74.3725° E', 'https://www.google.com/maps/search/?api=1&query=Samiullah+Associates+Gazi+Road')" class="w-full bg-gradient-to-r from-pink-400 to-yellow-400 hover:opacity-90 text-purple-950 font-bold py-3 rounded-xl transition-all text-xs uppercase tracking-wider flex items-center justify-center gap-2 shadow-lg">
                        <i class="fa-solid fa-radar"></i> Location Scanner
                    </button>
                </div>
            </div>

            <!-- Event 3: Valima -->
            <div class="glass-card rounded-3xl p-6 md:p-8 flex flex-col justify-between shadow-2xl group transition-all duration-300">
                <div class="space-y-4">
                    <div class="w-14 h-14 bg-pink-500/10 rounded-2xl flex items-center justify-center border border-pink-400/40 group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-champagne-glasses text-pink-300 text-xl"></i>
                    </div>
                    <span class="text-[10px] uppercase tracking-[0.25em] text-pink-300 font-bold block">Function 03</span>
                    <h3 class="serif-font text-3xl font-bold dreamy-gradient">The Valima</h3>
                    <div class="space-y-2.5 text-xs text-sunset-champagne/90 font-light pt-2">
                        <p class="flex items-center gap-2">
                            <i class="fa-regular fa-calendar text-pink-300 w-4"></i> 31-October 2026
                        </p>
                        <p class="flex items-center gap-2">
                            <i class="fa-regular fa-clock text-pink-300 w-4"></i> Timing: 12 AM - 4 PM (Lunch)
                        </p>
                        <p class="flex items-center gap-2 pt-1">
                            <i class="fa-solid fa-location-dot text-pink-300 w-4"></i> Location: NAWAB farm house
                        </p>
                    </div>
                </div>
                <div class="pt-8">
                    <button onclick="openScannerModal('NAWAB farm house', '31.4501° N, 74.3102° E', 'https://www.google.com/maps/search/?api=1&query=NAWAB+farm+house')" class="w-full bg-pink-500/10 hover:bg-pink-500 text-pink-200 hover:text-purple-950 border border-pink-400/40 font-semibold py-3 rounded-xl transition-all text-xs uppercase tracking-wider flex items-center justify-center gap-2">
                        <i class="fa-solid fa-radar"></i> Location Scanner
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- RSVP Form Section -->
    <section id="rsvp" class="py-20 px-4 relative z-10 bg-purple-950/30 border-y border-pink-500/20">
        <div class="max-w-2xl mx-auto">
            <div class="text-center space-y-2 mb-10">
                <span class="text-xs uppercase tracking-[0.3em] text-pink-300 font-semibold">Response Card</span>
                <h2 class="serif-font text-4xl md:text-5xl font-bold dreamy-gradient">Online RSVP Form</h2>
                <p class="text-sunset-champagne/70 text-sm">Please submit your attendance response by October 25, 2026.</p>
            </div>

            <form id="rsvp-form" onsubmit="handleRSVP(event)" class="glass-card rounded-3xl p-6 md:p-10 space-y-6 shadow-2xl">
                <div>
                    <label class="block text-xs uppercase tracking-widest text-sunset-champagne mb-2 font-medium">Your Full Name &amp; Title *</label>
                    <input type="text" id="guest-name" required placeholder="e.g. Dr. Ahmed Khan & Family" class="w-full bg-dreamy-950/60 border border-pink-400/30 rounded-xl px-4 py-3 text-sunset-champagne placeholder-sunset-champagne/40 text-sm focus:outline-none focus:border-pink-400 transition-colors">
                </div>

                <div class="grid md:grid-cols-2 gap-4">
                    <div>
                        <label class="block text-xs uppercase tracking-widest text-sunset-champagne mb-2 font-medium">Phone Number / Email *</label>
                        <input type="text" id="guest-contact" required placeholder="+92 300 1234567" class="w-full bg-dreamy-950/60 border border-pink-400/30 rounded-xl px-4 py-3 text-sunset-champagne placeholder-sunset-champagne/40 text-sm focus:outline-none focus:border-pink-400 transition-colors">
                    </div>
                    <div>
                        <label class="block text-xs uppercase tracking-widest text-sunset-champagne mb-2 font-medium">Attendance Status *</label>
                        <select id="guest-status" onchange="toggleEventSelection()" class="w-full bg-dreamy-950/60 border border-pink-400/30 rounded-xl px-4 py-3 text-sunset-champagne text-sm focus:outline-none focus:border-pink-400 transition-colors">
                            <option value="Attending" class="bg-dreamy-950">Joyfully Accepting</option>
                            <option value="Not Attending" class="bg-dreamy-950">Regretfully Declining</option>
                        </select>
                    </div>
                </div>

                <div id="events-selection-box">
                    <label class="block text-xs uppercase tracking-widest text-sunset-champagne mb-2 font-medium">Select Events You Will Attend *</label>
                    <div class="grid grid-cols-3 gap-3">
                        <label class="flex items-center gap-2 bg-dreamy-950/40 border border-pink-400/20 px-3 py-2.5 rounded-xl cursor-pointer hover:border-pink-400/50 text-xs text-sunset-champagne">
                            <input type="checkbox" name="events" value="Mehndi" checked class="accent-pink-400"> Mehndi
                        </label>
                        <label class="flex items-center gap-2 bg-dreamy-950/40 border border-pink-400/20 px-3 py-2.5 rounded-xl cursor-pointer hover:border-pink-400/50 text-xs text-sunset-champagne">
                            <input type="checkbox" name="events" value="Barat" checked class="accent-pink-400"> Barat
                        </label>
                        <label class="flex items-center gap-2 bg-dreamy-950/40 border border-pink-400/20 px-3 py-2.5 rounded-xl cursor-pointer hover:border-pink-400/50 text-xs text-sunset-champagne">
                            <input type="checkbox" name="events" value="Valima" checked class="accent-pink-400"> Valima
                        </label>
                    </div>
                </div>

                <div>
                    <label class="block text-xs uppercase tracking-widest text-sunset-champagne mb-2 font-medium">Wishes for Shahzaib &amp; Afifa</label>
                    <textarea id="guest-wish" rows="3" placeholder="Write a heartwarming blessing for the couple..." class="w-full bg-dreamy-950/60 border border-pink-400/30 rounded-xl px-4 py-3 text-sunset-champagne placeholder-sunset-champagne/40 text-sm focus:outline-none focus:border-pink-400 transition-colors resize-none"></textarea>
                </div>

                <button type="submit" onclick="playClickSound()" class="w-full bg-gradient-to-r from-pink-400 to-yellow-400 hover:opacity-90 text-purple-950 font-bold py-4 rounded-xl transition-all shadow-xl uppercase tracking-widest text-xs">
                    Confirm &amp; Send RSVP
                </button>
            </form>
        </div>
    </section>

    <!-- Live Wishes Wall Section -->
    <section id="wishes" class="py-20 px-4 max-w-4xl mx-auto relative z-10">
        <div class="text-center space-y-2 mb-12">
            <span class="text-xs uppercase tracking-[0.3em] text-pink-300 font-semibold">Wall of Blessings</span>
            <h2 class="serif-font text-4xl font-bold dreamy-gradient">Live Guest Wishes</h2>
            <p class="text-sunset-champagne/70 text-sm">Heartfelt messages from friends and family members.</p>
        </div>

        <div id="wishes-container" class="grid md:grid-cols-2 gap-4">
            <!-- Dynamic Wishes will be injected here and persisted in localStorage -->
        </div>
    </section>

    <!-- Footer -->
    <footer class="py-12 px-4 bg-dreamy-950 border-t border-pink-500/20 text-center space-y-4 relative z-10">
        <div class="serif-font text-3xl font-bold dreamy-gradient tracking-widest">Shahzaib &amp; Afifa</div>
        <p class="text-sunset-champagne/60 text-xs tracking-widest uppercase">We await your gracious presence with excitement and joy!</p>
        <p class="text-sunset-champagne/40 text-[10px] pt-4">&copy; 2026 Shahzaib &amp; Afifa Wedding Celebration. Built with Dreamy Precision.</p>
    </footer>

    <!-- JavaScript Application Logic -->
    <script>
        // --- Web Audio API Sound Effects & Ambient Melody ---
        let audioCtx = null;
        let isAudioPlaying = false;
        let ambientOscillator = null;
        let ambientGain = null;

        function initAudio() {
            if (!audioCtx) {
                audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            }
        }

        // Play gentle chime for buttons
        function playClickSound() {
            try {
                initAudio();
                if (!audioCtx) return;
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();
                osc.type = 'sine';
                osc.frequency.setValueAtTime(659.25, audioCtx.currentTime); // E5 note
                osc.frequency.exponentialRampToValueAtTime(987.77, audioCtx.currentTime + 0.1);
                gain.gain.setValueAtTime(0.04, audioCtx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.1);
                osc.connect(gain);
                gain.connect(audioCtx.destination);
                osc.start();
                osc.stop(audioCtx.currentTime + 0.1);
            } catch (e) {
                console.log("Audio not allowed yet");
            }
        }

        // Toggle Dreamy Ambient Soundscape
        function toggleAudio() {
            initAudio();
            const btnIcon = document.getElementById('audio-icon');
            if (!isAudioPlaying) {
                if (audioCtx.state === 'suspended') {
                    audioCtx.resume();
                }
                ambientOscillator = audioCtx.createOscillator();
                ambientGain = audioCtx.createGain();
                ambientOscillator.type = 'sine';
                ambientOscillator.frequency.setValueAtTime(329.63, audioCtx.currentTime); // E4 dreamy chord
                
                const filter = audioCtx.createBiquadFilter();
                filter.type = 'lowpass';
                filter.frequency.setValueAtTime(800, audioCtx.currentTime);

                ambientGain.gain.setValueAtTime(0.015, audioCtx.currentTime);
                
                ambientOscillator.connect(filter);
                filter.connect(ambientGain);
                ambientGain.connect(audioCtx.destination);
                
                ambientOscillator.start();
                isAudioPlaying = true;
                btnIcon.className = "fa-solid fa-volume-high text-lg";
            } else {
                if (ambientOscillator) {
                    ambientOscillator.stop();
                    ambientOscillator.disconnect();
                }
                isAudioPlaying = false;
                btnIcon.className = "fa-solid fa-volume-xmark text-lg";
            }
        }

        // --- Particle & Starlight Bokeh Background Canvas ---
        const canvas = document.getElementById('particle-canvas');
        const ctx = canvas.getContext('2d');
        let particles = [];

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 2.5 + 0.8;
                this.speedX = (Math.random() - 0.5) * 0.3;
                this.speedY = (Math.random() - 0.5) * 0.3 - 0.15;
                this.opacity = Math.random() * 0.7 + 0.2;
                this.color = Math.random() > 0.5 ? '255, 183, 197' : '255, 215, 0'; // Pink or Gold bokeh
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                if (this.y < 0) this.y = canvas.height;
                if (this.x < 0) this.x = canvas.width;
                if (this.x > canvas.width) this.x = 0;
            }
            draw() {
                ctx.fillStyle = `rgba(${this.color}, ${this.opacity})`;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        for (let i = 0; i < 85; i++) {
            particles.push(new Particle());
        }

        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(p => {
                p.update();
                p.draw();
            });
            requestAnimationFrame(animateParticles);
        }
        animateParticles();

        // --- Countdown Timer Logic (Target: 29-Oct-2026, 19:00:00) ---
        const weddingTimestamp = new Date('October 29, 2026 19:00:00').getTime();

        function updateCountdown() {
            const now = new Date().getTime();
            const distance = weddingTimestamp - now;

            if (distance < 0) {
                document.getElementById('days').innerText = '00';
                document.getElementById('hours').innerText = '00';
                document.getElementById('minutes').innerText = '00';
                document.getElementById('seconds').innerText = '00';
                return;
            }

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById('days').innerText = String(days).padStart(2, '0');
            document.getElementById('hours').innerText = String(hours).padStart(2, '0');
            document.getElementById('minutes').innerText = String(minutes).padStart(2, '0');
            document.getElementById('seconds').innerText = String(seconds).padStart(2, '0');
        }
        setInterval(updateCountdown, 1000);
        updateCountdown();

        // --- Mobile Menu Toggle ---
        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }

        // --- Location Scanner Modal Integration ---
        let currentMapsUrl = '';

        function openScannerModal(venueName, latLong, mapsUrl) {
            playClickSound();
            currentMapsUrl = mapsUrl;
            document.getElementById('scanner-venue-title').innerText = venueName;
            document.getElementById('scan-lat').innerText = latLong;
            document.getElementById('scanner-modal').classList.remove('hidden');

            const progressEl = document.getElementById('scan-progress');
            progressEl.innerText = "SCANNING STARLIGHT RADAR...";
            setTimeout(() => {
                progressEl.innerText = "COORDINATES VERIFIED (100%)";
            }, 1200);
        }

        function closeScanner() {
            document.getElementById('scanner-modal').classList.add('hidden');
        }

        function launchDirections() {
            playClickSound();
            if (currentMapsUrl) {
                window.open(currentMapsUrl, '_blank');
            }
            closeScanner();
        }

        // --- RSVP & Wishes Wall with LocalStorage Persistence ---
        let wishesList = JSON.parse(localStorage.getItem('wedding_wishes_shahzaib')) || [
            { name: "sadia", wish: "May Allah bless your marriage with endless happiness, prosperity, and everlasting love. Heartiest congratulations!", time: "Today" },
            { name: "Bilal", wish: "Wishing Shahzaib & Afifa a magnificent dreamy journey ahead as you build your new lives together!", time: "Yesterday" }
        ];

        function renderWishes() {
            const container = document.getElementById('wishes-container');
            container.innerHTML = '';
            wishesList.forEach(item => {
                const card = document.createElement('div');
                card.className = 'glass-card rounded-2xl p-5 space-y-2 shadow-md';
                card.innerHTML = `
                    <div class="flex justify-between items-center">
                        <span class="serif-font text-pink-300 font-bold text-lg">${escapeHtml(item.name)}</span>
                        <span class="text-[10px] text-sunset-champagne/50 uppercase tracking-widest">${escapeHtml(item.time)}</span>
                    </div>
                    <p class="text-sunset-champagne/90 text-xs italic">"${escapeHtml(item.wish)}"</p>
                `;
                container.appendChild(card);
            });
        }
        renderWishes();

        function toggleEventSelection() {
            const status = document.getElementById('guest-status').value;
            const box = document.getElementById('events-selection-box');
            if (status === 'Not Attending') {
                box.style.opacity = '0.4';
                box.style.pointerEvents = 'none';
            } else {
                box.style.opacity = '1';
                box.style.pointerEvents = 'auto';
            }
        }

        function handleRSVP(event) {
            event.preventDefault();
            const name = document.getElementById('guest-name').value;
            const status = document.getElementById('guest-status').value;
            const wish = document.getElementById('guest-wish').value.trim();

            const modal = document.getElementById('toast-modal');
            const title = document.getElementById('toast-title');
            const message = document.getElementById('toast-message');

            if (status === 'Attending') {
                title.innerText = "Thank You, " + name.split(' ')[0] + "!";
                message.innerText = "Your attendance has been confirmed. We eagerly look forward to celebrating with you!";
            } else {
                title.innerText = "Response Recorded";
                message.innerText = "Thank you for informing us. You will be dearly missed in our celebrations!";
            }

            modal.classList.remove('hidden');

            if (wish) {
                wishesList.unshift({
                    name: name,
                    wish: wish,
                    time: "Just now"
                });
                localStorage.setItem('wedding_wishes_shahzaib', JSON.stringify(wishesList));
                renderWishes();
            }

            document.getElementById('rsvp-form').reset();
            toggleEventSelection();
        }

        function closeModal() {
            document.getElementById('toast-modal').classList.add('hidden');
        }

        function escapeHtml(text) {
            const map = { '&': '&amp;', '<': '&lt;', '>': '&gt;', '"': '&quot;', "'": '&#039;' };
            return text.replace(/[&<>"']/g, function(m) { return map[m]; });
        }
    </script>
</body>
</html>
