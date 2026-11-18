# NFC
Um teste para comercialização de NFCs
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SDtapNFC's | Conexão Instantânea</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Space+Grotesk:wght@600;700&display=swap" rel="stylesheet">

  <style>
    :root {
      --bg-deep: #020817;
      --bg-surface: rgba(15, 23, 42, 0.6);
      --accent-blue: #3b82f6;
      --accent-cyan: #00f0ff;
      --text-main: #f8fafc;
      --text-muted: #94a3b8;
      --border-glow: rgba(0, 240, 255, 0.25);
      --border-subtle: rgba(255, 255, 255, 0.08);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background-color: var(--bg-deep);
      background-image: 
        radial-gradient(circle at 15% 15%, rgba(59, 130, 246, 0.15) 0%, transparent 40%),
        radial-gradient(circle at 85% 60%, rgba(0, 240, 255, 0.1) 0%, transparent 45%),
        linear-gradient(rgba(255, 255, 255, 0.02) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255, 255, 255, 0.02) 1px, transparent 1px);
      background-size: 100% 100%, 100% 100%, 40px 40px, 40px 40px;
      color: var(--text-main);
      font-family: 'Inter', sans-serif;
      line-height: 1.5;
      overflow-x: hidden;
    }

    h1, h2, h3, .logo {
      font-family: 'Space Grotesk', sans-serif;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    /* Header */
    header {
      position: fixed;
      top: 0;
      width: 100%;
      z-index: 100;
      background: rgba(2, 8, 23, 0.75);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border-subtle);
    }

    nav {
      max-width: 1040px;
      margin: auto;
      padding: 16px 24px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .logo {
      font-size: 1.35rem;
      font-weight: 700;
      letter-spacing: -0.5px;
    }

    .logo span {
      color: var(--accent-cyan);
      text-shadow: 0 0 15px rgba(0, 240, 255, 0.5);
    }

    .nav-cta {
      font-size: 0.85rem;
      font-weight: 600;
      padding: 8px 16px;
      border-radius: 99px;
      background: rgba(0, 240, 255, 0.1);
      border: 1px solid var(--border-glow);
      color: var(--accent-cyan);
      transition: all 0.25s ease;
    }

    .nav-cta:hover {
      background: var(--accent-cyan);
      color: var(--bg-deep);
      box-shadow: 0 0 20px rgba(0, 240, 255, 0.4);
    }

    /* Hero Section */
    .hero {
      max-width: 1040px;
      margin: auto;
      padding: 140px 24px 80px;
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      align-items: center;
      gap: 48px;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 6px 14px;
      border-radius: 99px;
      background: rgba(59, 130, 246, 0.1);
      border: 1px solid rgba(59, 130, 246, 0.3);
      color: #60a5fa;
      font-size: 0.8rem;
      font-weight: 500;
      letter-spacing: 0.5px;
      text-transform: uppercase;
      margin-bottom: 20px;
    }

    .badge::before {
      content: "";
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: var(--accent-cyan);
      box-shadow: 0 0 8px var(--accent-cyan);
    }

    h1 {
      font-size: clamp(2.5rem, 5vw, 4rem);
      line-height: 1.08;
      letter-spacing: -1.5px;
      margin-bottom: 20px;
    }

    h1 span {
      background: linear-gradient(90deg, var(--accent-cyan), #60a5fa);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero p {
      color: var(--text-muted);
      font-size: 1.05rem;
      max-width: 480px;
      margin-bottom: 32px;
    }

    .actions {
      display: flex;
      gap: 14px;
      flex-wrap: wrap;
    }

    .btn-glow {
      padding: 14px 26px;
      border-radius: 12px;
      font-weight: 600;
      font-size: 0.95rem;
      background: linear-gradient(135deg, var(--accent-blue), #0284c7);
      color: white;
      border: 1px solid rgba(255, 255, 255, 0.2);
      box-shadow: 0 8px 25px -5px rgba(59, 130, 246, 0.5);
      transition: all 0.25s ease;
    }

    .btn-glow:hover {
      transform: translateY(-2px);
      box-shadow: 0 12px 30px -5px rgba(0, 240, 255, 0.5);
    }

    .btn-glass {
      padding: 14px 24px;
      border-radius: 12px;
      font-weight: 500;
      font-size: 0.95rem;
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid var(--border-subtle);
      color: var(--text-main);
      transition: all 0.25s ease;
    }

    .btn-glass:hover {
      background: rgba(255, 255, 255, 0.08);
      border-color: var(--border-glow);
    }

    /* Cartão 3D / Tecnológico */
    .card-showcase {
      position: relative;
      display: flex;
      justify-content: center;
    }

    .smart-card {
      width: 100%;
      max-width: 340px;
      aspect-ratio: 1.58 / 1;
      border-radius: 20px;
      background: linear-gradient(135deg, rgba(15, 23, 42, 0.9), rgba(2, 8, 23, 0.95));
      border: 1px solid var(--border-glow);
      padding: 24px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      position: relative;
      overflow: hidden;
      box-shadow: 
        0 25px 50px -12px rgba(0, 0, 0, 0.8),
        inset 0 1px 1px rgba(255, 255, 255, 0.15);
      animation: float 5s ease-in-out infinite;
    }

    .smart-card::after {
      content: "";
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: radial-gradient(circle, rgba(0, 240, 255, 0.12) 0%, transparent 60%);
      pointer-events: none;
    }

    .card-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .chip {
      width: 40px;
      height: 28px;
      border-radius: 6px;
      background: linear-gradient(135deg, #334155, #1e293b);
      border: 1px solid rgba(255, 255, 255, 0.2);
      position: relative;
    }

    .nfc-waves {
      color: var(--accent-cyan);
      font-size: 1.4rem;
      animation: pulse 2s infinite;
    }

    .card-bottom {
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
    }

    .card-brand {
      font-family: 'Space Grotesk', sans-serif;
      font-weight: 700;
      font-size: 1.1rem;
      letter-spacing: 0.5px;
    }

    .card-brand span {
      color: var(--accent-cyan);
    }

    .card-status {
      font-size: 0.7rem;
      color: var(--accent-cyan);
      letter-spacing: 1px;
      text-transform: uppercase;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0px) rotate(-1deg); }
      50% { transform: translateY(-10px) rotate(1deg); }
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.5; transform: scale(1.1); }
    }

    /* Bento Grid (Soluções + Processo resumidos) */
    .bento-section {
      max-width: 1040px;
      margin: auto;
      padding: 40px 24px 80px;
    }

    .bento-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 16px;
    }

    .bento-item {
      background: var(--bg-surface);
      backdrop-filter: blur(12px);
      border: 1px solid var(--border-subtle);
      border-radius: 20px;
      padding: 28px;
      transition: all 0.3s ease;
    }

    .bento-item:hover {
      border-color: var(--border-glow);
      transform: translateY(-4px);
      background: rgba(15, 23, 42, 0.85);
    }

    .bento-icon {
      width: 42px;
      height: 42px;
      border-radius: 10px;
      background: rgba(0, 240, 255, 0.1);
      border: 1px solid rgba(0, 240, 255, 0.2);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--accent-cyan);
      font-size: 1.2rem;
      margin-bottom: 18px;
    }

    .bento-item h3 {
      font-size: 1.15rem;
      margin-bottom: 8px;
    }

    .bento-item p {
      color: var(--text-muted);
      font-size: 0.9rem;
    }

    /* Barra de Processo Ultra Resumida */
    .process-bar {
      grid-column: span 3;
      background: linear-gradient(90deg, rgba(15, 23, 42, 0.8), rgba(30, 58, 138, 0.25));
      border: 1px solid var(--border-subtle);
      border-radius: 20px;
      padding: 24px 32px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
      flex-wrap: wrap;
    }

    .step-pill {
      display: flex;
      align-items: center;
      gap: 12px;
      font-size: 0.9rem;
      font-weight: 500;
    }

    .step-num {
      width: 28px;
      height: 28px;
      border-radius: 50%;
      background: var(--accent-blue);
      color: white;
      font-family: 'Space Grotesk', sans-serif;
      font-weight: 700;
      font-size: 0.8rem;
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 0 12px rgba(59, 130, 246, 0.6);
    }

    /* CTA Compacto */
    .cta-box {
      max-width: 1040px;
      margin: 0 auto 80px;
      padding: 0 24px;
    }

    .cta-inner {
      background: linear-gradient(135deg, rgba(30, 58, 138, 0.35), rgba(2, 8, 23, 0.9));
      border: 1px solid var(--border-glow);
      border-radius: 24px;
      padding: 48px 32px;
      text-align: center;
      position: relative;
      overflow: hidden;
    }

    .cta-inner h2 {
      font-size: clamp(1.6rem, 3vw, 2.2rem);
      margin-bottom: 12px;
    }

    .cta-inner p {
      color: var(--text-muted);
      margin-bottom: 28px;
      font-size: 0.95rem;
    }

    footer {
      text-align: center;
      padding: 24px;
      border-top: 1px solid var(--border-subtle);
      color: var(--text-muted);
      font-size: 0.85rem;
    }

    @media (max-width: 850px) {
      .hero {
        grid-template-columns: 1fr;
        text-align: center;
        padding-top: 110px;
      }

      .hero p {
        margin: 0 auto 32px;
      }

      .actions {
        justify-content: center;
      }

      .bento-grid {
        grid-template-columns: 1fr;
      }

      .process-bar {
        grid-column: span 1;
        flex-direction: column;
        align-items: flex-start;
      }
    }
  </style>
