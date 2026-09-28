
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lumière Studio — Beleza Redefinida</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
<style>
  :root {
    --bg: #0f0a0d;
    --bg-2: #1a1216;
    --cream: #f7efe8;
    --rose: #e8b4b8;
    --rose-deep: #c98b91;
    --gold: #d4af7a;
    --gold-light: #e6c893;
    --text: #f5ede7;
    --text-dim: #b8a9a3;
    --glass: rgba(255, 255, 255, 0.04);
    --glass-border: rgba(255, 255, 255, 0.08);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Inter', sans-serif;
    background: var(--bg);
    color: var(--text);
    overflow-x: hidden;
    line-height: 1.6;
    cursor: none;
  }

  /* ===== CURSOR PERSONALIZADO ===== */
  .cursor-dot, .cursor-ring {
    position: fixed;
    top: 0; left: 0;
    pointer-events: none;
    z-index: 9999;
    border-radius: 50%;
    transform: translate(-50%, -50%);
    transition: width .3s, height .3s, background .3s;
  }
  .cursor-dot {
    width: 6px; height: 6px;
    background: var(--gold);
  }
  .cursor-ring {
    width: 34px; height: 34px;
    border: 1px solid rgba(212, 175, 122, 0.5);
    transition: transform .15s ease-out, width .3s, height .3s;
  }
  .cursor-ring.hover {
    width: 60px; height: 60px;
    background: rgba(212, 175, 122, 0.08);
    border-color: var(--gold);
  }
  @media (max-width: 900px) {
    .cursor-dot, .cursor-ring { display: none; }
    body { cursor: auto; }
  }

  /* ===== FUNDO ANIMADO ===== */
  .bg-orbs {
    position: fixed;
    inset: 0;
    z-index: -2;
    overflow: hidden;
    background: var(--bg);
  }
  .orb {
    position: absolute;
    border-radius: 50%;
    filter: blur(120px);
    opacity: 0.35;
    animation: float 20s infinite ease-in-out;
  }
  .orb-1 { width: 500px; height: 500px; background: #c98b91; top: -10%; left: -10%; }
  .orb-2 { width: 450px; height: 450px; background: #7a4a5c; bottom: -15%; right: -10%; animation-delay: -5s; }
  .orb-3 { width: 380px; height: 380px; background: #d4af7a; top: 40%; left: 50%; animation-delay: -10s; opacity: 0.18; }

  @keyframes float {
    0%, 100% { transform: translate(0,0) scale(1); }
    33% { transform: translate(60px, -40px) scale(1.1); }
    66% { transform: translate(-40px, 50px) scale(0.95); }
  }

  /* Grain overlay */
  .grain {
    position: fixed;
    inset: 0;
    z-index: -1;
    pointer-events: none;
    opacity: 0.035;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E");
  }

  /* ===== NAV ===== */
  nav {
    position: fixed;
    top: 20px;
    left: 50%;
    transform: translateX(-50%);
    width: min(1200px, 94%);
    padding: 14px 26px;
    background: rgba(15, 10, 13, 0.6);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    border: 1px solid var(--glass-border);
    border-radius: 100px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 1000;
    transition: all .4s;
  }
  nav.scrolled {
    top: 12px;
    background: rgba(15, 10, 13, 0.85);
    box-shadow: 0 20px 40px rgba(0,0,0,0.4);
  }
  .logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem;
    font-weight: 600;
    letter-spacing: -0.02em;
    background: linear-gradient(135deg, #f7efe8 0%, #d4af7a 100%);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .logo i { color: var(--gold); -webkit-text-fill-color: var(--gold); }

  .nav-links {
    display: flex;
    gap: 34px;
    align-items: center;
  }
  .nav-links a {
    color: var(--text-dim);
    text-decoration: none;
    font-size: 0.9rem;
    font-weight: 400;
    position: relative;
    transition: color .3s;
  }
  .nav-links a::after {
    content: '';
    position: absolute;
    bottom: -4px; left: 0;
    width: 0; height: 1px;
    background: var(--gold);
    transition: width .3s;
  }
  .nav-links a:hover { color: var(--text); }
  .nav-links a:hover::after { width: 100%; }

  .nav-actions { display: flex; gap: 10px; align-items: center; }

  .btn-ghost {
    background: transparent;
    border: 1px solid var(--glass-border);
    color: var(--text);
    padding: 9px 20px;
    border-radius: 100px;
    font-size: 0.85rem;
    font-family: inherit;
    cursor: none;
    transition: all .3s;
  }
  .btn-ghost:hover {
    border-color: var(--gold);
    color: var(--gold);
    background: rgba(212, 175, 122, 0.05);
  }

  .btn-gold {
    background: linear-gradient(135deg, var(--gold) 0%, var(--gold-light) 100%);
    border: none;
    color: #1a1216;
    padding: 10px 22px;
    border-radius: 100px;
    font-size: 0.85rem;
    font-weight: 600;
    font-family: inherit;
    cursor: none;
    transition: all .3s;
    box-shadow: 0 8px 24px rgba(212, 175, 122, 0.25);
  }
  .btn-gold:hover {
    transform: translateY(-2px);
    box-shadow: 0 12px 32px rgba(212, 175, 122, 0.4);
  }

  .menu-toggle {
    display: none;
    background: none;
    border: none;
    color: var(--text);
    font-size: 1.4rem;
    cursor: none;
  }

  /* ===== HERO ===== */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1.1fr 0.9fr;
    align-items: center;
    gap: 60px;
    padding: 140px 6% 80px;
    position: relative;
  }

  .hero-text { max-width: 620px; }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 7px 16px;
    background: rgba(212, 175, 122, 0.08);
    border: 1px solid rgba(212, 175, 122, 0.25);
    border-radius: 100px;
    font-size: 0.78rem;
    color: var(--gold-light);
    letter-spacing: 0.05em;
    text-transform: uppercase;
    margin-bottom: 28px;
    opacity: 0;
    animation: fadeUp .8s .1s forwards;
  }
  .badge i { font-size: 0.7rem; }

  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.8rem, 6vw, 5rem);
    font-weight: 400;
    line-height: 1.05;
    letter-spacing: -0.03em;
    margin-bottom: 26px;
    opacity: 0;
    animation: fadeUp .9s .25s forwards;
  }
  .hero h1 em {
    font-style: italic;
    background: linear-gradient(135deg, var(--rose) 0%, var(--gold) 100%);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .hero p {
    font-size: 1.05rem;
    color: var(--text-dim);
    font-weight: 300;
    max-width: 480px;
    margin-bottom: 40px;
    opacity: 0;
    animation: fadeUp .9s .4s forwards;
  }

  .hero-cta {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
    opacity: 0;
    animation: fadeUp .9s .55s forwards;
  }

  .btn-primary {
    display: inline-flex;
    align-items: center;
    gap: 12px;
    padding: 16px 34px;
    background: linear-gradient(135deg, var(--gold) 0%, var(--gold-light) 100%);
    color: #1a1216;
    border: none;
    border-radius: 100px;
    font-size: 0.95rem;
    font-weight: 600;
    font-family: inherit;
    cursor: none;
    transition: all .3s;
    box-shadow: 0 12px 32px rgba(212, 175, 122, 0.3);
    position: relative;
    overflow: hidden;
  }
  .btn-primary::before {
    content: '';
    position: absolute;
    top: 50%; left: 50%;
    width: 0; height: 0;
    background: rgba(255,255,255,0.3);
    border-radius: 50%;
    transform: translate(-50%, -50%);
    transition: width .6s, height .6s;
  }
  .btn-primary:hover::before { width: 400px; height: 400px; }
  .btn-primary:hover { transform: translateY(-3px); box-shadow: 0 18px 40px rgba(212, 175, 122, 0.45); }
  .btn-primary span { position: relative; z-index: 1; }
  .btn-primary i { position: relative; z-index: 1; transition: transform .3s; }
  .btn-primary:hover i { transform: translateX(5px); }

  .btn-outline {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    padding: 16px 30px;
    background: transparent;
    border: 1px solid var(--glass-border);
    color: var(--text);
    border-radius: 100px;
    font-size: 0.95rem;
    font-weight: 500;
    font-family: inherit;
    cursor: none;
    transition: all .3s;
    backdrop-filter: blur(10px);
  }
  .btn-outline:hover {
    border-color: var(--gold);
    color: var(--gold);
    background: rgba(212, 175, 122, 0.05);
  }

  /* Hero visual */
  .hero-visual {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    opacity: 0;
    animation: fadeIn 1.2s .6s forwards;
  }
  .visual-frame {
    width: 100%;
    max-width: 420px;
    aspect-ratio: 4/5;
    border-radius: 200px 200px 24px 24px;
    background: linear-gradient(160deg, #2a1e23 0%, #1a1216 100%);
    border: 1px solid var(--glass-border);
    position: relative;
    overflow: hidden;
    box-shadow: 0 40px 80px rgba(0,0,0,0.5);
  }
  .visual-frame::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
      radial-gradient(circle at 30% 20%, rgba(232, 180, 184, 0.35), transparent 50%),
      radial-gradient(circle at 70% 80%, rgba(212, 175, 122, 0.3), transparent 50%);
  }
  .visual-frame img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    opacity: 0.75;
    mix-blend-mode: luminosity;
  }
  .visual-content {
    position: absolute;
    inset: 0;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 40px 32px;
    z-index: 2;
  }
  .visual-content .rating {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 10px;
    font-size: 0.85rem;
    color: var(--gold-light);
  }
  .visual-content .rating span { color: var(--text-dim); }
  .visual-content h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.7rem;
    font-weight: 500;
    line-height: 1.2;
  }

  /* Floating stats cards */
  .float-card {
    position: absolute;
    background: rgba(26, 18, 22, 0.85);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    border: 1px solid var(--glass-border);
    border-radius: 20px;
    padding: 16px 20px;
    box-shadow: 0 20px 40px rgba(0,0,0,0.4);
    animation: floatCard 5s ease-in-out infinite;
  }
  .float-card-1 { top: 10%; left: -8%; animation-delay: 0s; }
  .float-card-2 { bottom: 20%; right: -8%; animation-delay: -2.5s; }
  .float-card .num {
    font-family: 'Playfair Display', serif;
    font-size: 1.6rem;
    color: var(--gold);
    font-weight: 600;
    line-height: 1;
  }
  .float-card .lbl {
    font-size: 0.7rem;
    color: var(--text-dim);
    text-transform: uppercase;
    letter-spacing: 0.08em;
    margin-top: 6px;
  }

  @keyframes floatCard {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-14px); }
  }
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeIn {
    from { opacity: 0; transform: scale(0.96); }
    to { opacity: 1; transform: scale(1); }
  }

  /* ===== SECTION STYLES ===== */
  section { padding: 120px 6%; position: relative; }

  .section-label {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    font-size: 0.75rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 18px;
    font-weight: 500;
  }
  .section-label::before {
    content: '';
    width: 28px;
    height: 1px;
    background: var(--gold);
  }

  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 4.5vw, 3.4rem);
    font-weight: 400;
    line-height: 1.15;
    letter-spacing: -0.02em;
    margin-bottom: 20px;
    max-width: 700px;
  }
  .section-title em {
    font-style: italic;
    color: var(--rose);
  }

  .section-sub {
    color: var(--text-dim);
    font-weight: 300;
    max-width: 560px;
    margin-bottom: 60px;
    font-size: 1rem;
  }

  /* ===== SERVIÇOS ===== */
  .services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 22px;
  }

  .service-card {
    position: relative;
    padding: 36px 30px;
    background: var(--glass);
    border: 1px solid var(--glass-border);
    border-radius: 28px;
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    transition: all .5s cubic-bezier(0.2, 0.8, 0.2, 1);
    overflow: hidden;
    opacity: 0;
    transform: translateY(40px);
  }
  .service-card.revealed {
    opacity: 1;
    transform: translateY(0);
  }
  .service-card::before {
    content: '';
    position: absolute;
    top: -50%; right: -50%;
    width: 200px; height: 200px;
    background: radial-gradient(circle, rgba(212, 175, 122, 0.15), transparent 70%);
    opacity: 0;
    transition: opacity .5s;
  }
  .service-card:hover {
    transform: translateY(-8px);
    border-color: rgba(212, 175, 122, 0.35);
    background: rgba(212, 175, 122, 0.04);
    box-shadow: 0 30px 60px rgba(0,0,0,0.4);
  }
  .service-card:hover::before { opacity: 1; }

  .service-icon {
    width: 60px;
    height: 60px;
    border-radius: 18px;
    background: linear-gradient(135deg, rgba(212, 175, 122, 0.15), rgba(232, 180, 184, 0.1));
    border: 1px solid rgba(212, 175, 122, 0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.5rem;
    color: var(--gold);
    margin-bottom: 24px;
    transition: all .4s;
  }
  .service-card:hover .service-icon {
    transform: rotate(-6deg) scale(1.08);
    background: linear-gradient(135deg, var(--gold), var(--gold-light));
    color: #1a1216;
  }

  .service-card h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.35rem;
    font-weight: 500;
    margin-bottom: 10px;
  }
  .service-card p {
    color: var(--text-dim);
    font-size: 0.9rem;
    font-weight: 300;
    line-height: 1.6;
    margin-bottom: 20px;
  }
  .service-price {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-top: 18px;
    border-top: 1px solid var(--glass-border);
    font-size: 0.85rem;
  }
  .service-price .price {
    color: var(--gold);
    font-weight: 600;
    font-size: 1rem;
  }
  .service-price .arrow {
    width: 32px; height: 32px;
    border-radius: 50%;
    background: rgba(212, 175, 122, 0.1);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--gold);
    transition: all .3s;
  }
  .service-card:hover .arrow {
    background: var(--gold);
    color: #1a1216;
    transform: rotate(-45deg);
  }

  /* ===== AGENDAMENTO ===== */
  .booking {
    display: grid;
    grid-template-columns: 0.9fr 1.1fr;
    gap: 60px;
    align-items: start;
    background: linear-gradient(135deg, rgba(26, 18, 22, 0.6), rgba(15, 10, 13, 0.6));
    border: 1px solid var(--glass-border);
    border-radius: 40px;
    padding: 60px 50px;
    backdrop-filter: blur(30px);
    -webkit-backdrop-filter: blur(30px);
    position: relative;
    overflow: hidden;
    margin: 0 6%;
    width: auto;
  }
  .booking::before {
    content: '';
    position: absolute;
    top: -100px; right: -100px;
    width: 300px; height: 300px;
    background: radial-gradient(circle, rgba(212, 175, 122, 0.15), transparent 70%);
    border-radius: 50%;
  }

  .booking-info h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.8rem, 3.5vw, 2.6rem);
    font-weight: 400;
    line-height: 1.15;
    margin-bottom: 20px;
    letter-spacing: -0.02em;
  }
  .booking-info h2 em { color: var(--gold); font-style: italic; }
  .booking-info p {
    color: var(--text-dim);
    font-weight: 300;
    margin-bottom: 34px;
    font-size: 0.95rem;
  }

  .booking-features {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }
  .booking-features li {
    display: flex;
    align-items: center;
    gap: 14px;
    list-style: none;
    font-size: 0.9rem;
    color: var(--text);
    font-weight: 300;
  }
  .booking-features li i {
    width: 34px; height: 34px;
    border-radius: 50%;
    background: rgba(212, 175, 122, 0.1);
    border: 1px solid rgba(212, 175, 122, 0.25);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--gold);
    font-size: 0.8rem;
    flex-shrink: 0;
  }

  .booking-form {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 18px;
  }
  .form-field {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }
  .form-field.full { grid-column: 1 / -1; }
  .form-field label {
    font-size: 0.78rem;
    color: var(--text-dim);
    text-transform: uppercase;
    letter-spacing: 0.08em;
    font-weight: 500;
  }
  .form-field input,
  .form-field select {
    padding: 14px 18px;
    background: rgba(15, 10, 13, 0.6);
    border: 1px solid var(--glass-border);
    border-radius: 14px;
    color: var(--text);
    font-family: inherit;
    font-size: 0.92rem;
    outline: none;
    transition: all .3s;
    cursor: none;
  }
  .form-field input:focus,
  .form-field select:focus {
    border-color: var(--gold);
    background: rgba(15, 10, 13, 0.9);
    box-shadow: 0 0 0 4px rgba(212, 175, 122, 0.1);
  }
  .form-field input::placeholder { color: #5a4d52; }
  .form-field select option { background: #1a1216; color: var(--text); }

  .form-field input[type="date"]::-webkit-calendar-picker-indicator,
  .form-field input[type="time"]::-webkit-calendar-picker-indicator {
    filter: invert(0.7) sepia(1) hue-rotate(320deg);
    cursor: none;
  }

  .btn-submit {
    grid-column: 1 / -1;
    padding: 17px;
    background: linear-gradient(135deg, var(--gold) 0%, var(--gold-light) 100%);
    color: #1a1216;
    border: none;
    border-radius: 100px;
    font-size: 0.95rem;
    font-weight: 600;
    font-family: inherit;
    cursor: none;
    transition: all .3s;
    box-shadow: 0 12px 32px rgba(212, 175, 122, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    margin-top: 6px;
  }
  .btn-submit:hover {
    transform: translateY(-2px);
    box-shadow: 0 18px 40px rgba(212, 175, 122, 0.45);
  }

  /* ===== FLOAT ACTIONS ===== */
  .float-actions {
    position: fixed;
    bottom: 30px;
    right: 30px;
    display: flex;
    flex-direction: column;
    gap: 14px;
    z-index: 900;
  }
  .fab {
    width: 58px;
    height: 58px;
    border-radius: 50%;
    border: none;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.5rem;
    cursor: none;
    transition: all .35s cubic-bezier(0.2, 0.8, 0.2, 1);
    position: relative;
    box-shadow: 0 12px 30px rgba(0,0,0,0.35);
  }
  .fab::after {
    content: attr(data-tip);
    position: absolute;
    right: 72px;
    top: 50%;
    transform: translateY(-50%) translateX(8px);
    background: rgba(26, 18, 22, 0.95);
    backdrop-filter: blur(10px);
    color: var(--text);
    padding: 8px 14px;
    border-radius: 10px;
    font-size: 0.78rem;
    font-family: 'Inter', sans-serif;
    white-space: nowrap;
    opacity: 0;
    pointer-events: none;
    transition: all .3s;
    border: 1px solid var(--glass-border);
  }
  .fab:hover::after {
    opacity: 1;
    transform: translateY(-50%) translateX(0);
  }
  .fab-whatsapp {
    background: linear-gradient(135deg, #25d366, #20b859);
    color: white;
  }
  .fab-whatsapp:hover { transform: scale(1.1) rotate(-8deg); }
  .fab-whatsapp .pulse {
    position: absolute;
    inset: 0;
    border-radius: 50%;
    border: 2px solid #25d366;
    animation: pulse 2s infinite;
    pointer-events: none;
  }
  @keyframes pulse {
    0% { transform: scale(1); opacity: 0.8; }
    100% { transform: scale(1.5); opacity: 0; }
  }
  .fab-chat {
    background: linear-gradient(135deg, var(--gold), var(--gold-light));
    color: #1a1216;
  }
  .fab-chat:hover { transform: scale(1.1) rotate(8deg); }
  .fab-top {
    background: rgba(26, 18, 22, 0.85);
    border: 1px solid var(--glass-border);
    color: var(--text);
    backdrop-filter: blur(10px);
    font-size: 1.1rem;
    opacity: 0;
    visibility: hidden;
    transform: translateY(20px);
  }
  .fab-top.show {
    opacity: 1;
    visibility: visible;
    transform: translateY(0);
  }
  .fab-top:hover { border-color: var(--gold); color: var(--gold); }

  /* ===== CHATBOT ===== */
  .chat-panel {
    position: fixed;
    bottom: 110px;
    right: 30px;
    width: 380px;
    max-width: calc(100vw - 40px);
    height: 560px;
    max-height: calc(100vh - 140px);
    background: rgba(20, 14, 18, 0.95);
    backdrop-filter: blur(30px);
    -webkit-backdrop-filter: blur(30px);
    border: 1px solid var(--glass-border);
    border-radius: 28px;
    box-shadow: 0 40px 80px rgba(0,0,0,0.6);
    display: flex;
    flex-direction: column;
    overflow: hidden;
    z-index: 950;
    opacity: 0;
    visibility: hidden;
    transform: translateY(20px) scale(0.96);
    transition: all .35s cubic-bezier(0.2, 0.8, 0.2, 1);
    transform-origin: bottom right;
  }
  .chat-panel.open {
    opacity: 1;
    visibility: visible;
    transform: translateY(0) scale(1);
  }

  .chat-header {
    padding: 20px 22px;
    background: linear-gradient(135deg, rgba(212, 175, 122, 0.15), rgba(232, 180, 184, 0.08));
    border-bottom: 1px solid var(--glass-border);
    display: flex;
    align-items: center;
    gap: 14px;
  }
  .chat-avatar {
    width: 44px; height: 44px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--gold), var(--rose));
    display: flex;
    align-items: center;
    justify-content: center;
    color: #1a1216;
    font-size: 1.2rem;
    position: relative;
    flex-shrink: 0;
  }
  .chat-avatar::after {
    content: '';
    position: absolute;
    bottom: 2px; right: 2px;
    width: 11px; height: 11px;
    background: #25d366;
    border-radius: 50%;
    border: 2px solid #1a1216;
  }
  .chat-header-info h4 {
    font-family: 'Playfair Display', serif;
    font-size: 1.05rem;
    font-weight: 500;
    color: var(--text);
  }
  .chat-header-info p {
    font-size: 0.75rem;
    color: #25d366;
    display: flex;
    align-items: center;
    gap: 5px;
  }
  .chat-close {
    margin-left: auto;
    background: none;
    border: none;
    color: var(--text-dim);
    font-size: 1.2rem;
    cursor: none;
    width: 32px; height: 32px;
    border-radius: 50%;
    transition: all .3s;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .chat-close:hover { background: rgba(255,255,255,0.05); color: var(--text); }

  .chat-body {
    flex: 1;
    overflow-y: auto;
    padding: 22px;
    display: flex;
    flex-direction: column;
    gap: 14px;
  }
  .chat-body::-webkit-scrollbar { width: 4px; }
  .chat-body::-webkit-scrollbar-thumb { background: var(--glass-border); border-radius: 2px; }

  .msg {
    max-width: 82%;
    padding: 12px 16px;
    border-radius: 18px;
    font-size: 0.88rem;
    line-height: 1.5;
    animation: msgIn .35s cubic-bezier(0.2, 0.8, 0.2, 1);
    word-wrap: break-word;
  }
  @keyframes msgIn {
    from { opacity: 0; transform: translateY(8px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .msg-bot {
    background: rgba(212, 175, 122, 0.1);
    border: 1px solid rgba(212, 175, 122, 0.18);
    color: var(--text);
    align-self: flex-start;
    border-bottom-left-radius: 6px;
  }
  .msg-user {
    background: linear-gradient(135deg, var(--gold), var(--gold-light));
    color: #1a1216;
    align-self: flex-end;
    border-bottom-right-radius: 6px;
    font-weight: 500;
  }
  .msg-typing {
    display: flex;
    gap: 4px;
    padding: 16px 18px;
  }
  .msg-typing span {
    width: 6px; height: 6px;
    background: var(--text-dim);
    border-radius: 50%;
    animation: typing 1.2s infinite;
  }
  .msg-typing span:nth-child(2) { animation-delay: 0.15s; }
  .msg-typing span:nth-child(3) { animation-delay: 0.3s; }
  @keyframes typing {
    0%, 60%, 100% { transform: translateY(0); opacity: 0.4; }
    30% { transform: translateY(-6px); opacity: 1; }
  }

  .quick-replies {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    padding: 0 22px 12px;
  }
  .quick-reply {
    padding: 7px 14px;
    background: rgba(212, 175, 122, 0.08);
    border: 1px solid rgba(212, 175, 122, 0.25);
    border-radius: 100px;
    color: var(--gold-light);
    font-size: 0.78rem;
    font-family: inherit;
    cursor: none;
    transition: all .3s;
    white-space: nowrap;
  }
  .quick-reply:hover {
    background: var(--gold);
    color: #1a1216;
    border-color: var(--gold);
  }

  .chat-input-area {
    padding: 16px 20px;
    border-top: 1px solid var(--glass-border);
    display: flex;
    gap: 10px;
    align-items: center;
    background: rgba(15, 10, 13, 0.5);
  }
  .chat-input-area input {
    flex: 1;
    padding: 12px 16px;
    background: rgba(255,255,255,0.03);
    border: 1px solid var(--glass-border);
    border-radius: 100px;
    color: var(--text);
    font-family: inherit;
    font-size: 0.88rem;
    outline: none;
    transition: border-color .3s;
    cursor: none;
  }
  .chat-input-area input:focus { border-color: var(--gold); }
  .chat-input-area input::placeholder { color: #5a4d52; }
  .chat-send {
    width: 42px; height: 42px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--gold), var(--gold-light));
    border: none;
    color: #1a1216;
    font-size: 1rem;
    cursor: none;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all .3s;
    flex-shrink: 0;
  }
  .chat-send:hover { transform: scale(1.08) rotate(-12deg); }

  /* ===== MODAIS ===== */
  .modal-bg {
    position: fixed;
    inset: 0;
    background: rgba(10, 6, 9, 0.7);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 2000;
    opacity: 0;
    visibility: hidden;
    transition: all .35s;
    padding: 20px;
  }
  .modal-bg.open { opacity: 1; visibility: visible; }

  .modal-box {
    background: linear-gradient(160deg, rgba(30, 21, 26, 0.98), rgba(20, 14, 18, 0.98));
    border: 1px solid var(--glass-border);
    border-radius: 32px;
    padding: 44px 40px;
    width: 100%;
    max-width: 440px;
    position: relative;
    box-shadow: 0 40px 100px rgba(0,0,0,0.6);
    transform: scale(0.94) translateY(10px);
    transition: all .4s cubic-bezier(0.2, 0.8, 0.2, 1);
  }
  .modal-bg.open .modal-box { transform: scale(1) translateY(0); }

  .modal-box::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--gold), transparent);
    opacity: 0.5;
  }

  .modal-close {
    position: absolute;
    top: 20px; right: 20px;
    width: 36px; height: 36px;
    border-radius: 50%;
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--glass-border);
    color: var(--text-dim);
    font-size: 1rem;
    cursor: none;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all .3s;
  }
  .modal-close:hover { color: var(--gold); border-color: var(--gold); transform: rotate(90deg); }

  .modal-icon {
    width: 58px; height: 58px;
    border-radius: 18px;
    background: linear-gradient(135deg, rgba(212, 175, 122, 0.15), rgba(232, 180, 184, 0.08));
    border: 1px solid rgba(212, 175, 122, 0.25);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--gold);
    font-size: 1.4rem;
    margin-bottom: 24px;
  }

  .modal-box h2 {
    font-family: 'Playfair Display', serif;
    font-size: 1.9rem;
    font-weight: 400;
    margin-bottom: 8px;
    letter-spacing: -0.02em;
  }
  .modal-box h2 em { color: var(--gold); font-style: italic; }
  .modal-box .modal-sub {
    color: var(--text-dim);
    font-size: 0.88rem;
    font-weight: 300;
    margin-bottom: 30px;
  }

  .modal-field { margin-bottom: 16px; }
  .modal-field label {
    display: block;
    font-size: 0.75rem;
    color: var(--text-dim);
    text-transform: uppercase;
    letter-spacing: 0.08em;
    margin-bottom: 8px;
    font-weight: 500;
  }
  .modal-field input {
    width: 100%;
    padding: 14px 18px;
    background: rgba(15, 10, 13, 0.6);
    border: 1px solid var(--glass-border);
    border-radius: 14px;
    color: var(--text);
    font-family: inherit;
    font-size: 0.92rem;
    outline: none;
    transition: all .3s;
    cursor: none;
  }
  .modal-field input:focus {
    border-color: var(--gold);
    box-shadow: 0 0 0 4px rgba(212, 175, 122, 0.1);
  }
  .modal-field input::placeholder { color: #5a4d52; }

  .modal-btn {
    width: 100%;
    padding: 16px;
    background: linear-gradient(135deg, var(--gold), var(--gold-light));
    border: none;
    border-radius: 100px;
    color: #1a1216;
    font-family: inherit;
    font-size: 0.95rem;
    font-weight: 600;
    cursor: none;
    margin-top: 8px;
    transition: all .3s;
    box-shadow: 0 12px 32px rgba(212, 175, 122, 0.3);
  }
  .modal-btn:hover { transform: translateY(-2px); box-shadow: 0 18px 40px rgba(212, 175, 122, 0.45); }

  .modal-switch {
    text-align: center;
    margin-top: 22px;
    font-size: 0.85rem;
    color: var(--text-dim);
  }
  .modal-switch a {
    color: var(--gold);
    text-decoration: none;
    font-weight: 600;
    cursor: none;
    transition: color .3s;
  }
  .modal-switch a:hover { color: var(--gold-light); }

  /* ===== FOOTER ===== */
  footer {
    padding: 60px 6% 40px;
    border-top: 1px solid var(--glass-border);
    text-align: center;
    color: var(--text-dim);
    font-size: 0.85rem;
    font-weight: 300;
  }
  footer .footer-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.6rem;
    color: var(--text);
    margin-bottom: 12px;
  }
  footer .footer-logo i { color: var(--gold); margin-right: 8px; }
  footer .socials {
    display: flex;
    justify-content: center;
    gap: 14px;
    margin: 24px 0;
  }
  footer .socials a {
    width: 42px; height: 42px;
    border-radius: 50%;
    background: var(--glass);
    border: 1px solid var(--glass-border);
    color: var(--text-dim);
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all .3s;
    text-decoration: none;
    cursor: none;
  }
  footer .socials a:hover {
    border-color: var(--gold);
    color: var(--gold);
    transform: translateY(-3px);
  }

  /* ===== RESPONSIVE ===== */
  @media (max-width: 1024px) {
    .hero { grid-template-columns: 1fr; padding-top: 130px; }
    .hero-visual { max-width: 400px; margin: 0 auto; }
    .float-card-1 { left: 0; }
    .float-card-2 { right: 0; }
    .booking { grid-template-columns: 1fr; padding: 44px 32px; margin: 0 4%; }
  }

  @media (max-width: 700px) {
    .nav-links { display: none; }
    .menu-toggle { display: block; }
    nav { padding: 12px 20px; }
    section { padding: 80px 5%; }
    .hero { padding: 120px 5% 60px; }
    .booking { padding: 32px 22px; margin: 0 3%; border-radius: 28px; }
    .booking-form { grid-template-columns: 1fr; }
    .chat-panel { right: 15px; bottom: 100px; width: calc(100vw - 30px); height: 70vh; }
    .float-actions { bottom: 20px; right: 18px; }
    .fab { width: 52px; height: 52px; font-size: 1.3rem; }
    .modal-box { padding: 34px 26px; }
    .float-card { padding: 12px 16px; }
    .float-card .num { font-size: 1.3rem; }
  }

  /* Reveal utility */
  .reveal { opacity: 0; transform: translateY(40px); transition: all 1s cubic-bezier(0.2, 0.8, 0.2, 1); }
  .reveal.on { opacity: 1; transform: translateY(0); }
