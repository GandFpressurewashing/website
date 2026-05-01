<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>G & F Pressure Washing</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background-color: #f4f9ff;
    }

    header {
      background: white;
      text-align: center;
      padding: 15px;
      border-bottom: 3px solid #0b3d91;
    }

    header img {
      width: 100px;
    }

    nav {
      background: #145da0;
      text-align: center;
      padding: 10px;
    }

    nav a {
      color: white;
      margin: 10px;
      text-decoration: none;
      font-weight: bold;
    }

    .hero {
      background: url('https://images.unsplash.com/photo-1600585154340-be6161a56a0c') center/cover;
      color: white;
      text-align: center;
      padding: 80px 20px;
    }

    .btn {
      background: #ffd700;
      color: black;
      padding: 12px 20px;
      text-decoration: none;
      font-weight: bold;
      border-radius: 5px;
    }

    .container {
      padding: 30px 20px;
      max-width: 1000px;
      margin: auto;
    }

    h2 {
      color: #0b3d91;
    }

    .services {
      display: flex;
      gap: 20px;
      flex-wrap: wrap;
    }

    .box {
      background: white;
      padding: 15px;
      border-radius: 10px;
      flex: 1;
      box-shadow: 0 2px 5px rgba(0,0,0,0.2);
    }

    .about {
      background: white;
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.2);
    }

    /* BEFORE AFTER SLIDER */
    .ba-slider {
      position: relative;
      overflow: hidden;
      max-width: 500px;
      margin: 30px auto;
      border-radius: 10px;
    }

    .ba-slider img {
      width: 100%;
      display: block;
    }

    .resize {
      position: absolute;
      top: 0;
      left: 0;
      width: 50%;
      overflow: hidden;
    }

    .handle {
      position: absolute;
      top: 0;
      left: 50%;
      width: 4px;
      height: 100%;
      background: #ffd700;
      cursor: ew-resize;
    }

    .contact {
      text-align: center;
      background: white;
      padding: 20px;
      border-radius: 10px;
    }

    footer {
      background: #0b3d91;
      color: white;
      text-align: center;
      padding: 10px;
    }
  </style>
</head>

<body>

<header>
  <img src="logo.png">
  <h1>G & F Pressure Washing</h1>
  <p>Serving San Antonio, Texas</p>
</header>

<nav>
  <a href="#services">Services</a>
  <a href="#results">Results</a>
  <a href="#about">About</a>
  <a href="#contact">Contact</a>
</nav>

<section class="hero">
  <h1>Make Your Property Look Brand New</h1>
  <p>Driveways • Homes • Sidewalks • Patios</p>
  <br>
  <a href="#contact" class="btn">Get a Free Quote</a>
</section>

<div class="container" id="services">
  <h2>Our Services</h2>
  <div class="services">
    <div class="box">
      <h3>Driveway Cleaning</h3>
      <p>Remove dirt, stains, and buildup.</p>
    </div>
    <div class="box">
      <h3>House Washing</h3>
      <p>Safely clean your home's exterior.</p>
    </div>
    <div class="box">
      <h3>Patios & Sidewalks</h3>
      <p>Restore outdoor spaces to like-new condition.</p>
    </div>
  </div>
</div>

<div class="container" id="results">
  <h2>Before & After Results</h2>

  <div class="ba-slider">
    <img src="before1.jpg">
    <div class="resize">
      <img src="after1.jpg">
    </div>
    <span class="handle"></span>
  </div>

  <div class="ba-slider">
    <img src="before2.jpg">
    <div class="resize">
      <img src="after2.jpg">
    </div>
    <span class="handle"></span>
  </div>

</div>

<div class="container" id="about">
  <h2>About Us</h2>
  <div class="about">
    <p>
      We are Gregory Buchek and Fernando Rodriguez, two hardworking high school students based in San Antonio.
    </p>
    <p>
      We started G & F Pressure Washing to provide high-quality, affordable cleaning services while building real business experience.
    </p>
    <p>
      We take pride in our work, show up on time, and make sure every job is done right.
    </p>
  </div>
</div>

<div class="container" id="contact">
  <div class="contact">
    <h2>Contact Us</h2>
    <p>Call or text for a free quote</p>

    <a href="tel:2109311240" class="btn">📞 Call Now</a>
    <br><br>
    <a href="sms:2109311240" class="btn">💬 Text Us</a>

    <p><strong>Phone:</strong> 210-931-1240</p>
  </div>
</div>

<footer>
  <p>© 2026 G & F Pressure Washing</p>
</footer>

<script>
document.querySelectorAll('.ba-slider').forEach(slider => {
  let isDragging = false;
  const handle = slider.querySelector('.handle');
  const resize = slider.querySelector('.resize');

  handle.addEventListener('mousedown', () => isDragging = true);
  window.addEventListener('mouseup', () => isDragging = false);

  slider.addEventListener('mousemove', (e) => {
    if (!isDragging) return;
    let rect = slider.getBoundingClientRect();
    let x = e.clientX - rect.left;
    let percent = (x / rect.width) * 100;
    percent = Math.max(0, Math.min(100, percent));
    resize.style.width = percent + "%";
    handle.style.left = percent + "%";
  });

  slider.addEventListener('touchmove', (e) => {
    let rect = slider.getBoundingClientRect();
    let x = e.touches[0].clientX - rect.left;
    let percent = (x / rect.width) * 100;
    percent = Math.max(0, Math.min(100, percent));
    resize.style.width = percent + "%";
    handle.style.left = percent + "%";
  });
});
</script>

</body>
</html>