<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ALAM AL KAHAF - Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        /* BASE STYLES */
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #ffffff;
            min-height: 100vh;
        }
        
        /* CONTENT CONTAINER */
        .main-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem 1.5rem;
        }

        /* SOCIAL/DOCUMENT LINK STYLING */
        .social-link {
            display: flex;
            align-items: center;
            padding: 1rem;
            margin-bottom: 0.5rem;
            border-radius: 8px;
            background-color: #f7f7f7;
            color: #333;
            font-weight: 500;
            transition: background-color 0.2s;
            text-decoration: none;
        }

        .social-link:hover {
            background-color: #ebebeb;
        }

        .social-icon {
            margin-right: 0.75rem;
            width: 20px;
            height: 20px;
        }
        
        /* RESPONSIVE PROFILE IMAGE SIZE */
        .profile-circle {
            width: 280px; 
            height: 280px; 
            margin-bottom: 1.5rem; 
        }

        @media (min-width: 768px) {
            .profile-circle {
                width: 384px; 
                height: 384px; 
                margin-bottom: 0;
            }
        }

        /* ADVENTURE/PROJECT BOX STYLING */
        .adventure-box {
            border: 1px solid #e5e5e5;
            padding: 1.5rem;
            border-radius: 12px;
            transition: box-shadow 0.3s, border-color 0.3s;
        }
        .adventure-box:hover {
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
            border-color: #d1d5db;
        }
    </style>
