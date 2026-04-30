<!DOCTYPE html>

<html lang="pl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Auron Holding – Remonty Pod Klucz</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;600;700&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

:root {
–gold: #C9A84C;
–gold-light: #E8C97A;
–gold-dark: #9A7030;
–black: #0A0A0A;
–dark: #111111;
–dark2: #1A1A1A;
–dark3: #222222;
–white: #F5F2EC;
–gray: #888880;
–gray2: #555550;
}

html { scroll-behavior: smooth; }

body {
background: var(–black);
color: var(–white);
font-family: ‘Montserrat’, sans-serif;
font-weight: 300;
overflow-x: hidden;
cursor: none;
}

/* CURSOR */
.cursor {
width: 10px; height: 10px;
background: var(–gold);
border-radius: 50%;
position: fixed;
pointer-events: none;
z-index: 9999;
transform: translate(-50%, -50%);
transition: width .2s, height .2s, background .2s;
}
.cursor-ring {
width: 38px; height: 38px;
border: 1px solid var(–gold);
border-radius: 50%;
position: fixed;
pointer-events: none;
z-index: 9998;
transform: translate(-50%, -50%);
transition: all .12s ease;
opacity: 0.6;
}
body:hover .cursor { opacity: 1; }

/* NOISE OVERLAY */
body::before {
content: ‘’;
position: fixed;
inset: 0;
background-image: url(“data:image/svg+xml,%3Csvg viewBox=‘0 0 256 256’ xmlns=‘http://www.w3.org/2000/svg’%3E%3Cfilter id=‘noise’%3E%3CfeTurbulence type=‘fractalNoise’ baseFrequency=‘0.9’ numOctaves=‘4’ stitchTiles=‘stitch’/%3E%3C/filter%3E%3Crect width=‘100%25’ height=‘100%25’ filter=‘url(%23noise)’ opacity=‘0.04’/%3E%3C/svg%3E”);
pointer-events: none;
z-index: 9000;
opacity: 0.5;
}

/* NAV */
nav {
position: fixed;
top: 0; left: 0; right: 0;
z-index: 100;
padding: 28px 60px;
display: flex;
justify-content: space-between;
align-items: center;
background: linear-gradient(to bottom, rgba(0,0,0,0.9) 0%, transparent 100%);
backdrop-filter: blur(0px);
transition: all .4s;
}
nav.scrolled {
padding: 18px 60px;
background: rgba(10,10,10,0.96);
backdrop-filter: blur(20px);
border-bottom: 1px solid rgba(201,168,76,0.15);
}
.logo {
font-family: ‘Cormorant Garamond’, serif;
font-size: 28px;
font-weight: 700;
letter-spacing: 4px;
color: var(–white);
text-decoration: none;
text-transform: uppercase;
}
.logo span { color: var(–gold); }
.nav-links { display: flex; gap: 44px; list-style: none; }
.nav-links a {
color: var(–gray);
text-decoration: none;
font-size: 11px;
letter-spacing: 3px;
text-transform: uppercase;
font-weight: 500;
transition: color .3s;
position: relative;
}
.nav-links a::after {
content: ‘’;
position: absolute;
bottom: -4px; left: 0;
width: 0; height: 1px;
background: var(–gold);
transition: width .3s;
}
.nav-links a:hover { color: var(–gold); }
.nav-links a:hover::after { width: 100%; }
.nav-cta {
border: 1px solid var(–gold);
color: var(–gold) !important;
padding: 10px 24px;
transition: all .3s !important;
}
.nav-cta:hover { background: var(–gold); color: var(–black) !important; }
.nav-cta::after { display: none !important; }

/* HERO */
.hero {
min-height: 100vh;
display: grid;
grid-template-columns: 1fr 1fr;
position: relative;
overflow: hidden;
}
.hero-left {
padding: 180px 60px 100px;
display: flex;
flex-direction: column;
justify-content: center;
position: relative;
z-index: 2;
}
.hero-tag {
font-size: 11px;
letter-spacing: 5px;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 36px;
opacity: 0;
animation: fadeUp .8s ease forwards .3s;
}
.hero-h1 {
font-family: ‘Cormorant Garamond’, serif;
font-size: clamp(52px, 5.5vw, 88px);
font-weight: 300;
line-height: 1.05;
letter-spacing: -1px;
margin-bottom: 32px;
opacity: 0;
animation: fadeUp .8s ease forwards .5s;
}
.hero-h1 em {
font-style: italic;
color: var(–gold);
display: block;
}
.hero-desc {
font-size: 14px;
line-height: 1.9;
color: var(–gray);
max-width: 400px;
margin-bottom: 56px;
opacity: 0;
animation: fadeUp .8s ease forwards .7s;
}
.hero-btns {
display: flex;
gap: 20px;
opacity: 0;
animation: fadeUp .8s ease forwards .9s;
}
.btn-primary {
background: var(–gold);
color: var(–black);
padding: 16px 40px;
font-size: 11px;
letter-spacing: 3px;
text-transform: uppercase;
font-weight: 600;
text-decoration: none;
font-family: ‘Montserrat’, sans-serif;
transition: all .3s;
position: relative;
overflow: hidden;
}
.btn-primary::before {
content: ‘’;
position: absolute;
inset: 0;
background: var(–gold-light);
transform: translateX(-100%);
transition: transform .4s ease;
}
.btn-primary:hover::before { transform: translateX(0); }
.btn-primary span { position: relative; z-index: 1; }
.btn-secondary {
border: 1px solid var(–gray2);
color: var(–white);
padding: 16px 40px;
font-size: 11px;
letter-spacing: 3px;
text-transform: uppercase;
font-weight: 500;
text-decoration: none;
font-family: ‘Montserrat’, sans-serif;
transition: all .3s;
}
.btn-secondary:hover { border-color: var(–gold); color: var(–gold); }

.hero-right {
position: relative;
overflow: hidden;
}
.hero-img-wrap {
position: absolute;
inset: 0;
animation: fadeIn 1.2s ease forwards;
}
.hero-img-wrap::after {
content: ‘’;
position: absolute;
inset: 0;
background: linear-gradient(to right, var(–black) 0%, rgba(0,0,0,0.3) 50%, rgba(0,0,0,0.5) 100%);
}
.hero-img {
width: 100%; height: 100%;
object-fit: cover;
filter: grayscale(20%) contrast(1.05);
transform: scale(1.05);
animation: slowZoom 12s ease-in-out infinite alternate;
}
.hero-number {
position: absolute;
right: -40px;
bottom: 80px;
font-family: ‘Cormorant Garamond’, serif;
font-size: 200px;
font-weight: 700;
color: rgba(201,168,76,0.06);
line-height: 1;
z-index: 3;
pointer-events: none;
letter-spacing: -10px;
}
.hero-stats {
position: absolute;
bottom: 60px;
left: 60px;
display: flex;
gap: 50px;
opacity: 0;
animation: fadeUp .8s ease forwards 1.1s;
}
.stat { border-left: 2px solid var(–gold); padding-left: 16px; }
.stat-num {
font-family: ‘Cormorant Garamond’, serif;
font-size: 42px;
font-weight: 300;
color: var(–gold);
line-height: 1;
}
.stat-label {
font-size: 10px;
letter-spacing: 2px;
text-transform: uppercase;
color: var(–gray);
margin-top: 4px;
}

/* MARQUEE */
.marquee-wrap {
background: var(–gold);
overflow: hidden;
padding: 14px 0;
}
.marquee-track {
display: flex;
gap: 0;
animation: marquee 20s linear infinite;
white-space: nowrap;
}
.marquee-item {
font-size: 11px;
letter-spacing: 4px;
text-transform: uppercase;
color: var(–black);
font-weight: 600;
padding: 0 40px;
flex-shrink: 0;
}
.marquee-dot {
color: rgba(0,0,0,0.4);
padding: 0 10px;
}

/* SERVICES */
.section { padding: 130px 60px; }
.section-label {
font-size: 10px;
letter-spacing: 5px;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 24px;
}
.section-title {
font-family: ‘Cormorant Garamond’, serif;
font-size: clamp(38px, 4vw, 64px);
font-weight: 300;
line-height: 1.1;
margin-bottom: 80px;
}
.section-title strong { color: var(–gold); font-weight: 600; }

.services-grid {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 2px;
}
.service-card {
background: var(–dark2);
padding: 48px 40px;
position: relative;
overflow: hidden;
transition: all .4s;
border: 1px solid transparent;
}
.service-card::before {
content: ‘’;
position: absolute;
bottom: 0; left: 0;
height: 3px; width: 0;
background: var(–gold);
transition: width .4s ease;
}
.service-card:hover {
border-color: rgba(201,168,76,0.2);
background: var(–dark3);
transform: translateY(-6px);
}
.service-card:hover::before { width: 100%; }
.service-num {
font-family: ‘Cormorant Garamond’, serif;
font-size: 80px;
font-weight: 700;
color: rgba(201,168,76,0.08);
line-height: 1;
position: absolute;
top: 20px; right: 20px;
}
.service-icon {
font-size: 32px;
margin-bottom: 24px;
}
.service-name {
font-family: ‘Cormorant Garamond’, serif;
font-size: 26px;
font-weight: 600;
margin-bottom: 16px;
color: var(–white);
transition: color .3s;
}
.service-card:hover .service-name { color: var(–gold); }
.service-desc {
font-size: 13px;
line-height: 1.8;
color: var(–gray);
}

/* PROCESS */
.process-section {
background: var(–dark2);
padding: 130px 60px;
}
.process-grid {
display: grid;
grid-template-columns: repeat(4, 1fr);
gap: 40px;
margin-top: 60px;
}
.process-step { position: relative; }
.process-step::after {
content: ‘→’;
position: absolute;
right: -25px; top: 22px;
color: var(–gold);
font-size: 20px;
opacity: 0.4;
}
.process-step:last-child::after { display: none; }
.step-num {
font-family: ‘Cormorant Garamond’, serif;
font-size: 64px;
font-weight: 700;
color: rgba(201,168,76,0.12);
line-height: 1;
margin-bottom: 16px;
}
.step-title {
font-size: 14px;
font-weight: 600;
letter-spacing: 1px;
margin-bottom: 12px;
color: var(–white);
}
.step-desc { font-size: 13px; color: var(–gray); line-height: 1.8; }

/* WHY US */
.why-grid {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 80px;
align-items: center;
}
.why-img-wrap {
position: relative;
height: 580px;
}
.why-img-main {
width: 80%;
height: 80%;
object-fit: cover;
position: absolute;
top: 0; right: 0;
filter: grayscale(30%);
}
.why-img-accent {
width: 55%;
height: 50%;
object-fit: cover;
position: absolute;
bottom: 0; left: 0;
filter: grayscale(30%);
border: 4px solid var(–black);
}
.why-badge {
position: absolute;
top: 50%; left: 20%;
transform: translate(-50%, -50%);
background: var(–gold);
color: var(–black);
width: 120px; height: 120px;
border-radius: 50%;
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
font-family: ‘Cormorant Garamond’, serif;
z-index: 5;
}
.why-badge-num { font-size: 36px; font-weight: 700; line-height: 1; }
.why-badge-text { font-size: 10px; letter-spacing: 1px; text-align: center; font-family: ‘Montserrat’, sans-serif; font-weight: 600; }
.why-points { display: flex; flex-direction: column; gap: 28px; margin-top: 40px; }
.why-point { display: flex; gap: 20px; align-items: flex-start; }
.why-point-icon {
width: 44px; height: 44px;
border: 1px solid var(–gold);
display: flex; align-items: center; justify-content: center;
font-size: 18px;
flex-shrink: 0;
color: var(–gold);
}
.why-point-title { font-size: 14px; font-weight: 600; margin-bottom: 6px; }
.why-point-text { font-size: 13px; color: var(–gray); line-height: 1.7; }

/* CONTACT */
.contact-section {
background: var(–dark2);
padding: 130px 60px;
}
.contact-grid {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 100px;
align-items: start;
margin-top: 60px;
}
.contact-info { display: flex; flex-direction: column; gap: 36px; }
.contact-item { display: flex; gap: 20px; align-items: flex-start; }
.contact-item-icon {
width: 48px; height: 48px;
background: rgba(201,168,76,0.1);
border: 1px solid rgba(201,168,76,0.3);
display: flex; align-items: center; justify-content: center;
font-size: 20px;
flex-shrink: 0;
}
.contact-item-label {
font-size: 10px;
letter-spacing: 3px;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 6px;
}
.contact-item-value {
font-size: 16px;
font-weight: 400;
color: var(–white);
}
.contact-item-sub {
font-size: 13px;
color: var(–gray);
margin-top: 4px;
}
.contact-cities {
display: flex; flex-wrap: wrap; gap: 10px;
margin-top: 16px;
}
.city-tag {
border: 1px solid var(–gray2);
padding: 6px 16px;
font-size: 11px;
letter-spacing: 2px;
text-transform: uppercase;
color: var(–gray);
transition: all .3s;
}
.city-tag:hover { border-color: var(–gold); color: var(–gold); }

/* FORM */
.contact-form { display: flex; flex-direction: column; gap: 20px; }
.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
.form-group { display: flex; flex-direction: column; gap: 8px; }
.form-label { font-size: 10px; letter-spacing: 3px; text-transform: uppercase; color: var(–gray); }
.form-input, .form-textarea {
background: rgba(255,255,255,0.04);
border: 1px solid var(–gray2);
color: var(–white);
padding: 14px 18px;
font-size: 14px;
font-family: ‘Montserrat’, sans-serif;
font-weight: 300;
outline: none;
transition: border-color .3s;
}
.form-input:focus, .form-textarea:focus { border-color: var(–gold); }
.form-textarea { resize: vertical; min-height: 120px; }
.form-submit {
background: var(–gold);
color: var(–black);
border: none;
padding: 18px;
font-size: 11px;
letter-spacing: 3px;
text-transform: uppercase;
font-weight: 700;
font-family: ‘Montserrat’, sans-serif;
cursor: none;
transition: all .3s;
position: relative;
overflow: hidden;
}
.form-submit:hover { background: var(–gold-light); }

/* FOOTER */
footer {
background: var(–dark);
border-top: 1px solid rgba(201,168,76,0.15);
padding: 60px 60px 40px;
}
.footer-grid {
display: grid;
grid-template-columns: 2fr 1fr 1fr;
gap: 60px;
margin-bottom: 60px;
}
.footer-logo {
font-family: ‘Cormorant Garamond’, serif;
font-size: 32px;
font-weight: 700;
letter-spacing: 4px;
text-transform: uppercase;
margin-bottom: 16px;
}
.footer-logo span { color: var(–gold); }
.footer-desc { font-size: 13px; color: var(–gray); line-height: 1.8; max-width: 280px; }
.footer-col-title {
font-size: 10px;
letter-spacing: 4px;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 24px;
}
.footer-links { display: flex; flex-direction: column; gap: 12px; }
.footer-links a {
font-size: 13px;
color: var(–gray);
text-decoration: none;
transition: color .3s;
}
.footer-links a:hover { color: var(–white); }
.footer-bottom {
border-top: 1px solid var(–dark3);
padding-top: 32px;
display: flex;
justify-content: space-between;
align-items: center;
}
.footer-copy { font-size: 12px; color: var(–gray2); }
.footer-copy span { color: var(–gold); }

/* GOLD LINE DIVIDER */
.gold-line {
width: 80px; height: 1px;
background: linear-gradient(to right, var(–gold), transparent);
margin-bottom: 40px;
}

/* ANIMATIONS */
@keyframes fadeUp {
from { opacity: 0; transform: translateY(30px); }
to { opacity: 1; transform: translateY(0); }
}
@keyframes fadeIn {
from { opacity: 0; }
to { opacity: 1; }
}
@keyframes slowZoom {
from { transform: scale(1.05); }
to { transform: scale(1.12); }
}
@keyframes marquee {
from { transform: translateX(0); }
to { transform: translateX(-50%); }
}

/* REVEAL ON SCROLL */
.reveal {
opacity: 0;
transform: translateY(40px);
transition: opacity .7s ease, transform .7s ease;
}
.reveal.visible {
opacity: 1;
transform: translateY(0);
}

/* MOBILE */
@media (max-width: 900px) {
nav { padding: 20px 24px; }
nav.scrolled { padding: 14px 24px; }
.nav-links { display: none; }
.hero { grid-template-columns: 1fr; }
.hero-left { padding: 140px 24px 60px; }
.hero-right { height: 300px; }
.hero-stats { left: 24px; bottom: 24px; }
.section { padding: 80px 24px; }
.services-grid { grid-template-columns: 1fr; gap: 2px; }
.process-section { padding: 80px 24px; }
.process-grid { grid-template-columns: 1fr 1fr; }
.process-step::after { display: none; }
.why-grid { grid-template-columns: 1fr; }
.why-img-wrap { height: 360px; }
.contact-section { padding: 80px 24px; }
.contact-grid { grid-template-columns: 1fr; gap: 40px; }
.form-row { grid-template-columns: 1fr; }
footer { padding: 40px 24px 24px; }
.footer-grid { grid-template-columns: 1fr; gap: 32px; }
.footer-bottom { flex-direction: column; gap: 12px; text-align: center; }
}
</style>

</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- NAV -->

<nav id="nav">
  <a href="#" class="logo">Auron <span>Holding</span></a>
  <ul class="nav-links">
    <li><a href="#uslugi">Usługi</a></li>
    <li><a href="#proces">Proces</a></li>
    <li><a href="#dlaczego">O nas</a></li>
    <li><a href="#kontakt" class="nav-cta">Bezpłatna wycena</a></li>
  </ul>
</nav>

<!-- HERO -->

<section class="hero" id="home">
  <div class="hero-left">
    <p class="hero-tag">✦ Remonty pod klucz · Polska</p>
    <h1 class="hero-h1">
      Twoja przestrzeń,<br>
      <em>nasza pasja.</em>
    </h1>
    <p class="hero-desc">Profesjonalne remonty pod klucz na terenie całej Polski. Od projektu do realizacji – kompleksowo, terminowo i zgodnie z najwyższymi standardami.</p>
    <div class="hero-btns">
      <a href="#kontakt" class="btn-primary"><span>Bezpłatna wycena</span></a>
      <a href="#uslugi" class="btn-secondary">Nasze usługi</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-img-wrap">
      <img src="https://images.unsplash.com/photo-1504307651254-35680f356dfd?w=1200&q=80" alt="Remont" class="hero-img">
    </div>
    <div class="hero-number">A</div>
  </div>
  <div class="hero-stats">
    <div class="stat">
      <div class="stat-num">6+</div>
      <div class="stat-label">Lat doświadczenia</div>
    </div>
    <div class="stat">
      <div class="stat-num">100%</div>
      <div class="stat-label">Pod klucz</div>
    </div>
    <div class="stat">
      <div class="stat-num">3</div>
      <div class="stat-label">Główne miasta</div>
    </div>
  </div>
</section>

<!-- MARQUEE -->

<div class="marquee-wrap">
  <div class="marquee-track" id="marquee">
    <span class="marquee-item">Remonty Pod Klucz <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Poznań <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Gdańsk <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Warszawa <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Cała Polska <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Profesjonalnie <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Terminowo <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Kompleksowo <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Remonty Pod Klucz <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Poznań <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Gdańsk <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Warszawa <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Cała Polska <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Profesjonalnie <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Terminowo <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Kompleksowo <span class="marquee-dot">✦</span></span>
  </div>
</div>

<!-- SERVICES -->

<section class="section" id="uslugi">
  <div class="section-label reveal">✦ Co oferujemy</div>
  <h2 class="section-title reveal">Pełen zakres <strong>usług remontowych</strong></h2>
  <div class="services-grid">
    <div class="service-card reveal">
      <div class="service-num">01</div>
      <div class="service-icon">🏠</div>
      <h3 class="service-name">Remont mieszkania</h3>
      <p class="service-desc">Kompleksowy remont lokalu mieszkalnego – od wyburzenia po wykończenie. Realizujemy projekty dowolnej wielkości z pełną gwarancją jakości.</p>
    </div>
    <div class="service-card reveal">
      <div class="service-num">02</div>
      <div class="service-icon">🏢</div>
      <h3 class="service-name">Przestrzenie biurowe</h3>
      <p class="service-desc">Adaptacja i remont biur, lokali komercyjnych oraz przestrzeni użytkowych. Minimalizujemy przerwy w Twojej działalności.</p>
    </div>
    <div class="service-card reveal">
      <div class="service-num">03</div>
      <div class="service-icon">🛁</div>
      <h3 class="service-name">Łazienki i kuchnie</h3>
      <p class="service-desc">Specjalistyczne remonty łazienek i kuchni. Układanie płytek, instalacje hydrauliczne, zabudowy – wszystko w jednym miejscu.</p>
    </div>
    <div class="service-card reveal">
      <div class="service-num">04</div>
      <div class="service-icon">🎨</div>
      <h3 class="service-name">Malowanie i tynkowanie</h3>
      <p class="service-desc">Profesjonalne prace malarskie i tynkarskie. Gładzie, dekoracje, efekty specjalne – każda powierzchnia w perfekcyjnym stanie.</p>
    </div>
    <div class="service-card reveal">
      <div class="service-num">05</div>
      <div class="service-icon">⚡</div>
      <h3 class="service-name">Instalacje elektryczne</h3>
      <p class="service-desc">Kompleksowe prace elektryczne – wymiana instalacji, montaż rozdzielnic, oświetlenia LED i systemów smart home.</p>
    </div>
    <div class="service-card reveal">
      <div class="service-num">06</div>
      <div class="service-icon">🔧</div>
      <h3 class="service-name">Instalacje hydrauliczne</h3>
      <p class="service-desc">Wymiana i montaż instalacji wodno-kanalizacyjnych, centralnego ogrzewania oraz systemów grzewczych.</p>
    </div>
  </div>
</section>

<!-- PROCESS -->

<section class="process-section" id="proces">
  <div class="section-label reveal">✦ Jak działamy</div>
  <h2 class="section-title reveal">Prosty <strong>proces współpracy</strong></h2>
  <div class="process-grid">
    <div class="process-step reveal">
      <div class="step-num">01</div>
      <h3 class="step-title">Bezpłatna konsultacja</h3>
      <p class="step-desc">Kontaktujesz się z nami. Wyjeżdżamy na miejsce, omawiamy zakres prac i Twoje oczekiwania bez żadnych zobowiązań.</p>
    </div>
    <div class="process-step reveal">
      <div class="step-num">02</div>
      <h3 class="step-title">Wycena i umowa</h3>
      <p class="step-desc">Przygotowujemy szczegółową wycenę i harmonogram prac. Podpisujemy umowę z jasno określonymi warunkami.</p>
    </div>
    <div class="process-step reveal">
      <div class="step-num">03</div>
      <h3 class="step-title">Realizacja</h3>
      <p class="step-desc">Nasz zespół przystępuje do pracy. Na bieżąco informujemy o postępach i jesteśmy dostępni pod telefonem.</p>
    </div>
    <div class="process-step reveal">
      <div class="step-num">04</div>
      <h3 class="step-title">Odbiór i gwarancja</h3>
      <p class="step-desc">Wspólnie odbieramy ukończone prace. Przekazujemy dokumentację i udzielamy gwarancji na wykonane roboty.</p>
    </div>
  </div>
</section>

<!-- WHY US -->

<section class="section" id="dlaczego">
  <div class="why-grid">
    <div class="why-img-wrap reveal">
      <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=800&q=80" alt="Remont" class="why-img-main">
      <img src="https://images.unsplash.com/photo-1581858726788-75bc0f6a952d?w=600&q=80" alt="Ekipa" class="why-img-accent">
      <div class="why-badge">
        <span class="why-badge-num">6+</span>
        <span class="why-badge-text">lat na rynku</span>
      </div>
    </div>
    <div class="reveal">
      <div class="section-label">✦ Dlaczego my</div>
      <h2 class="section-title">Jakość, której <strong>możesz zaufać</strong></h2>
      <div class="gold-line"></div>
      <p style="font-size:14px; color:var(--gray); line-height:1.9; margin-bottom:32px;">Auron Holding to doświadczony zespół specjalistów, który łączy rzemiosło z nowoczesnymi rozwiązaniami. Działamy w Poznaniu, Gdańsku, Warszawie i na terenie całej Polski.</p>
      <div class="why-points">
        <div class="why-point">
          <div class="why-point-icon">✓</div>
          <div>
            <div class="why-point-title">Terminowość</div>
            <div class="why-point-text">Dotrzymujemy ustalonych terminów. Harmonogram prac jest dla nas zobowiązaniem, nie sugestią.</div>
          </div>
        </div>
        <div class="why-point">
          <div class="why-point-icon">✓</div>
          <div>
            <div class="why-point-title">Doświadczony zespół</div>
            <div class="why-point-text">Nasi fachowcy posiadają wieloletnie doświadczenie i stale podnoszą kwalifikacje.</div>
          </div>
        </div>
        <div class="why-point">
          <div class="why-point-icon">✓</div>
          <div>
            <div class="why-point-title">Przejrzyste ceny</div>
            <div class="why-point-text">Szczegółowa wycena przed rozpoczęciem prac. Bez ukrytych kosztów i nieprzyjemnych niespodzianek.</div>
          </div>
        </div>
        <div class="why-point">
          <div class="why-point-icon">✓</div>
          <div>
            <div class="why-point-title">Gwarancja jakości</div>
            <div class="why-point-text">Udzielamy pisemnej gwarancji na wszystkie wykonane prace. Twój spokój ducha to nasz priorytet.</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->

<section class="contact-section" id="kontakt">
  <div class="section-label reveal">✦ Skontaktuj się</div>
  <h2 class="section-title reveal">Zacznijmy <strong>Twój remont</strong></h2>
  <div class="contact-grid">
    <div class="contact-info reveal">
      <div class="contact-item">
        <div class="contact-item-icon">📞</div>
        <div>
          <div class="contact-item-label">Telefon</div>
          <div class="contact-item-value">+48 507 105 301</div>
          <div class="contact-item-sub">Pon–Sob, 8:00–18:00</div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-item-icon">✉</div>
        <div>
          <div class="contact-item-label">Email</div>
          <div class="contact-item-value">auron.holding@gmail.com</div>
          <div class="contact-item-sub">Odpowiadamy w ciągu 24h</div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-item-icon">📍</div>
        <div>
          <div class="contact-item-label">Adres</div>
          <div class="contact-item-value">ul. Polarna 2C/1, Poznań</div>
          <div class="contact-item-sub">Działamy na terenie całej Polski</div>
          <div class="contact-cities">
            <span class="city-tag">Poznań</span>
            <span class="city-tag">Gdańsk</span>
            <span class="city-tag">Warszawa</span>
            <span class="city-tag">Cała Polska</span>
          </div>
        </div>
      </div>
    </div>
    <div class="contact-form reveal">
      <div class="form-row">
        <div class="form-group">
          <label class="form-label">Imię i nazwisko</label>
          <input type="text" class="form-input" placeholder="Jan Kowalski">
        </div>
        <div class="form-group">
          <label class="form-label">Telefon</label>
          <input type="text" class="form-input" placeholder="+48 000 000 000">
        </div>
      </div>
      <div class="form-group">
        <label class="form-label">Email</label>
        <input type="email" class="form-input" placeholder="jan@example.com">
      </div>
      <div class="form-group">
        <label class="form-label">Rodzaj usługi</label>
        <input type="text" class="form-input" placeholder="np. Remont mieszkania 60m²">
      </div>
      <div class="form-group">
        <label class="form-label">Opis prac</label>
        <textarea class="form-textarea" placeholder="Opisz zakres prac – co wymaga remontu, powierzchnia, lokalizacja..."></textarea>
      </div>
      <button class="form-submit" onclick="alert('Dziękujemy! Skontaktujemy się wkrótce.')">Wyślij zapytanie →</button>
    </div>
  </div>
</section>

<!-- FOOTER -->

<footer>
  <div class="footer-grid">
    <div>
      <div class="footer-logo">Auron <span>Holding</span></div>
      <p class="footer-desc">Profesjonalne remonty pod klucz na terenie całej Polski. Jakość, terminowość i przejrzyste ceny od ponad 6 lat.</p>
    </div>
    <div>
      <div class="footer-col-title">Usługi</div>
      <div class="footer-links">
        <a href="#uslugi">Remonty mieszkań</a>
        <a href="#uslugi">Przestrzenie biurowe</a>
        <a href="#uslugi">Łazienki i kuchnie</a>
        <a href="#uslugi">Instalacje</a>
        <a href="#uslugi">Malowanie</a>
      </div>
    </div>
    <div>
      <div class="footer-col-title">Kontakt</div>
      <div class="footer-links">
        <a href="tel:+48507105301">+48 507 105 301</a>
        <a href="mailto:auron.holding@gmail.com">auron.holding@gmail.com</a>
        <a href="#">Polarna 2C/1, Poznań</a>
        <a href="#">Poznań · Gdańsk · Warszawa</a>
      </div>
    </div>
  </div>
  <div class="footer-bottom">
    <p class="footer-copy">© 2025 <span>Auron Holding</span>. Wszelkie prawa zastrzeżone.</p>
    <p class="footer-copy">Remonty pod klucz · Cała Polska</p>
  </div>
</footer>

<script>
  // Custom cursor
  const cursor = document.getElementById('cursor');
  const ring = document.getElementById('cursorRing');
  let mx = 0, my = 0, rx = 0, ry = 0;
  document.addEventListener('mousemove', e => { mx = e.clientX; my = e.clientY; cursor.style.left = mx+'px'; cursor.style.top = my+'px'; });
  function animateRing() {
    rx += (mx - rx) * 0.12;
    ry += (my - ry) * 0.12;
    ring.style.left = rx+'px';
    ring.style.top = ry+'px';
    requestAnimationFrame(animateRing);
  }
  animateRing();
  document.querySelectorAll('a, button, .service-card').forEach(el => {
    el.addEventListener('mouseenter', () => { cursor.style.width = '20px'; cursor.style.height = '20px'; ring.style.width = '60px'; ring.style.height = '60px'; ring.style.borderColor = 'var(--gold-light)'; });
    el.addEventListener('mouseleave', () => { cursor.style.width = '10px'; cursor.style.height = '10px'; ring.style.width = '38px'; ring.style.height = '38px'; ring.style.borderColor = 'var(--gold)'; });
  });

  // Nav scroll
  const nav = document.getElementById('nav');
  window.addEventListener('scroll', () => { nav.classList.toggle('scrolled', window.scrollY > 60); });

  // Reveal on scroll
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver(entries => {
    entries.forEach((e, i) => { if (e.isIntersecting) { setTimeout(() => e.target.classList.add('visible'), i * 80); } });
  }, { threshold: 0.12 });
  reveals.forEach(el => observer.observe(el));

  // Smooth scroll
  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', e => {
      e.preventDefault();
      const t = document.querySelector(a.getAttribute('href'));
      if (t) t.scrollIntoView({ behavior: 'smooth' });
    });
  });
</script>

</body>
</html>
