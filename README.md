<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Online Philosophy Courses | Peterson Academy</title>
  <meta name="description" content="Online philosophy courses for people who want to think clearly. Serious education, rigorous structure, and intellectual standards." />

  <!-- Fonts (single-file but externally hosted) -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=EB+Garamond:wght@500;600;700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">

  <style>
    :root{
      /* Keep your general palette (dark + red accent), refine neutrals */
      --bg: #0b0d10;
      --bg-2: #0f1217;
      --surface: #121621;
      --surface-2: #161b26;

      --text: rgba(255,255,255,0.92);
      --muted: rgba(255,255,255,0.72);
      --subtle: rgba(255,255,255,0.58);

      --ink: #0b0d10; /* for light surfaces */
      --ink-muted: #404752;

      --border: rgba(255,255,255,0.10);
      --border-2: rgba(0,0,0,0.10);

      --brand: #c9302c;
      --brand-2: #a02622;

      --success: #32d583; /* green check */
      --shadow: 0 18px 60px rgba(0,0,0,0.45);
      --shadow-soft: 0 14px 40px rgba(0,0,0,0.18);

      --radius: 18px;
      --radius-sm: 12px;

      --container: 1100px;
      --pad: clamp(16px, 3vw, 28px);
    }

    *{ box-sizing:border-box; }
    html{ scroll-behavior:smooth; }
    body{
      margin:0;
      font-family: Inter, system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
      line-height: 1.7;
      color: var(--ink);
      background: #f7f7f8;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
    }

    a{ color: inherit; }
    a:focus-visible, button:focus-visible, summary:focus-visible{
      outline: 3px solid rgba(201,48,44,0.45);
      outline-offset: 3px;
      border-radius: 10px;
    }

    .container{
      max-width: var(--container);
      margin: 0 auto;
      padding: 0 var(--pad);
    }

    /* Skip link */
    .skip-link{
      position:absolute;
      left:-999px;
      top:auto;
      width:1px;
      height:1px;
      overflow:hidden;
    }
    .skip-link:focus{
      left: 16px;
      top: 16px;
      width:auto;
      height:auto;
      padding: 10px 12px;
      background: #fff;
      border-radius: 10px;
      box-shadow: var(--shadow-soft);
      z-index: 9999;
    }

    /* Announcement bar */
    .announce{
      background: linear-gradient(135deg, rgba(201,48,44,0.18), rgba(201,48,44,0.06));
      border-bottom: 1px solid rgba(201,48,44,0.18);
      color: rgba(255,255,255,0.9);
    }
    .announce-inner{
      background: var(--bg);
      color: var(--text);
      padding: 10px var(--pad);
      display:flex;
      gap: 10px;
      align-items:center;
      justify-content:center;
      font-size: 0.95rem;
    }
    .announce-pill{
      display:inline-flex;
      align-items:center;
      gap: 8px;
      border: 1px solid rgba(255,255,255,0.12);
      background: rgba(255,255,255,0.06);
      padding: 6px 10px;
      border-radius: 999px;
      white-space: nowrap;
    }
    .dot{
      width: 8px;
      height: 8px;
      border-radius: 99px;
      background: var(--brand);
      box-shadow: 0 0 0 6px rgba(201,48,44,0.14);
    }

    /* Header / Hero */
    header{
      position: relative;
      color: var(--text);
      background: radial-gradient(1200px 600px at 20% 0%, rgba(201,48,44,0.22), transparent 60%),
                  radial-gradient(1000px 520px at 80% 20%, rgba(255,255,255,0.08), transparent 55%),
                  linear-gradient(135deg, #090a0c 0%, #141823 55%, #0b0d10 100%);
      overflow:hidden;
      border-bottom: 1px solid rgba(255,255,255,0.10);
    }
    header::before{
      content:'';
      position:absolute;
      inset:0;
      background:
        radial-gradient(circle at 1px 1px, rgba(255,255,255,0.06) 1px, transparent 1px);
      background-size: 22px 22px;
      opacity: 0.25;
      pointer-events:none;
    }

    .nav{
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(10px);
      background: rgba(11,13,16,0.62);
      border-bottom: 1px solid rgba(255,255,255,0.10);
    }
    .nav-inner{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap: 14px;
      padding: 14px var(--pad);
      max-width: var(--container);
      margin: 0 auto;
    }

    .brandmark{
      display:flex;
      align-items:baseline;
      gap: 10px;
      text-decoration:none;
    }
    .brandmark .mark{
      width: 12px;
      height: 12px;
      border-radius: 4px;
      background: var(--brand);
      box-shadow: 0 10px 24px rgba(201,48,44,0.35);
      transform: translateY(-1px);
    }
    .brandmark .word{
      font-family: "EB Garamond", Georgia, serif;
      font-weight: 700;
      letter-spacing: 0.2px;
      font-size: 1.15rem;
      color: var(--text);
    }
    .brandmark .sub{
      font-size: 0.92rem;
      color: var(--subtle);
      font-weight: 500;
      display:none;
    }

    /* Mobile nav toggle */
    .nav-actions{ display:flex; align-items:center; gap: 10px; }
    .nav-links{
      display:none;
      gap: 14px;
      align-items:center;
    }
    .nav-links a{
      text-decoration:none;
      color: rgba(255,255,255,0.78);
      font-weight: 500;
      font-size: 0.95rem;
      padding: 8px 10px;
      border-radius: 10px;
    }
    .nav-links a:hover{
      background: rgba(255,255,255,0.06);
      color: rgba(255,255,255,0.92);
    }

    .btn{
      display:inline-flex;
      align-items:center;
      justify-content:center;
      gap: 10px;
      border-radius: 12px;
      padding: 12px 16px;
      text-decoration:none;
      font-weight: 600;
      font-size: 1rem;
      border: 1px solid transparent;
      transition: transform .18s ease, box-shadow .18s ease, background .18s ease, border-color .18s ease;
      cursor:pointer;
      user-select:none;
      white-space: nowrap;
    }
    .btn-primary{
      background: linear-gradient(135deg, var(--brand), var(--brand-2));
      color: white;
      box-shadow: 0 14px 30px rgba(201,48,44,0.22);
    }
    .btn-primary:hover{
      transform: translateY(-1px);
      box-shadow: 0 18px 40px rgba(201,48,44,0.28);
    }
    .btn-ghost{
      background: rgba(255,255,255,0.06);
      border-color: rgba(255,255,255,0.14);
      color: rgba(255,255,255,0.88);
    }
    .btn-ghost:hover{
      background: rgba(255,255,255,0.10);
      transform: translateY(-1px);
    }

    .menu-btn{
      background: rgba(255,255,255,0.06);
      border: 1px solid rgba(255,255,255,0.14);
      color: rgba(255,255,255,0.9);
      padding: 10px 12px;
      border-radius: 12px;
      cursor:pointer;
      display:inline-flex;
      align-items:center;
      gap: 8px;
      font-weight: 600;
    }
    .menu-icon{
      width: 18px; height: 12px; position: relative; display:inline-block;
    }
    .menu-icon span{
      position:absolute; left:0; right:0; height:2px; background: rgba(255,255,255,0.85); border-radius: 9px;
      transition: transform .2s ease, top .2s ease, opacity .2s ease;
    }
    .menu-icon span:nth-child(1){ top:0; }
    .menu-icon span:nth-child(2){ top:5px; }
    .menu-icon span:nth-child(3){ top:10px; }

    /* Mobile drawer */
    .drawer{
      display:none;
      border-top: 1px solid rgba(255,255,255,0.10);
      background: rgba(11,13,16,0.92);
      backdrop-filter: blur(10px);
    }
    .drawer-inner{
      max-width: var(--container);
      margin: 0 auto;
      padding: 12px var(--pad) 16px;
      display:flex;
      flex-direction:column;
      gap: 8px;
    }
    .drawer a{
      text-decoration:none;
      color: rgba(255,255,255,0.82);
      padding: 10px 12px;
      border-radius: 12px;
      border: 1px solid rgba(255,255,255,0.10);
      background: rgba(255,255,255,0.04);
    }
    .drawer a:hover{
      background: rgba(255,255,255,0.08);
    }

    .hero{
      padding: clamp(46px, 7vw, 84px) 0 clamp(34px, 6vw, 70px);
    }
    .hero-grid{
      display:grid;
      gap: 28px;
    }

    h1{
      font-family: "EB Garamond", Georgia, serif;
      font-weight: 700;
      letter-spacing: 0.2px;
      font-size: clamp(2.05rem, 5vw, 3.25rem);
      line-height: 1.08;
      margin: 0 0 16px;
    }
    .subhead{
      margin: 0 0 22px;
      font-size: clamp(1.04rem, 2.2vw, 1.2rem);
      line-height: 1.75;
      color: rgba(255,255,255,0.78);
      max-width: 68ch;
    }
    .hero-ctas{
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
      align-items:center;
      margin: 18px 0 18px;
    }

    .proof-bar{
      display:flex;
      flex-wrap:wrap;
      gap: 10px;
      padding: 0;
      margin: 16px 0 0;
      list-style:none;
    }
    .proof-pill{
      display:inline-flex;
      align-items:center;
      gap: 8px;
      padding: 10px 12px;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,0.12);
      background: rgba(255,255,255,0.06);
      color: rgba(255,255,255,0.84);
      font-size: 0.95rem;
      line-height: 1.2;
    }
    .check{
      width: 18px; height: 18px;
      border-radius: 999px;
      background: rgba(50,213,131,0.14);
      border: 1px solid rgba(50,213,131,0.34);
      display:inline-flex;
      align-items:center;
      justify-content:center;
      color: var(--success);
      font-weight: 800;
      font-size: 0.9rem;
    }

    /* A compact tuition card to modernize the hero without changing copy */
    .tuition{
      background: linear-gradient(135deg, rgba(255,255,255,0.06), rgba(255,255,255,0.03));
      border: 1px solid rgba(255,255,255,0.12);
      border-radius: var(--radius);
      box-shadow: 0 18px 60px rgba(0,0,0,0.35);
      padding: 18px 18px 16px;
    }
    .tuition-top{
      display:flex;
      align-items:flex-start;
      justify-content:space-between;
      gap: 10px;
      margin-bottom: 10px;
    }
    .tuition-title{
      font-weight: 700;
      color: rgba(255,255,255,0.92);
      margin: 0;
      font-size: 1rem;
    }
    .tuition-price{
      font-family: "EB Garamond", Georgia, serif;
      font-weight: 700;
      font-size: 1.8rem;
      margin: 0;
      color: rgba(255,255,255,0.96);
      line-height: 1.1;
    }
    .tuition-note{
      margin: 0 0 14px;
      color: rgba(255,255,255,0.70);
      font-size: 0.95rem;
    }
    .tuition-list{
      margin: 0;
      padding: 0;
      list-style:none;
      display:grid;
      gap: 10px;
    }
    .tuition-list li{
      display:flex;
      gap: 10px;
      align-items:flex-start;
      color: rgba(255,255,255,0.82);
      font-size: 0.98rem;
      line-height: 1.45;
    }
    .tuition-list li .check{ flex: 0 0 auto; }

    /* Main */
    main{
      background: #fff;
    }
    .section{
      padding: clamp(44px, 6vw, 86px) 0;
      border-bottom: 1px solid rgba(0,0,0,0.08);
    }
    .section:last-child{ border-bottom:none; }
    .section-alt{
      background: #f6f6f7;
    }

    .section-head{
      max-width: 78ch;
      margin-bottom: 28px;
    }

    h2{
      font-family: "EB Garamond", Georgia, serif;
      font-size: clamp(1.75rem, 3.2vw, 2.6rem);
      line-height: 1.15;
      margin: 0 0 10px;
      color: #111318;
      letter-spacing: 0.15px;
    }
    p{
      margin: 0 0 16px;
      font-size: 1.08rem;
      color: #2b2f38;
    }

    /* Lists */
    .arrow-list{
      list-style:none;
      padding: 0;
      margin: 18px 0 24px;
      display:grid;
      gap: 10px;
      max-width: 76ch;
    }
    .arrow-list li{
      display:flex;
      gap: 10px;
      align-items:flex-start;
      padding: 12px 12px;
      border-radius: 14px;
      background: rgba(201,48,44,0.04);
      border: 1px solid rgba(201,48,44,0.10);
      color: #2b2f38;
      font-size: 1.06rem;
    }
    .arrow{
      flex: 0 0 auto;
      width: 26px;
      height: 26px;
      border-radius: 10px;
      display:inline-flex;
      align-items:center;
      justify-content:center;
      background: rgba(201,48,44,0.10);
      color: var(--brand);
      font-weight: 900;
      line-height: 1;
      margin-top: 1px;
    }

    /* Value box */
    .value-box{
      background: linear-gradient(135deg, #0b0d10 0%, #171c29 100%);
      color: var(--text);
      border-radius: var(--radius);
      padding: clamp(18px, 3.5vw, 34px);
      box-shadow: var(--shadow);
      border: 1px solid rgba(255,255,255,0.10);
      position: relative;
      overflow: hidden;
      margin-top: 22px;
    }
    .value-box::before{
      content:'';
      position:absolute;
      inset:-2px;
      background: radial-gradient(650px 240px at 15% 10%, rgba(201,48,44,0.35), transparent 60%);
      opacity: 0.65;
      pointer-events:none;
    }
    .value-box > *{ position: relative; z-index: 1; }

    .value-box h3{
      font-family: "EB Garamond", Georgia, serif;
      font-size: 1.65rem;
      margin: 0 0 12px;
      color: rgba(255,255,255,0.95);
    }

    .value-list{
      list-style:none;
      margin: 0;
      padding: 0;
      display:grid;
      gap: 10px;
      max-width: 70ch;
    }
    .value-list li{
      display:flex;
      gap: 10px;
      align-items:flex-start;
      color: rgba(255,255,255,0.86);
      font-size: 1.04rem;
      line-height: 1.45;
    }
    .pricing{
      margin-top: 16px;
      font-weight: 800;
      font-size: clamp(1.25rem, 2.4vw, 1.65rem);
      color: rgba(50,213,131,0.95);
    }

    /* Start-here callout */
    .callout{
      margin-top: 22px;
      padding: 18px 18px;
      border-radius: var(--radius);
      background: #fff;
      border: 1px solid rgba(0,0,0,0.10);
      box-shadow: var(--shadow-soft);
      position: relative;
      overflow:hidden;
    }
    .callout::before{
      content:'';
      position:absolute;
      inset:0;
      background: linear-gradient(90deg, rgba(201,48,44,0.14), transparent 55%);
      opacity: 0.8;
      pointer-events:none;
    }
    .callout p{
      position: relative;
      margin: 0;
      font-size: 1.18rem;
      font-weight: 650;
      color: #161a22;
    }
    .callout p strong{ color: var(--brand); }

    /* Cards */
    .card{
      background: #fff;
      border: 1px solid rgba(0,0,0,0.10);
      border-radius: var(--radius);
      box-shadow: var(--shadow-soft);
    }

    .course-card{
      padding: clamp(18px, 3.2vw, 34px);
      margin-top: 18px;
      transition: transform .18s ease, border-color .18s ease, box-shadow .18s ease;
      position: relative;
    }
    .course-card:hover{
      transform: translateY(-3px);
      border-color: rgba(201,48,44,0.28);
      box-shadow: 0 22px 70px rgba(0,0,0,0.14);
    }
    .course-card h3{
      margin: 0 0 10px;
      font-family: "EB Garamond", Georgia, serif;
      font-size: clamp(1.35rem, 2.2vw, 1.7rem);
      line-height: 1.2;
      color: var(--brand);
      letter-spacing: 0.15px;
    }
    .takeaway{
      margin-top: 14px;
      padding: 14px 14px;
      border-radius: 14px;
      background: rgba(0,0,0,0.03);
      border-left: 4px solid var(--brand);
      color: #2b2f38;
      font-style: italic;
    }

    /* FAQ as details accordion */
    .faq{
      display:grid;
      gap: 12px;
      margin-top: 18px;
    }
    details{
      background: #fff;
      border: 1px solid rgba(0,0,0,0.10);
      border-radius: var(--radius);
      box-shadow: var(--shadow-soft);
      overflow:hidden;
    }
    summary{
      list-style:none;
      cursor:pointer;
      padding: 16px 18px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap: 16px;
    }
    summary::-webkit-details-marker{ display:none; }
    .q{
      font-family: "EB Garamond", Georgia, serif;
      font-weight: 700;
      font-size: 1.35rem;
      line-height: 1.2;
      color: var(--brand);
      margin: 0;
    }
    .chev{
      width: 36px;
      height: 36px;
      border-radius: 12px;
      background: rgba(201,48,44,0.08);
      border: 1px solid rgba(201,48,44,0.16);
      display:inline-flex;
      align-items:center;
      justify-content:center;
      color: var(--brand);
      font-weight: 900;
      transition: transform .18s ease;
      flex: 0 0 auto;
    }
    details[open] .chev{ transform: rotate(180deg); }
    .answer{
      padding: 0 18px 18px;
    }

    /* Testimonials */
    .testimonial-grid{
      display:grid;
      grid-template-columns: 1fr;
      gap: 14px;
      margin-top: 18px;
    }
    .testimonial{
      padding: 18px 18px;
      border-radius: var(--radius);
      border: 1px solid rgba(0,0,0,0.10);
      background: #fff;
      box-shadow: var(--shadow-soft);
      color: #2b2f38;
      font-style: italic;
      position: relative;
      overflow:hidden;
    }
    .testimonial::before{
      content: """;
      position:absolute;
      top: 8px;
      left: 14px;
      font-family: "EB Garamond", Georgia, serif;
      font-size: 3.4rem;
      color: rgba(201,48,44,0.22);
      line-height: 1;
    }
    .testimonial p{
      margin: 0;
      padding-left: 10px;
      color: #2b2f38;
    }

    /* Closing CTA */
    .closing-cta{
      background: radial-gradient(900px 520px at 20% 0%, rgba(255,255,255,0.18), transparent 60%),
                  linear-gradient(135deg, var(--brand) 0%, var(--brand-2) 100%);
      color: white;
      text-align:center;
      padding: clamp(54px, 7vw, 104px) 0;
      position: relative;
      overflow:hidden;
    }
    .closing-cta::before{
      content:'';
      position:absolute;
      inset:0;
      background:
        radial-gradient(circle at 1px 1px, rgba(255,255,255,0.12) 1px, transparent 1px);
      background-size: 24px 24px;
      opacity: 0.22;
      pointer-events:none;
    }
    .closing-cta .container{ position: relative; z-index: 1; }
    .closing-cta h2{
      color: rgba(255,255,255,0.98);
      margin-bottom: 12px;
      font-size: clamp(1.6rem, 3.2vw, 2.35rem);
    }
    .closing-cta p{
      color: rgba(255,255,255,0.92);
      max-width: 80ch;
      margin: 0 auto 14px;
      font-size: 1.12rem;
    }
    .cta-secondary{
      background: #ffffff;
      color: var(--brand);
      border: 1px solid rgba(255,255,255,0.8);
      box-shadow: 0 18px 50px rgba(0,0,0,0.18);
    }
    .cta-secondary:hover{
      transform: translateY(-1px);
      box-shadow: 0 22px 60px rgba(0,0,0,0.22);
      background: #f6f6f6;
    }
    .guarantee{
      margin-top: 14px;
      font-size: 0.98rem;
      opacity: 0.95;
    }

    /* Footer-ish micro line */
    .micro{
      padding: 18px 0;
      background: #0b0d10;
      color: rgba(255,255,255,0.65);
      font-size: 0.95rem;
      border-top: 1px solid rgba(255,255,255,0.10);
      text-align:center;
    }

    /* Responsive enhancements */
    @media (min-width: 860px){
      .brandmark .sub{ display:inline; }
      .nav-links{ display:flex; }
      .menu-btn{ display:none; }
      .hero-grid{
        grid-template-columns: 1.15fr 0.85fr;
        align-items: start;
        gap: 34px;
      }
      .testimonial-grid{
        grid-template-columns: repeat(2, 1fr);
        gap: 16px;
      }
    }

    @media (prefers-reduced-motion: reduce){
      html{ scroll-behavior:auto; }
      *{ transition:none !important; }
    }
  </style>
</head>

<body>
  <a class="skip-link" href="#main">Skip to content</a>

  <header>
    <div class="nav" role="navigation" aria-label="Primary">
      <div class="nav-inner">
        <a class="brandmark" href="#">
          <span class="mark" aria-hidden="true"></span>
          <span class="word">Peterson Academy</span>
          <span class="sub">— Philosophy</span>
        </a>

        <div class="nav-actions">
          <nav class="nav-links" aria-label="On-page links">
            <a href="#problem">The Problem</a>
            <a href="#value">What You Get</a>
            <a href="#courses">Featured Courses</a>
            <a href="#faq">FAQ</a>
          </nav>

          <a href="#" class="btn btn-primary">Join</a>

          <button class="menu-btn" id="menuBtn" aria-expanded="false" aria-controls="drawer">
            <span class="menu-icon" aria-hidden="true">
              <span></span><span></span><span></span>
            </span>
            Menu
          </button>
        </div>
      </div>

      <div class="drawer" id="drawer">
        <div class="drawer-inner">
          <a href="#problem">The Problem</a>
          <a href="#value">What You Get</a>
          <a href="#courses">Featured Courses</a>
          <a href="#faq">FAQ</a>
        </div>
      </div>
    </div>

    <div class="hero">
      <div class="container">
        <div class="hero-grid">
          <div>
            <h1>Online Philosophy Courses for People Who Want to Think Clearly</h1>
            <p class="subhead">
              If you've been searching for <strong>philosophy courses online</strong> because you want more than opinions,
              you are in the right place. Peterson Academy is built for serious learners who want structure, depth,
              and intellectual standards that are getting harder to find.
            </p>

            <div class="hero-ctas">
              <a href="#" class="btn btn-primary">Join Peterson Academy</a>
              <a href="#courses" class="btn btn-ghost">Explore featured courses</a>
            </div>

            <ul class="proof-bar" aria-label="Key membership details">
              <li class="proof-pill"><span class="check" aria-hidden="true">✓</span>$399/year, billed annually</li>
              <li class="proof-pill"><span class="check" aria-hidden="true">✓</span>14-day money-back guarantee</li>
              <li class="proof-pill"><span class="check" aria-hidden="true">✓</span>4 new courses monthly</li>
              <li class="proof-pill"><span class="check" aria-hidden="true">✓</span>67,000+ students enrolled</li>
            </ul>
          </div>

          <aside class="tuition" aria-label="Tuition summary">
            <div class="tuition-top">
              <p class="tuition-title">Annual Membership</p>
              <p class="tuition-price">$399<span style="font-size:0.9rem; font-family:Inter, sans-serif; font-weight:600; color: rgba(255,255,255,0.72);"> /year</span></p>
            </div>
            <p class="tuition-note">(Billed annually)</p>
            <ul class="tuition-list">
              <li><span class="check" aria-hidden="true">✓</span><span>Full access to current and future courses for one year</span></li>
              <li><span class="check" aria-hidden="true">✓</span><span>New courses added monthly</span></li>
              <li><span class="check" aria-hidden="true">✓</span><span>Optional testing (for learners who want accountability)</span></li>
              <li><span class="check" aria-hidden="true">✓</span><span>14-day money-back guarantee</span></li>
            </ul>
          </aside>
        </div>
      </div>
    </div>
  </header>

  <main id="main">
    <!-- Problem/Solution Section -->
    <section class="section" id="problem">
      <div class="container">
        <div class="section-head">
          <h2>The Problem This Solves</h2>
          <p>You can absorb philosophy like trivia and remain essentially unchanged.</p>
          <p>Or you can study it the way it was meant to be studied, as training for your mind.</p>
          <p>Philosophy is the discipline that teaches you to:</p>
        </div>

        <ul class="arrow-list">
          <li><span class="arrow" aria-hidden="true">→</span>detect bad reasoning before it becomes a bad life decision</li>
          <li><span class="arrow" aria-hidden="true">→</span>separate what is true from what is merely persuasive</li>
          <li><span class="arrow" aria-hidden="true">→</span>speak with clarity instead of vague confidence</li>
          <li><span class="arrow" aria-hidden="true">→</span>build a worldview you can defend under pressure</li>
        </ul>

        <p>If you want to <strong>study philosophy online</strong>, the main challenge is not access to content.
          There is endless content.</p>
        <p>The challenge is finding an education that is coherent, rigorous, and strong enough to improve how you think.</p>
        <p><strong>That is what Peterson Academy is built for.</strong></p>
      </div>
    </section>

    <!-- Value Section -->
    <section class="section section-alt" id="value">
      <div class="container">
        <div class="section-head">
          <h2>What You're Actually Buying</h2>
          <p>Peterson Academy is an annual membership that gives you access to the full library of courses,
            plus all new releases.</p>
          <p>You are not buying one class. You are buying a year of serious education and a system you can
            return to again and again.</p>
        </div>

        <div class="value-box">
          <h3>What's Included:</h3>
          <ul class="value-list">
            <li><span class="check" aria-hidden="true">✓</span><span>Full access to current and future courses for one year</span></li>
            <li><span class="check" aria-hidden="true">✓</span><span>New courses added monthly</span></li>
            <li><span class="check" aria-hidden="true">✓</span><span>Optional testing (for learners who want accountability)</span></li>
            <li><span class="check" aria-hidden="true">✓</span><span>14-day money-back guarantee</span></li>
          </ul>
          <div class="pricing">Annual tuition: $399/year billed annually</div>
        </div>
      </div>
    </section>

    <!-- Start Here Section -->
    <section class="section" id="start">
      <div class="container">
        <div class="section-head">
          <h2>Start Here</h2>
          <p>If you are looking for an <strong>intro to philosophy course</strong>, start with the tool that makes
            everything else easier.</p>
        </div>

        <div class="callout" role="note" aria-label="Suggested learning path">
          <p><strong>Start with Logic.</strong> Then choose your direction: Ancient foundations, Plato, Nietzsche, and the philosophy of religion.</p>
        </div>

        <p style="margin-top:18px;">
          This "track" is designed to meet the intent behind searches like online philosophy courses, philosophy course online,
          study philosophy online, intro to philosophy course, and yes—philosophy certificate online / philosophy degree online.
        </p>
        <p><strong>You will not be treated like a child. You will be trained like an adult.</strong></p>
      </div>
    </section>

    <!-- Featured Courses -->
    <section class="section section-alt" id="courses">
      <div class="container">
        <div class="section-head">
          <h2>Featured Courses</h2>
        </div>

        <article class="course-card card">
          <h3>1) Logic | Dr. Stephen Hicks</h3>
          <p>Most people do not lose arguments because they are stupid. They lose because they do not know what an argument is.</p>
          <p>In <strong>Logic</strong>, a ten-hour course, Dr. Stephen Hicks guides you through the principles and real-world
            applications of reasoning, from foundational concepts through advanced logical systems. You learn argument structure,
            concept formation, fallacies, syllogisms, and both deductive and inductive logic.</p>
          <div class="takeaway">
            <strong>What this gives you:</strong> clearer thinking, clearer writing, and the ability to recognize when a
            confident claim is resting on nothing.
          </div>
        </article>

        <article class="course-card card">
          <h3>2) Ancient Philosophy | Dr. James Orr</h3>
          <p>If you want to understand Western thought, you start where it starts.</p>
          <p>In <strong>Ancient Philosophy</strong>, a seven-hour course, Dr. James Orr explores the foundations of Greek thought,
            moving from the Ionian and Eleatic schools through Plato and Aristotle, and into Stoicism and Epicureanism. Along the way,
            you track the birth of the big concepts that still shape modern life: metaphysics, epistemology, and ethics.</p>
          <div class="takeaway">
            <strong>What this gives you:</strong> a foundation that makes modern debates intelligible.
          </div>
        </article>

        <article class="course-card card">
          <h3>3) Plato: The Dawn of Thought | Dr. James Orr</h3>
          <p>Plato is not "old material." Plato is a live wire running underneath the modern world.</p>
          <p>In <strong>Plato: The Dawn of Thought</strong>, Dr. Orr explores Plato's intellectual world, the Dialogues,
            Socrates' method, and Plato's Theory of Forms. The course covers Plato's vision of the ideal city-state and traces
            the afterlife of his ideas through later thinkers and traditions.</p>
          <div class="takeaway">
            <strong>What this gives you:</strong> a higher standard for truth, knowledge, and meaning.
          </div>
        </article>

        <article class="course-card card">
          <h3>4) Introduction to Nietzsche | Dr. Jordan B. Peterson</h3>
          <p>Many people search "Nietzsche course" because they feel the modern world is drifting toward cynicism and confusion,
            and they want to understand why.</p>
          <p>In <strong>Introduction to Nietzsche</strong>, an eight-hour course, Dr. Peterson examines Nietzsche's life and
            enduring influence. The course covers the will to power, Nietzsche's critique of truth and morality, and the challenge
            of affirming life in the face of nihilism.</p>
          <div class="takeaway">
            <strong>What this gives you:</strong> clarity about nihilism, morality, and the cost of self-deception.
          </div>
        </article>

        <article class="course-card card">
          <h3>5) The Philosophy of Religion | Dr. James Orr</h3>
          <p>Even people who think they have "moved beyond religion" are often living inside religious assumptions they do not understand.</p>
          <p>In <strong>The Philosophy of Religion</strong>, an eight-hour course, Dr. Orr examines classic arguments for God's existence,
            major challenges like the problem of evil and the Euthyphro dilemma, and the nature of religious experience. The course closes
            by examining how religious frameworks address the modern meaning crisis through narrative unity and existential answers.</p>
          <div class="takeaway">
            <strong>What this gives you:</strong> a serious grasp of the religious question, whether you are a believer, skeptic,
            or somewhere in between.
          </div>
        </article>
      </div>
    </section>

    <!-- FAQ / Objections -->
    <section class="section" id="faq">
      <div class="container">
        <div class="section-head">
          <h2>Your Questions, Answered</h2>
        </div>

        <div class="faq" role="list">
          <details role="listitem">
            <summary>
              <span class="q">"Why is it $399 per year?"</span>
              <span class="chev" aria-hidden="true">⌄</span>
            </summary>
            <div class="answer">
              <p>Because the Academy is built to be accessible without diluting standards.</p>
              <p>One university course can cost more than an entire year of Peterson Academy. Here, $399 buys breadth, depth,
                and the ability to study at your own pace across a growing library of serious courses.</p>
              <p>Also, you do not have to "finish the semester." You can use this immediately. Start tonight with Logic and
                feel the difference within the first hour.</p>
            </div>
          </details>

          <details role="listitem">
            <summary>
              <span class="q">"Is Peterson Academy accredited?"</span>
              <span class="chev" aria-hidden="true">⌄</span>
            </summary>
            <div class="answer">
              <p>We are not currently accredited. We are pursuing accreditation in a number of jurisdictions. However, we are not
                willing to compromise the technical merits, originality or quality of our education to meet the requirements of any
                ideologically compromised "expert" body.</p>
              <p style="margin-top: 12px;"><strong>Plain-English guidance:</strong><br>
                If you need an accredited degree for licensure or a formal credential requirement, Peterson Academy may not be the right
                tool for that specific job.<br>
                If you want a serious education that makes you more articulate, more competent, and harder to manipulate, it is exactly
                the right tool.</p>
            </div>
          </details>
        </div>
      </div>
    </section>

    <!-- Testimonials -->
    <section class="section section-alt" id="testimonials">
      <div class="container">
        <div class="section-head">
          <h2>What Members Are Saying</h2>
        </div>

        <div class="testimonial-grid">
          <div class="testimonial"><p>These courses have fundamentally changed how I approach complex problems. The Logic course alone was worth the entire membership fee.</p></div>
          <div class="testimonial"><p>I've taken philosophy classes at university, but this is different. The instructors don't talk down to you, and the material is genuinely challenging in the best way.</p></div>
          <div class="testimonial"><p>After years of consuming surface-level content, Peterson Academy feels like finally getting access to the real thing. My thinking has become sharper and more precise.</p></div>
          <div class="testimonial"><p>The quality of instruction is extraordinary. Dr. Orr and Dr. Hicks make complex ideas accessible without dumbing them down. This is education for adults.</p></div>
          <div class="testimonial"><p>I can pace myself and revisit lectures as needed. The optional testing keeps me accountable, and the monthly additions mean I'm always learning something new.</p></div>
        </div>
      </div>
    </section>
  </main>

  <!-- Closing CTA -->
  <section class="closing-cta">
    <div class="container">
      <h2>Stop Waiting for the "Right Time"</h2>
      <p>If you've been looking for <strong>online philosophy courses</strong> because you know your mind could be sharper,
        stop waiting for the "right time." The right time is when you notice the cost of confusion.</p>
      <p>Join Peterson Academy today. Start with Logic. Build a mind that can carry weight.</p>
      <a href="#" class="btn cta-secondary">Join Peterson Academy (Annual Membership)</a>
      <p class="guarantee">14-day money-back guarantee</p>
    </div>
  </section>

  <div class="micro">
    © <span id="year"></span> Peterson Academy
  </div>

  <script>
    // Mobile drawer toggle + close on link click
    const btn = document.getElementById('menuBtn');
    const drawer = document.getElementById('drawer');

    function setOpen(open){
      drawer.style.display = open ? 'block' : 'none';
      btn.setAttribute('aria-expanded', String(open));
    }

    btn?.addEventListener('click', () => {
      const isOpen = btn.getAttribute('aria-expanded') === 'true';
      setOpen(!isOpen);
    });

    drawer?.querySelectorAll('a').forEach(a => {
      a.addEventListener('click', () => setOpen(false));
    });

    // Footer year
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