</head>
<body>

    <div class="main-content">
        
        <header class="mb-16">
            <h1 class="text-3xl font-bold mb-10">Portfolio</h1>
            <nav class="flex space-x-4 text-gray-500 font-medium overflow-x-auto whitespace-nowrap pb-1">
                <a href="#" class="text-black border-b-2 border-black pb-1">Home</a>
                <a href="#projects" class="hover:text-black">Projects</a>
                <a href="#" class="hover:text-black">About</a>
                <a href="#" class="hover:text-black">Contact</a>
            </nav>
        </header>
        
        ---

        <main class="grid lg:grid-cols-2 gap-12 items-start mb-20">
            
            <section class="order-2 lg:order-1">
                <p class="text-xl md:text-2xl mb-2">Hey there! 👋</p>
                <h2 class="text-4xl md:text-5xl font-bold mb-6">
                    I'm ALAM AL KAHAF.
                </h2>
                <p class="text-gray-500 mb-8">
                    2417735@donga.ac.kr
                </p>

                <h3 class="text-lg md:text-xl font-bold mb-3">Student & Analyst</h3>
                <p class="text-gray-700 leading-relaxed mb-8">
                    I am a student at **Donga University** specializing in data analysis and full-stack development. With a passion for transforming raw data into actionable insights and building robust web applications, I am dedicated to pushing the boundaries of technology and learning.
                </p>

                <blockquote class="border-l-4 border-gray-300 pl-4 italic text-gray-600 mb-12">
                    "The only way to do great work is to love what you do."
                    <footer class="mt-1 text-sm text-gray-500">Steve Jobs</footer>
                </blockquote>

                <div class="space-y-3">
                    <a href="YOUR_CV_LINK_HERE" target="_blank" class="social-link">
                        <svg class="social-icon" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M14.5 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V7.5L14.5 2z"/><polyline points="14 2 14 8 20 8"/><line x1="8" y1="15" x2="16" y2="15"/><line x1="8" y1="11" x2="16" y2="11"/><line x1="8" y1="19" x2="16" y2="19"/></svg>
                        Download CV / Resume
                    </a>
                    
                    <a href="YOUR_GOOGLE_DRIVE_LINK_HERE" target="_blank" class="social-link">
                        <svg class="social-icon" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 14.899A7 7 0 1 1 15.71 8h1.79a4.5 4.5 0 0 1 2.5 8.242M16 20h2"/><path d="M16 20l-1.5-1.5M16 20l-1.5 1.5"/><path d="M16 20l1.5-1.5M16 20l1.5 1.5"/></svg>
                        View Google Drive Files
                    </a>
                    
                    <a href="https://www.linkedin.com/in/kahaf-alam" target="_blank" class="social-link">
                        <svg class="social-icon" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>
                        LinkedIn
                    </a>
                    <a href="https://github.com/2417735" target="_blank" class="social-link">
                        <svg class="social-icon" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M15 22v-4a4.8 4.8 0 0 0-1-3.6.45.45 0 0 0-.6-.3c-.3 0-.6.1-.8.4a.5.5 0 0 1-.8.2c-.3-.2-.5-.4-.7-.6-.2-.2-.3-.5-.3-.9v-.3c0-.4 0-.8.1-1.2v-.2c-.3-.4-.6-.7-1-1.1s-1.1-.7-1.8-.7c-.8 0-1.4.2-1.9.7s-.8 1-.9 1.6c-.3.8-.4 1.7-.4 2.8v3.6c0 .4-.2.8-.5 1-.3.2-.8.3-1.3.3h-1.4v-3.6c0-.8.3-1.5.8-2s1.3-.9 2.1-1.1a14.7 14.7 0 0 1 1.7-1.4c.5-.3 1-.5 1.5-.5.4 0 .7.1 1.1.3s.7.5 1 .8.6.6.9 1a.5.5 0 0 0 .5.2.5.5 0 0 0 .5-.2v-1.1c0-.4.1-.7.2-1s.4-.6.7-.8c.4-.2.9-.3 1.5-.3h.1c.5 0 1 .1 1.4.3s.8.5 1.1.9c.3.4.5.8.6 1.3v.1c0 .5-.1 1-.3 1.4s-.5.7-.9 1c-.4.3-.8.6-1.2.7-.4.2-.8.3-1.3.3h-.1c.3.5.5 1.1.5 1.8v.7h-1.4zM12 2C6.5 2 2 6.5 2 12c0 4.4 2.9 8.2 7 9.5.5.1.7-.2.7-.5v-1.9c-2.8.6-3.4-1.2-3.4-1.2-.5-1.2-1.2-1.5-1.2-1.5-1-.7.1-.7.1-.7 1.1.1 1.7 1.1 1.7 1.1 1 .5 1.7.3 2.2.2.1-.8.4-1.2.7-1.5-2-.2-4.1-1-4.1-4.4 0-1 .4-2 .9-2.7C5.3 8.8 5 8 5.4 7c0 0 .8-.3 2.5 1.1a8.3 8.3 0 0 1 4.1 0c1.7-1.4 2.5-1.1 2.5-1.1.4 1 .1 1.8 0 2.4.6.7.9 1.7.9 2.7 0 3.4-2.1 4.2-4.1 4.4.4.4.8 1.1.8 2.2v3.3c0 .3.2.6.7.5C18.9 20.2 22 16.5 22 12c0-5.5-4.5-10-10-10"/></svg>
                        GitHub
                    </a>
                    <a href="https://www.youtube.com/@kahafalam3450" target="_blank" class="social-link">
                        <svg class="social-icon" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12.5 15.5l5.5 3V5l-5.5 3V5l-5.5 3v10.5l5.5-3z"/></svg>
                        YouTube
                    </a>
                </div>
            </section>

            <div class="order-1 lg:order-2 flex justify-center lg:justify-end">
                <div class="profile-circle rounded-full overflow-hidden bg-gray-200 shadow-xl">
                    <img 
                        src="unnamed.png" 
                        alt="ALAM AL KAHAF Profile Picture" 
                        class="w-full h-full object-cover object-center"
                    >
                </div>
            </div>
        </main>

        ---

        <section id="projects" class="pt-10 pb-20">
            <h2 class="text-3xl font-bold mb-8">My Adventures (Projects)</h2>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                
                <div class="adventure-box">
                    <h3 class="text-xl font-semibold mb-2 text-blue-600">Global Financial Analysis</h3>
                    <p class="text-gray-700 mb-4">
                        A comprehensive study using **Python (Pandas, NumPy)** and predictive modeling to forecast market trends across various global indices.
                    </p>
                    <a href="#" class="text-sm text-blue-500 hover:text-blue-700 font-medium">View Case Study &rarr;</a>
                </div>

                <div class="adventure-box">
                    <h3 class="text-xl font-semibold mb-2 text-green-600">E-Commerce Platform Rebuild</h3>
                    <p class="text-gray-700 mb-4">
                        Developed a scalable e-commerce backend using **Node.js** and **MongoDB**, resulting in a 30% reduction in server response time.
                    </p>
                    <a href="#" class="text-sm text-green-500 hover:text-green-700 font-medium">View Code on GitHub &rarr;</a>
                </div>

                <div class="adventure-box">
                    <h3 class="text-xl font-semibold mb-2 text-yellow-600">Donga University Tech Workshop</h3>
                    <p class="text-gray-700 mb-4">
                        Led a series of workshops teaching fundamentals of **SQL and data visualization** to over 50 undergraduate students.
                    </p>
                    <a href="#" class="text-sm text-yellow-500 hover:text-yellow-700 font-medium">See Photos & Details &rarr;</a>
                </div>

            </div>
        </section>

    </div>
</body>
</html>
