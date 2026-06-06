<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Jeren J | Android & Full Stack Developer Portfolio</title>
  <!-- Google Fonts & Font Awesome -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;400;500;600;700;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: linear-gradient(135deg, #0a0c10 0%, #0f111a 100%);
      color: #eef2ff;
      line-height: 1.6;
      scroll-behavior: smooth;
    }

    /* Animated gradient background */
    .animated-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -2;
      background: radial-gradient(circle at 20% 30%, #0f172a, #020617);
    }

    .animated-bg::before {
      content: '';
      position: absolute;
      width: 200%;
      height: 200%;
      top: -50%;
      left: -50%;
      background: radial-gradient(circle, rgba(79,70,229,0.15) 0%, transparent 60%);
      animation: rotateBg 30s linear infinite;
    }

    @keyframes rotateBg {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }

    /* Mouse following glow */
    .mouse-glow {
      position: fixed;
      width: 400px;
      height: 400px;
      background: radial-gradient(circle, rgba(99,102,241,0.2) 0%, rgba(139,92,246,0) 70%);
      border-radius: 50%;
      pointer-events: none;
      transform: translate(-50%, -50%);
      z-index: 1;
      filter: blur(50px);
      transition: transform 0.08s linear;
    }

    /* Custom scrollbar */
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: #0f1117; }
    ::-webkit-scrollbar-thumb { background: #6366f1; border-radius: 10px; }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 2rem 1.5rem 4rem;
      position: relative;
      z-index: 10;
    }

    /* Glassmorphic card */
    .glass-card {
      background: rgba(18, 25, 45, 0.55);
      backdrop-filter: blur(12px);
      border-radius: 1.75rem;
      border: 1px solid rgba(99, 102, 241, 0.25);
      transition: all 0.3s cubic-bezier(0.2, 0.9, 0.4, 1.1);
    }
    .glass-card:hover {
      border-color: rgba(139, 92, 246, 0.5);
      box-shadow: 0 20px 35px -12px rgba(79,70,229,0.25);
    }

    /* Hero Section */
    .hero {
      padding: 2.5rem;
      margin-bottom: 2.5rem;
    }

    .hero-content h1 {
      font-size: 3.5rem;
      font-weight: 800;
      background: linear-gradient(135deg, #fff, #a5b4fc, #818cf8);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      margin-bottom: 0.75rem;
    }

    .hero-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.75rem;
      margin: 1.25rem 0;
    }

    .hero-tag {
      background: rgba(79,70,229,0.2);
      padding: 0.4rem 1rem;
      border-radius: 40px;
      font-size: 0.85rem;
      font-weight: 500;
      border: 1px solid rgba(99,102,241,0.4);
    }

    .hero-tag i {
      margin-right: 6px;
      color: #a78bfa;
    }

    .location {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      background: rgba(0,0,0,0.3);
      padding: 0.5rem 1.2rem;
      border-radius: 40px;
      font-size: 0.85rem;
      margin-top: 0.5rem;
    }

    /* Stats */
    .stats {
      display: flex;
      gap: 2rem;
      margin: 1.5rem 0;
    }
    .stat-item {
      text-align: center;
    }
    .stat-number {
      font-size: 2rem;
      font-weight: 800;
      color: #c084fc;
    }
    .stat-label {
      font-size: 0.8rem;
      opacity: 0.8;
    }

    /* Section Titles */
    .section-title {
      font-size: 1.8rem;
      font-weight: 700;
      margin-bottom: 1.5rem;
      display: flex;
      align-items: center;
      gap: 0.75rem;
      border-left: 4px solid #6366f1;
      padding-left: 1.2rem;
    }

    /* Grid Layout */
    .grid-2 {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 1.8rem;
      margin-bottom: 2.5rem;
    }

    .card {
      padding: 1.8rem;
    }

    /* Tech Stack Items */
    .tech-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem;
      margin-top: 1rem;
    }
    .tech-item {
      background: rgba(79,70,229,0.2);
      border: 1px solid rgba(99,102,241,0.4);
      padding: 0.5rem 1.2rem;
      border-radius: 40px;
      font-size: 0.85rem;
      font-weight: 500;
      transition: all 0.2s;
    }
    .tech-item:hover {
      background: #4f46e5;
      transform: translateY(-2px);
    }
    .tech-item i {
      margin-right: 6px;
      color: #c084fc;
    }

    /* Featured Project */
    .featured-project {
      background: linear-gradient(135deg, #111827, #0a0f1a);
      border-radius: 1.75rem;
      padding: 2rem;
      margin-bottom: 2.5rem;
      border: 1px solid rgba(99,102,241,0.3);
      transition: all 0.3s;
    }
    .featured-project:hover {
      transform: translateY(-5px);
      border-color: #818cf8;
      box-shadow: 0 25px 35px -15px rgba(79,70,229,0.3);
    }
    .project-badge {
      background: #7c3aed;
      padding: 0.25rem 0.9rem;
      border-radius: 30px;
      font-size: 0.7rem;
      font-weight: 600;
      display: inline-block;
    }
    .project-title {
      font-size: 1.8rem;
      font-weight: 800;
      margin: 0.75rem 0 0.5rem;
    }
    .btn {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: linear-gradient(95deg, #4f46e5, #6d28d9);
      padding: 0.7rem 1.5rem;
      border-radius: 40px;
      font-weight: 600;
      text-decoration: none;
      color: white;
      transition: all 0.2s;
      margin-top: 1rem;
    }
    .btn:hover {
      transform: scale(1.03);
      box-shadow: 0 5px 15px rgba(79,70,229,0.4);
    }

    /* Social Links */
    .social-links {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      margin-top: 1rem;
    }
    .social-link {
      background: rgba(255,255,255,0.05);
      padding: 0.6rem 1.3rem;
      border-radius: 50px;
      text-decoration: none;
      color: #e2e8f0;
      font-size: 0.9rem;
      transition: all 0.2s;
      border: 1px solid rgba(255,255,255,0.05);
    }
    .social-link i {
      margin-right: 8px;
    }
    .social-link:hover {
      background: #4f46e5;
      transform: translateY(-3px);
      border-color: #a78bfa;
    }

    /* List styling */
    .custom-list {
      list-style: none;
      padding-left: 0;
    }
    .custom-list li {
      margin-bottom: 0.8rem;
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }
    .custom-list li i {
      color: #818cf8;
      width: 1.4rem;
    }

    .goal-box {
      background: rgba(0,0,0,0.3);
      border-radius: 1rem;
      padding: 1rem;
      margin-top: 1.2rem;
      border-left: 3px solid #818cf8;
    }

    .footer {
      text-align: center;
      margin-top: 3rem;
      padding-top: 2rem;
      border-top: 1px solid rgba(255,255,255,0.08);
      font-size: 0.85rem;
      opacity: 0.7;
    }

    @media (max-width: 680px) {
      .hero-content h1 { font-size: 2.2rem; }
      .section-title { font-size: 1.4rem; }
      .container { padding: 1rem; }
      .hero { padding: 1.5rem; }
      .stats { gap: 1rem; }
      .stat-number { font-size: 1.5rem; }
    }

    /* Floating icons animation */
    @keyframes float {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-8px); }
    }
    .float-icon {
      animation: float 4s ease-in-out infinite;
    }
  </style>
