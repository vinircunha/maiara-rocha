<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Maiara Rocha | Contabilidade para Pequenas Empresas</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,500;0,600;0,700;1,500&family=Work+Sans:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#0C1A13;
    --ledger-dark:#12261D;
    --ledger-mid:#1F4736;
    --ledger-line:#5E8770;
    --gold:#C9A227;
    --gold-bright:#E4C24E;
    --parchment:#F3EEDF;
    --parchment-dim:#E7E0C9;
    --seal:#8C2F26;
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--ledger-dark);
    color:var(--parchment);
    font-family:'Work Sans', sans-serif;
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3, .display{
    font-family:'Cormorant Garamond', serif;
    font-weight:600;
    letter-spacing:0.01em;
  }
  .mono{ font-family:'IBM Plex Mono', monospace; }
  a{color:inherit; text-decoration:none;}
  img{max-width:100%;display:block;}

  /* ambient ledger-line texture */
  .ruled{
    background-image: repeating-linear-gradient(
      to bottom,
      transparent 0px,
      transparent 37px,
      rgba(94,135,112,0.16) 38px
    );
  }

  .wrap{ max-width:1080px; margin:0 auto; padding:0 28px; }

  /* ---------- NAV ---------- */
  header{
    position:sticky; top:0; z-index:50;
    background:linear-gradient(180deg, var(--ledger-dark) 85%, rgba(18,38,29,0));
    border-bottom:1px solid rgba(201,162,39,0.25);
  }
  .nav-inner{
    display:flex; align-items:center; justify-content:space-between;
    padding:16px 28px;
    max-width:1080px; margin:0 auto;
  }
  .brand{
    display:flex; align-items:center; gap:10px;
  }
  .brand-mark{
    width:34px; height:34px; border-radius:50%;
    border:1.5px solid var(--gold);
    display:flex; align-items:center; justify-content:center;
    font-family:'Cormorant Garamond', serif;
    font-weight:700; font-size:16px; color:var(--gold-bright);
  }
  .brand-name{
    font-family:'Cormorant Garamond', serif;
    font-size:20px; font-weight:600; letter-spacing:0.02em;
    color:var(--parchment);
  }
  .tabs{
    display:flex; gap:2px;
  }
  .tabs a{
    font-size:13px; letter-spacing:0.06em; text-transform:uppercase;
    padding:10px 16px;
    color:var(--parchment-dim);
    border:1px solid transparent;
    border-bottom:none;
    border-radius:6px 6px 0 0;
    transition:all .2s ease;
  }
  .tabs a:hover{
    color:var(--gold-bright);
    border-color:rgba(201,162,39,0.35);
    background:rgba(201,162,39,0.06);
  }
  .nav-cta{
    display:none;
  }
  @media(min-width:720px){
    .nav-cta{
      display:inline-block;
      font-size:12.5px; letter-spacing:0.05em; text-transform:uppercase;
      background:var(--gold); color:var(--ink);
      padding:9px 16px; border-radius:3px; font-weight:600;
    }
  }
  @media(max-width:900px){ .tabs{display:none;} }

  /* ---------- HERO ---------- */
  .hero{
    position:relative;
    padding:88px 0 96px;
    overflow:hidden;
  }
  .hero-frame{
    border:1px solid rgba(201,162,39,0.4);
    padding:56px 40px;
    position:relative;
    background:
      linear-gradient(180deg, rgba(201,162,39,0.05), transparent 40%);
  }
  .hero-frame::before, .hero-frame::after{
    content:"";
    position:absolute; width:16px; height:16px;
    border:1px solid var(--gold);
  }
  .hero-frame::before{ top:-1px; left:-1px; border-right:none; border-bottom:none; }
  .hero-frame::after{ bottom:-1px; right:-1px; border-left:none; border-top:none; }
  .corner-tr{
    position:absolute; top:-1px; right:-1px; width:16px; height:16px;
    border:1px solid var(--gold); border-left:none; border-bottom:none;
  }
  .corner-bl{
    position:absolute; bottom:-1px; left:-1px; width:16px; height:16px;
    border:1px solid var(--gold); border-right:none; border-top:none;
  }
  .eyebrow{
    font-family:'IBM Plex Mono', monospace;
    font-size:12px; letter-spacing:0.22em; text-transform:uppercase;
    color:var(--gold-bright);
    margin-bottom:22px;
    display:flex; align-items:center; gap:12px;
  }
  .eyebrow::before{
    content:""; width:28px; height:1px; background:var(--gold);
  }
  .hero h1{
    font-size:clamp(38px, 6vw, 64px);
    line-height:1.06;
    color:var(--parchment);
    max-width:14ch;
  }
  .hero h1 em{
    font-style:italic; color:var(--gold-bright);
  }
  .hero-sub{
    margin-top:24px;
    font-size:18px;
    color:var(--parchment-dim);
    max-width:46ch;
  }
  .hero-actions{
    margin-top:38px;
    display:flex; align-items:center; gap:22px; flex-wrap:wrap;
  }

  /* wax seal button */
  .seal-btn{
    position:relative;
    display:inline-flex; align-items:center; gap:12px;
    background:var(--seal);
    color:var(--parchment);
    padding:16px 28px;
    border-radius:2px;
    font-weight:600; font-size:15px;
    box-shadow: 0 10px 24px -8px rgba(140,47,38,0.55);
    transition: transform .25s ease, box-shadow .25s ease;
    border:1px solid rgba(228,194,78,0.4);
  }
  .seal-btn:hover{
    transform:translateY(-2px);
    box-shadow: 0 14px 28px -8px rgba(140,47,38,0.65);
  }
  .seal-btn svg{ width:20px; height:20px; flex-shrink:0; }
  .seal-note{
    font-family:'IBM Plex Mono', monospace;
    font-size:12px; color:var(--parchment-dim); letter-spacing:0.04em;
  }

  /* ---------- SECTION SHELL ---------- */
  section{ position:relative; padding:72px 0; }
  .section-head{
    display:flex; align-items:baseline; gap:18px; margin-bottom:44px;
  }
  .section-num{
    font-family:'IBM Plex Mono', monospace;
    font-size:13px; color:var(--gold);
    border:1px solid rgba(201,162,39,0.4);
    padding:3px 8px; border-radius:2px;
  }
  .section-head h2{
    font-size:clamp(26px,3.4vw,36px);
    color:var(--parchment);
  }
  .section-tagline{
    color:var(--parchment-dim);
    max-width:56ch;
    margin:-24px 0 44px;
    font-size:15.5px;
  }

  /* ---------- SERVICES (ledger rows) ---------- */
  .ledger{
    border-top:1px solid rgba(201,162,39,0.3);
  }
  .ledger-row{
    display:grid;
    grid-template-columns: 64px 1fr;
    gap:22px;
    padding:26px 0;
    border-bottom:1px solid rgba(94,135,112,0.35);
    align-items:start;
  }
  .ledger-row .glyph{
    font-family:'Cormorant Garamond', serif;
    font-size:34px; color:var(--gold-bright); font-weight:600;
  }
  .ledger-row h3{
    font-size:21px; color:var(--parchment); margin-bottom:6px; font-weight:600;
  }
  .ledger-row p{ color:var(--parchment-dim); font-size:15px; max-width:60ch; }

  /* ---------- PRAZOS (dated entries) ---------- */
  .dates{
    display:grid; gap:0;
    border-top:1px solid rgba(201,162,39,0.3);
  }
  .date-row{
    display:grid;
    grid-template-columns: 130px 1fr;
    gap:20px;
    padding:20px 0;
    border-bottom:1px solid rgba(94,135,112,0.35);
  }
  .date-row .date{
    font-family:'IBM Plex Mono', monospace;
    color:var(--gold-bright);
    font-size:14px;
    padding-top:2px;
  }
  .date-row h4{
    font-size:17px; font-weight:600; color:var(--parchment); margin-bottom:4px;
  }
  .date-row p{ color:var(--parchment-dim); font-size:14.5px; }
  .dates-note{
    margin-top:20px; font-size:13px; color:var(--parchment-dim);
    font-style:italic; opacity:0.85;
  }

  /* ---------- MEI (card + definition) ---------- */
  .mei-grid{
    display:grid; gap:40px;
    grid-template-columns: 1fr;
  }
  @media(min-width:800px){ .mei-grid{ grid-template-columns: 1.1fr 1fr; } }
  .mei-card{
    background:var(--ledger-mid);
    border:1px solid rgba(201,162,39,0.3);
    border-radius:4px;
    padding:32px;
    position:relative;
  }
  .mei-card::before{
    content:"MEI";
    position:absolute; top:-14px; left:28px;
    background:var(--gold); color:var(--ink);
    font-family:'IBM Plex Mono', monospace;
    font-size:11px; letter-spacing:0.1em;
    padding:4px 10px; border-radius:2px; font-weight:600;
  }
  .mei-card p{ color:var(--parchment-dim); font-size:15px; margin-bottom:14px; }
  .mei-card p:last-child{ margin-bottom:0; }
  .mei-card strong{ color:var(--gold-bright); font-weight:600; }
  .mei-list{ list-style:none; }
  .mei-list li{
    padding:14px 0; border-bottom:1px solid rgba(94,135,112,0.3);
    display:flex; gap:12px; font-size:15px; color:var(--parchment-dim);
  }
  .mei-list li:last-child{ border-bottom:none; }
  .mei-list li::before{
    content:"—"; color:var(--gold); flex-shrink:0;
  }

  /* ---------- COBERTURA ---------- */
  .coverage{
    display:grid; gap:24px;
    grid-template-columns: 1fr;
  }
  @media(min-width:720px){ .coverage{ grid-template-columns: 1fr 1fr; } }
  .cov-card{
    border:1px solid rgba(201,162,39,0.3);
    padding:30px; border-radius:4px;
    background:rgba(201,162,39,0.04);
  }
  .cov-card h3{ font-size:20px; color:var(--parchment); margin-bottom:10px; }
  .cov-card p{ color:var(--parchment-dim); font-size:14.5px; }
  .cov-tag{
    display:inline-block; margin-top:16px;
    font-family:'IBM Plex Mono', monospace;
    font-size:11.5px; letter-spacing:0.06em; text-transform:uppercase;
    color:var(--gold-bright); border:1px solid var(--gold); padding:4px 10px; border-radius:2px;
  }

  /* ---------- FINAL CTA ---------- */
  .final-cta{
    text-align:center;
    padding:96px 0 110px;
  }
  .final-cta .frame{
    border:1px solid rgba(201,162,39,0.4);
    padding:56px 28px;
    position:relative;
  }
  .final-cta h2{
    font-size:clamp(28px,4vw,42px);
    color:var(--parchment);
    max-width:20ch; margin:0 auto 18px;
  }
  .final-cta p{ color:var(--parchment-dim); max-width:48ch; margin:0 auto 34px; }

  footer{
    border-top:1px solid rgba(201,162,39,0.25);
    padding:32px 0;
    text-align:center;
    font-size:12.5px; color:var(--parchment-dim);
    font-family:'IBM Plex Mono', monospace;
  }

  @media (prefers-reduced-motion: reduce){
    *{ transition:none !important; }
  }

  /* mobile whatsapp floating button */
  .float-wa{
    position:fixed; bottom:20px; right:20px; z-index:60;
    background:var(--seal); color:var(--parchment);
    width:56px; height:56px; border-radius:50%;
    display:flex; align-items:center; justify-content:center;
    box-shadow:0 8px 20px -6px rgba(0,0,0,0.5);
    border:1px solid rgba(228,194,78,0.5);
  }
  .float-wa svg{ width:26px; height:26px; }
