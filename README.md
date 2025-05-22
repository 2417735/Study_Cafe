<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Personal Website</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Arial', sans-serif; }
    body { background-color: #f0f0f5; color: #333; line-height: 1.6; }
    .main-container { display: flex; min-height: 100vh; }
    .panel { flex: 1; display: flex; flex-direction: column; justify-content: center; align-items: center; padding: 40px; text-align: center; transition: all 0.3s ease; }
    .panel:hover { flex: 1.5; }
    .black-panel { background-color: #222; color: white; }
    .blue-panel { background-color: #0085ca; color: white; }
    .white-panel { background-color: white; color: #222; }
    .btn { padding: 12px 25px; border: 2px solid currentColor; border-radius: 5px; text-decoration: none; font-weight: bold; transition: all 0.3s; display: inline-block; border-width: 3px; }
    .btn:hover { background-color: white; color: #222; }
    .black-outline { border-color: black; color: black; }
    .pink-outline { border-color: #ff69b4; color: #ff69b4; }
    .bio-fixed { 
      position: fixed; 
      bottom: 10px; 
      left: 10px; 
      font-family: 'Courier New', monospace; 
      font-size: 0.9rem; 
      background: rgba(255, 255, 255, 0.8); 
      padding: 10px; 
      border-radius: 8px;
      border: 1px solid #ccc;
    }
    .grade-display {
      position: fixed;
      top: 10px;
      left: 10px;
      z-index: 1000;
      background: rgba(255, 255, 255, 0.9);
      padding: 15px;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      min-width: 200px;
      font-size: 1rem;
    }
    .grade-loader {
      width: 30px;
      height: 30px;
      border: 3px solid #f3f3f3;
      border-top: 3px solid #0085ca;
      border-radius: 50%;
      animation: spin 1s linear infinite;
      margin: 15px auto;
    }
    .grade-error {
      color: #dc3545;
      font-weight: normal;
    }
    @keyframes spin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }
    .pin-button {
      margin-top: 15px;
    }
  </style>
</head>
<body>

  <div class="grade-display">
    <div id="grade-loader" class="grade-loader"></div>
    <div id="grade-content" style="display: none;">
      <h3>Current Course Grade</h3>
      <div id="grade-value" style="font-size: 1.5rem; margin: 5px 0;">Loading...</div>
    </div>
  </div>

  <div class="main-container">
    <div class="panel black-panel">
      <h2>README</h2>
      <p>Learn more about me, my academic journey, and research interests.</p>
      <a href="https://docs.google.com/document/d/1xe9krDjvvUrDFGY1bn4iDg_NHSHtk3PP5S_SjNl0-rQ/edit?usp=sharing" class="btn black-outline" target="_blank">README</a>
    </div>
    <div class="panel blue-panel">
      <h2>Assignments</h2>
      <p>Access my assignments and projects.</p>
      <a href="https://drive.google.com/drive/folders/1HEdPj6teJZ1kTmk-r2uzcGFjHI3ncf54" class="btn black-outline" target="_blank">Open Assignments</a>
    </div>
     <div class="panel meroon-panel">
      <h2>Virtual library</h2>
      <p>project.</p>
      <a href="https://drive.google.com/drive/folders/1mHxn9k3QIyhbLMQW3lqhFvjcAtnh7va-?usp=drive_link" target="_blank">Open Assignments</a>
    </div>
    <div class="panel white-panel">
      <h2>Meet Me!</h2>
      <p>Schedule a meeting by filling out my form.</p>
      <a href="https://forms.gle/7DCt8EuLRgdPb9p5A" class="btn black-outline" target="_blank">Book Appointment</a>
      <button class="btn pink-outline pin-button" onclick="checkPassword()">Hif Lumen</button>
    </div>
  </div>

  <div class="bio-fixed">
    <p><strong>Name:</strong> ALAM AL KAHAF<br><strong>Phone:</strong> 010-9672-4615</p>
  </div>

  <script>
    async function fetchGrade() {
      const scriptUrl = "https://script.google.com/macros/s/AKfycbyrv47SQm8fSjKYhNt5izqHG0sD2AHEZSqH5GoCDFxL3XTwSNMV-B4cjusnh884o3n0uA/exec"; 
      const assignments = 85;
      const exams = 90;

      try {
        const response = await fetch(`${scriptUrl}?assignments=${assignments}&exams=${exams}`);
        if (!response.ok) throw new Error("Network response was not ok");

        const data = await response.json();
        document.getElementById("grade-loader").style.display = "none";
        document.getElementById("grade-content").style.display = "block";
        document.getElementById("grade-value").textContent = `${data.grade}%`;
      } catch (error) {
        document.getElementById("grade-loader").style.display = "none";
        document.getElementById("grade-content").style.display = "block";
        document.getElementById("grade-value").textContent = "Error loading grade";
        console.error("Fetch error:", error);
      }
    }

    function checkPassword() {
      const userInput = prompt("Enter password to access ChatGPT link:");
      if (userInput === "123") {
        window.open("https://chatgpt.com/share/68287b74-1070-8001-be40-25ccc12da934", "_blank");
      } else {
        alert("Incorrect password.");
      }
    }

    fetchGrade();
  </script>
</body>
</html>