</style>
</head>
<body>

<!-- FUNDO ANIMADO -->
<div class="bg-orbs">
  <div class="orb orb-1"></div>
  <div class="orb orb-2"></div>
  <div class="orb orb-3"></div>
</div>
<div class="grain"></div>

<!-- CURSOR -->
<div class="cursor-dot"></div>
<div class="cursor-ring"></div>

<!-- NAV -->
<nav id="nav">
  <div class="logo"><i class="fas fa-spa"></i> Lumière</div>
  <div class="nav-links">
    <a href="#servicos">Serviços</a>
    <a href="#agendamento">Agendamento</a>
    <a href="#sobre">Sobre</a>
  </div>
  <div class="nav-actions">
    <button class="btn-ghost" id="openLogin">Entrar</button>
    <button class="btn-gold" id="openRegister">Agendar</button>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-text">
    <div class="badge"><i class="fas fa-star"></i> Studio de beleza premium · Desde 2015</div>
    <h1>Sua beleza, <em>redefinida</em> com arte e cuidado.</h1>
    <p>Experiências personalizadas de beleza e bem-estar em um ambiente onde cada detalhe foi pensado para você brilhar.</p>
    <div class="hero-cta">
      <button class="btn-primary" id="heroBook">
        <span>Agendar agora</span>
        <i class="fas fa-arrow-right"></i>
      </button>
      <a href="#servicos" class="btn-outline" style="text-decoration:none;">
        <i class="fas fa-play"></i> Ver serviços
      </a>
    </div>
  </div>

  <div class="hero-visual">
    <div class="visual-frame">
      <img src="https://images.unsplash.com/photo-1560066984-138dadb4c035?auto=format&fit=crop&w=800&q=80" alt="Salao de beleza">
      <div class="visual-content">
        <div class="rating">
          <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
          <span>· 4.9 (2.4k avaliações)</span>
        </div>
        <h3>Design de beleza com alma</h3>
      </div>
    </div>
    <div class="float-card float-card-1">
      <div class="num">12+</div>
      <div class="lbl">Anos de experiência</div>
    </div>
    <div class="float-card float-card-2">
      <div class="num">8k</div>
      <div class="lbl">Clientes felizes</div>
    </div>
  </div>