</head>
<body>

<div class="animated-bg"></div>
<div class="mouse-glow" id="mouseGlow"></div>

<div class="container">
  <!-- Hero Section -->
  <div class="hero glass-card">
    <div class="hero-content">
      <h1>👋 Hi, I'm Jeren J</h1>
      <div class="hero-tags">
        <span class="hero-tag"><i class="fab fa-android"></i> Android Developer</span>
        <span class="hero-tag"><i class="fas fa-code"></i> Full Stack Developer</span>
        <span class="hero-tag"><i class="fas fa-rocket"></i> Freelance App Developer</span>
      </div>
      <p style="font-size: 1.05rem; max-width: 550px;">Building real-world apps that solve everyday problems with clean UI and strong functionality.</p>
      <div class="location">
        <i class="fas fa-map-marker-alt" style="color: #c084fc;"></i> Trichy, Tamil Nadu, India
      </div>
      <div class="stats">
        <div class="stat-item"><div class="stat-number">10+</div><div class="stat-label">Projects</div></div>
        <div class="stat-item"><div class="stat-number">100%</div><div class="stat-label">User Focus</div></div>
        <div class="stat-item"><div class="stat-number">⚡</div><div class="stat-label">Kotlin/Compose</div></div>
      </div>
      <div class="social-links">
        <a href="https://github.com/jeren-dev" target="_blank" class="social-link"><i class="fab fa-github"></i> GitHub</a>
        <a href="https://linkedin.com/in/jeren-j-656a6031b" target="_blank" class="social-link"><i class="fab fa-linkedin"></i> LinkedIn</a>
        <a href="mailto:jeren3439@gmail.com" class="social-link"><i class="fas fa-envelope"></i> Email</a>
        <a href="https://instagram.com/mr____jerry__offl" target="_blank" class="social-link"><i class="fab fa-instagram"></i> Instagram</a>
      </div>
    </div>
  </div>

  <!-- About + Current Grid -->
  <div class="grid-2">
    <div class="card glass-card">
      <div class="section-title"><i class="fas fa-user-astronaut"></i> 🚀 About Me</div>
      <p>I am a passionate developer focused on building practical mobile and web applications with clean UI, strong functionality, and real-world impact.</p>
      <p style="margin-top: 1rem;">I specialize in <strong>Android development using Kotlin and Jetpack Compose</strong>, and I enjoy creating fast, user-friendly applications that solve real problems.</p>
    </div>

    <div class="card glass-card">
      <div class="section-title"><i class="fas fa-bolt"></i> 📌 Currently I am:</div>
      <ul class="custom-list">
        <li><i class="fas fa-hammer"></i> Building Android apps with real-world use cases</li>
        <li><i class="fas fa-seedling"></i> Improving my Full Stack development skills</li>
        <li><i class="fas fa-briefcase"></i> Exploring freelance opportunities and project-based work</li>
      </ul>
    </div>
  </div>

  <!-- Tech Stack Full -->
  <div class="card glass-card" style="margin-bottom: 2rem;">
    <div class="section-title"><i class="fas fa-cogs"></i> 🛠️ Tech Stack</div>
    <div style="display: flex; flex-wrap: wrap; gap: 2rem; justify-content: space-between;">
      <div style="flex: 1; min-width: 200px;">
        <h3><i class="fab fa-android"></i> 📱 Android Development</h3>
        <div class="tech-grid">
          <span class="tech-item">Kotlin</span>
          <span class="tech-item">Jetpack Compose</span>
          <span class="tech-item">XML UI Design</span>
          <span class="tech-item">SQLite</span>
        </div>
      </div>
      <div style="flex: 1; min-width: 200px;">
        <h3><i class="fas fa-globe"></i> 🌐 Web Development</h3>
        <div class="tech-grid">
          <span class="tech-item">HTML</span>
          <span class="tech-item">CSS</span>
          <span class="tech-item">JavaScript</span>
          <span class="tech-item">PHP</span>
          <span class="tech-item">MySQL</span>
        </div>
      </div>
      <div style="flex: 1; min-width: 200px;">
        <h3><i class="fas fa-tools"></i> ⚙️ Tools</h3>
        <div class="tech-grid">
          <span class="tech-item">Git & GitHub</span>
          <span class="tech-item">Android Studio</span>
          <span class="tech-item">VS Code</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Featured Project -->
  <div class="featured-project">
    <div style="display: flex; flex-wrap: wrap; justify-content: space-between; align-items: center;">
      <div>
        <span class="project-badge"><i class="fas fa-microphone-alt"></i> Voice-First Innovation</span>
        <div class="project-title">💰 VoiceBudget – Smart Expense Tracker App</div>
        <p style="margin: 1rem 0; max-width: 550px;">A modern voice-enabled Android application that helps users track income and expenses easily and efficiently.</p>
        <div class="tech-grid" style="margin-bottom: 0.5rem;">
          <span class="tech-item">Kotlin</span>
          <span class="tech-item">SQLite</span>
          <span class="tech-item">Voice Input</span>
          <span class="tech-item">Jetpack Compose</span>
        </div>
        <ul class="custom-list" style="margin: 0.8rem 0;">
          <li><i class="fas fa-check-circle"></i> Built with Kotlin & SQLite</li>
          <li><i class="fas fa-check-circle"></i> Clean and user-friendly UI</li>
          <li><i class="fas fa-check-circle"></i> Voice-based expense entry</li>
          <li><i class="fas fa-check-circle"></i> Smart budget tracking system</li>
        </ul>
        <a href="https://github.com/jeren-dev/VoiceBudget" target="_blank" class="btn"><i class="fab fa-github"></i> View on GitHub →</a>
      </div>
      <div style="font-size: 4rem; opacity: 0.6; margin-top: 1rem;">
        <i class="fas fa-chart-line float-icon"></i>
        <i class="fas fa-microphone-alt" style="margin-left: 0.5rem;"></i>
      </div>
    </div>
  </div>

  <!-- What I Do + Goals -->
  <div class="grid-2">
    <div class="card glass-card">
      <div class="section-title"><i class="fas fa-laptop-code"></i> 🎯 What I Do</div>
      <ul class="custom-list">
        <li><i class="fas fa-mobile-alt"></i> Android App Development</li>
        <li><i class="fas fa-code"></i> Full Stack Web Development</li>
        <li><i class="fas fa-briefcase"></i> Freelance App Projects</li>
        <li><i class="fas fa-puzzle-piece"></i> Problem Solving & UI Design</li>
      </ul>
    </div>

    <div class="card glass-card">
      <div class="section-title"><i class="fas fa-chart-line"></i> 🌱 Goals</div>
      <p>My goal is to become a professional software engineer and build impactful digital products that solve real-world problems.</p>
      <div class="goal-box">
        <i class="fas fa-rocket" style="color: #c084fc;"></i> In the long term, I aim to grow as a freelance developer and launch my own tech-based applications.
      </div>
    </div>
  </div>

  <!-- Connect Section -->
  <div class="card glass-card" style="text-align: center;">
    <div class="section-title" style="justify-content: center; border-left: none;">
      <i class="fas fa-hand-peace"></i> 📫 Connect With Me
    </div>
    <div class="social-links" style="justify-content: center;">
      <a href="mailto:jeren3439@gmail.com" class="social-link"><i class="fas fa-envelope"></i> jeren3439@gmail.com</a>
      <a href="https://instagram.com/mr____jerry__offl" class="social-link"><i class="fab fa-instagram"></i> Instagram</a>
      <a href="https://linkedin.com/in/jeren-j-656a6031b" class="social-link"><i class="fab fa-linkedin"></i> LinkedIn</a>
      <a href="https://github.com/jeren-dev" class="social-link"><i class="fab fa-github"></i> GitHub</a>
    </div>
    <div style="margin-top: 1.2rem; font-size: 0.85rem; opacity: 0.7;">
      <i class="fas fa-map-pin"></i> Trichy, Tamil Nadu, India
    </div>
  </div>

  <div class="footer">
    <p>⭐ Always learning. Always building. — Jeren J | Android & Full Stack Developer</p>
  </div>
