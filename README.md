<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Surya — GitHub Profile README</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:ital,wght@0,300;0,400;1,300&family=Plus+Jakarta+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #050810;
    --surface: #0b1120;
    --surface2: #111827;
    --border: rgba(255,255,255,0.07);
    --accent: #38bdf8;
    --accent2: #818cf8;
    --accent3: #34d399;
    --gold: #fbbf24;
    --text: #e2e8f0;
    --muted: #64748b;
    --glow: rgba(56,189,248,0.15);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Plus Jakarta Sans', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background: 
      radial-gradient(ellipse 60% 40% at 20% 10%, rgba(56,189,248,0.06) 0%, transparent 70%),
      radial-gradient(ellipse 50% 50% at 80% 80%, rgba(129,140,248,0.06) 0%, transparent 70%),
      radial-gradient(ellipse 40% 30% at 60% 40%, rgba(52,211,153,0.04) 0%, transparent 60%);
    pointer-events: none;
    z-index: 0;
  }

  .wrapper {
    max-width: 900px;
    margin: 0 auto;
    padding: 40px 24px 80px;
    position: relative;
    z-index: 1;
  }

  /* ─── HERO ─── */
  .hero {
    text-align: center;
    padding: 60px 20px 50px;
    position: relative;
  }

  .hero-ring {
    display: inline-block;
    position: relative;
    margin-bottom: 28px;
  }

  .avatar-wrapper {
    width: 110px;
    height: 110px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent), var(--accent2), var(--accent3));
    padding: 3px;
    display: inline-block;
    animation: spinGradient 4s linear infinite;
  }

  @keyframes spinGradient {
    from { filter: hue-rotate(0deg); }
    to   { filter: hue-rotate(360deg); }
  }

  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: var(--surface);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 3rem;
  }

  .hero h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.4rem, 6vw, 3.6rem);
    font-weight: 800;
    letter-spacing: -0.03em;
    line-height: 1.1;
    background: linear-gradient(135deg, #e2e8f0 30%, var(--accent) 60%, var(--accent2) 90%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 12px;
  }

  .typing-line {
    font-family: 'DM Mono', monospace;
    font-size: 0.95rem;
    color: var(--accent3);
    letter-spacing: 0.05em;
    opacity: 0;
    animation: fadeUp 0.6s ease 0.4s forwards;
  }

  .typing-cursor {
    display: inline-block;
    width: 2px;
    height: 1em;
    background: var(--accent3);
    margin-left: 3px;
    vertical-align: text-bottom;
    animation: blink 1s step-end infinite;
  }

  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  .badge-row {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    margin-top: 24px;
    opacity: 0;
    animation: fadeUp 0.6s ease 0.7s forwards;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 999px;
    font-size: 0.78rem;
    font-weight: 500;
    border: 1px solid var(--border);
    background: var(--surface);
    backdrop-filter: blur(8px);
    transition: all 0.2s;
    cursor: default;
  }
  .badge:hover { border-color: var(--accent); transform: translateY(-2px); box-shadow: 0 4px 20px var(--glow); }
  .badge .dot { width: 6px; height: 6px; border-radius: 50%; }
  .badge.blue .dot { background: var(--accent); }
  .badge.purple .dot { background: var(--accent2); }
  .badge.green .dot { background: var(--accent3); }
  .badge.gold .dot { background: var(--gold); }

  /* ─── STATS ROW ─── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
    margin: 40px 0;
    opacity: 0;
    animation: fadeUp 0.6s ease 0.9s forwards;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px 20px;
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: all 0.3s;
  }

  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--accent-card), transparent);
  }

  .stat-card.c1 { --accent-card: var(--accent); }
  .stat-card.c2 { --accent-card: var(--accent2); }
  .stat-card.c3 { --accent-card: var(--accent3); }

  .stat-card:hover { transform: translateY(-4px); border-color: rgba(255,255,255,0.15); box-shadow: 0 12px 40px rgba(0,0,0,0.4); }

  .stat-icon { font-size: 1.8rem; margin-bottom: 10px; }
  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 2rem;
    font-weight: 800;
    color: var(--accent-card);
    line-height: 1;
    margin-bottom: 6px;
  }
  .stat-label { font-size: 0.78rem; color: var(--muted); font-weight: 500; text-transform: uppercase; letter-spacing: 0.08em; }

  /* ─── SECTION HEADER ─── */
  .section-header {
    display: flex;
    align-items: center;
    gap: 14px;
    margin: 50px 0 24px;
  }

  .section-header .icon-box {
    width: 40px; height: 40px;
    border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.1rem;
    flex-shrink: 0;
  }

  .icon-box.blue { background: rgba(56,189,248,0.12); border: 1px solid rgba(56,189,248,0.2); }
  .icon-box.purple { background: rgba(129,140,248,0.12); border: 1px solid rgba(129,140,248,0.2); }
  .icon-box.green { background: rgba(52,211,153,0.12); border: 1px solid rgba(52,211,153,0.2); }
  .icon-box.gold { background: rgba(251,191,36,0.12); border: 1px solid rgba(251,191,36,0.2); }

  .section-header h2 {
    font-family: 'Syne', sans-serif;
    font-size: 1.3rem;
    font-weight: 700;
    letter-spacing: -0.02em;
  }

  .section-header .line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ─── ABOUT ─── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }

  .about-item {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 18px 20px;
    display: flex;
    align-items: flex-start;
    gap: 14px;
    transition: all 0.25s;
  }
  .about-item:hover { border-color: rgba(255,255,255,0.15); transform: translateY(-2px); }

  .about-item .emoji { font-size: 1.4rem; flex-shrink: 0; margin-top: 1px; }
  .about-item .content p { font-size: 0.88rem; color: var(--text); line-height: 1.55; }
  .about-item .content span { font-size: 0.75rem; color: var(--muted); display: block; margin-bottom: 4px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.07em; }

  /* ─── EDUCATION ─── */
  .edu-timeline { position: relative; padding-left: 28px; }
  .edu-timeline::before {
    content: '';
    position: absolute;
    left: 8px; top: 8px; bottom: 8px;
    width: 1px;
    background: linear-gradient(to bottom, var(--accent), var(--accent2), transparent);
  }

  .edu-item {
    position: relative;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 20px 22px;
    margin-bottom: 14px;
    transition: all 0.25s;
  }
  .edu-item:hover { border-color: rgba(255,255,255,0.15); }
  .edu-item::before {
    content: '';
    position: absolute;
    left: -24px; top: 24px;
    width: 10px; height: 10px;
    border-radius: 50%;
    background: var(--accent);
    box-shadow: 0 0 10px var(--accent);
  }

  .edu-degree {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 1rem;
    margin-bottom: 4px;
  }
  .edu-school { font-size: 0.85rem; color: var(--muted); margin-bottom: 10px; }
  .edu-tag {
    display: inline-block;
    padding: 3px 12px;
    border-radius: 999px;
    font-size: 0.75rem;
    font-weight: 600;
    background: rgba(56,189,248,0.1);
    border: 1px solid rgba(56,189,248,0.2);
    color: var(--accent);
  }

  /* ─── PROJECTS ─── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 18px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 18px;
    padding: 26px 22px;
    position: relative;
    overflow: hidden;
    transition: all 0.3s;
  }
  .project-card:hover { transform: translateY(-5px); border-color: rgba(255,255,255,0.18); box-shadow: 0 20px 60px rgba(0,0,0,0.5); }

  .project-card::after {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at 0% 0%, var(--card-glow) 0%, transparent 50%);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .project-card:hover::after { opacity: 1; }
  .project-card.p1 { --card-glow: rgba(56,189,248,0.07); }
  .project-card.p2 { --card-glow: rgba(129,140,248,0.07); }

  .project-icon {
    width: 46px; height: 46px;
    border-radius: 12px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.4rem;
    margin-bottom: 16px;
  }
  .p1 .project-icon { background: rgba(56,189,248,0.1); border: 1px solid rgba(56,189,248,0.2); }
  .p2 .project-icon { background: rgba(129,140,248,0.1); border: 1px solid rgba(129,140,248,0.2); }

  .project-name {
    font-family: 'Syne', sans-serif;
    font-size: 1.05rem;
    font-weight: 700;
    margin-bottom: 6px;
  }

  .project-tech {
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    color: var(--accent);
    margin-bottom: 14px;
    opacity: 0.8;
  }

  .project-features { list-style: none; }
  .project-features li {
    font-size: 0.83rem;
    color: #94a3b8;
    padding: 5px 0;
    padding-left: 16px;
    position: relative;
    line-height: 1.5;
  }
  .project-features li::before {
    content: '▸';
    position: absolute;
    left: 0;
    color: var(--accent3);
    font-size: 0.7rem;
    top: 6px;
  }

  /* ─── TECH STACK ─── */
  .tech-sections { display: flex; flex-direction: column; gap: 24px; }

  .tech-group-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.12em;
    margin-bottom: 12px;
  }

  .tech-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .tech-pill {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 16px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    font-size: 0.83rem;
    font-weight: 500;
    transition: all 0.2s;
    cursor: default;
  }
  .tech-pill:hover { border-color: var(--accent); transform: translateY(-2px); box-shadow: 0 4px 16px var(--glow); color: var(--accent); }
  .tech-pill img { width: 20px; height: 20px; object-fit: contain; }

  /* ─── GITHUB STATS ─── */
  .github-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-top: 4px;
  }
  .github-stats img {
    width: 100%;
    border-radius: 14px;
    border: 1px solid var(--border);
    display: block;
  }

  /* ─── CONNECT ─── */
  .connect-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 14px;
  }

  .connect-card {
    flex: 1;
    min-width: 160px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 18px 20px;
    text-align: center;
    text-decoration: none;
    color: var(--text);
    transition: all 0.25s;
  }
  .connect-card:hover { transform: translateY(-4px); box-shadow: 0 12px 30px rgba(0,0,0,0.4); border-color: rgba(255,255,255,0.2); }
  .connect-card .c-icon { font-size: 1.6rem; margin-bottom: 8px; }
  .connect-card .c-label { font-size: 0.8rem; color: var(--muted); font-weight: 500; }

  /* ─── FOOTER ─── */
  .footer {
    text-align: center;
    margin-top: 60px;
    padding-top: 30px;
    border-top: 1px solid var(--border);
    font-size: 0.8rem;
    color: var(--muted);
    font-family: 'DM Mono', monospace;
  }

  .footer .wave { animation: wave 2s infinite; display: inline-block; transform-origin: 70% 70%; }
  @keyframes wave {
    0%,100% { transform: rotate(0deg); }
    20% { transform: rotate(25deg); }
    40% { transform: rotate(-10deg); }
    60% { transform: rotate(25deg); }
  }

  /* ─── ANIMATIONS ─── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .animate { opacity: 0; animation: fadeUp 0.6s ease forwards; }

  /* Scroll-triggered fade-in via intersection observer */
  .reveal { opacity: 0; transform: translateY(24px); transition: opacity 0.6s ease, transform 0.6s ease; }
  .reveal.visible { opacity: 1; transform: none; }

  /* README preview chip */
  .preview-chip {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    background: rgba(56,189,248,0.08);
    border: 1px solid rgba(56,189,248,0.2);
    border-radius: 999px;
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    color: var(--accent);
    margin-bottom: 30px;
  }

  @media (max-width: 640px) {
    .about-grid, .projects-grid, .github-stats { grid-template-columns: 1fr; }
    .stats-grid { grid-template-columns: 1fr 1fr; }
  }
