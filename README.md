<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Vlog Play – Playful Vlog Template</title>
  <meta name="description" content="A playful, animated vlog website template using only HTML, CSS, and JavaScript." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;800&family=Nunito:wght@400;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg: #0f1226;
      --panel: #14173a;
      --panel-2: #111432;
      --text: #e7e8ff;
      --muted: #aeb2ff;
      --brand: #7c5cff; /* purple */
      --accent: #37e2d5; /* mint */
      --hot: #ff7ab6;     /* pink */
      --sun: #ffd166;     /* yellow */
      --ok: #6ee7b7;      /* green */
      --danger: #ff6b6b;  /* red */
      --shadow: 0 15px 40px rgba(0,0,0,.4);
    }/* Light mode tokens */
:root.light{
  --bg: #f8f8ff;
  --panel: #ffffff;
  --panel-2: #f1f3ff;
  --text: #181a2a;
  --muted: #4b4f66;
  --brand: #6c47ff;
  --accent: #14b8a6;
  --hot: #ff5fa2;
  --sun: #f4b000;
  --ok: #10b981;
  --danger: #ef4444;
  --shadow: 0 10px 30px rgba(17, 24, 39, .15);
}

* { box-sizing: border-box; }
html, body { height: 100%; }
body{
  margin:0; font-family: Poppins, system-ui, -apple-system, Segoe UI, Roboto, Noto Sans, Ubuntu, Cantarell, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji";
  background: radial-gradient(1200px 600px at 10% -10%, rgba(124,92,255,.25), transparent 60%),
              radial-gradient(1000px 500px at 100% 0%, rgba(55,226,213,.18), transparent 60%),
              linear-gradient(180deg, var(--bg), var(--bg));
  color: var(--text);
}
a{ color: inherit; text-decoration: none; }
img{ max-width: 100%; display: block; }

