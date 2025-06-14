<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts - Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <style>
        /* Base body styling with Inter font and background image */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f0f4f8; /* Fallback background color */
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1rem; /* Add some padding around the main container */

            /* Background image styles */
            background-image: url('https://images.unsplash.com/photo-1519681393784-a9398f6d2e80?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');
            background-size: cover; /* Ensures the image covers the entire body */
            background-position: center; /* Centers the background image */
            background-attachment: fixed; /* Makes the background image fixed while content scrolls */
            background-repeat: no-repeat; /* Prevents repeating of the background image */
        }

        /* Custom button styling for gradient and hover effects */
        .btn-primary {
            background-image: linear-gradient(to right, #4F80E2 0%, #3B82F6 100%);
            transition: all 0.3s ease;
            box-shadow: 0 4px 14px 0 rgba(0, 118, 255, 0.39);
        }
        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px 0 rgba(0, 118, 255, 0.49);
        }
        .btn-secondary {
            border: 2px solid #3B82F6;
            color: #3B82F6;
            transition: all 0.3s ease;
        }
        .btn-secondary:hover {
            background-color: #E0F2FE; /* Light blue on hover */
            transform: translateY(-2px);
            box-shadow: 0 4px 10px 0 rgba(59, 130, 246, 0.2);
        }

        /* Styling for the grade overview box */
        .grade-overview-box-alt {
            background-color: #ffffff;
            border: 1px solid #e0e0e0;
            border-radius: 10px;
            padding: 15px 20px;
            font-size: 0.95rem;
            box-shadow: 0 4px 12px rgba(0,0,0,0.08);
            text-align: left;
            color: #333;
            margin-bottom: 1.5rem; /* Space below the box */
            transition: all 0.3s ease;
            transform: translateY(0);
        }
        .grade-overview-box-alt:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 16px rgba(0,0,0,0.12);
        }
        .grade-overview-box-alt span {
            display: block;
            color: #222;
            font-weight: bold;
            margin: 2px 0;
        }
        /* Loading spinner animation */
        .grade-loader-alt {
            width: 16px;
            height: 16px;
            border: 2px solid rgba(0,0,0,0.1);
            border-top: 2px solid #3b82f6; /* Blue for loader */
            border-radius: 50%;
            animation: spin 1s linear infinite;
            display: inline-block;
            vertical-align: middle;
            margin-left: 8px;
        }
        .grade-error-text-alt {
            color: #dc3545;
            font-size: 0.85rem;
            margin-top: 6px;
        }
        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }

        /* Custom button for sidebar-like resource buttons (now used for dropdown items) */
        .btn-resource-dropdown {
            @apply block w-full text-left px-4 py-2 text-sm text-gray-700 hover:bg-gray-100 hover:text-gray-900;
            transition: background-color 0.2s ease, color 0.2s ease;
        }
        /* Specific coloring for pink buttons (if still needed, though now part of dropdown items) */
        .btn-resource-dropdown.pink {
            color: #db2777; /* Dark pink text */
        }
        .btn-resource-dropdown.pink:hover {
            background-color: #ffe4e6; /* Light pink background on hover */
            color: #db2777;
        }

        /* Styling for the dropdown menu unordered list */
        #dropdownMenu ul {
            list-style: none; /* Remove default bullet points */
            padding: 0;
            margin: 0;
        }

        /* Animation for background blobs */
        @keyframes blob-animation {
            0% { transform: translate(-50%, -50%) scale(1); border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%; }
            50% { transform: translate(-55%, -45%) scale(1.05); border-radius: 30% 60% 70% 40% / 50% 60% 30% 60%; }
            100% { transform: translate(-50%, -50%) scale(1); border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%; }
        }
        .blob-top-left {
            animation: blob-animation 10s ease-in-out infinite alternate;
        }
        .blob-bottom-right {
            animation: blob-animation 12s ease-in-out infinite alternate-reverse;
        }

        /* Modal specific styles */
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
            position: relative; /* For the close button positioning */
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
        .modal-input {
            width: 100%;
            padding: 0.75rem;
            margin-top: 1rem;
            border: 1px solid #D1D5DB;
            border-radius: 0.5rem;
            font-size: 1rem;
        }
        .modal-action-button {
            @apply mt-4 px-6 py-2 rounded-lg font-medium text-white;
            background-image: linear-gradient(to right, #4F80E2 0%, #3B82F6 100%);
            transition: all 0.3s ease;
            box-shadow: 0 4px 14px 0 rgba(0, 118, 255, 0.39);
        }
        .modal-action-button:hover {
            transform: translateY(-1px);
            box-shadow: 0 6px 20px 0 rgba(0, 118, 255, 0.49);
        }
    </style>
</head>
<body class="antialiased">
    <!-- Main container with a rounded blue-ish border -->
    <div class="max-w-7xl mx-auto p-6 lg:p-10 bg-white rounded-3xl shadow-xl border-2 border-blue-100 relative overflow-hidden">

        <!-- Background wave/blob shape - Enhanced for visual appeal -->
        <div class="absolute top-0 left-0 w-80 h-80 bg-blue-50 rounded-full opacity-70 -translate-x-1/2 -translate-y-1/2 blob-top-left filter blur-2xl"></div>
        <div class="absolute bottom-0 right-0 w-80 h-80 bg-blue-50 rounded-full opacity-70 translate-x-1/2 -translate-y-1/2 blob-bottom-right filter blur-2xl"></div>

        <!-- Header Section -->
        <header class="flex flex-col lg:flex-row items-center justify-between py-4 px-6 mb-8 lg:mb-12 z-10 relative">
            <!-- Logo/Name -->
            <div class="flex items-center mb-4 lg:mb-0">
                <div class="w-10 h-10 bg-gradient-to-br from-blue-500 to-blue-700 text-white flex items-center justify-center rounded-full text-xl font-bold mr-3 shadow-md">A</div>
                <span class="text-2xl font-semibold text-gray-800">ALAM AL KAHAF</span>
            </div>

            <!-- Navigation Links -->
            <nav class="hidden lg:flex space-x-6 text-gray-600 font-medium">
                <a href="#about" class="hover:text-blue-600 transition-colors duration-200 py-1">About Me</a>
                <a href="#academic" class="hover:text-blue-600 transition-colors duration-200 py-1">Academic</a>
                <a href="#connect" class="hover:text-blue-600 transition-colors duration-200 py-1">Connect</a>
                <a href="#hikes" class="hover:text-blue-600 transition-colors duration-200 py-1">Adventures</a>
            </nav>

            <!-- Mobile Menu Toggle (Currently just an icon, would require JS for full functionality) -->
            <div class="flex items-center space-x-4">
                <button class="lg:hidden text-gray-600 focus:outline-none p-2 rounded-lg hover:bg-gray-100 transition-colors duration-200">
                    <!-- Hamburger Icon from Lucide -->
                    <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-menu">
                        <line x1="4" x2="20" y1="12" y2="12"/><line x1="4" x2="20" y1="6" y2="6"/><line x1="4" x2="20" y1="18" y2="18"/>
                    </svg>
                </button>
            </div>
        </header>

        <!-- Hero Section -->
        <section class="flex flex-col lg:flex-row items-center lg:items-start lg:justify-start px-6 pb-12 lg:pb-20 z-10 relative">
            <!-- Profile Image -->
            <div class="flex-shrink-0 mb-8 lg:mb-0 lg:mr-16">
                <!-- Profile picture from your previous code -->
                <img src="IMG_0503.jpg" alt="ALAM AL KAHAF Profile Picture" 
                     class="w-48 h-48 rounded-full object-cover shadow-xl border-4 border-white transform hover:scale-105 transition-transform duration-300"
                     onerror="this.onerror=null;this.src='https://placehold.co/192x192/E0F2FE/2563EB?text=Profile';">
            </div>

            <!-- Hero Content -->
            <div class="text-center lg:text-left">
                <p class="text-blue-600 text-lg font-medium mb-2">Student & Developer</p>
                <h1 class="text-5xl lg:text-6xl font-bold text-gray-900 leading-tight mb-6">ALAM AL KAHAF</h1>
                <p class="text-gray-600 text-lg leading-relaxed max-w-xl mb-8">
                    A passionate student exploring the realms of AI, web development, and cybersecurity. Dedicated to continuous learning and building impactful projects.
                </p>
                <!-- Combined buttons and new dropdown -->
                <div class="flex flex-col sm:flex-row justify-center lg:justify-start space-y-4 sm:space-y-0 sm:space-x-4">
                    <a href="https://docs.google.com/document/d/1xe9krDjvvUrDFGY1bn4iDg_NHSHtk3PP5S_SjNl0-rQ/edit?usp=sharing" class="btn-primary text-white px-8 py-3 rounded-xl text-lg font-medium" target="_blank">README</a>
                    <a href="https://2417735.github.io/crypterror/" class="btn-secondary px-8 py-3 rounded-xl text-lg font-medium" target="_blank">Crypterror</a>
                    
                    <!-- Dropdown Container -->
                    <div class="relative inline-block text-left">
                        <button id="dropdownButton" class="btn-secondary px-8 py-3 rounded-xl text-lg font-medium inline-flex items-center justify-center w-full sm:w-auto">
                            More Resources
                            <svg class="ml-2 -mr-1 w-5 h-5" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                                <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
                            </svg>
                        </button>
                        <div id="dropdownMenu" class="origin-top-right absolute right-0 sm:left-0 mt-2 w-56 rounded-md shadow-lg bg-white ring-1 ring-black ring-opacity-5 focus:outline-none hidden" role="menu" aria-orientation="vertical" aria-labelledby="dropdownButton">
                            <div class="py-1" role="none">
                                <span class="block px-4 py-2 text-xs text-gray-400 font-bold uppercase">Academic Resources</span>
                                <ul>
                                    <li><a href="https://drive.google.com/drive/folders/1HEdPj6teJZ1kTmk-r2uzcGFjHI3ncf54" class="btn-resource-dropdown" role="menuitem" target="_blank">Assignments</a></li>
                                    <li><a href="https://drive.google.com/drive/folders/1mHxn9k3QIyhbLMQW3lqhFvjcAtnh7va-?usp=drive_link" class="btn-resource-dropdown" role="menuitem" target="_blank">Library</a></li>
                                </ul>
                                <span class="block px-4 py-2 text-xs text-gray-400 font-bold uppercase mt-2">Interactive Tools</span>
                                <ul>
                                    <li><a href="https://forms.gle/7DCt8EuLRgdPb9p5A" class="btn-resource-dropdown" role="menuitem" target="_blank">Book Appointment</a></li>
                                    <li><button class="btn-resource-dropdown pink" role="menuitem" onclick="showPasswordModal()">Hif Lumen</button></li>

                                     
                                    <li><button class="btn-resource-dropdown pink" role="menuitem" onclick="openAITutor()">AI Tutor</button></li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Personal Details Section -->
        <section id="about" class="px-6 py-12 lg:py-16">
            <h2 class="text-3xl lg:text-4xl font-bold text-gray-900 mb-10 text-center lg:text-left">About Me</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 lg:gap-12 bg-blue-50 p-6 rounded-xl shadow-md">
                <div class="flex items-start">
                    <div class="flex-shrink-0 p-3 bg-blue-100 rounded-full mr-4 shadow-sm">
                        <!-- Example Icon (using Lucide) for general info -->
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-user icon">
                            <path d="M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2"/><circle cx="12" cy="7" r="4"/>
                        </svg>
                    </div>
                    <div>
                        <h3 class="text-xl font-semibold text-gray-800 mb-2">Personal Information</h3>
                        <ul class="list-none p-0 text-gray-600">
                            <li><strong>Name:</strong> ALAM AL KAHAF</li>
                            <li><strong>Phone:</strong> 010-9672-4615</li>
                            <li><strong>Email:</strong> 2417735@donga.ac.kr</li>
                            <li><strong>Location:</strong> Busan, South Korea</li>
                        </ul>
                    </div>
                </div>

                <div class="flex items-start">
                    <div class="flex-shrink-0 p-3 bg-blue-100 rounded-full mr-4 shadow-sm">
                        <!-- Example Icon for academic info -->
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-graduation-cap icon">
                            <path d="M21.42 10.922a1 1 0 0 0-.019-1.895L14.28 5.177a2.5 2.5 0 0 0-2.564 0L2.599 9.027a1 1 0 0 0-.019 1.895l8.125 3.529a2.5 2.5 0 0 0 2.564 0Z"/><path d="M12 14.5V21"/><path d="M12 14.5H2.6"/><path d="M12 14.5H21.4"/><path d="M16 16v-3a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v3"/>
                        </svg>
                    </div>
                    <div>
                        <h3 class="text-xl font-semibold text-gray-800 mb-2">Academic Status</h3>
                        <ul class="list-none p-0 text-gray-600">
                            <li><strong>University:</strong> Donga University</li>
                            <li><strong>Major:</strong> IBM</li>
                            <li><strong>Status:</strong> Bachelor</li>
                            <!-- Grade Display Area -->
                            <li>
                                <strong>Current Overall Grade:</strong> 
                                <div class="flex items-center mt-2"> <div class="grade-overview-box-alt inline-block p-2 mr-3">
                                        <span id="gradeValue">Loading...</span>
                                        <span id="gradeLoader" class="grade-loader-alt" style="display: none;"></span>
                                        <span id="gradeStatusOverlay" class="grade-error-text-alt" style="display: none;"></span>
                                    </div>
                                    <button onclick="fetchGrade()" class="btn-secondary px-4 py-2 rounded-lg text-sm font-medium">
                                        Check Grades
                                        <a href="https://script.google.com/macros/s/AKfycby3Ka5_TJzmfr_iyHXdC6GQxjzEk5m1-zEGCF3A4zaN/dev" 
                                    </button>
                                </div>
                            </li>

        <!-- Recent Adventures Section -->
        <section id="hikes" class="px-6 py-12 lg:py-16">
            <h2 class="text-3xl lg:text-4xl font-bold text-gray-900 mb-10 text-center lg:text-left">Recent Adventures</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-8">
                <!-- Hike 1: IMG_1894.jpeg (Panoramic view) -->
                <div class="bg-white rounded-xl shadow-lg overflow-hidden transition-transform duration-300 hover:scale-[1.02]">
                    <img src="IMG_1894.jpeg" alt="Hiking View over Busan" class="w-full h-64 object-cover"
                         onerror="this.onerror=null;this.src='https://placehold.co/600x400/E0F2FE/2563EB?text=Hike+View';">
                    <div class="p-6">
                        <h3 class="text-2xl font-semibold text-gray-800 mb-2">Siyak Mountain Summit</h3>
                        <p class="text-gray-600 mb-4">
                            A breathtaking hike up Siyak Mountain (510m) offering panoramic views of Busan, South Korea.
                            The clear skies provided an incredible backdrop for this memorable ascent.
                        </p>
                        <div class="flex justify-between items-center text-sm text-gray-500">
                            <span>
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-map-pin inline-block mr-1"><path d="M12 17.5l-4-4.5a6 6 0 1 1 8 0z"/><circle cx="12" cy="10" r="3"/></svg>
                                Busan, South Korea
                            </span>
                            <span>
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-calendar inline-block mr-1"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>
                                May 2025
                            </span>
                        </div>
                    </div>
                </div>
                <!-- Hike 2: IMG_1775.jpeg (Summit marker) -->
                <div class="bg-white rounded-xl shadow-lg overflow-hidden transition-transform duration-300 hover:scale-[1.02]">
                    <img src="IMG_1894.jpg" alt="Siyak Mountain stone marker" class="w-full h-64 object-cover"
                         onerror="this.onerror=null;this.src='https://placehold.co/600x400/E0F2FE/2563EB?text=Hike+Marker';">
                    <div class="p-6">
                        <h3 class="text-2xl font-semibold text-gray-800 mb-2">Siyak Mountain Summit Marker</h3>
                        <p class="text-gray-600 mb-4">
                            Reached the summit of Siyak Mountain (시약산) along the Nakdong Jeongmaek (낙동 정맥), standing tall at 510 meters. A rewarding experience!
                        </p>
                        <div class="flex justify-between items-center text-sm text-gray-500">
                            <span>
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-map-pin inline-block mr-1"><path d="M12 17.5l-4-4.5a6 6 0 1 1 8 0z"/><circle cx="12" cy="10" r="3"/></svg>
                                Siyak Mountain, Korea
                            </span>
                            <span>
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-calendar inline-block mr-1"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>
                                May 2025
                            </span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Connect Section -->
        <section id="connect" class="px-6 py-12 lg:py-16">
            <h2 class="text-3xl lg:text-4xl font-bold text-gray-900 mb-10 text-center lg:text-left">Connect With Me</h2>
            <div class="bg-blue-50 p-6 rounded-xl shadow-md">
                <ul class="list-none p-0 text-gray-600 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                    <li><strong>GitHub:</strong> <a href="https://github.com/2417735" class="text-blue-600 hover:underline" target="_blank">github.com/2417735</a></li>
                    <li><strong>LinkedIn:</strong> <a href="#" class="text-blue-600 hover:underline" target="_blank">linkedin.com/in/yourprofile</a></li>
                    <li><strong>Portfolio:</strong> <a href="#" class="text-blue-600 hover:underline" target="_blank">yourportfolio.com</a></li>
                </ul>
            </div>
        </section>

        <!-- Footer Section -->
        <footer class="text-center py-8 text-gray-500 text-sm mt-12 z-10 relative">
            <p>&copy; 2025 ALAM AL KAHAF. All rights reserved.</p>
        </footer>

    </div>

    <!-- Password Modal Structure -->
    <div id="passwordModal" class="modal-overlay">
        <div class="modal-content">
            <button class="modal-close-button" onclick="closePasswordModal()">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-x"><path d="M18 6 6 18"/><path d="m6 6 12 12"/></svg>
            </button>
            <h3 class="text-2xl font-semibold text-gray-800 mb-4">Access Hif Lumen</h3>
            <p class="text-gray-600">Please enter the password to proceed.</p>
            <input type="password" id="passwordInput" class="modal-input" placeholder="Enter password" onkeydown="handlePasswordEnter(event)">
            <p id="passwordError" class="text-red-500 text-sm mt-2 hidden">Incorrect password. Please try again.</p>
            <button class="modal-action-button" onclick="verifyPassword()">Submit</button>
        </div>
    </div>

    <!-- JavaScript for Lucide Icons, Grade Fetching, Button Actions, and Modals -->
    <script src="https://unpkg.com/lucide@latest/dist/lucide.min.js"></script>
    
    <script> 
        // Updated Google Apps Script URL (consistent with grades.html)
        const GOOGLE_APPS_SCRIPT_URL = "https://script.google.com/macros/s/AKfycbwuQ5DsbxhXLm2uqi_Hqm41ugjPYuRZpc1kEmF-rOuJA_FyESsoW_P6JdRkBLVMut79vQ/exec";

        /**
         * Fetches and displays the current overall grade from Google Apps Script.
         */
        async function fetchGrade() {
            const gradeLoader = document.getElementById('gradeLoader');
            const gradeValueSpan = document.getElementById('gradeValue');
            const gradeStatusOverlay = document.getElementById('gradeStatusOverlay');

            // Show loading state
            if (gradeLoader) gradeLoader.style.display = 'inline-block';
            if (gradeValueSpan) {
                gradeValueSpan.textContent = 'Loading...';
                gradeValueSpan.style.color = '#4b5563'; // Neutral color during loading
            }
            if (gradeStatusOverlay) gradeStatusOverlay.style.display = 'none';

            try {
                const response = await fetch(GOOGLE_APPS_SCRIPT_URL);

                if (!response.ok) {
                    throw new Error(`HTTP error: ${response.status}`);
                }

                const data = await response.json();
                // Assuming the grade data format from the script is { current: number, max: number }
                if (data.error) {
                    throw new Error(data.error);
                }

                const current = data.current;
                const max = data.max;

                if (typeof current === 'number' && typeof max === 'number' && max > 0) {
                    const percent = Math.round((current / max) * 100);
                    if (gradeValueSpan) {
                        gradeValueSpan.textContent = `${percent}%`;
                        gradeValueSpan.style.color = '#10B981'; // Green for success
                    }
                } else {
                    throw new Error("Invalid grade data received.");
                }

            } catch (err) {
                console.error("Failed to fetch grade:", err);
                if (gradeValueSpan) {
                    gradeValueSpan.textContent = 'Error';
                    gradeValueSpan.style.color = '#EF4444'; // Red for error
                }
                if (gradeStatusOverlay) {
                    gradeStatusOverlay.textContent = 'Could not load grade.';
                    gradeStatusOverlay.style.display = 'block';
                }
            } finally {
                // Hide loader regardless of success or failure
                if (gradeLoader) gradeLoader.style.display = 'none';
            }
        }

        /**
         * Shows the password input modal.
         */
        function showPasswordModal() {
            const modal = document.getElementById('passwordModal');
            const passwordInput = document.getElementById('passwordInput');
            const passwordError = document.getElementById('passwordError');

            if (modal) {
                modal.classList.add('open');
            }
            if (passwordInput) {
                passwordInput.value = ''; // Clear previous input
                passwordInput.focus();    // Focus the input field
            }
            if (passwordError) {
                passwordError.style.display = 'none'; // Hide error message
            }
        }

        /**
         * Closes the password input modal.
         */
        function closePasswordModal() {
            const modal = document.getElementById('passwordModal');
            if (modal) {
                modal.classList.remove('open');
            }
        }

        /**
         * Verifies the entered password and grants access or shows an.
         */
        function verifyPassword() {
            const passwordInput = document.getElementById('passwordInput');
            const passwordError = document.getElementById('passwordError');
            const userInput = passwordInput ? passwordInput.value : '';

            if (userInput === CORRECT_PASSWORD) {
                window.open("https://chatgpt.com/share/68287b74-1070-8001-be40-25ccc12da934", "_blank");
                closePasswordModal();
            } else {
                if (passwordError) {
                    passwordError.style.display = 'block'; // Show error message
                }
            }
        }

        /**
         * Handles the 'Enter' key press in the password input field.
         * @param {KeyboardEvent} event - The keyboard event object.
         */
        function handlePasswordEnter(event) {
            if (event.key === 'Enter') {
                verifyPassword();
            }
        }

        /**
         * Function to open AI Tutor link.
         */
        function openAITutor() {
            window.open("ai chat.html", "_blank"); // Ensure 'ai chat.html' is in the correct path
        }

        // Dropdown logic
        const dropdownButton = document.getElementById('dropdownButton');
        const dropdownMenu = document.getElementById('dropdownMenu');

        function toggleDropdown() {
            if (dropdownMenu) {
                dropdownMenu.classList.toggle('hidden');
            }
        }

        function closeDropdown(event) {
            // Check if the click was outside the dropdown button and the dropdown menu
            if (dropdownMenu && !dropdownMenu.contains(event.target) && !dropdownButton.contains(event.target)) {
                dropdownMenu.classList.add('hidden');
            }
        }

        // Event listeners for dropdown
        document.addEventListener('DOMContentLoaded', () => {
            if (dropdownButton) {
                dropdownButton.addEventListener('click', toggleDropdown);
            }
            document.addEventListener('click', closeDropdown);

            // Initialize Lucide icons and fetch grade information on load
            lucide.createIcons();
            fetchGrade(); 
        });
    </script>
</body>
</html>
