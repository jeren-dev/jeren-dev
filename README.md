<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
  <title>Jeren J | Flagship Portfolio — Android & Full Stack Dev</title>
  <!-- Google Fonts & Font Awesome -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background-color: #0a0c10;
      color: #ededee;
      overflow-x: hidden;
      cursor: default;
      line-height: 1.5;
    }

    /* ---- Animated mouse-following gradient background ---- */
    .mouse-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -2;
      background: radial-gradient(circle at 20% 30%, #0b1120, #03050a);
      transition: background 0.1s ease;
    }

    .mouse-glow {
      position: fixed;
      width: 600px;
      height: 600px;
      background: radial-gradient(circle, rgba(99, 102, 241, 0.25) 0%, rgba(139, 92, 246, 0) 70%);
      border-radius: 50%;
      pointer-events: none;
      transform: translate(-50%, -50%);
      transition: transform 0.08s linear;
      z-index: -1;
      filter: blur(60px);
      opacity: 0.7;
    }

    /* custom scroll */
    ::-webkit-scrollbar {
      width: 6px;
    }
    ::-webkit-scrollbar-track {
      background: #0f1117;
    }
    ::-webkit-scrollbar-thumb {
      background: #4f46e5;
      border-radius: 12px;
    }

    /* container */
    .container {
      max-width: 1300px;
      margin: 0 auto;
      padding: 2rem 2rem 4rem;
      position: relative;
      z-index: 2;
    }

    /* glassmorphic card style */
    .glass-card {
      background: rgba(18, 22, 35, 0.65);
      backdrop-filter: blur(12px);
      border-radius: 2rem;
      border: 1px solid rgba(79, 70, 229, 0.3);
      box-shadow: 0 20px 35px -12px rgba(0,0,0,0.4);
      transition: all 0.3s ease;
    }

    /* header section big flex flagship */
    .hero {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 4rem;
    }

    .hero-left h1 {
      font-size: 4.2rem;
      font-weight: 800;
      background: linear-gradient(135deg, #FFFFFF, #a5b4fc, #818cf8);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      letter-spacing: -0.02em;
    }
    .badge {
      background: #4f46e5;
      padding: 0.3rem 0.9rem;
      border-radius: 40px;
      font-size: 0.8rem;
      font-weight: 600;
      display: inline-block;
      margin-top: 1rem;
    }
    .hero-stats {
      display: flex;
      gap: 2rem;
      margin: 1.5rem 0;
    }
    .stat {
      text-align: center;
    }
    .stat-number {
      font-size: 1.8rem;
      font-weight: 800;
      color: #c084fc;
    }

    .hero-right {
      background: rgba(0,0,0,0.4);
      border-radius: 2rem;
      padding: 0.8rem 1.8rem;
      backdrop-filter: blur(4px);
      border: 1px solid rgba(255,255,255,0.1);
    }

    /* grid layout */
    .grid-2col {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 2rem;
      margin-bottom: 3rem;
    }

    .section-title {
      font-size: 2rem;
      font-weight: 700;
      margin-bottom: 1.5rem;
      display: flex;
      align-items: center;
      gap: 0.8rem;
      border-left: 5px solid #4f46e5;
      padding-left: 1.2rem;
    }

    .tech-stack {
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem;
      margin: 1rem 0;
    }
    .tech-item {
      background: rgba(79, 70, 229, 0.2);
      border: 1px solid #4f46e570;
      padding: 0.5rem 1rem;
      border-radius: 40px;
      font-size: 0.85rem;
      font-weight: 500;
      transition: 0.2s;
    }
    .tech-item i {
      margin-right: 6px;
      color: #a78bfa;
    }

    .featured-project {
      background: linear-gradient(145deg, #13182b, #0b0f1c);
      border-radius: 2rem;
      padding: 1.6rem;
      transition: transform 0.25s ease, box-shadow 0.3s;
    }
    .featured-project:hover {
      transform: translateY(-6px);
      box-shadow: 0 25px 35px -12px rgba(79,70,229,0.3);
    }

    .project-title {
      font-size: 1.6rem;
      font-weight: 700;
    }
    .btn {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: #4f46e5;
      padding: 0.7rem 1.4rem;
      border-radius: 40px;
      font-weight: 600;
      text-decoration: none;
      color: white;
      transition: 0.2s;
      border: none;
      cursor: pointer;
    }
    .btn-outline {
      background: transparent;
      border: 1px solid #818cf8;
    }

    .social-links {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      margin-top: 1rem;
    }
    .social-icon {
      background: rgba(255,255,255,0.05);
      backdrop-filter: blur(4px);
      padding: 0.7rem 1.2rem;
      border-radius: 50px;
      transition: 0.2s;
      color: #ddd;
      text-decoration: none;
      font-size: 0.9rem;
      font-weight: 500;
    }
    .social-icon i {
      margin-right: 8px;
      font-size: 1.1rem;
    }
    .social-icon:hover {
      background: #4f46e5;
      color: white;
      transform: scale(1.05);
    }

    /* footer */
    .footer {
      text-align: center;
      margin-top: 4rem;
      padding-top: 2rem;
      border-top: 1px solid rgba(255,255,255,0.1);
      font-size: 0.85rem;
    }

    /* floating parallax images (world-class images) */
    .floating-img {
      position: absolute;
      pointer-events: none;
      z-index: 1;
      opacity: 0.2;
      transition: transform 0.4s ease;
    }
    .img-1 {
      top: 15%;
      left: -3%;
      width: 280px;
      filter: blur(2px);
    }
    .img-2 {
      bottom: 10%;
      right: -2%;
      width: 320px;
      transform: rotate(5deg);
    }
    .img-3 {
      top: 40%;
      right: 8%;
      width: 150px;
      opacity: 0.25;
    }
    @media (max-width: 780px) {
      .hero-left h1 { font-size: 2.8rem; }
      .container { padding: 1rem; }
      .floating-img { display: none; }
    }

    /* typing effect for about */
    .dynamic-text {
      font-weight: 600;
      color: #a78bfa;
    }

    /* glow animation for flagship */
    @keyframes subtle-pulse {
      0% { border-color: rgba(79,70,229,0.3); box-shadow: 0 0 0 0 rgba(79,70,229,0.2);}
      100% { border-color: rgba(139,92,246,0.6); box-shadow: 0 0 0 8px rgba(79,70,229,0);}
    }
    .hero-right, .featured-project {
      animation: subtle-pulse 2.5s infinite;
    }
  </style>
</head>
<body>

<div class="mouse-bg" id="mouseBg"></div>
<div class="mouse-glow" id="mouseGlow"></div>

<!-- abstract decorative images -->
<img class="floating-img img-1" src="https://cdn-icons-png.flaticon.com/512/6062/6062646.png" alt="android icon" />
<img class="floating-img img-2" src="https://cdn-icons-png.flaticon.com/512/1055/1055687.png" alt="code swirl" />
<img class="floating-img img-3" src="https://cdn-icons-png.flaticon.com/512/732/732212.png" alt="html css" />

<div class="container">
  <!-- HERO Section - Big Flex / Flagship Level -->
  <div class="hero glass-card" style="padding: 2rem 2.5rem;">
    <div class="hero-left">
      <div class="badge"><i class="fas fa-code"></i> FLAGSHIP BUILDER</div>
      <h1>👋 Hi, I'm Jeren J<br><span style="font-size: 2rem;">Android & Full Stack Architect</span></h1>
      <div class="hero-stats">
        <div class="stat"><div class="stat-number">8+</div><div>Projects Shipped</div></div>
        <div class="stat"><div class="stat-number">100%</div><div>Real-World Impact</div></div>
        <div class="stat"><div class="stat-number">⚡</div><div>Kotlin • Compose</div></div>
      </div>
      <p style="max-width: 500px; margin-bottom: 1rem;">📍 Trichy, Tamil Nadu, India — Building apps that solve everyday problems with world-class UI/UX & modern stacks.</p>
      <div class="social-links" style="margin-top: 0.5rem;">
        <a href="https://github.com/jeren-dev" target="_blank" class="social-icon"><i class="fab fa-github"></i> GitHub</a>
        <a href="https://linkedin.com/in/jeren-j-656a6031b" target="_blank" class="social-icon"><i class="fab fa-linkedin"></i> LinkedIn</a>
        <a href="mailto:jeren3439@gmail.com" class="social-icon"><i class="fas fa-envelope"></i> Email</a>
        <a href="https://instagram.com/mr____jerry__offl" target="_blank" class="social-icon"><i class="fab fa-instagram"></i> Instagram</a>
      </div>
    </div>
    <div class="hero-right">
      <i class="fas fa-quote-left" style="color:#818cf8; opacity:0.7;"></i>
      <p style="font-style: italic; max-width: 280px;">"Always learning. Always building. Flagship mindset, pixel-perfect execution."</p>
      <i class="fas fa-rocket" style="margin-top: 12px; display: inline-block;"></i> <span>Full Stack • VoiceBudget • Jetpack</span>
    </div>
  </div>

  <!-- 2 col: About me + Currently -->
  <div class="grid-2col">
    <div class="glass-card" style="padding: 1.8rem;">
      <div class="section-title" style="border-left-color:#a855f7;"><i class="fas fa-user-astronaut"></i> 🚀 About Me</div>
      <p>I am a passionate developer focused on building practical mobile and web applications with clean UI, strong functionality, and real-world impact. I specialize in <strong>Android development using Kotlin and Jetpack Compose</strong>, creating fast user-friendly apps.</p>
      <div style="margin: 1rem 0;"><i class="fas fa-map-marker-alt" style="color:#c084fc;"></i> Based in Trichy, India — open for freelance & collabs</div>
      <div class="tech-stack" style="margin-top: 1rem;">
        <span class="tech-item"><i class="fab fa-android"></i> Kotlin</span>
        <span class="tech-item"><i class="fas fa-mobile-alt"></i> Jetpack Compose</span>
        <span class="tech-item"><i class="fas fa-database"></i> SQLite</span>
      </div>
    </div>

    <div class="glass-card" style="padding: 1.8rem;">
      <div class="section-title" style="border-left-color:#f97316;"><i class="fas fa-bolt"></i> Currently I am:</div>
      <ul style="list-style: none; margin-left: 0;">
        <li style="margin-bottom: 12px;">🔨 <strong>Building Android apps</strong> with real-world use cases</li>
        <li style="margin-bottom: 12px;">🌱 <strong>Improving Full Stack</strong> development skills (PHP • MySQL)</li>
        <li style="margin-bottom: 12px;">💼 <strong>Exploring freelance opportunities</strong> and project-based work</li>
      </ul>
      <div class="badge" style="background: #0f172a; border:1px solid #4f46e5;"><i class="fas fa-brain"></i> Goal: Professional Software Engineer → Launch my own tech</div>
    </div>
  </div>

  <!-- Tech Stack Full Showcase -->
  <div class="glass-card" style="padding: 1.8rem; margin-bottom: 2rem;">
    <div class="section-title"><i class="fas fa-cogs"></i> 🛠️ Tech Stack — The Ultimate Arsenal</div>
    <div style="display: flex; flex-wrap: wrap; gap: 2rem; justify-content: space-between;">
      <div><h3><i class="fab fa-android"></i> 📱 Android</h3>
        <div class="tech-stack"><span class="tech-item">Kotlin</span><span class="tech-item">Jetpack Compose</span><span class="tech-item">XML UI</span><span class="tech-item">SQLite</span><span class="tech-item">Room</span></div>
      </div>
      <div><h3><i class="fas fa-globe"></i> 🌐 Web Dev</h3>
        <div class="tech-stack"><span class="tech-item">HTML5/CSS3</span><span class="tech-item">JavaScript ES6</span><span class="tech-item">PHP</span><span class="tech-item">MySQL</span><span class="tech-item">Responsive</span></div>
      </div>
      <div><h3><i class="fas fa-tools"></i> ⚙️ Tools</h3>
        <div class="tech-stack"><span class="tech-item">Git/GitHub</span><span class="tech-item">Android Studio</span><span class="tech-item">VS Code</span><span class="tech-item">Figma</span></div>
      </div>
    </div>
  </div>

  <!-- Featured project flagship big card -->
  <div style="margin-bottom: 3rem;">
    <div class="section-title"><i class="fas fa-star-of-life"></i> 📌 FLAGSHIP PROJECT</div>
    <div class="featured-project">
      <div style="display: flex; flex-wrap: wrap; justify-content: space-between; align-items: center;">
        <div>
          <span class="badge" style="background:#7c3aed;">🔥 Voice-First Innovation</span>
          <div class="project-title" style="margin-top: 0.5rem;">💰 VoiceBudget – Smart Expense Tracker</div>
          <p style="margin: 1rem 0; max-width: 600px;">Modern voice-enabled Android app to track income & expenses efficiently. Clean UI + SQLite persistence, and revolutionary voice-based entry. Smart budget tracking system to take control of your finances.</p>
          <div class="tech-stack">
            <span class="tech-item">Kotlin</span>
            <span class="tech-item">SQLite</span>
            <span class="tech-item">Voice Input API</span>
            <span class="tech-item">Jetpack Compose</span>
          </div>
          <a href="https://github.com/jeren-dev/VoiceBudget" target="_blank" class="btn" style="margin-top: 1.2rem;"><i class="fab fa-github"></i> View on GitHub →</a>
        </div>
        <div style="font-size: 4rem; opacity: 0.7;"><i class="fas fa-microphone-alt"></i> <i class="fas fa-chart-line"></i></div>
      </div>
    </div>
  </div>

  <!-- What I Do + Goals combined with images alignment world class -->
  <div class="grid-2col">
    <div class="glass-card" style="padding: 1.8rem;">
      <div class="section-title"><i class="fas fa-laptop-code"></i> 🎯 What I Do</div>
      <div style="display: grid; gap: 1rem;">
        <div><i class="fas fa-check-circle" style="color:#4f46e5;"></i> Android App Development (Kotlin/Compose)</div>
        <div><i class="fas fa-check-circle" style="color:#4f46e5;"></i> Full Stack Web Development</div>
        <div><i class="fas fa-check-circle" style="color:#4f46e5;"></i> Freelance App Projects & UI/UX Design</div>
        <div><i class="fas fa-check-circle" style="color:#4f46e5;"></i> Problem Solving & System Architecture</div>
      </div>
      <div style="margin-top: 1.5rem; background: rgba(0,0,0,0.3); border-radius: 1rem; padding: 1rem;">
        <i class="fas fa-chart-simple"></i> <strong>🌱 Long-term vision:</strong> become professional software engineer, build impactful digital products, launch own tech applications, and dominate the freelance ecosystem.
      </div>
    </div>
    <div class="glass-card" style="padding: 1.8rem; text-align: center;">
      <i class="fas fa-image" style="font-size: 2.5rem; color:#a5b4fc;"></i>
      <h3 style="margin: 1rem 0;">World-Class Design Philosophy</h3>
      <img src="https://cdn-icons-png.flaticon.com/512/2933/2933245.png" width="80" alt="design" style="opacity: 0.8;">
      <p style="margin-top: 1rem;">UI/UX that blends modern glassmorphism, micro-interactions, and adaptive layouts — making every interaction fluid.</p>
      <div class="tech-stack" style="justify-content: center;">
        <span class="tech-item">Figma expert</span>
        <span class="tech-item">Motion Layout</span>
        <span class="tech-item">Material You</span>
      </div>
    </div>
  </div>

  <!-- Connect & socials + footer big flex last -->
  <div class="glass-card" style="padding: 1.8rem; text-align: center; margin-bottom: 1rem;">
    <div class="section-title" style="justify-content: center; border-left: none;"><i class="fas fa-hand-peace"></i> 📫 Connect With Me — Let's Build The Future</div>
    <div class="social-links" style="justify-content: center; gap: 1.4rem;">
      <a href="mailto:jeren3439@gmail.com" class="social-icon"><i class="fas fa-envelope"></i> jeren3439@gmail.com</a>
      <a href="https://instagram.com/mr____jerry__offl" class="social-icon"><i class="fab fa-instagram"></i> Instagram</a>
      <a href="https://linkedin.com/in/jeren-j-656a6031b" class="social-icon"><i class="fab fa-linkedin"></i> LinkedIn</a>
      <a href="https://github.com/jeren-dev" class="social-icon"><i class="fab fa-github"></i> GitHub/jeren-dev</a>
    </div>
    <div style="margin-top: 2rem; font-size: 0.9rem;">
      <i class="fas fa-map-pin"></i> Trichy, Tamil Nadu, India | Open for freelance & collab
    </div>
  </div>

  <div class="footer">
    <p>⭐ Always learning. Always building. <strong>Flagship developer — Jeren J</strong> | Android & Full Stack Craftsmanship</p>
    <p style="margin-top: 8px;"><i class="fas fa-crown"></i> World-class UI/UX • Mouse-following ambient glow • Dynamic portfolio flagship edition</p>
  </div>
</div>

<script>
  // Mouse moving background glow effect (world class interactive)
  const mouseGlow = document.getElementById('mouseGlow');
  const mouseBg = document.getElementById('mouseBg');

  document.addEventListener('mousemove', (e) => {
    // smooth glow following cursor
    const x = e.clientX;
    const y = e.clientY;
    if (mouseGlow) {
      mouseGlow.style.transform = `translate(${x}px, ${y}px)`;
    }
    // dynamic radial background gradient shift based on mouse position for extra wow
    const percentX = (x / window.innerWidth) * 100;
    const percentY = (y / window.innerHeight) * 100;
    if (mouseBg) {
      mouseBg.style.background = `radial-gradient(circle at ${percentX}% ${percentY}%, #0f172f, #02040c)`;
    }
  });

  // small interactive animation on tech items and cards (extra micro)
  const techItems = document.querySelectorAll('.tech-item');
  techItems.forEach(item => {
    item.addEventListener('mouseenter', () => {
      item.style.transform = 'translateY(-3px)';
      item.style.backgroundColor = '#4f46e5';
      item.style.transition = '0.2s';
    });
    item.addEventListener('mouseleave', () => {
      item.style.transform = 'translateY(0px)';
      item.style.backgroundColor = 'rgba(79, 70, 229, 0.2)';
    });
  });

  // dynamic year in footer
  const yearSpan = document.createElement('span');
  // simple cursor parallax floating images on mouse move (extra polish)
  const floatingImgs = document.querySelectorAll('.floating-img');
  document.addEventListener('mousemove', (e) => {
    const mouseX = e.clientX / window.innerWidth;
    const mouseY = e.clientY / window.innerHeight;
    floatingImgs.forEach((img, idx) => {
      const speed = 12 + idx * 5;
      const moveX = (mouseX - 0.5) * speed;
      const moveY = (mouseY - 0.5) * speed;
      img.style.transform = `translate(${moveX}px, ${moveY}px) rotate(${idx * 2}deg)`;
    });
  });
</script>
</body>
</html>
