
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts - Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- Lucide Icons CDN (for "What I Do" style sections if needed, though not directly used for your sections here) -->
    <script src="https://unpkg.com/lucide@latest/dist/lucide.min.js"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f0f4f8; /* Light background similar to the Alex Smith image */
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1rem; /* Add some padding around the main container */
        }
        /* Custom button styling for gradient and hover effects from Alex Smith design */
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

        /* Styling for the grade overview box, adapted for the light theme */
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

        /* Custom button for sidebar buttons, adapted for light theme */
        .btn-resource {
            padding: 12px 20px;
            border: 2px solid #d1d5db; /* Light gray border */
            border-radius: 12px;
            text-decoration: none;
            font-weight: 600; /* Semi-bold */
            text-align: center;
            transition: all 0.3s ease;
            display: block;
            font-size: 0.95rem;
            color: #4b5563; /* Darker gray text */
            background-color: #f9fafb; /* Very light background */
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }
        .btn-resource:hover {
            background-color: #e0f2fe; /* Light blue on hover */
            border-color: #93c5fd; /* Lighter blue border on hover */
            color: #2563eb; /* Darker blue text on hover */
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }
        /* Specific coloring for pink buttons */
        .btn-resource.pink {
            border-color: #fbcfe8; /* Light pink border */
            color: #db2777; /* Dark pink text */
            background-color: #ffe4e6; /* Light pink background */
        }
        .btn-resource.pink:hover {
            background-color: #fda4af; /* Darker pink on hover */
            border-color: #f472b6;
            color: white;
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
    </style>
</head>
<body class="antialiased">
    <!-- Main container with a rounded blue-ish border -->
    <div class="max-w-7xl mx-auto p-6 lg:p-10 bg-white rounded-3xl shadow-xl border-2 border-blue-100 relative overflow-hidden">

        <!-- Background wave/blob shape - Enhanced for visual appeal -->
        <div class="absolute top-0 left-0 w-80 h-80 bg-blue-50 rounded-full opacity-70 -translate-x-1/2 -translate-y-1/2 blob-top-left filter blur-2xl"></div>
        <div class="absolute bottom-0 right-0 w-80 h-80 bg-blue-50 rounded-full opacity-70 translate-x-1/2 translate-y-1/2 blob-bottom-right filter blur-2xl"></div>

        <!-- Header Section -->
        <header class="flex flex-col lg:flex-row items-center justify-between py-4 px-6 mb-8 lg:mb-12 z-10 relative">
            <!-- Logo/Name -->
            <div class="flex items-center mb-4 lg:mb-0">
                <div class="w-10 h-10 bg-gradient-to-br from-blue-500 to-blue-700 text-white flex items-center justify-center rounded-full text-xl font-bold mr-3 shadow-md">A</div>
                <span class="text-2xl font-semibold text-gray-800">ALAM AL KAHAF</span>
            </div>

            <!-- Navigation Links (Placeholder - can be adapted from your sidebar if fewer) -->
            <nav class="hidden lg:flex space-x-6 text-gray-600 font-medium">
                <a href="#about" class="hover:text-blue-600 transition-colors duration-200 py-1">About Me</a>
                <a href="#academic" class="hover:text-blue-600 transition-colors duration-200 py-1">Academic</a>
                <a href="#connect" class="hover:text-blue-600 transition-colors duration-200 py-1">Connect</a>
                <a href="#resources" class="hover:text-blue-600 transition-colors duration-200 py-1">Resources</a>
            </nav>

            <!-- Mobile Menu Toggle (No "Get it Now" as it was from previous design) -->
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
                <img src="IMG_0503.jpg" alt="ALAM AL KAHAF Profile Picture" class="w-48 h-48 rounded-full object-cover shadow-xl border-4 border-white transform hover:scale-105 transition-transform duration-300"/>
            </div>

            <!-- Hero Content -->
            <div class="text-center lg:text-left">
                <p class="text-blue-600 text-lg font-medium mb-2">Student & Developer</p>
                <h1 class="text-5xl lg:text-6xl font-bold text-gray-900 leading-tight mb-6">ALAM AL KAHAF</h1>
                <p class="text-gray-600 text-lg leading-relaxed max-w-xl mb-8">
                    A passionate student exploring the realms of AI, web development, and cybersecurity. Dedicated to continuous learning and building impactful projects.
                </p>
                <!-- Combined buttons from your original sidebar -->
                <div class="flex flex-col sm:flex-row justify-center lg:justify-start space-y-4 sm:space-y-0 sm:space-x-4">
                    <a href="https://docs.google.com/document/d/1xe9krDjvvUrDFGY1bn4iDg_NHSHtk3PP5S_SjNl0-rQ/edit?usp=sharing" class="btn-primary text-white px-8 py-3 rounded-xl text-lg font-medium" target="_blank">README</a>
                    <a href="https://2417735.github.io/crypterror/" class="btn-secondary px-8 py-3 rounded-xl text-lg font-medium" target="_blank">Crypterror</a>
                </div>
            </div>
         <!-- JavaScript for Grade Fetching and Button Actions -->
    <script>
        // Updated Google Apps Script URL
        const GOOGLE_APPS_SCRIPT_URL = "https://script.google.com/macros/s/AKfycbwuQ5DsbxhXLm2uqi_Hqm41ugjPYuRZpc1kEmF-rOuJA_FyESsoW_P6JdRmBLVMut79vQ/exec";

        // Function to fetch the grade from the Google Apps Script URL
        async function fetchGrade() {
            const gradeLoader = document.getElementById('gradeLoader');
            const gradeValueSpan = document.getElementById('gradeValue');
            const gradeStatusOverlay = document.getElementById('gradeStatusOverlay');

            // Show loader and hide error/value
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
                if (gradeLoader) gradeLoader.style.display = 'none'; // Always hide loader in the end
            }
        }
            <!-- Additional Buttons -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <a href="https://drive.google.com/drive/folders/1HEdPj6teJZ1kTmk-r2uzcGFjHI3ncf54" class="btn-resource" target="_blank">Assignments</a>
                <a href="https://drive.google.com/drive/folders/1mHxn9k3QIyhbLMQW3lqhFvjcAtnh7va-?usp=drive_link" class="btn-resource" target="_blank">Library</a>
                <a href="https://forms.gle/7DCt8EuLRgdPb9p5A" class="btn-resource" target="_blank">Book Appointment</a>
                <button class="btn-resource pink" onclick="checkPassword()">Hif Lumen</button>
                <button class="btn-resource pink" onclick="openAITutor()">AI Tutor</button>
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
                            <li><strong>Email:</strong> your.email@example.com</li>
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
                            <li><strong>University:</strong> [Your University Name]</li>
                            <li><strong>Major:</strong> [Your Major]</li>
                            <li><strong>Status:</strong> [e.g., Undergraduate, Graduate]</li>
                            <li><strong>Grade:</strong> See "My Resources & Tools"</li>
                        </ul>
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

    <!-- JavaScript for Grade Fetching and Button Actions -->
    
    <script>
    const GOOGLE_APPS_SCRIPT_URL = "https://script.googleusercontent.com/a/macros/donga.ac.kr/echo?user_content_key=AehSKLgsWmgERdsRJEWdY3bbusUYmzlHmQAjhXCQDEcockIAVrq2D2gcjj8bR9XER5gzPCtv0PHYC6c-3nx8lRg42MGbHLxPOwcXrJ_xrBJKhL_lz9hJD-CWTi3fm4l-DcM3jOVUTCbQylFeCVxZ2bDUCz5plGy8dbXOBfcHF36vSx9A-XHSIq1DYrtcVByS1s8jRczWf_RVnionKRvfKUBf7fOeEqYJJANccHn54W1xXDuEoEfWxlD2JEkQ41a_EoJYnM-2qFrYwSM7uHkrIx4&lib=MwRwjs1Y-2dWdCdr1hmgm9ArgiwDOqQhJ";

    async function fetchGrade() {
        const gradeLoader = document.getElementById('gradeLoader');
        const gradeValueSpan = document.getElementById('gradeValue');
        const gradeStatusOverlay = document.getElementById('gradeStatusOverlay');

        gradeLoader.style.display = 'inline-block';
        gradeValueSpan.textContent = 'Loading...';
        gradeStatusOverlay.style.display = 'none';

        try {
            const response = await fetch(GOOGLE_APPS_SCRIPT_URL);

            if (!response.ok) throw new Error(`HTTP error: ${response.status}`);

            const data = await response.json();
            if (data.error) throw new Error(data.error);

            const current = data.current;
            const max = data.max;

            if (typeof current === 'number' && typeof max === 'number' && max > 0) {
                const percent = Math.round((current / max) * 100);
                gradeValueSpan.textContent = `${percent}%`;
                gradeValueSpan.style.color = '#222';
            } else {
                gradeValueSpan.textContent = 'N/A';
                gradeStatusOverlay.textContent = 'Invalid data from server.';
                gradeStatusOverlay.style.display = 'block';
            }

        } catch (err) {
            console.error(err);
            gradeValueSpan.textContent = 'Error';
            gradeStatusOverlay.textContent = 'Could not load grade.';
            gradeStatusOverlay.style.display = 'block';
        } finally {
            gradeLoader.style.display = 'none';
        }
    }

    document.addEventListener('DOMContentLoaded', fetchGrade);

    
        // Function to check password for "Hif Lumen" access
        function checkPassword() {
            // Using a simple prompt; consider a custom modal for better UX
            const userInput = prompt("Enter password to access Hif Lumen:");
            if (userInput === "123") {
                window.open("https://chatgpt.com/share/68287b74-1070-8001-be40-25ccc12da934", "_blank");
            } else {
                // Using a simple alert; consider a custom modal for better UX
                alert("Incorrect password. Please try again.");
            }
        }

        // Function to open AI Tutor link
        function openAITutor() {
            window.open("ai chat.html", "_blank");
        }

        // Initialize Lucide icons (for the new section icons)
        lucide.createIcons();

        // Fetch grade when the DOM is fully loaded
        document.addEventListener('DOMContentLoaded', fetchGrade);
    </script>
</body>
</html>
