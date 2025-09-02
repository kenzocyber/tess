# tess
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Kenzo | Ethical Hacker</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(180deg, #0c0c1d, #0a0a14, #000);
      color: #00fff7;
      font-family: 'Courier New', monospace;
    }

    .container {
      max-width: 420px;
      margin: auto;
      padding: 1rem;
      position: relative;
      z-index: 10;
    }

    h1, h2, h3 {
      font-weight: bold;
      text-transform: uppercase;
      letter-spacing: 2px;
    }

    .card {
      border: 1px solid #00fff7;
      border-radius: 0.5rem;
      padding: 1rem;
      background-color: rgba(17, 17, 34, 0.8);
      transition: transform 0.3s, box-shadow 0.3s;
    }
    .card:hover {
      transform: scale(1.03);
      box-shadow: 0 0 15px #00fff7;
    }

    /* MATRIX RAIN */
    canvas#matrixRain {
      position: fixed;
      top: 0;
      left: 0;
      z-index: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      opacity: 0.25; /* tipis biar elegan */
    }
  </style>
</head>
<body>
  <canvas id="matrixRain"></canvas>

  <div class="container">
    <header class="mb-4 text-center">
      <h1 class="text-xl">Kenzo — Ethical Hacker</h1>
      <p class="text-sm text-cyan-400">Security Researcher & Pentester</p>
    </header>

    <section class="card mb-4">
      <h2 class="text-base mb-2">About Me</h2>
      <p class="text-sm mb-2">Saya Kenzo, fokus dalam keamanan siber & ethical hacking. Tujuan saya adalah mengamankan sistem & berbagi pengetahuan.</p>
      <p class="text-xs text-cyan-300"><b>Email:</b> pykcyber@gmail.com</p>
      <p class="text-xs text-cyan-300"><b>WhatsApp:</b> <a href="https://wa.me/6283143490913" target="_blank" class="underline">+62 831-4349-0913</a></p>
    </section>

    <section class="mb-4">
      <h2 class="text-base mb-2">Skills</h2>
      <div class="space-y-2">
        <div class="card">Web App Pentesting ⭐⭐⭐⭐⭐</div>
        <div class="card">API Security ⭐⭐⭐⭐☆</div>
        <div class="card">Network Hardening ⭐⭐⭐⭐☆</div>
        <div class="card">Reverse Engineering ⭐⭐⭐☆☆</div>
        <div class="card">OSINT & Threat Intel ⭐⭐⭐⭐⭐</div>
      </div>
    </section>

    <section class="mb-4">
      <h2 class="text-base mb-2">Projects</h2>
      <div class="space-y-2">
        <div class="card">Enterprise Audit ⭐⭐⭐⭐⭐</div>
        <div class="card">Cloud Infra Review ⭐⭐⭐⭐☆</div>
        <div class="card">Bug Bounty Findings ⭐⭐⭐⭐⭐</div>
        <div class="card">API Security Hardening ⭐⭐⭐⭐☆</div>
      </div>
    </section>

    <section class="card mb-4">
      <h2 class="text-base mb-2">Contact</h2>
      <a href="mailto:pykcyber@gmail.com" class="block text-sm underline">pykcyber@gmail.com</a>
      <a href="https://wa.me/6283143490913" class="block text-sm underline mt-1">+62 831-4349-0913</a>
    </section>

    <footer class="text-center text-[10px] text-cyan-500">
      <p>Website ini dibuat oleh <b>Kenzo</b></p>
      <p>© 2025 Kenzo — Semua hak cipta dilindungi.</p>
    </footer>
  </div>

  <script>
    // MATRIX RAIN EFFECT
    const canvas = document.getElementById("matrixRain");
    const ctx = canvas.getContext("2d");

    canvas.height = window.innerHeight;
    canvas.width = window.innerWidth;

    const chars = "01";
    const fontSize = 14;
    const columns = canvas.width / fontSize;
    const drops = [];

    for (let x = 0; x < columns; x++) {
      drops[x] = 1;
    }

    function draw() {
      ctx.fillStyle = "rgba(0, 0, 0, 0.05)";
      ctx.fillRect(0, 0, canvas.width, canvas.height);

      ctx.fillStyle = "#00ff00";
      ctx.font = fontSize + "px monospace";

      for (let i = 0; i < drops.length; i++) {
        const text = chars.charAt(Math.floor(Math.random() * chars.length));
        ctx.fillText(text, i * fontSize, drops[i] * fontSize);

        if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
          drops[i] = 0;
        }
        drops[i]++;
      }
    }

    setInterval(draw, 40);
  </script>
</body>
</html>
