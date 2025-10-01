<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ALAM AL KAHAF - Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #f7f9fc;
            min-height: 100vh;
            display: flex;
            align-items: flex-start;
            justify-content: center;
            padding: 1rem;
            position: relative;
            overflow-x: hidden;
            scroll-behavior: smooth;
        }

        .main-container {
            background-color: #ffffff;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
            width: 100%;
            max-width: 1100px;
            overflow: hidden;
            position: relative;
            z-index: 10;
        }

        .bg-gradient-header {
            background: linear-gradient(90deg, #1d4ed8, #2563eb, #3b82f6);
            border-radius: 20px 20px 0 0;
            padding: 2rem;
            color: white;
            position: relative;
            z-index: 2;
        }

        .header-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }

        /* 1. Profile picture size fix: Added object-fit: cover for perfect display */
        .profile-picture {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 5px solid white;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            margin-bottom: 1rem;
            transition: transform 0.3s ease-in-out;
            object-fit: cover; /* Ensures the image covers the area without distortion */
            object-position: center; /* Centers the image */
        }

        .profile-picture:hover {
            transform: scale(1.05);
        }

        .social-icons a, .social-icons button {
            color: #dbeafe;
            transition: color 0.3s ease-in-out, transform 0.3s ease-in-out;
            margin: 0 0.75rem; /* Increased margin for better spacing */
            padding: 0.5rem 0.75rem; /* Added padding for a clickable area */
            border-radius: 8px;
            background-color: rgba(255, 255, 255, 0.1);
            font-weight: 500;
        }
        
        /* New style for social links */
        .social-icons a {
            text-decoration: none;
        }

        .social-icons a:hover, .social-icons button:hover {
            color: white;
            background-color: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
        }

        .nav-link {
            transition: color 0.3s ease-in-out, border-bottom 0.3s ease-in-out;
            padding-bottom: 0.25rem;
            border-bottom: 2px solid transparent;
        }

        .nav-link:hover {
            color: #1e40af;
            border-bottom-color: #3b82f6;
        }

        /* 5. Mobile view fix: Use flex-wrap for nav items on smaller screens */
        .main-nav {
             display: flex;
             justify-content: center;
             flex-wrap: wrap; /* Allows items to wrap on smaller screens */
             gap: 0.75rem 1.5rem; /* Space between items when wrapped */
        }
        
        .section {
            padding: 2rem 1.5rem;
        }

        .section-title {
            color: #1e293b;
            border-bottom: 2px solid #e2e8f0;
            padding-bottom: 0.5rem;
            margin-bottom: 1.5rem;
            font-weight: 600;
        }

        .info-card {
            background-color: #f0f4f8;
            border-radius: 12px;
            padding: 1.5rem;
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
            margin-bottom: 1.5rem;
            height: 100%; /* Ensures cards in the grid have the same height */
        }

        .info-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.05);
        }

        .info-card-title {
            color: #1e293b;
            font-weight: 600;
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
        }

        .info-card-title svg {
            margin-right: 0.75rem;
            color: #4f46e5;
        }

        .info-list li {
            font-family: 'Inter', sans-serif;
            color: #4b5563;
            margin-bottom: 0.5rem;
        }
        
        .project-card {
            background-color: #ffffff;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
            padding: 1.5rem;
            display: flex;
            flex-direction: column;
            height: 100%;
        }
        
        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.1);
        }

        .project-card-image {
            width: 100%;
            height: 180px;
            object-fit: cover;
            border-radius: 8px;
            margin-bottom: 1rem;
        }

        .project-link-button {
            display: inline-block;
            background-color: #2563eb;
            color: white;
            font-weight: 600;
            padding: 0.75rem 1.5rem;
            border-radius: 9999px;
            transition: background-color 0.3s, transform 0.3s;
            margin-top: auto;
            text-align: center;
        }

        .project-link-button:hover {
            background-color: #1e40af;
            transform: scale(1.05);
        }

        /* Modal Styles */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.6);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }

        .modal-overlay.open {
            opacity: 1;
            visibility: visible;
        }

        .modal-content {
            background-color: #ffffff;
            padding: 2.5rem;
            border-radius: 1rem;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
            width: 90%;
            max-width: 400px;
            text-align: center;
            transform: translateY(-20px);
            opacity: 0;
            transition: transform 0.3s ease, opacity 0.3s ease;
            position: relative;
        }

        .modal-overlay.open .modal-content {
            transform: translateY(0);
            opacity: 1;
        }

        .modal-close-button {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #6B7280;
            transition: color 0.2s ease;
        }

        .modal-close-button:hover {
            color: #1F2937;
        }

        /* 5. Mobile view fix: Responsive Grid adjustments */
        @media (max-width: 640px) {
            .grid-cols-1-sm-2-lg-3 {
                grid-template-columns: 1fr;
            }
        }
        @media (min-width: 640px) and (max-width: 1024px) {
            .grid-cols-1-sm-2-lg-3 {
                grid-template-columns: repeat(2, minmax(0, 1fr));
            }
        }
        @media (min-width: 1024px) {
            .grid-cols-1-sm-2-lg-3 {
                grid-template-columns: repeat(3, minmax(0, 1fr));
            }
        }
        
        .button-option {
            display: block;
            background-color: #4f46e5;
            color: white;
            font-weight: 600;
            padding: 0.75rem 1.5rem;
            border-radius: 8px;
            margin-bottom: 1rem;
            text-decoration: none;
            transition: background-color 0.3s, transform 0.3s;
        }
        
        .button-option:hover {
            background-color: #4338ca;
            transform: scale(1.02);
        }
    </style>