</section>

<!-- SERVIÇOS -->
<section id="servicos">
  <div class="reveal">
    <div class="section-label">Nossos Serviços</div>
    <h2 class="section-title">Cuidados <em>exclusivos</em> para realçar sua essência.</h2>
    <p class="section-sub">Do corte ao spa capilar, cada serviço é conduzido por especialistas apaixonados pelo que fazem.</p>
  </div>

  <div class="services-grid" id="servicesGrid">
    <div class="service-card reveal">
      <div class="service-icon"><i class="fas fa-scissors"></i></div>
      <h3>Corte & Styling</h3>
      <p>Cortes contemporâneos e finalização profissional que valorizam seu estilo único.</p>
      <div class="service-price">
        <span class="price">A partir de R$ 80</span>
        <span class="arrow"><i class="fas fa-arrow-right"></i></span>
      </div>
    </div>
    <div class="service-card reveal">
      <div class="service-icon"><i class="fas fa-palette"></i></div>
      <h3>Coloração Premium</h3>
      <p>Mechas, balayage, iluminado e técnicas exclusivas com produtos de alta performance.</p>
      <div class="service-price">
        <span class="price">A partir de R$ 180</span>
        <span class="arrow"><i class="fas fa-arrow-right"></i></span>
      </div>
    </div>
    <div class="service-card reveal">
      <div class="service-icon"><i class="fas fa-spa"></i></div>
      <h3>Tratamentos & Spa</h3>
      <p>Hidratação profunda, reconstrução e rituais de spa capilar relaxantes.</p>
      <div class="service-price">
        <span class="price">A partir de R$ 120</span>
        <span class="arrow"><i class="fas fa-arrow-right"></i></span>
      </div>
    </div>
    <div class="service-card reveal">
      <div class="service-icon"><i class="fas fa-hand-sparkles"></i></div>
      <h3>Nail Design</h3>
      <p>Manicure, pedicure e alongamentos com acabamento impecável e duradouro.</p>
      <div class="service-price">
        <span class="price">A partir de R$ 60</span>
        <span class="arrow"><i class="fas fa-arrow-right"></i></span>
      </div>
    </div>
    <div class="service-card reveal">
      <div class="service-icon"><i class="fas fa-eye"></i></div>
      <h3>Design de Sobrancelhas</h3>
      <p>Design personalizado, micropigmentação e henna com precisão milimétrica.</p>
      <div class="service-price">
        <span class="price">A partir de R$ 50</span>
        <span class="arrow"><i class="fas fa-arrow-right"></i></span>
      </div>
    </div>
    <div class="service-card reveal">
      <div class="service-icon"><i class="fas fa-magic"></i></div>
      <h3>Maquiagem & Noivas</h3>
      <p>Produções exclusivas para eventos, noivas e ocasiões especiais.</p>
      <div class="service-price">
        <span class="price">A partir de R$ 200</span>
        <span class="arrow"><i class="fas fa-arrow-right"></i></span>
      </div>
    </div>
  </div>
