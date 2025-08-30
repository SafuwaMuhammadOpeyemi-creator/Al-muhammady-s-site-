<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Al~muhammady Futuristics Designs</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(to bottom, #0a0a2a, #000);
      color: white;
    }
    header {
      text-align: center;
      padding: 2rem;
      background: #001f3f;
    }
    header h1 {
      color: #1E90FF;
      font-size: 2rem;
    }
    header p {
      color: #ccc;
    }
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1rem;
      padding: 2rem;
    }
    .card {
      background: #111;
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 0 10px rgba(30, 144, 255, 0.5);
      text-align: center;
      cursor: pointer;
    }
    .card img {
      width: 100%;
      height: 180px;
      object-fit: cover;
    }
    .card h2 {
      margin: 0.5rem 0;
    }
    button {
      background: #1E90FF;
      border: none;
      padding: 0.5rem 1rem;
      color: white;
      border-radius: 8px;
      cursor: pointer;
      margin: 0.5rem;
    }
    button:hover {
      background: #187bcd;
    }
    footer {
      text-align: center;
      padding: 1rem;
      border-top: 1px solid #333;
      margin-top: 2rem;
      color: #777;
    }

    /* Lightbox */
    .lightbox {
      display: none;
      position: fixed;
      z-index: 1000;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.9);
      align-items: center;
      justify-content: center;
      flex-direction: column;
    }
    .lightbox img {
      max-width: 90%;
      max-height: 70%;
    }
    .lightbox .close {
      position: absolute;
      top: 20px;
      right: 40px;
      font-size: 30px;
      cursor: pointer;
    }
    .lightbox .arrow {
      position: absolute;
      top: 50%;
      font-size: 40px;
      cursor: pointer;
      user-select: none;
    }
    .lightbox .arrow.left {
      left: 20px;
    }
    .lightbox .arrow.right {
      right: 20px;
    }
  </style>
</head>
<body>
  <header>
    <h1>Al~muhammady Futuristics Designs</h1>
    <p>Everything about GRAPHICS – World-class futuristic creativity</p>
  </header>

  <section class="grid">
    <div class="card" onclick="openLightbox(0)">
      <img src="logos-sample.jpg" alt="Logos"/>
      <h2>Logos</h2>
      <button onclick="event.stopPropagation(); chatWhatsApp('Logos')">Chat on WhatsApp</button>
    </div>
    <div class="card" onclick="openLightbox(1)">
      <img src="flyers-sample.jpg" alt="Flyers"/>
      <h2>Flyers</h2>
      <button onclick="event.stopPropagation(); chatWhatsApp('Flyers')">Chat on WhatsApp</button>
    </div>
    <div class="card" onclick="openLightbox(2)">
      <img src="posters-sample.jpg" alt="Posters"/>
      <h2>Posters</h2>
      <button onclick="event.stopPropagation(); chatWhatsApp('Posters')">Chat on WhatsApp</button>
    </div>
    <div class="card" onclick="openLightbox(3)">
      <img src="social-sample.jpg" alt="Social Media"/>
      <h2>Social Media Graphics</h2>
      <button onclick="event.stopPropagation(); chatWhatsApp('Social Media Graphics')">Chat on WhatsApp</button>
    </div>
    <div class="card" onclick="openLightbox(4)">
      <img src="photo-sample.jpg" alt="Photo Editing"/>
      <h2>Photo Editing</h2>
      <button onclick="event.stopPropagation(); chatWhatsApp('Photo Editing')">Chat on WhatsApp</button>
    </div>
  </section>

  <!-- Lightbox -->
  <div id="lightbox" class="lightbox">
    <span class="close" onclick="closeLightbox()">&times;</span>
    <span class="arrow left" onclick="prevImage()">&#10094;</span>
    <img id="lightbox-img" src="" alt="Preview"/>
    <span class="arrow right" onclick="nextImage()">&#10095;</span>
  </div>

  <footer>
    © <span id="year"></span> Almuhammadyfuturisticsgraphics. All rights reserved.
  </footer>

  <script>
    const whatsappNumber = "2348149369370"; // your real WhatsApp number
    function chatWhatsApp(service) {
      const url = `https://wa.me/${whatsappNumber}?text=Hello, I am interested in your ${service}`;
      window.open(url, "_blank");
    }

    document.getElementById("year").textContent = new Date().getFullYear();

    // Lightbox logic
    const images = [
      "logos-sample.jpg",
      "flyers-sample.jpg",
      "posters-sample.jpg",
      "social-sample.jpg",
      "photo-sample.jpg"
    ];
    let currentIndex = 0;

    function openLightbox(index) {
      currentIndex = index;
      document.getElementById("lightbox").style.display = "flex";
      document.getElementById("lightbox-img").src = images[currentIndex];
    }
    function closeLightbox() {
      document.getElementById("lightbox").style.display = "none";
    }
    function prevImage() {
      currentIndex = (currentIndex - 1 + images.length) % images.length;
      document.getElementById("lightbox-img").src = images[currentIndex];
    }
    function nextImage() {
      currentIndex = (currentIndex + 1) % images.length;
      document.getElementById("lightbox-img").src = images[currentIndex];
    }

    // Swipe support for mobile
    let startX = 0;
    const lightbox = document.getElementById("lightbox");
    lightbox.addEventListener("touchstart", (e) => {
      startX = e.touches[0].clientX;
    });
    lightbox.addEventListener("touchend", (e) => {
      const endX = e.changedTouches[0].clientX;
      if (startX - endX > 50) nextImage();
      if (endX - startX > 50) prevImage();
    });
  </script>
</body>
</html>
