<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Personal Portfolio | Adventure Hub</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-color: #f8fafc;
            --text-color: #1e293b;
            --accent-color: #3b82f6;
            --card-bg: #ffffff;
            --shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
        }

        .dark-mode {
            --bg-color: #0f172a;
            --text-color: #f1f5f9;
            --accent-color: #60a5fa;
            --card-bg: #1e293b;
            --shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.3);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            transition: background-color 0.4s, color 0.4s;
            overflow-x: hidden;
            scroll-behavior: smooth;
            /* Bolt Cursor */
            cursor: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="black" stroke="white" stroke-width="2"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/></svg>'), auto;
        }

        .main-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 1.5rem;
        }

        /* --- IDENTITY CARD --- */
        .profile-wrapper {
            display: flex;
            justify-content: center;
            margin-bottom: 4rem;
        }

        .profile-container {
            position: relative;
            perspective: 1000px;
            width: 300px;
            height: 300px;
            cursor: pointer;
        }

        .profile-circle {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            overflow: hidden;
            border: 4px solid var(--accent-color);
            transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
            backface-visibility: hidden;
        }

        .profile-circle img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .details-overlay {
            position: absolute;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: rgba(15, 23, 42, 0.95);
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
            backface-visibility: hidden;
        }

        .profile-container:hover .details-overlay {
            opacity: 1;
            transform: rotateY(0deg);
        }

        .profile-container:hover .profile-circle {
            transform: rotateY(180deg);
        }

        /* --- ADVENTURE CARDS --- */
        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--accent-color);
        }

        .adventure-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .adventure-card {
            background-color: var(--card-bg);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid rgba(128, 128, 128, 0.1);
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .adventure-card:hover {
            transform: translateY(-10px);
            border-color: var(--accent-color);
        }

        .drive-box {
            border: 2px dashed var(--accent-color);
            background: linear-gradient(145deg, var(--card-bg), rgba(96, 165, 250, 0.05));
        }

        .course-img {
            width: 100%;
            height: auto;
            border-radius: 12px;
            margin: 1.5rem 0;
            border: 1px solid rgba(128, 128, 128, 0.2);
        }

        /* --- INSIGHTS SECTION --- */
        .insights-wrapper {
            margin-top: 1.5rem;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(128, 128, 128, 0.2);
        }

        .insight-header {
            display: flex;
            align-items: center;
            gap: 8px;
            margin-bottom: 1rem;
            color: var(--accent-color);
            font-weight: 700;
            text-transform: uppercase;
            font-size: 0.85rem;
            letter-spacing: 1px;
        }

        /* --- UI ELEMENTS --- */
        #theme-toggle {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            z-index: 1000;
            background: var(--accent-color);
            color: white;
            border: none;
            width: 55px;
            height: 55px;
            border-radius: 50%;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
            cursor: pointer;
            font-size: 1.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: transform 0.2s;
        }

        #theme-toggle:active { transform: scale(0.9); }

        @media (max-width: 768px) {
            .adventure-grid { grid-template-columns: 1fr; }
            .profile-container { width: 260px; height: 260px; }
        }
    </style>
</head>
<body class="dark-mode">

    <button id="theme-toggle" title="Toggle Theme">🌓</button>

    <div class="main-content">
        
        <div class="profile-wrapper">
            <div class="profile-container">
                <div class="profile-circle">
                    <img src="https://via.placeholder.com/300" alt="Identity">
                </div>
                <div class="details-overlay">
                    <h2>Rider Profile</h2>
                    <p>Skill Level: 2026 Pro</p>
                    <p>Status: Licensed In Korea</p>
                    <p style="margin-top:10px; font-size: 0.8rem; opacity: 0.8;">Hover to inspect</p>
                </div>
            </div>
        </div>

        <h2 class="section-title">Adventures & Insights</h2>

        <div class="adventure-grid">
            
            <div class="adventure-card drive-box">
                <div style="display:flex; justify-content:space-between; align-items:flex-start;">
                    <h3>Motorcycle License Quest</h3>
                    <span style="background: var(--accent-color); color: white; padding: 4px 10px; border-radius: 20px; font-size: 0.7rem; font-weight: bold;">NEW</span>
                </div>
                <p style="margin-top: 10px; font-size: 0.9rem; opacity: 0.8;">Tackling the "2nd Class Small" functional course at the Seoul Testing Center.</p>
                
                <img src="Gemini_Generated_Image_aein84aein84aein.png" alt="Motorcycle Course Map" class="course-img">

                <div class="insights-wrapper">
                    <div class="insight-header">
                        <span>💡</span> New Insights
                    </div>
                    <ul style="list-style: none; font-size: 0.9rem; line-height: 1.6;">
                        <li style="margin-bottom: 8px;">• <strong>The Crank Trick:</strong> The front wheel must almost touch the outer line to clear the inner corner.</li>
                        <li>• <strong>Personal Experience:</strong> [Replace this: Add your story about the test day and the specific bike used!]</li>
                    </ul>
                </div>
            </div>

            <div class="adventure-card">
                <h3>Future Project</h3>
                <p>Adventure details coming soon...</p>
                <div class="insights-wrapper">
                    <div class="insight-header"><span>🔒</span> Locked</div>
                    <p style="font-size: 0.85rem; opacity: 0.6;">Complete current quests to unlock.</p>
                </div>
            </div>

        </div>
    </div>

    <script>
        const btn = document.getElementById('theme-toggle');
        const body = document.body;

        // Theme Toggle Logic
        btn.addEventListener('click', () => {
            body.classList.toggle('dark-mode');
            const isDark = body.classList.contains('dark-mode');
            localStorage.setItem('theme', isDark ? 'dark' : 'light');
        });

        // Load saved theme
        if (localStorage.getItem('theme') === 'light') {
            body.classList.remove('dark-mode');
        }
    </script>
</body>
</html>