/* ---------- Top nav ---------- */
.nav{
  position: sticky; top: 0; z-index: 50; backdrop-filter: saturate(150%) blur(10px);
  background: linear-gradient(180deg, rgba(20,23,58,.75), rgba(20,23,58,.45));
  border-bottom: 1px solid rgba(255,255,255,.08);
}
.nav-inner{ max-width: 1100px; margin: 0 auto; display:flex; align-items:center; gap: 18px; padding: 14px 18px; }
.logo{ display:flex; align-items:center; gap:10px; font-weight:800; letter-spacing:.3px; }
.logo-badge{ width:36px; height:36px; border-radius:12px; background: conic-gradient(from 120deg, var(--brand), var(--hot), var(--accent), var(--brand)); box-shadow: var(--shadow); position:relative; }
.logo-badge::after{ content:"▶"; position:absolute; inset:0; display:grid; place-items:center; color:#fff; font-size:16px; text-shadow:0 1px 2px rgba(0,0,0,.25); }
.nav-links{ margin-left:auto; display:flex; gap:16px; align-items:center; }
.nav-links a{ padding:8px 10px; border-radius:10px; position:relative; opacity:.9; }
.nav-links a::after{ content:""; position:absolute; left:10px; right:10px; bottom:6px; height:3px; border-radius:2px; background: linear-gradient(90deg, var(--accent), var(--hot)); transform: scaleX(0); transform-origin:left; transition:.25s ease; }
.nav-links a:hover::after{ transform: scaleX(1); }
.btn{ padding:10px 14px; border-radius:12px; font-weight:700; background: linear-gradient(135deg, var(--brand), var(--hot)); color:#fff; box-shadow: var(--shadow); border:0; cursor:pointer; }
.ghost{ background:transparent; border:1px solid rgba(255,255,255,.2); color: var(--text); }
.hamb{ display:none; }

/* ---------- Hero ---------- */
.hero{ position:relative; overflow:hidden; }
.hero-inner{ max-width:1100px; margin:0 auto; padding: 56px 18px 24px; display:grid; grid-template-columns: 1.2fr .8fr; gap: 28px; align-items:center; }
.hero h1{ font-size: clamp(32px, 4.6vw, 56px); line-height:1.02; margin:0 0 12px; }
.hero p{ margin:0 0 18px; color: var(--muted); }
.hero .actions{ display:flex; gap:12px; flex-wrap:wrap; }

.blob{ position:absolute; filter: blur(40px); opacity:.55; pointer-events:none; mix-blend-mode: screen; }
.blob.one{ width:480px; height:480px; background: radial-gradient(circle at 30% 30%, var(--brand), transparent 60%); border-radius: 58% 42% 55% 45%/45% 48% 52% 55%; left:-120px; top:-80px; animation: blob 14s ease-in-out infinite; }
.blob.two{ width:520px; height:520px; background: radial-gradient(circle at 60% 30%, var(--hot), transparent 60%); border-radius: 45% 55% 40% 60%/58% 40% 60% 42%; right:-160px; top:-120px; animation: blob 18s ease-in-out infinite reverse; }
.blob.three{ width:420px; height:420px; background: radial-gradient(circle at 40% 60%, var(--accent), transparent 60%); border-radius: 60% 40% 58% 42%/40% 60% 40% 60%; left:30%; bottom:-120px; animation: blob 22s ease-in-out infinite; }
@keyframes blob { 0%,100%{ transform:translateY(0) rotate(0deg);} 50%{ transform: translateY(-20px) rotate(20deg);} }

/* ---------- Marquee ---------- */
.marquee{ overflow:hidden; position:relative; border-block: 1px dashed rgba(255,255,255,.12); background: linear-gradient(180deg, rgba(255,255,255,.03), transparent); }
.marquee-track{ display:flex; gap:40px; padding:12px 0; will-change: transform; animation: marquee 20s linear infinite; }
.marquee span{ opacity:.9; font-weight:700; letter-spacing:.3px; }
@keyframes marquee { 0%{ transform: translateX(0); } 100%{ transform: translateX(-50%);} }

/* ---------- Section shells ---------- */
section{ max-width:1100px; margin:0 auto; padding: 40px 18px; }
.section-title{ display:flex; align-items:center; gap:12px; margin: 8px 0 18px; }
.section-title .dot{ width:12px; height:12px; border-radius:50%; background: conic-gradient(var(--accent), var(--hot)); box-shadow:0 0 0 6px rgba(255,255,255,.05); }

/* ---------- Video grid ---------- */
.grid{ display:grid; grid-template-columns: repeat(12, 1fr); gap:16px; }
.card{ grid-column: span 4; background: linear-gradient(180deg, var(--panel), var(--panel-2)); border: 1px solid rgba(255,255,255,.08); border-radius: 18px; overflow:hidden; box-shadow: var(--shadow); transform: translateY(0) scale(1); transition: transform .2s ease, box-shadow .2s ease; cursor:pointer; position:relative; }
.card:hover{ transform: translateY(-4px) scale(1.01); box-shadow: 0 20px 50px rgba(0,0,0,.45); }
.thumb{ aspect-ratio: 16/9; background: linear-gradient(135deg, rgba(124,92,255,.2), rgba(55,226,213,.16)),
                      linear-gradient(135deg, rgba(255,122,182,.35), transparent),
                      radial-gradient(circle at 70% 30%, rgba(255,209,102,.4), transparent 40%);
        display:grid; place-items:center; position:relative; }
.play{ width:64px; height:64px; border-radius:50%; background: linear-gradient(135deg, var(--brand), var(--hot)); display:grid; place-items:center; color:#fff; font-weight:800; box-shadow: var(--shadow); transform: scale(1); transition:.2s; }
.card:hover .play{ transform: scale(1.06) rotate(3deg); }
.meta{ padding:14px; display:flex; flex-direction:column; gap:10px; }
.meta h3{ margin:0; font-size: 18px; }
.tags{ display:flex; gap:8px; flex-wrap:wrap; }
.tag{ padding:6px 10px; border-radius:999px; font-size:12px; background: rgba(255,255,255,.06); border:1px dashed rgba(255,255,255,.15); }
.stats{ display:flex; gap:16px; color:var(--muted); font-size:12px; }

/* ---------- Big banner / CTA ---------- */
.cta{
  margin-top: 8px;
  background: linear-gradient(135deg, rgba(124,92,255,.2), rgba(55,226,213,.12)), linear-gradient(0deg, var(--panel), var(--panel));
  border: 1px solid rgba(255,255,255,.08); border-radius: 22px; padding: 20px; display:grid; grid-template-columns: 1.2fr .8fr; gap: 18px; align-items:center;
}
.cta h3{ margin:6px 0 10px; font-size: clamp(20px, 2.6vw, 28px); }
.cta p{ margin:0 0 12px; color:var(--muted); }
.cta .mini{ display:flex; gap:10px; align-items:center; }

/* ---------- About ---------- */
.about{ display:grid; grid-template-columns: .9fr 1.1fr; gap: 24px; align-items:center; }
.about-card{ background: linear-gradient(180deg, var(--panel), var(--panel-2)); border: 1px solid rgba(255,255,255,.08); border-radius: 22px; padding: 22px; box-shadow: var(--shadow); }
.about-card p{ margin:0 0 12px; color: var(--muted); }

/* ---------- Contact / Subscribe ---------- */
.sub-grid{ display:grid; grid-template-columns: 1fr 1fr; gap:18px; }
form{ display:grid; gap:10px; }
.input{ padding:12px 14px; border-radius:12px; border:1px solid rgba(255,255,255,.18); background: rgba(0,0,0,.18); color:var(--text); }
.input::placeholder{ color: rgba(255,255,255,.55); }
.toast{ position: fixed; right: 16px; bottom: 16px; background: var(--panel); border: 1px solid rgba(255,255,255,.12); padding: 12px 14px; border-radius: 14px; box-shadow: var(--shadow); display:none; }

/* ---------- Footer ---------- */
footer{ margin-top:20px; padding: 24px 18px 60px; background: linear-gradient(180deg, rgba(255,255,255,.04), rgba(255,255,255,0)); color: var(--muted); border-top:1px solid rgba(255,255,255,.08); }
.foot{ max-width:1100px; margin:0 auto; display:flex; align-items:center; justify-content:space-between; gap:20px; flex-wrap:wrap; }
.social{ display:flex; gap:12px; }
.social a{ width:36px; height:36px; display:grid; place-items:center; border-radius:12px; background:rgba(255,255,255,.06); border:1px dashed rgba(255,255,255,.12); }

/* ---------- Modal ---------- */
dialog{ border:none; border-radius:18px; width:min(960px, 92vw); background: var(--panel); color: var(--text); box-shadow: var(--shadow); }
.modal-head{ display:flex; align-items:center; justify-content:space-between; padding:10px 14px; border-bottom:1px solid rgba(255,255,255,.1); }
.modal-body{ padding:12px; }
.modal-body iframe{ width:100%; aspect-ratio:16/9; border:0; border-radius:14px; }

/* ---------- Utilities ---------- */
.hide{ display:none !important; }
.center{ text-align:center; }
.muted{ color: var(--muted); }

/* ---------- Responsive ---------- */
@media (max-width: 980px){
  .hero-inner{ grid-template-columns: 1fr; }
  .cta{ grid-template-columns: 1fr; }
  .about{ grid-template-columns: 1fr; }
  .grid .card{ grid-column: span 6; }
}
@media (max-width: 640px){
  .nav-links{ display:none; position:absolute; left:0; right:0; top:100%; background: var(--panel); border-bottom:1px solid rgba(255,255,255,.1); padding:12px 18px; }
  .nav-links.open{ display:flex; flex-direction:column; align-items:flex-start; gap:6px; }
  .hamb{ display:grid; place-items:center; margin-left:auto; background:transparent; border:1px solid rgba(255,255,255,.2); border-radius:10px; padding:8px; color:var(--text); cursor:pointer; }
  .grid .card{ grid-column: span 12; }
  .sub-grid{ grid-template-columns: 1fr; }
}

/* ---------- Fun microinteractions ---------- */
.btn.wiggle:hover{ animation: wiggle .7s ease; }
@keyframes wiggle{ 0%{ transform:rotate(0deg);} 25%{ transform:rotate(-3deg);} 50%{ transform:rotate(3deg);} 75%{ transform:rotate(-2deg);} 100%{ transform:rotate(0deg);} }
.btn:active{ transform: translateY(1px) scale(.99); }

  </style>
</head>
<body>
  <nav class="nav" aria-label="Primary">
    <div class="nav-inner">
      <a href="#" class="logo" aria-label="Vlog Play home">
        <span class="logo-badge" aria-hidden="true"></span>
        <span>Vlog <span style="background:linear-gradient(90deg,var(--accent),var(--hot));-webkit-background-clip:text;background-clip:text;color:transparent;">Play</span></span>
      </a>
      <button class="hamb" id="hamb" aria-label="Toggle menu">☰</button>
      <div class="nav-links" id="navLinks">
        <a href="#videos">Videos</a>
        <a href="#about">About</a>
        <a href="#subscribe">Subscribe</a>
        <a href="#contact">Contact</a>
        <button class="btn ghost" id="themeBtn" aria-label="Toggle theme">🌓 Theme</button>
      </div>
    </div>
  </nav>  <header class="hero" role="banner">
    <div class="blob one"></div>
    <div class="blob two"></div>
    <div class="blob three"></div>
    <div class="hero-inner">
      <div>
        <h1>Hey! Welcome to <span style="background:linear-gradient(90deg,var(--sun),var(--hot));-webkit-background-clip:text;background-clip:text;color:transparent;">my vlog</span> ✨</h1>
        <p>I share playful videos about daily life, travel, food, and mini tech hacks — with a sprinkle of whimsy and a lot of color.</p>
        <div class="actions">
          <a href="#videos" class="btn wiggle">▶ Watch Latest</a>
          <button class="btn" id="confettiBtn">🎉 Celebrate</button>
        </div>
      </div>
      <div>
        <div class="cta">
          <div>
            <span class="mini">
              <span class="dot"></span><small class="muted">New episode</small>
            </span>
            <h3>Weekend Vlog: Street Food Safari 🍜</h3>
            <p class="muted">Join me as I try 7 quirky snacks in one evening and rate them with an extremely scientific scale.</p>
            <div class="stats"><span>⭐ 4.9</span><span>•</span><span>⏱️ 12:31</span><span>•</span><span id="subCount">📺 12,345 subs</span></div>
          </div>
          <div>
            <div class="thumb" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ?autoplay=1" role="button" aria-label="Play featured video">
              <div class="play">▶</div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="marquee" aria-hidden="true">
      <div class="marquee-track">
        <span>New • Travel • Food • Daily • Tech • Behind the Scenes • Tips • Laughs • New • Travel • Food • Daily • Tech • Behind the Scenes • Tips • Laughs •</span>
      </div>
    </div>
  </header>  <main>
    <section id="videos">
      <div class="section-title"><span class="dot"></span><h2>Latest Videos</h2></div>
      <div class="grid" id="videoGrid" aria-live="polite">
        <!-- Cards will be populated by JS below -->
      </div>
    </section><section id="about">
  <div class="section-title"><span class="dot"></span><h2>About This Vlog</h2></div>
  <div class="about">
    <div class="about-card">
      <h3>Hi, I’m your friendly vlogger 👋</h3>
      <p>Welcome to a colorful corner of the internet. Expect quick edits, bright vibes, and honest takes. Every week I drop a new vlog about travel, food, or productivity tricks.</p>
      <p>Want to collab? I love experimenting with fun formats and mini challenges.</p>
      <div class="actions">
        <a class="btn" href="#contact">Let’s Collab</a>
        <button class="btn ghost" id="copyURL">Copy Site Link</button>
      </div>
    </div>
    <div class="about-card">
      <h3>Upload Schedule 📅</h3>
      <p class="muted">Tuesdays & Fridays — short, sweet, and packed with energy.</p>
      <h3 style="margin-top:16px;">Gear I Use 🎥</h3>
      <ul class="muted">
        <li>Mirrorless camera + 24mm lens</li>
        <li>Clip-on mic for clean audio</li>
        <li>Phone gimbal for smooth B-roll</li>
      </ul>
    </div>
  </div>
</section>

<section id="subscribe">
  <div class="section-title"><span class="dot"></span><h2>Subscribe for Updates</h2></div>
  <div class="sub-grid">
    <form id="subForm" novalidate>
      <input class="input" type="text" id="name" placeholder="Your name" aria-label="Your name">
      <input class="input" type="email" id="email" placeholder="Your email" aria-label="Your email" required>
      <button class="btn" type="submit">Subscribe ✉️</button>
      <small class="muted">No spam. Unsubscribe anytime.</small>
    </form>
    <div class="about-card">
      <h3>Perks ✨</h3>
      <p class="muted">Get video drops, behind‑the‑scenes, and early access to giveaways.</p>
      <div class="stats"><span id="emailCount">📨 0 joined today</span></div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="section-title"><span class="dot"></span><h2>Say Hello</h2></div>
  <div class="sub-grid">
    <form id="contactForm" novalidate>
      <input class="input" type="text" id="cname" placeholder="Your name" aria-label="Your name" required>
      <input class="input" type="email" id="cemail" placeholder="Your email" aria-label="Your email" required>
      <textarea class="input" id="cmsg" rows="4" placeholder="Your message" aria-label="Your message" required></textarea>
      <button class="btn" type="submit">Send 💌</button>
    </form>
    <div class="about-card">
      <h3>Business Inquiries</h3>
      <p class="muted">For sponsorships or collabs, include timelines and brief ideas. I usually reply within 48 hours.</p>
      <div class="actions">
        <a class="btn ghost" href="mailto:hello@example.com">Email Me</a>
      </div>
    </div>
  </div>
</section>

  </main>  <footer>
    <div class="foot">
      <div class="logo"><span class="logo-badge"></span><span>Vlog Play</span></div>
      <div class="social" aria-label="Social links">
        <a href="#" aria-label="YouTube" title="YouTube">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M23.5 6.2a4 4 0 0 0-2.8-2.8C18.9 3 12 3 12 3s-6.9 0-8.7.4A4 4 0 0 0 .5 6.2 41 41 0 0 0 0 12a41 41 0 0 0 .5 5.8 4 4 0 0 0 2.8 2.8C5.1 21 12 21 12 21s6.9 0 8.7-.4a4 4 0 0 0 2.8-2.8A41 41 0 0 0 24 12a41 41 0 0 0-.5-5.8zM9.6 15.5V8.5L15.8 12l-6.2 3.5z"/></svg>
        </a>
        <a href="#" aria-label="Instagram" title="Instagram">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M7 2h10a5 5 0 0 1 5 5v10a5 5 0 0 1-5 5H7a5 5 0 0 1-5-5V7a5 5 0 0 1 5-5m10 2H7a3 3 0 0 0-3 3v10a3 3 0 0 0 3 3h10a3 3 0 0 0 3-3V7a3 3 0 0 0-3-3m-5 3a6 6 0 1 1 0 12 6 6 0 0 1 0-12m6.5-.25a1.25 1.25 0 1 1 0 2.5 1.25 1.25 0 0 1 0-2.5Z"/></svg>
        </a>
        <a href="#" aria-label="Twitter" title="Twitter">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M22 5.8c-.7.3-1.5.5-2.3.6a4 4 0 0 0 1.7-2.1 8 8 0 0 1-2.5 1 4 4 0 0 0-7 2.8c0 .3 0 .5.1.8-3.3-.2-6.3-1.8-8.3-4.4a4 4 0 0 0 1.2 5.4c-.6 0-1.2-.2-1.7-.5a4 4 0 0 0 3.2 4 4 4 0 0 1-1.8.1 4 4 0 0 0 3.7 2.7A8.1 8.1 0 0 1 2 18.6a11.4 11.4 0 0 0 6.2 1.8c7.5 0 11.6-6.2 11.6-11.6v-.5c.8-.6 1.5-1.4 2-2.3Z"/></svg>
        </a>
      </div>
    </div>
  </footer>  <div class="toast" id="toast" role="alert">Done ✅</div>  <!-- Modal for video playback -->  <dialog id="videoModal" aria-label="Video player">
    <div class="modal-head">
      <strong>Now Playing</strong>
      <button class="btn ghost" id="closeModal">✕</button>
    </div>
    <div class="modal-body">
      <iframe id="player" src="" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen title="Video player"></iframe>
    </div>
  </dialog>  <script>
    // ---------- Theme toggle with localStorage ----------
    const themeBtn = document.getElementById('themeBtn');
    const appliedTheme = localStorage.getItem('theme');
    if(appliedTheme === 'light'){ document.documentElement.classList.add('light'); }
    themeBtn.addEventListener('click', () => {
      document.documentElement.classList.toggle('light');
      localStorage.setItem('theme', document.documentElement.classList.contains('light') ? 'light' : 'dark');
    });

   // ---------- Mobile menu ----------
    const hamb = document.getElementById('hamb');
    const navLinks = document.getElementById('navLinks');
    hamb.addEventListener('click',()=> navLinks.classList.toggle('open'));

  // ---------- Fake data for videos (edit freely) ----------
    const videos = [
      { id: 'v1', title: 'Morning Routine – Energy Boost ☕', length: '8:24', views: '23k', tags: ['daily','productivity'], yt: 'https://www.youtube.com/embed/ysz5S6PUM-U?autoplay=1' },
      { id: 'v2', title: 'Street Food Safari 🍢', length: '12:31', views: '41k', tags: ['food','travel'], yt: 'https://www.youtube.com/embed/dQw4w9WgXcQ?autoplay=1' },
      { id: 'v3', title: 'Desk Setup Glow‑Up ✨', length: '9:12', views: '18k', tags: ['tech','aesthetic'], yt: 'https://www.youtube.com/embed/aqz-KE-bpKQ?autoplay=1' },
      { id: 'v4', title: '24 Hours, 24 Tiny Challenges 🎯', length: '14:05', views: '57k', tags: ['challenge'], yt: 'https://www.youtube.com/embed/aqz-KE-bpKQ?autoplay=1' },
      { id: 'v5', title: 'Train Travel Vlog 🚆', length: '10:40', views: '29k', tags: ['travel'], yt: 'https://www.youtube.com/embed/ysz5S6PUM-U?autoplay=1' },
      { id: 'v6', title: 'Budget Camera Tips 🎥', length: '7:50', views: '21k', tags: ['tech','tips'], yt: 'https://www.youtube.com/embed/dQw4w9WgXcQ?autoplay=1' },
    ];

  const grid = document.getElementById('videoGrid');
    grid.innerHTML = videos.map(v => `
  <article class="card reveal" data-video="${v.yt}" tabindex="0" role="button" aria-label="Play: ${v.title}">
        <div class="thumb">
          <div class="play">▶</div>
          <span style="position:absolute; right:8px; bottom:8px; background:rgba(0,0,0,.5); padding:4px 8px; border-radius:8px; font-size:12px;">${v.length}</span>
        </div>
        <div class="meta">
          <h3>${v.title}</h3>
          <div class="tags">${v.tags.map(t => `<span class='tag'>#${t}</span>`).join('')}</div>
          <div class="stats"><span>👀 ${v.views}</span><span>•</span><span>👍 1.2k</span></div>
        </div>
      </article>
    `).join('');

  // ---------- Modal playback ----------
    const modal = document.getElementById('videoModal');
    const player = document.getElementById('player');
    const closeModal = document.getElementById('closeModal');

  function openVideo(src){
      player.src = src;
      if(typeof modal.showModal === 'function'){ modal.showModal(); }
      else { modal.classList.remove('hide'); }
    }
    function closeVideo(){ player.src = ''; if(modal.open) modal.close(); else modal.classList.add('hide'); }

  closeModal.addEventListener('click', closeVideo);
    modal.addEventListener('click', (e)=>{ if(e.target === modal) closeVideo(); });

  document.body.addEventListener('click', (e)=>{
      const el = e.target.closest('[data-video]');
      if(el){ openVideo(el.getAttribute('data-video')); }
    });

  // Keyboard accessibility
    document.body.addEventListener('keydown', (e)=>{
      if(e.key === 'Escape') closeVideo();
      if((e.key === 'Enter' || e.key === ' ') && document.activeElement?.hasAttribute('data-video')){
        e.preventDefault();
        openVideo(document.activeElement.getAttribute('data-video'));
      }
    });

  // ---------- Confetti burst ----------
    const confettiBtn = document.getElementById('confettiBtn');
    confettiBtn.addEventListener('click', ()=>{
      burstConfetti(confettiBtn);
      toast('Party time! 🎉');
    });

  function burstConfetti(origin){
      const colors = ['var(--brand)','var(--hot)','var(--accent)','var(--sun)'];
      const rect = origin.getBoundingClientRect();
      const spawnX = rect.left + rect.width/2; const spawnY = rect.top + rect.height/2;
      for(let i=0;i<40;i++){
        const p = document.createElement('span');
        p.style.position='fixed';
        p.style.left = spawnX + 'px';
        p.style.top = spawnY + 'px';
        p.style.width = p.style.height = (6 + Math.random()*6) + 'px';
        p.style.background = colors[Math.floor(Math.random()*colors.length)];
        p.style.borderRadius = Math.random() > .5 ? '2px' : '50%';
        p.style.pointerEvents = 'none';
        p.style.zIndex = 1000;
        document.body.appendChild(p);
        const angle = Math.random()*2*Math.PI; const speed = 4 + Math.random()*8;
        const vy = Math.sin(angle)*speed; const vx = Math.cos(angle)*speed;
        let life = 0; const gravity = .3 + Math.random()*.2;
        const timer = setInterval(()=>{
          life += 1; const x = parseFloat(p.style.left); const y = parseFloat(p.style.top);
          p.style.left = (x + vx) + 'px';
          p.style.top = (y + vy + gravity*life) + 'px';
          p.style.opacity = String(1 - life/60);
          if(life>60){ clearInterval(timer); p.remove(); }
        }, 16);
      }
    }

  // ---------- Simple toast ----------
    const toastEl = document.getElementById('toast');
    function toast(msg){
      toastEl.textContent = msg;
      toastEl.style.display = 'block';
      setTimeout(()=> toastEl.style.display = 'none', 2200);
    }

   // ---------- Copy URL ----------
    document.getElementById('copyURL').addEventListener('click', async ()=>{
      try{ await navigator.clipboard.writeText(location.href); toast('Link copied! 🔗'); }
      catch{ toast('Could not copy'); }
    });

   // ---------- Fun counters ----------
    const subCount = document.getElementById('subCount');
    let subs = 12345;
    function bumpSubs(){ subs += Math.floor(Math.random()*5)+1; subCount.textContent = `📺 ${subs.toLocaleString()} subs`; }
    setInterval(bumpSubs, 5000);

   const emailCount = document.getElementById('emailCount');
    let joined = 0; setInterval(()=>{ joined += Math.random()>.6?1:0; emailCount.textContent = `📨 ${joined} joined today`; }, 4000);

  // ---------- Forms (client side only) ----------
    const subForm = document.getElementById('subForm');
    subForm.addEventListener('submit', (e)=>{
      e.preventDefault();
      const email = document.getElementById('email').value.trim();
      if(!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) return toast('Enter a valid email');
      toast('Subscribed! 🎉');
      subForm.reset();
      burstConfetti(subForm.querySelector('button'));
    });

   const contactForm = document.getElementById('contactForm');
    contactForm.addEventListener('submit', (e)=>{
      e.preventDefault();
      const required = ['cname','cemail','cmsg'];
      for(const id of required){ if(!document.getElementById(id).value.trim()) return toast('Please fill all fields'); }
      if(!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(document.getElementById('cemail').value.trim())) return toast('Enter a valid email');
      toast('Message sent! ✉️');
      contactForm.reset();
    });

   // ---------- Scroll reveal ----------
    const io = new IntersectionObserver((entries)=>{
      for(const e of entries){ if(e.isIntersecting){ e.target.animate([{opacity:0, transform:'translateY(12px)'},{opacity:1, transform:'translateY(0)'}], {duration:500, easing:'ease-out'}); io.unobserve(e.target);} }
    }, { threshold: .12 });
    document.querySelectorAll('.reveal').forEach(el=> io.observe(el));
  </script></body>
</html>