</div>

<script>
  // Mouse following glow effect
  const mouseGlow = document.getElementById('mouseGlow');
  document.addEventListener('mousemove', (e) => {
    if (mouseGlow) {
      mouseGlow.style.transform = `translate(${e.clientX}px, ${e.clientY}px)`;
    }
  });

  // Smooth hover animations for tech items
  const techItems = document.querySelectorAll('.tech-item');
  techItems.forEach(item => {
    item.addEventListener('mouseenter', () => {
      item.style.transform = 'translateY(-3px)';
    });
    item.addEventListener('mouseleave', () => {
      item.style.transform = 'translateY(0px)';
    });
  });

  // Interactive stat counter animation on scroll (simple)
  const statNumbers = document.querySelectorAll('.stat-number');
  const animateNumbers = () => {
    statNumbers.forEach(el => {
      if (el.innerText.includes('+')) {
        const target = parseInt(el.innerText);
        if (!el.dataset.animated && target) {
          el.dataset.animated = 'true';
          let current = 0;
          const increment = target / 30;
          const updateNumber = () => {
            current += increment;
            if (current < target) {
              el.innerText = Math.floor(current) + '+';
              requestAnimationFrame(updateNumber);
            } else {
              el.innerText = target + '+';
            }
          };
          updateNumber();
        }
      }
    });
  };
  
  // Trigger on load
  window.addEventListener('load', () => {
    animateNumbers();
  });
</script>
</body>
</html>