</head>
<body class="antialiased">

    <div class="main-container">

        <header class="bg-gradient-header flex flex-col items-center">
            <div class="header-content">
                <img src="unnamed.png" alt="ALAM AL KAHAF Profile Picture" class="profile-picture">
                <h1 class="text-3xl font-bold mt-2">ALAM AL KAHAF</h1>
                <p class="text-sm font-medium mt-1 opacity-90">Student & Analyst </p>
                <div class="social-icons flex mt-4">
                    <a href="https://www.youtube.com/@kahafalam3450" target="_blank" title="YouTube Link">YouTube</a>
                    <button onclick="showInstagramModal()" class="flex items-center justify-center p-0" title="Instagram Profile">Instagram</button>
                    <a href="https://github.com/2417735" target="_blank" title="GitHub Profile">GitHub</a>
                </div>
            </div>
        </header>

        <nav class="bg-gray-50 py-4 border-b border-gray-200 sticky top-0 z-50">
            <div class="container mx-auto main-nav px-4 md:px-0">
                <a href="#about" class="nav-link text-gray-600 font-medium">About Me</a>
                <a href="#academic-projects" class="nav-link text-gray-600 font-medium">Academic Projects</a>
                <a href="#projects" class="nav-link text-gray-600 font-medium">My Projects</a>
                <button onclick="showReadMeModal()" class="nav-link text-gray-600 font-medium bg-transparent border-none cursor-pointer">README</button>
                <a href="https://drive.google.com/drive/folders/16IEAmmFaVHOD_y1dpCjGZiLzdloiM7FL?usp=drive_link" target="_blank" class="nav-link text-gray-600 font-medium">Google Drive</a>
                <a href="yourcv.pdf" download class="nav-link text-gray-600 font-medium">Download CV</a>
            </div>
        </nav>

        <main class="p-6 md:p-8">

            <section id="about" class="section">
                <h2 class="text-2xl section-title">About Me</h2>
                <div class="info-card">
                    <h3 class="info-card-title text-lg">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-user"><path d="M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2"/><circle cx="12" cy="7" r="4"/></svg>
                        Personal Information
                    </h3>
                    <ul class="info-list">
                        <li><strong>Name:</strong> ALAM AL KAHAF</li>
                        <li><strong>Phone:</strong> 010-9672-4615</li>
                        <li><strong>Email:</strong> 2417735@donga.ac.kr</li>
                        <li><strong>Location:</strong> Busan, South Korea</li>
                    </ul>
                </div>
            </section>
            
            ---

            <section id="academic-projects" class="section">
                <h2 class="text-2xl section-title">Academic Projects</h2>
                <div class="grid grid-cols-1-sm-2-lg-3 gap-6">
                    <div class="info-card">
                        <h3 class="info-card-title text-lg">
                            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-book-open"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"/><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"/></svg>
                            E-commerce Platform
                        </h3>
                        <ul class="info-list">
                            <li><strong>Course:</strong> Web Development Fundamentals</li>
                            <li><strong>Description:</strong> A full-stack e-commerce site with user authentication, product listings, and a shopping cart.</li>
                            <li><strong>Technologies:</strong> React, Node.js, Express, MongoDB</li>
                        </ul>
                    </div>
                    <div class="info-card">
                        <h3 class="info-card-title text-lg">
                            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-book-open"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"/><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"/></svg>
                            Data Analysis Dashboard
                        </h3>
                        <ul class="info-list">
                            <li><strong>Course:</strong> Data Science in Business</li>
                            <li><strong>Description:</strong> An interactive dashboard for visualizing sales and customer data to identify key business trends.</li>
                            <li><strong>Technologies:</strong> Python, Pandas, Matplotlib, Dash</li>
                        </ul>
                    </div>
                </div>
            </section>
            
            ---

            <section id="projects" class="section">
                <h2 class="text-2xl section-title">My Projects</h2>
                <div class="grid grid-cols-1-sm-2-lg-3 gap-6">
                    <div class="project-card">
                        <img src="https://placehold.co/600x400/E0F2FE/2563EB?text=Foreign" alt="Foreign Project" class="project-card-image">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Foreign Project</h3>
                        <p class="text-gray-600 text-sm mb-4">A web-based project for managing foreign student resources and information.</p>
                        <a href="https://2417735.github.io/Foreign/" target="_blank" class="project-link-button text-center">View Project</a>
                    </div>
                    <div class="project-card">
                        <img src="https://placehold.co/600x400/E0F2FE/2563EB?text=Crypterror" alt="Crypterror Project" class="project-card-image">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Crypterror</h3>
                        <p class="text-gray-600 text-sm mb-4">An application focused on cybersecurity concepts and cryptographic principles.</p>
                        <a href="https://2417735.github.io/crypterror/" target="_blank" class="project-link-button text-center">View Project</a>
                    </div>
                </div>
            </section>
            
            ---

            <section id="adventures" class="section">
                <h2 class="text-2xl section-title">Recent Adventures</h2>
                <div class="grid grid-cols-1-sm-2-lg-3 gap-6">
                    <div class="info-card">
                        <img src="jeju3-17.jpeg" alt="Jeju Island Trip" class="rounded-lg mb-4 w-full h-auto">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">My Jeju Trip 🌴</h3>
                        <p class="text-gray-600 text-sm">
                            An unforgettable adventure exploring the volcanic landscapes, stunning beaches, and unique culture of Jeju Island.
                        </p>
                        <p class="text-gray-400 text-xs mt-2">October 2025 (Placeholder)</p>
                    </div>
                    
                    <div class="info-card">
                        <img src="IMG_1775.jpeg" alt="Siyak Mountain Summit" class="rounded-lg mb-4 w-full h-auto">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Siyak Mountain Summit</h3>
                        <p class="text-gray-600 text-sm">
                            A breathtaking hike up Siyak Mountain (510m) offering panoramic views of Busan, South Korea.
                        </p>
                        <p class="text-gray-400 text-xs mt-2">May 2025</p>
                    </div>
                    <div class="info-card">
                        <img src="caption.jpg" alt="Donga University" class="rounded-lg mb-4 w-full h-auto">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Donga University</h3>
                        <p class="text-gray-600 text-sm">
                            Exploring the beautiful campus of Donga University, a mix of modern and traditional Korean architecture.
                        </p>
                        <p class="text-gray-400 text-xs mt-2">March 2025</p>
                    </div>
                </div>
            </section>

        </main>

        <footer class="text-center py-6 text-gray-500 text-sm border-t border-gray-200 mt-6">
            <p>&copy; 2025 ALAM AL KAHAF. All rights reserved.</p>
        </footer>
    </div>

    <div id="instagramModal" class="modal-overlay">
        <div class="modal-content !p-6">
            <button class="modal-close-button" onclick="closeInstagramModal()">
                <img src="WhatsApp Image 2025-09-22 at 2.05.23 PM.jpeg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-x"><path d="M18 6 6 18"/><path d="m6 6 12 12"/></svg>
            </button>
            <h3 class="text-xl font-semibold text-gray-800 mb-4">Scan to connect on Instagram</h3>
            <img src="https://i.ibb.co/6P01x6N/WhatsApp-Image-2025-09-22-at-2-05-23-PM.jpg" alt="Instagram QR Code" class="w-full max-w-xs mx-auto rounded-lg shadow-lg">
            <p class="text-lg font-medium text-gray-700 mt-4">@BEING_CHOTO</p>
        </div>
    </div>

    <div id="readMeModal" class="modal-overlay">
        <div class="modal-content">
            <button class="modal-close-button" onclick="closeReadMeModal()">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-x"><path d="M18 6 6 18"/><path d="m6 6 12 12"/></svg>
            </button>
            <h3 class="text-xl font-semibold text-gray-800 mb-6">Select a README Document</h3>
            <a href="https://docs.google.com/document/d/1xe9krDjvvUrDFGY1bn4iDg_NHSHtk3PP5S_SjNl0-rQ/edit?usp=sharing" target="_blank" class="button-option">
                Digital Literacy
            </a>
            <a href="https://docs.google.com/document/d/1CPx5GHMdnrahhT2PI1-otAzeyNKrGcKFs2yZfFKJJ_A/edit?tab=t.0" target="_blank" class="button-option">
                Master Assignment
            </a>
        </div>
    </div>

    <script src="https://unpkg.com/lucide@latest/dist/lucide.min.js"></script>
    <script>
        // Instagram Modal Functions
        function showInstagramModal() {
            const modal = document.getElementById('instagramModal');
            if (modal) {
                modal.classList.add('open');
            }
        }

        function closeInstagramModal() {
            const modal = document.getElementById('instagramModal');
            if (modal) {
                modal.classList.remove('open');
            }
        }
        
        // README Modal Functions (New)
        function showReadMeModal() {
            const modal = document.getElementById('readMeModal');
            if (modal) {
                modal.classList.add('open');
            }
        }

        function closeReadMeModal() {
            const modal = document.getElementById('readMeModal');
            if (modal) {
                modal.classList.remove('open');
            }
        }
        
        document.addEventListener('DOMContentLoaded', () => {
            lucide.createIcons();
        });
    </script>
</body>
</html>