</section>

<!-- AGENDAMENTO -->
<section id="agendamento">
  <div class="booking reveal">
    <div class="booking-info">
      <div class="section-label">Reserva Rápida</div>
      <h2>Agende seu <em>momento</em> em poucos cliques.</h2>
      <p>Escolha o serviço, o profissional e o horário perfeito. Confirmamos em até 5 minutos pelo WhatsApp.</p>
      <ul class="booking-features">
        <li><i class="fas fa-check"></i> Confirmação em até 5 minutos</li>
        <li><i class="fas fa-check"></i> Reagendamento gratuito</li>
        <li><i class="fas fa-check"></i> Lembrete automático por WhatsApp</li>
      </ul>
    </div>

    <form class="booking-form" id="bookingForm">
      <div class="form-field">
        <label>Nome</label>
        <input type="text" placeholder="Como podemos te chamar?" required>
      </div>
      <div class="form-field">
        <label>Telefone</label>
        <input type="tel" placeholder="(11) 99999-9999" required>
      </div>
      <div class="form-field">
        <label>Serviço</label>
        <select required>
          <option value="">Selecione o serviço</option>
          <option>Corte & Styling</option>
          <option>Coloração Premium</option>
          <option>Tratamentos & Spa</option>
          <option>Nail Design</option>
          <option>Design de Sobrancelhas</option>
          <option>Maquiagem & Noivas</option>
        </select>
      </div>
      <div class="form-field">
        <label>Profissional</label>
        <select required>
          <option value="">Qualquer disponível</option>
          <option>Ana Clara</option>
          <option>Beatriz Lima</option>
          <option>Carla Souza</option>
        </select>
      </div>
      <div class="form-field">
        <label>Data</label>
        <input type="date" required>
      </div>
      <div class="form-field">
        <label>Horário</label>
        <input type="time" required>
      </div>
      <button type="submit" class="btn-submit">
        <i class="fas fa-calendar-check"></i> Confirmar agendamento
      </button>
    </form>
  </div>