</style>
</head>
<body>

<header>
  <div class="nav-inner">
    <div class="brand">
      <div class="brand-mark">MR</div>
      <div class="brand-name">Maiara Rocha</div>
    </div>
    <nav class="tabs">
      <a href="#servicos">Serviços</a>
      <a href="#prazos">Prazos</a>
      <a href="#mei">MEI</a>
      <a href="#cobertura">Cobertura</a>
    </nav>
    <a class="nav-cta" href="https://wa.me/5512987120584?text=Ol%C3%A1%2C%20vim%20pelo%20site%20e%20gostaria%20de%20falar%20sobre%20a%20contabilidade%20da%20minha%20empresa." target="_blank" rel="noopener">Falar no WhatsApp</a>
  </div>
</header>

<main>
  <!-- HERO -->
  <section class="hero wrap">
    <div class="hero-frame">
      <span class="corner-tr"></span>
      <span class="corner-bl"></span>
      <div class="eyebrow">Contabilidade para pequenas empresas</div>
      <h1>Cuidamos dos números <em>para você cuidar do negócio</em></h1>
      <p class="hero-sub">Fiscal, trabalhista e impostos de PME, sem surpresas. Maiara Rocha organiza a contabilidade do seu CNPJ com clareza — do MEI à empresa que já cresceu.</p>
      <div class="hero-actions">
        <a class="seal-btn" href="https://wa.me/5512987120584?text=Ol%C3%A1%2C%20vim%20pelo%20site%20e%20gostaria%20de%20falar%20sobre%20a%20contabilidade%20da%20minha%20empresa." target="_blank" rel="noopener">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12.04 2C6.58 2 2.13 6.45 2.13 11.91c0 1.87.5 3.62 1.44 5.13L2 22l5.13-1.53a9.9 9.9 0 0 0 4.9 1.3h.01c5.46 0 9.9-4.45 9.9-9.91 0-2.65-1.03-5.14-2.9-7.01A9.87 9.87 0 0 0 12.04 2Zm0 1.67c2.19 0 4.25.85 5.8 2.4a8.2 8.2 0 0 1 2.4 5.8c0 4.52-3.68 8.2-8.2 8.2a8.2 8.2 0 0 1-4.15-1.13l-.3-.17-3.05.9.91-2.97-.19-.31a8.15 8.15 0 0 1-1.24-4.33c0-4.52 3.68-8.2 8.2-8.2ZM8.5 7.13c-.16 0-.42.06-.64.3-.22.24-.85.83-.85 2.02s.87 2.34.99 2.5c.12.16 1.7 2.6 4.13 3.64.58.25 1.03.4 1.38.51.58.18 1.11.16 1.53.1.47-.07 1.44-.59 1.64-1.16.2-.57.2-1.06.14-1.16-.06-.1-.22-.16-.46-.28-.24-.12-1.44-.71-1.66-.79-.22-.08-.39-.12-.55.12-.16.24-.63.79-.77.95-.14.16-.28.18-.52.06-.24-.12-1.01-.37-1.93-1.19-.71-.63-1.2-1.41-1.34-1.65-.14-.24-.02-.37.1-.49.11-.11.24-.28.36-.42.12-.14.16-.24.24-.4.08-.16.04-.3-.02-.42-.06-.12-.55-1.35-.76-1.85-.2-.48-.4-.42-.55-.42Z"/></svg>
          Chamar no WhatsApp
        </a>
        <span class="seal-note">Resposta em horário comercial</span>
      </div>
    </div>
  </section>

  <!-- SERVIÇOS -->
  <section id="servicos" class="wrap">
    <div class="section-head">
      <span class="section-num">01</span>
      <h2>Serviços</h2>
    </div>
    <p class="section-tagline">Tudo que envolve o CNPJ acompanhado de perto — sem jargão, sem atraso, sem letra miúda.</p>
    <div class="ledger">
      <div class="ledger-row">
        <div class="glyph">Fi</div>
        <div>
          <h3>Fiscal</h3>
          <p>Apuração de impostos, emissão de guias e escrituração em dia, para o CNPJ nunca ficar exposto a multa por atraso.</p>
        </div>
      </div>
      <div class="ledger-row">
        <div class="glyph">Tr</div>
        <div>
          <h3>Trabalhista</h3>
          <p>Folha de pagamento, admissões, rescisões e obrigações com funcionários — conduzidas dentro da lei, sem dor de cabeça.</p>
        </div>
      </div>
      <div class="ledger-row">
        <div class="glyph">Im</div>
        <div>
          <h3>Impostos de PME</h3>
          <p>Cálculo e orientação sobre Simples Nacional, Lucro Presumido e demais regimes, sempre com o cenário mais vantajoso para o seu porte.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- PRAZOS -->
  <section id="prazos" class="wrap">
    <div class="section-head">
      <span class="section-num">02</span>
      <h2>Prazos para ficar de olho</h2>
    </div>
    <p class="section-tagline">Um calendário simplificado das obrigações que mais pegam PME e MEI de surpresa. Como cliente, você recebe os lembretes específicos do seu regime.</p>
    <div class="dates">
      <div class="date-row">
        <div class="date">Dia 20</div>
        <div>
          <h4>Vencimento do DAS</h4>
          <p>Guia mensal do Simples Nacional (ou DAS-MEI), com o imposto do mês anterior.</p>
        </div>
      </div>
      <div class="date-row">
        <div class="date">Dia 07</div>
        <div>
          <h4>Obrigações da folha</h4>
          <p>Encargos e guias trabalhistas referentes à folha de pagamento do mês anterior.</p>
        </div>
      </div>
      <div class="date-row">
        <div class="date">31 de maio</div>
        <div>
          <h4>Declaração Anual do MEI</h4>
          <p>DASN-SIMEI, com o faturamento do ano anterior — obrigatória mesmo sem movimento.</p>
        </div>
      </div>
      <div class="date-row">
        <div class="date">Anual</div>
        <div>
          <h4>Renovação de alvarás e licenças</h4>
          <p>Verificação de vencimentos municipais e estaduais que variam por atividade e cidade.</p>
        </div>
      </div>
    </div>
    <p class="dates-note">Datas de referência — o calendário exato muda conforme o regime tributário e o município. Isso é conversa para a nossa primeira reunião.</p>
  </section>

  <!-- MEI -->
  <section id="mei" class="wrap">
    <div class="section-head">
      <span class="section-num">03</span>
      <h2>O que é considerado MEI</h2>
    </div>
    <div class="mei-grid">
      <div class="mei-card">
        <p><strong>MEI</strong> é o Microempreendedor Individual: um CNPJ simplificado para quem fatura até <strong>R$ 81.000 por ano</strong> e atua sozinho, podendo ter no máximo um funcionário.</p>
        <p>É a porta de entrada mais comum para formalizar autônomos e pequenos negócios — impostos fixos e obrigações reduzidas, mas com regras próprias que precisam ser respeitadas.</p>
      </div>
      <ul class="mei-list">
        <li>Pagamento mensal fixo através do DAS-MEI</li>
        <li>Limite de faturamento anual de R$ 81 mil</li>
        <li>Permitido apenas um funcionário registrado</li>
        <li>Declaração anual obrigatória (DASN-SIMEI)</li>
        <li>Migração para ME quando o negócio cresce além do limite</li>
      </ul>
    </div>
  </section>

  <!-- RELATÓRIOS / ABERTURA / REGULARIZAÇÃO -->
  <section class="wrap">
    <div class="section-head">
      <span class="section-num">04</span>
      <h2>Relatórios, aberturas e regularização</h2>
    </div>
    <div class="ledger">
      <div class="ledger-row">
        <div class="glyph">Re</div>
        <div>
          <h3>Relatórios gerenciais</h3>
          <p>Balanços e demonstrativos claros, para você enxergar a saúde financeira do negócio sem depender de planilha própria.</p>
        </div>
      </div>
      <div class="ledger-row">
        <div class="glyph">Ab</div>
        <div>
          <h3>Abertura de empresa</h3>
          <p>Do MEI à sociedade limitada: escolha de regime, registro na Receita e nas prefeituras, e CNPJ pronto para operar.</p>
        </div>
      </div>
      <div class="ledger-row">
        <div class="glyph">Rg</div>
        <div>
          <h3>Regularização</h3>
          <p>CNPJ com pendências, débitos ou obrigações atrasadas? Levantamos o histórico e colocamos tudo em dia.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- COBERTURA -->
  <section id="cobertura" class="wrap">
    <div class="section-head">
      <span class="section-num">05</span>
      <h2>Onde atendemos</h2>
    </div>
    <div class="coverage">
      <div class="cov-card">
        <h3>Remoto</h3>
        <p>Atendimento por todo o Brasil, com reuniões e envio de documentos 100% online.</p>
        <span class="cov-tag">Todo o país</span>
      </div>
      <div class="cov-card">
        <h3>Presencial</h3>
        <p>Reuniões pessoalmente para quem está em São José dos Campos, SP, e prefere conversar cara a cara.</p>
        <span class="cov-tag">São José dos Campos · SP</span>
      </div>
    </div>
  </section>

  <!-- FINAL CTA -->
  <section class="final-cta wrap">
    <div class="frame">
      <span class="corner-tr"></span>
      <span class="corner-bl"></span>
      <h2>Sua contabilidade, sem surpresas.</h2>
      <p>Fale com a Maiara agora e entenda como deixar o fiscal, o trabalhista e os impostos do seu CNPJ em dia.</p>
      <a class="seal-btn" href="https://wa.me/5512987120584?text=Ol%C3%A1%2C%20vim%20pelo%20site%20e%20gostaria%20de%20falar%20sobre%20a%20contabilidade%20da%20minha%20empresa." target="_blank" rel="noopener">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12.04 2C6.58 2 2.13 6.45 2.13 11.91c0 1.87.5 3.62 1.44 5.13L2 22l5.13-1.53a9.9 9.9 0 0 0 4.9 1.3h.01c5.46 0 9.9-4.45 9.9-9.91 0-2.65-1.03-5.14-2.9-7.01A9.87 9.87 0 0 0 12.04 2Zm0 1.67c2.19 0 4.25.85 5.8 2.4a8.2 8.2 0 0 1 2.4 5.8c0 4.52-3.68 8.2-8.2 8.2a8.2 8.2 0 0 1-4.15-1.13l-.3-.17-3.05.9.91-2.97-.19-.31a8.15 8.15 0 0 1-1.24-4.33c0-4.52 3.68-8.2 8.2-8.2ZM8.5 7.13c-.16 0-.42.06-.64.3-.22.24-.85.83-.85 2.02s.87 2.34.99 2.5c.12.16 1.7 2.6 4.13 3.64.58.25 1.03.4 1.38.51.58.18 1.11.16 1.53.1.47-.07 1.44-.59 1.64-1.16.2-.57.2-1.06.14-1.16-.06-.1-.22-.16-.46-.28-.24-.12-1.44-.71-1.66-.79-.22-.08-.39-.12-.55.12-.16.24-.63.79-.77.95-.14.16-.28.18-.52.06-.24-.12-1.01-.37-1.93-1.19-.71-.63-1.2-1.41-1.34-1.65-.14-.24-.02-.37.1-.49.11-.11.24-.28.36-.42.12-.14.16-.24.24-.4.08-.16.04-.3-.02-.42-.06-.12-.55-1.35-.76-1.85-.2-.48-.4-.42-.55-.42Z"/></svg>
        Falar com a Maiara
      </a>
    </div>
  </section>
