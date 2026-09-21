<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Éclat Salon | Beleza & Estilo</title>
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;1,400&display=swap" rel="stylesheet">
  <!-- Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background-color: #faf7f2;
      color: #2e2e2e;
      line-height: 1.5;
      scroll-behavior: smooth;
    }

    h1, h2, h3, .logo {
      font-family: 'Playfair Display', serif;
      font-weight: 600;
      letter-spacing: -0.02em;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 24px;
    }

    /* Header */
    header {
      background-color: #faf7f2;
      padding: 20px 0;
      position: sticky;
      top: 0;
      z-index: 100;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.02);
      backdrop-filter: blur(6px);
      background-color: rgba(250, 247, 242, 0.92);
    }

    .header-flex {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .logo {
      font-size: 1.9rem;
      font-weight: 700;
      color: #1e1e1e;
      letter-spacing: -0.03em;
    }

    .logo span {
      color: #c49a6c;
      font-style: italic;
      font-weight: 500;
    }

    .nav-links {
      display: flex;
      gap: 36px;
      align-items: center;
    }

    .nav-links a {
      text-decoration: none;
      color: #3a3a3a;
      font-weight: 500;
      font-size: 1rem;
      transition: color 0.2s ease;
    }

    .nav-links a:hover {
      color: #c49a6c;
    }

    .btn-outline {
      border: 1.5px solid #c49a6c;
      background: transparent;
      padding: 10px 24px;
      border-radius: 40px;
      font-weight: 600;
      color: #c49a6c;
      transition: all 0.2s ease;
      font-size: 0.95rem;
    }

    .btn-outline:hover {
      background: #c49a6c;
      color: white;
      border-color: #c49a6c;
    }

    /* Hero */
    .hero {
      padding: 70px 0 80px;
      background: linear-gradient(135deg, #faf7f2 0%, #f3ede6 100%);
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 50px;
      align-items: center;
    }

    .hero-subtitle {
      font-size: 0.9rem;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: #c49a6c;
      font-weight: 600;
      margin-bottom: 16px;
      display: inline-block;
      border-bottom: 2px solid #c49a6c;
      padding-bottom: 4px;
    }

    .hero h1 {
      font-size: 3.5rem;
      line-height: 1.15;
      color: #1e1e1e;
      margin-bottom: 24px;
      font-weight: 600;
    }

    .hero h1 i {
      font-style: italic;
      color: #c49a6c;
      font-weight: 400;
    }

    .hero p {
      font-size: 1.15rem;
      color: #5a5a5a;
      margin-bottom: 36px;
      max-width: 90%;
      font-weight: 300;
    }

    .btn-primary {
      background-color: #1e1e1e;
      color: white;
      padding: 16px 42px;
      border-radius: 40px;
      font-weight: 600;
      font-size: 1rem;
      border: none;
      cursor: pointer;
      transition: all 0.25s ease;
      box-shadow: 0 10px 25px -8px rgba(0, 0, 0, 0.15);
      display: inline-block;
      text-decoration: none;
      letter-spacing: 0.3px;
    }

    .btn-primary:hover {
      background-color: #c49a6c;
      transform: translateY(-2px);
      box-shadow: 0 18px 30px -8px rgba(196, 154, 108, 0.35);
    }

    .hero-image {
      background: #d9cfc4;
      border-radius: 32px;
      overflow: hidden;
      aspect-ratio: 4/5;
      box-shadow: 0 30px 45px -20px rgba(0, 0, 0, 0.3);
      background-image: url('https://images.unsplash.com/photo-1560066984-138dadb4c035?q=80&w=987&auto=format&fit=crop');
      background-size: cover;
      background-position: center;
    }

    /* Diferenciais */
    .features {
      padding: 80px 0;
    }

    .section-label {
      text-align: center;
      font-size: 0.85rem;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: #c49a6c;
      font-weight: 600;
      margin-bottom: 16px;
    }

    .section-title {
      text-align: center;
      font-size: 2.6rem;
      font-weight: 600;
      color: #1e1e1e;
      margin-bottom: 20px;
      line-height: 1.2;
    }

    .section-title i {
      font-style: italic;
      color: #c49a6c;
      font-weight: 400;
    }

    .features-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 40px;
      margin-top: 60px;
    }

    .feature-card {
      background: white;
      padding: 40px 30px;
      border-radius: 24px;
      box-shadow: 0 10px 30px -12px rgba(0, 0, 0, 0.05);
      transition: transform 0.2s ease, box-shadow 0.2s ease;
      text-align: center;
      border: 1px solid #f0e9e1;
    }

    .feature-card:hover {
      transform: translateY(-8px);
      box-shadow: 0 30px 45px -18px rgba(196, 154, 108, 0.25);
    }

    .feature-icon {
      font-size: 2.4rem;
      color: #c49a6c;
      margin-bottom: 24px;
    }

    .feature-card h3 {
      font-size: 1.5rem;
      margin-bottom: 16px;
      font-weight: 600;
    }

    .feature-card p {
      color: #6b6b6b;
      font-weight: 300;
      font-size: 1rem;
    }

    /* Serviços */
    .services {
      padding: 80px 0;
      background-color: #f3ede6;
    }

    .services-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 30px;
      margin-top: 50px;
    }

    .service-item {
      background: white;
      border-radius: 20px;
      padding: 32px 20px;
      text-align: center;
      box-shadow: 0 10px 25px -12px rgba(0, 0, 0, 0.08);
      transition: all 0.25s ease;
      border: 1px solid #ffffff50;
    }

    .service-item:hover {
      background: #1e1e1e;
      color: white;
    }

    .service-item:hover .service-icon,
    .service-item:hover p {
      color: #f0e9e1;
    }

    .service-item:hover h4 {
      color: white;
    }

    .service-icon {
      font-size: 2rem;
      color: #c49a6c;
      margin-bottom: 20px;
      transition: color 0.2s ease;
    }

    .service-item h4 {
      font-size: 1.25rem;
      margin-bottom: 8px;
      font-weight: 600;
      transition: color 0.2s ease;
    }

    .service-item p {
      color: #7a7a7a;
      font-size: 0.9rem;
      font-weight: 300;
      transition: color 0.2s ease;
    }

    /* Depoimento */
    .testimonial {
      padding: 80px 0;
      background: #faf7f2;
    }

    .testimonial-card {
      max-width: 800px;
      margin: 0 auto;
      background: white;
      border-radius: 40px;
      padding: 60px 50px;
      box-shadow: 0 25px 50px -20px rgba(0, 0, 0, 0.1);
      text-align: center;
      border: 1px solid #f0e9e1;
    }

    .testimonial-card i.fa-quote-left {
      font-size: 2.5rem;
      color: #c49a6c;
      opacity: 0.5;
      margin-bottom: 24px;
    }

    .testimonial-card p {
      font-size: 1.35rem;
      line-height: 1.6;
      font-weight: 300;
      font-style: italic;
      color: #3a3a3a;
      margin-bottom: 32px;
    }

    .testimonial-author {
      font-weight: 600;
      color: #1e1e1e;
      letter-spacing: 0.5px;
      font-size: 1.1rem;
    }

    .testimonial-author span {
      font-weight: 300;
      color: #c49a6c;
      font-style: italic;
    }

    /* CTA final */
    .cta-final {
      padding: 80px 0;
      background: linear-gradient(135deg, #1e1e1e 0%, #2b2b2b 100%);
      color: white;
    }

    .cta-flex {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 40px;
    }

    .cta-text h2 {
      font-size: 2.5rem;
      font-weight: 600;
      margin-bottom: 12px;
    }

    .cta-text h2 i {
      font-style: italic;
      color: #c49a6c;
      font-weight: 400;
    }

    .cta-text p {
      color: #b0b0b0;
      font-size: 1.1rem;
      font-weight: 300;
      max-width: 500px;
    }

    .btn-gold {
      background-color: #c49a6c;
      color: #1e1e1e;
      padding: 18px 48px;
      border-radius: 50px;
      font-weight: 700;
      font-size: 1.05rem;
      text-decoration: none;
      transition: all 0.25s ease;
      display: inline-block;
      box-shadow: 0 12px 25px -8px rgba(196, 154, 108, 0.4);
      letter-spacing: 0.5px;
    }

    .btn-gold:hover {
      background-color: #dbb88c;
      transform: scale(1.02);
      box-shadow: 0 20px 35px -10px rgba(196, 154, 108, 0.6);
    }

    /* Footer */
    footer {
      padding: 50px 0 30px;
      background: #faf7f2;
      border-top: 1px solid #e7ddd2;
    }

    .footer-grid {
      display: grid;
      grid-template-columns: 2fr 1fr 1fr 1.5fr;
      gap: 40px;
      margin-bottom: 50px;
    }

    .footer-logo {
      font-size: 1.8rem;
      font-family: 'Playfair Display', serif;
      font-weight: 700;
      margin-bottom: 20px;
    }

    .footer-logo span {
      color: #c49a6c;
      font-style: italic;
    }

    .footer-about p {
      color: #6b6b6b;
      font-weight: 300;
      font-size: 0.95rem;
      max-width: 260px;
      margin-bottom: 24px;
    }

    .social-icons a {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 40px;
      height: 40px;
      background: white;
      border-radius: 50%;
      color: #1e1e1e;
      margin-right: 12px;
      text-decoration: none;
      transition: all 0.2s ease;
      border: 1px solid #e7ddd2;
    }

    .social-icons a:hover {
      background: #c49a6c;
      color: white;
      border-color: #c49a6c;
    }

    .footer-col h4 {
      font-size: 1.1rem;
      margin-bottom: 24px;
      font-weight: 600;
      color: #1e1e1e;
      letter-spacing: 0.5px;
    }

    .footer-col ul {
      list-style: none;
    }

    .footer-col ul li {
      margin-bottom: 14px;
    }

    .footer-col ul a {
      text-decoration: none;
      color: #6b6b6b;
      font-weight: 300;
      transition: color 0.2s;
      font-size: 0.95rem;
    }

    .footer-col ul a:hover {
      color: #c49a6c;
    }

    .footer-contact p {
      color: #6b6b6b;
      font-weight: 300;
      font-size: 0.95rem;
      margin-bottom: 14px;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .footer-contact i {
      color: #c49a6c;
      width: 18px;
    }

    .copyright {
      text-align: center;
      padding-top: 30px;
      border-top: 1px solid #e7ddd2;
      color: #8a8a8a;
      font-size: 0.9rem;
      font-weight: 300;
    }

    /* Responsivo */
    @media (max-width: 992px) {
      .hero-grid {
        grid-template-columns: 1fr;
        text-align: center;
      }
      .hero p {
        max-width: 100%;
        margin-left: auto;
        margin-right: auto;
      }
      .hero h1 {
        font-size: 2.8rem;
      }
      .features-grid {
        grid-template-columns: 1fr 1fr;
      }
      .services-grid {
        grid-template-columns: 1fr 1fr;
      }
      .footer-grid {
        grid-template-columns: 1fr 1fr;
      }
      .cta-flex {
        flex-direction: column;
        text-align: center;
      }
      .cta-text p {
        margin: 0 auto;
      }
    }

    @media (max-width: 768px) {
      .header-flex {
        flex-direction: column;
        gap: 20px;
      }
      .nav-links {
        flex-wrap: wrap;
        justify-content: center;
        gap: 20px;
      }
      .hero h1 {
        font-size: 2.3rem;
      }
      .section-title {
        font-size: 2rem;
      }
      .features-grid {
        grid-template-columns: 1fr;
      }
      .services-grid {
        grid-template-columns: 1fr;
      }
      .testimonial-card {
        padding: 40px 24px;
      }
      .testimonial-card p {
        font-size: 1.15rem;
      }
      .footer-grid {
        grid-template-columns: 1fr;
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
      .btn-primary, .btn-gold {
        padding: 14px 32px;
      }
    }

    @media (max-width: 480px) {
      .hero h1 {
        font-size: 1.9rem;
      }
      .section-title {
        font-size: 1.8rem;
      }
      .cta-text h2 {
        font-size: 2rem;
      }
      .btn-gold {
        padding: 14px 28px;
        font-size: 0.95rem;
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="container header-flex">
      <div class="logo">Éclat<span>Salon</span></div>
      <nav class="nav-links">
        <a href="#">Início</a>
        <a href="#">Serviços</a>
        <a href="#">Sobre</a>
        <a href="#">Contato</a>
        <a href="#" class="btn-outline">Agendar</a>
      </nav>
    </div>
  </header>

  <main>
    <!-- Hero -->
    <section class="hero">
      <div class="container hero-grid">
        <div class="hero-content">
          <span class="hero-subtitle">Beleza consciente</span>
          <h1>Realce sua <i>beleza</i> natural com um toque de sofisticação</h1>
          <p>No Éclat Salon, cada detalhe é pensado para proporcionar uma experiência única. Cabelos, unhas, maquiagem e bem-estar em um só lugar.</p>
          <a href="#" class="btn-primary">Agende seu horário <i class="fas fa-arrow-right" style="margin-left: 10px; font-size: 0.9rem;"></i></a>
        </div>
        <div class="hero-image"></div>
      </div>
    </section>

    <!-- Diferenciais -->
    <section class="features">
      <div class="container">
        <div class="section-label">Por que escolher o Éclat</div>
        <h2 class="section-title">Excelência em cada <i>detalhe</i></h2>
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
            <div class="feature-icon"><i class="fas fa-clock"></i></div>
            <h3>Ambiente exclusivo</h3>
            <p>Espaço acolhedor e reservado, pensado para o seu relaxamento total.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Serviços -->
    <section class="services">
      <div class="container">
        <div class="section-label">Nossos serviços</div>
        <h2 class="section-title">Cuidados <i>completos</i> para você</h2>
        <div class="services-grid">
          <div class="service-item">
            <div class="service-icon"><i class="fas fa-cut"></i></div>
            <h4>Cabelo</h4>
            <p>Cortes, coloração, tratamentos e penteados</p>
          </div>
          <div class="service-item">
            <div class="service-icon"><i class="fas fa-hand-sparkles"></i></div>
            <h4>Unhas</h4>
            <p>Manicure, pedicure, nail art e alongamentos</p>
          </div>
          <div class="service-item">
            <div class="service-icon"><i class="fas fa-eye"></i></div>
            <h4>Maquiagem</h4>
            <p>Social, noiva, editorial e automaquiagem</p>
          </div>
          <div class="service-item">
            <div class="service-icon"><i class="fas fa-spa"></i></div>
            <h4>Estética</h4>
            <p>Limpeza de pele, massagens e bem-estar</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Depoimento -->
    <section class="testimonial">
      <div class="container">
        <div class="testimonial-card">
          <i class="fas fa-quote-left"></i>
          <p>“Minha experiência no Éclat foi transformadora. O cuidado com cada detalhe, desde a recepção até o resultado final, superou todas as expectativas. Me sinto renovada a cada visita.”</p>
          <div class="testimonial-author">Mariana Albuquerque <span>— cliente há 3 anos</span></div>
        </div>
      </div>
    </section>

    <!-- CTA final -->
    <section class="cta-final">
      <div class="container cta-flex">
        <div class="cta-text">
          <h2>Pronta para <i>brilhar</i>?</h2>
          <p>Agende seu horário e descubra o poder de um atendimento personalizado e exclusivo.</p>
        </div>
        <a href="#" class="btn-gold">Agendar agora <i class="fas fa-calendar-check" style="margin-left: 10px;"></i></a>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      <div class="footer-grid">
        <div class="footer-about">
          <div class="footer-logo">Éclat<span>Salon</span></div>
          <p>Beleza, bem-estar e sofisticação em um só lugar. Sua melhor versão começa aqui.</p>
          <div class="social-icons">
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-facebook-f"></i></a>
            <a href="#"><i class="fab fa-whatsapp"></i></a>
            <a href="#"><i class="fab fa-tiktok"></i></a>
          </div>
        </div>
        <div class="footer-col">
          <h4>Navegação</h4>
          <ul>
            <li><a href="#">Início</a></li>
            <li><a href="#">Serviços</a></li>
            <li><a href="#">Sobre nós</a></li>
            <li><a href="#">Contato</a></li>
          </ul>
        </div>
        <div class="footer-col">
          <h4>Serviços</h4>
          <ul>
            <li><a href="#">Cabelo</a></li>
            <li><a href="#">Unhas</a></li>
            <li><a href="#">Maquiagem</a></li>
            <li><a href="#">Estética</a></li>
          </ul>
        </div>
        <div class="footer-contact">
          <h4>Contato</h4>
          <p><i class="fas fa-map-marker-alt"></i> Rua das Flores, 123 – Jardins, SP</p>
          <p><i class="fas fa-phone-alt"></i> (11) 98765-4321</p>
          <p><i class="fas fa-envelope"></i> contato@eclatsalon.com</p>
          <p><i class="fas fa-clock"></i> Ter–Sáb: 10h às 20h</p>
        </div>
      </div>
      <div class="copyright">
        &copy; 2025 Éclat Salon. Todos os direitos reservados. Design conceitual.
      </div>
    </div>
  </footer>
</body>
</html>