</section>

<!-- SOBRE / FOOTER -->
<footer id="sobre">
  <div class="footer-logo"><i class="fas fa-spa"></i> Lumière Studio</div>
  <p>Beleza redefinida com arte, ciência e cuidado humano.</p>
  <div class="socials">
    <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
    <a href="#" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>
    <a href="#" aria-label="TikTok"><i class="fab fa-tiktok"></i></a>
    <a href="#" aria-label="Pinterest"><i class="fab fa-pinterest-p"></i></a>
  </div>
  <p>© 2025 Lumière Studio · Rua das Flores, 123 · São Paulo</p>
</footer>

<!-- FLOAT ACTIONS -->
<div class="float-actions">
  <a href="https://wa.me/5511999999999?text=Olá!%20Gostaria%20de%20agendar%20um%20horário." class="fab fab-whatsapp" data-tip="WhatsApp" target="_blank" rel="noopener">
    <i class="fab fa-whatsapp"></i>
    <span class="pulse"></span>
  </a>
  <button class="fab fab-chat" id="fabChat" data-tip="Assistente virtual">
    <i class="fas fa-comment-dots"></i>
  </button>
  <button class="fab fab-top" id="fabTop" data-tip="Voltar ao topo">
    <i class="fas fa-arrow-up"></i>
  </button>
