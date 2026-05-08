<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Adam Elhessy — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Bebas+Neue&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #020408;
    --surface: #0a0f1a;
    --surface2: #0d1424;
    --accent-cyan: #00d9ff;
    --accent-pink: #f75c7e;
    --accent-gold: #ffd700;
    --text: #e8eaf0;
    --text-dim: #6b7a99;
    --border: rgba(0, 217, 255, 0.12);
    --glow-cyan: 0 0 30px rgba(0,217,255,0.25);
    --glow-pink: 0 0 30px rgba(247,92,126,0.25);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Inter', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,217,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,217,255,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    animation: gridMove 20s linear infinite;
    pointer-events: none;
    z-index: 0;
  }

  @keyframes gridMove {
    0% { transform: translateY(0); }
    100% { transform: translateY(60px); }
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 60px 30px;
    position: relative;
    z-index: 1;
  }

  /* ───── HERO ───── */
  .hero {
    text-align: center;
    padding: 80px 0 60px;
    position: relative;
  }

  .hero-tag {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--accent-cyan);
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-bottom: 24px;
    opacity: 0;
    animation: fadeUp 0.6s ease 0.2s forwards;
  }

  .hero-name {
    font-family: 'Bebas Neue', cursive;
    font-size: clamp(72px, 12vw, 130px);
    line-height: 0.9;
    letter-spacing: 2px;
    background: linear-gradient(135deg, #fff 0%, var(--accent-cyan) 50%, var(--accent-pink) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    opacity: 0;
    animation: fadeUp 0.7s ease 0.3s forwards;
    position: relative;
  }

  .hero-name::after {
    content: 'ADAM ELHESSY';
    position: absolute;
    inset: 0;
    font-family: 'Bebas Neue', cursive;
    font-size: clamp(72px, 12vw, 130px);
    letter-spacing: 2px;
    background: linear-gradient(135deg, transparent 0%, rgba(0,217,255,0.15) 50%, transparent 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    filter: blur(8px);
    transform: translateY(4px);
    z-index: -1;
  }

  .hero-role {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: var(--text-dim);
    margin-top: 20px;
    letter-spacing: 2px;
    opacity: 0;
    animation: fadeUp 0.7s ease 0.5s forwards;
  }

  .hero-role span {
    color: var(--accent-pink);
  }

  .hero-divider {
    width: 1px;
    height: 60px;
    background: linear-gradient(to bottom, var(--accent-cyan), transparent);
    margin: 40px auto 0;
    opacity: 0;
    animation: fadeUp 0.7s ease 0.7s forwards;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* ───── SECTION HEADER ───── */
  .section-label {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 32px;
  }

  .section-label span {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--accent-cyan);
    letter-spacing: 4px;
    text-transform: uppercase;
    white-space: nowrap;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(to right, var(--accent-cyan), transparent);
    opacity: 0.3;
  }

  /* ───── ABOUT ───── */
  .about {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 40px;
    margin-bottom: 80px;
    padding-top: 20px;
  }

  .about-text {
    font-size: 15px;
    line-height: 1.85;
    color: #9aa8c7;
    font-weight: 300;
  }

  .about-text strong {
    color: var(--text);
    font-weight: 600;
  }

  .about-stats {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .stat-card {
    border: 1px solid var(--border);
    padding: 18px 22px;
    border-radius: 2px;
    background: var(--surface);
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.3s;
    cursor: default;
  }

  .stat-card::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 2px;
    background: var(--accent-cyan);
  }

  .stat-card:nth-child(2)::before { background: var(--accent-pink); }
  .stat-card:nth-child(3)::before { background: var(--accent-gold); }

  .stat-card:hover {
    border-color: rgba(0,217,255,0.3);
    transform: translateX(4px);
  }

  .stat-card-label {
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    color: var(--text-dim);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 6px;
  }

  .stat-card-value {
    font-size: 15px;
    font-weight: 600;
    color: var(--text);
    letter-spacing: 0.5px;
  }

  /* ───── SKILLS ───── */
  .skills-section {
    margin-bottom: 80px;
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 2px;
  }

  .skill-item {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 28px 20px;
    text-align: center;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
    cursor: default;
  }

  .skill-item::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 1px;
    background: var(--accent-cyan);
    transform: scaleX(0);
    transition: transform 0.3s;
  }

  .skill-item:hover {
    background: var(--surface2);
    border-color: rgba(0,217,255,0.25);
    box-shadow: var(--glow-cyan);
  }

  .skill-item:hover::after { transform: scaleX(1); }

  .skill-icon {
    font-size: 28px;
    margin-bottom: 12px;
    display: block;
    filter: grayscale(0.2);
    transition: filter 0.3s, transform 0.3s;
  }

  .skill-item:hover .skill-icon {
    filter: grayscale(0);
    transform: scale(1.1);
  }

  .skill-name {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--text-dim);
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  .skill-level {
    margin-top: 10px;
    height: 2px;
    background: rgba(255,255,255,0.05);
    border-radius: 1px;
    overflow: hidden;
  }

  .skill-fill {
    height: 100%;
    border-radius: 1px;
    background: linear-gradient(90deg, var(--accent-cyan), var(--accent-pink));
    animation: fillBar 1.5s ease forwards;
    transform-origin: left;
    transform: scaleX(0);
  }

  @keyframes fillBar {
    to { transform: scaleX(1); }
  }

  /* ───── TERMINAL BIO ───── */
  .terminal {
    background: #010810;
    border: 1px solid var(--border);
    border-radius: 4px;
    margin-bottom: 80px;
    overflow: hidden;
  }

  .terminal-bar {
    background: #0d1424;
    padding: 12px 18px;
    display: flex;
    align-items: center;
    gap: 8px;
    border-bottom: 1px solid var(--border);
  }

  .dot {
    width: 10px; height: 10px;
    border-radius: 50%;
  }
  .dot-red { background: #ff5f57; }
  .dot-yellow { background: #febc2e; }
  .dot-green { background: #28c840; }

  .terminal-title {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--text-dim);
    margin-left: 8px;
    letter-spacing: 1px;
  }

  .terminal-body {
    padding: 28px;
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    line-height: 2;
  }

  .t-prompt { color: var(--accent-cyan); }
  .t-cmd { color: var(--text); }
  .t-comment { color: #3d5a80; }
  .t-key { color: var(--accent-pink); }
  .t-val { color: #a8ff78; }
  .t-string { color: #ffd700; }
  .t-cursor {
    display: inline-block;
    width: 8px; height: 14px;
    background: var(--accent-cyan);
    vertical-align: middle;
    animation: blink 1s step-end infinite;
  }
  @keyframes blink { 50% { opacity: 0; } }

  /* ───── CONNECT ───── */
  .connect-section {
    margin-bottom: 60px;
  }

  .connect-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .connect-card {
    display: flex;
    align-items: center;
    gap: 20px;
    padding: 24px 28px;
    border: 1px solid var(--border);
    background: var(--surface);
    text-decoration: none;
    color: var(--text);
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }

  .connect-card::before {
    content: '';
    position: absolute;
    inset: 0;
    opacity: 0;
    transition: opacity 0.3s;
  }

  .connect-card.linkedin::before {
    background: linear-gradient(135deg, rgba(0,119,181,0.1), transparent);
  }

  .connect-card.gmail::before {
    background: linear-gradient(135deg, rgba(234,67,53,0.1), transparent);
  }

  .connect-card:hover {
    border-color: rgba(0,217,255,0.3);
    transform: translateY(-2px);
    box-shadow: 0 8px 40px rgba(0,0,0,0.4);
  }

  .connect-card:hover::before { opacity: 1; }

  .connect-icon {
    width: 44px; height: 44px;
    border-radius: 2px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    flex-shrink: 0;
  }

  .linkedin .connect-icon { background: rgba(0,119,181,0.15); color: #0077b5; }
  .gmail .connect-icon { background: rgba(234,67,53,0.15); color: #ea4335; }

  .connect-label {
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    color: var(--text-dim);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 4px;
  }

  .connect-value {
    font-size: 14px;
    font-weight: 500;
  }

  .connect-arrow {
    margin-left: auto;
    color: var(--text-dim);
    font-size: 18px;
    transition: transform 0.3s, color 0.3s;
  }

  .connect-card:hover .connect-arrow {
    transform: translateX(4px);
    color: var(--accent-cyan);
  }

  /* ───── FOOTER ───── */
  .footer {
    text-align: center;
    padding: 40px 0;
    border-top: 1px solid var(--border);
  }

  .footer-quote {
    font-size: 13px;
    color: var(--text-dim);
    font-style: italic;
    letter-spacing: 0.5px;
  }

  .footer-quote strong {
    color: var(--accent-cyan);
    font-style: normal;
  }

  .footer-sig {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: rgba(255,255,255,0.1);
    letter-spacing: 3px;
    margin-top: 16px;
    text-transform: uppercase;
  }

  /* ───── SCANLINE ───── */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.03) 2px,
      rgba(0,0,0,0.03) 4px
    );
    pointer-events: none;
    z-index: 9999;
  }

  @media (max-width: 640px) {
    .about { grid-template-columns: 1fr; }
    .connect-grid { grid-template-columns: 1fr; }
    .skills-grid { grid-template-columns: repeat(2, 1fr); }
  }
</style>
</head>
<body>

<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-tag">// Software Developer &amp; Systems Engineer</div>
    <div class="hero-name">Adam Elhessy</div>
    <div class="hero-role">
      <span>C++</span> · Git &amp; GitHub · <span>Technical Documentation</span>
    </div>
    <div class="hero-divider"></div>
  </div>

  <!-- ABOUT -->
  <div class="about">
    <div>
      <div class="section-label"><span>01 — About</span></div>
      <p class="about-text">
        Highly motivated <strong>C++ Developer</strong> with a deep passion for building efficient systems and exploring new technologies. I specialize in software development lifecycles and thrive in environments where <strong>Git and GitHub</strong> are the heart of collaboration.
        <br><br>
        Beyond code, I'm an expert in technical documentation via <strong>Microsoft Word</strong> — translating high-level logic into clear, professional guides. Dedicated learner. Team player. Always chasing the next challenge.
      </p>
    </div>
    <div class="about-stats">
      <div class="stat-card">
        <div class="stat-card-label">Primary Language</div>
        <div class="stat-card-value">C++ / Systems Programming</div>
      </div>
      <div class="stat-card">
        <div class="stat-card-label">Version Control</div>
        <div class="stat-card-value">Git &amp; GitHub — Expert</div>
      </div>
      <div class="stat-card">
        <div class="stat-card-label">Documentation</div>
        <div class="stat-card-value">Microsoft Word — Expert Level</div>
      </div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="skills-section">
    <div class="section-label"><span>02 — Stack</span></div>
    <div class="skills-grid">
      <div class="skill-item">
        <span class="skill-icon">⚡</span>
        <div class="skill-name">C++</div>
        <div class="skill-level"><div class="skill-fill" style="animation-delay:0.1s"></div></div>
      </div>
      <div class="skill-item">
        <span class="skill-icon">🌿</span>
        <div class="skill-name">Git</div>
        <div class="skill-level"><div class="skill-fill" style="animation-delay:0.2s"></div></div>
      </div>
      <div class="skill-item">
        <span class="skill-icon">🐙</span>
        <div class="skill-name">GitHub</div>
        <div class="skill-level"><div class="skill-fill" style="animation-delay:0.3s"></div></div>
      </div>
      <div class="skill-item">
        <span class="skill-icon">🛠️</span>
        <div class="skill-name">Visual Studio</div>
        <div class="skill-level"><div class="skill-fill" style="animation-delay:0.4s"></div></div>
      </div>
      <div class="skill-item">
        <span class="skill-icon">💻</span>
        <div class="skill-name">VS Code</div>
        <div class="skill-level"><div class="skill-fill" style="animation-delay:0.5s"></div></div>
      </div>
      <div class="skill-item">
        <span class="skill-icon">📄</span>
        <div class="skill-name">MS Word</div>
        <div class="skill-level"><div class="skill-fill" style="animation-delay:0.6s"></div></div>
      </div>
    </div>
  </div>

  <!-- TERMINAL -->
  <div class="terminal">
    <div class="terminal-bar">
      <div class="dot dot-red"></div>
      <div class="dot dot-yellow"></div>
      <div class="dot dot-green"></div>
      <div class="terminal-title">adam@elhessy ~ bash</div>
    </div>
    <div class="terminal-body">
      <div><span class="t-prompt">➜ adam </span><span class="t-cmd">cat profile.json</span></div>
      <div><span class="t-comment"># ──────────────────────────</span></div>
      <div>{</div>
      <div>&nbsp;&nbsp;<span class="t-key">"name"</span>: <span class="t-string">"Adam Elhessy"</span>,</div>
      <div>&nbsp;&nbsp;<span class="t-key">"role"</span>: <span class="t-string">"C++ Developer"</span>,</div>
      <div>&nbsp;&nbsp;<span class="t-key">"passion"</span>: <span class="t-string">"Efficient Systems &amp; New Tech"</span>,</div>
      <div>&nbsp;&nbsp;<span class="t-key">"strengths"</span>: [<span class="t-string">"Git"</span>, <span class="t-string">"GitHub"</span>, <span class="t-string">"Documentation"</span>],</div>
      <div>&nbsp;&nbsp;<span class="t-key">"mindset"</span>: <span class="t-string">"Always learning. Always building."</span>,</div>
      <div>&nbsp;&nbsp;<span class="t-key">"status"</span>: <span class="t-val">OPEN_TO_OPPORTUNITIES</span></div>
      <div>}</div>
      <div><span class="t-prompt">➜ adam </span><span class="t-cursor"></span></div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="connect-section">
    <div class="section-label"><span>03 — Connect</span></div>
    <div class="connect-grid">
      <a href="https://www.linkedin.com/in/adam-elhessy-818686384/" target="_blank" class="connect-card linkedin">
        <div class="connect-icon">in</div>
        <div>
          <div class="connect-label">LinkedIn</div>
          <div class="connect-value">Adam Elhessy</div>
        </div>
        <div class="connect-arrow">→</div>
      </a>
      <a href="mailto:adam.elhessy2007@gmail.com" class="connect-card gmail">
        <div class="connect-icon">✉</div>
        <div>
          <div class="connect-label">Email</div>
          <div class="connect-value">adam.elhessy2007@gmail.com</div>
        </div>
        <div class="connect-arrow">→</div>
      </a>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="footer-quote">
      "The best code is not the cleverest — it's the most <strong>intentional</strong>."
    </div>
    <div class="footer-sig">© Adam Elhessy · Built with precision</div>
  </div>

</div>

</body>
</html>
