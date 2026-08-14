<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Senior Dev - Premium Landing Page</title>
    
    <!-- Fonts: Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
    
    <!-- Phosphor Icons (Modern Icons) -->
    <script src="https://unpkg.com/@phosphor-icons/web"></script>

    <!-- Tailwind CSS (Utility-first styling) -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: { sans: ['Inter', 'sans-serif'] },
                    colors: {
                        dark: '#050505',
                        primary: '#8b5cf6', // Violet
                        secondary: '#3b82f6', // Blue
                    }
                }
            }
        }
    </script>

    <style>
        /* --- Base & Utilities --- */
        body {
            background-color: #050505;
            color: white;
            overflow-x: hidden;
        }

        /* Lenis Smooth Scroll Setup */
        html.lenis { height: auto; }
        .lenis.lenis-smooth { scroll-behavior: auto; }

        /* --- Custom Glassmorphism --- */
        .glass {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        .glass-nav {
            background: rgba(5, 5, 5, 0.5);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

        /* --- Background Orbs --- */
        .orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(100px);
            z-index: -1;
            animation: float 10s infinite ease-in-out alternate;
        }
        @keyframes float {
            0% { transform: translate(0, 0) scale(1); }
            100% { transform: translate(50px, 50px) scale(1.2); }
        }

        /* --- Loading Spinner Modern --- */
        .loader-ring {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            border: 3px solid transparent;
            border-top-color: #8b5cf6;
            border-right-color: #3b82f6;
            animation: spin 1s linear infinite;
        }
        @keyframes spin {
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="antialiased selection:bg-primary selection:text-white">

    <!-- 1. LOADING SCREEN -->
    <div id="loader" class="fixed inset-0 z-[100] bg-dark flex flex-col items-center justify-center">
        <div class="loader-ring mb-6"></div>
        <div class="overflow-hidden">
            <h2 id="loader-text" class="text-xl font-semibold tracking-widest text-gray-400 uppercase">
                Initializing...
            </h2>
        </div>
    </div>

    <!-- 2. MODERN NAVBAR -->
    <nav id="navbar" class="glass-nav fixed top-0 w-full z-50 px-8 py-5 flex justify-between items-center opacity-0 -translate-y-full">
        <div class="text-2xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-primary to-secondary cursor-pointer">
            NEXUS<span class="text-white">.</span>
        </div>
        <ul class="hidden md:flex gap-8 text-sm font-medium text-gray-300">
            <li class="hover:text-white transition-colors cursor-pointer">Home</li>
            <li class="hover:text-white transition-colors cursor-pointer">Features</li>
            <li class="hover:text-white transition-colors cursor-pointer">Showcase</li>
        </ul>
        <button class="glass px-6 py-2 rounded-full text-sm font-semibold hover:bg-white/10 transition-all duration-300 flex items-center gap-2">
            Get Access <i class="ph ph-arrow-right"></i>
        </button>
    </nav>

    <!-- 3. HERO SECTION (Dengan Card & Animasi GSAP) -->
    <main class="relative min-h-screen flex items-center justify-center px-6 pt-20">
        <!-- Ambient Lights -->
        <div class="orb bg-primary w-[400px] h-[400px] top-[10%] left-[20%]"></div>
        <div class="orb bg-secondary w-[350px] h-[350px] bottom-[10%] right-[20%]" style="animation-delay: -5s;"></div>

        <div class="max-w-5xl w-full grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
            
            <!-- Hero Text -->
            <div id="hero-content" class="space-y-6">
                <div class="overflow-hidden">
                    <span class="hero-line block text-sm font-bold tracking-widest text-primary uppercase">Welcome to the future</span>
                </div>
                <div class="overflow-hidden">
                    <h1 class="hero-line text-5xl md:text-7xl font-extrabold leading-tight">
                        Build <br>
                        <span class="bg-clip-text text-transparent bg-gradient-to-r from-primary to-secondary">Faster.</span>
                    </h1>
                </div>
                <div class="overflow-hidden">
                    <p class="hero-line text-gray-400 text-lg max-w-md">
                        Membangun antarmuka modern tidak pernah semudah ini. Performa tingkat tinggi dipadukan dengan desain mutakhir.
                    </p>
                </div>
                <div class="overflow-hidden pt-4">
                    <div class="hero-line flex gap-4">
                        <button class="bg-white text-black px-8 py-3 rounded-full font-bold hover:scale-105 transition-transform">
                            Start Now
                        </button>
                    </div>
                </div>
            </div>

            <!-- Glass Card (dari request sebelumnya) -->
            <div id="hero-card" class="glass rounded-[32px] p-10 shadow-2xl relative group transform transition duration-500 hover:-translate-y-4 hover:shadow-primary/20">
                <div class="absolute inset-0 bg-gradient-to-br from-white/10 to-transparent opacity-0 group-hover:opacity-100 transition duration-500 rounded-[32px]"></div>
                
                <i class="ph ph-code text-5xl text-primary mb-6"></i>
                <h2 class="text-3xl font-bold mb-4">Senior Grade UI</h2>
                <p class="text-gray-400 leading-relaxed mb-8">
                    Card ini menggunakan styling utility dari Tailwind, dipadukan dengan custom glassmorphism. Semuanya dirender sempurna di 60 FPS.
                </p>
                <div class="flex items-center gap-4 border-t border-white/10 pt-6">
                    <img src="https://i.pravatar.cc/100?img=11" alt="Avatar" class="w-12 h-12 rounded-full ring-2 ring-primary">
                    <div>
                        <p class="text-sm font-bold">Alex Dev</p>
                        <p class="text-xs text-gray-500">Lead Engineer</p>
                    </div>
                </div>
            </div>
            
        </div>
    </main>

    <!-- 4. SCROLL SECTION (Mendemonstrasikan Animasi saat Scroll) -->
    <section class="min-h-screen py-32 px-6 relative z-10">
        <div class="max-w-6xl mx-auto">
            <div class="text-center mb-20 section-header opacity-0">
                <h2 class="text-4xl md:text-5xl font-bold mb-4">Mengapa Memilih Stack Ini?</h2>
                <p class="text-gray-400 max-w-2xl mx-auto">Fitur luar biasa yang membuat website kamu terasa seperti aplikasi native kelas premium.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Feature Cards -->
                <div class="feature-card glass p-8 rounded-3xl opacity-0 translate-y-10">
                    <div class="w-14 h-14 rounded-2xl bg-primary/20 flex items-center justify-center mb-6">
                        <i class="ph ph-wind text-3xl text-primary"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Tailwind CSS</h3>
                    <p class="text-gray-400 text-sm leading-relaxed">Utility-first framework. Membuat desain responsif dan konsisten dalam hitungan menit tanpa harus pusing memikirkan nama class.</p>
                </div>

                <div class="feature-card glass p-8 rounded-3xl opacity-0 translate-y-10">
                    <div class="w-14 h-14 rounded-2xl bg-secondary/20 flex items-center justify-center mb-6">
                        <i class="ph ph-film-script text-3xl text-secondary"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">GSAP Animation</h3>
                    <p class="text-gray-400 text-sm leading-relaxed">Standar industri untuk animasi web. Memberikan kontrol penuh atas *timeline* animasi dengan performa yang dirender langsung oleh GPU.</p>
                </div>

                <div class="feature-card glass p-8 rounded-3xl opacity-0 translate-y-10">
                    <div class="w-14 h-14 rounded-2xl bg-white/10 flex items-center justify-center mb-6">
                        <i class="ph ph-mouse-scroll text-3xl text-white"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Lenis Scroll</h3>
                    <p class="text-gray-400 text-sm leading-relaxed">Menghilangkan efek scroll kasar bawaan browser, menggantinya dengan momentum mulus yang memberikan kesan sangat elegan.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- LIBRARIES SCRIPTS -->
    <!-- GSAP Core & ScrollTrigger -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
    <!-- Studio Freight Lenis (Smooth Scroll) -->
    <script src="https://unpkg.com/@studio-freight/lenis@1.0.34/dist/lenis.min.js"></script>

    <!-- CUSTOM LOGIC SENIOR DEV -->
    <script>
        // 1. Inisialisasi Lenis (Smooth Scrolling Premium)
        const lenis = new Lenis({
            duration: 1.2,
            easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)), // Easing khusus
            smooth: true,
        });

        // Sinkronisasi Lenis dengan sistem *requestAnimationFrame* browser
        function raf(time) {
            lenis.raf(time);
            requestAnimationFrame(raf);
        }
        requestAnimationFrame(raf);

        // Sinkronisasi Lenis dengan GSAP ScrollTrigger
        gsap.registerPlugin(ScrollTrigger);
        lenis.on('scroll', ScrollTrigger.update);
        gsap.ticker.add((time)=>{ lenis.raf(time * 1000) });
        gsap.ticker.lagSmoothing(0);


        // 2. Master Timeline Animasi (Loader -> Navbar -> Hero)
        window.addEventListener('load', () => {
            // Kita buat timeline agar animasi berjalan berurutan seperti film
            const tl = gsap.timeline();

            // A. Animasi Loading Selesai
            tl.to("#loader-text", { opacity: 0, duration: 0.5, delay: 0.5 })
              .to(".loader-ring", { scale: 0, opacity: 0, duration: 0.5, ease: "back.in(1.7)" }, "-=0.3")
              .to("#loader", { yPercent: -100, duration: 0.8, ease: "power4.inOut" })
              
            // B. Navbar Turun dari atas
              .to("#navbar", { y: 0, opacity: 1, duration: 0.8, ease: "power3.out" }, "-=0.2")
              
            // C. Teks Hero Muncul satu per satu (Stagger effect)
              .fromTo(".hero-line", 
                  { y: 100, opacity: 0 }, 
                  { y: 0, opacity: 1, duration: 0.8, stagger: 0.15, ease: "power3.out" }, 
                  "-=0.4"
              )

            // D. Card Glassmorphism Muncul dengan efek rotasi 3D ringan
              .fromTo("#hero-card",
                  { y: 50, opacity: 0, rotationX: 10 },
                  { y: 0, opacity: 1, rotationX: 0, duration: 1, ease: "power3.out" },
                  "-=0.6"
              );
        });

        // 3. Scroll Animations (Akan tertrigger otomatis saat user scroll ke bawah)
        // Animasi Judul Section
        gsap.to(".section-header", {
            scrollTrigger: {
                trigger: ".section-header",
                start: "top 80%", // Mulai saat elemen berada 80% dari atas viewport
            },
            opacity: 1,
            y: -20,
            duration: 1,
            ease: "power2.out"
        });

        // Animasi Feature Cards (Muncul bergantian)
        gsap.to(".feature-card", {
            scrollTrigger: {
                trigger: ".feature-card",
                start: "top 85%",
            },
            opacity: 1,
            y: 0,
            duration: 0.8,
            stagger: 0.2, // Jarak waktu muncul antar card
            ease: "back.out(1.5)"
        });
    </script>
</body>
</html>
