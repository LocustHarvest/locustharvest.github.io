# Locust Harvest: From Plagues To Profit
"From Plagues to Profit — Amplifying Stories That Inspire the World."
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Locust Harvest — From Plagues to Profit</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Barlow+Condensed:wght@300;400;500;600;700&family=Barlow:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --gold: #C9A84C;
    --gold-light: #E8C97A;
    --gold-dim: #7A6330;
    --black: #0A0804;
    --dark: #110E07;
    --dark2: #1A1610;
    --dark3: #241F14;
    --stone: #2E2820;
    --ash: #6B6358;
    --mist: #AFA89E;
    --cream: #F0EBE0;
    --white: #FAF8F3;
    --red-ember: #8B2E0A;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--cream);
    font-family: 'Barlow', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
    cursor: default;
  }

  /* ── GRAIN OVERLAY ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 9999;
    opacity: 0.35;
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.5rem 4rem;
    background: linear-gradient(to bottom, rgba(10,8,4,0.95) 0%, transparent 100%);
    transition: background 0.4s;
  }

  nav.scrolled {
    background: rgba(10,8,4,0.97);
    border-bottom: 1px solid rgba(201,168,76,0.15);
  }

  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-weight: 900;
    font-size: 1.25rem;
    letter-spacing: 0.08em;
    color: var(--gold);
    text-decoration: none;
  }

  .nav-logo span {
    color: var(--cream);
    font-style: italic;
    font-weight: 400;
  }

  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }

  .nav-links a {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 500;
    font-size: 0.8rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--mist);
    text-decoration: none;
    transition: color 0.3s;
  }

  .nav-links a:hover { color: var(--gold); }

  /* ── HERO ── */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 0 4rem 6rem;
    overflow: hidden;
  }

  .hero-bg {
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 80% 60% at 70% 40%, rgba(201,168,76,0.06) 0%, transparent 60%),
      radial-gradient(ellipse 50% 80% at 20% 80%, rgba(139,46,10,0.08) 0%, transparent 50%),
      linear-gradient(175deg, #0A0804 0%, #1A1208 50%, #0D0B06 100%);
  }

  /* Locust silhouette pattern */
  .hero-bg::after {
    content: '';
    position: absolute;
    inset: 0;
    background-image:
      radial-gradient(1px 1px at 15% 25%, rgba(201,168,76,0.4) 0%, transparent 100%),
      radial-gradient(1px 1px at 42% 18%, rgba(201,168,76,0.3) 0%, transparent 100%),
      radial-gradient(1px 1px at 68% 35%, rgba(201,168,76,0.2) 0%, transparent 100%),
      radial-gradient(1px 1px at 85% 22%, rgba(201,168,76,0.35) 0%, transparent 100%),
      radial-gradient(1px 1px at 30% 60%, rgba(201,168,76,0.2) 0%, transparent 100%),
      radial-gradient(1px 1px at 55% 70%, rgba(201,168,76,0.15) 0%, transparent 100%);
    pointer-events: none;
  }

  .hero-eyebrow {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 500;
    font-size: 0.72rem;
    letter-spacing: 0.35em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1.5rem;
    opacity: 0;
    animation: fadeUp 1s 0.3s forwards;
  }

  .hero-title {
    font-family: 'Playfair Display', serif;
    font-weight: 900;
    font-size: clamp(4rem, 10vw, 9rem);
    line-height: 0.92;
    letter-spacing: -0.02em;
    color: var(--white);
    margin-bottom: 0.3em;
    opacity: 0;
    animation: fadeUp 1s 0.5s forwards;
  }

  .hero-title em {
    font-style: italic;
    color: var(--gold);
    display: block;
  }

  .hero-sub {
    font-family: 'Barlow', sans-serif;
    font-weight: 300;
    font-size: clamp(1rem, 2vw, 1.3rem);
    color: var(--mist);
    max-width: 520px;
    line-height: 1.6;
    margin-bottom: 3rem;
    opacity: 0;
    animation: fadeUp 1s 0.7s forwards;
  }

  .hero-actions {
    display: flex;
    gap: 1.5rem;
    align-items: center;
    opacity: 0;
    animation: fadeUp 1s 0.9s forwards;
  }

  .btn-primary {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 600;
    font-size: 0.78rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    background: var(--gold);
    color: var(--black);
    border: none;
    padding: 1rem 2.5rem;
    cursor: pointer;
    text-decoration: none;
    display: inline-block;
    transition: background 0.3s, transform 0.2s;
  }

  .btn-primary:hover {
    background: var(--gold-light);
    transform: translateY(-2px);
  }

  .btn-ghost {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 500;
    font-size: 0.78rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--mist);
    text-decoration: none;
    border-bottom: 1px solid var(--stone);
    padding-bottom: 2px;
    transition: color 0.3s, border-color 0.3s;
  }

  .btn-ghost:hover { color: var(--gold); border-color: var(--gold); }

  .hero-scroll-line {
    position: absolute;
    bottom: 2rem;
    right: 4rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    opacity: 0;
    animation: fadeIn 1s 1.4s forwards;
  }

  .hero-scroll-line span {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.62rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--ash);
    writing-mode: vertical-rl;
    transform: rotate(180deg);
  }

  .hero-scroll-line::after {
    content: '';
    width: 1px;
    height: 60px;
    background: linear-gradient(to bottom, var(--gold-dim), transparent);
    animation: lineGrow 1.5s 1.6s both;
  }

  /* ── DIVIDER ── */
  .gold-divider {
    width: 60px;
    height: 2px;
    background: var(--gold);
    margin-bottom: 1.5rem;
  }

  /* ── SECTION BASE ── */
  section { position: relative; }

  .section-label {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 500;
    font-size: 0.68rem;
    letter-spacing: 0.35em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1rem;
  }

  .section-title {
    font-family: 'Playfair Display', serif;
    font-weight: 700;
    font-size: clamp(2rem, 4vw, 3.5rem);
    line-height: 1.1;
    color: var(--white);
    margin-bottom: 1.5rem;
  }

  .section-title em {
    font-style: italic;
    color: var(--gold);
  }

  .section-body {
    font-size: 1rem;
    line-height: 1.75;
    color: var(--mist);
    max-width: 540px;
  }

  /* ── ABOUT / OVERVIEW ── */
  .about {
    padding: 8rem 4rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6rem;
    align-items: center;
    background: var(--dark);
  }

  .about-visual {
    position: relative;
    height: 480px;
  }

  .about-visual-box {
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, var(--dark3) 0%, var(--dark2) 100%);
    border: 1px solid rgba(201,168,76,0.12);
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }

  .about-visual-box::before {
    content: '';
    position: absolute;
    width: 300px;
    height: 300px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(201,168,76,0.08) 0%, transparent 70%);
  }

  .about-motto {
    font-family: 'Playfair Display', serif;
    font-weight: 900;
    font-style: italic;
    font-size: 2.5rem;
    color: var(--gold);
    text-align: center;
    line-height: 1.2;
    padding: 2rem;
    position: relative;
    z-index: 1;
  }

  .about-motto::before, .about-motto::after {
    content: '"';
    display: block;
    font-size: 6rem;
    line-height: 0.5;
    color: rgba(201,168,76,0.15);
    font-family: 'Playfair Display', serif;
  }

  .about-visual-accent {
    position: absolute;
    top: -20px;
    right: -20px;
    width: 120px;
    height: 120px;
    border: 2px solid rgba(201,168,76,0.2);
  }

  .about-visual-accent2 {
    position: absolute;
    bottom: -20px;
    left: -20px;
    width: 80px;
    height: 80px;
    background: var(--red-ember);
    opacity: 0.4;
  }

  /* ── CYCLE / PHILOSOPHY ── */
  .philosophy {
    padding: 8rem 4rem;
    background: var(--black);
    overflow: hidden;
  }

  .philosophy-header {
    max-width: 600px;
    margin-bottom: 5rem;
  }

  .cycle-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 0;
    border: 1px solid rgba(201,168,76,0.12);
  }

  .cycle-item {
    padding: 2.5rem 2rem;
    border-right: 1px solid rgba(201,168,76,0.12);
    position: relative;
    transition: background 0.4s;
  }

  .cycle-item:last-child { border-right: none; }

  .cycle-item:hover {
    background: rgba(201,168,76,0.04);
  }

  .cycle-num {
    font-family: 'Playfair Display', serif;
    font-size: 3.5rem;
    font-weight: 900;
    color: rgba(201,168,76,0.1);
    line-height: 1;
    margin-bottom: 1rem;
    transition: color 0.4s;
  }

  .cycle-item:hover .cycle-num { color: rgba(201,168,76,0.25); }

  .cycle-name {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 600;
    font-size: 1rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.75rem;
  }

  .cycle-desc {
    font-size: 0.85rem;
    line-height: 1.65;
    color: var(--ash);
  }

  .cycle-connector {
    position: absolute;
    top: 50%;
    right: -1px;
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: var(--gold-dim);
    transform: translate(50%, -50%);
    z-index: 2;
  }

  .cycle-item:last-child .cycle-connector { display: none; }

  .philosophy-quote {
    margin-top: 4rem;
    font-family: 'Playfair Display', serif;
    font-style: italic;
    font-size: clamp(1.2rem, 2.5vw, 1.8rem);
    color: var(--gold-dim);
    text-align: center;
    padding: 2rem;
    border-top: 1px solid rgba(201,168,76,0.1);
    border-bottom: 1px solid rgba(201,168,76,0.1);
  }

  /* ── PLATFORM ── */
  .platform {
    padding: 8rem 4rem;
    background: var(--dark);
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6rem;
    align-items: start;
  }

  .platform-cards {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  .pcard {
    background: var(--dark2);
    border: 1px solid rgba(201,168,76,0.1);
    padding: 2rem;
    transition: border-color 0.3s, transform 0.3s;
    position: relative;
    overflow: hidden;
  }

  .pcard::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 3px;
    background: var(--gold);
    transform: scaleY(0);
    transition: transform 0.3s;
    transform-origin: bottom;
  }

  .pcard:hover::before { transform: scaleY(1); }
  .pcard:hover { transform: translateX(6px); border-color: rgba(201,168,76,0.3); }

  .pcard-title {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 600;
    font-size: 0.75rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.75rem;
  }

  .pcard-text {
    font-size: 0.9rem;
    line-height: 1.7;
    color: var(--mist);
  }

  /* ── SERVICES ── */
  .services {
    padding: 8rem 4rem;
    background: var(--black);
  }

  .services-header {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: end;
    margin-bottom: 5rem;
  }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: rgba(201,168,76,0.1);
  }

  .service-item {
    background: var(--black);
    padding: 3rem 2.5rem;
    transition: background 0.4s;
  }

  .service-item:hover { background: var(--dark); }

  .service-icon {
    width: 40px;
    height: 40px;
    border: 1px solid var(--gold-dim);
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 1.5rem;
    color: var(--gold);
    font-size: 1.1rem;
  }

  .service-name {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 600;
    font-size: 1rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--white);
    margin-bottom: 0.75rem;
  }

  .service-text {
    font-size: 0.85rem;
    line-height: 1.7;
    color: var(--ash);
  }

  /* ── VALUES ── */
  .values {
    padding: 8rem 4rem;
    background: var(--dark2);
    text-align: center;
  }

  .values-header {
    max-width: 500px;
    margin: 0 auto 5rem;
  }

  .values-header .gold-divider { margin: 0 auto 1.5rem; }

  .values-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 3rem;
    max-width: 900px;
    margin: 0 auto;
  }

  .value-item {}

  .value-word {
    font-family: 'Playfair Display', serif;
    font-weight: 700;
    font-size: 1.5rem;
    color: var(--gold);
    margin-bottom: 0.75rem;
  }

  .value-def {
    font-size: 0.85rem;
    line-height: 1.7;
    color: var(--ash);
  }

  /* ── OBJECTIVES ── */
  .objectives {
    padding: 8rem 4rem;
    background: var(--black);
  }

  .obj-tabs {
    display: flex;
    gap: 0;
    border-bottom: 1px solid rgba(201,168,76,0.15);
    margin-bottom: 3rem;
  }

  .obj-tab {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 600;
    font-size: 0.75rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    padding: 1rem 2rem;
    cursor: pointer;
    color: var(--ash);
    border-bottom: 2px solid transparent;
    margin-bottom: -1px;
    transition: color 0.3s, border-color 0.3s;
    background: none;
    border-top: none;
    border-left: none;
    border-right: none;
  }

  .obj-tab.active {
    color: var(--gold);
    border-bottom-color: var(--gold);
  }

  .obj-panel { display: none; }
  .obj-panel.active { display: block; }

  .obj-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 1.25rem;
    max-width: 700px;
  }

  .obj-list li {
    display: flex;
    align-items: flex-start;
    gap: 1.25rem;
    font-size: 1rem;
    line-height: 1.65;
    color: var(--mist);
  }

  .obj-list li::before {
    content: '▶';
    font-size: 0.55rem;
    color: var(--gold);
    margin-top: 0.5em;
    flex-shrink: 0;
  }

  /* ── SOCIAL ── */
  .social {
    padding: 8rem 4rem;
    background: var(--dark);
  }

  .social-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1.5rem;
    margin-top: 4rem;
  }

  .social-handle {
    background: var(--dark3);
    border: 1px solid rgba(201,168,76,0.08);
    padding: 2rem;
    transition: border-color 0.3s, background 0.3s;
  }

  .social-handle:hover {
    border-color: rgba(201,168,76,0.25);
    background: rgba(201,168,76,0.03);
  }

  .handle-name {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 1rem;
    color: var(--gold);
    margin-bottom: 0.5rem;
  }

  .handle-desc {
    font-size: 0.82rem;
    line-height: 1.6;
    color: var(--ash);
  }

  /* ── CTA ── */
  .cta {
    padding: 8rem 4rem;
    background: var(--dark3);
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .cta::before {
    content: '';
    position: absolute;
    top: -200px; left: 50%;
    transform: translateX(-50%);
    width: 600px;
    height: 600px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(201,168,76,0.06) 0%, transparent 70%);
    pointer-events: none;
  }

  .cta-title {
    font-family: 'Playfair Display', serif;
    font-weight: 900;
    font-size: clamp(2.5rem, 6vw, 5rem);
    line-height: 1.1;
    color: var(--white);
    margin-bottom: 1.5rem;
  }

  .cta-title em {
    font-style: italic;
    color: var(--gold);
  }

  .cta-sub {
    font-size: 1.05rem;
    color: var(--mist);
    margin-bottom: 3rem;
    max-width: 500px;
    margin-left: auto;
    margin-right: auto;
  }

  .cta-contact {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    align-items: center;
    margin-top: 3rem;
  }

  .cta-contact a {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 400;
    font-size: 0.85rem;
    letter-spacing: 0.12em;
    color: var(--ash);
    text-decoration: none;
    transition: color 0.3s;
  }

  .cta-contact a:hover { color: var(--gold); }

  /* ── FOOTER ── */
  footer {
    background: var(--black);
    padding: 3rem 4rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-top: 1px solid rgba(201,168,76,0.1);
  }

  .footer-brand {
    font-family: 'Playfair Display', serif;
    font-weight: 700;
    font-size: 1.1rem;
    color: var(--gold);
  }

  .footer-reg {
    font-size: 0.72rem;
    color: var(--ash);
    letter-spacing: 0.05em;
    margin-top: 0.25rem;
  }

  .footer-right {
    font-size: 0.72rem;
    color: var(--ash);
    text-align: right;
    letter-spacing: 0.05em;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeIn {
    from { opacity: 0; }
    to   { opacity: 1; }
  }

  @keyframes lineGrow {
    from { transform: scaleY(0); }
    to   { transform: scaleY(1); }
  }

  /* Scroll-reveal */
  .reveal {
    opacity: 0;
    transform: translateY(40px);
    transition: opacity 0.8s ease, transform 0.8s ease;
  }

  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  .reveal-delay-1 { transition-delay: 0.1s; }
  .reveal-delay-2 { transition-delay: 0.2s; }
  .reveal-delay-3 { transition-delay: 0.3s; }
  .reveal-delay-4 { transition-delay: 0.4s; }
  .reveal-delay-5 { transition-delay: 0.5s; }

  /* ── RESPONSIVE ── */
  @media (max-width: 1024px) {
    nav { padding: 1.5rem 2rem; }
    .hero { padding: 0 2rem 5rem; }
    .about, .platform { grid-template-columns: 1fr; gap: 3rem; padding: 5rem 2rem; }
    .about-visual { height: 300px; }
    .cycle-grid { grid-template-columns: 1fr 1fr; }
    .services-header { grid-template-columns: 1fr; }
    .services-grid { grid-template-columns: 1fr 1fr; padding: 0 2rem; }
    .services { padding: 5rem 2rem; }
    .values-grid { grid-template-columns: 1fr 1fr; gap: 2rem; }
    .values, .objectives, .social, .cta { padding: 5rem 2rem; }
    .philosophy { padding: 5rem 2rem; }
    .social-grid { grid-template-columns: 1fr 1fr; }
    footer { flex-direction: column; gap: 1rem; text-align: center; padding: 2rem; }
    .footer-right { text-align: center; }
    .nav-links { display: none; }
  }

  @media (max-width: 640px) {
    .cycle-grid { grid-template-columns: 1fr; }
    .services-grid { grid-template-columns: 1fr; }
    .values-grid { grid-template-columns: 1fr; }
    .social-grid { grid-template-columns: 1fr; }
    .services-header { gap: 2rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav id="nav">
  <a href="#" class="nav-logo">LOCUST <span>HARVEST</span></a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#philosophy">Philosophy</a></li>
    <li><a href="#platform">Platform</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg"></div>
  <p class="hero-eyebrow">Locust Harvest (Pty) Ltd · Est. 2026</p>
  <h1 class="hero-title">
    From Plagues<br>
    <em>to Profit.</em>
  </h1>
  <p class="hero-sub">Transforming disruption into opportunity — through the power of human storytelling and precision strategy.</p>
  <div class="hero-actions">
    <a href="#platform" class="btn-primary">Explore the Platform</a>
    <a href="#contact" class="btn-ghost">Get in touch →</a>
  </div>
  <div class="hero-scroll-line">
    <span>Scroll</span>
  </div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="about-visual reveal">
    <div class="about-visual-box">
      <div class="about-motto">From<br>Plagues<br>to Profit</div>
    </div>
    <div class="about-visual-accent"></div>
    <div class="about-visual-accent2"></div>
  </div>
  <div class="about-content">
    <p class="section-label reveal">Company Overview</p>
    <div class="gold-divider reveal"></div>
    <h2 class="section-title reveal">Where Resilience Meets <em>Precision</em></h2>
    <p class="section-body reveal">LOCUST HARVEST (PTY) LTD is an innovative strategy-driven company built on a powerful dual mandate: transforming disruption into opportunity, and capturing the most extraordinary human stories of resilience that the world has to offer.</p>
    <br>
    <p class="section-body reveal" style="margin-top:1rem;">Inspired by the natural behaviour of locust swarms and the biblical principle of restoration following devastation, we combine analytical precision with the raw power of human storytelling — creating platforms where individuals and organisations rise from challenge to triumph.</p>
  </div>
</section>

<!-- PHILOSOPHY -->
<section class="philosophy" id="philosophy">
  <div class="philosophy-header">
    <p class="section-label reveal">Strategic Philosophy</p>
    <div class="gold-divider reveal"></div>
    <h2 class="section-title reveal">The Five <em>Phases</em> of Every Environment</h2>
    <p class="section-body reveal">Every environment — personal, financial, or societal — moves through identifiable phases. Understanding them allows for strategic positioning rather than reactive decision-making.</p>
  </div>
  <div class="cycle-grid">
    <div class="cycle-item reveal">
      <div class="cycle-num">01</div>
      <div class="cycle-name">Accumulation</div>
      <p class="cycle-desc">The preparation phase where underlying conditions are forming beneath the surface, unseen by most.</p>
      <div class="cycle-connector"></div>
    </div>
    <div class="cycle-item reveal reveal-delay-1">
      <div class="cycle-num">02</div>
      <div class="cycle-name">Manipulation</div>
      <p class="cycle-desc">A period where behaviour may appear misleading, uncertain, or designed to confuse and misdirect.</p>
      <div class="cycle-connector"></div>
    </div>
    <div class="cycle-item reveal reveal-delay-2">
      <div class="cycle-num">03</div>
      <div class="cycle-name">Distribution</div>
      <p class="cycle-desc">Movement toward a defined and recognisable direction — the signal becomes clear.</p>
      <div class="cycle-connector"></div>
    </div>
    <div class="cycle-item reveal reveal-delay-3">
      <div class="cycle-num">04</div>
      <div class="cycle-name">Devastation</div>
      <p class="cycle-desc">A significant disruptive event or outcome — the lowest point of the cycle. The plague arrives.</p>
      <div class="cycle-connector"></div>
    </div>
    <div class="cycle-item reveal reveal-delay-4">
      <div class="cycle-num">05</div>
      <div class="cycle-name">Restoration</div>
      <p class="cycle-desc">The recovery phase where new opportunities emerge, growth begins, and profit is claimed.</p>
    </div>
  </div>
  <p class="philosophy-quote reveal">"Only someone who is not being manipulated can see manipulation."</p>
</section>

<!-- PLATFORM -->
<section class="platform" id="platform">
  <div>
    <p class="section-label reveal">The Platform</p>
    <div class="gold-divider reveal"></div>
    <h2 class="section-title reveal">A Global <em>Storytelling</em> Ecosystem</h2>
    <p class="section-body reveal">At the heart of Locust Harvest is a collection of premium, monetised digital platforms where people from every corner of the world can tell their personal stories of rising against all odds.</p>
    <br>
    <p class="section-body reveal" style="margin-top:1rem;">We capture inspirational true stories of triumph over extraordinary adversity — from entrepreneurs to survivors, community leaders to everyday heroes.</p>
  </div>
  <div class="platform-cards">
    <div class="pcard reveal">
      <div class="pcard-title">What We Capture</div>
      <p class="pcard-text">Authentic journeys from devastation, hardship or failure to restoration and success. Narratives that inspire, educate and motivate global audiences.</p>
    </div>
    <div class="pcard reveal reveal-delay-1">
      <div class="pcard-title">Upfront Payment</div>
      <p class="pcard-text">Story owners receive a negotiated once-off payment at the time of story submission and publication.</p>
    </div>
    <div class="pcard reveal reveal-delay-2">
      <div class="pcard-title">Revenue Share</div>
      <p class="pcard-text">Story owners receive an agreed percentage of all earnings generated from their story across all monetised platforms.</p>
    </div>
    <div class="pcard reveal reveal-delay-3">
      <div class="pcard-title">Multi-Platform Reach</div>
      <p class="pcard-text">All platforms are monetised and earning-generating across web, social, and streaming environments. Stories curated for quality, authenticity, and impact.</p>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section class="services" id="services">
  <div class="services-header">
    <div>
      <p class="section-label reveal">Products & Services</p>
      <div class="gold-divider reveal"></div>
      <h2 class="section-title reveal">What We <em>Offer</em></h2>
    </div>
    <p class="section-body reveal">Structured services that combine the power of human narrative with precision analytical frameworks — delivering insight, impact, and opportunity.</p>
  </div>
  <div class="services-grid">
    <div class="service-item reveal">
      <div class="service-icon">◈</div>
      <div class="service-name">Storytelling Platform</div>
      <p class="service-text">Global "From Plague to Profit" digital story platform with story acquisition, curation, production and multi-platform distribution.</p>
    </div>
    <div class="service-item reveal reveal-delay-1">
      <div class="service-icon">◎</div>
      <div class="service-name">Pattern Analysis</div>
      <p class="service-text">Strategic identification of behavioural structures and directional tendencies across dynamic environments.</p>
    </div>
    <div class="service-item reveal reveal-delay-2">
      <div class="service-icon">◇</div>
      <div class="service-name">Opportunity Timing</div>
      <p class="service-text">Methods to determine favourable timing for decisions — the difference between reactive and strategic positioning.</p>
    </div>
    <div class="service-item reveal reveal-delay-3">
      <div class="service-icon">▲</div>
      <div class="service-name">Analytical Methods</div>
      <p class="service-text">Structured rule-based approaches to interpreting change and building reliable decision frameworks.</p>
    </div>
    <div class="service-item reveal reveal-delay-4">
      <div class="service-icon">✦</div>
      <div class="service-name">Educational Resources</div>
      <p class="service-text">Principles of structured analytical observation — training and resources to sharpen strategic thinking.</p>
    </div>
    <div class="service-item reveal reveal-delay-5">
      <div class="service-icon">⟡</div>
      <div class="service-name">Research & Development</div>
      <p class="service-text">Continuous improvement of methodologies and development of proprietary analytical and pattern recognition technologies.</p>
    </div>
  </div>
</section>

<!-- VALUES -->
<section class="values" id="values">
  <div class="values-header">
    <p class="section-label">Core Values</p>
    <div class="gold-divider"></div>
    <h2 class="section-title">Built on <em>Principle</em></h2>
  </div>
  <div class="values-grid">
    <div class="value-item reveal">
      <div class="value-word">Precision</div>
      <p class="value-def">Accuracy, patience and disciplined execution in all strategic processes.</p>
    </div>
    <div class="value-item reveal reveal-delay-1">
      <div class="value-word">Insight</div>
      <p class="value-def">Understanding patterns provides a strategic advantage in any environment.</p>
    </div>
    <div class="value-item reveal reveal-delay-2">
      <div class="value-word">Integrity</div>
      <p class="value-def">Transparency, honesty and accountability in all engagements, without exception.</p>
    </div>
    <div class="value-item reveal reveal-delay-3">
      <div class="value-word">Consistency</div>
      <p class="value-def">Structured approaches rather than emotional or impulsive decisions.</p>
    </div>
    <div class="value-item reveal reveal-delay-4">
      <div class="value-word">Restoration</div>
      <p class="value-def">Every challenge presents an opportunity for renewal and growth.</p>
    </div>
    <div class="value-item reveal reveal-delay-5">
      <div class="value-word">Excellence</div>
      <p class="value-def">Committed to continuous improvement and high-quality outcomes in everything we do.</p>
    </div>
  </div>
</section>

<!-- OBJECTIVES -->
<section class="objectives" id="objectives">
  <p class="section-label reveal">Business Objectives</p>
  <div class="gold-divider reveal"></div>
  <h2 class="section-title reveal" style="max-width:600px;">The Road <em>Ahead</em></h2>
  <div class="obj-tabs reveal">
    <button class="obj-tab active" onclick="showTab('short')">Short-Term</button>
    <button class="obj-tab" onclick="showTab('medium')">Medium-Term</button>
    <button class="obj-tab" onclick="showTab('long')">Long-Term</button>
  </div>
  <div class="obj-panel active" id="tab-short">
    <ul class="obj-list">
      <li>Establish and launch the 'From Plague to Profit' digital storytelling platform</li>
      <li>Begin acquiring and publishing inspirational story content from global contributors</li>
      <li>Establish structured analytical framework and tools</li>
      <li>Build strong brand identity and social media presence across all channels</li>
    </ul>
  </div>
  <div class="obj-panel" id="tab-medium">
    <ul class="obj-list">
      <li>Expand platform reach and grow audience across all channels</li>
      <li>Develop automated story submission and curation tools</li>
      <li>Build strategic content partnerships and media collaborations</li>
      <li>Increase monetisation and story owner revenue sharing</li>
    </ul>
  </div>
  <div class="obj-panel" id="tab-long">
    <ul class="obj-list">
      <li>Become the globally recognised home of 'From Plague to Profit' storytelling</li>
      <li>Develop proprietary analytical and pattern recognition technologies</li>
      <li>Publish research, books and comprehensive training programs</li>
      <li>Expand internationally across all major markets</li>
    </ul>
  </div>
</section>

<!-- SOCIAL -->
<section class="social" id="social">
  <p class="section-label reveal">Digital Presence</p>
  <div class="gold-divider reveal"></div>
  <h2 class="section-title reveal">Find Us <em>Everywhere</em></h2>
  <div class="social-grid">
    <div class="social-handle reveal">
      <div class="handle-name">@LocustHarvest</div>
      <p class="handle-desc">Primary brand account — company news, platform updates, and strategy content.</p>
    </div>
    <div class="social-handle reveal reveal-delay-1">
      <div class="handle-name">@FromPlaguesToProfit</div>
      <p class="handle-desc">Storytelling and inspiration — featuring story owner narratives and testimonials.</p>
    </div>
    <div class="social-handle reveal reveal-delay-2">
      <div class="handle-name">@Plagues2Profit</div>
      <p class="handle-desc">Short-form content, highlights, and viral inspiration stories for every platform.</p>
    </div>
    <div class="social-handle reveal reveal-delay-3">
      <div class="handle-name">@AgainstAllOdds</div>
      <p class="handle-desc">Mixed content celebrating stories of resilience from around the world.</p>
    </div>
  </div>
</section>

<!-- CTA -->
<section class="cta" id="contact">
  <h2 class="cta-title reveal">Your Plague Is<br><em>Your Profit</em></h2>
  <p class="cta-sub reveal">Have a story to tell? A strategy to build? Get in touch with the Locust Harvest team today.</p>
  <a href="mailto:sydneytayiya@locustharvest.com" class="btn-primary reveal">sydneytayiya@locustharvest.com</a>
  <div class="cta-contact reveal">
    <a href="tel:+27713641561">+27 71 364 1561</a>
    <a href="tel:+27627418656">+27 62 741 8656</a>
    <a href="https://www.locustharvest.com" target="_blank">www.locustharvest.com</a>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div>
    <div class="footer-brand">LOCUST HARVEST</div>
    <div class="footer-reg">Reg No: 2026/392620/07 · Tax No: 9050539320</div>
  </div>
  <div class="footer-right">
    © 2026 Locust Harvest (Pty) Ltd<br>
    "From Plagues to Profit"
  </div>
</footer>

<script>
  // Nav scroll effect
  const nav = document.getElementById('nav');
  window.addEventListener('scroll', () => {
    nav.classList.toggle('scrolled', window.scrollY > 60);
  });

  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.12 });
  reveals.forEach(el => observer.observe(el));

  // Objective tabs
  function showTab(id) {
    document.querySelectorAll('.obj-tab').forEach(t => t.classList.remove('active'));
    document.querySelectorAll('.obj-panel').forEach(p => p.classList.remove('active'));
    document.getElementById('tab-' + id).classList.add('active');
    event.target.classList.add('active');
  }
</script>
</body>
</html>