</div>

<!-- CHATBOT -->
<div class="chat-panel" id="chatPanel">
  <div class="chat-header">
    <div class="chat-avatar"><i class="fas fa-sparkles"></i></div>
    <div class="chat-header-info">
      <h4>Lumi · Assistente</h4>
      <p><i class="fas fa-circle" style="font-size:0.5rem;"></i> Online agora</p>
    </div>
    <button class="chat-close" id="chatClose"><i class="fas fa-times"></i></button>
  </div>
  <div class="chat-body" id="chatBody">
    <div class="msg msg-bot">Olá! ✨ Sou a Lumi, sua assistente virtual. Como posso iluminar seu dia?</div>
  </div>
  <div class="quick-replies" id="quickReplies">
    <button class="quick-reply" data-msg="Quero agendar um horário">📅 Agendar</button>
    <button class="quick-reply" data-msg="Quais são os preços?">💰 Preços</button>
    <button class="quick-reply" data-msg="Onde vocês ficam?">📍 Endereço</button>
    <button class="quick-reply" data-msg="Qual o horário de funcionamento?">🕐 Horários</button>
  </div>
  <div class="chat-input-area">
    <input type="text" id="chatInput" placeholder="Escreva sua mensagem...">
    <button class="chat-send" id="chatSend"><i class="fas fa-paper-plane"></i></button>
  </div>
