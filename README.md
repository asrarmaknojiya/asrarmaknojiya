<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Asrar Maknojiya — Developer Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Mono:wght@400;500&family=Inter:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --card: #16161f;
    --border: rgba(255,255,255,0.07);
    --border-bright: rgba(255,255,255,0.14);
    --text-primary: #f0f0f8;
    --text-secondary: #8888aa;
    --text-muted: #55556a;
    --accent: #6c63ff;
    --accent-glow: rgba(108,99,255,0.25);
    --green: #22d3a0;
    --orange: #ff8c42;
    --pink: #f472b6;
    --yellow: #fbbf24;
    --font-head: 'Syne', sans-serif;
    --font-body: 'Inter', sans-serif;
    --font-mono: 'DM Mono', monospace;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text-primary);
    font-family: var(--font-body);
    line-height: 1.6;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Grid bg */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(108,99,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(108,99,255,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 0 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .hero {
    padding: 80px 0 60px;
    text-align: center;
    position: relative;
  }

  .hero-orb {
    position: absolute;
    top: -60px;
    left: 50%;
    transform: translateX(-50%);
    width: 320px;
    height: 320px;
    background: radial-gradient(circle, rgba(108,99,255,0.18) 0%, transparent 70%);
    pointer-events: none;
  }

  .avatar-ring {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 100px;
    height: 100px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent), var(--green));
    padding: 3px;
    margin-bottom: 24px;
    animation: pulse-ring 3s ease-in-out infinite;
  }

  @keyframes pulse-ring {
    0%, 100% { box-shadow: 0 0 0 0 rgba(108,99,255,0.4); }
    50% { box-shadow: 0 0 0 12px rgba(108,99,255,0); }
  }

  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: var(--surface);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--font-head);
    font-size: 32px;
    font-weight: 800;
    background: linear-gradient(135deg, #1a1a2e, #16213e);
    color: var(--accent);
    letter-spacing: -1px;
  }

  .hero-title {
    font-family: var(--font-head);
    font-size: clamp(36px, 6vw, 58px);
    font-weight: 800;
    letter-spacing: -2px;
    line-height: 1.05;
    margin-bottom: 12px;
    background: linear-gradient(135deg, #f0f0f8 30%, #8888aa);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-role {
    font-family: var(--font-mono);
    font-size: 14px;
    color: var(--accent);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 20px;
    opacity: 0.85;
  }

  .hero-bio {
    font-size: 15px;
    color: var(--text-secondary);
    max-width: 520px;
    margin: 0 auto 32px;
    line-height: 1.75;
  }

  .hero-bio strong { color: var(--text-primary); font-weight: 500; }

  /* Typing text */
  .typing-wrap {
    font-family: var(--font-mono);
    font-size: 13px;
    color: var(--green);
    background: rgba(34,211,160,0.08);
    border: 1px solid rgba(34,211,160,0.18);
    border-radius: 8px;
    display: inline-block;
    padding: 8px 18px;
    margin-bottom: 32px;
  }

  .cursor { animation: blink 1s step-end infinite; }
  @keyframes blink { 0%,100% { opacity:1; } 50% { opacity:0; } }

  /* Social links */
  .social-row {
    display: flex;
    gap: 10px;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 0;
  }

  .social-btn {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    padding: 8px 16px;
    border-radius: 8px;
    border: 1px solid var(--border-bright);
    background: var(--card);
    color: var(--text-secondary);
    font-size: 13px;
    font-family: var(--font-mono);
    text-decoration: none;
    transition: all 0.2s ease;
  }

  .social-btn:hover {
    border-color: var(--accent);
    color: var(--accent);
    transform: translateY(-2px);
  }

  .social-btn svg { width: 14px; height: 14px; fill: currentColor; flex-shrink: 0; }

  /* ── DIVIDER ── */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border-bright), transparent);
    margin: 48px 0;
  }

  /* ── SECTION LABEL ── */
  .section-label {
    font-family: var(--font-mono);
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border-bright);
  }

  /* ── TECH STACK ── */
  .tech-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
    gap: 12px;
    margin-bottom: 48px;
  }

  .tech-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 16px 14px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    cursor: default;
    transition: all 0.25s ease;
    text-align: center;
  }

  .tech-card:hover {
    border-color: var(--border-bright);
    transform: translateY(-3px);
    background: #1c1c28;
  }

  .tech-icon {
    width: 36px;
    height: 36px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
  }

  .tech-name {
    font-family: var(--font-head);
    font-size: 12px;
    font-weight: 600;
    color: var(--text-primary);
  }

  .tech-sub {
    font-size: 10px;
    color: var(--text-muted);
    font-family: var(--font-mono);
  }

  .t-react .tech-icon { background: rgba(97,218,251,0.12); }
  .t-js .tech-icon { background: rgba(247,220,111,0.12); }
  .t-node .tech-icon { background: rgba(68,170,68,0.12); }
  .t-express .tech-icon { background: rgba(200,200,200,0.08); }
  .t-java .tech-icon { background: rgba(248,152,32,0.12); }
  .t-spring .tech-icon { background: rgba(111,211,71,0.12); }
  .t-mysql .tech-icon { background: rgba(0,117,143,0.15); }
  .t-rest .tech-icon { background: rgba(108,99,255,0.12); }
  .t-jwt .tech-icon { background: rgba(244,114,182,0.12); }
  .t-git .tech-icon { background: rgba(240,80,50,0.12); }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 16px;
    margin-bottom: 48px;
  }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 22px 20px;
    position: relative;
    overflow: hidden;
    transition: all 0.25s ease;
    cursor: default;
  }

  .project-card:hover {
    border-color: var(--border-bright);
    transform: translateY(-3px);
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    border-radius: 14px 14px 0 0;
  }

  .p-realestate::before { background: linear-gradient(90deg, var(--accent), var(--green)); }
  .p-ecommerce::before { background: linear-gradient(90deg, var(--orange), var(--yellow)); }
  .p-tailor::before { background: linear-gradient(90deg, var(--pink), var(--accent)); }
  .p-jwt::before { background: linear-gradient(90deg, var(--green), var(--accent)); }
  .p-portfolio::before { background: linear-gradient(90deg, var(--yellow), var(--orange)); }
  .p-zepx::before { background: linear-gradient(90deg, var(--accent), var(--pink)); }

  .project-icon {
    font-size: 26px;
    margin-bottom: 12px;
    display: block;
  }

  .project-title {
    font-family: var(--font-head);
    font-size: 15px;
    font-weight: 700;
    color: var(--text-primary);
    margin-bottom: 6px;
  }

  .project-desc {
    font-size: 12.5px;
    color: var(--text-secondary);
    line-height: 1.6;
    margin-bottom: 14px;
  }

  .project-tags {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
  }

  .tag {
    font-family: var(--font-mono);
    font-size: 10px;
    padding: 3px 8px;
    border-radius: 5px;
    background: rgba(108,99,255,0.1);
    color: #9b93ff;
    border: 1px solid rgba(108,99,255,0.2);
  }

  .tag.green { background: rgba(34,211,160,0.1); color: #22d3a0; border-color: rgba(34,211,160,0.2); }
  .tag.orange { background: rgba(255,140,66,0.1); color: #ff8c42; border-color: rgba(255,140,66,0.2); }
  .tag.pink { background: rgba(244,114,182,0.1); color: #f472b6; border-color: rgba(244,114,182,0.2); }

  /* ── SKILLS BAR ── */
  .skills-list {
    display: flex;
    flex-direction: column;
    gap: 14px;
    margin-bottom: 48px;
  }

  .skill-row {
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .skill-label {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--text-secondary);
    width: 130px;
    flex-shrink: 0;
  }

  .skill-bar-bg {
    flex: 1;
    height: 6px;
    background: rgba(255,255,255,0.05);
    border-radius: 3px;
    overflow: hidden;
  }

  .skill-bar-fill {
    height: 100%;
    border-radius: 3px;
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 1s cubic-bezier(0.4,0,0.2,1);
  }

  .skill-bar-fill.animated { transform: scaleX(1); }

  .skill-pct {
    font-family: var(--font-mono);
    font-size: 11px;
    color: var(--text-muted);
    width: 32px;
    text-align: right;
  }

  /* ── STATS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 12px;
    margin-bottom: 48px;
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 16px;
    text-align: center;
    transition: all 0.2s ease;
  }

  .stat-card:hover {
    border-color: var(--accent);
    transform: translateY(-2px);
  }

  .stat-num {
    font-family: var(--font-head);
    font-size: 32px;
    font-weight: 800;
    color: var(--accent);
    line-height: 1;
    margin-bottom: 6px;
  }

  .stat-label {
    font-size: 11px;
    color: var(--text-muted);
    font-family: var(--font-mono);
    letter-spacing: 1px;
    text-transform: uppercase;
  }

  /* ── CURRENTLY EXPLORING ── */
  .exploring-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(210px, 1fr));
    gap: 10px;
    margin-bottom: 48px;
  }

  .exp-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 12px 16px;
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 13px;
    color: var(--text-secondary);
    transition: all 0.2s ease;
  }

  .exp-item:hover { border-color: var(--border-bright); color: var(--text-primary); }
  .exp-dot { width: 7px; height: 7px; border-radius: 50%; background: var(--green); flex-shrink: 0; animation: pulse-dot 2s ease infinite; }
  @keyframes pulse-dot { 0%,100% { opacity:1; } 50% { opacity:0.4; } }

  /* ── FOOTER ── */
  .footer {
    padding: 40px 0 60px;
    text-align: center;
    border-top: 1px solid var(--border);
  }

  .footer-text {
    font-size: 12px;
    color: var(--text-muted);
    font-family: var(--font-mono);
  }

  .footer-text a { color: var(--accent); text-decoration: none; }

  /* Animations */
  .fade-up {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.5s ease, transform 0.5s ease;
  }
  .fade-up.visible { opacity: 1; transform: translateY(0); }

  /* ── FILTER TABS ── */
  .filter-tabs {
    display: flex;
    gap: 8px;
    margin-bottom: 16px;
    flex-wrap: wrap;
  }

  .ftab {
    font-family: var(--font-mono);
    font-size: 11px;
    padding: 5px 14px;
    border-radius: 6px;
    border: 1px solid var(--border);
    background: transparent;
    color: var(--text-muted);
    cursor: pointer;
    transition: all 0.15s ease;
    letter-spacing: 1px;
    text-transform: uppercase;
  }

  .ftab:hover, .ftab.active {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(108,99,255,0.08);
  }

  .project-card.hidden { display: none; }
