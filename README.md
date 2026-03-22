# Zunain-portfolio-2
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Zunain | Web Developer – Karnataka</title>
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --bg: #080c10;
      --surface: #0f1318;
      --border: #1e2530;
      --accent: #00e5a0;
      --accent2: #0099ff;
      --text: #e8edf2;
      --muted: #7a8899;
      --card: #111820;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'DM Sans', sans-serif;
      font-size: 16px;
      line-height: 1.7;
      overflow-x: hidden;
    }

    body::before {
      content: '';
      position: fixed; inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
      pointer-events: none; z-index: 0; opacity: 0.4;
    }

    body::after {
      content: '';
      position: fixed; inset: 0;
      background-image:
        linear-gradient(rgba(0,229,160,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,229,160,0.03) 1px, transparent 1px);
      background-size: 60px 60px;
      pointer-events: none; z-index: 0;
    }

    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 20px 48px;
      background: rgba(8,12,16,0.85);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border);
    }

    .nav-logo {
      font-family: 'Syne', sans-serif;
      font-weight: 800; font-size: 1.2rem;
      color: var(--accent);
      letter-spacing: -0.5px;
    }

    .nav-links { display: flex; gap: 36px; }
    .nav-links a {
      color: var(--muted); text-decoration: none;
      font-size: 0.9rem; font-weight: 500;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--text); }

    .hero {
      min-height: 100vh;
      display: flex; flex-direction: column;
      justify-content: center;
      padding: 120px 48px 80px;
      position: relative;
    }

    .hero-badge {
      display: inline-flex; align-items: center; gap: 8px;
      background: rgba(0,229,160,0.08);
      border: 1px solid rgba(0,229,160,0.2);
      color: var(--accent);
      padding: 6px 14px; border-radius: 100px;
      font-size: 0.78rem; font-weight: 500;
      letter-spacing: 0.5px; text-transform: uppercase;
      margin-bottom: 32px;
      width: fit-content;
      animation: fadeUp 0.6s ease both;
    }

    .hero-badge span {
      width: 6px; height: 6px; border-radius: 50%;
      background: var(--accent);
      animation: pulse 2s infinite;
    }

    .hero-title {
      font-family: 'Syne', sans-serif;
      font-size: clamp(3rem, 7vw, 6.5rem);
      font-weight: 800;
      line-height: 1.0;
      letter-spacing: -2px;
      margin-bottom: 24px;
      animation: fadeUp 0.6s 0.1s ease both;
    }

    .hero-title em {
      font-style: normal;
      background: linear-gradient(90deg, var(--accent), var(--accent2));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .hero-sub {
      max-width: 540px;
      color: var(--muted);
      font-size: 1.1rem;
      font-weight: 300;
      margin-bottom: 48px;
      animation: fadeUp 0.6s 0.2s ease both;
    }

    .hero-cta {
      display: flex; gap: 16px; flex-wrap: wrap;
      animation: fadeUp 0.6s 0.3s ease both;
    }

    .btn-primary {
      display: inline-flex; align-items: center; gap: 10px;
      background: var(--accent);
      color: #080c10;
      padding: 14px 28px; border-radius: 8px;
      font-weight: 700; font-size: 0.95rem;
      text-decoration: none;
      transition: transform 0.2s, box-shadow 0.2s;
      box-shadow: 0 0 24px rgba(0,229,160,0.2);
    }
    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 0 36px rgba(0,229,160,0.35);
    }

    .btn-secondary {
      display: inline-flex; align-items: center; gap: 10px;
      border: 1px solid var(--border);
      color: var(--text);
      padding: 14px 28px; border-radius: 8px;
      font-weight: 500; font-size: 0.95rem;
      text-decoration: none;
      background: transparent;
      transition: border-color 0.2s, background 0.2s;
    }
    .btn-secondary:hover {
      border-color: var(--accent);
      background: rgba(0,229,160,0.05);
    }

    .hero-glow {
      position: absolute; right: 5%; top: 20%;
      width: 500px; height: 500px;
      background: radial-gradient(circle, rgba(0,229,160,0.08) 0%, transparent 70%);
      pointer-events: none;
      animation: float 8s ease-in-out infinite;
    }

    .stats-strip {
      display: grid; grid-template-columns: repeat(3, 1fr);
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
    }

    .stat {
      padding: 40px 48px;
      border-right: 1px solid var(--border);
    }
    .stat:last-child { border-right: none; }

    .stat-num {
      font-family: 'Syne', sans-serif;
      font-size: 2.8rem; font-weight: 800;
      color: var(--accent);
      letter-spacing: -1px;
    }

    .stat-label { color: var(--muted); font-size: 0.9rem; margin-top: 4px; }

    section { padding: 100px 48px; position: relative; z-index: 1; }

    .section-tag {
      font-size: 0.75rem; font-weight: 600;
      letter-spacing: 2px; text-transform: uppercase;
      color: var(--accent); margin-bottom: 16px;
    }

    .section-title {
      font-family: 'Syne', sans-serif;
      font-size: clamp(1.8rem, 4vw, 3rem);
      font-weight: 800; letter-spacing: -1px;
      line-height: 1.1; margin-bottom: 16px;
    }

    .section-sub {
      color: var(--muted); font-size: 1rem;
      max-width: 500px; margin-bottom: 60px;
    }

    .services-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
      border-radius: 12px;
      overflow: hidden;
    }

    .service-card {
      background: var(--card);
      padding: 36px;
      transition: background 0.3s;
      position: relative;
      overflow: hidden;
    }

    .service-card::before {
      content: '';
      position: absolute; top: 0; left: 0; right: 0;
      height: 2px;
      background: linear-gradient(90deg, var(--accent), var(--accent2));
      transform: scaleX(0);
      transition: transform 0.3s;
      transform-origin: left;
    }

    .service-card:hover { background: #141c24; }
    .service-card:hover::before { transform: scaleX(1); }

    .service-icon { font-size: 2rem; margin-bottom: 20px; }

    .service-title {
      font-family: 'Syne', sans-serif;
      font-weight: 700; font-size: 1.1rem;
      margin-bottom: 10px;
    }

    .service-desc { color: var(--muted); font-size: 0.9rem; line-height: 1.6; }

    .service-price {
      margin-top: 20px;
      color: var(--accent);
      font-family: 'Syne', sans-serif;
      font-weight: 700; font-size: 1rem;
    }

    .portfolio-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 24px;
    }

    .project-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px;
      overflow: hidden;
      transition: transform 0.3s, border-color 0.3s;
    }

    .project-card:hover {
      transform: translateY(-6px);
      border-color: rgba(0,229,160,0.3);
    }

    .project-preview {
      height: 200px;
      display: flex; align-items: center; justify-content: center;
      position: relative;
      overflow: hidden;
    }

    .preview-aitech {
      background: linear-gradient(135deg, #0a0f1a 0%, #0d1b2a 50%, #050b14 100%);
    }

    .preview-demo {
      background: linear-gradient(135deg, #0f0a1a 0%, #1a0d2e 50%, #080510 100%);
    }

    .preview-dots {
      position: absolute; inset: 0;
      background-image: radial-gradient(circle, rgba(0,229,160,0.15) 1px, transparent 1px);
      background-size: 24px 24px;
    }

    .preview-label {
      position: relative; z-index: 1;
      font-family: 'Syne', sans-serif;
      font-size: 1.3rem; font-weight: 800;
      color: var(--accent);
      text-align: center;
    }

    .project-info { padding: 24px; }

    .project-name {
      font-family: 'Syne', sans-serif;
      font-weight: 700; font-size: 1.05rem;
      margin-bottom: 8px;
    }

    .project-desc { color: var(--muted); font-size: 0.88rem; margin-bottom: 16px; }

    .project-tags { display: flex; gap: 8px; flex-wrap: wrap; }

    .tag {
      background: rgba(0,229,160,0.08);
      border: 1px solid rgba(0,229,160,0.15);
      color: var(--accent);
      padding: 3px 10px; border-radius: 100px;
      font-size: 0.75rem; font-weight: 500;
    }

    .process-list {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      position: relative;
    }

    .process-list::before {
      content: '';
      position: absolute;
      top: 32px; left: 40px; right: 40px;
      height: 1px;
      background: linear-gradient(90deg, transparent, var(--border), var(--border), transparent);
    }

    .process-step {
      padding: 0 32px 32px;
      text-align: center;
    }

    .step-num {
      width: 64px; height: 64px;
      border: 1px solid var(--border);
      border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      margin: 0 auto 24px;
      background: var(--bg);
      font-family: 'Syne', sans-serif;
      font-weight: 800; font-size: 1.2rem;
      color: var(--accent);
      position: relative; z-index: 1;
    }

    .step-title {
      font-family: 'Syne', sans-serif;
      font-weight: 700; font-size: 1rem;
      margin-bottom: 8px;
    }

    .step-desc { color: var(--muted); font-size: 0.88rem; }

    .contact-section {
      background: var(--surface);
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
    }

    .contact-inner { max-width: 640px; }

    .contact-ctas {
      display: flex; gap: 16px; flex-wrap: wrap;
      margin-top: 40px;
    }

    .whatsapp-btn {
      display: inline-flex; align-items: center; gap: 10px;
      background: #25D366;
      color: #fff;
      padding: 14px 28px; border-radius: 8px;
      font-weight: 700; font-size: 0.95rem;
      text-decoration: none;
      transition: transform 0.2s, box-shadow 0.2s;
      box-shadow: 0 0 24px rgba(37,211,102,0.2);
    }
    .whatsapp-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 0 36px rgba(37,211,102,0.35);
    }

    footer {
      padding: 32px 48px;
      display: flex; align-items: center; justify-content: space-between;
      border-top: 1px solid var(--border);
      position: relative; z-index: 1;
    }

    .footer-logo { font-family: 'Syne', sans-serif; font-weight: 800; color: var(--accent); }
    .footer-text { color: var(--muted); font-size: 0.85rem; }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.3; }
    }
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-30px); }
    }

    .reveal {
      opacity: 0; transform: translateY(32px);
      transition: opacity 0.6s ease, transform 0.6s ease;
    }
    .reveal.visible { opacity: 1; transform: translateY(0); }

    @media (max-width: 768px) {
      nav { padding: 16px 24px; }
      .nav-links { display: none; }
      .hero { padding: 100px 24px 60px; }
      .hero-title { font-size: 2.8rem; letter-spacing: -1px; }
      .stats-strip { grid-template-columns: 1fr; }
      .stat { border-right: none; border-bottom: 1px solid var(--border); padding: 28px 24px; }
      section { padding: 72px 24px; }
      footer { flex-direction: column; gap: 12px; text-align: center; padding: 24px; }
      .process-list::before { display: none; }
    }
  </style>