</div>

<!-- MODAL LOGIN -->
<div class="modal-bg" id="loginModal">
  <div class="modal-box">
    <button class="modal-close" data-close="loginModal"><i class="fas fa-times"></i></button>
    <div class="modal-icon"><i class="fas fa-fingerprint"></i></div>
    <h2>Bem-vinda <em>de volta</em></h2>
    <p class="modal-sub">Acesse sua conta para gerenciar agendamentos.</p>
    <form id="loginForm">
      <div class="modal-field">
        <label>E-mail</label>
        <input type="email" placeholder="seu@email.com" required>
      </div>
      <div class="modal-field">
        <label>Senha</label>
        <input type="password" placeholder="••••••••" required>
      </div>
      <button type="submit" class="modal-btn">Entrar</button>
      <div class="modal-switch">Ainda não tem conta? <a data-switch="register">Criar agora</a></div>
    </form>
  </div>
</div>

<!-- MODAL CADASTRO -->
<div class="modal-bg" id="registerModal">
  <div class="modal-box">
    <button class="modal-close" data-close="registerModal"><i class="fas fa-times"></i></button>
    <div class="modal-icon"><i class="fas fa-user-plus"></i></div>
    <h2>Crie sua <em>conta</em></h2>
    <p class="modal-sub">Faça parte do clube Lumière e receba benefícios exclusivos.</p>
    <form id="registerForm">
      <div class="modal-field">
        <label>Nome completo</label>
        <input type="text" placeholder="Seu nome" required>
      </div>
      <div class="modal-field">
        <label>E-mail</label>
        <input type="email" placeholder="seu@email.com" required>
      </div>
      <div class="modal-field">
        <label>Senha</label>
        <input type="password" placeholder="Mínimo 6 caracteres" required>
      </div>
      <button type="submit" class="modal-btn">Criar conta</button>
      <div class="modal-switch">Já possui conta? <a data-switch="login">Fazer login</a></div>
    </form>
  </div>
</div>