</head>
<body>

  <header>
    <nav>
      <div class="logo">SD<span>tap</span>NFC's</div>
      <a href="https://wa.me/5598991824315" target="_blank" class="nav-cta">Pedir agora</a>
    </nav>
  </header>

  <main>
    <section class="hero">
      <div>
        <div class="badge">Tecnologia NFC </div>
        <h1>Um toque. <span>Conexão infinita.</span></h1>
        <p>Cartões, chaveiros e tags inteligentes personalizados. Compartilhe redes, contatos e avaliações sem aplicativos.</p>
        
        <div class="actions">
          <a href="https://wa.me/5598991824315" target="_blank" class="btn-glow">Criar meu NFC</a>
          <a href="https://www.instagram.com/samoel.derek?dmpr=MXZvcDM4dDh0cGQwNg%3D%3D&utm_source=qr" target="_blank" class="btn-glass">Instagram</a>
        </div>
      </div>

      <div class="card-showcase">
        <div class="smart-card">
          <div class="card-top">
            <div class="chip"></div>
            <div class="nfc-waves">)))</div>
          </div>
          <div class="card-bottom">
            <div class="card-brand">SD<span>tap</span>NFC's</div>
            <div class="card-status">• Ativo</div>
          </div>
        </div>
      </div>
    </section>

    <section class="bento-section">
      <div class="bento-grid">
        <div class="bento-item">
          <div class="bento-icon">◈</div>
          <h3>Smart Cards</h3>
          <p>Substitua cartões de papel. Transfira seu portfólio, WhatsApp e redes sociais em 1 segundo.</p>
        </div>

        <div class="bento-item">
          <div class="bento-icon">⬡</div>
          <h3>Tags & Chaveiros</h3>
          <p>Acessórios resistentes e personalizados para levar sua identidade digital sempre com você.</p>
        </div>

        <div class="bento-item">
          <div class="bento-icon">★</div>
          <h3>Boost Comercial</h3>
          <p>Aproxime o celular do cliente direto para o seu cardápio digital, catálogo ou avaliação no Google.</p>
        </div>

    
        </div>
      </div>
    </section>

    <section class="cta-box">
      <div class="cta-inner">
        <h2>Pronto para evoluir sua conexão?</h2>
        <p>Personalização sob medida para você ou sua empresa.</p>
        <a href="https://wa.me/5598991824315" target="_blank" class="btn-glow">Falar no WhatsApp</a>
      </div>
    </section>
  </main>

  <footer>
    © 2026 SDtapNFC's — Conexões Inteligentes.
  </footer>

</body>
</html>
