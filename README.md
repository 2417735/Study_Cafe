<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>ALAM AL KAHAF - Personal Profile</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      font-family: 'Inter', sans-serif;
      background-color: #222;
      color: #333;
      min-height: 100vh;
      display: flex;
      margin: 0;
    }
    .sidebar {
      width: 220px;
      background-color: #f8f8f8;
      padding: 1.5rem;
      border-right: 1px solid #eee;
      display: flex;
      flex-direction: column;
      gap: 0.75rem;
    }
    .btn {
      padding: 10px;
      border: 3px solid currentColor;
      border-radius: 5px;
      text-decoration: none;
      font-weight: bold;
      text-align: center;
      transition: all 0.3s;
      display: block;
    }
    .btn:hover {
      background-color: currentColor;
      color: white;
    }
    .black-outline { border-color: #222; color: #222; }
    .pink-outline { border-color: #ff69b4; color: #ff69b4; }
    .grade-bar-label {
      position: fixed; top: 5px; left: 240px;
      font-size: 0.8rem; color: #fff;
      background: rgba(0,0,0,0.4); padding: 2px 8px;
      border-radius: 5px; z-index: 1001;
    }
    .grade-display {
      position: fixed; top: 30px; left: 240px;
      width: 200px; height: 25px;
      background-color: #e0e0e0;
      border-radius: 9999px;
      overflow: hidden;
      box-shadow: 0 4px 6px rgba(0,0,0,0.1);
      z-index: 1000;
    }
    .grade-bar-fill {
      height: 100%;
      background-color: #e0e0e0;
      transition: width 0.5s ease-in-out, background-color 0.3s ease;
      display: flex; align-items: center;
      justify-content: flex-end;
      padding-right: 0.5rem;
      color: white;
      font-weight: bold;
      font-size: 0.875rem;
      width: 0%;
    }
    .grade-bar-fill span { white-space: nowrap; }
    .grade-loader {
      position: absolute;
      top: 50%; left: 50%;
      transform: translate(-50%, -50%);
      width: 20px; height: 20px;
      border: 2px solid rgba(255,255,255,0.3);
      border-top: 2px solid #0085ca;
      border-radius: 50%;
      animation: spin 1s linear infinite;
    }
    .grade-error-text {
      color: #dc3545;
      position: absolute;
      left: 0; right: 0;
      text-align: center;
      line-height: 25px;
    }
    @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }

    .profile-container {
      flex: 1;
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
  </style>
</head>
<body>

  <!-- Left Sidebar with Vertical Buttons -->
  <div class="sidebar">
    <a href="https://docs.google.com/document/d/1xe9krDjvvUrDFGY1bn4iDg_NHSHtk3PP5S_SjNl0-rQ/edit?usp=sharing" class="btn black-outline" target="_blank">README</a>
    <a href="https://2417735.github.io/crypterror/" class="btn black-outline" target="_blank">Crypterror</a>
    <a href="https://drive.google.com/drive/folders/1HEdPj6teJZ1kTmk-r2uzcGFjHI3ncf54" class="btn black-outline" target="_blank">Assignments</a>
    <a href="https://drive.google.com/drive/folders/1mHxn9k3QIyhbLMQW3lqhFvjcAtnh7va-?usp=drive_link" class="btn black-outline" target="_blank">Library</a>
    <a href="https://forms.gle/7DCt8EuLRgdPb9p5A" class="btn black-outline" target="_blank">Book Appointment</a>
    <button class="btn pink-outline" onclick="checkPassword()">Hif Lumen</button>
    <button class="btn pink-outline" onclick="openAITutor()">AI Tutor</button>
  </div>

  <!-- Main Content -->
  <div class="profile-container">
    <!-- Grade Bar Label & Display -->
    <div class="grade-bar-label">My Total Grade</div>
    <div class="grade-display" aria-label="Current course grade display">
      <div id="gradeLoader" class="grade-loader"></div>
      <div id="gradeBarFill" class="grade-bar-fill">
        <span id="gradeValue" style="display:none;"></span>
      </div>
      <div id="gradeStatusOverlay" class="grade-error-text" style="display:none;"></div>
    </div>

    <!-- Profile Card -->
    <div class="profile-card">
      <header class="profile-header">
        <div class="profile-img-container">
          <img src="uploaded:IMG_0503.jpg-18aab1bc-96a7-4324-b099-34df4fb512e1" alt="ALAM AL KAHAF Profile Picture" class="profile-img"
               onerror="this.onerror=null; this.src='https://placehold.co/150x150/9CA3AF/FFFFFF?text=Profile';"/>
        </div>
        <h1 class="text-3xl font-extrabold text-gray-900">ALAM AL KAHAF</h1>
        <p class="text-xl text-gray-700 font-semibold">Student & Developer</p>
        <p class="text-gray-600 max-w-lg text-center">
          A passionate student exploring AI, web development, and cybersecurity. Continuously learning and building impactful projects.
        </p>
      </header>

      <section class="profile-details">
        <h3>Personal Details</h3>
        <ul>
          <li><strong>Name:</strong> ALAM AL KAHAF</li>
          <li><strong>Phone:</strong> 010-9672-4615</li>
          <li><strong>Email:</strong> your.email@example.com</li>
          <li><strong>Location:</strong> Busan, South Korea</li>
        </ul>
      </section>

      <section class="profile-details">
        <h3>Academic Status</h3>
        <ul>
          <li><strong>University:</strong> [Your University Name]</li>
          <li><strong>Major:</strong> [Your Major]</li>
          <li><strong>Status:</strong> [Undergraduate / Graduate]</li>
          <li><strong>Current Grade:</strong> Shown above</li>
        </ul>
      </section>

      <section class="profile-details">
        <h3>Connect</h3>
        <ul>
          <li><strong>LinkedIn:</strong> <a href="#" class="text-blue-600 hover:underline" target="_blank">linkedin.com/in/yourprofile</a></li>
          <li><strong>GitHub:</strong> <a href="https://github.com/2417735" class="text-blue-600 hover:underline" target="_blank">github.com/2417735</a></li>
          <li><strong>Portfolio:</strong> <a href="https://yourportfolio.com" class="text-blue-600 hover:underline" target="_blank">yourportfolio.com</a></li>
        </ul>
      </section>
    </div>
  </div>

  <script>
    const GOOGLE_APPS_SCRIPT_URL = "https://script.google.com/macros/s/AKfycby3Ka5_TJzmfr_iyHXdC6GQxjzEk5m1-zEGCF3A4zaN/dev";

    async function fetchGrade() {
      const loader = document.getElementById('gradeLoader');
      const barFill = document.getElementById('gradeBarFill');
      const gradeText = document.getElementById('gradeValue');
      const overlay = document.getElementById('gradeStatusOverlay');

      loader.style.display = 'block';
      gradeText.style.display = 'none';
      overlay.style.display = 'none';
      barFill.style.width = '0%';
      barFill.style.backgroundColor = '#e0e0e0';

      try {
        const res = await fetch(GOOGLE_APPS_SCRIPT_URL);
        if (!res.ok) throw new Error(`HTTP ${res.status}`);
        const data = await res.json();
        if (data.error) throw new Error(data.error);

        const { current, max } = data;
        if (typeof current !== 'number' || typeof max !== 'number' || max <= 0) {
          throw new Error('Invalid grade data');
        }

        const pct = Math.round((current / max) * 100);
        barFill.style.width = pct + '%';
        gradeText.textContent = pct + '%';

        if (pct < 50) barFill.style.backgroundColor = '#EF4444';
        else if (pct < 75) barFill.style.backgroundColor = '#F59E0B';
        else barFill.style.backgroundColor = '#4CAF50';

      } catch (err) {
        console.error(err);
        overlay.textContent = 'Error loading grade';
        overlay.style.display = 'block';
        barFill.style.width = '0%';
        barFill.style.backgroundColor = '#EF4444';
        gradeText.textContent = 'Unavailable';
      } finally {
        loader.style.display = 'none';
        gradeText.style.display = overlay.style.display === 'block' ? 'none' : 'block';
      }
    }

    function checkPassword() {
      const pwd = prompt("Enter password:");
      if (pwd === "123") window.open("https://chatgpt.com/share/68287b74-1070-8001-be40-25ccc12da934", "_blank");
      else alert("Incorrect password.");
    }

    function openAITutor() {
      window.open("ai chat.html", "_blank");
    }

    document.addEventListener('DOMContentLoaded', fetchGrade);
  </script>
</body>
</html>
