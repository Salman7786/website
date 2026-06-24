<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>TrueCloudArabia – Cloud & Technology Solutions</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --navy:    #0A1628;
      --navy2:   #1E3A5F;
      --gold:    #C9A84C;
      --gold-lt: #E2C97A;
      --white:   #F0EDE6;
      --mist:    #E8F0F7;
      --gray:    #8A9BB0;
      --text:    #1C2B3A;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Inter', sans-serif;
      background: var(--white);
      color: var(--text);
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 5vw;
      height: 72px;
      background: rgba(10,22,40,0.92);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(201,168,76,0.2);
    }
    .nav-logo {
      display: flex; align-items: center; gap: 12px; text-decoration: none;
    }
    .nav-logo-icon {
      width: 38px; height: 38px;
    }
    .nav-logo-text {
      font-family: 'Playfair Display', serif;
      font-size: 1.25rem; font-weight: 700;
      color: var(--white);
      letter-spacing: 0.02em;
    }
    .nav-logo-text span { color: var(--gold); }
    .nav-links {
      display: flex; gap: 36px; list-style: none;
    }
    .nav-links a {
      color: rgba(240,237,230,0.75);
      text-decoration: none; font-size: 0.88rem;
      font-weight: 500; letter-spacing: 0.04em;
      text-transform: uppercase;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--gold); }
    .nav-cta {
      background: var(--gold); color: var(--navy) !important;
      padding: 8px 22px; border-radius: 4px;
      font-weight: 600 !important;
    }
    .nav-cta:hover { background: var(--gold-lt) !important; color: var(--navy) !important; }

    /* ── HERO ── */
    #hero {
      position: relative; overflow: hidden;
      min-height: 100vh;
      display: flex; align-items: center;
      background: var(--navy);
      padding: 120px 5vw 80px;
    }

    /* Arabic geometric pattern SVG background */
    #hero-pattern {
      position: absolute; inset: 0;
      opacity: 0.06;
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='120'%3E%3Cg fill='none' stroke='%23C9A84C' stroke-width='1'%3E%3Cpolygon points='60,10 73,40 105,40 80,60 90,90 60,72 30,90 40,60 15,40 47,40'/%3E%3Cpolygon points='60,30 68,52 92,52 73,66 80,88 60,75 40,88 47,66 28,52 52,52' stroke-width='0.5'/%3E%3Ccircle cx='60' cy='60' r='50' stroke-width='0.3'/%3E%3Ccircle cx='60' cy='60' r='35' stroke-width='0.3'/%3E%3C/g%3E%3C/svg%3E");
      background-size: 120px 120px;
    }

    /* Glowing orb */
    #hero::after {
      content: '';
      position: absolute; right: -10vw; top: 50%; transform: translateY(-50%);
      width: 60vw; height: 60vw; max-width: 700px; max-height: 700px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(201,168,76,0.12) 0%, rgba(30,58,95,0.08) 50%, transparent 70%);
      pointer-events: none;
    }

    .hero-content { position: relative; z-index: 2; max-width: 680px; }
    .hero-eyebrow {
      display: inline-block;
      font-size: 0.78rem; font-weight: 600;
      letter-spacing: 0.2em; text-transform: uppercase;
      color: var(--gold); margin-bottom: 24px;
      border-left: 3px solid var(--gold); padding-left: 12px;
    }
    .hero-headline {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2.4rem, 5vw, 4rem);
      font-weight: 700; line-height: 1.15;
      color: var(--white); margin-bottom: 24px;
    }
    .hero-headline em { color: var(--gold); font-style: normal; }
    .hero-sub {
      font-size: 1.1rem; font-weight: 300; line-height: 1.75;
      color: rgba(240,237,230,0.7); margin-bottom: 44px; max-width: 540px;
    }
    .hero-actions { display: flex; gap: 16px; flex-wrap: wrap; }
    .btn-primary {
      background: var(--gold); color: var(--navy);
      padding: 14px 32px; border-radius: 4px;
      font-weight: 600; font-size: 0.95rem;
      text-decoration: none; transition: background 0.2s, transform 0.2s;
      letter-spacing: 0.02em;
    }
    .btn-primary:hover { background: var(--gold-lt); transform: translateY(-2px); }
    .btn-ghost {
      border: 1.5px solid rgba(201,168,76,0.5); color: var(--gold);
      padding: 14px 32px; border-radius: 4px;
      font-weight: 500; font-size: 0.95rem;
      text-decoration: none; transition: border-color 0.2s, background 0.2s;
    }
    .btn-ghost:hover { border-color: var(--gold); background: rgba(201,168,76,0.07); }

    .hero-stats {
      position: relative; z-index: 2;
      display: flex; gap: 0; margin-top: 72px;
      border-top: 1px solid rgba(201,168,76,0.2); padding-top: 36px;
      flex-wrap: wrap;
    }
    .stat {
      flex: 1 1 160px; padding-right: 36px;
      border-right: 1px solid rgba(201,168,76,0.15);
      margin-right: 36px;
    }
    .stat:last-child { border-right: none; margin-right: 0; }
    .stat-num {
      font-family: 'Playfair Display', serif;
      font-size: 2.4rem; font-weight: 700;
      color: var(--gold); line-height: 1;
      margin-bottom: 6px;
    }
    .stat-label { font-size: 0.82rem; color: rgba(240,237,230,0.55); letter-spacing: 0.05em; text-transform: uppercase; }

    /* ── SECTION COMMON ── */
    section { padding: 100px 5vw; }
    .section-tag {
      font-size: 0.75rem; font-weight: 600;
      letter-spacing: 0.2em; text-transform: uppercase;
      color: var(--gold); margin-bottom: 14px;
    }
    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(1.8rem, 3.5vw, 2.8rem);
      font-weight: 700; line-height: 1.2;
      color: var(--navy); margin-bottom: 18px;
    }
    .section-intro {
      font-size: 1.05rem; line-height: 1.8;
      color: #4A6070; max-width: 580px;
    }

    /* ── SERVICES ── */
    #services { background: var(--white); }
    .services-header { margin-bottom: 60px; }

    .services-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
      gap: 28px;
    }
    .service-card {
      background: #fff;
      border: 1px solid #DDE6EF;
      border-radius: 8px;
      padding: 36px 32px;
      transition: box-shadow 0.25s, transform 0.25s, border-color 0.25s;
      position: relative; overflow: hidden;
    }
    .service-card::before {
      content: '';
      position: absolute; top: 0; left: 0; right: 0; height: 3px;
      background: linear-gradient(90deg, var(--gold), var(--navy2));
      opacity: 0; transition: opacity 0.25s;
    }
    .service-card:hover {
      box-shadow: 0 16px 48px rgba(10,22,40,0.1);
      transform: translateY(-4px);
      border-color: rgba(201,168,76,0.35);
    }
    .service-card:hover::before { opacity: 1; }
    .service-icon {
      width: 52px; height: 52px; margin-bottom: 22px;
      background: linear-gradient(135deg, rgba(201,168,76,0.15), rgba(30,58,95,0.1));
      border-radius: 10px;
      display: flex; align-items: center; justify-content: center;
    }
    .service-icon svg { width: 26px; height: 26px; }
    .service-card h3 {
      font-family: 'Playfair Display', serif;
      font-size: 1.2rem; font-weight: 600;
      color: var(--navy); margin-bottom: 12px;
    }
    .service-card p {
      font-size: 0.92rem; line-height: 1.75; color: #5A7080;
    }
    .service-link {
      display: inline-flex; align-items: center; gap: 6px;
      margin-top: 20px; font-size: 0.85rem; font-weight: 600;
      color: var(--gold); text-decoration: none;
      letter-spacing: 0.03em;
    }
    .service-link:hover { gap: 10px; }

    /* ── WHY US ── */
    #why {
      background: var(--navy);
      position: relative; overflow: hidden;
    }
    #why::before {
      content: ''; position: absolute; inset: 0;
      opacity: 0.04;
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='80' height='80'%3E%3Cpath d='M40 5L75 25V55L40 75L5 55V25Z' fill='none' stroke='%23C9A84C' stroke-width='1'/%3E%3C/svg%3E");
      background-size: 80px 80px;
    }
    #why .section-title { color: var(--white); }
    #why .section-intro { color: rgba(240,237,230,0.6); }

    .why-grid {
      display: grid; grid-template-columns: 1fr 1fr;
      gap: 48px; margin-top: 60px; position: relative; z-index: 1;
    }
    @media (max-width: 768px) { .why-grid { grid-template-columns: 1fr; } }
    .why-item { display: flex; gap: 20px; align-items: flex-start; }
    .why-num {
      font-family: 'Playfair Display', serif;
      font-size: 2.2rem; font-weight: 700;
      color: rgba(201,168,76,0.25); line-height: 1;
      min-width: 48px; padding-top: 4px;
    }
    .why-item h4 {
      font-size: 1.05rem; font-weight: 600;
      color: var(--white); margin-bottom: 8px;
    }
    .why-item p { font-size: 0.9rem; line-height: 1.75; color: rgba(240,237,230,0.55); }

    /* ── PARTNERS (Cloud Platforms) ── */
    #platforms {
      background: var(--mist);
      text-align: center; padding: 60px 5vw;
    }
    .platform-label {
      font-size: 0.75rem; letter-spacing: 0.18em; text-transform: uppercase;
      color: var(--gray); margin-bottom: 36px; font-weight: 500;
    }
    .platform-logos {
      display: flex; align-items: center; justify-content: center;
      flex-wrap: wrap; gap: 48px;
    }
    .platform-logo {
      font-family: 'Inter', sans-serif;
      font-weight: 700; font-size: 1.15rem;
      color: #8A9BB0; letter-spacing: 0.02em;
      transition: color 0.2s;
    }
    .platform-logo:hover { color: var(--navy2); }

    /* ── CONTACT ── */
    #contact { background: var(--white); }
    .contact-wrap {
      display: grid; grid-template-columns: 1fr 1.2fr; gap: 80px; align-items: start;
    }
    @media (max-width: 900px) { .contact-wrap { grid-template-columns: 1fr; gap: 48px; } }

    .contact-info h2 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(1.6rem, 3vw, 2.4rem);
      color: var(--navy); margin-bottom: 18px; font-weight: 700;
    }
    .contact-info p {
      font-size: 0.97rem; line-height: 1.8; color: #5A7080; margin-bottom: 36px;
    }
    .contact-detail {
      display: flex; align-items: flex-start; gap: 14px;
      margin-bottom: 20px;
    }
    .contact-detail-icon {
      width: 40px; height: 40px; border-radius: 8px; flex-shrink: 0;
      background: linear-gradient(135deg, rgba(201,168,76,0.15), rgba(30,58,95,0.08));
      display: flex; align-items: center; justify-content: center;
    }
    .contact-detail-icon svg { width: 18px; height: 18px; }
    .contact-detail h5 {
      font-size: 0.78rem; text-transform: uppercase;
      letter-spacing: 0.12em; color: var(--gold);
      font-weight: 600; margin-bottom: 4px;
    }
    .contact-detail p { font-size: 0.9rem; color: var(--text); line-height: 1.5; margin: 0; }

    /* Form */
    .contact-form {
      background: #fff;
      border: 1px solid #DDE6EF;
      border-radius: 10px; padding: 44px 40px;
      box-shadow: 0 8px 32px rgba(10,22,40,0.06);
    }
    .contact-form h3 {
      font-family: 'Playfair Display', serif;
      font-size: 1.35rem; font-weight: 600;
      color: var(--navy); margin-bottom: 28px;
    }
    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
    @media (max-width: 600px) { .form-row { grid-template-columns: 1fr; } }
    .form-group { margin-bottom: 18px; }
    .form-group label {
      display: block; font-size: 0.8rem; font-weight: 600;
      letter-spacing: 0.06em; text-transform: uppercase;
      color: var(--navy2); margin-bottom: 7px;
    }
    .form-group input,
    .form-group select,
    .form-group textarea {
      width: 100%; padding: 12px 16px;
      border: 1.5px solid #D4DCE6; border-radius: 5px;
      font-family: 'Inter', sans-serif; font-size: 0.93rem; color: var(--text);
      background: #FAFBFC;
      transition: border-color 0.2s, box-shadow 0.2s;
      outline: none;
    }
    .form-group input:focus,
    .form-group select:focus,
    .form-group textarea:focus {
      border-color: var(--gold); box-shadow: 0 0 0 3px rgba(201,168,76,0.12);
      background: #fff;
    }
    .form-group textarea { resize: vertical; min-height: 110px; }
    .form-group select { appearance: none; cursor: pointer; }
    .form-submit {
      width: 100%; padding: 14px;
      background: var(--navy); color: var(--gold);
      border: none; border-radius: 5px; cursor: pointer;
      font-family: 'Inter', sans-serif;
      font-size: 0.95rem; font-weight: 600;
      letter-spacing: 0.04em; text-transform: uppercase;
      transition: background 0.2s, transform 0.2s;
      margin-top: 6px;
    }
    .form-submit:hover { background: var(--navy2); transform: translateY(-1px); }
    .form-submit:disabled { opacity: 0.6; cursor: not-allowed; transform: none; }

    .form-status {
      margin-top: 14px; padding: 12px 16px;
      border-radius: 5px; font-size: 0.9rem;
      display: none;
    }
    .form-status.success {
      background: #E8F5E9; color: #2E7D32;
      border: 1px solid #A5D6A7; display: block;
    }
    .form-status.error {
      background: #FFEBEE; color: #C62828;
      border: 1px solid #EF9A9A; display: block;
    }
    .s3-note {
      font-size: 0.78rem; color: var(--gray);
      margin-top: 12px; line-height: 1.5;
      padding: 10px 14px; background: #F5F8FB;
      border-radius: 4px; border-left: 3px solid var(--gold);
    }

    /* ── FOOTER ── */
    footer {
      background: var(--navy);
      padding: 60px 5vw 32px;
      border-top: 1px solid rgba(201,168,76,0.15);
    }
    .footer-top {
      display: grid; grid-template-columns: 1.5fr 1fr 1fr 1fr;
      gap: 48px; margin-bottom: 48px;
    }
    @media (max-width: 900px) { .footer-top { grid-template-columns: 1fr 1fr; } }
    @media (max-width: 600px) { .footer-top { grid-template-columns: 1fr; } }
    .footer-brand p {
      font-size: 0.88rem; line-height: 1.75;
      color: rgba(240,237,230,0.45); margin-top: 16px; max-width: 260px;
    }
    .footer-col h5 {
      font-size: 0.75rem; text-transform: uppercase;
      letter-spacing: 0.16em; color: var(--gold);
      font-weight: 600; margin-bottom: 18px;
    }
    .footer-col ul { list-style: none; }
    .footer-col ul li { margin-bottom: 10px; }
    .footer-col ul a {
      color: rgba(240,237,230,0.45);
      text-decoration: none; font-size: 0.87rem;
      transition: color 0.2s;
    }
    .footer-col ul a:hover { color: var(--white); }
    .footer-bottom {
      border-top: 1px solid rgba(255,255,255,0.08);
      padding-top: 28px;
      display: flex; justify-content: space-between; align-items: center;
      flex-wrap: wrap; gap: 12px;
    }
    .footer-bottom p { font-size: 0.82rem; color: rgba(240,237,230,0.3); }
    .footer-bottom span { color: var(--gold); }

    /* ── RESPONSIVE NAV ── */
    @media (max-width: 768px) {
      .nav-links { display: none; }
      .hero-stats { gap: 20px; }
      .stat { flex: 0 0 45%; margin-right: 0; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <a class="nav-logo" href="#">
      <svg class="nav-logo-icon" viewBox="0 0 38 38" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle cx="19" cy="19" r="18" stroke="#C9A84C" stroke-width="1.5"/>
        <path d="M10 22 Q14 12 19 14 Q24 16 24 20 Q27 14 30 18" stroke="#C9A84C" stroke-width="2" fill="none" stroke-linecap="round"/>
        <path d="M8 26 Q14 18 19 22 Q24 26 30 22" stroke="#1E3A5F" stroke-width="2.5" fill="none" stroke-linecap="round" opacity="0"/>
        <circle cx="19" cy="19" r="4" fill="rgba(201,168,76,0.18)" stroke="#C9A84C" stroke-width="1"/>
        <path d="M19 7 L19 11 M19 27 L19 31 M7 19 L11 19 M27 19 L31 19" stroke="#C9A84C" stroke-width="1" stroke-linecap="round" opacity="0.5"/>
      </svg>
      <span class="nav-logo-text">True<span>Cloud</span>Arabia</span>
    </a>
    <ul class="nav-links">
      <li><a href="#services">Services</a></li>
      <li><a href="#why">Why Us</a></li>
      <li><a href="#platforms">Platforms</a></li>
      <li><a href="#contact" class="nav-cta">Contact Us</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section id="hero">
    <div id="hero-pattern"></div>
    <div style="width:100%; position:relative; z-index:2;">
      <div class="hero-content">
        <div class="hero-eyebrow">Trusted Cloud Partner · Kingdom of Saudi Arabia & GCC</div>
        <h1 class="hero-headline">
          Elevating Enterprises<br>Through <em>Cloud Transformation</em>
        </h1>
        <p class="hero-sub">
          TrueCloudArabia delivers end-to-end cloud migration, application modernization, and managed staffing solutions — purpose-built for organizations across the Arabian Peninsula.
        </p>
        <div class="hero-actions">
          <a href="#contact" class="btn-primary">Start Your Journey</a>
          <a href="#services" class="btn-ghost">Explore Services</a>
        </div>
      </div>
      <div class="hero-stats">
        <div class="stat">
          <div class="stat-num">200+</div>
          <div class="stat-label">Migrations Delivered</div>
        </div>
        <div class="stat">
          <div class="stat-num">98%</div>
          <div class="stat-label">Client Satisfaction</div>
        </div>
        <div class="stat">
          <div class="stat-num">50+</div>
          <div class="stat-label">Certified Engineers</div>
        </div>
        <div class="stat">
          <div class="stat-num">6</div>
          <div class="stat-label">GCC Countries Served</div>
        </div>
      </div>
    </div>
  </section>

  <!-- PLATFORMS -->
  <div id="platforms">
    <p class="platform-label">Certified Partnership Across Leading Cloud Platforms</p>
    <div class="platform-logos">
      <span class="platform-logo">Amazon Web Services</span>
      <span class="platform-logo">Microsoft Azure</span>
      <span class="platform-logo">Google Cloud</span>
      <span class="platform-logo">Oracle Cloud</span>
      <span class="platform-logo">IBM Cloud</span>
    </div>
  </div>

  <!-- SERVICES -->
  <section id="services">
    <div class="services-header">
      <p class="section-tag">What We Do</p>
      <h2 class="section-title">Comprehensive Cloud &amp;<br>Technology Services</h2>
      <p class="section-intro">From strategy through execution, TrueCloudArabia is your single partner for every stage of cloud adoption and growth.</p>
    </div>

    <div class="services-grid">

      <!-- Cloud Migration -->
      <div class="service-card">
        <div class="service-icon">
          <svg viewBox="0 0 26 26" fill="none" stroke="#C9A84C" stroke-width="1.8" stroke-linecap="round">
            <path d="M20 17a5 5 0 0 0-1-9.9A8 8 0 1 0 6 17"/>
            <polyline points="13 12 13 20 10 17"/>
            <polyline points="13 20 16 17"/>
          </svg>
        </div>
        <h3>Cloud Migration</h3>
        <p>Seamlessly migrate your on-premises workloads, servers, and data to AWS, Azure, or GCP. Our proven lift-and-shift, re-platform, and re-architect frameworks minimize downtime and risk throughout your transition.</p>
        <a href="#contact" class="service-link">Learn more →</a>
      </div>

      <!-- Application Migration -->
      <div class="service-card">
        <div class="service-icon">
          <svg viewBox="0 0 26 26" fill="none" stroke="#C9A84C" stroke-width="1.8" stroke-linecap="round">
            <rect x="3" y="3" width="9" height="9" rx="1"/>
            <rect x="14" y="3" width="9" height="9" rx="1"/>
            <rect x="3" y="14" width="9" height="9" rx="1"/>
            <path d="M17 17 h3 M19 15 v5"/>
          </svg>
        </div>
        <h3>Application Migration</h3>
        <p>Modernize legacy applications into cloud-native microservices. We refactor monolithic systems, containerize workloads with Kubernetes and Docker, and enable CI/CD pipelines for continuous delivery.</p>
        <a href="#contact" class="service-link">Learn more →</a>
      </div>

      <!-- DB Migration -->
      <div class="service-card">
        <div class="service-icon">
          <svg viewBox="0 0 26 26" fill="none" stroke="#C9A84C" stroke-width="1.8" stroke-linecap="round">
            <ellipse cx="13" cy="7" rx="9" ry="3.5"/>
            <path d="M4 7v6c0 1.93 4.03 3.5 9 3.5s9-1.57 9-3.5V7"/>
            <path d="M4 13v6c0 1.93 4.03 3.5 9 3.5s9-1.57 9-3.5v-6"/>
          </svg>
        </div>
        <h3>Database Migration</h3>
        <p>Migrate Oracle, SQL Server, MySQL, or PostgreSQL databases to cloud-managed services with zero data loss. We specialize in heterogeneous migrations, schema conversion, and post-migration optimization.</p>
        <a href="#contact" class="service-link">Learn more →</a>
      </div>

      <!-- Cloud Architecture -->
      <div class="service-card">
        <div class="service-icon">
          <svg viewBox="0 0 26 26" fill="none" stroke="#C9A84C" stroke-width="1.8" stroke-linecap="round">
            <polygon points="13 2 3 8 3 20 13 26 23 20 23 8"/>
            <polyline points="3 8 13 14 23 8"/>
            <line x1="13" y1="14" x2="13" y2="26"/>
          </svg>
        </div>
        <h3>Cloud Architecture</h3>
        <p>Design Well-Architected cloud environments built for security, performance, reliability, and cost efficiency. We deliver reference architectures, HA/DR strategies, and governance frameworks tailored to GCC compliance requirements.</p>
        <a href="#contact" class="service-link">Learn more →</a>
      </div>

      <!-- Staffing & Contracting -->
      <div class="service-card">
        <div class="service-icon">
          <svg viewBox="0 0 26 26" fill="none" stroke="#C9A84C" stroke-width="1.8" stroke-linecap="round">
            <circle cx="10" cy="8" r="4"/>
            <path d="M2 22c0-4 3.6-7 8-7"/>
            <circle cx="20" cy="15" r="3"/>
            <path d="M17 22c0-2.2 1.3-4 3-4s3 1.8 3 4"/>
          </svg>
        </div>
        <h3>IT Staffing &amp; Contracting</h3>
        <p>Augment your team with certified cloud architects, DevOps engineers, data engineers, and security specialists. We provide contract, permanent, and project-based placements across KSA, UAE, Bahrain, and Kuwait.</p>
        <a href="#contact" class="service-link">Learn more →</a>
      </div>

      <!-- Managed Services -->
      <div class="service-card">
        <div class="service-icon">
          <svg viewBox="0 0 26 26" fill="none" stroke="#C9A84C" stroke-width="1.8" stroke-linecap="round">
            <circle cx="13" cy="13" r="3"/>
            <path d="M13 2v3M13 21v3M2 13h3M21 13h3M5.6 5.6l2.1 2.1M18.3 18.3l2.1 2.1M5.6 20.4l2.1-2.1M18.3 7.7l2.1-2.1"/>
          </svg>
        </div>
        <h3>Managed Cloud Services</h3>
        <p>Offload day-to-day cloud operations with our 24×7 monitoring, incident response, patching, and cost optimization service. Focus on your business while we ensure your cloud runs at peak efficiency.</p>
        <a href="#contact" class="service-link">Learn more →</a>
      </div>

    </div>
  </section>

  <!-- WHY US -->
  <section id="why">
    <div style="position:relative;z-index:1;">
      <p class="section-tag" style="color:var(--gold-lt)">Why TrueCloudArabia</p>
      <h2 class="section-title">Regional Expertise.<br>Global Standards.</h2>
      <p class="section-intro">We combine deep GCC market knowledge with internationally certified cloud expertise to deliver outcomes others can't.</p>
    </div>
    <div class="why-grid">
      <div class="why-item">
        <div class="why-num">01</div>
        <div>
          <h4>Saudi Vision 2030 Aligned</h4>
          <p>Our solutions support digital transformation goals aligned with national strategic programmes, ensuring your modernization investment meets regulatory and government frameworks.</p>
        </div>
      </div>
      <div class="why-item">
        <div class="why-num">02</div>
        <div>
          <h4>Multi-Cloud Agnostic</h4>
          <p>Certified across AWS, Azure, GCP, and Oracle Cloud, we recommend and implement the best platform for your workload — no vendor bias, only the right fit.</p>
        </div>
      </div>
      <div class="why-item">
        <div class="why-num">03</div>
        <div>
          <h4>Data Residency &amp; Compliance</h4>
          <p>Full understanding of NDMO, SAMA, CITC, and MOHAP data sovereignty requirements ensures your cloud architecture is compliant from day one.</p>
        </div>
      </div>
      <div class="why-item">
        <div class="why-num">04</div>
        <div>
          <h4>Bilingual Delivery Teams</h4>
          <p>Arabic and English-speaking project managers, architects, and support engineers embedded with your team for seamless communication and faster decisions.</p>
        </div>
      </div>
      <div class="why-item">
        <div class="why-num">05</div>
        <div>
          <h4>Fixed-Outcome Engagements</h4>
          <p>Clear scope, milestone-based delivery, and transparent pricing. No surprise invoices — we commit to outcomes and stand behind our work with post-go-live support.</p>
        </div>
      </div>
      <div class="why-item">
        <div class="why-num">06</div>
        <div>
          <h4>Rapid Talent Deployment</h4>
          <p>A bench of pre-screened, certified cloud professionals ready to deploy within 48–72 hours for urgent project needs and critical team augmentation across the GCC.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <div class="contact-wrap">
      <div class="contact-info">
        <p class="section-tag">Get In Touch</p>
        <h2>Let's Build Your<br>Cloud Future</h2>
        <p>Tell us about your project or challenge. Our team will respond within one business day with a tailored assessment and roadmap recommendation.</p>

        <div class="contact-detail">
          <div class="contact-detail-icon">
            <svg viewBox="0 0 18 18" fill="none" stroke="#C9A84C" stroke-width="1.6" stroke-linecap="round">
              <path d="M9 1C6.24 1 4 3.24 4 6c0 4.25 5 11 5 11s5-6.75 5-11c0-2.76-2.24-5-5-5z"/>
              <circle cx="9" cy="6" r="1.8"/>
            </svg>
          </div>
          <div>
            <h5>Headquarters</h5>
            <p>Riyadh, Kingdom of Saudi Arabia<br>GCC Regional Offices: UAE · Bahrain · Kuwait</p>
          </div>
        </div>

        <div class="contact-detail">
          <div class="contact-detail-icon">
            <svg viewBox="0 0 18 18" fill="none" stroke="#C9A84C" stroke-width="1.6" stroke-linecap="round">
              <path d="M3 3h12v10a2 2 0 01-2 2H5a2 2 0 01-2-2V3z"/>
              <path d="M3 3l6 7 6-7"/>
            </svg>
          </div>
          <div>
            <h5>Email</h5>
            <p>info@truecloudrabia.com</p>
          </div>
        </div>

        <div class="contact-detail">
          <div class="contact-detail-icon">
            <svg viewBox="0 0 18 18" fill="none" stroke="#C9A84C" stroke-width="1.6" stroke-linecap="round">
              <path d="M3 3.5A1.5 1.5 0 014.5 2h.879a1.5 1.5 0 011.415 1.004l.73 2.19a1.5 1.5 0 01-.343 1.557L6 7.9c1.156 2.1 2.9 3.844 5 5l1.15-1.18a1.5 1.5 0 011.557-.343l2.19.73A1.5 1.5 0 0117 13.62V14.5A1.5 1.5 0 0115.5 16C8.044 16 2 9.956 2 2.5A1.5 1.5 0 013 1h.5"/>
            </svg>
          </div>
          <div>
            <h5>Phone</h5>
            <p>+966 (0) 11 XXX XXXX</p>
          </div>
        </div>
      </div>

      <!-- FORM -->
      <div class="contact-form">
        <h3>Send Us a Message</h3>
        <div class="form-row">
          <div class="form-group">
            <label>First Name</label>
            <input type="text" id="fname" placeholder="Ahmed" required />
          </div>
          <div class="form-group">
            <label>Last Name</label>
            <input type="text" id="lname" placeholder="Al-Rashidi" required />
          </div>
        </div>
        <div class="form-row">
          <div class="form-group">
            <label>Email</label>
            <input type="email" id="email" placeholder="ahmed@company.com" required />
          </div>
          <div class="form-group">
            <label>Phone</label>
            <input type="tel" id="phone" placeholder="+966 5X XXX XXXX" />
          </div>
        </div>
        <div class="form-group">
          <label>Company</label>
          <input type="text" id="company" placeholder="Your Organization" />
        </div>
        <div class="form-group">
          <label>Service of Interest</label>
          <select id="service">
            <option value="">— Select a service —</option>
            <option>Cloud Migration</option>
            <option>Application Migration</option>
            <option>Database Migration</option>
            <option>Cloud Architecture &amp; Design</option>
            <option>IT Staffing &amp; Contracting</option>
            <option>Managed Cloud Services</option>
            <option>General Inquiry</option>
          </select>
        </div>
        <div class="form-group">
          <label>Message</label>
          <textarea id="message" placeholder="Describe your project or challenge..."></textarea>
        </div>
        <button class="form-submit" id="submit-btn" onclick="submitForm()">Send Message</button>
        <div class="form-status" id="form-status"></div>
        <p class="s3-note">
          ⚙️ <strong>Developer note:</strong> This form POSTs JSON to your S3 bucket endpoint via a pre-signed URL or API Gateway. Update the <code>S3_ENDPOINT</code> constant in the script below with your endpoint before deployment.
        </p>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="footer-top">
      <div class="footer-brand">
        <span style="font-family:'Playfair Display',serif;font-size:1.2rem;font-weight:700;color:var(--white)">True<span style="color:var(--gold)">Cloud</span>Arabia</span>
        <p>Your trusted cloud transformation partner in the Kingdom of Saudi Arabia and across the GCC. Delivering cloud excellence aligned with Vision 2030.</p>
      </div>
      <div class="footer-col">
        <h5>Services</h5>
        <ul>
          <li><a href="#services">Cloud Migration</a></li>
          <li><a href="#services">Application Migration</a></li>
          <li><a href="#services">Database Migration</a></li>
          <li><a href="#services">Cloud Architecture</a></li>
          <li><a href="#services">IT Staffing</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h5>Company</h5>
        <ul>
          <li><a href="#">About Us</a></li>
          <li><a href="#">Case Studies</a></li>
          <li><a href="#">Certifications</a></li>
          <li><a href="#">Careers</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h5>Regions</h5>
        <ul>
          <li><a href="#">Saudi Arabia</a></li>
          <li><a href="#">United Arab Emirates</a></li>
          <li><a href="#">Bahrain</a></li>
          <li><a href="#">Kuwait</a></li>
          <li><a href="#">Qatar</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>© 2025 TrueCloudArabia. All rights reserved.</p>
      <p>Built with <span>♥</span> for the Cloud</p>
    </div>
  </footer>

  <script>
    // ── S3 Form Submission ──────────────────────────────────────────────────
    // IMPORTANT: Replace this with your actual S3 pre-signed POST URL or
    // API Gateway endpoint. Two common patterns:
    //   1) API Gateway → Lambda → S3 PutObject
    //   2) S3 pre-signed POST (generated server-side)
    const S3_ENDPOINT = "https://YOUR-API-GATEWAY-OR-PRESIGNED-URL-HERE";

    async function submitForm() {
      const btn = document.getElementById("submit-btn");
      const statusEl = document.getElementById("form-status");

      const fname   = document.getElementById("fname").value.trim();
      const lname   = document.getElementById("lname").value.trim();
      const email   = document.getElementById("email").value.trim();
      const phone   = document.getElementById("phone").value.trim();
      const company = document.getElementById("company").value.trim();
      const service = document.getElementById("service").value;
      const message = document.getElementById("message").value.trim();

      if (!fname || !lname || !email || !message) {
        statusEl.className = "form-status error";
        statusEl.textContent = "Please fill in all required fields (name, email, message).";
        return;
      }

      const payload = {
        submittedAt: new Date().toISOString(),
        firstName: fname,
        lastName: lname,
        email,
        phone,
        company,
        service,
        message,
        source: "truecloudrabia.com/contact"
      };

      btn.disabled = true;
      btn.textContent = "Sending…";
      statusEl.className = "form-status";

      try {
        // If S3_ENDPOINT is not configured, simulate success for demo purposes
        if (S3_ENDPOINT.includes("YOUR-API-GATEWAY")) {
          await new Promise(r => setTimeout(r, 1200)); // simulate network
          console.log("Form payload (demo):", payload);
          statusEl.className = "form-status success";
          statusEl.textContent = "✅ Thank you! Your message has been received. We'll be in touch within one business day.";
          clearForm();
        } else {
          const res = await fetch(S3_ENDPOINT, {
            method: "POST",
            headers: { "Content-Type": "application/json" },
            body: JSON.stringify(payload)
          });
          if (!res.ok) throw new Error(`HTTP ${res.status}`);
          statusEl.className = "form-status success";
          statusEl.textContent = "✅ Thank you! Your message has been received. We'll be in touch within one business day.";
          clearForm();
        }
      } catch (err) {
        statusEl.className = "form-status error";
        statusEl.textContent = "⚠️ Something went wrong. Please email us directly at info@truecloudrabia.com";
        console.error(err);
      } finally {
        btn.disabled = false;
        btn.textContent = "Send Message";
      }
    }

    function clearForm() {
      ["fname","lname","email","phone","company","message"].forEach(id => {
        document.getElementById(id).value = "";
      });
      document.getElementById("service").selectedIndex = 0;
    }

    // Smooth nav highlight on scroll
    const sections = document.querySelectorAll("section[id]");
    window.addEventListener("scroll", () => {
      let current = "";
      sections.forEach(sec => {
        if (window.scrollY >= sec.offsetTop - 100) current = sec.id;
      });
      document.querySelectorAll(".nav-links a").forEach(a => {
        a.style.color = a.getAttribute("href") === `#${current}`
          ? "var(--gold)" : "";
      });
    });
  </script>
</body>
</html>
