
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
            scroll-behavior: smooth;
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
            transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .details-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(15, 23, 42, 0.9);
            backdrop-filter: blur(10px);
            border-radius: 50%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 1.5rem;
            color: white;
            opacity: 0;
            transform: rotateY(180deg);
            transition: opacity 0.5s, transform 0.6s;
            text-align: center;
        }

        .profile-container:hover .details-overlay {
            opacity: 1;
            transform: rotateY(0deg);
        }

        .profile-container:hover .profile-circle {
            transform: rotateY(180deg);
        }

        /* --- UI ELEMENTS --- */
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

        .social-link {
            background-color: var(--card-bg);
            color: var(--text-color);
            transition: all 0.3s ease;
        }

        .social-link:hover {
            transform: translateY(-3px);
            background-color: var(--accent-color);
            color: white;
        }

        .project-box, .adventure-card {
            background-color: var(--card-bg);
            border: 1px solid rgba(128, 128, 128, 0.1);
            transition: all 0.3s ease;
            height: 100%;
        }

        .project-box:hover, .adventure-card:hover {
            transform: translateY(-8px);
            border-color: var(--accent-color);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }

        /* --- GRADIENTS --- */
        .fuji-gradient {
            background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
        }

        .jeju-gradient {
            background: linear-gradient(135deg, #0ea5e9 0%, #2563eb 100%);
        }

        @media (max-width: 768px) {
            .profile-circle { width: 280px; height: 280px; }
            .details-overlay { font-size: 0.75rem; padding: 1rem; }
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
                <h1 class="text-3xl font-bold tracking-tight">Portfolio</h1>
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
                    Business Management Student At Donga University. Focused on the intersection of data, strategy, and emerging technologies.
                </p>

                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <a href="mailto:2417735@donga.ac.kr" class="social-link p-4 rounded-2xl flex items-center font-medium">
                        <svg class="mr-3" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
                        2417735@donga.ac.kr
                    </a>
                    <a href="https://github.com/2417735" target="_blank" class="social-link p-4 rounded-2xl flex items-center font-medium">
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
                        <h4 class="text-xl font-bold mb-3">Vision & Journey</h4>
                        <p class="text-xs italic opacity-90 px-4 leading-relaxed">
                            “When I finish with track and field, I’ll change sports and move on. If I can’t race at the top level by 2016, then I want to turn my hand to another game – football.” <br>
                            <span class="block mt-2 font-bold">- Usain Bolt</span>
                        </p>
                        <div class="w-16 h-px bg-white/30 my-4"></div>
                        <div class="flex flex-wrap justify-center gap-2">
                            <span class="text-[9px] bg-blue-500 px-2 py-1 rounded-full uppercase font-bold text-white">Ai Data Analyst</span>
                            <span class="text-[9px] bg-purple-500 px-2 py-1 rounded-full uppercase font-bold text-white">SEO Optimizer</span>
                            <span class="text-[9px] bg-green-500 px-2 py-1 rounded-full uppercase font-bold text-white">Market Researcher</span>
                        </div>
                    </div>
                </div>
            </div>
        </main>

        <section id="projects" class="mb-32">
            <h3 class="text-2xl font-bold mb-10 flex items-center">
                <span class="w-8 h-1 bg-blue-500 mr-4"></span> Academic Projects
            </h3>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="project-box p-8 rounded-3xl flex flex-col justify-between">
                    <div>
                        <h4 class="text-xl font-bold mb-3 text-blue-500">Ai Data Analysis</h4>
                        <p class="text-sm opacity-70 mb-6 leading-relaxed text-gray-500">Using Ai to identify bugs and optimize datasets for academic research and thesis development.</p>
                    </div>
                    <a href="#" class="text-xs font-bold uppercase tracking-widest hover:text-blue-500 transition">View Report &rarr;</a>
                </div>
                <div class="project-box p-8 rounded-3xl flex flex-col justify-between">
                    <div>
                        <h4 class="text-xl font-bold mb-3 text-green-500">Personal Portal</h4>
                        <p class="text-sm opacity-70 mb-6 leading-relaxed text-gray-500">A study on building customized management portals leveraging artificial intelligence workflows.</p>
                    </div>
                    <a href="#" class="text-xs font-bold uppercase tracking-widest hover:text-green-500 transition">View Details &rarr;</a>
                </div>
                <div class="project-box p-8 rounded-3xl flex flex-col justify-between">
                    <div>
                        <h4 class="text-xl font-bold mb-3 text-yellow-500">Excel Formula Model</h4>
                        <p class="text-sm opacity-70 mb-6 leading-relaxed text-gray-500">Designing complex logical models in Excel assisted by generative Ai for business efficiency.</p>
                    </div>
                    <a href="#" class="text-xs font-bold uppercase tracking-widest hover:text-yellow-500 transition">Doc Link &rarr;</a>
                </div>
            </div>
        </section>

        <section id="adventures" class="mb-32">
            <h3 class="text-2xl font-bold mb-10 flex items-center">
                <span class="w-8 h-1 bg-red-500 mr-4"></span> Adventures & Insights
            </h3>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="adventure-card rounded-3xl overflow-hidden group">
                    <div class="h-48 overflow-hidden">
                        <img src="baomosa.jpeg" class="w-full h-full object-cover group-hover:scale-110 transition duration-500">
                    </div>
                    <div class="p-6">
                        <h4 class="text-lg font-bold mb-2">Hiking Geumjeongsan</h4>
                        <p class="opacity-70 text-xs leading-relaxed">A journey to the highest peak in Busan. A reflection on nature and discipline.</p>
                    </div>
                </div>
                <div class="adventure-card rounded-3xl overflow-hidden group">
                    <div class="h-48 overflow-hidden">
                        <img src="atomic-habits-james-clear-irustima.jpg" class="w-full h-full object-cover group-hover:scale-110 transition duration-500">
                    </div>
                    <div class="p-6">
                        <h4 class="text-lg font-bold mb-2">Atomic Habits</h4>
                        <p class="opacity-70 text-xs leading-relaxed">Insights into compound growth and life improvements through tiny daily habits.</p>
                    </div>
                </div>
                <div class="adventure-card rounded-3xl overflow-hidden group">
                    <div class="h-48 bg-slate-800 flex items-center justify-center">
                         <span class="text-white font-bold opacity-20 text-3xl italic">Cinema Review</span>
                    </div>
                    <div class="p-6">
                        <h4 class="text-lg font-bold mb-2">Apur Sangsar</h4>
                        <p class="opacity-70 text-xs leading-relaxed">Reviewing Satyajit Ray's masterpiece, exploring themes of life and resilience.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="jeju-adventure" class="mb-10">
            <div class="jeju-gradient rounded-[2.5rem] md:rounded-[3rem] p-8 md:p-16 text-white relative overflow-hidden shadow-2xl">
                <div class="absolute right-0 top-0 w-1/2 h-full opacity-30">
                    <img src="jeju3-17.jpeg" alt="Jeju Trip" class="w-full h-full object-cover">
                </div>
                <div class="relative z-10 max-w-xl">
                    <span class="bg-white/20 px-3 py-1 rounded-full text-[10px] uppercase font-bold tracking-widest">Featured Adventure</span>
                    <h2 class="text-4xl md:text-5xl font-bold mt-4 mb-6">Jeju Island Trip</h2>
                    <p class="opacity-90 leading-relaxed text-sm md:text-base">
                        Exploring the volcanic landscapes and serene coasts of Jeju. This trip was a deep dive into South Korea's natural beauty, from Hallasan to the emerald waters of the east.
                    </p>
                    <div class="mt-8 flex items-center space-x-4">
                        <div class="h-px w-12 bg-white/50"></div>
                        <span class="text-xs font-mono opacity-70 italic">Memories from the South</span>
                    </div>
                </div>
            </div>
        </section>

        <section id="fuji-tribute" class="fuji-gradient rounded-[2.5rem] md:rounded-[3rem] p-12 md:p-24 text-center text-white relative overflow-hidden">
            <div class="absolute inset-0 opacity-20 pointer-events-none">
                <img src="fuji-san-and-lake.jpg" class="w-full h-full object-cover">
            </div>
            <div class="relative z-10">
                <h2 class="text-7xl md:text-9xl font-black opacity-10 absolute -top-10 left-1/2 -translate-x-1/2 select-none">FUJI</h2>
                <h3 class="text-4xl md:text-6xl font-bold mb-6">富士山</h3>
                <p class="max-w-xl mx-auto opacity-80 leading-loose text-sm md:text-base px-4">
                    At 3,776 meters, Mt. Fuji is the peak of resilience. It stands as a silent mentor, teaching us that greatness is built on a solid foundation.
                </p>
                <div class="mt-10 text-[10px] tracking-[0.3em] opacity-40 uppercase font-mono">35.3606° N, 138.7274° E</div>
            </div>
        </section>

        <footer class="mt-20 pb-10 text-center opacity-40 text-xs">
            &copy; 2026 ALAM AL KAHAF • Designed with Passion
        </footer>

    </div>

    <script>
        const themeToggle = document.getElementById('theme-toggle');
        const body = document.body;

        themeToggle.addEventListener('click', () => {
            body.classList.toggle('dark-mode');
            const isDark = body.classList.contains('dark-mode');
            themeToggle.innerHTML = isDark 
                ? '<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-sun"><circle cx="12" cy="12" r="5"></circle><line x1="12" y1="1" x2="12" y2="3"></line><line x1="12" y1="21" x2="12" y2="23"></line><line x1="4.22" y1="4.22" x2="5.64" y2="5.64"></line><line x1="18.36" y1="18.36" x2="19.78" y2="19.78"></line><line x1="1" y1="12" x2="3" y2="12"></line><line x1="21" y1="12" x2="23" y2="12"></line><line x1="4.22" y1="19.78" x2="5.64" y2="18.36"></line><line x1="18.36" y1="5.64" x2="19.78" y2="4.22"></line></svg>'
                : '<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-moon"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path></svg>';
        });
    </script>
</body>
</html>
