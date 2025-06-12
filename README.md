<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>ALAM AL KAHAF - Personal Profile</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* General Body and Layout */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #222; /* Dark background */
            color: #333;
            display: flex; /* Use flex for sidebar and main content */
            margin: 0;
            min-height: 100vh;
        }
        /* Sidebar Styling */
        .sidebar {
            width: 220px; /* Fixed width sidebar */
            background-color: #f8f8f8; /* Light background for sidebar */
            padding: 1.5rem;
            border-right: 1px solid #eee;
            display: flex;
            flex-direction: column;
            justify-content: flex-end; /* Pushes buttons to the bottom */
            gap: 0.75rem; /* Space between buttons */
            flex-shrink: 0; /* Prevent sidebar from shrinking */
            position: relative; /* For grade box absolute positioning */
        }
        /* Button Styling within Sidebar */
        .btn {
            padding: 10px;
            border: 3px solid currentColor;
            border-radius: 5px;
            text-decoration: none;
            font-weight: bold;
            text-align: center;
            transition: all 0.3s;
            display: block; /* Make buttons take full width */
        }
        .btn:hover {
            background-color: currentColor;
            color: white;
        }
        .black-outline { border-color: #222; color: #222; }
        .pink-outline { border-color: #ff69b4; color: #ff69b4; }

        /* Grade Overview Box Styling */
        .grade-overview-box {
            position: absolute; /* Positioned within the sidebar */
            top: 20px;
            left: 20px;
            background-color: #fff;
            border: 1px solid #ccc;
            border-radius: 10px;
            padding: 10px 15px;
            font-size: 0.85rem;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            z-index: 10;
            min-width: 180px; /* Ensure it has enough width */
            text-align: left; /* Align text within the box */
        }
        .grade-overview-box span {
            display: block; /* Each detail on a new line */
            color: #222;
            font-weight: bold;
            margin: 2px 0;
        }
        .grade-loader {
            width: 14px;
            height: 14px;
            border: 2px solid rgba(255,255,255,0.3);
            border-top: 2px solid #0085ca;
            border-radius: 50%;
            animation: spin 1s linear infinite;
            display: inline-block; /* Keep it inline with text */
            vertical-align: middle; /* Align with text vertically */
            margin-left: 5px; /* Space from label */
        }
        .grade-error-text {
            color: #dc3545;
            font-size: 0.8rem;
            margin-top: 4px;
        }
        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }

        /* Main Profile Content Container */
        .profile-container {
            flex: 1; /* Takes remaining space */
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        .profile-card {
            background-color: #f8f8f8;
            border-radius: 1.5rem;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
            max-width: 900px;
            width: 100%;
            overflow: hidden;
            display: flex;
            flex-direction: column;
        }
        .profile-header {
            background-color: #f0f0f5;
            padding: 2.5rem;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            gap: 1.5rem;
        }
        .profile-img-container {
            width: 150px; height: 150px;
            border-radius: 50%;
            overflow: hidden;
            border: 4px solid white;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            flex-shrink: 0;
        }
        .profile-img { width: 100%; height: 100%; object-fit: cover; }
        .profile-details {
            padding: 1.5rem 2.5rem;
            background-color: white;
            border-top: 1px solid #eee;
        }
        .profile-details h3 {
            font-size: 1.6rem; font-weight: 700;
            color: #222;
            margin-bottom: 0.75rem;
            border-bottom: 2px solid #0085ca;
            padding-bottom: 0.25rem;
            display: inline-block;
        }
        .profile-details ul {
            list-style: none; padding-left: 0;
        }
        .profile-details li {
            margin-bottom: 0.5rem; color: #555; font-size: 1rem;
        }
        .profile-details li strong {
            color: #222;
            min-width: 80px;
            display: inline-block;
        }

        /* Responsive adjustments for overall layout */
        @media (max-width: 768px) {
            body {
                flex-direction: column; /* Stack sidebar and main content */
                padding: 10px;
            }
            .sidebar {
                width: 100%; /* Full width sidebar */
                height: auto; /* Auto height */
                padding: 1rem;
                border-right: none;
                border-bottom: 1px solid #eee;
                flex-direction: row; /* Buttons horizontally on top of mobile sidebar */
                flex-wrap: wrap; /* Allow buttons to wrap */
                justify-content: center;
                gap: 0.5rem;
                position: static; /* Remove fixed positioning on mobile */
            }
            .sidebar .grade-overview-box {
                position: static; /* Remove absolute positioning on mobile */
                margin-bottom: 1rem; /* Space below it */
                width: 100%; /* Full width within sidebar */
                text-align: center; /* Center content on mobile */
                box-shadow: none; /* Less prominent shadow on mobile */
            }
            .profile-container {
                padding: 10px;
            }
            .profile-card {
                border-radius: 1rem;
            }
            .profile-header {
                padding: 1.5rem;
                gap: 1rem;
            }
            .profile-img-container {
                width: 100px;
                height: 100px;
            }
            .profile-header h1 {
                font-size: 2rem;
            }
            .profile-header p {
                font-size: 0.9rem;
            }
            .profile-details {
                padding: 1rem;
            }
            .profile-details h3 {
                font-size: 1.2rem;
            }
            .profile-details li {
                font-size: 0.85rem;
            }
        }
    </style>
</head>
<body>
    <!-- Sidebar with Vertical Buttons and Grade Overview -->
    <div class="sidebar">
        <!-- Grade Overview Box (Now inside the sidebar) -->
        <div class="grade-overview-box">
            <span>My Total Grade:</span>
            <span>Current: <span id="gradeValue">Loading...</span></span>
            <span>Max: <span id="maxGradeValue">...</span></span> <!-- Added span for max value -->
            <span id="gradeLoader" class="grade-loader" style="display:none;"></span>
            <div id="gradeStatusOverlay" class="grade-error-text" style="display:none;"></div>
        </div>

        <div class="flex flex-col gap-2 mt-auto"> <!-- mt-auto pushes buttons to bottom -->
            <a href="https://docs.google.com/document/d/1xe9krDjvvUrDFGY1bn4iDg_NHSHtk3PP5S_SjNl0-rQ/edit?usp=sharing" class="btn black-outline" target="_blank">README</a>
            <a href="https://2417735.github.io/crypterror/" class="btn black-outline" target="_blank">Crypterror</a>
            <a href="https://drive.google.com/drive/folders/1HEdPj6teJZ1kTmk-r2uzcGFjHI3ncf54" class="btn black-outline" target="_blank">Assignments</a>
            <a href="https://drive.google.com/drive/folders/1mHxn9k3QIyhbLMQW3lqhFvjcAtnh7va-?usp=drive_link" class="btn black-outline" target="_blank">Library</a>
            <a href="https://forms.gle/7DCt8EuLRgdPb9p5A" class="btn black-outline" target="_blank">Book Appointment</a>
            <button class="btn pink-outline" onclick="checkPassword()">Hif Lumen</button>
            <button class="btn pink-outline" onclick="openAITutor()">AI Tutor</button>
        </div>
    </div>

    <!-- Main Content for Profile Card -->
    <div class="profile-container">
        <div class="profile-card">
            <header class="profile-header">
                <div class="profile-img-container">
                    <img src="uploaded:IMG_0503.jpg-18aab1bc-96a7-4324-b099-34df4fb512e1" alt="ALAM AL KAHAF Profile Picture" class="profile-img" onerror="this.onerror=null;this.src='https://placehold.co/150x150/9CA3AF/FFFFFF?text=Profile';"/>
                </div>
                <h1 class="text-3xl font-extrabold text-gray-900">ALAM AL KAHAF</h1>
                <p class="text-xl text-gray-700 font-semibold">Student & Developer</p>
                <p class="text-gray-600 max-w-lg text-center">
                    A passionate student exploring the realms of AI, web development, and cybersecurity. Dedicated to continuous learning and building impactful projects.
                </p>
            </header>

            <section class="profile-details">
                <h3>Personal Details</h3>
                <ul>
                    <li><strong>Name:</strong> ALAM AL KAHAF</li>
                    <li><strong>Phone:</strong> 010-9672-4615</li>
                    <li><strong>Email:</strong> your.email@example.com</li> <!-- REMINDER: Update your email here -->
                    <li><strong>Location:</strong> Busan, South Korea</li>
                </ul>
            </section>

            <section class="profile-details">
                <h3>Academic Status</h3>
                <ul>
                    <li><strong>University:</strong> [Your University Name]</li> <!-- REMINDER: Update your University -->
                    <li><strong>Major:</strong> [Your Major]</li> <!-- REMINDER: Update your Major -->
                    <li><strong>Status:</strong> [e.g., Undergraduate, Graduate]</li> <!-- REMINDER: Update your Academic Status -->
                    <li><strong>Grade:</strong> See top-left overview</li>
                </ul>
            </section>

            <section class="profile-details">
                <h3>Connect</h3>
                <ul>
                    <li><strong>GitHub:</strong> <a href="https://github.com/2417735" class="text-blue-600 hover:underline" target="_blank">github.com/2417735</a></li>
                    <li><strong>LinkedIn:</strong> <a href="#" class="text-blue-600 hover:underline" target="_blank">linkedin.com/in/yourprofile</a></li>
                    <li><strong>Portfolio:</strong> <a href="#" class="text-blue-600 hover:underline" target="_blank">yourportfolio.com</a></li>
                </ul>
            </section>
        </div>
    </div>

    <script>
        // Your DEPLOYED Google Apps Script URL.
        // It's crucial to make sure your Google Apps Script is deployed with access set to "Anyone".
        const GOOGLE_APPS_SCRIPT_URL = "https://script.googleusercontent.com/a/macros/donga.ac.kr/echo?user_content_key=AehSKLgsWmgERdsRJEWdY3bbusUYmzlHmQAjhXCQDEcockIAVrq2D2gcjj8bR9XER5gzPCtv0PHYC6c-3nx8lRg42MGbHLxPOwcXrJ_xrBJKhL_lz9hJD-CWTi3fm4l-DcM3jOVUTCbQylFeCVxZ2bDUCz5plGy8dbXOBfcHF36vSx9A-XHSIq1DYrtcVByS1s8jRczWf_RVnionKRvfKUBf7fOeEqYJJANccHn54W1xXDuEoEfWxlD2JEkQ41a_EoJYnM-2qFrYwSM7uHkrIx4&lib=MwRwjs1Y-2dWdCdr1hmgm9ArgiwDOqQhJ";

        /**
         * Fetches the grade from the deployed Google Apps Script and updates the grade overview box.
         * Now fetches 'current' and 'max' values and calculates the percentage.
         */
        async function fetchGrade() {
            const gradeLoader = document.getElementById('gradeLoader');
            const gradeValueSpan = document.getElementById('gradeValue'); // Span for the current grade
            const maxGradeValueSpan = document.getElementById('maxGradeValue'); // Span for the max grade
            const gradeStatusOverlay = document.getElementById('gradeStatusOverlay'); // Overlay for errors

            // Initial state: Show loader, hide text, reset values
            gradeLoader.style.display = 'inline-block'; // Use inline-block to align with text
            gradeValueSpan.textContent = 'Loading...';
            maxGradeValueSpan.textContent = '...'; // Show loading for max as well
            gradeStatusOverlay.style.display = 'none';

            try {
                console.log('Attempting to fetch grade from:', GOOGLE_APPS_SCRIPT_URL);
                const response = await fetch(GOOGLE_APPS_SCRIPT_URL);
                console.log('Fetch response received. Status:', response.status);

                if (!response.ok) {
                    const errorText = await response.text();
                    throw new Error(`HTTP error! status: ${response.status} - ${errorText.substring(0, 100)}...`);
                }

                const data = await response.json();
                console.log('Received data:', data);

                if (data.error) {
                    throw new Error(`Apps Script Error: ${data.error}`);
                }

                const current = data.current;
                const max = data.max;

                if (typeof current === 'number' && typeof max === 'number' && max > 0) {
                    const percentage = (current / max) * 100;
                    const displayPercentage = Math.round(percentage); // Round for cleaner display

                    gradeValueSpan.textContent = `${displayPercentage}%`;
                    maxGradeValueSpan.textContent = `${max}`; // Display the actual max value fetched
                    gradeValueSpan.style.color = '#222'; // Ensure text is visible
                    maxGradeValueSpan.style.color = '#222'; // Ensure text is visible

                    // No color change for the overview text itself, as it's not a bar.
                    // If you want color cues, you'd add classes here and define them in CSS.
                    console.log(`Grade successfully displayed: ${displayPercentage}% (Current: ${current}, Max: ${max})`);

                } else {
                    gradeValueSpan.textContent = 'N/A';
                    maxGradeValueSpan.textContent = 'N/A';
                    gradeStatusOverlay.textContent = 'Invalid Data';
                    gradeStatusOverlay.style.display = 'block';
                    console.error("Invalid current/max values received:", { current, max }, "Expected numbers, Max > 0.");
                }

            } catch (error) {
                console.error("Error fetching grade:", error);
                gradeValueSpan.textContent = 'Error';
                maxGradeValueSpan.textContent = 'Error';
                gradeStatusOverlay.textContent = 'Failed to load grade.';
                gradeStatusOverlay.style.display = 'block';
            } finally {
                gradeLoader.style.display = 'none'; // Always hide loader in the end
            }
        }

        // Functions for your buttons (unchanged from previous version)
        function checkPassword() {
            const userInput = prompt("Enter password to access Hif Lumen:");
            if (userInput === "123") { // Make sure this matches your actual password
                window.open("https://chatgpt.com/share/68287b74-1070-8001-be40-25ccc12da934", "_blank");
            } else {
                alert("Incorrect password.");
            }
        }

        function openAITutor() {
            window.open("ai chat.html", "_blank"); // Ensure 'ai chat.html' path is correct
        }

        // Call fetchGrade when the DOM is fully loaded
        document.addEventListener('DOMContentLoaded', fetchGrade);
    </script>
</body>
</html>
