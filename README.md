<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Almuhammady Futuristics Graphics</title>
  <link rel="stylesheet" href="style.css" />
  <script src="script.js" defer></script>
</head>
<body>
  <!-- Header -->
  <header>
    <h1>Almuhammady Futuristics Graphics</h1>
    <p>Showcasing world-class futuristic designs</p>
  </header>

  <!-- Categories -->
  <section id="categories">
    <div class="card">
      <img src="logos-sample.jpg" alt="Logos">
      <h2>Logos</h2>
      <button onclick="chatWhatsApp('Logos')">Chat on WhatsApp</button>
    </div>
    <div class="card">
      <img src="flyers-sample.jpg" alt="Flyers">
      <h2>Flyers</h2>
      <button onclick="chatWhatsApp('Flyers')">Chat on WhatsApp</button>
    </div>
    <div class="card">
      <img src="posters-sample.jpg" alt="Posters">
      <h2>Posters</h2>
      <button onclick="chatWhatsApp('Posters')">Chat on WhatsApp</button>
    </div>
    <div class="card">
      <img src="social-sample.jpg" alt="Social Media Graphics">
      <h2>Social Media Graphics</h2>
      <button onclick="chatWhatsApp('Social Media Graphics')">Chat on WhatsApp</button>
    </div>
    <div class="card">
      <img src="photo-sample.jpg" alt="Photo Editing">
      <h2>Photo Editing</h2>
      <button onclick="chatWhatsApp('Photo Editing')">Chat on WhatsApp</button>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <p>© <span id="year"></span> Almuhammady Futuristics Graphics. All rights reserved.</p>
  </footer>
</body>
</html>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: linear-gradient(to bottom, #0f172a, #000);
  color: white;
  text-align: center;
}

header {
  padding: 20px;
}

h1 {
  color: #22d3ee;
  font-size: 2rem;
}

p {
  color: #9ca3af;
}

#categories {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  padding: 20px;
}

.card {
  background: #1e293b;
  border-radius: 12px;
  padding: 10px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.5);
}

.card img {
  width: 100%;
  height: 150px;
  object-fit: cover;
  border-radius: 12px;
}

button {
  margin-top: 10px;
  padding: 10px 15px;
  border: none;
  border-radius: 8px;
  background: #06b6d4;
  color: white;
  cursor: pointer;
  font-weight: bold;
}

button:hover {
  background: #0891b2;
}

footer {
  margin-top: 40px;
  padding: 15px;
  border-top: 1px solid #334155;
  color: #9ca3af;
}
