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
      display: flex;
      margin: 0;
      min-height: 100vh;
    }
    .sidebar {
      width: 220px;
      background-color: #f8f8f8;
      padding: 1.5rem;
      border-right: 1px solid #eee;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
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
    .grade-overview-box {
      position: absolute;
      top: 20px;
      left: 20px;
      background-color: #fff;
      border: 1px solid #ccc;
      border-radius: 10px;
      padding: 10px 15px;
      font-size: 0.85rem;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      z-index: 10;
    }
    .grade-overview-box span {
      display: block;
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
      display: inline-block;
      vertical-align: middle;
    }
    .grade-error-text {
      color: #dc3545;
      font-size: 0.8rem;
      margin-top: 4px;
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
  <!-- Sidebar with Vertical Buttons -->
  <div class="sidebar">
    <div class="flex flex-col gap-2 mt-auto">
      <a href="https://docs.google.com/document/d/1xe9krDjvvUrDFGY1bn4iDg_NHSHtk3PP5S_SjNl0-rQ/edit?usp=sharing" class="btn black-outline" target="_blank">README</a>
      <a href="https://2417735.github.io/crypterror/" class="btn black-outline" target="_blank">Crypterror</a>
      <a href="https://drive.google.com/drive/folders/1HEdPj6teJZ1kTmk-r2uzcGFjHI3ncf54" class="btn black-outline" target="_blank">Assignments</a>
      <a href="https://drive.google.com/drive/folders/1mHxn9k3QIyhbLMQW3lqhFvjcAtnh7va-?usp=drive_link" class="btn black-outline" target="_blank">Library</a>
      <a href="https://forms.gle/7DCt8EuLRgdPb9p5A" class="btn black-outline" target="_blank">Book Appointment</a>
      <button class="btn pink-outline" onclick="checkPassword()">Hif Lumen</button>
      <button class="btn pink-outline" onclick="openAITutor()">AI Tutor</button>
    </div>
  </div>

  <!-- Main Content -->
  <div class="profile-container">
    <!-- Grade Overview Box -->
    <div class="grade-overview-box">
      <span>Current: <span id="gradeValue">Loading...</span></span>
      <span>Max: 100%</span>
      <span id="gradeLoader" class="grade-loader"></span>
      <div id="gradeStatusOverlay" class="grade-error-text" style="display:none;"></div>
    </div>

    <!-- Profile Card -->
    <div class="profile-card">
      <header class="profile-header">
        <div class="profile-img-container">
          <img src="IMG_0503.jpg" alt="Profile" class="profile-img"/>
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
          <li><strong>Email:</strong> alamalkahaf@gmail.com</li>
          <li><strong>Location:</strong> Busan, South Korea</li>
        </ul>
      </section>

      <section class="profile-details">
        <h3>Academic Status</h3>
        <ul>
          <li><strong>University:</strong> Pusan National University</li>
          <li><strong>Major:</strong> Artificial Intelligence (AI)</li>
          <li><strong>Status:</strong> Undergraduate</li>
          <li><strong>Grade:</strong> See top-left</li>
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
    const GOOGLE_APPS_SCRIPT_URL = "https://script.googleusercontent.com/a/macros/donga.ac.kr/echo?user_content_key=AehSKLgsWmgERdsRJEWdY3bbusUYmzlHmQAjhXCQDEcockIAVrq2D2gcjj8bR9XER5gzPCtv0PHYC6c-3nx8lRg42MGbHLxPOwcXrJ_xrBJKhL_lz9hJD-CWTi3fm4l-DcM3jOVUTCbQylFeCVxZ2bDUCz5plGy8dbXOBfcHF36vSx9A-XHSIq1DYrtcVByS1s8jRczWf_RVnionKRvfKUBf7fOeEqYJJANccHn54W1xXDuEoEfWxlD2JEkQ41a_EoJYnM-2qFrYwSM7uHkrIx4&lib=MwRwjs1Y-2dWdCdr1hmgm9ArgiwDOqQhJ";

    async function fetchGrade() {
      const loader = document.getElementById('gradeLoader');
      const gradeValue = document.getElementById('gradeValue');
      const errorText = document.getElementById('gradeStatusOverlay');

      try {
        const response = await fetch(GOOGLE_APPS_SCRIPT_URL);
        const result = await response.json();

        if (result && result.grade !== undefined) {
          const grade = parseFloat(result.grade);
          loader.style.display = 'none';
          gradeValue.textContent = grade + '%';
        } else {
          throw new Error("Invalid grade data");
        }
      } catch (err) {
        console.error("Error fetching grade:", err);
        loader.style.display = 'none';
        errorText.style.display = 'block';
        errorText.textContent = "Failed to load grade.";
      }
    }

    function checkPassword() {
      const pwd = prompt("Enter password to access Hif Lumen:");
      if (pwd === "hiflumensecret") {
        window.location.href = "https://example.com/hif-lumen";
      } else {
        alert("Incorrect password.");
      }
    }

    function openAITutor() {
      window.open("https://tutor.openai.com/", "_blank");
    }

    window.onload = fetchGrade;
  </script>
</body>
</html>
