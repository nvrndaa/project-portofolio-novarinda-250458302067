<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Portfolio — Nova Rinda</title>
  <meta name="description" content="Portfolio pribadi — Nama Anda. Web developer / designer." />
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    /* ----------------------------
       Lavender Pastel Single-file Portfolio
       3 vertical pages (About / Projects / Contact)
       ---------------------------- */
    :root{
      --lav1: #e8defa; /* top */
      --lav2: #dcd6f7; /* bottom */
      --muted: #6b6480;
      --text: #2d1b4e;
      --accent: #a78bfa;
      --accent-2:#bcd2ff;
      --card: #f6f3ff;
      --glass: rgba(167,139,250,0.08);
      --radius:16px;
      --max-w:1100px;
    }

    *{box-sizing:border-box}
    html,body{height:100%}
    body {
      margin: 0;
      font-family: 'Poppins', system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background: linear-gradient(180deg, var(--lav1) 0%, var(--lav2) 100%);
      color: var(--text);
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      line-height: 1.5;
      padding: 28px;
      display: flex;
      justify-content: center;
    }

    .wrap { width: 100%; max-width: var(--max-w); }

    /* Header */
    header {
      display:flex;
      align-items:center;
      gap:16px;
      padding:16px;
      border-radius:14px;
      margin-bottom:20px;
      background: linear-gradient(90deg, rgba(167,139,250,0.10), rgba(188,210,255,0.06));
      box-shadow: 0 8px 28px rgba(45,27,78,0.06);
      backdrop-filter: blur(6px);
    }
    .logo { display:flex; align-items:center; gap:12px }
    .logo svg { width:48px; height:48px; flex-shrink:0 }
    .brand { font-weight:700; font-size:16px; color:var(--text) }
    .meta { font-size:13px; color:var(--muted) }

    nav { margin-left:auto }
    nav a {
      color: var(--muted);
      text-decoration:none;
      margin-left:12px;
      font-size:14px;
      padding:8px;
      border-radius:10px;
      transition: all .18s ease;
    }
    nav a:hover { background:var(--glass); color:var(--accent); transform:translateY(-2px) }

    /* Page sections */
    section { min-height:100vh; padding:28px 0; display:flex; align-items:center; }
    .page { border-radius:18px; background: var(--card); box-shadow:0 10px 36px rgba(45,27,78,0.06); padding:36px; }

    /* HERO / ABOUT */
    .hero { display:grid; grid-template-columns: 1fr 420px; gap:28px; align-items:center }
    .hero h1 { font-size:34px; margin:0 0 12px; color:#3e206d }
    .lead { margin:0 0 16px; color:var(--muted); font-size:15px }
    .cta { display:flex; gap:12px; margin-top:8px }
    .btn-primary {
      background: linear-gradient(90deg, var(--accent), var(--accent-2));
      color: white;
      padding:12px 16px;
      border-radius:12px;
      text-decoration:none;
      font-weight:700;
      box-shadow: 0 10px 24px rgba(167,139,250,0.16);
    }
    .btn-ghost {
      background: transparent;
      border:1px solid rgba(220,214,255,0.6);
      color: var(--accent);
      padding:10px 14px;
      border-radius:12px;
      text-decoration:none;
      font-weight:600;
    }

    .illus { display:flex; justify-content:center; align-items:center }
    .illus .card {
      width:100%;
      height:320px;
      border-radius:14px;
      background: linear-gradient(180deg, #f4f1ff, #eef6ff);
      display:flex;
      justify-content:center;
      align-items:center;
      font-size:44px;
      color:var(--accent);
      box-shadow: 0 8px 20px rgba(45,27,78,0.05);
    }

    /* Projects */
    .projects-grid { display:grid; grid-template-columns: repeat(3, 1fr); gap:18px; margin-top:18px }
    .project {
      background: linear-gradient(180deg,#fbf9ff,#f6f3ff);
      border-radius:12px;
      padding:14px;
      border:1px solid rgba(230,225,255,0.8);
      transition: transform .22s ease, box-shadow .22s ease;
    }
    .project:hover { transform: translateY(-6px); box-shadow: 0 14px 36px rgba(45,27,78,0.08) }
    .thumb {
      height:120px;
      border-radius:10px;
      background: linear-gradient(135deg, rgba(167,139,250,0.18), rgba(188,210,255,0.12));
      display:flex; align-items:center; justify-content:center; font-size:36px; color:#fff;
      margin-bottom:10px;
    }
    .project h3 { margin:8px 0 6px; font-size:16px; color:#3e206d }
    .project p { margin:0; color:var(--muted); font-size:14px }

    /* Skills & contact */
    .two { display:grid; grid-template-columns: 1fr 360px; gap:20px; align-items:start }
    .skills { display:flex; flex-wrap:wrap; gap:10px; margin-top:10px }
    .skill {
      padding:10px 12px;
      background: linear-gradient(180deg,#efeaff,#efe8ff);
      border-radius:999px;
      font-weight:600;
      color:#3e206d;
      box-shadow: 0 6px 14px rgba(167,139,250,0.06);
    }
    .contact-card {
      padding:18px;
      border-radius:12px;
      background: linear-gradient(180deg,#fbf9ff,#f6f3ff);
      border:1px solid rgba(230,225,255,0.8);
    }
    .contact-card p { margin:8px 0; color:var(--muted) }

    .divider { height:1px; background: linear-gradient(90deg, transparent, rgba(230,225,255,0.9), transparent); margin:18px 0; border-radius:2px }

    footer { margin-top:18px; text-align:center; color:var(--muted); font-size:13px }

    /* Responsive */
    @media (max-width:1000px){
      .hero{grid-template-columns:1fr}
      .projects-grid{grid-template-columns:repeat(2,1fr)}
      .two{grid-template-columns:1fr}
    }
    @media (max-width:640px){
      .projects-grid{grid-template-columns:1fr}
      .illus .card { height:240px }
      header { padding:12px }
    }

    /* small helper */
    .tag { display:inline-block; padding:6px 8px; background:#efeaff; border-radius:8px; font-size:12px; color:#3e206d; margin-right:8px; }
  </style>
</head>
<body>
  <div class="wrap">

    <!-- HEADER -->
    <header>
      <div class="logo">
        <!-- logo svg (lavender square) -->
        <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
          <defs>
            <linearGradient id="lg" x1="0" x2="1">
              <stop offset="0" stop-color="#a78bfa"/>
              <stop offset="1" stop-color="#bcd2ff"/>
            </linearGradient>
          </defs>
          <rect width="48" height="48" rx="10" fill="url(#lg)"/>
          <g transform="translate(8,8)" fill="#fff">
            <path d="M8 0c3.3 0 6 2.7 6 6s-2.7 6-6 6S2 9.3 2 6 4.7 0 8 0z" opacity="0.95"/>
            <path d="M0 6c0 3.3 2.7 6 6 6s6-2.7 6-6S9.3 0 6 0 0 2.7 0 6z" transform="translate(8,2)" opacity="0.9"/>
          </g>
        </svg>

        <div>
          <div class="brand">Nova Rinda</div>
          <div class="meta">Frontend Developer • UI / UX</div>
        </div>
      </div>

      <nav>
        <a href="#about">About</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
      </nav>
    </header>

    <!-- PAGE 1: ABOUT / HERO -->
    <section id="about">
      <div class="page hero">
        <div>
          <h1>Hai — Saya Nova Rinda</h1>
          <p class="lead">Saya mendesain dan membangun antarmuka web yang ramah pengguna dengan sentuhan lavender lembut. Fokus saya adalah membuat produk cepat, aksesibel, dan enak dipandang.</p>

          <div style="margin:12px 0">
            <span class="tag">HTML</span>
            <span class="tag">CSS</span>
            <span class="tag">React</span>
          </div>

          <div class="cta">
            <a class="btn-primary" href="#projects">Lihat Proyek</a>
            <a class="btn-ghost" href="#contact">Hubungi</a>
          </div>

          <div class="divider"></div>

          <h3>Ringkasan</h3>
          <p class="meta">5+ tahun pengalaman membangun website & aplikasi. Terbiasa bekerja dengan tim dan berfokus pada kualitas UI serta performa.</p>
        </div>

        <div class="illus">
          <div class="card" aria-hidden="true">
            <!-- simple decorative svg illustration -->
            <svg width="220" height="160" viewBox="0 0 220 160" xmlns="http://www.w3.org/2000/svg" role="img">
              <rect x="0" y="0" width="220" height="160" rx="12" fill="none"/>
              <g transform="translate(20,18)">
                <rect width="180" height="110" rx="10" fill="#fff" stroke="#eef4ff"/>
                <rect x="14" y="18" width="152" height="72" rx="6" fill="#f6f3ff"/>
                <g transform="translate(28,34)" fill="#d6ccff">
                  <rect width="96" height="10" rx="4"/>
                  <rect y="18" width="60" height="10" rx="4"/>
                  <rect y="36" width="88" height="10" rx="4"/>
                </g>
                <circle cx="36" cy="88" r="14" fill="#f0e8ff"/>
                <circle cx="140" cy="88" r="10" fill="#f4f2ff"/>
              </g>
            </svg>
          </div>
        </div>
      </div>
    </section>

    <!-- PAGE 2: PROJECTS -->
    <section id="projects">
      <div class="page">
        <h2 style="margin-top:0">Proyek Pilihan</h2>
        <p class="meta">Contoh proyek — dari landing page hingga aplikasi dashboard.</p>

        <div class="projects-grid">
          <article class="project">
            <div class="thumb">🛒</div>
            <h3>E-Commerce Shop</h3>
            <p>React • Tailwind • Integrasi pembayaran</p>
          </article>

          <article class="project">
            <div class="thumb">🎨</div>
            <h3>Landing Kreatif</h3>
            <p>HTML • CSS • Aksesibilitas</p>
          </article>

          <article class="project">
            <div class="thumb">📊</div>
            <h3>Dashboard Internal</h3>
            <p>Laravel • Inertia • Charts</p>
          </article>

          <article class="project">
            <div class="thumb">🧩</div>
            <h3>Prototype UI</h3>
            <p>Figma → HTML Prototype</p>
          </article>

          <article class="project">
            <div class="thumb">🚀</div>
            <h3>Optimasi Performa</h3>
            <p>Audits • LCP • Code-splitting</p>
          </article>

          <article class="project">
            <div class="thumb">🌷</div>
            <h3>Personal Portfolio</h3>
            <p>Tampilan lembut & personal branding</p>
          </article>
        </div>

      </div>
    </section>

    <!-- PAGE 3: SKILLS / CONTACT -->
    <section id="contact">
      <div class="page two">
        <div>
          <h2>Skill & Tools</h2>
          <p class="meta">Toolset yang sering saya gunakan.</p>
          <div class="skills">
            <div class="skill">HTML</div>
            <div class="skill">CSS</div>
            <div class="skill">JavaScript</div>
            <div class="skill">React</div>
            <div class="skill">Laravel</div>
            <div class="skill">Figma</div>
            <div class="skill">Git</div>
          </div>

          <div style="margin-top:22px">
            <h3>Terima kasih sudah berkunjung 💜</h3>
            <p class="meta">Kalau kamu suka, kirim pesan atau undang saya ngobrol tentang proyekmu.</p>
          </div>
        </div>

        <aside class="contact-card">
          <h3>Kontak</h3>
          <p><strong>Email</strong></p>
          <p class="meta">novarinda@gmail.com</p>

          <p><strong>Lokasi</strong></p>
          <p class="meta">Jawa Timur, Indonesia</p>

          <div style="margin-top:16px">
            <a class="btn-primary" href="mailto:nama@example.com">Kirim Email</a>
          </div>

          <div style="margin-top:16px">
            <a class="btn-ghost" href="#">Unduh CV (PDF)</a>
          </div>
        </aside>
      </div>

      <footer>© 2025 Novarinda • Portofolio About Me</footer>
    </section>

  </div>
</body>
</html>