</main>

<footer>
  <div class="wrap">MAIARA ROCHA · CONTABILIDADE PARA PEQUENAS EMPRESAS</div>
</footer>

<a class="float-wa" href="https://wa.me/5512987120584?text=Ol%C3%A1%2C%20vim%20pelo%20site%20e%20gostaria%20de%20falar%20sobre%20a%20contabilidade%20da%20minha%20empresa." target="_blank" rel="noopener" aria-label="WhatsApp">
  <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12.04 2C6.58 2 2.13 6.45 2.13 11.91c0 1.87.5 3.62 1.44 5.13L2 22l5.13-1.53a9.9 9.9 0 0 0 4.9 1.3h.01c5.46 0 9.9-4.45 9.9-9.91 0-2.65-1.03-5.14-2.9-7.01A9.87 9.87 0 0 0 12.04 2Zm0 1.67c2.19 0 4.25.85 5.8 2.4a8.2 8.2 0 0 1 2.4 5.8c0 4.52-3.68 8.2-8.2 8.2a8.2 8.2 0 0 1-4.15-1.13l-.3-.17-3.05.9.91-2.97-.19-.31a8.15 8.15 0 0 1-1.24-4.33c0-4.52 3.68-8.2 8.2-8.2ZM8.5 7.13c-.16 0-.42.06-.64.3-.22.24-.85.83-.85 2.02s.87 2.34.99 2.5c.12.16 1.7 2.6 4.13 3.64.58.25 1.03.4 1.38.51.58.18 1.11.16 1.53.1.47-.07 1.44-.59 1.64-1.16.2-.57.2-1.06.14-1.16-.06-.1-.22-.16-.46-.28-.24-.12-1.44-.71-1.66-.79-.22-.08-.39-.12-.55.12-.16.24-.63.79-.77.95-.14.16-.28.18-.52.06-.24-.12-1.01-.37-1.93-1.19-.71-.63-1.2-1.41-1.34-1.65-.14-.24-.02-.37.1-.49.11-.11.24-.28.36-.42.12-.14.16-.24.24-.4.08-.16.04-.3-.02-.42-.06-.12-.55-1.35-.76-1.85-.2-.48-.4-.42-.55-.42Z"/></svg>
</a>

</body>
</html>