</style>
</head>
<body>
<div class="wrapper">

  <!-- README chip -->
  <div style="text-align:center">
    <div class="preview-chip">
      <span>●</span> GitHub Profile README Preview
    </div>
  </div>

  <!-- ── HERO ── -->
  <div class="hero">
    <div class="hero-ring">
      <div class="avatar-wrapper">
        <div class="avatar-inner">🧠</div>
      </div>
    </div>

    <h1>Hi, I'm Surya 👋</h1>

    <div class="typing-line">
      <span id="typed"></span><span class="typing-cursor"></span>
    </div>

    <div class="badge-row">
      <div class="badge blue"><div class="dot"></div> AI &amp; Data Science</div>
      <div class="badge purple"><div class="dot"></div> Power BI Developer</div>
      <div class="badge green"><div class="dot"></div> Data Analyst</div>
      <div class="badge gold"><div class="dot"></div> 1200+ Problems Solved</div>
    </div>
  </div>

  <!-- ── STATS ── -->
  <div class="stats-grid reveal">
    <div class="stat-card c1">
      <div class="stat-icon">🏆</div>
      <div class="stat-num">1200+</div>
      <div class="stat-label">Problems Solved</div>
    </div>
    <div class="stat-card c2">
      <div class="stat-icon">📊</div>
      <div class="stat-num">7.25</div>
      <div class="stat-label">CGPA</div>
    </div>
    <div class="stat-card c3">
      <div class="stat-icon">🚀</div>
      <div class="stat-num">2+</div>
      <div class="stat-label">Live Projects</div>
    </div>
  </div>

  <!-- ── ABOUT ── -->
  <div class="section-header reveal">
    <div class="icon-box blue">🚀</div>
    <h2>About Me</h2>
    <div class="line"></div>
  </div>

  <div class="about-grid reveal">
    <div class="about-item">
      <div class="emoji">🎓</div>
      <div class="content">
        <span>Education</span>
        <p>B.Tech AI &amp; Data Science (2nd Year)<br>Sri Eshwar College of Engineering</p>
      </div>
    </div>
    <div class="about-item">
      <div class="emoji">💡</div>
      <div class="content">
        <span>Passion</span>
        <p>Passionate about AI, Data Science, Business Intelligence &amp; Analytics</p>
      </div>
    </div>
    <div class="about-item">
      <div class="emoji">📈</div>
      <div class="content">
        <span>Achievement</span>
        <p>Solved 1200+ coding problems across multiple competitive platforms</p>
      </div>
    </div>
    <div class="about-item">
      <div class="emoji">🌱</div>
      <div class="content">
        <span>Currently Learning</span>
        <p>Machine Learning · Power BI · SQL · Excel · Data Science</p>
      </div>
    </div>
  </div>

  <!-- ── EDUCATION ── -->
  <div class="section-header reveal">
    <div class="icon-box gold">🎓</div>
    <h2>Education</h2>
    <div class="line"></div>
  </div>

  <div class="edu-timeline reveal">
    <div class="edu-item">
      <div class="edu-degree">B.Tech — Artificial Intelligence &amp; Data Science</div>
      <div class="edu-school">📍 Sri Eshwar College of Engineering &nbsp;·&nbsp; 2024 – 2028</div>
      <span class="edu-tag">CGPA: 7.25</span>
    </div>
    <div class="edu-item">
      <div class="edu-degree">HSC — Higher Secondary Certificate</div>
      <div class="edu-school">📍 Government Higher Secondary School</div>
      <span class="edu-tag">87.5%</span>
    </div>
    <div class="edu-item">
      <div class="edu-degree">SSLC — Secondary School Leaving Certificate</div>
      <div class="edu-school">📍 Government Higher Secondary School</div>
      <span class="edu-tag">64.2%</span>
    </div>
  </div>

  <!-- ── PROJECTS ── -->
  <div class="section-header reveal">
    <div class="icon-box purple">🛠</div>
    <h2>Projects</h2>
    <div class="line"></div>
  </div>

  <div class="projects-grid reveal">
    <div class="project-card p1">
      <div class="project-icon">🌐</div>
      <div class="project-name">Personal Portfolio Website</div>
      <div class="project-tech">HTML · CSS · JavaScript</div>
      <ul class="project-features">
        <li>Fully responsive portfolio website</li>
        <li>Contact form + light/dark mode</li>
        <li>Theme switcher + animated UI</li>
        <li>Deployed via GitHub Pages</li>
      </ul>
    </div>
    <div class="project-card p2">
      <div class="project-icon">🤖</div>
      <div class="project-name">StartupPro — AI Startup Analysis</div>
      <div class="project-tech">Python · Streamlit · ML</div>
      <ul class="project-features">
        <li>Predicts startup success using ML</li>
        <li>Plotly-based interactive dashboards</li>
        <li>Automated SWOT analysis engine</li>
        <li>12-week execution roadmap</li>
        <li>Team &amp; funding suggestions</li>
        <li>Generates PDF reports</li>
      </ul>
    </div>
  </div>

  <!-- ── TECH STACK ── -->
  <div class="section-header reveal">
    <div class="icon-box green">⚡</div>
    <h2>Tech Stack &amp; Skills</h2>
    <div class="line"></div>
  </div>

  <div class="tech-sections reveal">
    <div>
      <div class="tech-group-label">⭐ Programming Languages</div>
      <div class="tech-pills">
        <div class="tech-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg">Python</div>
        <div class="tech-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg">C</div>
        <div class="tech-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg">C++</div>
        <div class="tech-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg">SQL</div>
      </div>
    </div>
    <div>
      <div class="tech-group-label">📊 Data Science &amp; BI</div>
      <div class="tech-pills">
        <div class="tech-pill">📊 Power BI</div>
        <div class="tech-pill">📈 Excel</div>
        <div class="tech-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pandas/pandas-original.svg">Pandas</div>
        <div class="tech-pill">🔢 NumPy</div>
        <div class="tech-pill">📉 Matplotlib</div>
        <div class="tech-pill">📐 Seaborn</div>
        <div class="tech-pill">🤖 Scikit-learn</div>
      </div>
    </div>
    <div>
      <div class="tech-group-label">🌐 Web Development</div>
      <div class="tech-pills">
        <div class="tech-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg">HTML5</div>
        <div class="tech-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg">CSS3</div>
        <div class="tech-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg">JavaScript</div>
        <div class="tech-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/streamlit/streamlit-original.svg" onerror="this.src='data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 20 20%22><text y=%2215%22 font-size=%2215%22>🔴</text></svg>'">Streamlit</div>
      </div>
    </div>
    <div>
      <div class="tech-group-label">🛠 Tools &amp; Platforms</div>
      <div class="tech-pills">
        <div class="tech-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg">Git</div>
        <div class="tech-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" style="filter:invert(1)">GitHub</div>
        <div class="tech-pill"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg">VS Code</div>
        <div class="tech-pill">📓 Jupyter</div>
        <div class="tech-pill">🐍 Anaconda</div>
      </div>
    </div>
  </div>

  <!-- ── GITHUB STATS ── -->
  <div class="section-header reveal">
    <div class="icon-box blue">📈</div>
    <h2>GitHub Stats</h2>
    <div class="line"></div>
  </div>

  <div class="github-stats reveal">
    <img src="https://github-readme-stats.vercel.app/api?username=SuryaKS&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0b1120&title_color=38bdf8&icon_color=818cf8&text_color=e2e8f0" alt="GitHub Stats" onerror="this.src='https://github-readme-stats.vercel.app/api?username=suryaks27&show_icons=true&theme=tokyonight&hide_border=true'">
    <img src="https://github-readme-streak-stats.herokuapp.com/?user=SuryaKS&theme=tokyonight&hide_border=true&background=0b1120&stroke=38bdf8&ring=818cf8&fire=34d399&currStreakLabel=38bdf8" alt="Streak Stats" onerror="this.src='https://github-readme-streak-stats.herokuapp.com/?user=suryaks27&theme=tokyonight&hide_border=true'">
  </div>

  <!-- ── CONNECT ── -->
  <div class="section-header reveal">
    <div class="icon-box green">🤝</div>
    <h2>Connect</h2>
    <div class="line"></div>
  </div>

  <div class="connect-grid reveal">
    <a class="connect-card" href="#">
      <div class="c-icon">💼</div>
      <div style="font-weight:600;font-size:0.9rem;margin-bottom:4px">LinkedIn</div>
      <div class="c-label">Professional</div>
    </a>
    <a class="connect-card" href="#">
      <div class="c-icon">🐙</div>
      <div style="font-weight:600;font-size:0.9rem;margin-bottom:4px">GitHub</div>
      <div class="c-label">Source Code</div>
    </a>
    <a class="connect-card" href="#">
      <div class="c-icon">📧</div>
      <div style="font-weight:600;font-size:0.9rem;margin-bottom:4px">Email</div>
      <div class="c-label">Direct Contact</div>
    </a>
    <a class="connect-card" href="#">
      <div class="c-icon">🌐</div>
      <div style="font-weight:600;font-size:0.9rem;margin-bottom:4px">Portfolio</div>
      <div class="c-label">My Work</div>
    </a>
  </div>

  <!-- ── FOOTER ── -->
  <div class="footer reveal">
    <p>Thanks for visiting! <span class="wave">👋</span></p>
    <p style="margin-top:8px;opacity:0.5">crafted with ❤️ by Surya · AI &amp; Data Science</p>
    <p style="margin-top:12px">
      <img src="https://komarev.com/ghpvc/?username=SuryaKS&label=Profile+Views&color=38bdf8&style=flat-square" alt="profile views" style="border-radius:4px">
    </p>
  </div>

</div>

<script>
// Typing animation
const phrases = [
  'AI & Data Science Student 🎓',
  'Data Analyst Enthusiast 📈',
  'Power BI Developer 📊',
  'ML Enthusiast 🤖',
  'Problem Solver 💡',
];
let pi = 0, ci = 0, deleting = false;
const el = document.getElementById('typed');

function type() {
  const cur = phrases[pi];
  if (!deleting) {
    el.textContent = cur.slice(0, ++ci);
    if (ci === cur.length) { deleting = true; setTimeout(type, 2000); return; }
  } else {
    el.textContent = cur.slice(0, --ci);
    if (ci === 0) { deleting = false; pi = (pi + 1) % phrases.length; }
  }
  setTimeout(type, deleting ? 40 : 65);
}
setTimeout(type, 1200);

// Scroll reveal
const obs = new IntersectionObserver(entries => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); obs.unobserve(e.target); } });
}, { threshold: 0.1 });
document.querySelectorAll('.reveal').forEach(el => obs.observe(el));
</script>
</body>
</html>
