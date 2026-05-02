<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Animesh Kumar — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #070d19;
    --bg2: #0d1526;
    --bg3: #121f35;
    --accent: #00e5a0;
    --accent2: #00b8ff;
    --accent3: #7b61ff;
    --text: #e8f0ff;
    --muted: #7a8ca8;
    --border: rgba(0,229,160,0.15);
    --card-bg: rgba(13,21,38,0.85);
    --font-head: 'Syne', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-head);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── Animated grid background ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,160,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,160,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 2.5rem 1.5rem 4rem;
    position: relative;
    z-index: 1;
  }

  /* ── Fade-up animation keyframes ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(28px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes glitch1 {
    0%,100% { clip-path: inset(80% 0 0 0); transform: translate(-3px,0); }
    25%      { clip-path: inset(10% 0 70% 0); transform: translate(3px,0); }
    50%      { clip-path: inset(40% 0 40% 0); transform: translate(-2px,0); }
    75%      { clip-path: inset(60% 0 20% 0); transform: translate(2px,0); }
  }
  @keyframes glitch2 {
    0%,100% { clip-path: inset(0 0 90% 0); transform: translate(3px,0); }
    33%      { clip-path: inset(50% 0 30% 0); transform: translate(-3px,0); }
    66%      { clip-path: inset(20% 0 60% 0); transform: translate(2px,0); }
  }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }
  @keyframes scanline {
    0%   { transform: translateY(-100%); }
    100% { transform: translateY(100vh); }
  }
  @keyframes pulse {
    0%,100% { box-shadow: 0 0 0 0 rgba(0,229,160,0.4); }
    50%      { box-shadow: 0 0 0 8px rgba(0,229,160,0); }
  }
  @keyframes float {
    0%,100% { transform: translateY(0); }
    50%      { transform: translateY(-6px); }
  }
  @keyframes shimmer {
    0%   { background-position: -400px 0; }
    100% { background-position: 400px 0; }
  }
  @keyframes borderFlow {
    0%   { background-position: 0% 50%; }
    50%  { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }
  @keyframes typing {
    from { width: 0; }
    to   { width: 100%; }
  }
  @keyframes orbit {
    from { transform: rotate(0deg) translateX(22px) rotate(0deg); }
    to   { transform: rotate(360deg) translateX(22px) rotate(-360deg); }
  }
  @keyframes countUp {
    from { opacity:0; transform:scale(.8); }
    to   { opacity:1; transform:scale(1); }
  }
  @keyframes rotateGlow {
    0%   { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
  }

  /* ── HERO SECTION ── */
  .hero { text-align: center; padding: 2rem 0 1rem; animation: fadeUp .8s ease both; }

  .avatar-wrap {
    position: relative;
    display: inline-block;
    margin-bottom: 1.5rem;
    animation: float 4s ease-in-out infinite;
  }
  .avatar-ring {
    position: absolute; inset: -6px;
    border-radius: 50%;
    background: conic-gradient(var(--accent), var(--accent2), var(--accent3), var(--accent));
    animation: rotateGlow 3s linear infinite;
    z-index: 0;
  }
  .avatar-ring::before {
    content: '';
    position: absolute; inset: 4px;
    border-radius: 50%;
    background: var(--bg);
  }
  .avatar {
    position: relative;
    width: 110px; height: 110px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--bg3) 0%, #1a2a4a 100%);
    display: flex; align-items: center; justify-content: center;
    font-size: 3rem;
    z-index: 1;
    border: 2px solid var(--bg);
  }

  .hero-name {
    font-size: clamp(2rem, 5vw, 3rem);
    font-weight: 800;
    letter-spacing: -0.03em;
    line-height: 1.1;
    position: relative;
    display: inline-block;
  }
  .hero-name .glitch-wrap { position: relative; }
  .hero-name .glitch-wrap::before,
  .hero-name .glitch-wrap::after {
    content: attr(data-text);
    position: absolute; inset: 0;
    background: var(--bg);
  }
  .hero-name .glitch-wrap::before {
    color: var(--accent2);
    animation: glitch1 4s infinite linear;
    opacity: .6;
  }
  .hero-name .glitch-wrap::after {
    color: var(--accent3);
    animation: glitch2 4s infinite linear;
    opacity: .6;
  }
  .accent-text {
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-sub {
    color: var(--muted);
    font-family: var(--font-mono);
    font-size: .85rem;
    margin-top: .5rem;
    letter-spacing: .04em;
  }
  .hero-sub span { color: var(--accent); }

  /* Typing line */
  .typing-bar {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 999px;
    padding: .4rem 1rem;
    margin-top: 1rem;
    font-family: var(--font-mono);
    font-size: .8rem;
    color: var(--accent);
  }
  .typing-bar .prompt { color: var(--muted); }
  .cursor { display: inline-block; width: 2px; height: 1em; background: var(--accent); animation: blink 1s step-end infinite; vertical-align: middle; }

  /* ── SECTION LABEL ── */
  .section-label {
    display: flex; align-items: center; gap: 10px;
    font-family: var(--font-mono);
    font-size: .7rem;
    color: var(--accent);
    letter-spacing: .12em;
    text-transform: uppercase;
    margin-bottom: 1.2rem;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  /* ── GLASS CARD ── */
  .glass-card {
    background: var(--card-bg);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 1.5rem;
    position: relative;
    overflow: hidden;
    transition: border-color .3s, transform .3s;
  }
  .glass-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--accent), transparent);
    opacity: .5;
  }
  .glass-card:hover { border-color: rgba(0,229,160,.35); transform: translateY(-2px); }

  /* ── ABOUT SECTION ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }
  @media (max-width: 560px) { .about-grid { grid-template-columns: 1fr; } }

  .about-item {
    display: flex; align-items: flex-start; gap: 12px;
    background: var(--bg3);
    border: 1px solid rgba(255,255,255,.05);
    border-radius: 12px;
    padding: .9rem 1rem;
    animation: fadeUp .6s ease both;
    transition: border-color .3s, background .3s;
  }
  .about-item:hover { border-color: var(--border); background: rgba(0,229,160,.04); }

  .about-icon {
    font-size: 1.2rem;
    min-width: 30px;
    text-align: center;
    margin-top: 1px;
  }
  .about-item p {
    font-family: var(--font-mono);
    font-size: .78rem;
    line-height: 1.6;
    color: var(--muted);
  }
  .about-item p strong { color: var(--text); font-weight: 600; }
  .about-item p a { color: var(--accent); text-decoration: none; }
  .about-item p a:hover { text-decoration: underline; }

  /* ── CONNECT ── */
  .connect-grid {
    display: flex; flex-wrap: wrap; gap: 12px;
  }
  .social-btn {
    display: flex; align-items: center; gap: 10px;
    background: var(--bg3);
    border: 1px solid rgba(255,255,255,.07);
    border-radius: 10px;
    padding: .7rem 1.1rem;
    text-decoration: none;
    color: var(--text);
    font-family: var(--font-mono);
    font-size: .78rem;
    font-weight: 600;
    letter-spacing: .04em;
    transition: all .3s;
    position: relative;
    overflow: hidden;
  }
  .social-btn::after {
    content: '';
    position: absolute; inset: 0;
    background: linear-gradient(135deg, transparent 0%, rgba(255,255,255,.03) 100%);
    opacity: 0;
    transition: opacity .3s;
  }
  .social-btn:hover::after { opacity: 1; }
  .social-btn:hover { transform: translateY(-3px); }

  .social-btn.linkedin:hover { border-color: #0077b5; color: #0096dd; box-shadow: 0 6px 20px rgba(0,119,181,.2); }
  .social-btn.leetcode:hover { border-color: #ffa116; color: #ffa116; box-shadow: 0 6px 20px rgba(255,161,22,.2); }
  .social-btn.gfg:hover     { border-color: #2f8d46; color: #4caf50; box-shadow: 0 6px 20px rgba(47,141,70,.2); }
  .social-btn.insta:hover   { border-color: #e1306c; color: #e1306c; box-shadow: 0 6px 20px rgba(225,48,108,.2); }

  .social-icon { font-size: 1.1rem; }

  /* LinkedIn SVG */
  .svg-icon { width: 20px; height: 20px; flex-shrink: 0; }

  /* ── SKILLS ── */
  .skills-grid {
    display: flex; flex-wrap: wrap; gap: 8px;
  }
  .skill-chip {
    display: flex; align-items: center; gap: 6px;
    background: var(--bg3);
    border: 1px solid rgba(255,255,255,.06);
    border-radius: 8px;
    padding: .5rem .9rem;
    font-family: var(--font-mono);
    font-size: .75rem;
    color: var(--muted);
    transition: all .25s;
    animation: fadeUp .5s ease both;
  }
  .skill-chip:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(0,229,160,.06);
    transform: translateY(-2px) scale(1.03);
  }
  .skill-chip .dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: currentColor;
    opacity: .6;
  }

  /* ── STATS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }
  @media (max-width: 560px) { .stats-grid { grid-template-columns: 1fr; } }

  .stat-img {
    width: 100%; border-radius: 12px;
    border: 1px solid var(--border);
    display: block;
    transition: transform .3s, box-shadow .3s;
  }
  .stat-img:hover {
    transform: translateY(-3px);
    box-shadow: 0 12px 40px rgba(0,229,160,.12);
  }
  .stat-full {
    grid-column: 1 / -1;
  }

  /* ── QUOTE ── */
  .quote-block {
    text-align: center;
    padding: 2rem 1.5rem;
    position: relative;
  }
  .quote-block::before {
    content: '"';
    position: absolute;
    top: -10px; left: 50%; transform: translateX(-50%);
    font-size: 5rem;
    color: rgba(0,229,160,.08);
    font-family: Georgia, serif;
    line-height: 1;
  }
  .quote-text {
    font-family: var(--font-mono);
    font-size: .95rem;
    color: var(--muted);
    letter-spacing: .02em;
  }
  .quote-text span { color: var(--accent); }

  /* ── VISITOR BADGE ── */
  .footer-row {
    display: flex; justify-content: center; align-items: center;
    gap: 12px; flex-wrap: wrap;
    margin-top: 1rem;
  }
  .badge {
    font-family: var(--font-mono);
    font-size: .68rem;
    color: var(--muted);
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 999px;
    padding: .3rem .8rem;
    letter-spacing: .05em;
  }
  .badge span { color: var(--accent); }

  /* ── SECTION SPACING ── */
  .section { margin-bottom: 2.2rem; animation: fadeUp .7s ease both; }
  .section:nth-child(1) { animation-delay: .05s; }
  .section:nth-child(2) { animation-delay: .15s; }
  .section:nth-child(3) { animation-delay: .25s; }
  .section:nth-child(4) { animation-delay: .35s; }
  .section:nth-child(5) { animation-delay: .45s; }
  .section:nth-child(6) { animation-delay: .55s; }

  .about-item:nth-child(1) { animation-delay: .2s; }
  .about-item:nth-child(2) { animation-delay: .28s; }
  .about-item:nth-child(3) { animation-delay: .36s; }
  .about-item:nth-child(4) { animation-delay: .44s; }
  .about-item:nth-child(5) { animation-delay: .52s; }
  .about-item:nth-child(6) { animation-delay: .60s; }

  .skill-chip:nth-child(1) { animation-delay: .1s; }
  .skill-chip:nth-child(2) { animation-delay: .15s; }
  .skill-chip:nth-child(3) { animation-delay: .2s; }
  .skill-chip:nth-child(4) { animation-delay: .25s; }
  .skill-chip:nth-child(5) { animation-delay: .3s; }

  /* Scanline effect */
  .scanline {
    position: fixed; top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(transparent, rgba(0,229,160,.06), transparent);
    animation: scanline 8s linear infinite;
    pointer-events: none;
    z-index: 999;
  }

  /* ── STATUS DOT ── */
  .status-dot {
    display: inline-block;
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--accent);
    animation: pulse 2s ease-in-out infinite;
    vertical-align: middle;
    margin-right: 4px;
  }
</style>
</head>
<body>

<div class="scanline"></div>

<div class="container">

  <!-- ── HERO ── -->
  <div class="hero">
    <div class="avatar-wrap">
      <div class="avatar-ring"></div>
      <div class="avatar">👨‍💻</div>
    </div>
    <h1 class="hero-name">
      Hi, I'm&nbsp;<span class="glitch-wrap accent-text" data-text="Animesh Kumar">Animesh Kumar</span>
    </h1>
    <p class="hero-sub">
      <span>NIT Srinagar</span> · B.Tech Information Technology
    </p>
    <div style="margin-top:1rem;">
      <div class="typing-bar" id="typingBar">
        <span class="prompt">~/dev $&nbsp;</span>
        <span id="typedText"></span>
        <span class="cursor"></span>
      </div>
    </div>
  </div>

  <!-- ── ABOUT ── -->
  <div class="section">
    <div class="section-label">// about me</div>
    <div class="glass-card">
      <div class="about-grid">
        <div class="about-item">
          <span class="about-icon">🎓</span>
          <p><strong>B.Tech IT Student</strong><br>National Institute of Technology, Srinagar J&K</p>
        </div>
        <div class="about-item">
          <span class="about-icon">🌱</span>
          <p>Currently mastering <strong>Data Structures &amp; Algorithms</strong> in Java</p>
        </div>
        <div class="about-item">
          <span class="about-icon">💬</span>
          <p>Ask me about <strong>DSA, Problem Solving &amp; Java</strong></p>
        </div>
        <div class="about-item">
          <span class="about-icon">📫</span>
          <p>Reach me at<br><a href="mailto:rajuranjanxbkj@gmail.com">rajuranjanxbkj@gmail.com</a></p>
        </div>
        <div class="about-item">
          <span class="about-icon">⚡</span>
          <p>Passionate about writing <strong>clean &amp; optimized</strong> code</p>
        </div>
        <div class="about-item">
          <span class="about-icon">🔍</span>
          <p><span class="status-dot"></span><strong>Open</strong> to internships &amp; collaborations</p>
        </div>
      </div>
    </div>
  </div>

  <!-- ── CONNECT ── -->
  <div class="section">
    <div class="section-label">// connect with me</div>
    <div class="glass-card">
      <div class="connect-grid">

        <a href="https://linkedin.com/in/animesh-kumar-771b60228" target="_blank" class="social-btn linkedin">
          <svg class="svg-icon" viewBox="0 0 24 24" fill="currentColor">
            <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
          </svg>
          LinkedIn
        </a>

        <a href="https://www.leetcode.com/annimesh_nits" target="_blank" class="social-btn leetcode">
          <svg class="svg-icon" viewBox="0 0 24 24" fill="currentColor">
            <path d="M13.483 0a1.374 1.374 0 0 0-.961.438L7.116 6.226l-3.854 4.126a5.266 5.266 0 0 0-1.209 2.104 5.35 5.35 0 0 0-.125.513 5.527 5.527 0 0 0 .062 2.362 5.83 5.83 0 0 0 .349 1.017 5.938 5.938 0 0 0 1.271 1.818l4.277 4.193.039.038c2.248 2.165 5.852 2.133 8.063-.074l2.396-2.392c.54-.54.54-1.414.003-1.955a1.378 1.378 0 0 0-1.951-.003l-2.396 2.392a3.021 3.021 0 0 1-4.205.038l-.02-.019-4.276-4.193c-.652-.64-.972-1.469-.948-2.263a2.68 2.68 0 0 1 .066-.523 2.545 2.545 0 0 1 .619-1.164L9.13 8.114c1.058-1.134 3.204-1.27 4.43-.278l3.501 2.831c.593.48 1.461.387 1.94-.207a1.384 1.384 0 0 0-.207-1.943l-3.5-2.831c-.8-.647-1.766-1.045-2.774-1.202l2.015-2.158A1.384 1.384 0 0 0 13.483 0zm-2.866 12.815a1.38 1.38 0 0 0-1.38 1.382 1.38 1.38 0 0 0 1.38 1.382H20.79a1.38 1.38 0 0 0 1.38-1.382 1.38 1.38 0 0 0-1.38-1.382z"/>
          </svg>
          LeetCode
        </a>

        <a href="https://www.geeksforgeeks.org/profile/annimeshkumar" target="_blank" class="social-btn gfg">
          <svg class="svg-icon" viewBox="0 0 24 24" fill="currentColor">
            <path d="M21.45 14.315c-.143.28-.334.532-.565.745a3.691 3.691 0 0 1-1.104.695c-.434.168-.9.254-1.37.254h-1.7v-1.96h1.7c.34 0 .67-.1.96-.29.28-.19.5-.46.63-.77.13-.31.16-.65.09-.98a1.72 1.72 0 0 0-.46-.87 1.69 1.69 0 0 0-.86-.48 1.7 1.7 0 0 0-.98.09 1.69 1.69 0 0 0-.77.63c-.19.29-.29.62-.29.96v.83H15.3v-.83c0-.47.086-.93.254-1.37a3.691 3.691 0 0 1 .695-1.104c.294-.3.64-.54 1.02-.7.39-.17.81-.25 1.23-.25.42 0 .84.08 1.23.25.38.16.724.4 1.02.7.294.3.526.66.68 1.06.155.4.22.83.19 1.26a3.6 3.6 0 0 1-.17.97zM8.7 14.315c.143.28.334.532.565.745.303.278.66.49 1.104.695.434.168.9.254 1.37.254h1.7v-1.96h-1.7c-.34 0-.67-.1-.96-.29a1.69 1.69 0 0 1-.63-.77 1.72 1.72 0 0 1-.09-.98c.09-.33.26-.63.46-.87.21-.24.47-.42.86-.48.39-.07.77-.01 1.1.18.31.19.58.47.77.81v.83h1.7v-.83c0-.47-.086-.93-.254-1.37a3.691 3.691 0 0 0-.695-1.104 3.691 3.691 0 0 0-1.02-.7 3.6 3.6 0 0 0-1.23-.25c-.42 0-.84.08-1.23.25-.38.16-.724.4-1.02.7-.294.3-.526.66-.68 1.06-.155.4-.22.83-.19 1.26.03.33.1.65.22.97zM12 2C6.477 2 2 6.477 2 12s4.477 10 10 10 10-4.477 10-10S17.523 2 12 2zm0 18c-4.418 0-8-3.582-8-8s3.582-8 8-8 8 3.582 8 8-3.582 8-8 8z"/>
          </svg>
          GeeksForGeeks
        </a>

        <a href="https://www.instagram.com/annimesh.kumar/" target="_blank" class="social-btn insta">
          <svg class="svg-icon" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 1 0 0 12.324 6.162 6.162 0 0 0 0-12.324zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.406-11.845a1.44 1.44 0 1 0 0 2.881 1.44 1.44 0 0 0 0-2.881z"/>
          </svg>
          Instagram
        </a>

        <a href="mailto:rajuranjanxbkj@gmail.com" class="social-btn" style="border-color:rgba(234,67,53,.3);" onmouseover="this.style.borderColor='#ea4335';this.style.color='#ea4335';this.style.boxShadow='0 6px 20px rgba(234,67,53,.2)'" onmouseout="this.style.borderColor='rgba(234,67,53,.3)';this.style.color='';this.style.boxShadow=''">
          <svg class="svg-icon" viewBox="0 0 24 24" fill="currentColor">
            <path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/>
          </svg>
          Email
        </a>

      </div>
    </div>
  </div>

  <!-- ── SKILLS ── -->
  <div class="section">
    <div class="section-label">// languages &amp; tools</div>
    <div class="glass-card">
      <div class="skills-grid">
        <div class="skill-chip"><span class="dot"></span>Java</div>
        <div class="skill-chip"><span class="dot"></span>Data Structures</div>
        <div class="skill-chip"><span class="dot"></span>Algorithms</div>
        <div class="skill-chip"><span class="dot"></span>Git</div>
        <div class="skill-chip"><span class="dot"></span>GitHub</div>
        <div class="skill-chip"><span class="dot"></span>VS Code</div>
        <div class="skill-chip"><span class="dot"></span>IntelliJ IDEA</div>
        <div class="skill-chip"><span class="dot"></span>Problem Solving</div>
        <div class="skill-chip"><span class="dot"></span>OOP</div>
        <div class="skill-chip"><span class="dot"></span>Competitive Programming</div>
      </div>
    </div>
  </div>

  <!-- ── GITHUB STATS ── -->
  <div class="section">
    <div class="section-label">// github stats</div>
    <div class="stats-grid">
      <img class="stat-img"
        src="https://github-readme-stats.vercel.app/api?username=animeshx45&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=00e5a0&icon_color=00b8ff&text_color=e8f0ff"
        alt="Animesh GitHub Stats" loading="lazy" />
      <img class="stat-img"
        src="https://github-readme-streak-stats.herokuapp.com/?user=animeshx45&theme=tokyonight&hide_border=true&background=0D1117&ring=00e5a0&fire=00b8ff&currStreakLabel=00e5a0"
        alt="Animesh GitHub Streak" loading="lazy" />
      <img class="stat-img stat-full"
        src="https://github-readme-stats.vercel.app/api/top-langs/?username=animeshx45&layout=compact&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=00e5a0&text_color=e8f0ff"
        alt="Top Languages" loading="lazy" />
    </div>
  </div>

  <!-- ── QUOTE ── -->
  <div class="section">
    <div class="glass-card quote-block">
      <p class="quote-text">
        <span>"</span>First, solve the problem. Then, write the code.<span>"</span>
      </p>
      <p style="font-family:var(--font-mono);font-size:.68rem;color:var(--muted);margin-top:.6rem;letter-spacing:.08em;">— John Johnson</p>
    </div>
  </div>

  <!-- ── FOOTER ── -->
  <div class="footer-row">
    <span class="badge">Made with <span>♥</span> by Animesh</span>
    <img src="https://komarev.com/ghpvc/?username=animeshx45&style=flat-square&color=00e5a0&label=Profile+Views" alt="Profile Views" style="border-radius:999px;height:22px;" />
  </div>

</div>

<script>
  // Typing animation
  const phrases = [
    'DSA Enthusiast 🧩',
    'Java Developer ☕',
    'Problem Solver 🔍',
    'Future SWE 🚀',
    'NIT Srinagar 🎓'
  ];
  let pi = 0, ci = 0, deleting = false;
  const el = document.getElementById('typedText');

  function type() {
    const word = phrases[pi];
    if (!deleting) {
      el.textContent = word.slice(0, ++ci);
      if (ci === word.length) { deleting = true; setTimeout(type, 1800); return; }
    } else {
      el.textContent = word.slice(0, --ci);
      if (ci === 0) { deleting = false; pi = (pi + 1) % phrases.length; }
    }
    setTimeout(type, deleting ? 55 : 90);
  }
  setTimeout(type, 700);

  // Staggered scroll reveals
  const obs = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) { e.target.style.opacity = '1'; e.target.style.transform = 'translateY(0)'; }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.about-item, .skill-chip, .social-btn').forEach((el, i) => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(20px)';
    el.style.transition = `opacity .5s ease ${i * 0.06}s, transform .5s ease ${i * 0.06}s, border-color .3s, background .3s, box-shadow .3s, color .3s`;
    obs.observe(el);
  });
</script>
</body>
</html>
