<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Éclat Salon | Beleza & Estilo</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,400;0,9..144,500;0,9..144,600;0,9..144,700;1,9..144,400&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --emerald-50: #f0faf5;
      --emerald-100: #d9f2e4;
      --emerald-200: #b3e5ca;
      --emerald-300: #7dd3a5;
      --emerald-400: #4abf7e;
      --emerald-500: #1e9e5e;
      --emerald-600: #0d7a45;
      --emerald-700: #0a5e35;
      --emerald-800: #084a2a;
      --emerald-900: #063d23;
      --sand-50: #faf8f5;
      --sand-100: #f4efe8;
      --sand-200: #e8dfd3;
      --sand-300: #d9c9b6;
      --sand-400: #c9b39a;
      --sand-500: #b89d7f;
      --sand-600: #a88666;
      --sand-700: #8c6d52;
      --sand-800: #725a44;
      --sand-900: #5e4a39;
      --ink-900: #0f1512;
      --ink-700: #2c3a33;
      --ink-500: #5a6b62;
      --ink-300: #93a39a;
      --white: #ffffff;
      --whatsapp: #25D366;
      --whatsapp-dark: #128C7E;
      --shadow-sm: 0 1px 3px rgba(15, 21, 18, 0.04);
      --shadow-md: 0 8px 24px -6px rgba(15, 21, 18, 0.08);
      --shadow-lg: 0 24px 48px -12px rgba(15, 21, 18, 0.12);
      --shadow-xl: 0 32px 64px -16px rgba(15, 21, 18, 0.18);
      --radius-sm: 10px;
      --radius-md: 16px;
      --radius-lg: 24px;
      --radius-xl: 32px;
      --radius-full: 9999px;
      --transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
      background-color: var(--sand-50);
      color: var(--ink-700);
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
      overflow-x: hidden;
    }

    h1, h2, h3, h4, .font-display {
      font-family: 'Fraunces', Georgia, serif;
      font-weight: 500;
      letter-spacing: -0.02em;
      line-height: 1.15;
      color: var(--ink-900);
    }

    .container {
      max-width: 1240px;
      margin: 0 auto;
      padding: 0 24px;
      width: 100%;
    }

    /* ---------- HEADER ---------- */
    header {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      z-index: 1000;
      padding: 16px 0;
      transition: all var(--transition);
      background: transparent;
    }

    header.scrolled {
      background: rgba(250, 248, 245, 0.85);
      backdrop-filter: blur(16px) saturate(180%);
      -webkit-backdrop-filter: blur(16px) saturate(180%);
      padding: 10px 0;
      box-shadow: var(--shadow-sm);
      border-bottom: 1px solid rgba(232, 223, 211, 0.6);
    }

    .header-flex {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 24px;
    }

    .logo {
      font-family: 'Fraunces', serif;
      font-size: 1.7rem;
      font-weight: 600;
      color: var(--ink-900);
      letter-spacing: -0.03em;
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 2px;
    }

    .logo span {
      color: var(--emerald-500);
      font-style: italic;
      font-weight: 400;
    }

    .logo-dot {
      width: 7px;
      height: 7px;
      background: var(--emerald-500);
      border-radius: 50%;
      display: inline-block;
      margin-left: 4px;
      margin-bottom: 8px;
    }

    .nav-links {
      display: flex;
      gap: 36px;
      align-items: center;
    }

    .nav-links a {
      text-decoration: none;
      color: var(--ink-700);
      font-weight: 500;
      font-size: 0.94rem;
      transition: color var(--transition);
      position: relative;
    }

    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -6px;
      left: 0;
      width: 0;
      height: 2px;
      background: var(--emerald-500);
      border-radius: 2px;
      transition: width var(--transition);
    }

    .nav-links a:hover {
      color: var(--emerald-600);
    }

    .nav-links a:hover::after {
      width: 100%;
    }

    .btn-header {
      background: var(--whatsapp);
      color: var(--white);
      padding: 11px 26px;
      border-radius: var(--radius-full);
      font-weight: 600;
      font-size: 0.9rem;
      text-decoration: none;
      transition: all var(--transition);
      box-shadow: 0 4px 14px -4px rgba(37, 211, 102, 0.4);
      border: none;
      cursor: pointer;
      white-space: nowrap;
      display: inline-flex;
      align-items: center;
      gap: 8px;
    }

    .btn-header:hover {
      background: var(--whatsapp-dark);
      transform: translateY(-2px);
      box-shadow: 0 8px 22px -6px rgba(37, 211, 102, 0.5);
    }

    .btn-header i {
      font-size: 1rem;
    }

    .menu-toggle {
      display: none;
      background: none;
      border: none;
      font-size: 1.4rem;
      color: var(--ink-900);
      cursor: pointer;
      padding: 8px;
    }

    /* ---------- HERO ---------- */
    .hero {
      padding: 160px 0 100px;
      position: relative;
      overflow: hidden;
      background: radial-gradient(ellipse 80% 60% at 70% 0%, var(--emerald-50) 0%, var(--sand-50) 60%);
    }

    .hero::before {
      content: '';
      position: absolute;
      top: -10%;
      right: -5%;
      width: 600px;
      height: 600px;
      background: radial-gradient(circle, rgba(30, 158, 94, 0.06) 0%, transparent 70%);
      border-radius: 50%;
      pointer-events: none;
    }

    .hero::after {
      content: '';
      position: absolute;
      bottom: -20%;
      left: -10%;
      width: 500px;
      height: 500px;
      background: radial-gradient(circle, rgba(184, 157, 127, 0.08) 0%, transparent 70%);
      border-radius: 50%;
      pointer-events: none;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 64px;
      align-items: center;
      position: relative;
      z-index: 1;
    }

    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: var(--white);
      border: 1px solid var(--emerald-100);
      padding: 8px 16px 8px 10px;
      border-radius: var(--radius-full);
      font-size: 0.82rem;
      font-weight: 600;
      color: var(--emerald-700);
      margin-bottom: 28px;
      box-shadow: var(--shadow-sm);
    }

    .hero-badge .dot {
      width: 8px;
      height: 8px;
      background: var(--emerald-500);
      border-radius: 50%;
      position: relative;
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.4; }
    }

    .hero h1 {
      font-size: clamp(2.4rem, 5vw, 4rem);
      font-weight: 500;
      margin-bottom: 24px;
      letter-spacing: -0.03em;
    }

    .hero h1 i {
      font-style: italic;
      color: var(--emerald-500);
      font-weight: 400;
      position: relative;
    }

    .hero h1 i::after {
      content: '';
      position: absolute;
      bottom: 8px;
      left: 0;
      right: 0;
      height: 8px;
      background: var(--emerald-100);
      z-index: -1;
      border-radius: 4px;
    }

    .hero p {
      font-size: clamp(1rem, 1.2vw, 1.15rem);
      color: var(--ink-500);
      margin-bottom: 40px;
      max-width: 520px;
      font-weight: 400;
    }

    .hero-actions {
      display: flex;
      align-items: center;
      gap: 24px;
      flex-wrap: wrap;
    }

    .btn-primary {
      background: var(--whatsapp);
      color: var(--white);
      padding: 17px 40px;
      border-radius: var(--radius-full);
      font-weight: 600;
      font-size: 1rem;
      border: none;
      cursor: pointer;
      transition: all var(--transition);
      box-shadow: 0 10px 28px -8px rgba(37, 211, 102, 0.5);
      display: inline-flex;
      align-items: center;
      gap: 10px;
      text-decoration: none;
      letter-spacing: 0.2px;
      font-family: 'Inter', sans-serif;
    }

    .btn-primary:hover {
      background: var(--whatsapp-dark);
      transform: translateY(-3px);
      box-shadow: 0 18px 36px -10px rgba(37, 211, 102, 0.6);
    }

    .btn-primary i {
      transition: transform var(--transition);
    }

    .btn-primary:hover i {
      transform: translateX(4px);
    }

    .hero-stats {
      display: flex;
      gap: 40px;
      margin-top: 56px;
      padding-top: 32px;
      border-top: 1px solid var(--sand-200);
    }

    .stat h3 {
      font-size: 1.9rem;
      font-weight: 600;
      color: var(--emerald-600);
      line-height: 1;
      margin-bottom: 6px;
      font-family: 'Fraunces', serif;
    }

    .stat p {
      font-size: 0.85rem;
      color: var(--ink-500);
      margin: 0;
      font-weight: 500;
    }

    .hero-visual {
      position: relative;
    }

    .hero-image-wrapper {
      position: relative;
      border-radius: var(--radius-xl);
      overflow: hidden;
      aspect-ratio: 4/5;
      box-shadow: var(--shadow-xl);
      background: var(--sand-200);
    }

    .hero-image-wrapper img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
      transition: transform 0.7s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .hero-image-wrapper:hover img {
      transform: scale(1.04);
    }

    .floating-card {
      position: absolute;
      background: rgba(255, 255, 255, 0.92);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 255, 255, 0.6);
      border-radius: var(--radius-md);
      padding: 16px 20px;
      box-shadow: var(--shadow-lg);
      display: flex;
      align-items: center;
      gap: 12px;
      animation: float 6s ease-in-out infinite;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-12px); }
    }

    .floating-card.card-1 {
      bottom: 32px;
      left: -24px;
      animation-delay: 0s;
    }

    .floating-card.card-2 {
      top: 40px;
      right: -20px;
      animation-delay: 3s;
    }

    .floating-icon {
      width: 42px;
      height: 42px;
      border-radius: 50%;
      background: var(--emerald-50);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--emerald-600);
      font-size: 1rem;
      flex-shrink: 0;
    }

    .floating-card strong {
      display: block;
      font-size: 0.9rem;
      color: var(--ink-900);
      font-weight: 600;
      line-height: 1.3;
    }

    .floating-card small {
      font-size: 0.78rem;
      color: var(--ink-500);
    }

    /* ---------- MARQUEE ---------- */
    .marquee-section {
      padding: 32px 0;
      background: var(--ink-900);
      overflow: hidden;
      white-space: nowrap;
    }

    .marquee {
      display: inline-flex;
      gap: 56px;
      animation: scroll 30s linear infinite;
    }

    @keyframes scroll {
      0% { transform: translateX(0); }
      100% { transform: translateX(-50%); }
    }

    .marquee-item {
      display: inline-flex;
      align-items: center;
      gap: 56px;
      color: var(--sand-200);
      font-size: 1.1rem;
      font-weight: 400;
      font-family: 'Fraunces', serif;
      font-style: italic;
      letter-spacing: 0.02em;
    }

    .marquee-item i {
      color: var(--emerald-400);
      font-size: 0.9rem;
      font-style: normal;
    }

    /* ---------- SECTION BASE ---------- */
    section {
      padding: 100px 0;
    }

    .section-head {
      text-align: center;
      max-width: 680px;
      margin: 0 auto 64px;
    }

    .section-label {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-size: 0.8rem;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--emerald-600);
      font-weight: 700;
      margin-bottom: 16px;
    }

    .section-label::before,
    .section-label::after {
      content: '';
      width: 20px;
      height: 1.5px;
      background: var(--emerald-300);
      border-radius: 2px;
    }

    .section-title {
      font-size: clamp(1.9rem, 3.5vw, 2.8rem);
      font-weight: 500;
      letter-spacing: -0.03em;
    }

    .section-title i {
      font-style: italic;
      color: var(--emerald-500);
      font-weight: 400;
    }

    .section-head p {
      color: var(--ink-500);
      font-size: 1.05rem;
      margin-top: 16px;
    }

    /* ---------- FEATURES ---------- */
    .features-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 24px;
    }

    .feature-card {
      background: var(--white);
      padding: 40px 32px;
      border-radius: var(--radius-lg);
      transition: all var(--transition);
      border: 1px solid var(--sand-200);
      position: relative;
      overflow: hidden;
    }

    .feature-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 3px;
      background: linear-gradient(90deg, var(--emerald-400), var(--emerald-600));
      transform: scaleX(0);
      transform-origin: left;
      transition: transform var(--transition);
    }

    .feature-card:hover {
      transform: translateY(-6px);
      box-shadow: var(--shadow-lg);
      border-color: transparent;
    }

    .feature-card:hover::before {
      transform: scaleX(1);
    }

    .feature-icon {
      width: 56px;
      height: 56px;
      border-radius: var(--radius-md);
      background: var(--emerald-50);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.4rem;
      color: var(--emerald-600);
      margin-bottom: 28px;
      transition: all var(--transition);
    }

    .feature-card:hover .feature-icon {
      background: var(--emerald-600);
      color: var(--white);
      transform: rotate(-6deg) scale(1.05);
    }

    .feature-card h3 {
      font-size: 1.3rem;
      margin-bottom: 12px;
      font-weight: 600;
    }

    .feature-card p {
      color: var(--ink-500);
      font-size: 0.95rem;
      font-weight: 400;
    }

    /* ---------- SERVICES ---------- */
    .services {
      background: var(--ink-900);
      position: relative;
      overflow: hidden;
    }

    .services::before {
      content: '';
      position: absolute;
      top: -50%;
      right: -20%;
      width: 700px;
      height: 700px;
      background: radial-gradient(circle, rgba(30, 158, 94, 0.15) 0%, transparent 60%);
      border-radius: 50%;
      pointer-events: none;
    }

    .services .section-label {
      color: var(--emerald-400);
    }

    .services .section-label::before,
    .services .section-label::after {
      background: var(--emerald-500);
    }

    .services .section-title {
      color: var(--white);
    }

    .services .section-title i {
      color: var(--emerald-400);
    }

    .services .section-head p {
      color: var(--ink-300);
    }

    .services-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 20px;
      position: relative;
      z-index: 1;
    }

    .service-item {
      background: rgba(255, 255, 255, 0.04);
      backdrop-filter: blur(8px);
      -webkit-backdrop-filter: blur(8px);
      border: 1px solid rgba(255, 255, 255, 0.08);
      border-radius: var(--radius-lg);
      padding: 36px 24px;
      text-align: center;
      transition: all var(--transition);
      cursor: default;
      text-decoration: none;
      display: block;
    }

    .service-item:hover {
      background: var(--whatsapp);
      border-color: var(--whatsapp);
      transform: translateY(-6px);
      box-shadow: 0 20px 40px -12px rgba(37, 211, 102, 0.5);
    }

    .service-icon {
      width: 60px;
      height: 60px;
      border-radius: 50%;
      background: rgba(30, 158, 94, 0.15);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.4rem;
      color: var(--emerald-400);
      margin: 0 auto 24px;
      transition: all var(--transition);
    }

    .service-item:hover .service-icon {
      background: rgba(255, 255, 255, 0.2);
      color: var(--white);
      transform: scale(1.1);
    }

    .service-item h4 {
      font-size: 1.15rem;
      margin-bottom: 10px;
      font-weight: 600;
      color: var(--white);
      transition: color var(--transition);
    }

    .service-item p {
      color: var(--ink-300);
      font-size: 0.88rem;
      font-weight: 400;
      transition: color var(--transition);
    }

    .service-item:hover p {
      color: rgba(255, 255, 255, 0.95);
    }

    /* ---------- TESTIMONIAL ---------- */
    .testimonial-section {
      background: var(--sand-50);
    }

    .testimonial-card {
      max-width: 860px;
      margin: 0 auto;
      background: var(--white);
      border-radius: var(--radius-xl);
      padding: 64px 56px;
      box-shadow: var(--shadow-lg);
      text-align: center;
      border: 1px solid var(--sand-200);
      position: relative;
    }

    .testimonial-card .quote-mark {
      font-family: 'Fraunces', serif;
      font-size: 5rem;
      line-height: 1;
      color: var(--emerald-200);
      position: absolute;
      top: 24px;
      left: 40px;
      font-style: italic;
      font-weight: 600;
      user-select: none;
    }

    .testimonial-text {
      font-family: 'Fraunces', serif;
      font-size: clamp(1.15rem, 2vw, 1.5rem);
      line-height: 1.6;
      font-weight: 400;
      font-style: italic;
      color: var(--ink-700);
      margin-bottom: 36px;
      position: relative;
      z-index: 1;
    }

    .testimonial-author {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 14px;
    }

    .author-avatar {
      width: 52px;
      height: 52px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--emerald-400), var(--emerald-600));
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--white);
      font-weight: 700;
      font-size: 1.1rem;
      font-family: 'Fraunces', serif;
    }

    .author-info {
      text-align: left;
    }

    .author-info strong {
      display: block;
      color: var(--ink-900);
      font-weight: 600;
      font-size: 0.98rem;
    }

    .author-info span {
      color: var(--ink-500);
      font-size: 0.85rem;
      font-weight: 400;
    }

    .stars {
      color: var(--sand-500);
      font-size: 0.8rem;
      letter-spacing: 2px;
      margin-bottom: 4px;
    }

    /* ---------- CTA FINAL ---------- */
    .cta-final {
      padding: 0 0 100px;
    }

    .cta-box {
      background: linear-gradient(135deg, var(--emerald-700) 0%, var(--emerald-600) 50%, var(--emerald-500) 100%);
      border-radius: var(--radius-xl);
      padding: 72px 64px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 48px;
      position: relative;
      overflow: hidden;
      box-shadow: 0 32px 64px -20px rgba(13, 122, 69, 0.4);
    }

    .cta-box::before {
      content: '';
      position: absolute;
      top: -50%;
      right: -10%;
      width: 500px;
      height: 500px;
      background: radial-gradient(circle, rgba(255, 255, 255, 0.1) 0%, transparent 60%);
      border-radius: 50%;
      pointer-events: none;
    }

    .cta-box::after {
      content: '';
      position: absolute;
      bottom: -60%;
      left: -5%;
      width: 400px;
      height: 400px;
      background: radial-gradient(circle, rgba(255, 255, 255, 0.08) 0%, transparent 60%);
      border-radius: 50%;
      pointer-events: none;
    }

    .cta-text {
      position: relative;
      z-index: 1;
    }

    .cta-text h2 {
      font-size: clamp(1.8rem, 3vw, 2.5rem);
      color: var(--white);
      font-weight: 500;
      margin-bottom: 14px;
      letter-spacing: -0.03em;
    }

    .cta-text h2 i {
      font-style: italic;
      color: var(--emerald-100);
      font-weight: 400;
    }

    .cta-text p {
      color: rgba(255, 255, 255, 0.8);
      font-size: 1.05rem;
      font-weight: 400;
      max-width: 480px;
    }

    .btn-whatsapp {
      background: var(--white);
      color: var(--whatsapp-dark);
      padding: 18px 44px;
      border-radius: var(--radius-full);
      font-weight: 700;
      font-size: 1rem;
      text-decoration: none;
      transition: all var(--transition);
      display: inline-flex;
      align-items: center;
      gap: 12px;
      white-space: nowrap;
      position: relative;
      z-index: 1;
      box-shadow: 0 12px 28px -8px rgba(0, 0, 0, 0.25);
      font-family: 'Inter', sans-serif;
    }

    .btn-whatsapp:hover {
      transform: translateY(-3px) scale(1.02);
      box-shadow: 0 20px 40px -10px rgba(0, 0, 0, 0.35);
      background: var(--whatsapp);
      color: var(--white);
    }

    .btn-whatsapp i {
      font-size: 1.3rem;
      transition: transform var(--transition);
    }

    .btn-whatsapp:hover i {
      transform: rotate(-10deg) scale(1.1);
    }

    /* ---------- WHATSAPP FLUTUANTE ---------- */
    .whatsapp-float {
      position: fixed;
      bottom: 28px;
      right: 28px;
      width: 60px;
      height: 60px;
      background: var(--whatsapp);
      color: var(--white);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.8rem;
      box-shadow: 0 8px 24px -4px rgba(37, 211, 102, 0.5);
      z-index: 999;
      text-decoration: none;
      transition: all var(--transition);
      animation: whatsappPulse 2.5s infinite;
    }

    .whatsapp-float:hover {
      background: var(--whatsapp-dark);
      transform: scale(1.1) rotate(-6deg);
      box-shadow: 0 12px 32px -4px rgba(37, 211, 102, 0.7);
    }

    @keyframes whatsappPulse {
      0%, 100% { box-shadow: 0 8px 24px -4px rgba(37, 211, 102, 0.5), 0 0 0 0 rgba(37, 211, 102, 0.5); }
      50% { box-shadow: 0 8px 24px -4px rgba(37, 211, 102, 0.5), 0 0 0 16px rgba(37, 211, 102, 0); }
    }

    .whatsapp-float .tooltip {
      position: absolute;
      right: 72px;
      background: var(--ink-900);
      color: var(--white);
      padding: 8px 14px;
      border-radius: var(--radius-sm);
      font-size: 0.85rem;
      font-weight: 500;
      white-space: nowrap;
      opacity: 0;
      pointer-events: none;
      transition: opacity var(--transition);
      font-family: 'Inter', sans-serif;
    }

    .whatsapp-float .tooltip::after {
      content: '';
      position: absolute;
      right: -6px;
      top: 50%;
      transform: translateY(-50%);
      border: 6px solid transparent;
      border-left-color: var(--ink-900);
    }

    .whatsapp-float:hover .tooltip {
      opacity: 1;
    }

    /* ---------- FOOTER ---------- */
    footer {
      background: var(--ink-900);
      padding: 72px 0 0;
      color: var(--ink-300);
    }

    .footer-grid {
      display: grid;
      grid-template-columns: 1.6fr 1fr 1fr 1.3fr;
      gap: 48px;
      margin-bottom: 56px;
    }

    .footer-logo {
      font-family: 'Fraunces', serif;
      font-size: 1.6rem;
      font-weight: 600;
      color: var(--white);
      margin-bottom: 18px;
      display: flex;
      align-items: center;
      gap: 2px;
    }

    .footer-logo span {
      color: var(--emerald-400);
      font-style: italic;
      font-weight: 400;
    }

    .footer-about p {
      color: var(--ink-300);
      font-weight: 400;
      font-size: 0.92rem;
      max-width: 300px;
      margin-bottom: 24px;
      line-height: 1.7;
    }

    .social-icons {
      display: flex;
      gap: 10px;
    }

    .social-icons a {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 40px;
      height: 40px;
      background: rgba(255, 255, 255, 0.06);
      border: 1px solid rgba(255, 255, 255, 0.08);
      border-radius: 50%;
      color: var(--sand-200);
      text-decoration: none;
      transition: all var(--transition);
      font-size: 0.95rem;
    }

    .social-icons a:hover {
      background: var(--whatsapp);
      border-color: var(--whatsapp);
      color: var(--white);
      transform: translateY(-3px);
    }

    .footer-col h4 {
      font-size: 0.95rem;
      margin-bottom: 22px;
      font-weight: 600;
      color: var(--white);
      letter-spacing: 0.3px;
      font-family: 'Inter', sans-serif;
    }

    .footer-col ul {
      list-style: none;
    }

    .footer-col ul li {
      margin-bottom: 13px;
    }

    .footer-col ul a {
      text-decoration: none;
      color: var(--ink-300);
      font-weight: 400;
      transition: all var(--transition);
      font-size: 0.92rem;
      display: inline-flex;
      align-items: center;
      gap: 8px;
    }

    .footer-col ul a:hover {
      color: var(--emerald-400);
      transform: translateX(3px);
    }

    .footer-contact p {
      color: var(--ink-300);
      font-weight: 400;
      font-size: 0.92rem;
      margin-bottom: 16px;
      display: flex;
      align-items: flex-start;
      gap: 12px;
      line-height: 1.5;
    }

    .footer-contact i {
      color: var(--emerald-400);
      width: 16px;
      margin-top: 4px;
      flex-shrink: 0;
      font-size: 0.9rem;
    }

    .footer-contact a {
      color: var(--ink-300);
      text-decoration: none;
      transition: color var(--transition);
    }

    .footer-contact a:hover {
      color: var(--whatsapp);
    }

    .footer-bottom {
      border-top: 1px solid rgba(255, 255, 255, 0.08);
      padding: 28px 0;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      flex-wrap: wrap;
    }

    .footer-bottom p {
      color: var(--ink-500);
      font-size: 0.85rem;
      font-weight: 400;
    }

    .footer-bottom a {
      color: var(--ink-300);
      text-decoration: none;
      transition: color var(--transition);
    }

    .footer-bottom a:hover {
      color: var(--emerald-400);
    }

    /* ---------- RESPONSIVE ---------- */
    @media (max-width: 1080px) {
      .services-grid {
        grid-template-columns: repeat(2, 1fr);
      }
      .footer-grid {
        grid-template-columns: 1fr 1fr;
        gap: 40px;
      }
    }

    @media (max-width: 900px) {
      .nav-links {
        position: fixed;
        top: 0;
        right: -100%;
        width: min(320px, 80vw);
        height: 100vh;
        background: var(--white);
        flex-direction: column;
        align-items: flex-start;
        padding: 100px 32px 40px;
        gap: 28px;
        box-shadow: -20px 0 60px -20px rgba(0, 0, 0, 0.2);
        transition: right 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        z-index: 999;
      }

      .nav-links.open {
        right: 0;
      }

      .nav-links a {
        font-size: 1.05rem;
        width: 100%;
      }

      .nav-links .btn-header {
        width: 100%;
        justify-content: center;
        margin-top: 8px;
      }

      .menu-toggle {
        display: block;
        z-index: 1000;
      }

      .hero {
        padding: 130px 0 80px;
      }

      .hero-grid {
        grid-template-columns: 1fr;
        gap: 48px;
        text-align: center;
      }

      .hero p {
        margin-left: auto;
        margin-right: auto;
      }

      .hero-actions {
        justify-content: center;
      }

      .hero-stats {
        justify-content: center;
      }

      .hero-visual {
        max-width: 420px;
        margin: 0 auto;
        width: 100%;
      }

      .floating-card.card-1 {
        left: -8px;
        bottom: 20px;
      }

      .floating-card.card-2 {
        right: -8px;
        top: 20px;
      }

      .features-grid {
        grid-template-columns: 1fr;
        gap: 20px;
      }

      .cta-box {
        flex-direction: column;
        text-align: center;
        padding: 56px 32px;
      }

      .cta-text p {
        margin: 0 auto;
      }
    }

    @media (max-width: 640px) {
      .container {
        padding: 0 20px;
      }

      section {
        padding: 72px 0;
      }

      .hero {
        padding: 120px 0 64px;
      }

      .hero-stats {
        gap: 28px;
        flex-wrap: wrap;
      }

      .stat h3 {
        font-size: 1.5rem;
      }

      .services-grid {
        grid-template-columns: 1fr;
      }

      .testimonial-card {
        padding: 48px 28px;
      }

      .testimonial-card .quote-mark {
        font-size: 3.5rem;
        top: 16px;
        left: 24px;
      }

      .cta-box {
        padding: 48px 24px;
      }

      .btn-whatsapp {
        padding: 16px 32px;
        font-size: 0.95rem;
      }

      .footer-grid {
        grid-template-columns: 1fr;
        gap: 36px;
        text-align: center;
      }

      .footer-about p {
        margin-left: auto;
        margin-right: auto;
      }

      .social-icons {
        justify-content: center;
      }

      .footer-contact p {
        justify-content: center;
      }

      .footer-col ul a:hover {
        transform: none;
      }

      .footer-bottom {
        flex-direction: column;
        text-align: center;
      }

      .whatsapp-float {
        width: 54px;
        height: 54px;
        font-size: 1.6rem;
        bottom: 20px;
        right: 20px;
      }

      .whatsapp-float .tooltip {
        display: none;
      }
    }

    @media (max-width: 400px) {
      .hero h1 {
        font-size: 1.9rem;
      }

      .btn-primary {
        padding: 15px 28px;
        font-size: 0.92rem;
      }

      .floating-card {
        padding: 12px 14px;
      }

      .floating-card strong {
        font-size: 0.82rem;
      }
    }
  </style>
