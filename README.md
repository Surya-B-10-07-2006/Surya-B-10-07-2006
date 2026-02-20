<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Surya B — GitHub Profile README</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0e1a;
    --surface: #0f1628;
    --card: #131929;
    --border: #1e2d4a;
    --accent: #00d4ff;
    --accent2: #7c3aed;
    --accent3: #10b981;
    --text: #e2e8f0;
    --muted: #64748b;
    --glow: rgba(0,212,255,0.15);
  }

  * { margin:0; padding:0; box-sizing:border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated grid background */
  body::before {
    content:'';
    position:fixed;
    inset:0;
    background-image:
      linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
    background-size: 50px 50px;
    pointer-events:none;
    z-index:0;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 40px 20px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    text-align: center;
    margin-bottom: 48px;
    animation: fadeDown 0.8s ease both;
  }

  .avatar-ring {
    width: 110px;
    height: 110px;
    border-radius: 50%;
    margin: 0 auto 20px;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    padding: 3px;
    position: relative;
  }

  .avatar-inner {
    width:100%;
    height:100%;
    border-radius:50%;
    background: var(--bg);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 42px;
  }

  .avatar-ring::after {
    content:'';
    position:absolute;
    inset:-6px;
    border-radius:50%;
    border: 2px solid rgba(0,212,255,0.2);
    animation: spin 8s linear infinite;
  }

  @keyframes spin { to { transform: rotate(360deg); } }

  .name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2rem, 5vw, 3rem);
    font-weight: 800;
    background: linear-gradient(135deg, var(--accent), var(--accent2) 60%, var(--accent3));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    letter-spacing: -1px;
    margin-bottom: 8px;
  }

  .tagline {
    color: var(--muted);
    font-size: 0.85rem;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 20px;
  }

  .typing-line {
    display: inline-block;
    font-size: 1rem;
    color: var(--accent3);
    border-right: 2px solid var(--accent3);
    white-space: nowrap;
    overflow: hidden;
    animation: typing 3s steps(45) 1s both, blink 0.75s step-end infinite;
    max-width: fit-content;
    margin: 0 auto;
  }

  @keyframes typing {
    from { width: 0 }
    to { width: 100% }
  }
  @keyframes blink {
    50% { border-color: transparent }
  }

  /* ── CONTACT BADGES ── */
  .badges {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    margin-top: 20px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 20px;
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 0.5px;
    text-decoration: none;
    transition: transform 0.2s, box-shadow 0.2s;
    cursor: pointer;
  }

  .badge:hover { transform: translateY(-2px); box-shadow: 0 4px 20px rgba(0,212,255,0.3); }

  .badge-blue  { background: rgba(0,212,255,0.1); border: 1px solid rgba(0,212,255,0.3); color: var(--accent); }
  .badge-purple{ background: rgba(124,58,237,0.1); border: 1px solid rgba(124,58,237,0.3); color: #a78bfa; }
  .badge-green { background: rgba(16,185,129,0.1); border: 1px solid rgba(16,185,129,0.3); color: var(--accent3); }

  /* ── SECTION TITLE ── */
  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 0.7rem;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .section-title::after {
    content:'';
    flex:1;
    height:1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  /* ── CARDS ── */
  .card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, box-shadow 0.3s;
  }

  .card::before {
    content:'';
    position:absolute;
    top:0; left:0; right:0;
    height:2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s ease;
  }

  .card:hover { border-color: rgba(0,212,255,0.3); box-shadow: 0 0 30px var(--glow); }
  .card:hover::before { transform: scaleX(1); }

  /* ── STATS GRID ── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 16px;
    margin-bottom: 32px;
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    text-align: center;
    position: relative;
    overflow: hidden;
    animation: fadeUp 0.6s ease both;
    transition: transform 0.2s;
  }

  .stat-card:hover { transform: translateY(-4px); }

  .stat-card::after {
    content:'';
    position:absolute;
    inset:0;
    background: radial-gradient(circle at 50% 0%, var(--glow), transparent 70%);
    pointer-events:none;
  }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 2rem;
    font-weight: 800;
    color: var(--accent);
    display: block;
  }

  .stat-label {
    font-size: 0.7rem;
    color: var(--muted);
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-top: 4px;
  }

  /* ── SKILLS ── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 16px;
    margin-bottom: 32px;
  }

  .skill-group-title {
    font-size: 0.65rem;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent2);
    margin-bottom: 12px;
    font-weight: 700;
  }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .skill-tag {
    padding: 4px 12px;
    border-radius: 6px;
    font-size: 0.72rem;
    font-weight: 700;
    background: var(--surface);
    border: 1px solid var(--border);
    color: var(--text);
    transition: all 0.2s;
    cursor: default;
  }

  .skill-tag:hover {
    border-color: var(--accent);
    color: var(--accent);
    box-shadow: 0 0 10px rgba(0,212,255,0.2);
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 16px;
    margin-bottom: 32px;
  }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    position: relative;
    overflow: hidden;
    animation: fadeUp 0.7s ease both;
    transition: transform 0.3s, box-shadow 0.3s;
  }

  .project-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 12px 40px rgba(0,212,255,0.12);
    border-color: rgba(0,212,255,0.4);
  }

  .project-icon {
    font-size: 1.8rem;
    margin-bottom: 12px;
    display: block;
  }

  .project-name {
    font-family: 'Syne', sans-serif;
    font-size: 1.1rem;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 8px;
  }

  .project-desc {
    font-size: 0.78rem;
    color: var(--muted);
    line-height: 1.7;
    margin-bottom: 16px;
  }

  .project-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .stack-pill {
    padding: 2px 10px;
    border-radius: 4px;
    font-size: 0.65rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  .stack-pill.blue { background: rgba(0,212,255,0.15); color: var(--accent); }
  .stack-pill.purple { background: rgba(124,58,237,0.15); color: #a78bfa; }
  .stack-pill.green { background: rgba(16,185,129,0.15); color: var(--accent3); }
  .stack-pill.orange { background: rgba(251,146,60,0.15); color: #fb923c; }

  /* ── CODING PROFILES ── */
  .profiles-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 14px;
    margin-bottom: 32px;
  }

  .profile-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px;
    text-align: center;
    transition: all 0.25s;
    cursor: pointer;
  }

  .profile-card:hover {
    border-color: var(--accent);
    background: rgba(0,212,255,0.05);
    transform: scale(1.03);
  }

  .profile-emoji { font-size: 1.6rem; display: block; margin-bottom: 8px; }
  .profile-name { font-size: 0.8rem; font-weight: 700; color: var(--text); margin-bottom: 4px; }
  .profile-stat { font-size: 0.7rem; color: var(--accent3); }

  /* ── CERTS ── */
  .certs-list { display: flex; flex-direction: column; gap: 12px; margin-bottom: 32px; }

  .cert-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px 20px;
    display: flex;
    align-items: center;
    gap: 14px;
    transition: all 0.2s;
  }

  .cert-item:hover { border-color: rgba(16,185,129,0.4); background: rgba(16,185,129,0.04); }

  .cert-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--accent3);
    flex-shrink: 0;
    box-shadow: 0 0 8px var(--accent3);
  }

  .cert-name { font-size: 0.82rem; color: var(--text); flex:1; }
  .cert-year { font-size: 0.72rem; color: var(--muted); }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding: 32px 0 16px;
    border-top: 1px solid var(--border);
    margin-top: 32px;
  }

  .footer-text { font-size: 0.72rem; color: var(--muted); letter-spacing: 2px; }
  .footer-text span { color: var(--accent); }

  /* ── ANIMATIONS ── */
  @keyframes fadeDown {
    from { opacity:0; transform: translateY(-30px); }
    to { opacity:1; transform: translateY(0); }
  }
  @keyframes fadeUp {
    from { opacity:0; transform: translateY(20px); }
    to { opacity:1; transform: translateY(0); }
  }

  .animate { animation: fadeUp 0.6s ease both; }
  .delay-1 { animation-delay: 0.1s; }
  .delay-2 { animation-delay: 0.2s; }
  .delay-3 { animation-delay: 0.3s; }
  .delay-4 { animation-delay: 0.4s; }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 4px; }

  /* Hover glow on section areas */
  .section-block { margin-bottom: 36px; }
