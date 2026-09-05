
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Yuvraj Singh</title>

  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:ital,wght@1,400;1,500;1,600&display=swap');

    * {
      box-sizing: border-box;
      font-family: 'Inter', sans-serif;
    }

    html,
    body {
      margin: 0;
      width: 100%;
      min-height: 100%;
    }

    body {
      background: #fff;
    }

    .font-playfair {
      font-family: 'Playfair Display', serif;
    }

    .page {
      min-height: 100vh;
      background: #fff;
      letter-spacing: -0.02em;
    }

    .hero {
      position: relative;
      width: 100%;
      height: 100vh;
      height: 100dvh;
      overflow: hidden;
      background: #000;
    }

    .base-image {
      position: absolute;
      inset: 0;
      z-index: 10;
      background-position: center;
      background-size: cover;
      background-repeat: no-repeat;
    }

    .reveal-layer {
      position: absolute;
      inset: 0;
      z-index: 30;
      pointer-events: none;
      background-position: center;
      background-size: cover;
      background-repeat: no-repeat;
      -webkit-mask-repeat: no-repeat;
      mask-repeat: no-repeat;
      -webkit-mask-size: 100% 100%;
      mask-size: 100% 100%;
    }

    .mask-canvas {
      position: absolute;
      inset: 0;
      pointer-events: none;
      display: none;
    }

    .hero-heading {
      position: absolute;
      top: 14%;
      left: 0;
      right: 0;
      z-index: 50;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 0 20px;
      text-align: center;
      pointer-events: none;
    }

    .hero-heading h1 {
      margin: 0;
      color: #fff;
      line-height: 0.95;
      font-weight: 400;
    }

    .heading-line-one,
    .heading-line-two {
      display: block;
      font-size: 3rem;
      font-weight: 400;
    }

    .heading-line-one {
      font-family: 'Playfair Display', serif;
      font-style: italic;
      letter-spacing: -0.05em;
    }

    .heading-line-two {
      margin-top: -0.25rem;
      letter-spacing: -0.08em;
    }

    .bottom-left {
      position: absolute;
      bottom: 56px;
      left: 40px;
      z-index: 50;
      max-width: 260px;
    }

    .bottom-left p,
    .bottom-right p {
      margin: 0;
      color: rgba(255, 255, 255, 0.8);
      line-height: 1.625;
    }

    .bottom-left p {
      font-size: 0.875rem;
    }

    .bottom-right {
      position: absolute;
      right: 20px;
      bottom: 40px;
      left: 20px;
      z-index: 50;
      display: flex;
      max-width: 100%;
      flex-direction: column;
      align-items: flex-start;
      gap: 16px;
    }

    .bottom-right p {
      font-size: 0.75rem;
    }

    .start-button {
      padding: 12px 28px;
      border: 0;
      border-radius: 9999px;
      background: #e8702a;
      color: #fff;
      font-size: 0.875rem;
      font-weight: 500;
      cursor: pointer;
      transition:
        background-color 0.2s ease,
        transform 0.2s ease,
        box-shadow 0.2s ease;
    }

    .start-button:hover {
      background: #d2611f;
      transform: scale(1.03);
      box-shadow: 0 10px 25px rgba(232, 112, 42, 0.3);
    }

    .start-button:active {
      transform: scale(0.95);
    }

    .nav {
      position: fixed;
      top: 0;
      right: 0;
      left: 0;
      z-index: 100;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 16px;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .logo svg {
      display: block;
      width: 26px;
      height: 26px;
      fill: #fff;
      flex: 0 0 auto;
    }

    .wordmark {
      color: #fff;
      font-family: 'Playfair Display', serif;
      font-size: 1.5rem;
      font-style: italic;
      line-height: 1;
    }

    .nav-pill {
      position: absolute;
      left: 50%;
      display: none;
      align-items: center;
      gap: 4px;
      padding: 8px;
      border: 1px solid rgba(255, 255, 255, 0.3);
      border-radius: 9999px;
      background: rgba(255, 255, 255, 0.2);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      transform: translateX(-50%);
    }

    .nav-pill button {
      padding: 6px 16px;
      border: 0;
      border-radius: 9999px;
      background: transparent;
      color: rgba(255, 255, 255, 0.8);
      font-size: 0.875rem;
      font-weight: 500;
      cursor: pointer;
      white-space: nowrap;
      transition:
        background-color 0.2s ease,
        color 0.2s ease;
    }

    .nav-pill button:hover {
      background: rgba(255, 255, 255, 0.2);
      color: #fff;
    }

    .nav-pill .active {
      background: #fff;
      color: #111827;
    }

    .signup {
      display: none;
      padding: 10px 24px;
      border: 0;
      border-radius: 9999px;
      background: #fff;
      color: #111827;
      font-size: 0.875rem;
      font-weight: 600;
      cursor: pointer;
      transition: background-color 0.2s ease;
    }

    .signup:hover {
      background: #f3f4f6;
    }

    .mobile-menu {
      display: flex;
      width: 40px;
      height: 40px;
      align-items: center;
      justify-content: center;
      padding: 0;
      border: 1px solid rgba(255, 255, 255, 0.3);
      border-radius: 9999px;
      background: rgba(255, 255, 255, 0.15);
      color: #fff;
      cursor: pointer;
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
    }

    .mobile-menu svg {
      width: 21px;
      height: 21px;
    }

    @keyframes heroReveal {
      0% {
        opacity: 0;
        transform: translateY(28px);
        filter: blur(12px);
      }

      100% {
        opacity: 1;
        transform: translateY(0);
        filter: blur(0);
      }
    }

    @keyframes heroFadeUp {
      0% {
        opacity: 0;
        transform: translateY(20px);
      }

      100% {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes heroZoom {
      0% {
        transform: scale(1.12);
      }

      100% {
        transform: scale(1);
      }
    }

    .hero-anim {
      opacity: 0;
      animation-fill-mode: forwards;
      animation-timing-function: cubic-bezier(0.16, 1, 0.3, 1);
    }

    .hero-reveal {
      animation-name: heroReveal;
      animation-duration: 1.1s;
    }

    .hero-fade {
      animation-name: heroFadeUp;
      animation-duration: 1s;
    }

    .hero-zoom {
      animation: heroZoom 1.8s cubic-bezier(0.16, 1, 0.3, 1) forwards;
    }

    @media (min-width: 640px) {
      .nav {
        padding: 20px;
      }

      .heading-line-one,
      .heading-line-two {
        font-size: 4.5rem;
      }

      .bottom-left {
        display: block;
        left: 40px;
        bottom: 56px;
      }

      .bottom-right {
        right: 40px;
        bottom: 96px;
        left: auto;
        max-width: 260px;
        gap: 20px;
      }

      .bottom-right p {
        font-size: 0.875rem;
      }
    }

    @media (min-width: 768px) {
      .heading-line-one,
      .heading-line-two {
        font-size: 6rem;
      }

      .nav-pill {
        display: flex;
      }

      .signup {
        display: block;
      }

      .mobile-menu {
        display: none;
      }

      .bottom-left {
        left: 56px;
      }

      .bottom-right {
        right: 56px;
      }
    }

    @media (max-width: 639px) {
      .bottom-left {
        display: none;
      }
    }

    @media (prefers-reduced-motion: reduce) {
      .hero-anim,
      .hero-zoom {
        animation: none;
        opacity: 1;
      }
    }
  </style>
</head>

<body>
  <div class="page">
    <nav class="nav">
      <div class="logo">
        <svg
          viewBox="0 0 256 256"
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
        >
          <path d="M 256 256 L 128 256 L 0 128 L 128 128 Z M 256 128 L 128 128 L 0 0 L 128 0 Z"></path>
        </svg>

        <span class="wordmark">Yuvraj Singh</span>
      </div>

      <div class="nav-pill">
        <button class="active">Course</button>
        <button>Field Guides</button>
        <button>Geology</button>
        <button>Plans</button>
        <button>Live Tour</button>
      </div>

      <button class="signup">Sign Up</button>

      <button class="mobile-menu" aria-label="Open navigation">
        <svg
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="1.8"
          stroke-linecap="round"
          stroke-linejoin="round"
          aria-hidden="true"
        >
          <path d="M4 6h16"></path>
          <path d="M4 12h16"></path>
          <path d="M4 18h16"></path>
        </svg>
      </button>
    </nav>

    <section class="hero">
      <div
        id="baseImage"
        class="base-image hero-zoom"
      ></div>

      <canvas id="maskCanvas" class="mask-canvas"></canvas>

      <div
        id="revealLayer"
        class="reveal-layer"
      ></div>

      <div class="hero-heading">
        <h1>
          <span
            class="heading-line-one hero-anim hero-reveal"
            style="animation-delay: 0.25s;"
          >
            Layers hold
          </span>

          <span
            class="heading-line-two hero-anim hero-reveal"
            style="animation-delay: 0.42s;"
          >
            tales of time
          </span>
        </h1>
      </div>

      <div
        class="bottom-left hero-anim hero-fade"
        style="animation-delay: 0.7s;"
      >
        <p>
          Every layer of sediment records a chapter of our planet, from ancient seabeds to drifting ash, layered across millions of years beneath us.
        </p>
      </div>

      <div
        class="bottom-right hero-anim hero-fade"
        style="animation-delay: 0.85s;"
      >
        <p>
          Our interactive maps let you peel back the crust to trace how stones, fossils, and deep time combine to shape the ground beneath your feet.
        </p>

        <button class="start-button">
          Start Digging
        </button>
      </div>
    </section>
  </div>

  <script>
    const BG_IMAGE_1 =
      'https://images.higgs.ai/?default=1&output=webp&url=https%3A%2F%2Fd8j0ntlcm91z4.cloudfront.net%2Fuser_38xzZboKViGWJOttwIXH07lWA1P%2Fhf_20260609_195923_b0ba8ace-1d1d-4f2c-9a28-1ab84b330680.png&w=1280&q=85';

    const BG_IMAGE_2 =
      'https://images.higgs.ai/?default=1&output=webp&url=https%3A%2F%2Fd8j0ntlcm91z4.cloudfront.net%2Fuser_38xzZboKViGWJOttwIXH07lWA1P%2Fhf_20260609_201152_bba90a12-bf12-459f-91f0-51f237dbaf3b.png&w=1280&q=85';

    const SPOTLIGHT_R = 260;

    const baseImage = document.getElementById('baseImage');
    const revealLayer = document.getElementById('revealLayer');
    const canvas = document.getElementById('maskCanvas');
    const ctx = canvas.getContext('2d');

    baseImage.style.backgroundImage = `url("${BG_IMAGE_1}")`;
    revealLayer.style.backgroundImage = `url("${BG_IMAGE_2}")`;

    const mouse = {
      x: -999,
      y: -999
    };

    const smooth = {
      x: -999,
      y: -999
    };

    let cursorPos = {
      x: -999,
      y: -999
    };

    let rafRef = null;

    function resizeCanvas() {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    }

    function updateRevealMask() {
      if (!ctx) return;

      ctx.clearRect(0, 0, canvas.width, canvas.height);

      const gradient = ctx.createRadialGradient(
        cursorPos.x,
        cursorPos.y,
        0,
        cursorPos.x,
        cursorPos.y,
        SPOTLIGHT_R
      );

      gradient.addColorStop(0, 'rgba(255,255,255,1)');
      gradient.addColorStop(0.4, 'rgba(255,255,255,1)');
      gradient.addColorStop(0.6, 'rgba(255,255,255,0.75)');
      gradient.addColorStop(0.75, 'rgba(255,255,255,0.4)');
      gradient.addColorStop(0.88, 'rgba(255,255,255,0.12)');
      gradient.addColorStop(1, 'rgba(255,255,255,0)');

      ctx.fillStyle = gradient;
      ctx.beginPath();
      ctx.arc(
        cursorPos.x,
        cursorPos.y,
        SPOTLIGHT_R,
        0,
        Math.PI * 2
      );
      ctx.fill();

      const mask = canvas.toDataURL();

      revealLayer.style.maskImage = `url("${mask}")`;
      revealLayer.style.webkitMaskImage = `url("${mask}")`;
      revealLayer.style.maskSize = '100% 100%';
      revealLayer.style.webkitMaskSize = '100% 100%';
      revealLayer.style.maskRepeat = 'no-repeat';
      revealLayer.style.webkitMaskRepeat = 'no-repeat';
    }

    function animate() {
      smooth.x += (mouse.x - smooth.x) * 0.1;
      smooth.y += (mouse.y - smooth.y) * 0.1;

      cursorPos.x = smooth.x;
      cursorPos.y = smooth.y;

      updateRevealMask();

      rafRef = requestAnimationFrame(animate);
    }

    function handleMouseMove(event) {
      mouse.x = event.clientX;
      mouse.y = event.clientY;
    }

    resizeCanvas();

    window.addEventListener('resize', resizeCanvas);
    window.addEventListener('mousemove', handleMouseMove);

    rafRef = requestAnimationFrame(animate);

    window.addEventListener('beforeunload', () => {
      window.removeEventListener('resize', resizeCanvas);
      window.removeEventListener('mousemove', handleMouseMove);

      if (rafRef !== null) {
        cancelAnimationFrame(rafRef);
      }
    });
  </script>
</body>
</html>