</style>
</head>
<body>

<div class="container">

  <!-- HERO -->
  <section class="hero">
    <div class="hero-orb"></div>
    <div class="avatar-ring">
      <div class="avatar-inner">AM</div>
    </div>
    <p class="hero-role">Full-Stack Developer</p>
    <h1 class="hero-title">Asrar Maknojiya</h1>
    <p class="hero-bio">
      Building <strong>scalable web apps</strong> with clean architecture.
      Passionate about <strong>React</strong>, <strong>Node.js</strong>, and <strong>Spring Boot</strong>
      — turning complex problems into elegant solutions.
    </p>
    <div class="typing-wrap">
      <span id="typed-text"></span><span class="cursor">▋</span>
    </div>
    <div class="social-row">
      <a href="https://asrarmaknojiya.vercel.app/" class="social-btn" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 17.93c-3.94-.49-7-3.85-7-7.93s3.06-7.44 7-7.93v15.86zm2-15.86c1.03.13 2 .45 2.87.93H13v-.93zM13 7h5.24c.25.31.48.65.68 1H13V7zm0 3h6.74c.08.32.15.65.19 1H13v-1zm0 9.93V19h2.87c-.87.48-1.84.8-2.87.93zM18.24 17H13v-1h5.92c-.2.35-.43.69-.68 1zm1.5-3H13v-1h6.93c-.04.35-.11.68-.19 1z"/></svg>
        Portfolio
      </a>
      <a href="https://github.com/asrarmaknojiya" class="social-btn" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.44 9.8 8.21 11.39.6.11.82-.26.82-.58v-2.03c-3.34.73-4.04-1.61-4.04-1.61-.55-1.39-1.34-1.76-1.34-1.76-1.09-.74.08-.73.08-.73 1.21.09 1.84 1.24 1.84 1.24 1.07 1.84 2.81 1.31 3.5 1 .11-.78.42-1.31.76-1.61-2.67-.3-5.47-1.33-5.47-5.93 0-1.31.47-2.38 1.24-3.22-.12-.3-.54-1.52.12-3.18 0 0 1.01-.32 3.3 1.23A11.5 11.5 0 0112 5.8c1.02.005 2.04.14 3 .41 2.28-1.55 3.29-1.23 3.29-1.23.66 1.66.24 2.88.12 3.18.77.84 1.24 1.91 1.24 3.22 0 4.61-2.81 5.62-5.48 5.92.43.37.81 1.1.81 2.22v3.29c0 .32.21.7.82.58C20.56 21.8 24 17.31 24 12c0-6.63-5.37-12-12-12z"/></svg>
        GitHub
      </a>
      <a href="https://www.linkedin.com/in/asrar-maknojiya-b03a01326/" class="social-btn" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M20.45 20.45h-3.55v-5.57c0-1.33-.03-3.04-1.85-3.04-1.85 0-2.13 1.45-2.13 2.94v5.67H9.37V9h3.41v1.56h.05c.48-.9 1.64-1.85 3.37-1.85 3.6 0 4.27 2.37 4.27 5.45v6.29zM5.34 7.43a2.06 2.06 0 110-4.12 2.06 2.06 0 010 4.12zm1.78 13.02H3.56V9h3.56v11.45zM22.23 0H1.77C.79 0 0 .77 0 1.72v20.56C0 23.23.79 24 1.77 24h20.46c.98 0 1.77-.77 1.77-1.72V1.72C24 .77 23.21 0 22.23 0z"/></svg>
        LinkedIn
      </a>
      <a href="mailto:asrarjabir786@gmail.com" class="social-btn">
        <svg viewBox="0 0 24 24"><path d="M24 5.46v13.08A2.46 2.46 0 0121.54 21H2.46A2.46 2.46 0 010 18.54V5.46A2.46 2.46 0 012.46 3h19.08A2.46 2.46 0 0124 5.46zm-2.46-.92H2.46L12 11.87l9.54-7.33zm.92 1.86L12.56 14.1a.92.92 0 01-1.12 0L1.54 6.4V18.54c0 .51.41.92.92.92h19.08c.51 0 .92-.41.92-.92V6.4z"/></svg>
        Email
      </a>
    </div>
  </section>

  <div class="divider"></div>

  <!-- STATS -->
  <section class="fade-up">
    <div class="section-label">Quick Stats</div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-num">16+</div>
        <div class="stat-label">Repositories</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">6+</div>
        <div class="stat-label">Projects Built</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">5+</div>
        <div class="stat-label">Tech Stacks</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">∞</div>
        <div class="stat-label">Lines of Code</div>
      </div>
    </div>
  </section>

  <!-- TECH STACK -->
  <section class="fade-up">
    <div class="section-label">Tech Stack</div>
    <div class="tech-grid">
      <div class="tech-card t-react">
        <div class="tech-icon">⚛️</div>
        <div class="tech-name">React</div>
        <div class="tech-sub">Frontend</div>
      </div>
      <div class="tech-card t-js">
        <div class="tech-icon">⚡</div>
        <div class="tech-name">JavaScript</div>
        <div class="tech-sub">ES2022+</div>
      </div>
      <div class="tech-card t-node">
        <div class="tech-icon">🟢</div>
        <div class="tech-name">Node.js</div>
        <div class="tech-sub">Runtime</div>
      </div>
      <div class="tech-card t-express">
        <div class="tech-icon">🚂</div>
        <div class="tech-name">Express.js</div>
        <div class="tech-sub">Backend</div>
      </div>
      <div class="tech-card t-java">
        <div class="tech-icon">☕</div>
        <div class="tech-name">Java</div>
        <div class="tech-sub">OOP Language</div>
      </div>
      <div class="tech-card t-spring">
        <div class="tech-icon">🌱</div>
        <div class="tech-name">Spring Boot</div>
        <div class="tech-sub">Java Framework</div>
      </div>
      <div class="tech-card t-mysql">
        <div class="tech-icon">🗄️</div>
        <div class="tech-name">MySQL</div>
        <div class="tech-sub">Database</div>
      </div>
      <div class="tech-card t-rest">
        <div class="tech-icon">🔗</div>
        <div class="tech-name">REST APIs</div>
        <div class="tech-sub">Architecture</div>
      </div>
      <div class="tech-card t-jwt">
        <div class="tech-icon">🔐</div>
        <div class="tech-name">JWT Auth</div>
        <div class="tech-sub">Security</div>
      </div>
      <div class="tech-card t-git">
        <div class="tech-icon">🌿</div>
        <div class="tech-name">Git</div>
        <div class="tech-sub">Version Control</div>
      </div>
    </div>
  </section>

  <!-- SKILL PROFICIENCY -->
  <section class="fade-up">
    <div class="section-label">Proficiency</div>
    <div class="skills-list" id="skills-list">
      <div class="skill-row">
        <span class="skill-label">React.js</span>
        <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:92%;background:linear-gradient(90deg,#6c63ff,#22d3a0)"></div></div>
        <span class="skill-pct">92%</span>
      </div>
      <div class="skill-row">
        <span class="skill-label">JavaScript</span>
        <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:90%;background:linear-gradient(90deg,#fbbf24,#ff8c42)"></div></div>
        <span class="skill-pct">90%</span>
      </div>
      <div class="skill-row">
        <span class="skill-label">Node.js</span>
        <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:85%;background:linear-gradient(90deg,#22d3a0,#6c63ff)"></div></div>
        <span class="skill-pct">85%</span>
      </div>
      <div class="skill-row">
        <span class="skill-label">Express.js</span>
        <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:83%;background:linear-gradient(90deg,#aaaacc,#6c63ff)"></div></div>
        <span class="skill-pct">83%</span>
      </div>
      <div class="skill-row">
        <span class="skill-label">Java</span>
        <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:78%;background:linear-gradient(90deg,#ff8c42,#fbbf24)"></div></div>
        <span class="skill-pct">78%</span>
      </div>
      <div class="skill-row">
        <span class="skill-label">Spring Boot</span>
        <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:72%;background:linear-gradient(90deg,#6fcf47,#22d3a0)"></div></div>
        <span class="skill-pct">72%</span>
      </div>
      <div class="skill-row">
        <span class="skill-label">MySQL</span>
        <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:80%;background:linear-gradient(90deg,#008f8f,#22d3a0)"></div></div>
        <span class="skill-pct">80%</span>
      </div>
      <div class="skill-row">
        <span class="skill-label">REST APIs</span>
        <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:88%;background:linear-gradient(90deg,#f472b6,#6c63ff)"></div></div>
        <span class="skill-pct">88%</span>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section class="fade-up">
    <div class="section-label">Featured Projects</div>
    <div class="filter-tabs">
      <button class="ftab active" data-filter="all">All</button>
      <button class="ftab" data-filter="react">React</button>
      <button class="ftab" data-filter="node">Node.js</button>
      <button class="ftab" data-filter="java">Java / Spring</button>
    </div>
    <div class="projects-grid" id="projects-grid">
      <div class="project-card p-realestate" data-tags="react,node">
        <span class="project-icon">🏢</span>
        <div class="project-title">Real Estate Management System</div>
        <div class="project-desc">Full-featured property management platform with listings, dashboards, and role-based access control.</div>
        <div class="project-tags">
          <span class="tag">React</span>
          <span class="tag green">Node.js</span>
          <span class="tag green">MySQL</span>
        </div>
      </div>
      <div class="project-card p-ecommerce" data-tags="react,node">
        <span class="project-icon">🛒</span>
        <div class="project-title">E-Commerce Platform</div>
        <div class="project-desc">End-to-end e-commerce engine with full CRUD, cart system, order tracking, and admin dashboard.</div>
        <div class="project-tags">
          <span class="tag">React</span>
          <span class="tag orange">Express.js</span>
          <span class="tag green">MySQL</span>
        </div>
      </div>
      <div class="project-card p-tailor" data-tags="react,node">
        <span class="project-icon">🧵</span>
        <div class="project-title">TailorConnect</div>
        <div class="project-desc">Smart tailor finder platform connecting customers with local tailors via location-based search and booking.</div>
        <div class="project-tags">
          <span class="tag">React</span>
          <span class="tag pink">Node.js</span>
          <span class="tag">REST API</span>
        </div>
      </div>
      <div class="project-card p-jwt" data-tags="node,java">
        <span class="project-icon">🔐</span>
        <div class="project-title">JWT Auth + RBAC System</div>
        <div class="project-desc">Secure authentication system with JSON Web Tokens and Role-Based Access Control for enterprise use.</div>
        <div class="project-tags">
          <span class="tag green">Node.js</span>
          <span class="tag">JWT</span>
          <span class="tag orange">Java</span>
        </div>
      </div>
      <div class="project-card p-portfolio" data-tags="react">
        <span class="project-icon">💼</span>
        <div class="project-title">Developer Portfolio</div>
        <div class="project-desc">Personal portfolio website built with React + TypeScript, featuring smooth animations and responsive design.</div>
        <div class="project-tags">
          <span class="tag">React</span>
          <span class="tag orange">TypeScript</span>
          <span class="tag green">Vercel</span>
        </div>
      </div>
      <div class="project-card p-zepx" data-tags="react,node">
        <span class="project-icon">⚡</span>
        <div class="project-title">Zepx</div>
        <div class="project-desc">A JavaScript-based full-stack application showcasing modern patterns with clean component architecture.</div>
        <div class="project-tags">
          <span class="tag">JavaScript</span>
          <span class="tag">React</span>
          <span class="tag green">Node.js</span>
        </div>
      </div>
    </div>
  </section>

  <!-- CURRENTLY EXPLORING -->
  <section class="fade-up">
    <div class="section-label">Currently Exploring</div>
    <div class="exploring-list">
      <div class="exp-item"><span class="exp-dot"></span>Advanced React Patterns & TypeScript</div>
      <div class="exp-item"><span class="exp-dot"></span>Spring Boot Microservices</div>
      <div class="exp-item"><span class="exp-dot"></span>Clean Architecture & SOLID</div>
      <div class="exp-item"><span class="exp-dot"></span>Backend Security & JWT flows</div>
      <div class="exp-item"><span class="exp-dot"></span>Multi-domain SaaS systems</div>
      <div class="exp-item"><span class="exp-dot"></span>REST API Design Best Practices</div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <p class="footer-text">
      Built with passion · <a href="https://github.com/asrarmaknojiya" target="_blank">@asrarmaknojiya</a> · Open to opportunities
    </p>
  </footer>

</div>

<script>
  // Typing animation
  const lines = [
    'const dev = "Full-Stack JS Developer";',
    'const skills = ["React","Node","Java","Spring"];',
    'const passion = "Clean code & scalable apps";',
    'console.log("Always building, always learning");'
  ];
  let li = 0, ci = 0, deleting = false;
  const el = document.getElementById('typed-text');
  function type() {
    const line = lines[li];
    if (!deleting) {
      el.textContent = line.slice(0, ++ci);
      if (ci === line.length) { deleting = true; setTimeout(type, 1800); return; }
    } else {
      el.textContent = line.slice(0, --ci);
      if (ci === 0) { deleting = false; li = (li + 1) % lines.length; setTimeout(type, 400); return; }
    }
    setTimeout(type, deleting ? 30 : 55);
  }
  setTimeout(type, 800);

  // Intersection observer for fade-up
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
  }, { threshold: 0.1 });
  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

  // Skill bar animation
  const barObserver = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.querySelectorAll('.skill-bar-fill').forEach(b => b.classList.add('animated'));
      }
    });
  }, { threshold: 0.3 });
  const sl = document.getElementById('skills-list');
  if (sl) barObserver.observe(sl);

  // Project filter tabs
  document.querySelectorAll('.ftab').forEach(tab => {
    tab.addEventListener('click', function() {
      document.querySelectorAll('.ftab').forEach(t => t.classList.remove('active'));
      this.classList.add('active');
      const filter = this.dataset.filter;
      document.querySelectorAll('.project-card').forEach(card => {
        const tags = card.dataset.tags || '';
        card.classList.toggle('hidden', filter !== 'all' && !tags.includes(filter));
      });
    });
  });
</script>
</body>
</html>
