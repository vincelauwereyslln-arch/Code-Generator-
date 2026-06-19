<!DOCTYPE html>
<html lang="nl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover" />
  <meta name="apple-mobile-web-app-capable" content="yes" />
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent" />
  <meta name="apple-mobile-web-app-title" content="Codegen" />
  <meta name="theme-color" content="#0f0f13" />
  <title>Code Generator</title>

  <!-- PWA manifest inline via JS -->
  <script>
    const manifest = {
      name: "Code Generator",
      short_name: "Codegen",
      start_url: ".",
      display: "standalone",
      background_color: "#0f0f13",
      theme_color: "#0f0f13",
      icons: [{
        src: "data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 512 512'><rect width='512' height='512' rx='100' fill='%230f0f13'/><text x='256' y='340' font-size='260' text-anchor='middle' fill='%236c63ff' font-family='monospace' font-weight='bold'>4</text></svg>",
        sizes: "512x512",
        type: "image/svg+xml"
      }]
    };
    const blob = new Blob([JSON.stringify(manifest)], {type: 'application/json'});
    const url = URL.createObjectURL(blob);
    const link = document.createElement('link');
    link.rel = 'manifest';
    link.href = url;
    document.head.appendChild(link);
  </script>

  <!-- Apple touch icon (purple square with "4") -->
  <link rel="apple-touch-icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 512 512'><rect width='512' height='512' rx='100' fill='%230f0f13'/><text x='256' y='340' font-size='260' text-anchor='middle' fill='%236c63ff' font-family='monospace' font-weight='bold'>4</text></svg>" />

  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: #0f0f13;
      color: #e8e8ff;
      font-family: 'Courier New', monospace;
      min-height: 100vh;
      min-height: 100dvh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: env(safe-area-inset-top, 20px) 24px env(safe-area-inset-bottom, 20px);
      user-select: none;
      -webkit-user-select: none;
    }

    .label {
      color: #505070;
      font-size: 10px;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      margin-bottom: 44px;
    }

    /* Digit display */
    .digits {
      display: flex;
      gap: 12px;
      margin-bottom: 52px;
    }

    .digit {
      width: 68px;
      height: 90px;
      background: #16161f;
      border: 1px solid #222233;
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 44px;
      font-weight: 700;
      color: #c8c8ff;
      transition: border-color 0.1s, color 0.1s, transform 0.1s;
      box-shadow: 0 8px 24px rgba(0,0,0,0.5);
    }

    .digit.rolling {
      border-color: #6c63ff;
      color: #9a91ff;
      transform: scale(1.04);
    }

    /* Mode chips */
    .modes {
      display: flex;
      gap: 8px;
      margin-bottom: 32px;
    }

    .chip {
      background: transparent;
      border: 1px solid #222233;
      color: #505070;
      border-radius: 20px;
      padding: 7px 16px;
      font-size: 11px;
      font-family: 'Courier New', monospace;
      letter-spacing: 0.08em;
      cursor: pointer;
      transition: all 0.15s;
      -webkit-tap-highlight-color: transparent;
    }

    .chip.active {
      border-color: #6c63ff;
      color: #a89dff;
      background: rgba(108,99,255,0.12);
    }

    /* Generate button */
    .btn-generate {
      background: #6c63ff;
      color: #fff;
      border: none;
      border-radius: 14px;
      padding: 18px 48px;
      font-size: 13px;
      font-weight: 700;
      font-family: 'Courier New', monospace;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      cursor: pointer;
      transition: background 0.15s, transform 0.1s;
      -webkit-tap-highlight-color: transparent;
      box-shadow: 0 4px 20px rgba(108,99,255,0.4);
      margin-bottom: 16px;
    }

    .btn-generate:active {
      transform: scale(0.97);
      background: #5a52dd;
    }

    .btn-generate:disabled {
      opacity: 0.5;
    }

    /* Copy row */
    .copy-row {
      height: 36px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .btn-copy {
      background: none;
      border: none;
      color: #404060;
      font-family: 'Courier New', monospace;
      font-size: 12px;
      letter-spacing: 0.1em;
      cursor: pointer;
      padding: 8px 16px;
      border-radius: 8px;
      transition: color 0.15s;
      -webkit-tap-highlight-color: transparent;
    }

    .btn-copy.copied {
      color: #6c63ff;
    }

    /* History */
    .history {
      margin-top: 40px;
      width: 100%;
      max-width: 320px;
    }

    .history-label {
      color: #2a2a42;
      font-size: 9px;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      text-align: center;
      margin-bottom: 8px;
    }

    .history-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 10px 0;
      border-top: 1px solid #16161f;
    }

    .history-code {
      color: #404060;
      font-size: 14px;
      font-weight: 700;
      letter-spacing: 0.25em;
    }

    .history-copy {
      background: none;
      border: none;
      color: #303050;
      font-family: 'Courier New', monospace;
      font-size: 11px;
      cursor: pointer;
      padding: 4px 8px;
      -webkit-tap-highlight-color: transparent;
      transition: color 0.15s;
    }

    .history-copy.copied { color: #6c63ff; }

    /* Install hint (only shows before installed) */
    .install-hint {
      position: fixed;
      bottom: calc(env(safe-area-inset-bottom, 16px) + 16px);
      left: 50%;
      transform: translateX(-50%);
      background: #1a1a28;
      border: 1px solid #2a2a42;
      border-radius: 12px;
      padding: 12px 20px;
      font-size: 11px;
      color: #505075;
      letter-spacing: 0.05em;
      text-align: center;
      line-height: 1.5;
      width: calc(100% - 48px);
      max-width: 300px;
      pointer-events: none;
    }

    .install-hint span { color: #6c63ff; }

    @media (display-mode: standalone) {
      .install-hint { display: none; }
    }
  </style>
</head>
<body>

  <div class="label">Code Generator</div>

  <div class="digits" id="digits">
    <div class="digit">—</div>
    <div class="digit">—</div>
    <div class="digit">—</div>
    <div class="digit">—</div>
  </div>

  <div class="modes" id="modes">
    <button class="chip active" data-mode="nums">0–9</button>
    <button class="chip" data-mode="alpha">A–Z</button>
    <button class="chip" data-mode="mixed">A–Z 0–9</button>
  </div>

  <button class="btn-generate" id="btnGenerate">Genereer</button>

  <div class="copy-row">
    <button class="btn-copy" id="btnCopy" style="display:none">Kopieer code</button>
  </div>

  <div class="history" id="history" style="display:none">
    <div class="history-label">Recent</div>
    <div id="historyList"></div>
  </div>

  <div class="install-hint">
    Tik op <span>Deel ↑</span> dan <span>"Zet op beginscherm"</span><br>om als app te installeren
  </div>

  <script>
    const digitEls = document.querySelectorAll('.digit');
    const btnGenerate = document.getElementById('btnGenerate');
    const btnCopy = document.getElementById('btnCopy');
    const historyEl = document.getElementById('history');
    const historyList = document.getElementById('historyList');
    const modeEls = document.querySelectorAll('.chip');

    let mode = 'nums';
    let currentCode = null;
    let animating = false;
    let recentCodes = [];

    const CHARS = {
      nums: '0123456789',
      alpha: 'ABCDEFGHIJKLMNOPQRSTUVWXYZ',
      mixed: 'ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789'
    };

    function randChar() {
      const s = CHARS[mode];
      return s[Math.floor(Math.random() * s.length)];
    }

    function setDigits(arr) {
      digitEls.forEach((el, i) => el.textContent = arr[i]);
    }

    function setRolling(on) {
      digitEls.forEach(el => el.classList.toggle('rolling', on));
    }

    function generate() {
      if (animating) return;
      animating = true;
      btnGenerate.disabled = true;
      btnCopy.style.display = 'none';
      setRolling(true);

      let ticks = 0;
      const total = 16;
      const iv = setInterval(() => {
        setDigits([randChar(), randChar(), randChar(), randChar()]);
        ticks++;
        if (ticks >= total) {
          clearInterval(iv);
          const final = [randChar(), randChar(), randChar(), randChar()];
          setDigits(final);
          setRolling(false);
          currentCode = final.join('');
          addToHistory(currentCode);
          btnCopy.style.display = 'block';
          btnCopy.textContent = 'Kopieer code';
          btnCopy.classList.remove('copied');
          animating = false;
          btnGenerate.disabled = false;
          // haptic feedback on iOS
          if (navigator.vibrate) navigator.vibrate(10);
        }
      }, 55);
    }

    function copyText(text, el, label) {
      navigator.clipboard.writeText(text).catch(() => {
        // fallback
        const ta = document.createElement('textarea');
        ta.value = text;
        ta.style.position = 'fixed';
        ta.style.opacity = '0';
        document.body.appendChild(ta);
        ta.select();
        document.execCommand('copy');
        document.body.removeChild(ta);
      });
      el.textContent = '✓ Gekopieerd';
      el.classList.add('copied');
      setTimeout(() => {
        el.textContent = label;
        el.classList.remove('copied');
      }, 1500);
    }

    function addToHistory(code) {
      recentCodes = [code, ...recentCodes.filter(c => c !== code)].slice(0, 5);
      renderHistory();
    }

    function renderHistory() {
      if (recentCodes.length === 0) { historyEl.style.display = 'none'; return; }
      historyEl.style.display = 'block';
      historyList.innerHTML = recentCodes.map(code => `
        <div class="history-item">
          <span class="history-code">${code.split('').join('  ')}</span>
          <button class="history-copy" data-code="${code}">kopieer</button>
        </div>
      `).join('');
    }

    // Events
    btnGenerate.addEventListener('click', generate);

    btnCopy.addEventListener('click', () => {
      if (currentCode) copyText(currentCode, btnCopy, 'Kopieer code');
    });

    historyList.addEventListener('click', e => {
      const btn = e.target.closest('.history-copy');
      if (btn) copyText(btn.dataset.code, btn, 'kopieer');
    });

    modeEls.forEach(chip => {
      chip.addEventListener('click', () => {
        mode = chip.dataset.mode;
        modeEls.forEach(c => c.classList.remove('active'));
        chip.classList.add('active');
      });
    });

    // Service Worker for offline support
    if ('serviceWorker' in navigator) {
      const swCode = `
        self.addEventListener('install', e => self.skipWaiting());
        self.addEventListener('fetch', e => e.respondWith(fetch(e.request).catch(() => new Response(''))));
      `;
      const swBlob = new Blob([swCode], {type: 'application/javascript'});
      const swUrl = URL.createObjectURL(swBlob);
      navigator.serviceWorker.register(swUrl).catch(() => {});
    }
  </script>
</body>
</html>
