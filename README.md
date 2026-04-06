<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ALAM AL KAHAF | Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-color: #ffffff;
            --text-color: #1a1a1a;
            --accent-color: #3b82f6;
            --card-bg: #f7f7f7;
        }

        .dark-mode {
            --bg-color: #0f172a;
            --text-color: #f1f5f9;
            --accent-color: #60a5fa;
            --card-bg: #1e293b;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            transition: background-color 0.4s, color 0.4s;
            overflow-x: hidden;
        }

        .main-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem 1.5rem;
        }

        /* --- INTERACTIVE IDENTITY CARD --- */
        .profile-container {
            position: relative;
            cursor: pointer;
            perspective: 1000px;
        }

        .profile-circle {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            overflow: hidden;
            border: 4px solid var(--accent-color);
            transition: transform 0.5s ease;
        }

        .details-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(15, 23, 42, 0.85);
            backdrop-filter: blur(8px);
            border-radius: 50%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 2rem;
            color: white;
            opacity: 0;
            transform: rotateY(180deg);
            transition: opacity 0.5s, transform 0.5s;
            text-align: center;
        }

        .profile-container:hover .details-overlay {
            opacity: 1;
            transform: rotateY(0deg);
        }

        .profile-container:hover .profile-circle {
            transform: rotateY(180deg);
        }

        /* --- DARK MODE TOGGLE --- */
        #theme-toggle {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            z-index: 100;
            background: var(--accent-color);
            color: white;
            padding: 12px;
            border-radius: 50%;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            cursor: pointer;
            transition: transform 0.3s;
        }

        #theme-toggle:hover { transform: scale(1.1); }

        /* --- GENERAL UI EFFECTS --- */
        .social-link {
            background-color: var(--card-bg);
            color: var(--text-color);
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .social-link:hover {
            transform: translateX(8px);
            background-color: var(--accent-color);
            color: white;
        }

        .project-box, .adventure-card {
            background-color: var(--bg-color);
            border: 1px solid rgba(128, 128, 128, 0.2);
            transition: all 0.3s ease;
        }

        .project-box:hover {
            transform: translateY(-5px);
            border-color: var(--accent-color);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }

        .fuji-gradient {
            background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
        }

        /* Mobile specific adjustments */
        @media (max-width: 768px) {
            .profile-circle { width: 250px; height: 250px; }
            .details-overlay { font-size: 0.8rem; }
        }
    </style>
</head>
<body>

    <button id="theme-toggle" title="Toggle Night Mode">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-moon"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path></svg>
    </button>

    <div class="main-content">
        
        <header class="mb-16 flex justify-between items-center">
            <div>
                <h1 class="text-3xl font-bold">Portfolio</h1>
                <nav class="flex space-x-6 mt-4 text-sm font-medium opacity-70">
                    <a href="#" class="hover:text-blue-500 transition">Home</a>
                    <a href="#projects" class="hover:text-blue-500 transition">Projects</a>
                    <a href="#adventures" class="hover:text-blue-500 transition">Adventures</a>
                </nav>
            </div>
        </header>

        <main class="grid lg:grid-cols-2 gap-16 items-center mb-32">
            <section class="order-2 lg:order-1">
                <span class="text-blue-500 font-bold tracking-widest text-xs uppercase">Welcome to my world</span>
                <h2 class="text-5xl md:text-6xl font-bold mt-2 mb-6 tracking-tight">I'm Alam Al Kahaf</h2>
                <p class="text-lg opacity-80 leading-relaxed mb-8">
                    Data Analyst & Full-Stack Developer at **Donga University**. 
                    I turn complex data into visual stories and build digital experiences that matter.
                </p>

                <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                    <a href="mailto:2417735@donga.ac.kr" class="social-link p-4 rounded-xl flex items-center font-medium">
                        <svg class="mr-3" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
                        2417735@donga.ac.kr
                    </a>
                    <a href="https://github.com/2417735" target="_blank" class="social-link p-4 rounded-xl flex items-center font-medium">
                        <svg class="mr-3" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path></svg>
                        GitHub Profile
                    </a>
                </div>
            </section>

            <div class="order-1 lg:order-2 flex justify-center lg:justify-end">
                <div class="profile-container">
                    <div class="profile-circle shadow-2xl">
                        <img src="unnamed.png" alt="Profile" class="w-full h-full object-cover">
                    </div>
                    <div class="details-overlay">
                        <h4 class="text-xl font-bold mb-2">A </h4>
                        <p class="text-sm opacity-90 px-4">
                            “When I finish with track and field, I’ll change sports and move on. If I can’t race at the top level by 2016,then I want to turn my hand to another game – football because I can play and with enough effort I can get better.”* <br><br>
                            - Usain Bolt <br><br>
                           ___________________________
                        </p>
                        <div class="mt-6 flex space-x-2">
                            <span class="text-[10px] bg-blue-500 px-2 py-1 rounded">Ai Data Analyst</span>
                            <span class="text-[10px] bg-purple-500 px-2 py-1 rounded">SEO Optimizer</span>
                            <span class="text-[10px] bg-green-500 px-2 py-1 rounded">Market Researcher</span>
                        </div>
                    </div>
                </div>
            </div>
        </main>

        <section id="projects" class="mb-32">
            <h3 class="text-2xl font-bold mb-10 flex items-center">
                <span class="w-8 h-1 bg-blue-500 mr-4"></span> Academic Projects
            </h3>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="project-box p-8 rounded-2xl">
                    <h4 class="text-xl font-bold mb-3 text-blue-500">Ai Data Analysis Projects</h4>
                    <p class="text-sm opacity-70 mb-6 text-gray-500">Using Ai to find out the bugs and fix the file for academic thesis.</p>
                    <a href="#" class="text-xs font-bold uppercase tracking-widest hover:underline">View Report</a>
                </div>
                <div class="project-box p-8 rounded-2xl">
                    <h4 class="text-xl font-bold mb-3 text-green-500">Student Portal</h4>
                    <p class="text-sm opacity-70 mb-6 text-gray-500">Learn how to make a personal portal just using Ai</p>
                    <a href="#" class="text-xs font-bold uppercase tracking-widest hover:underline">Report</a>
                </div>
                <div class="project-box p-8 rounded-2xl">
                    <h4 class="text-xl font-bold mb-3 text-yellow-500">Excel Formula Model</h4>
                    <p class="text-sm opacity-70 mb-6 text-gray-500">Optimizing the data and using Ai to generate formula.</p>
                    <a href="#" class="text-xs font-bold uppercase tracking-widest hover:underline">Doc Link</a>
                </div>
            </div>
        </section>

        <section id="adventures" class="mb-32">
            <h3 class="text-2xl font-bold mb-10 flex items-center">
                <span class="w-8 h-1 bg-red-500 mr-4"></span> Adventures
            </h3>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="adventure-card rounded-3xl overflow-hidden group">
                    <div class="h-64 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1551632432-c735e82992a7?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover group-hover:scale-110 transition duration-500">
                    </div>
                    <div class="p-8">
                        <h4 class="text-xl font-bold mb-2">Hiking Geumjeongsan</h4>
                        <p class="opacity-70 text-sm">A journey to the highest peak in Busan. Reflection on nature and discipline.</p>
                    </div>
                </div>
                <div class="adventure-card rounded-3xl overflow-hidden group">
                    <div class="h-64 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1544716278-ca5e3f4abd8c?auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover group-hover:scale-110 transition duration-500">
                    </div>
                    <div class="p-8">
                        <h4 class="text-xl font-bold mb-2">Atomic Habits Review</h4>
                        <p class="opacity-70 text-sm">How 1% changes every day lead to massive coding improvements.</p>
                    </div>
                </div>
            </div>
            transition duration-500">
                    </div>
                    <div class="p-8">
                        <h4 class="text-xl font-bold mb-2"> Apur Sangsar</h4>
                        <p class="opacity-70 text-sm">Indian great writer and film director's classic movie review.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="fuji-tribute" class="fuji-gradient rounded-[3rem] p-12 md:p-24 text-center text-white relative overflow-hidden">
            <div class="relative z-10">
                <h2 class="text-7xl md:text-9xl font-black opacity-10 absolute -top-10 left-1/2 -translate-x-1/2">FUJI</h2>
                <h3 class="text-4xl md:text-6xl font-bold mb-6">富士山</h3>
                <p class="max-w-xl mx-auto opacity-80 leading-loose">
                    At 3,776 meters, Mt. Fuji is the peak of resilience. 
                    It stands as a silent mentor, teaching us that greatness is built on a solid foundation.
                </p>
                <div class="mt-10 text-[10px] tracking-[0.3em] opacity-40 uppercase">35.3606° N, 138.7274° E</div>
            </div>
        </section>

        <footer class="mt-20 pb-10 text-center opacity-40 text-xs">
            &copy; 2026 ALAM AL KAHAF • Designed with Passion
        </footer>

    </div>

    <script>
        // DARK MODE TOGGLE LOGIC
        const themeToggle = document.getElementById('theme-toggle');
        const body = document.body;

        themeToggle.addEventListener('click', () => {
            body.classList.toggle('dark-mode');
            const isDark = body.classList.contains('dark-mode');
            themeToggle.innerHTML = isDark 
                ? '<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-sun"><circle cx="12" cy="12" r="5"></circle><line x1="12" y1="1" x2="12" y2="3"></line><line x1="12" y1="21" x2="12" y2="23"></line><line x1="4.22" y1="4.22" x2="5.64" y2="5.64"></line><line x1="18.36" y1="18.36" x2="19.78" y2="19.78"></line><line x1="1" y1="12" x2="3" y2="12"></line><line x1="21" y1="12" x2="23" y2="12"></line><line x1="4.22" y1="19.78" x2="5.64" y2="18.36"></line><line x1="18.36" y1="5.64" x2="19.78" y2="4.22"></line></svg>'
                : '<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-moon"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path></svg>';
        });

        // PIN PROTECTION
        function checkPin(event) {
            event.preventDefault(); 
            const CORRECT_PIN = "2588";
            const DRIVE_URL = "YOUR_GOOGLE_DRIVE_LINK_HERE"; 
            const userPin = prompt("Enter PIN to view files:");
            if (userPin === CORRECT_PIN) {
                window.open(DRIVE_URL, '_blank');
            } else if (userPin) {
                alert("Access Denied.");
            }
        }
    </script>
</body>
</html>
