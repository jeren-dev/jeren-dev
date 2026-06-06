<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
  <title>Jeren J | Flagship Portfolio — Android & Full Stack Architect</title>
  <!-- Google Fonts & Font Awesome -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;400;500;600;700;800;900&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: #05070a;
      color: #f0f3fa;
      overflow-x: hidden;
      cursor: default;
      line-height: 1.5;
    }

    /* CANVAS 3D PARTICLE BACKGROUND - WORLD CLASS FIXED */
    #bg-canvas {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 0;
      display: block;
      pointer-events: none;
    }

    /* custom cursor glow (massive interactive) */
    .cursor-glow {
      position: fixed;
      width: 500px;
      height: 500px;
      background: radial-gradient(circle, rgba(99, 102, 241, 0.35) 0%, rgba(139, 92, 246, 0) 70%);
      border-radius: 50%;
      pointer-events: none;
      transform: translate(-50%, -50%);
      z-index: 2;
      filter: blur(80px);
      opacity: 0.9;
      transition: transform 0.03s linear;
    }

    /* custom scroll */
    ::-webkit-scrollbar {
      width: 6px;
    }
    ::-webkit-scrollbar-track {
      background: #0a0c15;
    }
    ::-webkit-scrollbar-thumb {
      background: #6366f1;
      border-radius: 20px;
    }

    /* container */
    .container {
      max-width: 1300px;
      margin: 0 auto;
      padding: 2rem 2rem 4rem;
      position: relative;
      z-index: 10;
    }

    /* glassmorphic card style - enhanced */
    .glass-card {
      background: rgba(12, 18, 30, 0.65);
      backdrop-filter: blur(14px);
      border-radius: 2rem;
      border: 1px solid rgba(99, 102, 241, 0.35);
      box-shadow: 0 25px 40px -12px rgba(0, 0, 0, 0.6);
      transition: all 0.35s cubic-bezier(0.2, 0.9, 0.4, 1.1);
    }
    .glass-card:hover {
      border-color: rgba(139, 92, 246, 0.7);
      box-shadow: 0 30px 45px -12px rgba(79, 70, 229, 0.5);
      background: rgba(15, 22, 38, 0.75);
    }

    /* header section big flex flagship */
    .hero {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 4rem;
      padding: 2rem 2.5rem !important;
    }

    .hero-left h1 {
      font-size: 4.6rem;
      font-weight: 800;
      background: linear-gradient(135deg, #ffffff, #c4b5fd, #a78bfa);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      letter-spacing: -0.02em;
      line-height: 1.2;
    }
    .badge {
      background: linear-gradient(95deg, #4f46e5, #7c3aed);
      padding: 0.3rem 1.1rem;
      border-radius: 40px;
      font-size: 0.75rem;
      font-weight: 700;
      display: inline-block;
      margin-top: 1rem;
      letter-spacing: 0.5px;
      box-shadow: 0 2px 12px rgba(79,70,229,0.5);
    }
    .hero-stats {
      display: flex;
      gap: 2.5rem;
      margin: 1.5rem 0;
    }
    .stat {
      text-align: center;
    }
    .stat-number {
      font-size: 2rem;
      font-weight: 800;
      background: linear-gradient(145deg, #c084fc, #a78bfa);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .hero-right {
      background: rgba(0, 0, 0, 0.45);
      border-radius: 2rem;
      padding: 1rem 2rem;
      backdrop-filter: blur(8px);
      border: 1px solid rgba(139, 92, 246, 0.6);
      transition: all 0.2s;
    }

    /* grid layout */
    .grid-2col {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
      gap: 2rem;
      margin-bottom: 3rem;
    }

    .section-title {
      font-size: 1.9rem;
      font-weight: 700;
      margin-bottom: 1.6rem;
      display: flex;
      align-items: center;
      gap: 0.8rem;
      border-left: 5px solid #6366f1;
      padding-left: 1.3rem;
    }

    .tech-stack {
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem;
      margin: 1rem 0;
    }
    .tech-item {
      background: rgba(79, 70, 229, 0.2);
      border: 1px solid #4f46e580;
      padding: 0.5rem 1.2rem;
      border-radius: 40px;
      font-size: 0.85rem;
      font-weight: 600;
      transition: 0.2s;
      cursor: default;
      backdrop-filter: blur(4px);
    }
    .tech-item i {
      margin-right: 8px;
      color: #a78bfa;
    }

    .featured-project {
      background: linear-gradient(125deg, #121a2c, #080c18);
      border-radius: 2rem;
      padding: 1.8rem;
      transition: transform 0.3s ease, box-shadow 0.3s;
      border: 1px solid rgba(99, 102, 241, 0.5);
    }
    .featured-project:hover {
      transform: translateY(-8px);
      box-shadow: 0 30px 40px -18px #4f46e5;
    }

    .project-title {
      font-size: 1.8rem;
      font-weight: 800;
    }
    .btn {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: linear-gradient(95deg, #4f46e5, #6d28d9);
      padding: 0.7rem 1.6rem;
      border-radius: 40px;
      font-weight: 700;
      text-decoration: none;
      color: white;
      transition: 0.2s;
      border: none;
      cursor: pointer;
      box-shadow: 0 4px 12px rgba(79,70,229,0.5);
    }
    .btn:hover {
      transform: scale(1.03);
      background: linear-gradient(95deg, #6366f1, #8b5cf6);
      box-shadow: 0 6px 16px rgba(139,92,246,0.5);
    }

    .social-links {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      margin-top: 1rem;
    }
    .social-icon {
      background: rgba(255, 255, 255, 0.05);
      backdrop-filter: blur(8px);
      padding: 0.7rem 1.3rem;
      border-radius: 50px;
      transition: 0.25s;
      color: #e2e8f0;
      text-decoration: none;
      font-size: 0.9rem;
      font-weight: 500;
      border: 1px solid rgba(255,255,255,0.08);
    }
    .social-icon i {
      margin-right: 8px;
      font-size: 1.1rem;
    }
    .social-icon:hover {
      background: #4f46e5;
      color: white;
      transform: translateY(-4px);
      border-color: #c084fc;
    }

    /* footer */
    .footer {
      text-align: center;
      margin-top: 4rem;
      padding-top: 2rem;
      border-top: 1px solid rgba(255, 255, 255, 0.1);
      font-size: 0.85rem;
      opacity: 0.8;
    }

    /* responsive */
    @media (max-width: 780px) {
      .hero-left h1 { font-size: 2.5rem; }
      .container { padding: 1rem; }
      .hero { padding: 1.5rem !important; }
      .section-title { font-size: 1.5rem; }
      .hero-stats { gap: 1rem; }
    }

    /* subtle pulse animation for flagship elements */
    @keyframes flagshipGlow {
      0% { box-shadow: 0 0 0 0 rgba(99, 102, 241, 0.2); border-color: rgba(99, 102, 241, 0.4);}
      50% { box-shadow: 0 0 0 10px rgba(99, 102, 241, 0.1); border-color: #c084fc;}
      100% { box-shadow: 0 0 0 0 rgba(99, 102, 241, 0); border-color: rgba(99, 102, 241, 0.4);}
    }
    .hero-right {
      animation: flagshipGlow 3s infinite ease;
    }
    .featured-project {
      animation: flagshipGlow 3.5s infinite ease 0.5s;
    }
  </style>
</head>
<body>

<!-- 3D Particle Canvas Background (Fully functional) -->
<canvas id="bg-canvas"></canvas>

<!-- Interactive mouse glow -->
<div class="cursor-glow" id="cursorGlow"></div>

<div class="container">
  <!-- HERO Section - Big Flex / Flagship Level -->
  <div class="hero glass-card">
    <div class="hero-left">
      <div class="badge"><i class="fas fa-crown"></i> FLAGSHIP ARCHITECT</div>
      <h1>👋 Hi, I'm Jeren J<br><span style="font-size: 1.9rem;">Android & Full Stack Virtuoso</span></h1>
      <div class="hero-stats">
        <div class="stat"><div class="stat-number">12+</div><div>Projects</div></div>
        <div class="stat"><div class="stat-number">100%</div><div>User First</div></div>
        <div class="stat"><div class="stat-number">🚀</div><div>Kotlin • Compose</div></div>
      </div>
      <p style="max-width: 550px; margin-bottom: 1.2rem;">📍 Trichy, Tamil Nadu, India — Crafting high-impact applications with world-class UI/UX and bleeding-edge tech.</p>
      <div class="social-links" style="margin-top: 0.2rem;">
        <a href="https://github.com/jeren-dev" target="_blank" class="social-icon"><i class="fab fa-github"></i> GitHub</a>
        <a href="https://linkedin.com/in/jeren-j-656a6031b" target="_blank" class="social-icon"><i class="fab fa-linkedin"></i> LinkedIn</a>
        <a href="mailto:jeren3439@gmail.com" class="social-icon"><i class="fas fa-envelope"></i> Email</a>
        <a href="https://instagram.com/mr____jerry__offl" target="_blank" class="social-icon"><i class="fab fa-instagram"></i> Instagram</a>
      </div>
    </div>
    <div class="hero-right">
      <i class="fas fa-quote-left" style="color:#a78bfa; opacity:0.9;"></i>
      <p style="font-style: italic; max-width: 280px; font-weight: 500;">"Always learning. Always building. Flagship mindset, pixel-perfect execution."</p>
      <div style="margin-top: 12px;"><i class="fas fa-microphone-alt"></i> VoiceBudget • <i class="fab fa-android"></i> Jetpack • <i class="fas fa-code-branch"></i> Full Stack</div>
    </div>
  </div>

  <!-- 2 col: About me + Currently -->
  <div class="grid-2col">
    <div class="glass-card" style="padding: 1.8rem;">
      <div class="section-title" style="border-left-color:#a855f7;"><i class="fas fa-user-astronaut"></i> 🚀 About Me</div>
      <p>I'm a passionate developer focused on building practical mobile and web applications with clean UI, strong functionality, and real-world impact. I specialize in <strong>Android development using Kotlin and Jetpack Compose</strong>, creating fast, user-friendly apps that solve everyday problems.</p>
      <div style="margin: 1rem 0;"><i class="fas fa-map-marker-alt" style="color:#c084fc;"></i> Trichy, India — open for freelance & global collabs</div>
      <div class="tech-stack" style="margin-top: 0.8rem;">
        <span class="tech-item"><i class="fab fa-android"></i> Kotlin</span>
        <span class="tech-item"><i class="fas fa-mobile-alt"></i> Jetpack Compose</span>
        <span class="tech-item"><i class="fas fa-database"></i> SQLite</span>
      </div>
    </div>

    <div class="glass-card" style="padding: 1.8rem;">
      <div class="section-title" style="border-left-color:#f97316;"><i class="fas fa-bolt"></i> Currently I am:</div>
      <ul style="list-style: none; margin-left: 0;">
        <li style="margin-bottom: 14px;">🔨 <strong>Building Android apps</strong> with real-world use cases</li>
        <li style="margin-bottom: 14px;">🌱 <strong>Improving Full Stack</strong> development (PHP • MySQL • Laravel basics)</li>
        <li style="margin-bottom: 14px;">💼 <strong>Exploring freelance opportunities</strong> & project-based work</li>
      </ul>
      <div class="badge" style="background: #0f172a; border:1px solid #6366f1;"><i class="fas fa-brain"></i> Goal: Professional Software Engineer → Launch my own tech empire</div>
    </div>
  </div>

  <!-- Tech Stack Full Showcase - massive layout -->
  <div class="glass-card" style="padding: 1.8rem; margin-bottom: 2rem;">
    <div class="section-title"><i class="fas fa-cogs"></i> 🛠️ Tech Stack — The Ultimate Arsenal</div>
    <div style="display: flex; flex-wrap: wrap; gap: 2rem; justify-content: space-between;">
      <div><h3><i class="fab fa-android"></i> 📱 Android</h3>
        <div class="tech-stack"><span class="tech-item">Kotlin</span><span class="tech-item">Jetpack Compose</span><span class="tech-item">XML UI</span><span class="tech-item">SQLite</span><span class="tech-item">Room</span><span class="tech-item">Coroutines</span></div>
      </div>
      <div><h3><i class="fas fa-globe"></i> 🌐 Web Dev</h3>
        <div class="tech-stack"><span class="tech-item">HTML5/CSS3</span><span class="tech-item">JavaScript ES6</span><span class="tech-item">PHP</span><span class="tech-item">MySQL</span><span class="tech-item">Tailwind</span></div>
      </div>
      <div><h3><i class="fas fa-tools"></i> ⚙️ Tools</h3>
        <div class="tech-stack"><span class="tech-item">Git/GitHub</span><span class="tech-item">Android Studio</span><span class="tech-item">VS Code</span><span class="tech-item">Figma</span><span class="tech-item">Postman</span></div>
      </div>
    </div>
  </div>

  <!-- Featured project flagship big card -->
  <div style="margin-bottom: 3rem;">
    <div class="section-title"><i class="fas fa-star-of-life"></i> 📌 FLAGSHIP PROJECT</div>
    <div class="featured-project">
      <div style="display: flex; flex-wrap: wrap; justify-content: space-between; align-items: center;">
        <div>
          <span class="badge" style="background:#7c3aed; font-size:0.7rem;">🔥 Voice-First Innovation</span>
          <div class="project-title" style="margin-top: 0.5rem;">💰 VoiceBudget – Smart Expense Tracker</div>
          <p style="margin: 1rem 0; max-width: 600px;">Revolutionary voice-enabled Android application that transforms expense tracking. Leverage voice commands for instant entry, SQLite for secure storage, and Jetpack Compose for fluid UI. Smart budget tracking system to master personal finance.</p>
          <div class="tech-stack">
            <span class="tech-item">Kotlin</span>
            <span class="tech-item">SQLite</span>
            <span class="tech-item">Voice Input API</span>
            <span class="tech-item">Jetpack Compose</span>
            <span class="tech-item">MVVM</span>
          </div>
          <a href="https://github.com/jeren-dev/VoiceBudget" target="_blank" class="btn" style="margin-top: 1.5rem;"><i class="fab fa-github"></i> Explore on GitHub →</a>
        </div>
        <div style="font-size: 5rem; opacity: 0.8; margin-top: 1rem;"><i class="fas fa-microphone-alt"></i> <i class="fas fa-chart-pie"></i></div>
      </div>
    </div>
  </div>

  <!-- What I Do + Goals combined with images alignment -->
  <div class="grid-2col">
    <div class="glass-card" style="padding: 1.8rem;">
      <div class="section-title"><i class="fas fa-laptop-code"></i> 🎯 What I Do</div>
      <div style="display: grid; gap: 1rem;">
        <div><i class="fas fa-check-circle" style="color:#4f46e5;"></i> Android App Development (Kotlin/Compose)</div>
        <div><i class="fas fa-check-circle" style="color:#4f46e5;"></i> Full Stack Web Development</div>
        <div><i class="fas fa-check-circle" style="color:#4f46e5;"></i> Freelance App Projects & UI/UX Design</div>
        <div><i class="fas fa-check-circle" style="color:#4f46e5;"></i> Problem Solving & System Architecture</div>
      </div>
      <div style="margin-top: 1.8rem; background: rgba(0,0,0,0.35); border-radius: 1rem; padding: 1rem;">
        <i class="fas fa-chart-line"></i> <strong>🌱 Long-term vision:</strong> Become professional software engineer, build impactful digital products, launch own tech applications, and dominate the freelance ecosystem globally.
      </div>
    </div>
    <div class="glass-card" style="padding: 1.8rem; text-align: center;">
      <i class="fas fa-palette" style="font-size: 2.5rem; color:#c4b5fd;"></i>
      <h3 style="margin: 1rem 0;">World-Class Design Philosophy</h3>
      <div style="display: flex; justify-content: center; gap: 1rem; margin: 0.5rem 0;">
        <img src="https://cdn-icons-png.flaticon.com/512/2933/2933245.png" width="70" alt="design" style="opacity: 0.9;">
        <img src="https://cdn-icons-png.flaticon.com/512/1055/1055666.png" width="70" alt="ui">
      </div>
      <p style="margin-top: 1rem;">UI/UX that blends modern glassmorphism, micro-interactions, and adaptive layouts — every interaction feels fluid and premium.</p>
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
    <p style="margin-top: 8px;"><i class="fas fa-crown"></i> World-class UI/UX • Dynamic 3D Particle Canvas • Mouse interactive glow • Flagship edition</p>
  </div>
</div>

<script>
  (function() {
    // ---- FIXED: 3D Particle Network Background (Canvas World-Class) ----
    const canvas = document.getElementById('bg-canvas');
    if (!canvas) return;
    const ctx = canvas.getContext('2d');
    let width = window.innerWidth;
    let height = window.innerHeight;
    let particles = [];
    const PARTICLE_COUNT = 150;
    let mouseX = width/2, mouseY = height/2;
    
    function initParticles() {
      particles = [];
      for (let i = 0; i < PARTICLE_COUNT; i++) {
        particles.push({
          x: Math.random() * width,
          y: Math.random() * height,
          radius: Math.random() * 2.5 + 1.2,
          vx: (Math.random() - 0.5) * 0.5,
          vy: (Math.random() - 0.5) * 0.5,
          baseColor: `hsl(${240 + Math.random() * 50}, 75%, 65%)`
        });
      }
    }
    
    function resizeCanvas() {
      width = window.innerWidth;
      height = window.innerHeight;
      canvas.width = width;
      canvas.height = height;
      initParticles();
    }
    
    function drawConnections() {
      for (let i = 0; i < particles.length; i++) {
        for (let j = i+1; j < particles.length; j++) {
          const dx = particles[i].x - particles[j].x;
          const dy = particles[i].y - particles[j].y;
          const dist = Math.hypot(dx, dy);
          if (dist < 130) {
            ctx.beginPath();
            ctx.moveTo(particles[i].x, particles[i].y);
            ctx.lineTo(particles[j].x, particles[j].y);
            const opacity = 0.25 * (1 - dist/130);
            ctx.strokeStyle = `rgba(139, 92, 246, ${opacity + 0.1})`;
            ctx.lineWidth = 0.9;
            ctx.stroke();
          }
        }
      }
    }
    
    function animateParticles() {
      if (!ctx) return;
      ctx.clearRect(0, 0, width, height);
      // beautiful dark gradient background
      const grad = ctx.createLinearGradient(0, 0, width*0.8, height);
      grad.addColorStop(0, '#02040c');
      grad.addColorStop(1, '#0a0f1c');
      ctx.fillStyle = grad;
      ctx.fillRect(0, 0, width, height);
      
      for (let p of particles) {
        // mouse attraction / repulsion effect for interactivity
        const dx = p.x - mouseX;
        const dy = p.y - mouseY;
        const dist = Math.hypot(dx, dy);
        if (dist < 160) {
          const angle = Math.atan2(dy, dx);
          const force = (160 - dist) / 160 * 1.0;
          p.vx += Math.cos(angle) * force * 0.18;
          p.vy += Math.sin(angle) * force * 0.18;
        }
        // velocity damping
        p.vx *= 0.99;
        p.vy *= 0.99;
        p.x += p.vx;
        p.y += p.vy;
        // wrap around edges smoothly
        if (p.x < -20) p.x = width + 20;
        if (p.x > width + 20) p.x = -20;
        if (p.y < -20) p.y = height + 20;
        if (p.y > height + 20) p.y = -20;
        
        ctx.beginPath();
        ctx.arc(p.x, p.y, p.radius, 0, Math.PI * 2);
        ctx.fillStyle = p.baseColor;
        ctx.shadowBlur = 10;
        ctx.shadowColor = "#a78bfa";
        ctx.fill();
        ctx.shadowBlur = 0;
      }
      drawConnections();
      requestAnimationFrame(animateParticles);
    }
    
    window.addEventListener('resize', () => {
      resizeCanvas();
    });
    
    // track mouse for both canvas interaction and cursor glow
    document.addEventListener('mousemove', (e) => {
      mouseX = e.clientX;
      mouseY = e.clientY;
      const cursorGlow = document.getElementById('cursorGlow');
      if (cursorGlow) {
        cursorGlow.style.transform = `translate(${e.clientX}px, ${e.clientY}px)`;
      }
    });
    
    resizeCanvas();
    animateParticles();
  })();

  // extra: interactive tech items hover scaling
  const techItems = document.querySelectorAll('.tech-item');
  techItems.forEach(item => {
    item.addEventListener('mouseenter', () => {
      item.style.transform = 'translateY(-4px) scale(1.02)';
      item.style.backgroundColor = '#4f46e5';
      item.style.borderColor = '#c084fc';
    });
    item.addEventListener('mouseleave', () => {
      item.style.transform = 'translateY(0px) scale(1)';
      item.style.backgroundColor = 'rgba(79, 70, 229, 0.2)';
    });
  });
  
  // smooth reveal
  window.addEventListener('load', () => {
    document.body.style.opacity = '1';
  });
  document.body.style.opacity = '1';
</script>
</body>
</html>
