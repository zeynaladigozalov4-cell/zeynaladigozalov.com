# zeynaladigozalov.com
<!DOCTYPE html>
<html lang="az">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Zeynal Adigozalov | Reelsmaker & Videoqraf</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Manrope:wght@500;700;800&family=Plus+Jakarta+Sans:wght@400;500;600&display=swap');

    :root {
      --bg-color: #08090c;
      --text-main: #f8fafc;
      --text-muted: #94a3b8;
      --card-bg: rgba(18, 20, 29, 0.4);
      --border-color: rgba(255, 255, 255, 0.08);
      --control-bg: rgba(255, 255, 255, 0.05);
      --glow-spot1: rgba(138, 43, 226, 0.18);
      --glow-spot2: rgba(59, 130, 246, 0.12);
      --modal-overlay: rgba(8, 9, 12, 0.88);
      --pattern-color: rgba(255, 255, 255, 0.04);
    }

    body.light-mode {
      --bg-color: #f1f5f9;
      --text-main: #0f172a;
      --text-muted: #64748b;
      --card-bg: rgba(255, 255, 255, 0.6);
      --border-color: rgba(15, 23, 42, 0.08);
      --control-bg: rgba(15, 23, 42, 0.04);
      --glow-spot1: rgba(99, 102, 241, 0.15);
      --glow-spot2: rgba(14, 165, 233, 0.1);
      --modal-overlay: rgba(241, 245, 249, 0.88);
      --pattern-color: rgba(15, 23, 42, 0.04);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      outline: none !important;
    }

    *:focus, *:active {
      outline: none !important;
      box-shadow: none !important;
    }

    body {
      background-color: var(--bg-color);
      color: var(--text-main);
      font-family: 'Plus Jakarta Sans', sans-serif;
      line-height: 1.6;
      padding: 30px 15px 60px;
      position: relative;
      overflow-x: hidden;
      transition: background-color 0.3s ease, color 0.3s ease;
    }

    .film-grain {
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.8' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)' opacity='0.03'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 999;
      opacity: 0.6;
    }

    .bg-pattern {
      position: fixed;
      inset: 0;
      background-image: radial-gradient(var(--pattern-color) 1.5px, transparent 1.5px);
      background-size: 28px 28px;
      pointer-events: none;
      z-index: 0;
    }

    .controls-wrapper {
      position: absolute;
      top: 20px;
      right: 25px;
      display: flex;
      align-items: center;
      gap: 10px;
      z-index: 10;
    }

    .lang-container {
      display: flex;
      gap: 4px;
      background: var(--control-bg);
      border: 1px solid var(--border-color);
      padding: 4px;
      border-radius: 20px;
      backdrop-filter: blur(12px);
    }

    .lang-btn {
      background: transparent;
      border: none;
      color: var(--text-muted);
      font-size: 0.75rem;
      font-weight: 700;
      padding: 5px 12px;
      border-radius: 16px;
      cursor: pointer;
      transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .lang-btn.active {
      background: var(--text-main);
      color: var(--bg-color);
      box-shadow: 0 2px 8px rgba(0,0,0,0.15);
    }

    .theme-toggle-btn {
      background: var(--control-bg);
      border: 1px solid var(--border-color);
      width: 40px;
      height: 40px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      backdrop-filter: blur(12px);
      transition: all 0.25s ease;
      color: var(--text-main);
    }

    .theme-toggle-btn:hover {
      transform: scale(1.05);
      border-color: rgba(255, 255, 255, 0.2);
    }

    .theme-toggle-btn svg {
      width: 18px;
      height: 18px;
      fill: none;
      stroke: currentColor;
      stroke-width: 2;
      stroke-linecap: round;
      stroke-linejoin: round;
    }

    .icon-sun { display: none; }
    .icon-moon { display: block; }

    body.light-mode .icon-sun { display: block; color: #f59e0b; }
    body.light-mode .icon-moon { display: none; }

    .bg-decorations {
      position: absolute;
      inset: 0;
      pointer-events: none;
      z-index: 0;
      overflow: hidden;
    }

    .glow-spot-1 {
      position: absolute;
      top: -100px;
      left: 15%;
      width: 600px;
      height: 400px;
      background: radial-gradient(circle, var(--glow-spot1) 0%, rgba(0,0,0,0) 70%);
      filter: blur(100px);
    }

    .glow-spot-2 {
      position: absolute;
      bottom: 20%;
      right: 10%;
      width: 500px;
      height: 500px;
      background: radial-gradient(circle, var(--glow-spot2) 0%, rgba(0,0,0,0) 70%);
      filter: blur(120px);
    }

    header {
      max-width: 800px;
      margin: 20px auto 35px;
      text-align: center;
      position: relative;
      z-index: 1;
    }

    header .name {
      font-family: 'Manrope', sans-serif;
      font-size: 2.8rem;
      font-weight: 800;
      letter-spacing: -1px;
      color: var(--text-main);
      margin-bottom: 6px;
    }

    header .subtitle {
      color: var(--text-muted);
      font-size: 0.85rem;
      font-weight: 700;
      letter-spacing: 2px;
      text-transform: uppercase;
      margin-bottom: 20px;
    }

    .social-links {
      display: flex;
      justify-content: center;
      gap: 12px;
    }

    .social-links a {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      text-decoration: none;
      font-size: 0.85rem;
      font-weight: 600;
      padding: 10px 24px;
      border-radius: 24px;
      transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .social-links a.instagram {
      position: relative;
      background: transparent;
      border: none;
      color: #e1306c;
      z-index: 1;
    }

    .social-links a.instagram::before {
      content: '';
      position: absolute;
      inset: 0;
      border-radius: 24px;
      padding: 2px;
      background: linear-gradient(45deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888);
      -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
      -webkit-mask-composite: xor;
      mask-composite: exclude;
      z-index: -1;
      transition: opacity 0.25s ease;
    }

    .social-links a.instagram:hover {
      background: linear-gradient(45deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888);
      color: #ffffff;
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(225, 48, 108, 0.3);
    }

    .social-links a.whatsapp {
      background: transparent;
      border: 2px solid #25d366;
      color: #25d366;
    }

    .social-links a.whatsapp:hover {
      background: #25d366;
      color: #000000;
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(37, 211, 102, 0.3);
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      position: relative;
      z-index: 1;
    }

    .filter-tabs {
      display: flex;
      justify-content: center;
      gap: 8px;
      flex-wrap: wrap;
      margin-bottom: 35px;
      overflow-x: auto;
      white-space: nowrap;
      padding-bottom: 5px;
      scrollbar-width: none;
    }

    .filter-tabs::-webkit-scrollbar {
      display: none;
    }

    .filter-btn {
      background: var(--control-bg);
      border: 1px solid var(--border-color);
      color: var(--text-muted);
      font-size: 0.82rem;
      font-weight: 600;
      padding: 9px 20px;
      border-radius: 20px;
      cursor: pointer;
      transition: all 0.25s ease;
      backdrop-filter: blur(10px);
      flex-shrink: 0;
    }

    .filter-btn:hover {
      background: var(--text-main);
      color: var(--bg-color);
      border-color: var(--text-main);
    }

    .filter-btn.active {
      background: var(--text-main);
      color: var(--bg-color);
      border-color: var(--text-main);
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    }

    .reels-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
      gap: 24px;
    }

    .reel-card {
      background: var(--card-bg);
      border-radius: 24px;
      overflow: hidden;
      border: 1px solid var(--border-color);
      backdrop-filter: blur(16px);
      transition: all 0.25s cubic-bezier(0.16, 1, 0.3, 1);
      cursor: pointer;
      position: relative;
      box-shadow: 0 10px 30px -10px rgba(0, 0, 0, 0.3);
    }

    .reel-card.hidden {
      display: none !important;
    }

    .reel-card:hover {
      transform: translateY(-4px) scale(1.03);
      border-color: rgba(255, 255, 255, 0.2);
      box-shadow: 0 15px 30px -10px rgba(0, 0, 0, 0.5);
    }

    .reel-card:active {
      transform: scale(0.97);
    }

    .reel-cover {
      width: 100%;
      aspect-ratio: 9 / 16;
      position: relative;
      overflow: hidden;
      border-radius: 23px;
      background: #000000;
    }

    .reel-cover img {
      width: 100%;
      height: 100%;
      object-fit: cover !important;
      transition: transform 0.35s cubic-bezier(0.16, 1, 0.3, 1);
      position: absolute;
      inset: 0;
      z-index: 1;
    }

    .reel-card:hover .reel-cover img,
    .reel-card.touch-active .reel-cover img {
      transform: scale(1.04);
    }

    .preview-video {
      position: absolute;
      inset: 0;
      width: 100%;
      height: 100%;
      object-fit: cover !important;
      opacity: 0;
      transition: opacity 0.25s ease;
      z-index: 2;
      pointer-events: none;
    }

    .reel-card:hover .preview-video,
    .reel-card.touch-active .preview-video {
      opacity: 1;
    }

    .play-overlay {
      position: absolute;
      inset: 0;
      background: rgba(0, 0, 0, 0);
      display: flex;
      align-items: center;
      justify-content: center;
      opacity: 0;
      transition: opacity 0.25s ease, background 0.25s ease;
      z-index: 3;
    }

    .reel-card:hover .play-overlay,
    .reel-card.touch-active .play-overlay {
      opacity: 1;
      background: rgba(0, 0, 0, 0.4);
    }

    .play-icon {
      width: 48px;
      height: 48px;
      background: rgba(255, 255, 255, 0.2);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 255, 255, 0.5);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: transform 0.25s ease, background 0.25s ease;
    }

    .play-icon::after {
      content: '';
      width: 0;
      height: 0;
      border-style: solid;
      border-width: 6px 0 6px 11px;
      border-color: transparent transparent transparent #ffffff;
      margin-left: 3px;
    }

    .reel-card:hover .play-icon,
    .reel-card.touch-active .play-icon {
      transform: scale(1.08);
      background: #ffffff;
    }

    .reel-card:hover .play-icon::after,
    .reel-card.touch-active .play-icon::after {
      border-color: transparent transparent transparent #000000;
    }

    .reel-info-overlay {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      padding: 24px 14px 14px 14px;
      background: linear-gradient(to top, rgba(5, 6, 9, 0.95) 0%, rgba(5, 6, 9, 0.6) 60%, transparent 100%);
      z-index: 4;
      display: flex;
      flex-direction: column;
      gap: 3px;
      pointer-events: none;
    }

    .reel-title {
      font-size: 0.92rem;
      font-weight: 700;
      color: #ffffff;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
      text-shadow: 0 1px 3px rgba(0, 0, 0, 0.8);
    }

    .reel-category {
      font-size: 0.72rem;
      font-weight: 600;
      color: rgba(255, 255, 255, 0.75);
      text-transform: uppercase;
      letter-spacing: 0.5px;
      text-shadow: 0 1px 2px rgba(0, 0, 0, 0.8);
    }

    .video-modal {
      display: none;
      position: fixed;
      inset: 0;
      background: var(--modal-overlay);
      backdrop-filter: blur(18px);
      -webkit-backdrop-filter: blur(18px);
      z-index: 1000;
      justify-content: center;
      align-items: center;
      padding: 20px;
      opacity: 0;
      transition: opacity 0.25s ease;
    }

    .video-modal.active {
      display: flex;
      opacity: 1;
    }

    .modal-container {
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 36px;
      overflow: hidden;
      background: transparent;
      border: none !important;
      outline: none !important;
      box-shadow: 0 30px 70px rgba(0, 0, 0, 0.7);
      transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
      z-index: 2;
    }

    .modal-container.portrait {
      width: 100%;
      max-width: 400px;
      height: 82vh;
      max-height: 760px;
      aspect-ratio: 9 / 16;
    }

    .modal-container.landscape {
      width: 90%;
      max-width: 960px;
      aspect-ratio: 16 / 9;
      height: auto;
      max-height: 82vh;
    }

    .modal-container video.main-player {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
      border-radius: 36px !important;
      cursor: pointer;
      background: transparent;
      outline: none !important;
      border: none !important;
    }

    .custom-controls {
      position: absolute;
      bottom: 16px;
      left: 16px;
      right: 16px;
      background: rgba(15, 17, 23, 0.65);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      border: 1px solid rgba(255, 255, 255, 0.12);
      border-radius: 16px;
      padding: 10px 14px;
      display: flex;
      align-items: center;
      gap: 8px;
      z-index: 10;
      opacity: 0;
      transform: translateY(10px);
      transition: opacity 0.25s ease, transform 0.25s ease;
    }

    .modal-container:hover .custom-controls {
      opacity: 1;
      transform: translateY(0);
    }

    .control-btn {
      background: transparent;
      border: none;
      color: #ffffff;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      width: 32px;
      height: 32px;
      border-radius: 8px;
      transition: background 0.2s ease;
    }

    .control-btn:hover {
      background: rgba(255, 255, 255, 0.15);
    }

    .control-btn svg {
      width: 18px;
      height: 18px;
      fill: currentColor;
    }

    .progress-bar-container {
      flex: 1;
      height: 8px;
      background: rgba(255, 255, 255, 0.2);
      border-radius: 4px;
      cursor: pointer;
      position: relative;
      overflow: hidden;
      touch-action: none;
    }

    .progress-filled {
      position: absolute;
      top: 0;
      left: 0;
      height: 100%;
      width: 100%;
      background: #ffffff;
      border-radius: 4px;
      transform-origin: left;
      transform: scaleX(0);
      pointer-events: none;
    }

    .time-display {
      font-size: 0.72rem;
      font-weight: 600;
      color: rgba(255, 255, 255, 0.85);
      min-width: 58px;
      text-align: center;
      font-variant-numeric: tabular-nums;
    }

    .close-modal {
      position: absolute;
      top: 25px;
      right: 25px;
      z-index: 1002;
      background: rgba(255, 255, 255, 0.1);
      width: 44px;
      height: 44px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 255, 255, 0.15);
      cursor: pointer;
      transition: all 0.25s ease;
    }

    .close-modal:hover {
      transform: scale(1.08) rotate(90deg);
      background: rgba(255, 255, 255, 0.25);
    }

    .close-modal svg {
      width: 18px;
      height: 18px;
      stroke: #ffffff;
      stroke-width: 2.5;
      stroke-linecap: round;
    }

    .device-hint {
      position: fixed;
      bottom: 28px;
      left: 50%;
      transform: translateX(-50%);
      color: rgba(255, 255, 255, 0.95);
      font-size: 0.8rem;
      font-weight: 600;
      font-family: 'Manrope', sans-serif;
      pointer-events: none;
      z-index: 1001;
      text-align: center;
      white-space: nowrap;
      background: rgba(18, 20, 29, 0.65);
      padding: 10px 24px;
      border-radius: 30px;
      backdrop-filter: blur(16px);
      border: 1px solid rgba(255, 255, 255, 0.12);
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4);
      opacity: 0;
      transition: opacity 0.3s ease, transform 0.3s ease;
    }

    .video-modal.active .device-hint {
      opacity: 1;
    }

    .toast-msg {
      position: fixed;
      top: 30px;
      left: 50%;
      transform: translateX(-50%) translateY(-20px);
      background: rgba(255, 255, 255, 0.9);
      color: #000;
      padding: 8px 18px;
      border-radius: 20px;
      font-size: 0.8rem;
      font-weight: 700;
      z-index: 2000;
      opacity: 0;
      pointer-events: none;
      transition: all 0.25s ease;
    }
    .toast-msg.show {
      opacity: 1;
      transform: translateX(-50%) translateY(0);
    }

    .hint-pc { display: block; }
    .hint-mobile { display: none; }

    @media (pointer: coarse) {
      .hint-pc { display: none; }
      .hint-mobile { display: block; }
      .custom-controls { opacity: 1; transform: translateY(0); }
    }

    footer {
      text-align: center;
      margin-top: 60px;
      padding: 20px 10px;
      color: var(--text-muted);
      font-size: 0.8rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 12px;
      position: relative;
      z-index: 1;
    }

    footer .contact-text {
      font-size: 0.78rem;
      font-weight: 700;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      color: var(--text-muted);
      opacity: 0.8;
      margin-bottom: 2px;
    }

    footer .social-links {
      transform: scale(0.9);
    }

    footer .social-links a.instagram,
    footer .social-links a.whatsapp {
      background: var(--control-bg);
      border: 1px solid var(--border-color);
      color: var(--text-main);
    }

    footer .social-links a.instagram::before {
      display: none;
    }

    footer .social-links a.instagram:hover,
    footer .social-links a.whatsapp:hover {
      background: var(--text-main);
      color: var(--bg-color);
      transform: translateY(-2px);
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
      border-color: var(--text-main);
    }

    @media (max-width: 600px) {
      header .name { font-size: 2.2rem; }
      .reels-grid { grid-template-columns: repeat(2, 1fr); gap: 10px; }
      .reel-card { border-radius: 18px; }
      .reel-cover { border-radius: 17px; background: #000000; }
      .reel-title { font-size: 0.82rem; }
      .reel-category { font-size: 0.65rem; }
      .modal-container { border-radius: 28px; }
      .modal-container video.main-player { border-radius: 28px !important; }
      .filter-tabs { justify-content: flex-start; padding-left: 5px; }
    }
  </style>
</head>
<body>

  <div class="film-grain"></div>
  <div class="bg-pattern"></div>
  <div class="toast-msg" id="toastMsg" data-az="Link kopyalandı" data-en="Link copied">Link kopyalandı</div>

  <div class="controls-wrapper">
    <div class="lang-container">
      <button class="lang-btn" data-lang-code="az">AZ</button>
      <button class="lang-btn" data-lang-code="en">EN</button>
    </div>

    <button class="theme-toggle-btn" id="themeToggleBtn" title="Rejim">
      <svg class="icon-moon" viewBox="0 0 24 24"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path></svg>
      <svg class="icon-sun" viewBox="0 0 24 24">
        <circle cx="12" cy="12" r="5"></circle>
        <line x1="12" y1="1" x2="12" y2="3"></line>
        <line x1="12" y1="21" x2="12" y2="23"></line>
        <line x1="4.22" y1="4.22" x2="5.64" y2="5.64"></line>
        <line x1="18.36" y1="18.36" x2="19.78" y2="19.78"></line>
        <line x1="1" y1="12" x2="3" y2="12"></line>
        <line x1="21" y1="12" x2="23" y2="12"></line>
        <line x1="4.22" y1="19.78" x2="5.64" y2="18.36"></line>
        <line x1="18.36" y1="5.64" x2="19.78" y2="4.22"></line>
      </svg>
    </button>
  </div>

  <div class="bg-decorations">
    <div class="glow-spot-1"></div>
    <div class="glow-spot-2"></div>
  </div>

  <header>
    <h1 class="name">Zeynal Adigozalov</h1>
    <p class="subtitle" data-az="Reelsmaker • Videoqraf" data-en="Reelsmaker • Videographer">Reelsmaker • Videoqraf</p>
    <div class="social-links">
      <a href="https://instagram.com/zeynal_adigozalov0" target="_blank" class="instagram">Instagram</a>
      <a href="https://wa.me/994555590392" target="_blank" class="whatsapp">WhatsApp</a>
    </div>
  </header>

  <main class="container">
    <div class="filter-tabs">
      <button class="filter-btn active" data-filter="all" data-az="Bütün çəkilişlər" data-en="All works">Bütün çəkilişlər</button>
      <button class="filter-btn" data-filter="cinematic" data-az="Sinematik" data-en="Cinematic">Sinematik</button>
      <button class="filter-btn" data-filter="brand" data-az="Brend və reklam" data-en="Brand & commercial">Brend və reklam</button>
      <button class="filter-btn" data-filter="sport" data-az="İdman" data-en="Sports">İdman</button>
      <button class="filter-btn" data-filter="event" data-az="Tədbir" data-en="Events">Tədbir</button>
      <button class="filter-btn" data-filter="creative" data-az="Kreativ" data-en="Creative">Kreativ</button>
    </div>

    <div class="reels-grid">
      <div class="reel-card" data-id="sinematik-gece" data-category="cinematic" data-aspect="vertical" data-video="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.mp4" onclick="openVideoFeed(this)">
        <div class="reel-cover">
          <img src="https://images.unsplash.com/photo-1536440136628-849c177e76a1?q=80&w=800&auto=format&fit=crop" alt="Reel" loading="lazy">
          <div class="play-overlay"><div class="play-icon"></div></div>
          <div class="reel-info-overlay">
            <div class="reel-title" data-az="Sinematik Gecə" data-en="Cinematic Night">Sinematik Gecə</div>
            <div class="reel-category" data-az="Sinematik" data-en="Cinematic">Sinematik</div>
          </div>
        </div>
      </div>

      <div class="reel-card" data-id="qisa-metraj" data-category="cinematic" data-aspect="horizontal" data-video="https://www.w3schools.com/html/mov_bbb.mp4" onclick="openVideoFeed(this)">
        <div class="reel-cover">
          <img src="https://images.unsplash.com/photo-1485846234645-a62644f84728?q=80&w=800&auto=format&fit=crop" alt="Reel" loading="lazy">
          <div class="play-overlay"><div class="play-icon"></div></div>
          <div class="reel-info-overlay">
            <div class="reel-title" data-az="Qısa Metraj" data-en="Short Film">Qısa Metraj</div>
            <div class="reel-category" data-az="Sinematik" data-en="Cinematic">Sinematik</div>
          </div>
        </div>
      </div>

      <div class="reel-card" data-id="brend-promo" data-category="brand" data-aspect="vertical" data-video="https://vjs.zencdn.net/v/oceans.mp4" onclick="openVideoFeed(this)">
        <div class="reel-cover">
          <img src="https://images.unsplash.com/photo-1509631179647-0177331693ae?q=80&w=800&auto=format&fit=crop" alt="Reel" loading="lazy">
          <div class="play-overlay"><div class="play-icon"></div></div>
          <div class="reel-info-overlay">
            <div class="reel-title" data-az="Brend Promo" data-en="Brand Promo">Brend Promo</div>
            <div class="reel-category" data-az="Brend və reklam" data-en="Brand & commercial">Brend və reklam</div>
          </div>
        </div>
      </div>

      <div class="reel-card" data-id="kommersiya-cekilis" data-category="brand" data-aspect="vertical" data-video="https://media.w3.org/2010/05/sintel/trailer.mp4" onclick="openVideoFeed(this)">
        <div class="reel-cover">
          <img src="https://images.unsplash.com/photo-1441986300917-64674bd600d8?q=80&w=800&auto=format&fit=crop" alt="Reel" loading="lazy">
          <div class="play-overlay"><div class="play-icon"></div></div>
          <div class="reel-info-overlay">
            <div class="reel-title" data-az="Kommersiya Çəkiliş" data-en="Commercial Shoot">Kommersiya Çəkiliş</div>
            <div class="reel-category" data-az="Brend və reklam" data-en="Brand & commercial">Brend və reklam</div>
          </div>
        </div>
      </div>

      <div class="reel-card" data-id="fitnes-motivasiya" data-category="sport" data-aspect="vertical" data-video="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.mp4" onclick="openVideoFeed(this)">
        <div class="reel-cover">
          <img src="https://images.unsplash.com/photo-1612872087720-bb876e2e67d1?q=80&w=800&auto=format&fit=crop" alt="Reel" loading="lazy">
          <div class="play-overlay"><div class="play-icon"></div></div>
          <div class="reel-info-overlay">
            <div class="reel-title" data-az="Fitnes Motivasiya" data-en="Fitness Motivation">Fitnes Motivasiya</div>
            <div class="reel-category" data-az="İdman" data-en="Sports">İdman</div>
          </div>
        </div>
      </div>

      <div class="reel-card" data-id="konsert-tedbiri" data-category="event" data-aspect="horizontal" data-video="https://vjs.zencdn.net/v/oceans.mp4" onclick="openVideoFeed(this)">
        <div class="reel-cover">
          <img src="https://images.unsplash.com/photo-1492684223066-81342ee5ff30?q=80&w=800&auto=format&fit=crop" alt="Reel" loading="lazy">
          <div class="play-overlay"><div class="play-icon"></div></div>
          <div class="reel-info-overlay">
            <div class="reel-title" data-az="Konsert Tədbiri" data-en="Concert Event">Konsert Tədbiri</div>
            <div class="reel-category" data-az="Tədbir" data-en="Events">Tədbir</div>
          </div>
        </div>
      </div>

      <div class="reel-card" data-id="kreativ-kecidler" data-category="creative" data-aspect="vertical" data-video="https://media.w3.org/2010/05/sintel/trailer.mp4" onclick="openVideoFeed(this)">
        <div class="reel-cover">
          <img src="https://images.unsplash.com/photo-1550684848-fac1c5b4e853?q=80&w=800&auto=format&fit=crop" alt="Reel" loading="lazy">
          <div class="play-overlay"><div class="play-icon"></div></div>
          <div class="reel-info-overlay">
            <div class="reel-title" data-az="Kreativ Keçidlər" data-en="Creative Transitions">Kreativ Keçidlər</div>
            <div class="reel-category" data-az="Kreativ" data-en="Creative">Kreativ</div>
          </div>
        </div>
      </div>
    </div>
  </main>

  <div class="video-modal" id="videoModal">
    <button class="close-modal" onclick="closeVideo()">
      <svg viewBox="0 0 24 24">
        <line x1="18" y1="6" x2="6" y2="18"></line>
        <line x1="6" y1="6" x2="18" y2="18"></line>
      </svg>
    </button>

    <div class="modal-container portrait" id="modalContainer">
      <video class="main-player" id="player" playsinline controlsList="nodownload noplaybackrate" disablePictureInPicture oncontextmenu="return false;"></video>

      <div class="custom-controls" id="customControls">
        <button class="control-btn" id="playPauseBtn" title="Play/Pause">
          <svg id="playIconSvg" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
        </button>

        <div class="progress-bar-container" id="progressBarContainer">
          <div class="progress-filled" id="progressFilled"></div>
        </div>

        <div class="time-display" id="timeDisplay">0:00 / 0:00</div>

        <button class="control-btn" id="muteBtn" title="Səssiz/Səsli">
          <svg id="muteIconSvg" viewBox="0 0 24 24"><path d="M3 9v6h4l5 5V4L7 9H3zm13.5 3c0-1.77-1.02-3.29-2.5-4.03v8.05c1.48-.73 2.5-2.25 2.5-4.02zM14 3.23v2.06c2.89.86 5 3.54 5 6.71s-2.11 5.85-5 6.71v2.06c4.01-.91 7-4.49 7-8.77s-2.99-7.86-7-8.77z"/></svg>
        </button>

        <button class="control-btn" id="shareBtn" title="Paylaş">
          <svg viewBox="0 0 24 24"><path d="M18 16.08c-.76 0-1.44.3-1.96.77L8.91 12.7c.05-.23.09-.46.09-.7s-.04-.47-.09-.7l7.05-4.11c.54.5 1.25.81 2.04.81 1.66 0 3-1.34 3-3s-1.34-3-3-3-3 1.34-3 3c0 .24.04.47.09.7L8.04 9.81C7.5 9.31 6.79 9 6 9c-1.66 0-3 1.34-3 3s1.34 3 3 3c.79 0 1.5-.31 2.04-.81l7.12 4.16c-.05.21-.08.43-.08.65 0 1.61 1.31 2.92 2.92 2.92s2.92-1.31 2.92-2.92c0-1.61-1.31-2.92-2.92-2.92z"/></svg>
        </button>

        <button class="control-btn" id="fullscreenBtn" title="Tam ekran">
          <svg viewBox="0 0 24 24"><path d="M7 14H5v5h5v-2H7v-3zm-2-4h2V7h3V5H5v5zm12 7h-3v2h5v-5h-2v3zM14 5v2h3v3h2V5h-5z"/></svg>
        </button>
      </div>
    </div>

    <div class="device-hint">
      <div class="hint-pc" data-az="Naviqasiya üçün siçan çarxı (scroll) və ya ↑↓ ox düymələrindən istifadə edin" data-en="Use mouse wheel or ↑↓ arrow keys to navigate">Naviqasiya üçün siçan çarxı (scroll) və ya ↑↓ ox düymələrindən istifadə edin</div>
      <div class="hint-mobile" data-az="↑↓ Növbəti video üçün sürüşdürün" data-en="↑↓ Swipe for next video">↑↓ Növbəti video üçün sürüşdürün</div>
    </div>
  </div>

  <footer>
    <div class="contact-text" data-az="Əlaqə üçün" data-en="Get in touch">Əlaqə üçün</div>
    <div class="social-links">
      <a href="https://instagram.com/zeynal_adigozalov0" target="_blank" class="instagram">Instagram</a>
      <a href="https://wa.me/994555590392" target="_blank" class="whatsapp">WhatsApp</a>
    </div>
    <p>© 2026 Zeynal Adigozalov</p>
  </footer>

  <script>
    const filterButtons = document.querySelectorAll('.filter-btn');
    const reelCards = document.querySelectorAll('.reel-card');

    filterButtons.forEach(button => {
      button.addEventListener('click', () => {
        filterButtons.forEach(btn => btn.classList.remove('active'));
        button.classList.add('active');

        const filterValue = button.getAttribute('data-filter');

        reelCards.forEach(card => {
          if (filterValue === 'all' || card.getAttribute('data-category') === filterValue) {
            card.classList.remove('hidden');
          } else {
            card.classList.add('hidden');
          }
        });
      });
    });

    reelCards.forEach(card => {
      const startPreview = () => {
        const videoSrc = card.getAttribute('data-video');
        if (!videoSrc) return;

        const cover = card.querySelector('.reel-cover');
        let previewVideo = cover.querySelector('.preview-video');

        if (!previewVideo) {
          previewVideo = document.createElement('video');
          previewVideo.className = 'preview-video';
          previewVideo.src = videoSrc;
          previewVideo.muted = true;
          previewVideo.loop = true;
          previewVideo.playsInline = true;
          previewVideo.preload = 'metadata';
          
          cover.insertBefore(previewVideo, cover.querySelector('.play-overlay'));
        }

        previewVideo.play().catch(() => {});
      };

      const stopPreview = () => {
        const previewVideo = card.querySelector('.preview-video');
        if (previewVideo) {
          previewVideo.pause();
        }
      };

      card.addEventListener('mouseenter', startPreview);
      card.addEventListener('mouseleave', stopPreview);

      card.addEventListener('touchstart', () => {
        card.classList.add('touch-active');
        startPreview();
      }, { passive: true });

      card.addEventListener('touchend', () => {
        setTimeout(() => {
          card.classList.remove('touch-active');
          stopPreview();
        }, 300);
      }, { passive: true });

      card.addEventListener('touchcancel', () => {
        card.classList.remove('touch-active');
        stopPreview();
      }, { passive: true });
    });

    const themeToggleBtn = document.getElementById('themeToggleBtn');
    themeToggleBtn.addEventListener('click', () => {
      document.body.classList.toggle('light-mode');
    });

    const LangManager = {
      defaultLang: 'az',
      supportedLangs: ['az', 'en'],

      init() {
        const savedLang = localStorage.getItem('user_lang');
        const browserLang = navigator.language.slice(0, 2).toLowerCase();
        
        let initialLang = this.defaultLang;
        if (savedLang && this.supportedLangs.includes(savedLang)) {
          initialLang = savedLang;
        } else if (this.supportedLangs.includes(browserLang)) {
          initialLang = browserLang;
        }

        this.setLanguage(initialLang);
        this.bindEvents();
      },

      setLanguage(lang) {
        localStorage.setItem('user_lang', lang);
        document.querySelectorAll('.lang-btn').forEach(btn => {
          if (btn.getAttribute('data-lang-code') === lang) {
            btn.classList.add('active');
          } else {
            btn.classList.remove('active');
          }
        });

        document.querySelectorAll('[data-az]').forEach(el => {
          const text = el.getAttribute(`data-${lang}`);
          if (text) {
            if (el.tagName === 'INPUT' || el.tagName === 'TEXTAREA') {
              el.placeholder = text;
            } else {
              el.textContent = text;
            }
          }
        });
      },

      bindEvents() {
        document.querySelectorAll('.lang-btn').forEach(btn => {
          btn.addEventListener('click', () => {
            const lang = btn.getAttribute('data-lang-code');
            this.setLanguage(lang);
          });
        });
      }
    };

    LangManager.init();

    const videoModal = document.getElementById('videoModal');
    const modalContainer = document.getElementById('modalContainer');
    const player = document.getElementById('player');
    const playPauseBtn = document.getElementById('playPauseBtn');
    const playIconSvg = document.getElementById('playIconSvg');
    const progressBarContainer = document.getElementById('progressBarContainer');
    const progressFilled = document.getElementById('progressFilled');
    const timeDisplay = document.getElementById('timeDisplay');
    const muteBtn = document.getElementById('muteBtn');
    const muteIconSvg = document.getElementById('muteIconSvg');
    const shareBtn = document.getElementById('shareBtn');
    const fullscreenBtn = document.getElementById('fullscreenBtn');
    const toastMsg = document.getElementById('toastMsg');

    let currentCardIndex = 0;
    let visibleCards = [];

    function updateVisibleCards() {
      visibleCards = Array.from(document.querySelectorAll('.reel-card')).filter(card => !card.classList.contains('hidden'));
    }

    function openVideoFeed(card) {
      updateVisibleCards();
      currentCardIndex = visibleCards.indexOf(card);
      if (currentCardIndex === -1) currentCardIndex = 0;
      loadVideoFromCard(visibleCards[currentCardIndex]);
      videoModal.classList.add('active');
      document.body.style.overflow = 'hidden';
    }

    function loadVideoFromCard(card) {
      const videoSrc = card.getAttribute('data-video');
      const aspect = card.getAttribute('data-aspect');
      
      modalContainer.className = 'modal-container ' + (aspect === 'horizontal' ? 'landscape' : 'portrait');
      player.src = videoSrc;
      player.currentTime = 0;
      player.play().catch(() => {});
      updatePlayPauseIcon();
    }

    function closeVideo() {
      videoModal.classList.remove('active');
      player.pause();
      player.src = '';
      document.body.style.overflow = '';
    }

    function togglePlayPause() {
      if (player.paused) {
        player.play();
      } else {
        player.pause();
      }
      updatePlayPauseIcon();
    }

    function updatePlayPauseIcon() {
      if (player.paused) {
        playIconSvg.innerHTML = '<path d="M8 5v14l11-7z"/>';
      } else {
        playIconSvg.innerHTML = '<path d="M6 19h4V5H6v14zm8-14v14h4V5h-4z"/>';
      }
    }

    playPauseBtn.addEventListener('click', togglePlayPause);
    player.addEventListener('click', togglePlayPause);
    player.addEventListener('play', updatePlayPauseIcon);
    player.addEventListener('pause', updatePlayPauseIcon);

    player.addEventListener('timeupdate', () => {
      if (!player.duration) return;
      const percent = (player.currentTime / player.duration);
      progressFilled.style.transform = `scaleX(${percent})`;
      timeDisplay.textContent = formatTime(player.currentTime) + ' / ' + formatTime(player.duration);
    });

    function formatTime(seconds) {
      const mins = Math.floor(seconds / 60);
      const secs = Math.floor(seconds % 60);
      return mins + ':' + (secs < 10 ? '0' : '') + secs;
    }

    progressBarContainer.addEventListener('click', (e) => {
      const rect = progressBarContainer.getBoundingClientRect();
      const pos = (e.clientX - rect.left) / rect.width;
      if (player.duration) {
        player.currentTime = pos * player.duration;
      }
    });

    muteBtn.addEventListener('click', () => {
      player.muted = !player.muted;
      if (player.muted) {
        muteIconSvg.innerHTML = '<path d="M16.5 12c0-1.77-1.02-3.29-2.5-4.03v2.21l2.45 2.45c.03-.2.05-.42.05-.63zm2.5 0c0 .94-.2 1.82-.54 2.64l1.51 1.51C20.63 14.91 21 13.5 21 12c0-4.28-2.99-7.86-7-8.77v2.06c2.89.86 5 3.54 5 6.71zM4.27 3L3 4.27 7.73 9H3v6h4l5 5v-6.73l4.25 4.25c-.67.52-1.42.93-2.25 1.18v2.06c1.38-.31 2.63-.95 3.69-1.81L19.73 21 21 19.73l-9-9L4.27 3zM12 4L9.91 6.09 12 8.18V4z"/>';
      } else {
        muteIconSvg.innerHTML = '<path d="M3 9v6h4l5 5V4L7 9H3zm13.5 3c0-1.77-1.02-3.29-2.5-4.03v8.05c1.48-.73 2.5-2.25 2.5-4.02zM14 3.23v2.06c2.89.86 5 3.54 5 6.71s-2.11 5.85-5 6.71v2.06c4.01-.91 7-4.49 7-8.77s-2.99-7.86-7-8.77z"/>';
      }
    });

    shareBtn.addEventListener('click', () => {
      navigator.clipboard.writeText(window.location.href);
      toastMsg.classList.add('show');
      setTimeout(() => {
        toastMsg.classList.remove('show');
      }, 2000);
    });

    fullscreenBtn.addEventListener('click', () => {
      if (!document.fullscreenElement) {
        modalContainer.requestFullscreen().catch(() => {});
      } else {
        document.exitFullscreen().catch(() => {});
      }
    });

    let isScrolling = false;
    window.addEventListener('wheel', (e) => {
      if (!videoModal.classList.contains('active')) return;
      if (isScrolling) return;
      isScrolling = true;
      setTimeout(() => { isScrolling = false; }, 400);

      if (e.deltaY > 0) {
        navigateVideo(1);
      } else {
        navigateVideo(-1);
      }
    }, { passive: true });

    window.addEventListener('keydown', (e) => {
      if (!videoModal.classList.contains('active')) return;
      if (e.key === 'ArrowDown' || e.key === 'ArrowRight') {
        e.preventDefault();
        navigateVideo(1);
      } else if (e.key === 'ArrowUp' || e.key === 'ArrowLeft') {
        e.preventDefault();
        navigateVideo(-1);
      } else if (e.key === 'Escape') {
        closeVideo();
      } else if (e.key === ' ') {
        e.preventDefault();
        togglePlayPause();
      }
    });

    function navigateVideo(direction) {
      updateVisibleCards();
      if (visibleCards.length === 0) return;
      currentCardIndex = (currentCardIndex + direction + visibleCards.length) % visibleCards.length;
      loadVideoFromCard(visibleCards[currentCardIndex]);
    }

    let touchStartY = 0;
    videoModal.addEventListener('touchstart', (e) => {
      touchStartY = e.touches[0].clientY;
    }, { passive: true });

    videoModal.addEventListener('touchend', (e) => {
      const touchEndY = e.changedTouches[0].clientY;
      const diff = touchStartY - touchEndY;
      if (Math.abs(diff) > 50) {
        if (diff > 0) {
          navigateVideo(1);
        } else {
          navigateVideo(-1);
        }
      }
    }, { passive: true });
  </script>
</body>
</html>