</head>
<body>

  <nav>
    <div class="nav-logo">Z//</div>
    <div class="nav-links">
      <a href="#services">Services</a>
      <a href="#work">Work</a>
      <a href="#process">Process</a>
      <a href="#contact">Contact</a>
    </div>
  </nav>

  <section class="hero">
    <div class="hero-glow"></div>
    <div class="hero-badge"><span></span> Available for Projects – Karnataka</div>
    <h1 class="hero-title">
      Websites that<br/>
      <em>actually work</em><br/>
      for your business.
    </h1>
    <p class="hero-sub">
      I build fast, professional websites for local businesses in Karnataka — deployed live in 3 days. No monthly fees. No complicated builders.
    </p>
    <div class="hero-cta">
      <a href="#contact" class="btn-primary">
        <svg width="18" height="18" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z"/></svg>
        WhatsApp Me
      </a>
      <a href="#work" class="btn-secondary">See My Work →</a>
    </div>
  </section>

  <div class="stats-strip reveal">
    <div class="stat">
      <div class="stat-num">₹0</div>
      <div class="stat-label">Monthly hosting fee for you</div>
    </div>
    <div class="stat">
      <div class="stat-num">3 Days</div>
      <div class="stat-label">Average delivery time</div>
    </div>
    <div class="stat">
      <div class="stat-num">100%</div>
      <div class="stat-label">Mobile responsive, always</div>
    </div>
  </div>

  <section id="services">
    <div class="section-tag">What I Offer</div>
    <h2 class="section-title reveal">Services built for<br/>local businesses</h2>
    <p class="section-sub reveal">Clear packages. Fixed prices. No hidden costs.</p>
    <div class="services-grid reveal">
      <div class="service-card">
        <div class="service-icon">🏪</div>
        <div class="service-title">Single Page Website</div>
        <div class="service-desc">A clean, professional one-pager with your services, contact info, location, and WhatsApp button. Perfect for shops, clinics, and solo businesses.</div>
        <div class="service-price">Starting ₹5,000</div>
      </div>
      <div class="service-card">
        <div class="service-icon">🏢</div>
        <div class="service-title">Full Business Website</div>
        <div class="service-desc">Multi-page site with Home, About, Services, Gallery, and Contact pages. Includes contact form, Google Maps, and SEO-friendly structure.</div>
        <div class="service-price">Starting ₹10,000</div>
      </div>
      <div class="service-card">
        <div class="service-icon">🔧</div>
        <div class="service-title">Monthly Maintenance</div>
        <div class="service-desc">Keep your website up to date. Update text, add new photos, fix issues, or add new sections. Flexible monthly retainer for ongoing support.</div>
        <div class="service-price">₹500 – ₹1,000/mo</div>
      </div>
      <div class="service-card">
        <div class="service-icon">📍</div>
        <div class="service-title">Google Business Setup</div>
        <div class="service-desc">Get your business on Google Maps, show up in local search results, and attract nearby customers who are actively looking for your service.</div>
        <div class="service-price">₹2,000 one-time</div>
      </div>
    </div>
  </section>

  <section id="work" style="background: var(--surface); border-top: 1px solid var(--border);">
    <div class="section-tag">Portfolio</div>
    <h2 class="section-title reveal">Real websites,<br/>real businesses</h2>
    <p class="section-sub reveal">Every site is built from scratch and deployed live — no templates, no drag-and-drop.</p>
    <div class="portfolio-grid reveal">
      <div class="project-card">
        <div class="project-preview preview-aitech">
          <div class="preview-dots"></div>
          <div class="preview-label">AI-TECH<br/><span style="font-size:0.7rem;opacity:0.6;">Computer Services & Training</span></div>
        </div>
        <div class="project-info">
          <div class="project-name">AI-TECH Computer Services & Training</div>
          <div class="project-desc">Full dark-themed business website for a computer training centre in Mannekheli, Karnataka. Includes animated hero, stat counters, services section, and working contact form.</div>
          <div class="project-tags">
            <span class="tag">HTML/CSS/JS</span>
            <span class="tag">Netlify</span>
            <span class="tag">Contact Form</span>
            <span class="tag">Animations</span>
          </div>
        </div>
      </div>
      <div class="project-card">
        <div class="project-preview preview-demo">
          <div class="preview-dots"></div>
          <div class="preview-label">YOUR BUSINESS<br/><span style="font-size:0.7rem;opacity:0.6;">Could look like this</span></div>
        </div>
        <div class="project-info">
          <div class="project-name">Your Business Here</div>
          <div class="project-desc">This slot could be your website. Whether you run a medical clinic, coaching centre, restaurant, or retail shop — I can build a site that makes customers trust you instantly.</div>
          <div class="project-tags">
            <span class="tag">Fast Delivery</span>
            <span class="tag">Mobile Ready</span>
            <span class="tag">Free Hosting</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="process">
    <div class="section-tag">How It Works</div>
    <h2 class="section-title reveal">Simple 4-step<br/>process</h2>
    <p class="section-sub reveal">From first message to live website in 3 days.</p>
    <div class="process-list reveal">
      <div class="process-step">
        <div class="step-num">01</div>
        <div class="step-title">You Share Details</div>
        <div class="step-desc">Send me your business name, services, address, phone, and any photos you have. WhatsApp is fine.</div>
      </div>
      <div class="process-step">
        <div class="step-num">02</div>
        <div class="step-title">I Build the Site</div>
        <div class="step-desc">I design and code your full website. You get a preview link within 24–48 hours to review.</div>
      </div>
      <div class="process-step">
        <div class="step-num">03</div>
        <div class="step-title">You Give Feedback</div>
        <div class="step-desc">Request any changes — text, colors, sections. One free revision is included in every package.</div>
      </div>
      <div class="process-step">
        <div class="step-num">04</div>
        <div class="step-title">Your Site Goes Live</div>
        <div class="step-desc">I deploy your website and hand over everything. You start getting customers from day one.</div>
      </div>
    </div>
  </section>

  <section id="contact" class="contact-section">
    <div class="contact-inner">
      <div class="section-tag">Get in Touch</div>
      <h2 class="section-title reveal">Ready to get<br/>your website?</h2>
      <p class="section-sub reveal" style="margin-bottom:0">
        Send me a WhatsApp message right now with your business name and what you need. I'll reply within a few hours with a plan and price — no obligation.
      </p>
      <div class="contact-ctas reveal">
        <a href="https://wa.me/917975379678?t