</head>
<body>
  <header id="header">
    <div class="container header-flex">
      <a href="#" class="logo">Éclat<span>Salon</span><span class="logo-dot"></span></a>
      <nav class="nav-links" id="navLinks">
        <a href="#inicio">Início</a>
        <a href="#servicos">Serviços</a>
        <a href="#sobre">Sobre</a>
        <a href="#contato">Contato</a>
        <a href="https://wa.me/5534992615849?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio%20no%20%C3%89clat%20Salon." target="_blank" rel="noopener" class="btn-header">
          <i class="fab fa-whatsapp"></i> Agendar
        </a>
      </nav>
      <button class="menu-toggle" id="menuToggle" aria-label="Abrir menu">
        <i class="fas fa-bars"></i>
      </button>
    </div>
  </header>

  <main>
    <!-- HERO -->
    <section class="hero" id="inicio">
      <div class="container hero-grid">
        <div class="hero-content">
          <div class="hero-badge">
            <span class="dot"></span>
            Agenda aberta para novos clientes
          </div>
          <h1>Realce sua <i>beleza</i> natural com um toque de sofisticação</h1>
          <p>No Éclat Salon, cada detalhe é pensado para proporcionar uma experiência única. Cabelos, unhas, maquiagem e bem-estar em um só lugar.</p>
          <div class="hero-actions">
            <a href="https://wa.me/5534992615849?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio%20no%20%C3%89clat%20Salon." target="_blank" rel="noopener" class="btn-primary">
              <i class="fab fa-whatsapp"></i>
              Agende pelo WhatsApp
              <i class="fas fa-arrow-right"></i>
            </a>
          </div>
          <div class="hero-stats">
            <div class="stat">
              <h3>+12</h3>
              <p>Anos de experiência</p>
            </div>
            <div class="stat">
              <h3>+5k</h3>
              <p>Clientes satisfeitos</p>
            </div>
            <div class="stat">
              <h3>4.9</h3>
              <p>Avaliação média</p>
            </div>
          </div>
        </div>
        <div class="hero-visual">
          <div class="hero-image-wrapper">
            <img src="https://images.unsplash.com/photo-1560066984-138dadb4c035?q=80&w=987&auto=format&fit=crop" alt="Interior do salão Éclat" loading="eager">
          </div>
          <div class="floating-card card-1">
            <div class="floating-icon"><i class="fas fa-star"></i></div>
            <div>
              <strong>4.9 de 5 estrelas</strong>
              <small>+800 avaliações</small>
            </div>
          </div>
          <div class="floating-card card-2">
            <div class="floating-icon"><i class="fab fa-whatsapp"></i></div>
            <div>
              <strong>Agendamento fácil</strong>
              <small>Direto no WhatsApp</small>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- MARQUEE -->
    <div class="marquee-section" aria-hidden="true">
      <div class="marquee">
        <span class="marquee-item">Cabelo <i class="fas fa-circle"></i></span>
        <span class="marquee-item">Unhas <i class="fas fa-circle"></i></span>
        <span class="marquee-item">Maquiagem <i class="fas fa-circle"></i></span>
        <span class="marquee-item">Estética <i class="fas fa-circle"></i></span>
        <span class="marquee-item">Bem-estar <i class="fas fa-circle"></i></span>
        <span class="marquee-item">Cabelo <i class="fas fa-circle"></i></span>
        <span class="marquee-item">Unhas <i class="fas fa-circle"></i></span>
        <span class="marquee-item">Maquiagem <i class="fas fa-circle"></i></span>
        <span class="marquee-item">Estética <i class="fas fa-circle"></i></span>
        <span class="marquee-item">Bem-estar <i class="fas fa-circle"></i></span>
      </div>
    </div>

    <!-- FEATURES -->
    <section class="features" id="sobre">
      <div class="container">
        <div class="section-head">
          <div class="section-label">Por que escolher o Éclat</div>
          <h2 class="section-title">Excelência em cada <i>detalhe</i></h2>
          <p>Uma experiência completa de beleza e bem-estar com atendimento personalizado e resultados impecáveis.</p>
        </div>
        <div class="features-grid">
          <div class="feature-card">
            <div class="feature-icon"><i class="fas fa-gem"></i></div>
            <h3>Profissionais renomados</h3>
            <p>Equipe com formação internacional e atualização constante nas tendências de beleza.</p>
          </div>
          <div class="feature-card">
            <div class="feature-icon"><i class="fas fa-leaf"></i></div>
            <h3>Produtos premium</h3>
            <p>Trabalhamos com marcas sustentáveis e de alta performance para cuidar de você.</p>
          </div>
          <div class="feature-card">
            <div class="feature-icon"><i class="fas fa-spa"></i></div>
            <h3>Ambiente exclusivo</h3>
            <p>Espaço acolhedor e reservado, pensado para o seu relaxamento total.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- SERVICES -->
    <section class="services" id="servicos">
      <div class="container">
        <div class="section-head">
          <div class="section-label">Nossos serviços</div>
          <h2 class="section-title">Cuidados <i>completos</i> para você</h2>
          <p>Clique em um serviço e agende diretamente pelo WhatsApp.</p>
        </div>
        <div class="services-grid">
          <a href="https://wa.me/5534992615849?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio%20para%20CABELO%20no%20%C3%89clat%20Salon." target="_blank" rel="noopener" class="service-item">
            <div class="service-icon"><i class="fas fa-cut"></i></div>
            <h4>Cabelo</h4>
            <p>Cortes, coloração, tratamentos e penteados</p>
          </a>
          <a href="https://wa.me/5534992615849?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio%20para%20UNHAS%20no%20%C3%89clat%20Salon." target="_blank" rel="noopener" class="service-item">
            <div class="service-icon"><i class="fas fa-hand-sparkles"></i></div>
            <h4>Unhas</h4>
            <p>Manicure, pedicure, nail art e alongamentos</p>
          </a>
          <a href="https://wa.me/5534992615849?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio%20para%20MAQUIAGEM%20no%20%C3%89clat%20Salon." target="_blank" rel="noopener" class="service-item">
            <div class="service-icon"><i class="fas fa-eye"></i></div>
            <h4>Maquiagem</h4>
            <p>Social, noiva, editorial e automaquiagem</p>
          </a>
          <a href="https://wa.me/5534992615849?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio%20para%20EST%C3%89TICA%20no%20%C3%89clat%20Salon." target="_blank" rel="noopener" class="service-item">
            <div class="service-icon"><i class="fas fa-spa"></i></div>
            <h4>Estética</h4>
            <p>Limpeza de pele, massagens e bem-estar</p>
          </a>
        </div>
      </div>
    </section>

    <!-- TESTIMONIAL -->
    <section class="testimonial-section">
      <div class="container">
        <div class="testimonial-card">
          <span class="quote-mark">“</span>
          <p class="testimonial-text">Minha experiência no Éclat foi transformadora. O cuidado com cada detalhe, desde a recepção até o resultado final, superou todas as expectativas. Me sinto renovada a cada visita.</p>
          <div class="testimonial-author">
            <div class="author-avatar">MA</div>
            <div class="author-info">
              <div class="stars">
                <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
              </div>
              <strong>Mariana Albuquerque</strong>
              <span>Cliente há 3 anos</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA FINAL -->
    <section class="cta-final" id="agendar">
      <div class="container">
        <div class="cta-box">
          <div class="cta-text">
            <h2>Pronta para <i>brilhar</i>?</h2>
            <p>Agende seu horário pelo WhatsApp e descubra o poder de um atendimento personalizado e exclusivo.</p>
          </div>
          <a href="https://wa.me/5534992615849?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio%20no%20%C3%89clat%20Salon." target="_blank" rel="noopener" class="btn-whatsapp">
            <i class="fab fa-whatsapp"></i>
            Agendar pelo WhatsApp
          </a>
        </div>
      </div>
    </section>
  </main>

  <!-- FOOTER -->
  <footer id="contato">
    <div class="container">
      <div class="footer-grid">
        <div class="footer-about">
          <div class="footer-logo">Éclat<span>Salon</span></div>
          <p>Beleza, bem-estar e sofisticação em um só lugar. Sua melhor versão começa aqui.</p>
          <div class="social-icons">
            <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
            <a href="#" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>
            <a href="https://wa.me/5534992615849" target="_blank" rel="noopener" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
            <a href="#" aria-label="TikTok"><i class="fab fa-tiktok"></i></a>
          </div>
        </div>
        <div class="footer-col">
          <h4>Navegação</h4>
          <ul>
            <li><a href="#inicio">Início</a></li>
            <li><a href="#servicos">Serviços</a></li>
            <li><a href="#sobre">Sobre nós</a></li>
            <li><a href="#contato">Contato</a></li>
          </ul>
        </div>
        <div class="footer-col">
          <h4>Serviços</h4>
          <ul>
            <li><a href="https://wa.me/5534992615849?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio%20para%20CABELO%20no%20%C3%89clat%20Salon." target="_blank" rel="noopener">Cabelo</a></li>
            <li><a href="https://wa.me/5534992615849?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio%20para%20UNHAS%20no%20%C3%89clat%20Salon." target="_blank" rel="noopener">Unhas</a></li>
            <li><a href="https://wa.me/5534992615849?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio%20para%20MAQUIAGEM%20no%20%C3%89clat%20Salon." target="_blank" rel="noopener">Maquiagem</a></li>
            <li><a href="https://wa.me/5534992615849?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio%20para%20EST%C3%89TICA%20no%20%C3%89clat%20Salon." target="_blank" rel="noopener">Estética</a></li>
          </ul>
        </div>
        <div class="footer-contact">
          <h4>Contato</h4>
          <p><i class="fas fa-map-marker-alt"></i> Rua das Flores, 123 – Jardins, SP</p>
          <p><i class="fab fa-whatsapp"></i> <a href="https://wa.me/5534992615849" target="_blank" rel="noopener">(34)99261-5849</a></p>
          <p><i class="fas fa-envelope"></i> contato@eclatsalon.com</p>
          <p><i class="fas fa-clock"></i> Ter–Sáb: 10h às 20h</p>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2025 Éclat Salon. Todos os direitos reservados.</p>
        <p>Design conceitual — <a href="#">Política de Privacidade</a></p>
      </div>
    </div>
  </footer>

  <!-- BOTÃO FLUTUANTE WHATSAPP -->
  <a href="https://wa.me/5534992615849?text=Ol%C3%A1!%20Gostaria%20de%20agendar%20um%20hor%C3%A1rio%20no%20%C3%89clat%20Salon." target="_blank" rel="noopener" class="whatsapp-float" aria-label="Fale conosco no WhatsApp">
    <i class="fab fa-whatsapp"></i>
    <span class="tooltip">Agende pelo WhatsApp</span>
  </a>

  <script>
    // Header scrolled state
    const header = document.getElementById('header');
    const menuToggle = document.getElementById('menuToggle');
    const navLinks = document.getElementById('navLinks');

    window.addEventListener('scroll', () => {
      if (window.scrollY > 40) {
        header.classList.add('scrolled');
      } else {
        header.classList.remove('scrolled');
      }
    });

    // Mobile menu toggle
    menuToggle.addEventListener('click', () => {
      navLinks.classList.toggle('open');
      const icon = menuToggle.querySelector('i');
      if (navLinks.classList.contains('open')) {
        icon.classList.remove('fa-bars');
        icon.classList.add('fa-times');
        document.body.style.overflow = 'hidden';
      } else {
        icon.classList.remove('fa-times');
        icon.classList.add('fa-bars');
        document.body.style.overflow = '';
      }
    });

    // Close menu on link click
    navLinks.querySelectorAll('a').forEach(link => {
      link.addEventListener('click', () => {
        navLinks.classList.remove('open');
        const icon = menuToggle.querySelector('i');
        icon.classList.remove('fa-times');
        icon.classList.add('fa-bars');
        document.body.style.overflow = '';
      });
    });

    // Close menu when clicking outside
    document.addEventListener('click', (e) => {
      if (navLinks.classList.contains('open') && 
          !navLinks.contains(e.target) && 
          !menuToggle.contains(e.target)) {
        navLinks.classList.remove('open');
        const icon = menuToggle.querySelector('i');
        icon.classList.remove('fa-times');
        icon.classList.add('fa-bars');
        document.body.style.overflow = '';
      }
    });

    // Smooth scroll for anchor links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        const href = this.getAttribute('href');
        if (href === '#') return;
        const target = document.querySelector(href);
        if (target) {
          e.preventDefault();
          const offsetTop = target.getBoundingClientRect().top + window.pageYOffset - 80;
          window.scrollTo({
            top: offsetTop,
            behavior: 'smooth'
          });
        }
      });
    });
  </script>
</body>
</html>