<script>
(() => {
  // ===== CURSOR =====
  const dot = document.querySelector('.cursor-dot');
  const ring = document.querySelector('.cursor-ring');
  let mx = 0, my = 0, rx = 0, ry = 0;

  window.addEventListener('mousemove', (e) => {
    mx = e.clientX; my = e.clientY;
    dot.style.left = mx + 'px';
    dot.style.top = my + 'px';
  });

  function animateRing() {
    rx += (mx - rx) * 0.15;
    ry += (my - ry) * 0.15;
    ring.style.left = rx + 'px';
    ring.style.top = ry + 'px';
    requestAnimationFrame(animateRing);
  }
  animateRing();

  document.querySelectorAll('a, button, input, select, .service-card, .quick-reply').forEach(el => {
    el.addEventListener('mouseenter', () => ring.classList.add('hover'));
    el.addEventListener('mouseleave', () => ring.classList.remove('hover'));
  });

  // ===== NAV SCROLL =====
  const nav = document.getElementById('nav');
  const fabTop = document.getElementById('fabTop');
  window.addEventListener('scroll', () => {
    nav.classList.toggle('scrolled', window.scrollY > 50);
    fabTop.classList.toggle('show', window.scrollY > 400);
  });

  fabTop.addEventListener('click', () => window.scrollTo({ top: 0, behavior: 'smooth' }));

  // ===== REVEAL =====
  const io = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('on');
        io.unobserve(e.target);
      }
    });
  }, { threshold: 0.15 });
  document.querySelectorAll('.reveal').forEach(el => io.observe(el));

  // ===== MODAIS =====
  const loginModal = document.getElementById('loginModal');
  const registerModal = document.getElementById('registerModal');
  const openModal = (m) => m.classList.add('open');
  const closeModal = (m) => m.classList.remove('open');

  document.getElementById('openLogin').addEventListener('click', () => openModal(loginModal));
  document.getElementById('openRegister').addEventListener('click', () => openModal(registerModal));

  document.querySelectorAll('[data-close]').forEach(btn => {
    btn.addEventListener('click', () => closeModal(document.getElementById(btn.dataset.close)));
  });

  document.querySelectorAll('.modal-bg').forEach(bg => {
    bg.addEventListener('click', (e) => { if (e.target === bg) closeModal(bg); });
  });

  document.querySelectorAll('[data-switch]').forEach(a => {
    a.addEventListener('click', () => {
      if (a.dataset.switch === 'register') { closeModal(loginModal); openModal(registerModal); }
      else { closeModal(registerModal); openModal(loginModal); }
    });
  });

  document.getElementById('loginForm').addEventListener('submit', (e) => {
    e.preventDefault();
    closeModal(loginModal);
    showToast('✨ Login realizado com sucesso!');
    e.target.reset();
  });
  document.getElementById('registerForm').addEventListener('submit', (e) => {
    e.preventDefault();
    closeModal(registerModal);
    showToast('🎉 Conta criada! Bem-vinda ao Lumière.');
    e.target.reset();
  });

  // ===== BOOKING =====
  document.getElementById('bookingForm').addEventListener('submit', (e) => {
    e.preventDefault();
    showToast('✅ Agendamento confirmado! Enviaremos os detalhes no WhatsApp.');
    e.target.reset();
  });

  document.getElementById('heroBook').addEventListener('click', () => {
    document.getElementById('agendamento').scrollIntoView({ behavior: 'smooth' });
  });

  // ===== TOAST =====
  function showToast(msg) {
    const t = document.createElement('div');
    t.textContent = msg;
    Object.assign(t.style, {
      position: 'fixed', bottom: '30px', left: '50%',
      transform: 'translateX(-50%) translateY(100px)',
      background: 'linear-gradient(135deg, #d4af7a, #e6c893)',
      color: '#1a1216', padding: '14px 26px', borderRadius: '100px',
      fontWeight: '600', fontSize: '0.9rem', zIndex: '9999',
      boxShadow: '0 20px 40px rgba(212,175,122,0.4)',
      transition: 'transform .4s cubic-bezier(0.2,0.8,0.2,1)',
      fontFamily: 'Inter, sans-serif'
    });
    document.body.appendChild(t);
    requestAnimationFrame(() => t.style.transform = 'translateX(-50%) translateY(0)');
    setTimeout(() => {
      t.style.transform = 'translateX(-50%) translateY(100px)';
      setTimeout(() => t.remove(), 500);
    }, 3200);
  }

  // ===== CHATBOT =====
  const chatPanel = document.getElementById('chatPanel');
  const fabChat = document.getElementById('fabChat');
  const chatClose = document.getElementById('chatClose');
  const chatBody = document.getElementById('chatBody');
  const chatInput = document.getElementById('chatInput');
  const chatSend = document.getElementById('chatSend');
  const quickReplies = document.getElementById('quickReplies');

  fabChat.addEventListener('click', () => {
    chatPanel.classList.toggle('open');
    if (chatPanel.classList.contains('open')) setTimeout(() => chatInput.focus(), 300);
  });
  chatClose.addEventListener('click', () => chatPanel.classList.remove('open'));

  const botReplies = {
    agendar: 'Perfeito! 📅 Você pode agendar diretamente no formulário do site ou me informar: serviço desejado, data e horário preferido.',
    preço: 'Nossos valores começam em:\n• Corte: R$ 80\n• Coloração: R$ 180\n• Tratamentos: R$ 120\n• Nail Design: R$ 60\n• Sobrancelhas: R$ 50\n• Maquiagem: R$ 200\n\nQuer que eu já reserve um horário?',
    preco: 'Nossos valores começam em:\n• Corte: R$ 80\n• Coloração: R$ 180\n• Tratamentos: R$ 120\n• Nail Design: R$ 60\n• Sobrancelhas: R$ 50\n• Maquiagem: R$ 200\n\nQuer que eu já reserve um horário?',
    endereco: '📍 Estamos na Rua das Flores, 123 — Centro, São Paulo. Fácil acesso pelo metrô (estação República).',
    horario: '🕐 Atendemos de terça a sábado, das 9h às 19h. Domingos e segundas mediante agendamento especial.',
    oi: 'Olá! ✨ Como posso tornar seu dia mais luminoso?',
    ola: 'Olá! ✨ Como posso tornar seu dia mais luminoso?',
    obrigado: 'Por nada! 💖 Estou sempre por aqui se precisar.',
    obrigada: 'Por nada! 💖 Estou sempre por aqui se precisar.',
    default: 'Que interessante! Para te ajudar melhor, posso falar sobre agendamentos, preços, endereço ou horários. Sobre qual você quer saber?'
  };

  function getReply(text) {
    const t = text.toLowerCase();
    if (t.includes('agendar') || t.includes('marcar') || t.includes('horário') && t.includes('quero')) return botReplies.agendar;
    if (t.includes('preço') || t.includes('valor') || t.includes('custa') || t.includes('quanto')) return botReplies.preco;
    if (t.includes('onde') || t.includes('endereço') || t.includes('local') || t.includes('fica')) return botReplies.endereco;
    if (t.includes('horário') || t.includes('funcionamento') || t.includes('aberto') || t.includes('que horas')) return botReplies.horario;
    if (t.match(/\b(oi|olá|ola|hey|bom dia|boa tarde|boa noite)\b/)) return botReplies.oi;
    if (t.includes('obrigad')) return botReplies.obrigado;
    return botReplies.default;
  }

  function addMsg(text, type) {
    const d = document.createElement('div');
    d.className = 'msg msg-' + type;
    d.textContent = text;
    chatBody.appendChild(d);
    chatBody.scrollTop = chatBody.scrollHeight;
  }

  function addTyping() {
    const d = document.createElement('div');
    d.className = 'msg msg-bot msg-typing';
    d.id = 'typingIndicator';
    d.innerHTML = '<span></span><span></span><span></span>';
    chatBody.appendChild(d);
    chatBody.scrollTop = chatBody.scrollHeight;
    return d;
  }

  function sendMessage(text) {
    if (!text.trim()) return;
    addMsg(text, 'user');
    chatInput.value = '';
    quickReplies.style.display = 'none';
    const typing = addTyping();
    setTimeout(() => {
      typing.remove();
      addMsg(getReply(text), 'bot');
    }, 900);
  }

  chatSend.addEventListener('click', () => sendMessage(chatInput.value));
  chatInput.addEventListener('keypress', (e) => {
    if (e.key === 'Enter') { e.preventDefault(); sendMessage(chatInput.value); }
  });

  document.querySelectorAll('.quick-reply').forEach(btn => {
    btn.addEventListener('click', () => sendMessage(btn.dataset.msg));
  });
})();
</script>
</body>
</html>
