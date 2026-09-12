<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Daftuar Technology: Web Development, Business Software, Support and Maintenance.">
  <title>Daftuar Technology | Smart Digital Solutions</title>
  <style>
    :root {
      --bg: #061827;
      --bg-soft: #0b1f32;
      --panel: rgba(12, 25, 39, 0.92);
      --panel-strong: #102744;
      --primary: #1ca6ff;
      --primary-deep: #0a7ae9;
      --accent: #7bd6ff;
      --line: rgba(114, 173, 255, 0.2);
      --text: #b7d4ee;
      --white: #edf8ff;
      --muted: #81a8ce;
      --success: #58d99d;
      --shadow: 0 25px 60px rgba(7, 17, 29, 0.42);
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      color: var(--white);
      background:
        radial-gradient(circle at top right, rgba(28, 166, 255, 0.2), transparent 25%),
        linear-gradient(180deg, #061827 0%, #071b2f 35%, #061827 100%);
    }

    a { text-decoration: none; }
    .container { width: min(1140px, calc(100% - 42px)); margin: auto; }

    /* Navigation */
    .top {
      background:
        radial-gradient(circle at 15% 0%, rgba(28, 166, 255, 0.25), transparent 18%),
        linear-gradient(180deg, rgba(8, 25, 42, 0.95), rgba(6, 24, 39, 0.95));
      border-bottom: 1px solid var(--line);
      padding-bottom: 62px;
    }

    nav {
      height: 82px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
      position: sticky;
      top: 0;
      z-index: 20;
      backdrop-filter: blur(12px);
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 12px;
      color: var(--white);
      font-size: 18px;
      font-weight: 800;
      letter-spacing: 0.4px;
    }

    .logo span {
      width: 38px;
      height: 38px;
      display: grid;
      place-items: center;
      background: linear-gradient(135deg, var(--primary), var(--primary-deep));
      color: white;
      border-radius: 12px 12px 12px 3px;
      font-size: 21px;
      box-shadow: 0 12px 24px rgba(28, 166, 255, 0.35);
    }

    .links {
      display: flex;
      gap: 28px;
      align-items: center;
    }

    .links a {
      color: var(--muted);
      font-size: 14px;
      font-weight: 700;
      letter-spacing: 0.02em;
      transition: color 0.2s ease;
    }

    .links a:hover { color: var(--accent); }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      border-radius: 12px;
      border: 1px solid transparent;
      background: linear-gradient(135deg, var(--primary), var(--primary-deep));
      color: #fff;
      padding: 14px 20px;
      font-weight: 800;
      box-shadow: 0 20px 30px rgba(28, 166, 255, 0.22);
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    .btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 24px 34px rgba(28, 166, 255, 0.3);
    }

    .outline {
      background: transparent;
      color: var(--white);
      border-color: rgba(134, 195, 255, 0.35);
      box-shadow: none;
    }

    /* Hero */
    .hero {
      min-height: 500px;
      display: grid;
      grid-template-columns: 1.08fr .92fr;
      align-items: center;
      gap: 42px;
      padding-top: 20px;
    }

    .tag {
      display: inline-block;
      color: var(--accent);
      background: rgba(123, 214, 255, 0.08);
      border: 1px solid rgba(123, 214, 255, 0.2);
      border-radius: 999px;
      padding: 8px 14px;
      font-size: 11px;
      letter-spacing: 2px;
      text-transform: uppercase;
      font-weight: 800;
    }

    h1 {
      font-size: clamp(38px, 5vw, 62px);
      line-height: 1.02;
      letter-spacing: -2px;
      margin: 18px 0 16px;
    }

    h1 strong { color: var(--accent); }

    .hero p, .intro {
      font-size: 18px;
      line-height: 1.7;
      color: var(--text);
      max-width: 560px;
      margin: 0;
    }

    .hero-actions {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
      margin-top: 30px;
    }

    .hero-stats {
      margin-top: 28px;
      display: flex;
      gap: 16px;
      flex-wrap: wrap;
    }

    .stat {
      min-width: 130px;
      border: 1px solid var(--line);
      background: rgba(14, 31, 45, 0.7);
      border-radius: 14px;
      padding: 16px 18px;
    }

    .stat strong {
      display: block;
      font-size: 25px;
      color: var(--white);
      margin-bottom: 6px;
    }

    .stat span {
      color: var(--muted);
      font-size: 12px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      font-weight: 700;
    }

    .screen {
      background: linear-gradient(180deg, rgba(13, 29, 43, 0.96), rgba(9, 17, 29, 0.96));
      border: 1px solid rgba(150, 200, 255, 0.16);
      border-radius: 24px;
      box-shadow: var(--shadow);
      padding: 22px;
      position: relative;
      overflow: hidden;
    }

    .screen::before {
      content: "";
      position: absolute;
      inset: -40% auto auto -10%;
      width: 200px;
      height: 200px;
      background: radial-gradient(circle, rgba(28, 166, 255, 0.3), transparent 60%);
    }

    .dots { display: flex; gap: 7px; position: relative; z-index: 1; }
    .dots i { width: 9px; height: 9px; border-radius: 50%; background: #ff6d64; }
    .dots i:nth-child(2) { background: #ffc842; }
    .dots i:nth-child(3) { background: #31c774; }

    .screen small {
      display: block;
      margin: 26px 0 16px;
      color: #d5ebff;
      font-weight: 800;
      letter-spacing: 0.04em;
      position: relative;
      z-index: 1;
    }

    .bars {
      position: relative;
      z-index: 1;
      height: 190px;
      display: flex;
      align-items: flex-end;
      gap: 12px;
      background: linear-gradient(180deg, rgba(22, 38, 58, 0.7), rgba(21, 38, 56, 0.2));
      border: 1px solid rgba(119, 175, 245, 0.14);
      border-radius: 14px;
      padding: 14px 12px 0;
      overflow: hidden;
    }

    .bars b {
      flex: 1;
      background: linear-gradient(180deg, var(--accent), var(--primary));
      border-radius: 9px 9px 0 0;
      box-shadow: inset 0 1px rgba(255,255,255,0.15), 0 10px 18px rgba(28, 166, 255, 0.18);
    }

    .bars b:nth-child(1) { height: 32%; }
    .bars b:nth-child(2) { height: 48%; }
    .bars b:nth-child(3) { height: 39%; }
    .bars b:nth-child(4) { height: 68%; }
    .bars b:nth-child(5) { height: 57%; }
    .bars b:nth-child(6) { height: 92%; }

    /* Generic */
    section { padding: 92px 0; }
    .label {
      color: var(--accent);
      font-weight: 800;
      letter-spacing: 1.8px;
      text-transform: uppercase;
      font-size: 12px;
    }
    h2 {
      font-size: clamp(30px, 4vw, 42px);
      letter-spacing: -1.5px;
      margin: 12px 0 14px;
      line-height: 1.12;
    }

    /* Services */
    .services { background: rgba(9, 18, 29, 0.75); }

    .cards {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 22px;
      margin-top: 38px;
    }

    .card {
      background: linear-gradient(180deg, rgba(12, 23, 35, 0.96), rgba(10, 20, 31, 0.96));
      border: 1px solid var(--line);
      border-radius: 18px;
      padding: 28px;
      transition: transform 0.2s ease, border-color 0.2s ease;
    }

    .card:hover {
      transform: translateY(-5px);
      border-color: rgba(123, 214, 255, 0.4);
    }

    .icon {
      display: grid;
      place-items: center;
      width: 54px;
      height: 54px;
      border-radius: 14px;
      background: linear-gradient(135deg, rgba(28,166,255,0.18), rgba(10,122,233,0.28));
      border: 1px solid rgba(123, 214, 255, 0.25);
      font-size: 22px;
      margin-bottom: 22px;
    }

    .card h3 { font-size: 22px; margin: 0 0 12px; }
    .card p {
      font-size: 15px;
      color: var(--text);
      line-height: 1.7;
      margin: 0;
    }

    /* Plans */
    .plans {
      background: rgba(7, 18, 28, 0.8);
      text-align: center;
      border-top: 1px solid var(--line);
      border-bottom: 1px solid var(--line);
    }
    .plans .intro { margin: 0 auto; }

    .trial {
      margin: 34px 0 30px;
      background: linear-gradient(120deg, #0e4f9b, #0a7ae9, #2bb9ff);
      border: 1px solid rgba(122, 203, 255, 0.34);
      color: #fff;
      border-radius: 20px;
      padding: 28px 30px;
      display: grid;
      grid-template-columns: 1fr auto;
      align-items: center;
      text-align: left;
      gap: 18px;
      box-shadow: 0 18px 36px rgba(11, 122, 233, 0.22);
    }

    .trial .offer {
      font-size: 12px;
      font-weight: 800;
      letter-spacing: 1.7px;
    }
    .trial h3 { font-size: 30px; margin: 8px 0; }
    .trial p { margin: 0; color: rgba(255,255,255,0.9); }
    .trial .btn { background: #fff; color: var(--primary-deep); box-shadow: none; }

    .price-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 22px;
      text-align: left;
      margin-top: 28px;
    }

    .price-card {
      background: linear-gradient(180deg, rgba(13, 30, 45, 0.96), rgba(11, 21, 34, 0.96));
      border: 1px solid var(--line);
      border-radius: 20px;
      padding: 28px 24px;
      display: flex;
      flex-direction: column;
      min-height: 360px;
      transition: border-color 0.2s ease, transform 0.2s ease;
    }

    .price-card:hover { transform: translateY(-4px); }
    .price-card.featured {
      border: 2px solid rgba(28, 166, 255, 0.9);
      box-shadow: 0 18px 36px rgba(28, 166, 255, 0.12);
    }

    .price-card h3 { font-size: 24px; margin: 0 0 12px; }
    .price {
      font-size: 34px;
      font-weight: 800;
      margin-bottom: 18px;
      letter-spacing: -0.04em;
    }
    .price small { font-size: 14px; font-weight: 600; color: var(--text); }

    .features {
      list-style: none;
      padding: 0;
      margin: 0 0 24px;
      color: var(--text);
      line-height: 2.2;
      font-size: 15px;
    }
    .features li:before { content: '✓'; color: var(--success); font-weight: 800; margin-right: 9px; }
    .price-card .btn { margin-top: auto; text-align: center; }

    /* About */
    .about {
      display: grid;
      grid-template-columns: 0.9fr 1.1fr;
      gap: 68px;
      align-items: center;
    }

    .founder-card {
      position: relative;
      border-radius: 24px;
      overflow: hidden;
      border: 1px solid var(--line);
      box-shadow: var(--shadow);
      background: rgba(12, 25, 39, 0.8);
    }

    .founder-img {
      width: 100%;
      height: 420px;
      object-fit: cover;
      object-position: top center;
      display: block;
    }

    .founder-overlay {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      padding: 22px 20px 18px;
      background: linear-gradient(to top, rgba(6, 24, 39, 0.96), rgba(6, 24, 39, 0.15), transparent);
    }

    .founder-overlay strong {
      font-size: 26px;
      display: block;
      color: var(--white);
    }
    .founder-overlay span {
      display: block;
      color: var(--accent);
      font-weight: 700;
      font-size: 14px;
      margin-top: 4px;
    }

    .check {
      padding: 0;
      list-style: none;
      color: var(--text);
      line-height: 2.2;
      margin-top: 22px;
    }
    .check li:before { content: '✓'; color: var(--success); font-weight: 900; margin-right: 11px; }

    .legal-section {
      background: rgba(9, 19, 30, 0.88);
      border-top: 1px solid var(--line);
    }
    .legal-wrap {
      display: grid;
      grid-template-columns: 0.85fr 1.15fr;
      gap: 60px;
      align-items: center;
    }
    .legal-card {
      background: linear-gradient(180deg, rgba(15, 31, 48, 0.96), rgba(10, 19, 30, 0.96));
      border: 1px solid var(--line);
      border-radius: 22px;
      padding: 28px 24px;
      box-shadow: var(--shadow);
    }
    .lawyer-photo-wrap {
      position: relative;
      overflow: hidden;
      border-radius: 22px;
      border: 1px solid var(--line);
      background: rgba(9, 18, 29, 0.8);
      box-shadow: var(--shadow);
    }
    .lawyer-photo {
      display: block;
      width: 100%;
      height: 520px;
      object-fit: cover;
      object-position: center top;
    }
    .lawyer-label {
      position: absolute;
      left: 18px;
      right: 18px;
      bottom: 18px;
      background: rgba(6, 24, 39, 0.7);
      border: 1px solid rgba(123, 214, 255, 0.18);
      border-radius: 12px;
      padding: 12px 14px;
      backdrop-filter: blur(4px);
    }
    .lawyer-label strong {
      display: block;
      font-size: 24px;
      color: var(--white);
    }
    .lawyer-label span {
      display: block;
      color: var(--accent);
      font-size: 13px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      font-weight: 700;
      margin-top: 4px;
    }
    .legal-badge {
      display: inline-block;
      background: rgba(28, 166, 255, 0.12);
      border: 1px solid rgba(123, 214, 255, 0.25);
      color: var(--accent);
      border-radius: 999px;
      padding: 8px 12px;
      font-size: 11px;
      letter-spacing: 1.6px;
      text-transform: uppercase;
      font-weight: 800;
      margin-bottom: 18px;
    }
    .legal-card h3 {
      margin: 0 0 12px;
      font-size: 30px;
      letter-spacing: -0.04em;
    }
    .legal-card p {
      margin: 0 0 18px;
      color: var(--text);
      line-height: 1.7;
      font-size: 16px;
    }
    .legal-pills {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }
    .legal-pills span {
      background: rgba(123, 214, 255, 0.08);
      border: 1px solid rgba(123, 214, 255, 0.18);
      color: var(--white);
      border-radius: 999px;
      padding: 8px 12px;
      font-size: 12px;
      font-weight: 700;
    }

    /* Contact */
    .contact { background: rgba(6, 18, 28, 0.9); border-top: 1px solid var(--line); }
    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 70px;
      align-items: start;
    }

    .details {
      margin-top: 26px;
      color: #d3e8ff;
      line-height: 1.9;
      font-size: 17px;
    }
    .details a { color: var(--white); font-weight: 800; }

    .form {
      background: linear-gradient(180deg, rgba(15, 31, 48, 0.95), rgba(10, 20, 30, 0.95));
      border-radius: 20px;
      padding: 26px 24px;
      border: 1px solid var(--line);
      box-shadow: var(--shadow);
    }
    .form h3 { margin: 0 0 20px; font-size: 28px; }
    .form label {
      font-size: 13px;
      font-weight: 700;
      display: block;
      margin: 0 0 8px;
      color: var(--white);
    }
    .form input, .form textarea {
      width: 100%;
      padding: 13px 14px;
      background: rgba(6, 17, 28, 0.9);
      border: 1px solid rgba(117, 171, 236, 0.28);
      border-radius: 10px;
      margin-bottom: 16px;
      font: inherit;
      color: var(--white);
      outline: none;
    }
    .form input:focus, .form textarea:focus {
      border-color: rgba(123, 214, 255, 0.7);
      box-shadow: 0 0 0 3px rgba(28,166,255,0.12);
    }
    .form textarea { resize: vertical; min-height: 90px; }
    .form .btn { width: 100%; }

    /* Footer */
    footer {
      background: #020d18;
      color: #8eafcf;
      font-size: 13px;
      padding: 24px 0;
      border-top: 1px solid rgba(114, 173, 255, 0.18);
    }
    footer .container {
      display: flex;
      justify-content: space-between;
      gap: 16px;
      align-items: center;
    }

    /* Responsive */
    @media (max-width: 720px) {
      .links { display: none; }
      .hero, .about, .contact-grid, .cards, .price-grid {
        grid-template-columns: 1fr;
      }
      .trial { grid-template-columns: 1fr; text-align: center; }
      footer .container { flex-direction: column; gap: 10px; }
      .hero { padding-top: 10px; }
    }
  </style>
</head>
<body>

  <!-- Top Header & Navigation -->
  <header class="top" id="home">
    <div class="container">
      <nav>
        <a class="logo" href="#home"><span>D</span> DAFTUAR TECHNOLOGY</a>
        <div class="links">
          <a href="#services">Services</a>
          <a href="#plans">Software Plans</a>
          <a href="#about">About</a>
          <a href="#contact">Contact</a>
        </div>
        <a class="btn" href="https://wa.me/917479900660?text=HELLO%20DAFTUAR%20TECHNOLOGY" target="_blank">Let's Talk</a>
      </nav>

      <div class="hero">
        <div>
          <div class="tag">Technology that works for you</div>
          <h1>Make your business <strong>impossible to ignore.</strong></h1>
          <p>We create websites, business software, and reliable support systems to help your enterprise grow with confidence.</p>
          <div class="hero-actions">
            <a class="btn" href="https://wa.me/917479900660?text=HELLO%20DAFTUAR%20TECHNOLOGY" target="_blank">Send Hello on WhatsApp</a>
            <a class="btn outline" href="#services">Explore Services</a>
          </div>
          <div class="hero-stats">
            <div class="stat">
              <strong>3+</strong>
              <span>Years of insight</span>
            </div>
            <div class="stat">
              <strong>50+</strong>
              <span>Projects delivered</span>
            </div>
            <div class="stat">
              <strong>24/7</strong>
              <span>Support</span>
            </div>
          </div>
        </div>
        <div class="screen">
          <div class="dots"><i></i><i></i><i></i></div>
          <small>Business Growth Overview</small>
          <div class="bars">
            <b></b><b></b><b></b><b></b><b></b><b></b>
          </div>
        </div>
      </div>
    </div>
  </header>

  <!-- Services Section -->
  <section class="services" id="services">
    <div class="container">
      <div class="label">What We Do</div>
      <h2>Digital services built around your goals</h2>
      <p class="intro">Daftuar Technology brings clarity to your tools, from your online presence to your daily management systems.</p>
      
      <div class="cards">
        <article class="card">
          <div class="icon">⌘</div>
          <h3>Web Development</h3>
          <p>Modern, responsive websites that make a sharp first impression and turn visitors into active clients.</p>
        </article>
        <article class="card">
          <div class="icon">▣</div>
          <h3>Business Software</h3>
          <p>Practical software solutions designed to simplify workflows, billing, and keep operations moving.</p>
        </article>
        <article class="card">
          <div class="icon">↻</div>
          <h3>Support &amp; Maintenance</h3>
          <p>Dependable technical support and ongoing maintenance to keep your digital tools running smoothly.</p>
        </article>
      </div>
    </div>
  </section>

  <!-- Software Plans Section -->
  <section class="plans" id="plans">
    <div class="container">
      <div class="label">Software Plans</div>
      <h2>Start free, then choose the plan that fits</h2>
      <p class="intro">Simple and transparent pricing plans designed for every stage of your business growth.</p>
      
      <div class="trial">
        <div>
          <div class="offer">LIMITED-TIME OFFER</div>
          <h3>15 DAYS FREE TRIAL</h3>
          <p>Try DAFTUAR BILL before you buy. No upfront payment required to get started.</p>
        </div>
        <a class="btn" href="https://wa.me/917479900660?text=HELLO%20DAFTUAR%20TECHNOLOGY%2C%20I%20WANT%20TO%20START%20MY%2015%20DAYS%20FREE%20TRIAL" target="_blank">START FREE TRIAL</a>
      </div>

      <div class="price-grid">
        <article class="price-card">
          <h3>Basic</h3>
          <div class="price">₹999 <small>/ year</small></div>
          <ul class="features">
            <li>Billing Management</li>
            <li>Basic Inventory</li>
            <li>Invoice Generation</li>
            <li>Basic Reports</li>
          </ul>
          <a class="btn outline" href="https://wa.me/917479900660?text=HELLO%20DAFTUAR%20TECHNOLOGY%2C%20I%20AM%20INTERESTED%20IN%20THE%20BASIC%20PLAN%20(%E2%82%B9999%2FYEAR)" target="_blank">Get Started</a>
        </article>

        <article class="price-card featured">
          <h3>Professional</h3>
          <div class="price">₹3,999 <small>/ year</small></div>
          <ul class="features">
            <li>Advanced Billing</li>
            <li>Barcode &amp; Inventory</li>
            <li>Ledger &amp; Payments</li>
            <li>Advanced Reports</li>
          </ul>
          <a class="btn" href="https://wa.me/917479900660?text=HELLO%20DAFTUAR%20TECHNOLOGY%2C%20I%20AM%20INTERESTED%20IN%20THE%20PROFESSIONAL%20PLAN%20(%E2%82%B93999%2FYEAR)" target="_blank">Get Started</a>
        </article>

        <article class="price-card">
          <h3>Business</h3>
          <div class="price">₹6,999 <small>/ year</small></div>
          <ul class="features">
            <li>Complete Management</li>
            <li>Multi-User Support</li>
            <li>Business Analytics</li>
            <li>Priority Support</li>
          </ul>
          <a class="btn outline" href="https://wa.me/917479900660?text=HELLO%20DAFTUAR%20TECHNOLOGY%2C%20I%20AM%20INTERESTED%20IN%20THE%20BUSINESS%20PLAN%20(%E2%82%B96999%2FYEAR)" target="_blank">Contact Sales</a>
        </article>
      </div>
    </div>
  </section>

  <!-- About Section -->
  <section id="about">
    <div class="container about">
      <div class="founder-card">
        <img src="FOUNDER-MAYANK-DAFTUAR.JPG.png" alt="Mayank Daftuar - Founder of Daftuar Technology" class="founder-img">
        <div class="founder-overlay">
          <strong>Mayank Daftuar</strong>
          <span>Founder &amp; Owner</span>
        </div>
      </div>
      <div>
        <div class="label">Leadership</div>
        <h2>Technology with a personal commitment</h2>
        <p class="intro">Daftuar Technology is founded and led by Mayank Daftuar[cite: 1]. We believe great software should feel simple, efficient, and built for real-world impact.</p>
        <ul class="check">
          <li>Clear communication from concept to final launch</li>
          <li>Tailored technical solutions suited to your business</li>
          <li>Dedicated ongoing technical partnership post-delivery</li>
        </ul>
      </div>
    </div>
  </section>

  <section class="legal-section" id="legal">
    <div class="container legal-wrap">
      <div class="lawyer-photo-wrap">
        <img src="corporate-lawye.jpg" alt="Corporate lawyer of Daftuar Technology" class="lawyer-photo">
        <div class="lawyer-label">
          <strong>Corporate Lawyer</strong>
          <span>Legal Advisor</span>
        </div>
      </div>

      <div class="legal-card">
        <div class="legal-badge">Founder Profile</div>
        <h3>Leadership That Blends Vision with Legal Insight</h3>
        <p>Our founder leads Daftuar Technology with a strong business mindset, legal awareness, and a commitment to building sustainable digital solutions for growth-focused organizations.</p>
        <p class="intro">He is the visionary leader of the company, combining entrepreneurial direction with practical legal understanding to support business decisions and long-term trust.</p>
        <ul class="check">
          <li>Business strategy and operational leadership</li>
          <li>Legal-aware decision making for company growth</li>
          <li>Commitment to integrity, trust, and long-term value</li>
        </ul>
        <div class="legal-pills">
          <span>Leadership</span>
          <span>Strategy</span>
          <span>Business Growth</span>
          <span>Integrity</span>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section class="contact" id="contact">
    <div class="container contact-grid">
      <div>
        <div class="label">Start a Conversation</div>
        <h2>Have a project in mind? Let's build.</h2>
        <p class="intro">Tell us a bit about your business goals. We would love to collaborate with you.</p>
        <p class="details">
          Call us direct: <a href="tel:+917479900660">+91 74799 00660</a><br><br>
          Or message us directly via WhatsApp.
        </p>
        <a class="btn" style="background:var(--aqua); color:var(--navy); box-shadow:none;" href="https://wa.me/917479900660?text=HELLO%20DAFTUAR%20TECHNOLOGY" target="_blank">Send Hello on WhatsApp</a>
      </div>

      <form class="form" action="mailto:info@daftuarantechnology.com" method="post" enctype="text/plain">
        <h3>Send us a message</h3>
        <label for="name">Your Name</label>
        <input id="name" name="Name" type="text" placeholder="Enter your full name" required>

        <label for="email">Email Address</label>
        <input id="email" name="Email" type="email" placeholder="you@example.com" required>

        <label for="message">How can we help?</label>
        <textarea id="message" name="Message" placeholder="Tell us about your project or requirements"></textarea>

        <button class="btn" type="submit">Send Message</button>
      </form>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <div class="container">
      <span>© 2026 Daftuar Technology. All rights reserved.</span>
      <span>Web Development · Business Software · Support &amp; Maintenance</span>
    </div>
  </footer>

</body>
</html>