</style>
</head>
<body>

<div class="container">

  <!-- ── HEADER ── -->
  <header class="header">
    <div class="avatar-ring">
      <div class="avatar-inner">🚀</div>
    </div>
    <h1 class="name">Surya B</h1>
    <p class="tagline">AI & Data Science · Sri Eshwar College of Engineering</p>
    <p class="typing-line">Building intelligent systems, one line at a time.</p>
    <div class="badges">
      <span class="badge badge-blue">📧 surya.b2024aids@sece.ac.in</span>
      <span class="badge badge-purple">📱 8189840977</span>
      <span class="badge badge-green">📍 B.Tech AIDS · 2024–2028</span>
    </div>
  </header>

  <!-- ── STATS ── -->
  <div class="section-block animate delay-1">
    <p class="section-title">// by the numbers</p>
    <div class="stats-grid">
      <div class="stat-card">
        <span class="stat-num">700+</span>
        <span class="stat-label">SkillRack Problems</span>
      </div>
      <div class="stat-card">
        <span class="stat-num">300+</span>
        <span class="stat-label">CodeChef Problems</span>
      </div>
      <div class="stat-card">
        <span class="stat-num">200+</span>
        <span class="stat-label">LeetCode Problems</span>
      </div>
      <div class="stat-card">
        <span class="stat-num">4+</span>
        <span class="stat-label">Certifications</span>
      </div>
    </div>
  </div>

  <!-- ── PROJECTS ── -->
  <div class="section-block animate delay-2">
    <p class="section-title">// projects</p>
    <div class="projects-grid">

      <div class="project-card">
        <span class="project-icon">🤖</span>
        <div class="project-name">StartupPro</div>
        <p class="project-desc">AI-driven startup analysis platform that predicts success probability, auto-generates SWOT analysis, 12-week roadmaps, team & funding recommendations with downloadable PDF reports.</p>
        <div class="project-stack">
          <span class="stack-pill blue">Python</span>
          <span class="stack-pill green">Streamlit</span>
          <span class="stack-pill purple">Groq API</span>
          <span class="stack-pill orange">ML</span>
          <span class="stack-pill blue">Plotly</span>
        </div>
      </div>

      <div class="project-card">
        <span class="project-icon">🌐</span>
        <div class="project-name">Personal Portfolio</div>
        <p class="project-desc">Fully responsive portfolio with light/dark mode toggle, theme color switcher, animated UI elements, interactive contact form, and deployed via GitHub Pages.</p>
        <div class="project-stack">
          <span class="stack-pill orange">HTML</span>
          <span class="stack-pill blue">CSS</span>
          <span class="stack-pill green">JavaScript</span>
        </div>
      </div>

    </div>
  </div>

  <!-- ── SKILLS ── -->
  <div class="section-block animate delay-3">
    <p class="section-title">// tech stack</p>
    <div class="skills-grid">

      <div class="card">
        <p class="skill-group-title">⚡ Programming</p>
        <div class="skill-tags">
          <span class="skill-tag">Python</span>
          <span class="skill-tag">C</span>
          <span class="skill-tag">C++</span>
          <span class="skill-tag">Java</span>
        </div>
      </div>

      <div class="card">
        <p class="skill-group-title">📊 Data & BI</p>
        <div class="skill-tags">
          <span class="skill-tag">Power BI</span>
          <span class="skill-tag">Tableau</span>
          <span class="skill-tag">Excel</span>
          <span class="skill-tag">Pandas</span>
          <span class="skill-tag">NumPy</span>
        </div>
      </div>

      <div class="card">
        <p class="skill-group-title">🌐 Web</p>
        <div class="skill-tags">
          <span class="skill-tag">HTML</span>
          <span class="skill-tag">CSS</span>
          <span class="skill-tag">JavaScript</span>
          <span class="skill-tag">React</span>
          <span class="skill-tag">Node.js</span>
          <span class="skill-tag">Express.js</span>
        </div>
      </div>

      <div class="card">
        <p class="skill-group-title">🗄️ Database & Tools</p>
        <div class="skill-tags">
          <span class="skill-tag">SQL</span>
          <span class="skill-tag">MySQL</span>
          <span class="skill-tag">Git</span>
          <span class="skill-tag">GitHub</span>
          <span class="skill-tag">VS Code</span>
        </div>
      </div>

    </div>
  </div>

  <!-- ── CODING PROFILES ── -->
  <div class="section-block animate delay-4">
    <p class="section-title">// coding profiles</p>
    <div class="profiles-grid">
      <div class="profile-card">
        <span class="profile-emoji">🏆</span>
        <div class="profile-name">SkillRack</div>
        <div class="profile-stat">700+ · 🥉 Bronze · 🥈 Silver</div>
      </div>
      <div class="profile-card">
        <span class="profile-emoji">⚔️</span>
        <div class="profile-name">LeetCode</div>
        <div class="profile-stat">200+ problems solved</div>
      </div>
      <div class="profile-card">
        <span class="profile-emoji">👨‍💻</span>
        <div class="profile-name">HackerRank</div>
        <div class="profile-stat">Python ⭐⭐⭐ · C ⭐⭐⭐ · SQL ⭐</div>
      </div>
      <div class="profile-card">
        <span class="profile-emoji">🍴</span>
        <div class="profile-name">CodeChef</div>
        <div class="profile-stat">300+ problems solved</div>
      </div>
    </div>
  </div>

  <!-- ── CERTIFICATIONS ── -->
  <div class="section-block animate delay-4">
    <p class="section-title">// certifications</p>
    <div class="certs-list">
      <div class="cert-item">
        <div class="cert-dot"></div>
        <span class="cert-name">Power BI for Data Analysis — Simplilearn × Microsoft</span>
        <span class="cert-year">2025</span>
      </div>
      <div class="cert-item">
        <div class="cert-dot"></div>
        <span class="cert-name">Python for Data Analysis: Pandas & NumPy — Coursera</span>
        <span class="cert-year">2025</span>
      </div>
      <div class="cert-item">
        <div class="cert-dot"></div>
        <span class="cert-name">Introduction to MS Excel — Simplilearn × Microsoft</span>
        <span class="cert-year">2024</span>
      </div>
      <div class="cert-item">
        <div class="cert-dot"></div>
        <span class="cert-name">Power BI Badge — Microsoft</span>
        <span class="cert-year">2024</span>
      </div>
    </div>
  </div>

  <!-- ── ACHIEVEMENTS ── -->
  <div class="section-block animate">
    <p class="section-title">// achievements</p>
    <div class="card">
      <div style="display:flex; gap:20px; flex-wrap:wrap;">
        <div style="flex:1; min-width:200px;">
          <p style="font-size:0.75rem; color:var(--muted); margin-bottom:6px;">🏅 Participant</p>
          <p style="font-size:0.9rem; font-weight:700; color:var(--text);">Createathon</p>
          <p style="font-size:0.72rem; color:var(--muted);">Inter-College Hackathon</p>
        </div>
        <div style="flex:1; min-width:200px;">
          <p style="font-size:0.75rem; color:var(--muted); margin-bottom:6px;">🏅 Participant</p>
          <p style="font-size:0.9rem; font-weight:700; color:var(--text);">Freshathon</p>
          <p style="font-size:0.72rem; color:var(--muted);">Inter-College Hackathon</p>
        </div>
        <div style="flex:1; min-width:200px;">
          <p style="font-size:0.75rem; color:var(--muted); margin-bottom:6px;">🎓 Academic</p>
          <p style="font-size:0.9rem; font-weight:700; color:var(--text);">HSC 87.5%</p>
          <p style="font-size:0.72rem; color:var(--muted);">Govt. Higher Secondary School</p>
        </div>
      </div>
    </div>
  </div>

  <!-- ── FOOTER ── -->
  <footer class="footer">
    <p class="footer-text">⚡ Made with <span>passion</span> · Currently pursuing B.Tech AI & Data Science · <span>2024–2028</span></p>
  </footer>

</div>

</body>
</html>
