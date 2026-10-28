<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>TAB SỰ KIỆN | Trang chủ</title>
  <style>
    /* ═══════════════════════════════════════════════════════
       1. FONT & RESET
       ═══════════════════════════════════════════════════════ */
    @font-face {
      font-family: "GFF-Latin-Bold";
      src: url("https://dl.dir.freefiremobile.com/common/web_event/common/fonts/website/GFFLatinW05-Bold.woff2") format("woff2"),
           url("https://dl.dir.freefiremobile.com/common/web_event/common/fonts/website/GFFLatinW05-Bold.woff") format("woff");
      font-weight: 700; font-style: normal; font-display: swap;
    }

    :root {
      --ui-alpha: 1;
      --body-bg: url('https://cdn.wildflamestudio.com/common/web_event/official2.ff.garena.all/img/20228/b2b0012af7e3bfcdc90cd8744065e8ab.jpg');
    }
    * { margin: 0; padding: 0; box-sizing: border-box; }
    html { -webkit-text-size-adjust: 100%; -webkit-tap-highlight-color: transparent; }
    html, body { width: 100%; min-height: 100%; }

    /* ═══════════════════════════════════════════════════════
       2. BODY & BACKGROUND
       ═══════════════════════════════════════════════════════ */
    body {
      --pt: max(clamp(6px, 1.5vmin, 24px), env(safe-area-inset-top));
      --pb: max(clamp(6px, 1.5vmin, 24px), env(safe-area-inset-bottom));
      --pl: max(clamp(6px, 1.5vmin, 24px), env(safe-area-inset-left));
      --pr: max(clamp(6px, 1.5vmin, 24px), env(safe-area-inset-right));
      font-family: "GFF-Latin-Bold", system-ui, -apple-system, 'Segoe UI', Roboto, sans-serif;
      background: #0a0f1e; color: #fff;
      min-height: 100vh; min-height: 100dvh;
      display: flex; padding: var(--pt) var(--pr) var(--pb) var(--pl);
      overflow-x: hidden;
    }
    body::before {
      content: ""; position: fixed; inset: 0; z-index: -1; pointer-events: none;
      background-image:
        radial-gradient(circle at 20% 30%, rgba(10,20,40,.45) 0%, rgba(0,0,0,.75) 100%),
        var(--body-bg);
      background-size: cover; background-position: center; background-repeat: no-repeat;
    }

    /* ═══════════════════════════════════════════════════════
       3. LAYOUT
       ═══════════════════════════════════════════════════════ */
    .page-wrapper { margin: auto; width: 100%; display: flex; justify-content: center; }
    .container {
      position: relative;
      width: min(100%, calc((100dvh - var(--pt) - var(--pb)) * 16 / 9), 1600px);
      aspect-ratio: 16 / 9;
      background: rgba(10, 15, 30, calc(0.3 * var(--ui-alpha, 1)));
      -webkit-backdrop-filter: blur(calc(10px * var(--ui-alpha, 1)));
      backdrop-filter: blur(calc(10px * var(--ui-alpha, 1)));
      border-radius: clamp(16px, 2.5vmin, 48px);
      padding: clamp(14px, 2.5vmin, 40px) clamp(16px, 3vmin, 60px);
      border: 1px solid rgba(255, 255, 255, calc(0.1 * var(--ui-alpha, 1)));
      box-shadow: 0 30px 50px rgba(0, 0, 0, calc(0.6 * var(--ui-alpha, 1)));
      display: flex; flex-direction: column; align-items: center; justify-content: space-between;
      gap: clamp(10px, 2vmin, 28px);
      animation: fadeUp .5s cubic-bezier(.2,.9,.3,1);
      overflow: hidden;
    }
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px) scale(.98); }
      to   { opacity: 1; transform: translateY(0) scale(1); }
    }
    @media (min-aspect-ratio: 1/1) and (max-aspect-ratio: 16/10) {
      .container { width: min(100%, calc((100dvh - var(--pt) - var(--pb)) * 4 / 3), 1400px); aspect-ratio: 4 / 3; }
    }
    @media (max-height: 560px) and (orientation: landscape) {
      .container { aspect-ratio: auto; width: min(100%, 1600px); height: calc(100dvh - var(--pt) - var(--pb)); }
    }
    @media (max-aspect-ratio: 1/1) {
      .container { aspect-ratio: auto; width: min(100%, 720px); height: auto; }
    }
    @media (min-width: 700px) and (max-aspect-ratio: 1/1) {
      .container { width: min(100%, 960px); }
    }
    @media (min-width: 2000px) and (min-aspect-ratio: 16/10) {
      .container { max-width: 1800px; }
    }

    /* ═══════════════════════════════════════════════════════
       4. BLOCK WRAPPER + LABELS
       ═══════════════════════════════════════════════════════ */
    .block-wrap {
      position: relative; width: 100%;
      display: flex; flex-direction: column;
      padding-top: clamp(22px, 3.2vmin, 48px);
    }
    .header-wrap, .tab-wrap { flex-shrink: 0; }
    .block-wrap.header-wrap { padding-top: clamp(44px, 6vmin, 88px); }
    .content-wrap { flex: 1; min-height: 0; }
    .content-wrap > .content { flex: 1; min-height: 0; }

    .block-label {
      position: absolute; top: 0; left: 0; z-index: 5;
      text-align: left; padding-left: clamp(6px, 1vmin, 18px);
      font-family: "GFF-Latin-Bold", sans-serif;
      font-size: clamp(.72rem, 2.2vmin, 1.85rem);
      letter-spacing: clamp(1.5px, .85vmin, 8px);
      text-transform: uppercase; line-height: 1; white-space: nowrap;
      background: linear-gradient(135deg, #fff 0%, #ffe28a 40%, #ffb347 80%, #ffd966 100%);
      -webkit-background-clip: text; background-clip: text; color: transparent;
      filter: drop-shadow(0 4px 14px rgba(255,180,0,.55)) drop-shadow(0 2px 4px rgba(0,0,0,.85));
      pointer-events: none; transition: opacity .25s ease;
    }
    .block-label--center { left: 0; right: 0; text-align: center; padding-left: 0; }

    .block-labels {
      position: absolute; top: 0; left: 0; right: 0; z-index: 5;
      padding: 0 clamp(6px, 1vmin, 18px);
      display: flex; flex-direction: column; align-items: flex-start;
      gap: clamp(3px, .6vmin, 8px);
      pointer-events: none; text-align: left;
    }
    .block-labels .block-label { position: relative; top: auto; left: auto; padding-left: 0; }

    .block-label--tag {
      width: 100%; text-align: center; white-space: normal;
      font-size: clamp(.85rem, 2.4vmin, 1.65rem);
      letter-spacing: clamp(1.2px, .9vmin, 6px);
      background: linear-gradient(115deg,
        var(--tag-shine, #fff) 0%,
        color-mix(in srgb, var(--tag-main, #ff3a3a) 20%, var(--tag-shine, #fff)) 8%,
        var(--tag-main, #ff3a3a) 18%,
        color-mix(in srgb, var(--tag-main, #ff3a3a) 50%, var(--tag-shine, #fff)) 26%,
        var(--tag-shine, #fff) 34%,
        color-mix(in srgb, var(--tag-main, #ff3a3a) 80%, #000) 44%,
        var(--tag-main, #ff3a3a) 52%,
        var(--tag-shine, #fff) 60%,
        color-mix(in srgb, var(--tag-main, #ff3a3a) 60%, var(--tag-shine, #fff)) 68%,
        color-mix(in srgb, var(--tag-main, #ff3a3a) 85%, #000) 76%,
        color-mix(in srgb, var(--tag-main, #ff3a3a) 30%, var(--tag-shine, #fff)) 86%,
        var(--tag-shine, #fff) 100%);
      background-size: 200% 100%;
      -webkit-background-clip: text; background-clip: text; color: transparent;
      filter: drop-shadow(0 3px 14px rgba(255,40,40,.55)) drop-shadow(0 0 6px rgba(255,255,255,.35)) drop-shadow(0 2px 4px rgba(0,0,0,.9));
      animation: tagShift 6s ease-in-out infinite alternate;
    }
    @keyframes tagShift { from { background-position: 0% 50%; } to { background-position: 100% 50%; } }

    .block-label[data-banner-label] {
      --banner-main: #ffb347;
      --banner-shine: #ffffff;
      background: linear-gradient(135deg,
        var(--banner-shine) 0%,
        color-mix(in srgb, var(--banner-main) 40%, var(--banner-shine)) 25%,
        var(--banner-main) 55%,
        color-mix(in srgb, var(--banner-main) 60%, var(--banner-shine)) 85%,
        var(--banner-shine) 100%);
      background-size: 200% 100%;
      -webkit-background-clip: text; background-clip: text; color: transparent;
      filter: drop-shadow(0 4px 14px color-mix(in srgb, var(--banner-main) 55%, transparent))
              drop-shadow(0 2px 4px rgba(0,0,0,.85));
      animation: tagShift 6s ease-in-out infinite alternate;
    }

    /* ═══════════════════════════════════════════════════════
       5. GLASS PANEL
       ═══════════════════════════════════════════════════════ */
    .glass-panel {
      position: relative;
      --cut: clamp(12px, 2.5vmin, 22px);
      --border-w: 1.5px;
      width: 100%;
      padding: clamp(12px, 2.5vmin, 24px) !important;
      background: linear-gradient(135deg,
        rgba(255,255,255,calc(.70*var(--ui-alpha,1))) 0%,
        rgba(255,255,255,calc(.15*var(--ui-alpha,1))) 25%,
        rgba(255,255,255,calc(.05*var(--ui-alpha,1))) 50%,
        rgba(255,255,255,calc(.15*var(--ui-alpha,1))) 75%,
        rgba(255,255,255,calc(.60*var(--ui-alpha,1))) 100%);
      clip-path: polygon(var(--cut) 0, 100% 0, 100% calc(100% - var(--cut)), calc(100% - var(--cut)) 100%, 0 100%, 0 var(--cut));
      filter: drop-shadow(0 calc(10px*var(--ui-alpha,1)) calc(20px*var(--ui-alpha,1)) rgba(0,0,0,calc(.4*var(--ui-alpha,1))));
      border: none !important; box-shadow: none !important; border-radius: 0 !important;
    }
    .glass-panel::before {
      content: ""; position: absolute; inset: var(--border-w); z-index: -1;
      background:
        radial-gradient(ellipse 120% 60% at 50% -10%, rgba(180,210,255,calc(.18*var(--ui-alpha,1))) 0%, transparent 65%),
        radial-gradient(ellipse 100% 60% at 50% 110%, rgba(255,200,100,calc(.08*var(--ui-alpha,1))) 0%, transparent 60%),
        linear-gradient(180deg, rgba(15,22,40,calc(.35*var(--ui-alpha,1))) 0%, rgba(5,10,20,calc(.55*var(--ui-alpha,1))) 100%);
      -webkit-backdrop-filter: blur(calc(22px*var(--ui-alpha,1))) saturate(calc(1 + .8*var(--ui-alpha,1))) brightness(calc(1 + .06*var(--ui-alpha,1)));
      backdrop-filter: blur(calc(22px*var(--ui-alpha,1))) saturate(calc(1 + .8*var(--ui-alpha,1))) brightness(calc(1 + .06*var(--ui-alpha,1)));
      clip-path: polygon(calc(var(--cut) - var(--border-w)*2) 0, 100% 0, 100% calc(100% - var(--cut) + var(--border-w)*2), calc(100% - var(--cut) + var(--border-w)*2) 100%, 0 100%, 0 calc(var(--cut) - var(--border-w)*2));
    }

    /* ═══════════════════════════════════════════════════════
       6. EVENT NAV
       ═══════════════════════════════════════════════════════ */
    .event-nav {
      position: relative; z-index: 20;
      display: flex; align-items: center; justify-content: center;
      gap: clamp(6px, 1.2vmin, 14px);
      width: 100%; flex-wrap: wrap; flex-shrink: 0;
      margin-top: clamp(40px, 8vmin, 70px);
      margin-bottom: clamp(10px, 2vmin, 20px);
    }
    .event-btn {
      --cut: 14px; --border-w: 1.5px;
      --btn-vi: max(0.45, var(--ui-alpha, 1));
      position: relative; isolation: isolate;
      display: inline-flex; align-items: center; justify-content: center;
      font-family: "GFF-Latin-Bold", sans-serif;
      font-size: clamp(.72rem, 1.85vmin, 1.2rem);
      letter-spacing: clamp(1px, .4vmin, 2px);
      text-transform: uppercase; color: #fff;
      text-shadow: 0 1px 3px rgba(0,0,0,.7), 0 0 12px rgba(255,255,255,.2);
      padding: clamp(10px, 1.6vmin, 18px) clamp(22px, 3.2vmin, 46px);
      cursor: pointer; white-space: nowrap;
      border: none; outline: none;
      background: linear-gradient(135deg,
        rgba(255,255,255,calc(.75*var(--btn-vi))) 0%,
        rgba(255,255,255,calc(.25*var(--btn-vi))) 25%,
        rgba(255,255,255,calc(.15*var(--btn-vi))) 50%,
        rgba(255,255,255,calc(.25*var(--btn-vi))) 75%,
        rgba(255,255,255,calc(.70*var(--btn-vi))) 100%);
      clip-path: polygon(var(--cut) 0, 100% 0, 100% calc(100% - var(--cut)), calc(100% - var(--cut)) 100%, 0 100%, 0 var(--cut));
      transition: transform .35s cubic-bezier(.2,.9,.3,1), filter .35s ease, text-shadow .35s ease, background .35s ease;
      filter: drop-shadow(0 4px 12px rgba(0,0,0,.4));
    }
    .event-btn::before {
      content: ""; position: absolute; inset: var(--border-w); z-index: 1;
      pointer-events: none;
      background:
        radial-gradient(ellipse 130% 70% at 50% -25%, rgba(255,255,255,calc(.5*var(--btn-vi))) 0%, rgba(255,255,255,calc(.08*var(--btn-vi))) 45%, transparent 70%),
        radial-gradient(ellipse 100% 60% at 50% 130%, rgba(255,255,255,calc(.2*var(--btn-vi))) 0%, transparent 60%),
        linear-gradient(135deg, rgba(255,255,255,calc(.12*var(--btn-vi))) 0%, rgba(255,255,255,calc(.02*var(--btn-vi))) 50%, rgba(255,255,255,calc(.08*var(--btn-vi))) 100%);
      -webkit-backdrop-filter: blur(calc(14px*var(--ui-alpha,1))) saturate(calc(1 + .8*var(--ui-alpha,1)));
      backdrop-filter: blur(calc(14px*var(--ui-alpha,1))) saturate(calc(1 + .8*var(--ui-alpha,1)));
      clip-path: polygon(calc(var(--cut) - var(--border-w)*2) 0, 100% 0, 100% calc(100% - var(--cut) + var(--border-w)*2), calc(100% - var(--cut) + var(--border-w)*2) 100%, 0 100%, 0 calc(var(--cut) - var(--border-w)*2));
    }
    .event-btn::after {
      content: ""; position: absolute; inset: 0; z-index: 2; pointer-events: none;
      background: linear-gradient(105deg, transparent 30%, rgba(255,255,255,.3) 48%, rgba(255,255,255,.5) 50%, rgba(255,255,255,.3) 52%, transparent 70%);
      transform: translateX(-120%);
      transition: transform .9s cubic-bezier(.3,.8,.3,1);
      clip-path: polygon(var(--cut) 0, 100% 0, 100% calc(100% - var(--cut)), calc(100% - var(--cut)) 100%, 0 100%, 0 var(--cut));
    }
    .event-btn:hover::after { transform: translateX(120%); }
    .event-btn span { position: relative; z-index: 3; pointer-events: none; }
    .event-btn:hover {
      transform: translateY(-2px);
      filter: drop-shadow(0 6px 20px rgba(0,0,0,.5)) drop-shadow(0 0 8px rgba(255,255,255,.3));
      text-shadow: 0 1px 3px rgba(0,0,0,.7), 0 0 16px rgba(255,255,255,.45);
    }

    .event-btn.active {
      --btn-main: #ffd23a;
      --btn-shine: #fff8e0;
      background: linear-gradient(135deg,
        var(--btn-shine) 0%,
        color-mix(in srgb, var(--btn-main) 40%, var(--btn-shine)) 25%,
        color-mix(in srgb, var(--btn-main) 70%, var(--btn-shine)) 50%,
        color-mix(in srgb, var(--btn-main) 40%, var(--btn-shine)) 75%,
        var(--btn-shine) 100%);
      color: var(--btn-shine);
      text-shadow: 0 1px 4px rgba(0,0,0,.55), 0 0 16px color-mix(in srgb, var(--btn-main) 70%, transparent);
      filter: drop-shadow(0 4px 16px color-mix(in srgb, var(--btn-main) 55%, transparent))
              drop-shadow(0 0 6px color-mix(in srgb, var(--btn-shine) 60%, transparent));
    }
    .event-btn.active::before {
      background:
        radial-gradient(ellipse 130% 70% at 50% -25%, color-mix(in srgb, var(--btn-shine) 55%, transparent) 0%, color-mix(in srgb, var(--btn-shine) 10%, transparent) 45%, transparent 70%),
        radial-gradient(ellipse 100% 60% at 50% 130%, color-mix(in srgb, var(--btn-shine) 25%, transparent) 0%, transparent 60%),
        linear-gradient(135deg, color-mix(in srgb, var(--btn-shine) 15%, transparent) 0%, transparent 50%, color-mix(in srgb, var(--btn-shine) 10%, transparent) 100%);
    }
    .event-btn:active { transform: translateY(0) scale(.97); }

    #page-banner .event-btn.active {
      --btn-main: #ff2d2d;
      --btn-shine: #ffffff;
      background:
        radial-gradient(ellipse 65% 85% at 15% 20%, color-mix(in srgb, var(--btn-shine) 70%, transparent) 0%, transparent 55%),
        radial-gradient(ellipse 55% 75% at 85% 78%, color-mix(in srgb, var(--btn-shine) 60%, transparent) 0%, transparent 55%),
        radial-gradient(ellipse 70% 55% at 50% 10%, color-mix(in srgb, var(--btn-main) 40%, var(--btn-shine)) 0%, transparent 60%),
        radial-gradient(ellipse 60% 55% at 30% 92%, color-mix(in srgb, var(--btn-main) 30%, var(--btn-shine)) 0%, transparent 60%),
        radial-gradient(ellipse 80% 70% at 70% 50%, color-mix(in srgb, var(--btn-main) 55%, transparent) 0%, transparent 60%),
        linear-gradient(135deg,
          color-mix(in srgb, var(--btn-main) 90%, #000) 0%,
          var(--btn-main) 30%,
          color-mix(in srgb, var(--btn-main) 80%, #000) 55%,
          color-mix(in srgb, var(--btn-main) 90%, #fff) 78%,
          color-mix(in srgb, var(--btn-main) 75%, #000) 100%);
      color: #fff;
      text-shadow: 0 1px 4px rgba(0,0,0,.9), 0 0 14px color-mix(in srgb, var(--btn-main) 75%, transparent), 0 0 4px rgba(255,255,255,.5);
      filter: drop-shadow(0 4px 18px color-mix(in srgb, var(--btn-main) 60%, transparent))
              drop-shadow(0 0 12px color-mix(in srgb, var(--btn-shine) 40%, transparent));
    }
    #page-banner .event-btn.active::before {
      background:
        radial-gradient(ellipse 130% 70% at 50% -25%, color-mix(in srgb, var(--btn-shine) 40%, transparent) 0%, color-mix(in srgb, var(--btn-shine) 10%, transparent) 45%, transparent 70%),
        radial-gradient(ellipse 100% 60% at 50% 130%, color-mix(in srgb, var(--btn-main) 20%, transparent) 0%, transparent 60%),
        linear-gradient(135deg, color-mix(in srgb, var(--btn-shine) 12%, transparent) 0%, transparent 50%, color-mix(in srgb, var(--btn-shine) 10%, transparent) 100%);
    }
    @media (prefers-reduced-motion: no-preference) {
      #page-banner .event-btn.active {
        background-size: 200% 200%, 200% 200%, 200% 200%, 200% 200%, 200% 200%, 100% 100%;
        animation: redStainPulse 5s ease-in-out infinite alternate;
      }
      @keyframes redStainPulse {
        0%   { background-position: 0% 0%, 100% 100%, 50% 0%, 0% 100%, 60% 50%, 0% 0%; }
        50%  { background-position: 30% 20%, 70% 80%, 45% 15%, 15% 85%, 55% 55%, 0% 0%; }
        100% { background-position: 60% 40%, 40% 60%, 40% 30%, 30% 70%, 50% 60%, 0% 0%; }
      }
    }
    @media (max-width: 480px) {
      .event-btn { --cut: 10px; --border-w: 1.25px; padding: 8px 16px; font-size: clamp(.62rem, 2.6vmin, .85rem); }
    }

    /* ═══════════════════════════════════════════════════════
       7. HEADER / TAB
       ═══════════════════════════════════════════════════════ */
    .header {
      display: flex; flex-direction: column; align-items: center; justify-content: center;
      text-align: center; gap: clamp(4px, .8vmin, 10px); flex-shrink: 0;
    }
    .logo-img {
      height: clamp(48px, 9vmin, 120px); min-width: 100px;
      width: auto; max-width: 60%;
      object-fit: contain; flex-shrink: 0;
      filter: drop-shadow(0 10px 18px rgba(0,0,0,.7)) brightness(1.05);
      transition: transform .3s ease;
      pointer-events: none;
    }
    .logo-img:hover { transform: scale(1.03); }

    .tab-section {
      display: flex; flex-direction: column; align-items: center; justify-content: center;
      gap: clamp(4px, .8vmin, 12px); width: 100%; flex-shrink: 0;
    }
    .tab-wrapper { display: flex; justify-content: center; align-items: center; width: 100%; }
    .tab-image {
      max-width: 100%; height: auto;
      max-height: clamp(60px, 12vmin, 160px);
      min-width: 200px; min-height: 60px;
      object-fit: contain;
      filter: drop-shadow(0 8px 18px rgba(0,0,0,.5));
      transition: transform .25s ease, filter .25s ease;
      pointer-events: none;
    }

    /* ═══════════════════════════════════════════════════════
       8. CONTENT
       ═══════════════════════════════════════════════════════ */
    .content {
      display: flex; flex-direction: column; align-items: center; justify-content: center;
      text-align: center; gap: clamp(6px, 1.6vmin, 24px);
      width: 100%; flex: 1; min-height: 0;
    }
    .text-image-box {
      width: 100%; max-width: min(100%, 980px);
      flex: 1 1 auto; min-height: 100px; max-height: 100%;
      border-radius: clamp(12px, 1.8vmin, 28px);
      background-color: #0d1424;
      background-size: cover; background-position: center; background-repeat: no-repeat;
      display: flex; flex-direction: column; align-items: center; justify-content: center;
      text-align: center;
      padding: clamp(12px, 3vmin, 44px) clamp(16px, 3vmin, 50px);
      position: relative; overflow: hidden; isolation: isolate;
      border: 1px solid rgba(255,215,0,.25);
      box-shadow: 0 20px 40px -10px rgba(0,0,0,.7), 0 0 0 1px rgba(255,255,255,.08) inset;
      margin: 0 auto;
      transition: background-image .35s ease;
      -webkit-user-select: none; user-select: none;
      -webkit-touch-callout: none; -webkit-tap-highlight-color: transparent;
    }
    .text-image-box::before {
      content: ""; position: absolute; inset: 0; z-index: -1;
      background: linear-gradient(180deg, rgba(5,10,25,.55) 0%, rgba(0,0,0,.7) 100%);
    }

    /* ═══════════════════════════════════════════════════════
       9. BANNER MODE + CARD
       ═══════════════════════════════════════════════════════ */
    .content.banner-mode {
      justify-content: flex-start; align-items: stretch;
      padding: clamp(8px, 1.5vmin, 18px) !important;
      overflow: hidden;
    }
    .banner-showcase {
      display: flex; flex-direction: column;
      gap: clamp(12px, 2vmin, 20px);
      flex: 1; min-height: 0; width: 100%;
      overflow-y: auto; overflow-x: hidden;
      padding: 6px 8px 6px 6px;
      -webkit-overflow-scrolling: touch;
      scrollbar-width: thin;
      scrollbar-color: rgba(255,215,0,.5) transparent;
    }
    .banner-showcase::-webkit-scrollbar { width: 6px; }
    .banner-showcase::-webkit-scrollbar-track { background: rgba(255,255,255,.04); border-radius: 6px; }
    .banner-showcase::-webkit-scrollbar-thumb {
      background: linear-gradient(180deg, rgba(255,215,0,.6), rgba(255,180,0,.4));
      border-radius: 6px;
    }

    .banner-card {
      --card-cut: clamp(10px, 1.5vmin, 16px);
      position: relative; flex-shrink: 0; width: 100%;
      background:
        radial-gradient(ellipse 130% 60% at 50% 0%, rgba(255,220,120,.08) 0%, transparent 60%),
        linear-gradient(180deg, rgba(255,255,255,.09) 0%, rgba(255,255,255,.03) 100%);
      -webkit-backdrop-filter: blur(16px) saturate(150%);
      backdrop-filter: blur(16px) saturate(150%);
      border: 1px solid rgba(255,215,0,.3);
      clip-path: polygon(0 0, 100% 0, 100% calc(100% - var(--card-cut)), calc(100% - var(--card-cut)) 100%, 0 100%);
      box-shadow: 0 10px 28px rgba(0,0,0,.55), inset 0 0 0 1px rgba(255,255,255,.05);
      display: flex; flex-direction: column; gap: 10px;
      padding: 10px 12px 12px;
      transition: border-color .3s ease, box-shadow .3s ease, transform .3s ease;
    }
    .banner-card:hover {
      border-color: rgba(255,215,0,.6);
      box-shadow: 0 14px 36px rgba(0,0,0,.65), 0 0 22px rgba(255,200,50,.18), inset 0 0 0 1px rgba(255,255,255,.08);
      transform: translateY(-2px);
    }
    .banner-card__label {
      align-self: flex-start;
      display: inline-flex; align-items: center; gap: 6px;
      font-family: "GFF-Latin-Bold", sans-serif;
      font-size: clamp(9px, 1.15vmin, 11px);
      letter-spacing: 1.8px; text-transform: uppercase;
      color: #ffe28a;
      padding: 4px 10px;
      background: rgba(0,0,0,.4);
      border: 1px solid rgba(255,215,0,.45);
      box-shadow: 0 2px 8px rgba(0,0,0,.4), inset 0 0 8px rgba(255,200,50,.08);
      clip-path: polygon(0 0, 100% 0, 100% calc(100% - 6px), calc(100% - 6px) 100%, 0 100%);
      pointer-events: none; user-select: none; white-space: nowrap;
    }
    .banner-card__label::before {
      content: ""; width: 5px; height: 5px; border-radius: 50%;
      background: #ffd23a; box-shadow: 0 0 8px rgba(255,210,58,.9); flex-shrink: 0;
    }
    .banner-card__img {
      display: block; width: 100%; height: auto;
      object-fit: contain; border-radius: 4px;
      background: rgba(0,0,0,.25);
      pointer-events: none;
      transition: opacity .25s ease;
    }
    .banner-card__img.is-loading { opacity: .4; }
    .banner-card__img[data-banner="16-9"]     { aspect-ratio: 16 / 9; }
    .banner-card__img[data-banner="portrait"] { aspect-ratio: 436 / 606; }
    .banner-card__img[data-banner="256"]      { aspect-ratio: 256 / 107; }
    .banner-card__img[data-banner="512"]      { aspect-ratio: 512 / 182; }

    .banner-card--portrait { max-width: min(320px, 65%); margin: 0 auto; align-self: center; }

    .banner-card__view {
      position: absolute; bottom: 14px; right: 14px; z-index: 5;
      display: inline-flex; align-items: center; gap: 5px;
      padding: 4px 10px 4px 8px;
      font-family: "GFF-Latin-Bold", sans-serif;
      font-size: 10px; letter-spacing: 1.6px; line-height: 1; text-transform: uppercase;
      color: #ffe28a;
      background: rgba(0,0,0,.6);
      border: 1px solid rgba(255,215,0,.55);
      clip-path: polygon(7px 0, 100% 0, 100% calc(100% - 7px), calc(100% - 7px) 100%, 0 100%, 0 7px);
      -webkit-backdrop-filter: blur(10px) saturate(140%);
      backdrop-filter: blur(10px) saturate(140%);
      cursor: pointer; outline: none;
      box-shadow: 0 3px 10px rgba(0,0,0,.5), inset 0 0 6px rgba(255,200,50,.1);
      transition: transform .25s ease, background .25s ease, color .25s ease, box-shadow .25s ease;
      -webkit-tap-highlight-color: transparent;
    }
    .banner-card__view:hover, .banner-card__view:focus-visible {
      background: rgba(255,215,0,.92); color: #1a0f00;
      transform: translateY(-1px) scale(1.06);
      box-shadow: 0 6px 18px rgba(255,200,50,.55), inset 0 0 0 1px rgba(255,255,255,.3);
    }
    .banner-card__view:active { transform: translateY(0) scale(.97); }
    .banner-card__view svg { display: block; flex-shrink: 0; stroke: currentColor; fill: none; transition: stroke .25s ease; }

    .footer-note {
      font-size: clamp(.5rem, 1vmin, .95rem);
      color: rgba(255,255,255,.45);
      letter-spacing: clamp(1px, .25vmin, 3px);
      text-transform: uppercase;
      font-family: "GFF-Latin-Bold", sans-serif;
      flex-shrink: 0; text-align: center; white-space: nowrap;
    }

    /* ═══════════════════════════════════════════════════════
       10. LIGHTBOX
       ═══════════════════════════════════════════════════════ */
    .banner-lightbox {
      position: fixed; inset: 0; z-index: 10000;
      display: flex; align-items: center; justify-content: center;
      padding: clamp(16px, 3vmin, 44px);
      background: rgba(0,0,0,.9);
      -webkit-backdrop-filter: blur(12px) saturate(140%);
      backdrop-filter: blur(12px) saturate(140%);
      opacity: 0; visibility: hidden; pointer-events: none;
      transition: opacity .3s ease, visibility .3s ease;
    }
    .banner-lightbox.active { opacity: 1; visibility: visible; pointer-events: auto; }
    .banner-lightbox__close {
      position: absolute; top: 14px; right: 14px;
      width: 34px; height: 34px;
      display: flex; align-items: center; justify-content: center;
      font-family: "GFF-Latin-Bold", sans-serif;
      font-size: 14px; line-height: 1;
      color: #ffe28a;
      background: rgba(255,255,255,.08);
      border: 1px solid rgba(255,215,0,.5);
      clip-path: polygon(0 0, 100% 0, 100% 100%, 9px 100%, 0 calc(100% - 9px));
      -webkit-backdrop-filter: blur(12px); backdrop-filter: blur(12px);
      cursor: pointer; outline: none; z-index: 2;
      transition: background .25s ease, color .25s ease, transform .25s ease;
    }
    .banner-lightbox__close:hover { background: rgba(255,215,0,.92); color: #1a0f00; transform: scale(1.08); }
    .banner-lightbox__close:active { transform: scale(.96); }
    .banner-lightbox__img {
      max-width: 100%;
      max-height: calc(100dvh - 100px);
      object-fit: contain; border-radius: 4px;
      box-shadow: 0 16px 45px rgba(0,0,0,.72), 0 0 0 1px rgba(255,215,0,.25);
      pointer-events: none;
      animation: lightboxImgIn .35s cubic-bezier(.2,.9,.3,1);
    }
    @keyframes lightboxImgIn {
      from { opacity: 0; transform: scale(.92); }
      to   { opacity: 1; transform: scale(1); }
    }

    /* ═══════════════════════════════════════════════════════
       11. MENU LIQUID GLASS
       ═══════════════════════════════════════════════════════ */
    .ff-menu-wrapper {
      position: absolute; top: clamp(10px, 2vmin, 20px); left: clamp(10px, 2vmin, 20px);
      z-index: 100; font-family: "GFF-Latin-Bold", sans-serif;
    }
    .ff-menu-btn {
      position: relative; z-index: 2;
      width: 32px; height: 32px;
      background: rgba(255,255,255,.12);
      -webkit-backdrop-filter: blur(12px) saturate(150%);
      backdrop-filter: blur(12px) saturate(150%);
      border: 1px solid rgba(255,255,255,.28);
      cursor: pointer;
      display: flex; flex-direction: column; align-items: center; justify-content: center;
      gap: 3px;
      clip-path: polygon(0 0, 100% 0, 100% calc(100% - 9px), calc(100% - 9px) 100%, 0 100%);
      transition: transform .3s ease, background .3s ease, box-shadow .3s ease;
      outline: none;
      box-shadow: inset 0 0 8px rgba(255,255,255,.15), 0 3px 10px rgba(0,0,0,.3);
    }
    .ff-menu-btn:hover { background: rgba(255,255,255,.22); box-shadow: inset 0 0 12px rgba(255,255,255,.25), 0 3px 16px rgba(0,0,0,.4); }
    .ff-menu-btn:active { transform: scale(.9); }
    .ff-menu-btn span {
      display: block; width: 14px; height: 1.8px;
      background: rgba(255,255,255,.95); border-radius: 2px;
      box-shadow: 0 0 4px rgba(255,255,255,.5);
      transition: transform .35s cubic-bezier(.34,1.56,.64,1), opacity .25s ease;
    }
    .ff-menu-wrapper.active .ff-menu-btn span:nth-child(1) { transform: translateY(4.8px) rotate(45deg); }
    .ff-menu-wrapper.active .ff-menu-btn span:nth-child(2) { opacity: 0; transform: scaleX(0); }
    .ff-menu-wrapper.active .ff-menu-btn span:nth-child(3) { transform: translateY(-4.8px) rotate(-45deg); }

    .ff-menu-panel {
      position: absolute; top: 0; left: 0; z-index: 1;
      width: min(180px, 65vw);
      background: rgba(15,20,35,.6);
      -webkit-backdrop-filter: blur(24px) saturate(180%);
      backdrop-filter: blur(24px) saturate(180%);
      border: 1px solid rgba(255,255,255,.18);
      clip-path: polygon(0 0, 100% 0, 100% calc(100% - 18px), calc(100% - 18px) 100%, 0 100%);
      padding: 40px 8px 10px;
      opacity: 0; visibility: hidden;
      transform: scale(.85) translate(-8px, -8px);
      transform-origin: top left;
      transition: opacity .35s ease, transform .5s cubic-bezier(.34,1.56,.64,1), visibility .35s;
      box-shadow: inset 0 0 30px rgba(255,255,255,.06), 0 15px 40px rgba(0,0,0,.6);
    }
    .ff-menu-panel::before {
      content: ""; position: absolute; inset: 0; pointer-events: none; z-index: -1;
      background:
        radial-gradient(circle at 0% 0%, rgba(255,255,255,.16) 0%, transparent 60%),
        radial-gradient(circle at 100% 100%, rgba(255,255,255,.05) 0%, transparent 50%);
    }
    .ff-menu-wrapper.active .ff-menu-panel { opacity: 1; visibility: visible; transform: scale(1) translate(0,0); }

    .ff-menu-list { list-style: none; display: flex; flex-direction: column; gap: 5px; }
    .ff-menu-item {
      --cut: 10px;
      position: relative;
      display: flex; align-items: center; justify-content: space-between;
      padding: 9px 12px;
      background: rgba(255,255,255,.03);
      border: none;
      clip-path: polygon(0 0, 100% 0, 100% calc(100% - var(--cut)), calc(100% - var(--cut)) 100%, 0 100%);
      box-shadow: inset 0 0 0 1px rgba(255,255,255,.1);
      cursor: pointer;
      opacity: 0; transform: translateX(-15px);
      transition: opacity .3s ease, transform .4s cubic-bezier(.34,1.56,.64,1), background .25s ease, box-shadow .25s ease;
    }
    .ff-menu-wrapper.active .ff-menu-item { opacity: 1; transform: translateX(0); }
    .ff-menu-wrapper.active .ff-menu-item:nth-child(1) { transition-delay: .12s; }
    .ff-menu-wrapper.active .ff-menu-item:nth-child(2) { transition-delay: .2s; }
    .ff-menu-item:hover { background: rgba(255,255,255,.12); box-shadow: inset 0 0 0 1px rgba(255,255,255,.25); }
    .ff-menu-item.active {
      background: linear-gradient(90deg, rgba(255,255,255,.2) 0%, rgba(255,255,255,.06) 100%);
      box-shadow: inset 0 0 0 1px rgba(255,255,255,.35), inset 3px 0 0 #fff, inset 0 0 12px rgba(255,255,255,.12);
    }
    .ff-menu-item .menu-text {
      font-size: 11px; color: rgba(255,255,255,.85);
      letter-spacing: 2px; font-weight: 700;
    }
    .ff-menu-item.active .menu-text { color: #fff; text-shadow: 0 0 10px rgba(255,255,255,.6); }

    .menu-backdrop {
      position: absolute; inset: 0; z-index: 90;
      background: rgba(0,0,0,.3);
      -webkit-backdrop-filter: blur(2px); backdrop-filter: blur(2px);
      opacity: 0; visibility: hidden; pointer-events: none;
      transition: opacity .35s ease, visibility .35s ease;
      border-radius: inherit;
    }
    .container.menu-active .menu-backdrop { opacity: 1; visibility: visible; pointer-events: auto; }

    .page-section { display: none; }
    .page-section.active { display: flex; }

    /* ═══════════════════════════════════════════════════════
       12. RESPONSIVE
       ═══════════════════════════════════════════════════════ */
    @media (max-aspect-ratio: 1/1) {
      .container { gap: clamp(14px, 2.5vmin, 28px); }
      .event-nav { margin-top: clamp(35px, 6vmin, 55px); margin-bottom: 0; }
      .block-wrap { padding-top: clamp(20px, 3vmin, 34px); }
      .block-wrap.header-wrap { padding-top: clamp(42px, 5.6vmin, 66px); }
      .content-wrap { flex: 0 1 auto; }
      .content { flex: 0 1 auto; gap: clamp(10px, 2vmin, 20px); }
      .text-image-box { flex: 0 1 auto; aspect-ratio: 16 / 9; max-height: none; min-height: 0; width: 100%; }
      .footer-note { white-space: normal; }
      .glass-panel { padding: clamp(12px, 3vmin, 20px) !important; }
      .block-label { font-size: clamp(.7rem, 2.8vmin, 1.15rem); letter-spacing: clamp(1.2px, .7vmin, 4px); }
      .block-label--tag { font-size: clamp(.85rem, 2.8vmin, 1.35rem); letter-spacing: clamp(1px, .6vmin, 3.5px); }
      .banner-showcase { max-height: 60vh; }
      .banner-card--portrait { max-width: min(240px, 60%); }
    }
    @media (max-width: 480px) and (max-aspect-ratio: 1/1) {
      .container { border-radius: 16px; padding: 16px; gap: 12px; }
      .event-nav { margin-top: 35px; }
      .block-wrap { padding-top: 20px; }
      .block-wrap.header-wrap { padding-top: 42px; }
      .logo-img { height: clamp(40px, 9vmin, 70px); max-width: 70%; }
      .tab-image { max-height: clamp(48px, 11vmin, 90px); }
      .text-image-box { aspect-ratio: 4 / 3; }
      .footer-note { font-size: .55rem; letter-spacing: 1px; }
      .block-label { font-size: clamp(.62rem, 3.2vmin, .95rem); letter-spacing: clamp(1px, .6vmin, 3px); padding-left: 4px; }
      .block-label--center { padding-left: 0; }
      .block-label--tag { font-size: clamp(.78rem, 3.4vmin, 1.15rem); letter-spacing: clamp(.8px, .5vmin, 2.5px); }
      .block-labels { padding-left: 4px; gap: 3px; }
      .banner-card--portrait { max-width: 200px; }
      .banner-showcase { max-height: 55vh; gap: 12px; }
      .banner-card { padding: 8px 10px 10px; gap: 8px; }
      .banner-card__view { bottom: 10px; right: 10px; font-size: 9px; padding: 3px 8px 3px 6px; }
      .banner-card__view svg { width: 9px; height: 9px; }
    }
    @media (prefers-reduced-motion: reduce) {
      .container { animation: none; }
      .tab-image, .logo-img, .event-btn, .banner-card, .banner-card__img { transition: none; }
      .tab-image:hover, .logo-img:hover, .event-btn:hover, .banner-card:hover { transform: none; }
      .event-btn::after { display: none; }
      .block-label--tag { animation: none; }
      .block-label[data-banner-label] { animation: none; }
    }

    /* ═══════════════════════════════════════════════════════
       13. ADMIN TOOLKIT
       ═══════════════════════════════════════════════════════ */
    
    /* NÚT CÀI ĐẶT */
    .admin-toggle {
      position: absolute;
      top: clamp(10px, 2vmin, 20px);
      right: clamp(10px, 2vmin, 20px);
      z-index: 100;
      width: 42px; 
      height: 42px;
      display: flex; align-items: center; justify-content: center;
      background: rgba(25, 35, 50, 0.55);
      -webkit-backdrop-filter: blur(12px) saturate(150%);
      backdrop-filter: blur(12px) saturate(150%);
      border: 1px solid rgba(255, 255, 255, 0.45);
      clip-path: polygon(10px 0, 100% 0, 100% calc(100% - 10px), calc(100% - 10px) 100%, 0 100%, 0 10px);
      color: #ffffff;
      cursor: pointer;
      box-shadow: inset 0 0 10px rgba(255,255,255,0.05), 0 4px 15px rgba(0,0,0,0.3);
      transition: all .3s ease;
      outline: none;
    }
    .admin-toggle:hover {
      background: rgba(40, 55, 80, 0.8);
      transform: scale(1.05);
      box-shadow: inset 0 0 15px rgba(255,255,255,0.1), 0 6px 20px rgba(0,0,0,0.4);
    }
    .admin-toggle:active { transform: scale(0.95); }
    
    /* Icon xoay - ĐÃ TỐI ƯU MƯỢT HƠN */
    .admin-toggle svg {
      width: 22px; height: 22px;
      stroke: currentColor; fill: none; stroke-width: 1.8;
      /* Sử dụng easing mượt, bỏ hiệu ứng "nảy" gắt */
      transition: transform 0.5s cubic-bezier(0.4, 0, 0.2, 1);
    }
    
    .admin-toggle:hover svg {
      transform: rotate(45deg);
    }
    
    /* Khi panel mở (class .is-open) */
    .admin-toggle.is-open {
      background: rgba(255, 255, 255, 0.15);
      border-color: rgba(255, 255, 255, 0.9);
      box-shadow: inset 0 0 15px rgba(255,255,255,0.2), 0 0 20px rgba(255,255,255,0.15);
    }
    .admin-toggle.is-open svg {
      /* Xoay 180 độ + phóng to nhẹ tạo cảm giác "mở khóa" */
      transform: rotate(180deg) scale(1.1);
    }
    
    @media (max-width: 480px) {
      .admin-toggle { width: 36px; height: 36px; }
      .admin-toggle svg { width: 18px; height: 18px; }
    }

    /* LỚP NỀN MỜ */
    .admin-panel {
      position: fixed; inset: 0; z-index: 10010;
      display: flex; align-items: center; justify-content: center;
      padding: 16px;
      opacity: 0; visibility: hidden; pointer-events: none;
      transition: opacity .35s ease, visibility .35s ease;
    }
    .admin-panel.active { opacity: 1; visibility: visible; pointer-events: auto; }

    .admin-panel__backdrop {
      position: absolute; inset: 0;
      background: rgba(0, 0, 0, 0.4);
      -webkit-backdrop-filter: blur(16px) saturate(120%);
      backdrop-filter: blur(16px) saturate(120%);
      opacity: 0;
      transition: opacity .4s ease;
    }
    .admin-panel.active .admin-panel__backdrop { opacity: 1; }

    /* BẢNG CÀI ĐẶT - ĐÃ TỐI ƯU ANIMATION */
    .admin-panel__dialog {
      position: relative;
      width: min(680px, 100%);
      max-height: calc(100dvh - 32px);
      display: flex; flex-direction: column;
      background: rgba(18, 26, 40, 0.65);
      -webkit-backdrop-filter: blur(32px) saturate(180%) brightness(1.1);
      backdrop-filter: blur(32px) saturate(180%) brightness(1.1);
      border: 1px solid rgba(255, 255, 255, 0.35);
      clip-path: polygon(0 0, calc(100% - 20px) 0, 100% 20px, 100% 100%, 20px 100%, 0 calc(100% - 20px));
      box-shadow: 
        0 24px 64px rgba(0, 0, 0, 0.7),
        inset 0 0 0 1px rgba(255, 255, 255, 0.05);
      
      /* transform-origin được tính toán bằng JS */
      transform-origin: center center;
      opacity: 0;
      /* Giảm scale xuống 0.2 (thay vì 0.05) + trượt nhẹ lên để mượt hơn */
      transform: scale(0.2) translateY(20px);
      /* Giảm độ mờ (blur) để máy yếu không bị lag */
      filter: blur(4px);
      
      /* Sử dụng cubic-bezier mượt (ease-out mạnh), thời gian hợp lý */
      transition:
        opacity 0.35s ease,
        transform 0.5s cubic-bezier(0.2, 0.9, 0.3, 1),
        filter 0.35s ease;
      
      will-change: transform, opacity, filter;
      overflow: hidden;
    }
    
    .admin-panel.active .admin-panel__dialog {
      opacity: 1;
      transform: scale(1) translateY(0);
      filter: blur(0px);
    }

    /* Vệt sáng chéo Liquid Glass */
    .admin-panel__dialog::before {
      content: "";
      position: absolute; inset: 0;
      pointer-events: none;
      z-index: 0;
      background:
        linear-gradient(135deg,
          rgba(255, 255, 255, 0.15) 0%,
          rgba(255, 255, 255, 0.0) 20%,
          rgba(255, 255, 255, 0.0) 70%,
          rgba(255, 255, 255, 0.05) 100%),
        linear-gradient(115deg,
          transparent 40%,
          rgba(255, 255, 255, 0.05) 45%,
          rgba(255, 255, 255, 0.1) 48%,
          rgba(255, 255, 255, 0.0) 52%,
          transparent 60%
        );
    }
    .admin-panel__dialog::after { display: none; }

    /* HEADER & TABS */
    .admin-panel__header {
      display: flex; justify-content: space-between; align-items: center;
      padding: 14px 16px;
      border-bottom: 1px solid rgba(255, 255, 255, 0.1);
      flex-shrink: 0;
      background: rgba(0, 0, 0, 0.15);
      position: relative;
      z-index: 1;
    }
    .admin-panel__header h2 {
      font-size: 12px; letter-spacing: 2px;
      color: #ffffff;
      text-transform: uppercase;
      font-family: "GFF-Latin-Bold", sans-serif;
      text-shadow: 0 2px 4px rgba(0,0,0,0.5);
      white-space: nowrap;
    }
    
    /* NÚT CLOSE - CẮT GÓC TRÊN-PHẢI VÀ DƯỚI-TRÁI */
    .admin-panel__close {
      width: 28px; height: 28px;
      display: flex; align-items: center; justify-content: center;
      background: rgba(255,255,255,.05);
      border: 1px solid rgba(255, 255, 255, 0.3);
      color: #ffffff; cursor: pointer;
      clip-path: polygon(0 0, calc(100% - 6px) 0, 100% 6px, 100% 100%, 6px 100%, 0 calc(100% - 6px));
      transition: all .25s ease; font-family: inherit; font-size: 12px;
      flex-shrink: 0;
    }
    .admin-panel__close:hover { background: rgba(255,255,255,.2); }

    .admin-panel__tabs {
      display: flex; gap: 4px;
      padding: 0 16px;
      border-bottom: 1px solid rgba(255, 255, 255, 0.1);
      overflow-x: auto;
      flex-shrink: 0;
      min-height: 44px;
      background: rgba(0, 0, 0, 0.1);
      position: relative;
      z-index: 1;
      scrollbar-width: none;
      -webkit-overflow-scrolling: touch;
    }
    .admin-panel__tabs::-webkit-scrollbar { display: none; }

    .admin-panel__tabs button {
      padding: 12px 14px;
      background: transparent;
      border: none;
      border-bottom: 2px solid transparent;
      color: rgba(255, 255, 255, 0.6);
      font-family: "GFF-Latin-Bold", sans-serif;
      font-size: 10px;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      cursor: pointer;
      white-space: nowrap;
      transition: all .25s ease;
      flex-shrink: 0;
    }
    .admin-panel__tabs button:hover {
      color: #fff;
      background: rgba(255, 255, 255, 0.05);
    }
    .admin-panel__tabs button.active {
      color: #ffffff;
      border-bottom-color: #ffffff;
      text-shadow: 0 0 8px rgba(255, 255, 255, 0.5);
      background: rgba(255, 255, 255, 0.05);
    }

    /* BODY */
    .admin-panel__body {
      flex: 1; min-height: 0;
      overflow-y: auto;
      padding: 16px;
      position: relative;
      z-index: 1;
    }
    .admin-panel__body [data-panel] { display: flex; flex-direction: column; gap: 10px; }
    .admin-panel__body [data-panel][hidden] { display: none; }
    .admin-panel__body [data-cat-group] { display: flex; flex-direction: column; gap: 10px; }
    .admin-panel__body [data-cat-group][hidden] { display: none; }

    .admin-field { display: flex; flex-direction: column; gap: 4px; }
    .admin-field-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 8px;
    }

    .admin-field label {
      font-size: 9px; letter-spacing: 1.5px;
      color: rgba(255,255,255,.7);
      text-transform: uppercase;
      font-family: "GFF-Latin-Bold", sans-serif;
    }
    .admin-field input, .admin-field textarea {
      width: 100%;
      padding: 8px 10px;
      background: rgba(0,0,0,.3);
      border: 1px solid rgba(255,255,255,.15);
      border-radius: 3px;
      color: #fff;
      font-family: ui-monospace, Consolas, monospace;
      font-size: 11px;
      outline: none;
      transition: border-color .2s ease;
    }
    .admin-field input:focus, .admin-field textarea:focus { border-color: rgba(255,255,255,.6); }
    .admin-field textarea { resize: vertical; min-height: 130px; }

    .admin-field input[type="color"] {
      padding: 2px;
      height: 36px;
      cursor: pointer;
      -webkit-appearance: none;
      appearance: none;
    }
    .admin-field input[type="color"]::-webkit-color-swatch-wrapper { padding: 0; }
    .admin-field input[type="color"]::-webkit-color-swatch { border: none; border-radius: 2px; }
    .admin-field input[type="color"]::-moz-color-swatch { border: none; border-radius: 2px; }

    .admin-btn {
      padding: 8px 14px;
      background: rgba(255,255,255,.1);
      border: 1px solid rgba(255,255,255,.3);
      color: #fff;
      font-family: "GFF-Latin-Bold", sans-serif; font-size: 10px;
      letter-spacing: 1.5px; text-transform: uppercase;
      cursor: pointer;
      clip-path: polygon(6px 0, 100% 0, 100% calc(100% - 6px), calc(100% - 6px) 100%, 0 100%, 0 6px);
      transition: all .25s ease;
    }
    .admin-btn:hover { background: rgba(255,255,255,.25); }
    .admin-btn:active { transform: scale(.97); }
    
    .admin-btn--primary {
      background: rgba(100,200,255,.15);
      border-color: rgba(100,200,255,.4);
      color: #aee0ff;
    }
    .admin-btn--primary:hover { background: #4db8ff; color: #001020; border-color: #4db8ff; }
    
    .admin-btn--danger {
      background: rgba(255,50,50,.15);
      border-color: rgba(255,50,50,.4);
      color: #ffaaaa;
    }
    .admin-btn--danger:hover { background: #ff3a3a; color: #fff; border-color: #ff3a3a; }

    .admin-row { display: flex; gap: 8px; flex-wrap: wrap; }

    .admin-info {
      padding: 8px 12px;
      background: rgba(0,0,0,.3);
      border-left: 3px solid rgba(255,255,255,.5);
      font-size: 11px;
      color: rgba(255,255,255,.85);
      font-family: ui-monospace, Consolas, monospace;
      word-break: break-word;
    }

    .admin-section-title {
      font-size: 9px; letter-spacing: 1.8px;
      color: rgba(255,255,255,.85);
      text-transform: uppercase;
      font-family: "GFF-Latin-Bold", sans-serif;
      padding: 8px 0 4px;
      border-bottom: 1px dashed rgba(255,255,255,.2);
      margin-bottom: 2px;
    }
    .admin-section-title--small {
      font-size: 8px;
      padding: 6px 0 2px;
      border-bottom: none;
      color: rgba(255,255,255,.6);
      letter-spacing: 1.4px;
    }
    .admin-section-title--small .admin-scope-badge {
      display: inline-block;
      padding: 1px 5px;
      margin-left: 4px;
      font-size: 7px;
      background: rgba(255,255,255,.1);
      border: 1px solid rgba(255,255,255,.2);
      border-radius: 2px;
      letter-spacing: .8px;
      color: #fff;
    }

    .admin-event-tabs {
      display: flex; gap: 4px;
      padding: 6px;
      background: rgba(0,0,0,.2);
      border: 1px solid rgba(255,255,255,.15);
      border-radius: 3px;
      margin-bottom: 4px;
    }
    .admin-event-tab {
      flex: 1;
      padding: 8px 12px;
      background: transparent;
      border: 1px solid rgba(255,255,255,.1);
      border-radius: 2px;
      color: rgba(255,255,255,.6);
      font-family: "GFF-Latin-Bold", sans-serif;
      font-size: 10px;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      cursor: pointer;
      transition: all .25s ease;
    }
    .admin-event-tab:hover { background: rgba(255,255,255,.1); color: #fff; }
    .admin-event-tab.active {
      background: rgba(255,255,255,.15);
      border-color: rgba(255,255,255,.5);
      color: #fff;
      box-shadow: inset 0 0 10px rgba(255,255,255,.1);
    }

    .admin-cat-tabs {
      display: flex;
      margin: 4px 0 8px;
      background: rgba(0,0,0,.2);
      border: 1px solid rgba(255,255,255,.2);
      clip-path: polygon(0 0, 100% 0, 100% calc(100% - 10px), calc(100% - 10px) 100%, 0 100%);
      overflow: hidden;
    }
    .admin-cat-tab {
      flex: 1;
      padding: 11px 12px;
      background: transparent;
      border: none;
      color: rgba(255,255,255,.6);
      font-family: "GFF-Latin-Bold", sans-serif;
      font-size: 11px;
      letter-spacing: 2px;
      text-transform: uppercase;
      cursor: pointer;
      transition: all .25s ease;
      position: relative;
    }
    .admin-cat-tab + .admin-cat-tab { border-left: 1px solid rgba(255,255,255,.2); }
    .admin-cat-tab:hover { color: #fff; background: rgba(255,255,255,.1); }
    .admin-cat-tab.active {
      color: #fff;
      background: rgba(255,255,255,.15);
      text-shadow: 0 0 10px rgba(255,255,255,.5);
      box-shadow: inset 0 0 20px rgba(255,255,255,.1);
    }

    .admin-health-list { display: flex; flex-direction: column; gap: 12px; }
    .admin-health-section { display: flex; flex-direction: column; gap: 6px; }
    .admin-health-section .admin-section-title { margin: 0 0 4px; }
    .admin-health-item {
      display: flex; align-items: center; gap: 8px;
      padding: 8px 10px;
      background: rgba(0,0,0,.3);
      border: 1px solid rgba(255,255,255,.1);
      border-radius: 3px;
      font-size: 10px;
      font-family: ui-monospace, Consolas, monospace;
      pointer-events: none;
    }
    .admin-health-item__name {
      flex-shrink: 0;
      width: 130px;
      color: rgba(255,255,255,.9);
      font-family: "GFF-Latin-Bold", sans-serif;
      letter-spacing: .5px;
    }
    .admin-health-item__url {
      flex: 1; min-width: 0;
      color: rgba(255,255,255,.5);
      overflow: hidden; text-overflow: ellipsis; white-space: nowrap;
    }
    .admin-health-item__status {
      flex-shrink: 0;
      padding: 3px 8px; border-radius: 2px;
      font-size: 9px; letter-spacing: .5px; font-weight: 700;
      font-family: "GFF-Latin-Bold", sans-serif;
      white-space: nowrap;
    }
    .admin-health-item--ok .admin-health-item__status { background: rgba(50,200,100,.2); color: #66ff99; }
    .admin-health-item--err .admin-health-item__status { background: rgba(255,50,50,.2); color: #ff6666; }
    .admin-health-item--loading .admin-health-item__status { background: rgba(255,180,50,.2); color: #ffd666; }

    .admin-health-summary {
      padding: 8px 12px;
      background: rgba(0,0,0,.3);
      border: 1px solid rgba(255,255,255,.15);
      font-size: 11px;
      color: rgba(255,255,255,.85);
      font-family: "GFF-Latin-Bold", sans-serif;
      letter-spacing: .5px;
      display: flex; justify-content: space-between; gap: 10px; flex-wrap: wrap;
    }
    .admin-health-summary span { display: inline-flex; align-items: center; gap: 4px; }

    .admin-toast {
      position: fixed; bottom: 20px; left: 50%;
      transform: translateX(-50%) translateY(20px);
      padding: 10px 20px;
      background: rgba(20,26,42,.96);
      border: 1px solid rgba(255,255,255,.3);
      color: #ffffff;
      font-family: "GFF-Latin-Bold", sans-serif;
      font-size: 12px; letter-spacing: 1.5px;
      clip-path: polygon(8px 0, 100% 0, 100% calc(100% - 8px), calc(100% - 8px) 100%, 0 100%, 0 8px);
      box-shadow: 0 10px 30px rgba(0,0,0,.6);
      opacity: 0; pointer-events: none;
      transition: all .3s ease;
      z-index: 10020;
      white-space: nowrap;
      max-width: calc(100vw - 32px);
      overflow: hidden; text-overflow: ellipsis;
    }
    .admin-toast.show { opacity: 1; transform: translateX(-50%) translateY(0); }

    @media (prefers-reduced-motion: reduce) {
      .admin-panel__dialog { transition: none; transform: scale(1); opacity: 1; filter: none; }
      .admin-panel__backdrop { transition: none; opacity: 1; }
    }
  </style>
</head>
<body>

  <!-- TRANG 1: ASSETS -->
  <div class="page-wrapper page-section active" id="page-assets">
    <div class="container">
      <div class="menu-backdrop" aria-hidden="true"></div>

      <button class="admin-toggle" aria-label="Công cụ quản trị" title="Công cụ quản trị (Ctrl+Shift+A)">
        <svg viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round">
          <circle cx="12" cy="12" r="3"/>
          <path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 1 1-2.83 2.83l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 1 1-4 0v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 1 1-2.83-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 1 1 0-4h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 1 1 2.83-2.83l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 1 1 4 0v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 1 1 2.83 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 1 1 0 4h-.09a1.65 1.65 0 0 0-1.51 1z"/>
        </svg>
      </button>

      <div class="ff-menu-wrapper">
        <button class="ff-menu-btn" aria-label="Mở menu" aria-expanded="false">
          <span></span><span></span><span></span>
        </button>
        <div class="ff-menu-panel">
          <ul class="ff-menu-list">
            <li class="ff-menu-item active" data-target="page-assets"><span class="menu-text">ASSETS</span></li>
            <li class="ff-menu-item" data-target="page-banner"><span class="menu-text">BANNER</span></li>
          </ul>
        </div>
      </div>

      <nav class="event-nav" aria-label="Danh sách sự kiện">
        <button type="button" class="event-btn active" data-event="1"><span>Sự kiện 1</span></button>
        <button type="button" class="event-btn" data-event="2"><span>Sự kiện 2</span></button>
        <button type="button" class="event-btn" data-event="3"><span>Sự kiện 3</span></button>
      </nav>

      <div class="block-wrap header-wrap">
        <header class="header glass-panel">
          <img alt="Logo sự kiện" class="logo-img" data-img="logo" draggable="false">
        </header>
        <div class="block-labels">
          <div class="block-label block-label--tag" data-tag>ĐANG TẢI…</div>
          <div class="block-label">TITLE SỰ KIỆN</div>
        </div>
      </div>

      <div class="block-wrap tab-wrap">
        <div class="tab-section glass-panel">
          <div class="tab-wrapper">
            <img alt="Tab sự kiện" class="tab-image" data-img="tab" draggable="false">
          </div>
        </div>
        <div class="block-label">TAB SỰ KIỆN</div>
      </div>

      <div class="block-wrap content-wrap">
        <main class="content glass-panel">
          <div class="text-image-box" data-img="bg"></div>
        </main>
        <div class="block-label">BACKGROUND SỰ KIỆN</div>
      </div>

      <div class="footer-note">© 2026 Azerst – All rights reserved</div>
    </div>
  </div>

  <!-- TRANG 2: BANNER -->
  <div class="page-wrapper page-section" id="page-banner">
    <div class="container">
      <div class="menu-backdrop" aria-hidden="true"></div>

      <button class="admin-toggle" aria-label="Công cụ quản trị" title="Công cụ quản trị (Ctrl+Shift+A)">
        <svg viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round">
          <circle cx="12" cy="12" r="3"/>
          <path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 1 1-2.83 2.83l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 1 1-4 0v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 1 1-2.83-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 1 1 0-4h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 1 1 2.83-2.83l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 1 1 4 0v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 1 1 2.83 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 1 1 0 4h-.09a1.65 1.65 0 0 0-1.51 1z"/>
        </svg>
      </button>

      <div class="ff-menu-wrapper">
        <button class="ff-menu-btn" aria-label="Mở menu" aria-expanded="false">
          <span></span><span></span><span></span>
        </button>
        <div class="ff-menu-panel">
          <ul class="ff-menu-list">
            <li class="ff-menu-item" data-target="page-assets"><span class="menu-text">ASSETS</span></li>
            <li class="ff-menu-item active" data-target="page-banner"><span class="menu-text">BANNER</span></li>
          </ul>
        </div>
      </div>

      <nav class="event-nav" aria-label="Danh sách sự kiện banner">
        <button type="button" class="event-btn active" data-event="1"><span>Sự kiện 1</span></button>
        <button type="button" class="event-btn" data-event="2"><span>Sự kiện 2</span></button>
        <button type="button" class="event-btn" data-event="3"><span>Sự kiện 3</span></button>
      </nav>

      <div class="block-wrap content-wrap">
        <main class="content glass-panel banner-mode">
          <div class="banner-showcase">

            <div class="banner-card">
              <span class="banner-card__label">16 : 9</span>
              <img alt="Banner 16:9" class="banner-card__img" data-banner="16-9" draggable="false" loading="lazy">
              <button type="button" class="banner-card__view" aria-label="Xem ảnh 16:9">
                <svg viewBox="0 0 24 24" width="10" height="10" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"/><circle cx="12" cy="12" r="3"/>
                </svg><span>XEM</span>
              </button>
            </div>

            <div class="banner-card banner-card--portrait">
              <span class="banner-card__label">436 × 606</span>
              <img alt="Banner 436x606" class="banner-card__img" data-banner="portrait" draggable="false" loading="lazy">
              <button type="button" class="banner-card__view" aria-label="Xem ảnh 436x606">
                <svg viewBox="0 0 24 24" width="10" height="10" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"/><circle cx="12" cy="12" r="3"/>
                </svg><span>XEM</span>
              </button>
            </div>

            <div class="banner-card">
              <span class="banner-card__label">256 × 107</span>
              <img alt="Banner 256x107" class="banner-card__img" data-banner="256" draggable="false" loading="lazy">
              <button type="button" class="banner-card__view" aria-label="Xem ảnh 256x107">
                <svg viewBox="0 0 24 24" width="10" height="10" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"/><circle cx="12" cy="12" r="3"/>
                </svg><span>XEM</span>
              </button>
            </div>

            <div class="banner-card">
              <span class="banner-card__label">512 × 182</span>
              <img alt="Banner 512x182" class="banner-card__img" data-banner="512" draggable="false" loading="lazy">
              <button type="button" class="banner-card__view" aria-label="Xem ảnh 512x182">
                <svg viewBox="0 0 24 24" width="10" height="10" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"/><circle cx="12" cy="12" r="3"/>
                </svg><span>XEM</span>
              </button>
            </div>

          </div>
        </main>
        <div class="block-label block-label--center" data-banner-label>ĐANG TẢI…</div>
      </div>

      <div class="footer-note">© 2026 Azerst – All rights reserved</div>
    </div>
  </div>

  <!-- LIGHTBOX -->
  <div class="banner-lightbox" id="bannerLightbox" role="dialog" aria-modal="true" aria-label="Xem ảnh banner">
    <button type="button" class="banner-lightbox__close" aria-label="Đóng">✕</button>
    <img class="banner-lightbox__img" alt="Ảnh banner phóng to" draggable="false">
  </div>

  <!-- ADMIN PANEL -->
  <div class="admin-panel" id="adminPanel">
    <div class="admin-panel__backdrop" data-admin-close></div>
    <div class="admin-panel__dialog">
      <header class="admin-panel__header">
        <h2>🛠️ Công cụ quản trị</h2>
        <button class="admin-panel__close" data-admin-close aria-label="Đóng">✕</button>
      </header>

      <nav class="admin-panel__tabs">
        <button type="button" data-tab="edit" class="active">Sửa URL</button>
        <button type="button" data-tab="health">Kiểm ảnh</button>
        <button type="button" data-tab="data">Xuất / Nhập</button>
      </nav>

      <div class="admin-panel__body">

        <!-- TAB: EDIT -->
        <div data-panel="edit">
          <div class="admin-info" id="adminCurrentInfo">Đang tải…</div>

          <div class="admin-section-title">🌐 Toàn trang</div>
          <div class="admin-field">
            <label>Background toàn trang (Body)</label>
            <input type="url" data-admin-field="bodyBg" placeholder="https://…">
          </div>

          <div class="admin-section-title" style="margin-top:6px;">📦 Sự kiện</div>
          <div class="admin-event-tabs" role="tablist" aria-label="Chọn sự kiện">
            <button type="button" class="admin-event-tab active" data-event-tab="1">Sự kiện 1</button>
            <button type="button" class="admin-event-tab" data-event-tab="2">Sự kiện 2</button>
            <button type="button" class="admin-event-tab" data-event-tab="3">Sự kiện 3</button>
          </div>

          <div class="admin-cat-tabs" role="tablist" aria-label="Chọn loại nội dung">
            <button type="button" class="admin-cat-tab active" data-cat-tab="assets">ASSETS</button>
            <button type="button" class="admin-cat-tab" data-cat-tab="banner">BANNER</button>
          </div>

          <div data-cat-group="assets">
            <div class="admin-section-title admin-section-title--small">
              🎨 Màu tiêu đề TAG
              <span class="admin-scope-badge">TẤT CẢ SỰ KIỆN</span>
            </div>
            <div class="admin-field-row">
              <div class="admin-field">
                <label>Màu chính</label>
                <input type="color" data-admin-field="tagMain" value="#ff3a3a">
              </div>
              <div class="admin-field">
                <label>Màu sáng</label>
                <input type="color" data-admin-field="tagShine" value="#ffffff">
              </div>
            </div>

            <div class="admin-section-title admin-section-title--small">
              🎨 Màu nút khi bấm
              <span class="admin-scope-badge">TẤT CẢ SỰ KIỆN</span>
            </div>
            <div class="admin-field-row">
              <div class="admin-field">
                <label>Màu chính</label>
                <input type="color" data-admin-field="btnMain" value="#ffd23a">
              </div>
              <div class="admin-field">
                <label>Màu sáng</label>
                <input type="color" data-admin-field="btnShine" value="#fff8e0">
              </div>
            </div>

            <div class="admin-section-title admin-section-title--small" style="margin-top:10px;">
              📄 Nội dung sự kiện
            </div>
            <div class="admin-field">
              <label>Tiêu đề sự kiện (TAG)</label>
              <input type="text" data-admin-field="tag" placeholder="Nhập tiêu đề…">
            </div>
            <div class="admin-field">
              <label>Logo URL</label>
              <input type="url" data-admin-field="logo" placeholder="https://…">
            </div>
            <div class="admin-field">
              <label>Tab URL</label>
              <input type="url" data-admin-field="tab" placeholder="https://…">
            </div>
            <div class="admin-field">
              <label>Background sự kiện URL</label>
              <input type="url" data-admin-field="bg" placeholder="https://…">
            </div>
          </div>

          <div data-cat-group="banner" hidden>
            <div class="admin-section-title admin-section-title--small">
              🎨 Màu tiêu đề Banner
              <span class="admin-scope-badge">TẤT CẢ SỰ KIỆN</span>
            </div>
            <div class="admin-field-row">
              <div class="admin-field">
                <label>Màu chính</label>
                <input type="color" data-admin-field="bannerMain" value="#ffb347">
              </div>
              <div class="admin-field">
                <label>Màu sáng</label>
                <input type="color" data-admin-field="bannerShine" value="#ffffff">
              </div>
            </div>

            <div class="admin-section-title admin-section-title--small">
              🎨 Màu nút khi bấm
              <span class="admin-scope-badge">TẤT CẢ SỰ KIỆN</span>
            </div>
            <div class="admin-field-row">
              <div class="admin-field">
                <label>Màu chính</label>
                <input type="color" data-admin-field="btnBannerMain" value="#ff2d2d">
              </div>
              <div class="admin-field">
                <label>Màu sáng</label>
                <input type="color" data-admin-field="btnBannerShine" value="#ffffff">
              </div>
            </div>

            <div class="admin-section-title admin-section-title--small" style="margin-top:10px;">
              📄 Nội dung sự kiện
            </div>
            <div class="admin-field">
              <label>Tiêu đề Banner</label>
              <input type="text" data-admin-field="bannerTitle" placeholder="Nhập tiêu đề banner…">
            </div>
            <div class="admin-field">
              <label>Banner 16:9 URL</label>
              <input type="url" data-admin-field="banner169" placeholder="https://…">
            </div>
            <div class="admin-field">
              <label>Banner Portrait 436×606 URL</label>
              <input type="url" data-admin-field="bannerPortrait" placeholder="https://…">
            </div>
            <div class="admin-field">
              <label>Banner 256×107 URL</label>
              <input type="url" data-admin-field="banner256" placeholder="https://…">
            </div>
            <div class="admin-field">
              <label>Banner 512×182 URL</label>
              <input type="url" data-admin-field="banner512" placeholder="https://…">
            </div>
          </div>

          <div class="admin-row">
            <button type="button" class="admin-btn admin-btn--primary" data-admin-action="save">💾 Lưu</button>
            <button type="button" class="admin-btn" data-admin-action="revert">↺ Hoàn tác</button>
          </div>
        </div>

        <!-- TAB: HEALTH -->
        <div data-panel="health" hidden>
          <div class="admin-row">
            <button type="button" class="admin-btn admin-btn--primary" data-admin-action="checkHealth">🔍 Kiểm tra tất cả</button>
            <button type="button" class="admin-btn" data-admin-action="cancelHealth">✕ Hủy</button>
          </div>
          <div class="admin-health-summary" id="adminHealthSummary" hidden>
            <span>✅ <b id="healthOkCount">0</b> OK</span>
            <span>❌ <b id="healthErrCount">0</b> lỗi</span>
            <span>⏳ <b id="healthTotalCount">0</b> tổng</span>
          </div>
          <div class="admin-health-list" id="adminHealthList"></div>
        </div>

        <!-- TAB: DATA -->
        <div data-panel="data" hidden>
          <div class="admin-info">Cấu hình JSON của toàn bộ IMG. Sửa xong bấm Nhập để áp dụng.</div>
          <div class="admin-field">
            <label>JSON cấu hình</label>
            <textarea id="adminJson" spellcheck="false"></textarea>
          </div>
          <div class="admin-row">
            <button type="button" class="admin-btn admin-btn--primary" data-admin-action="copyJson">📋 Sao chép</button>
            <button type="button" class="admin-btn" data-admin-action="downloadJson">⬇ Tải file</button>
            <button type="button" class="admin-btn" data-admin-action="importJson">📥 Nhập JSON</button>
            <button type="button" class="admin-btn admin-btn--danger" data-admin-action="resetAll">⚠ Reset mặc định</button>
          </div>
        </div>

      </div>
    </div>
  </div>

  <div class="admin-toast" id="adminToast"></div>

  <script>
    /* ══════════════════════════════════════════════════════════════
       📁 KHO ẢNH + DỮ LIỆU
       ══════════════════════════════════════════════════════════════ */
    const IMG = {
      bodyBg: 'https://cdn.wildflamestudio.com/common/web_event/official2.ff.garena.all/img/20228/b2b0012af7e3bfcdc90cd8744065e8ab.jpg',

      logo: {
        1: 'https://azerst-image-vn.vercel.app/images/PWCaA9UUX.png',
        2: 'https://azerst-image-vn.vercel.app/images/m4jwa7iMn.png',
        3: 'https://azerst-image-vn.vercel.app/images/mw5xbjnMj.png',
      },
      tab: {
        1: 'https://azerst-image-vn.vercel.app/images/CA89esxJg.png',
        2: 'https://azerst-image-vn.vercel.app/images/Xl6yeAKFU.png',
        3: 'https://azerst-image-vn.vercel.app/images/GsqjGtxDt.png',
      },
      bg: {
        1: 'https://azerst-image-vn.vercel.app/images/RfqGsTUFB.png',
        2: 'https://azerst-image-vn.vercel.app/images/QOoBqwG3R.png',
        3: 'https://azerst-image-vn.vercel.app/images/rGM5HmhEG.png',
      },
      banner169: {
        1: 'https://azerst-image-vn.vercel.app/images/YQd6v2eKl.png',
        2: 'https://azerst-image-vn.vercel.app/images/64SsEq3sh.jpg',
        3: 'https://azerst-image-vn.vercel.app/images/hTbfK9XRk.png',
      },
      bannerPortrait: {
        1: 'https://azerst-image-vn.vercel.app/images/7emzKHIPG.png',
        2: 'https://azerst-image-vn.vercel.app/images/NkS5Uib75.png',
        3: 'https://azerst-image-vn.vercel.app/images/MrGWGnY3e.png',
      },
      banner256: {
        1: 'https://azerst-image-vn.vercel.app/images/rOLkC6nRi.png',
        2: 'https://azerst-image-vn.vercel.app/images/4q4A1mvDU.png',
        3: 'https://azerst-image-vn.vercel.app/images/9pWreeN5O.png',
      },
      banner512: {
        1: 'https://azerst-image-vn.vercel.app/images/IOHEbOLKn.png',
        2: 'https://azerst-image-vn.vercel.app/images/dmbomVVfA.png',
        3: 'https://azerst-image-vn.vercel.app/images/UUOllEYiO.png',
      },

      tag: {
        1: 'THỢ SĂN HUYẾT QUỶ',
        2: 'MÀN TRÌNH DIỄN KINH DỊ',
        3: 'MÓNG VUỐT TAI HỌA',
      },
      bannerTitle: {
        1: 'THỢ SĂN HUYẾT QUỶ',
        2: 'MÀN TRÌNH DIỄN KINH DỊ',
        3: 'MÓNG VUỐT TAI HỌA',
      },

      tagStyle:         { main: '#ff3a3a', shine: '#ffffff' },
      bannerTitleStyle: { main: '#ffb347', shine: '#ffffff' },
      btnStyle:         { main: '#ffd23a', shine: '#fff8e0' },
      btnBannerStyle:   { main: '#ff2d2d', shine: '#ffffff' },
    };

    const BANNER_MAP = {
      '16-9':     'banner169',
      'portrait': 'bannerPortrait',
      '256':      'banner256',
      '512':      'banner512',
    };

    function applyBodyBg() {
      if (IMG.bodyBg) {
        document.documentElement.style.setProperty('--body-bg', `url('${IMG.bodyBg}')`);
      }
    }
    applyBodyBg();

    /* ══════════════════════════════════════════════════════════════
       🎨 ÁP DỤNG MÀU
       ══════════════════════════════════════════════════════════════ */
    function applyPageStyles(page) {
      if (page.id === 'page-assets') {
        const tag = page.querySelector('[data-tag]');
        if (tag) {
          tag.style.setProperty('--tag-main',  IMG.tagStyle?.main  || '#ff3a3a');
          tag.style.setProperty('--tag-shine', IMG.tagStyle?.shine || '#ffffff');
        }
        const btn = page.querySelector('.event-btn.active');
        if (btn) {
          btn.style.setProperty('--btn-main',  IMG.btnStyle?.main  || '#ffd23a');
          btn.style.setProperty('--btn-shine', IMG.btnStyle?.shine || '#fff8e0');
        }
      } else if (page.id === 'page-banner') {
        const label = page.querySelector('[data-banner-label]');
        if (label) {
          label.style.setProperty('--banner-main',  IMG.bannerTitleStyle?.main  || '#ffb347');
          label.style.setProperty('--banner-shine', IMG.bannerTitleStyle?.shine || '#ffffff');
        }
        const btn = page.querySelector('.event-btn.active');
        if (btn) {
          btn.style.setProperty('--btn-main',  IMG.btnBannerStyle?.main  || '#ff2d2d');
          btn.style.setProperty('--btn-shine', IMG.btnBannerStyle?.shine || '#ffffff');
        }
      }
    }

    /* ══════════════════════════════════════════════════════════════
       🎬 CẬP NHẬT UI THEO SỰ KIỆN
       ══════════════════════════════════════════════════════════════ */
    function updateAssetsPage(page, key) {
      const logo = page.querySelector('[data-img="logo"]');
      const tab  = page.querySelector('[data-img="tab"]');
      const bg   = page.querySelector('[data-img="bg"]');
      const tag  = page.querySelector('[data-tag]');
      if (logo && IMG.logo[key]) logo.src = IMG.logo[key];
      if (tab  && IMG.tab[key])  tab.src  = IMG.tab[key];
      if (bg   && IMG.bg[key])   bg.style.backgroundImage = `url('${IMG.bg[key]}')`;
      if (tag  && IMG.tag[key])  tag.textContent = IMG.tag[key];
      applyPageStyles(page);
    }

    function updateBannerPage(page, key) {
      const label = page.querySelector('[data-banner-label]');
      const newLabel = IMG.bannerTitle?.[key] || IMG.tag?.[key];
      if (label && newLabel && label.textContent !== newLabel) {
        label.style.opacity = '.4';
        setTimeout(() => { label.textContent = newLabel; label.style.opacity = '1'; }, 140);
      }
      page.querySelectorAll('.banner-card__img').forEach(img => {
        const partKey = BANNER_MAP[img.dataset.banner];
        const newSrc  = partKey ? IMG[partKey]?.[key] : null;
        if (!newSrc) return;
        img.classList.add('is-loading');
        const pre = new Image();
        pre.onload = pre.onerror = () => { img.src = newSrc; img.classList.remove('is-loading'); };
        pre.src = newSrc;
      });
      applyPageStyles(page);
    }

    function refreshPage(page) {
      const btn = page.querySelector('.event-btn.active');
      if (!btn) return;
      const key = btn.dataset.event;
      if (page.id === 'page-assets') updateAssetsPage(page, key);
      if (page.id === 'page-banner') updateBannerPage(page, key);
    }

    /* ══════════════════════════════════════════════════════════════
       🖱️ CLICK TAB SỰ KIỆN
       ══════════════════════════════════════════════════════════════ */
    document.querySelectorAll('.event-btn').forEach(btn => {
      btn.addEventListener('click', function (e) {
        e.preventDefault();
        const page = this.closest('.page-section');
        if (!page) return;
        page.querySelectorAll('.event-btn').forEach(b => b.classList.remove('active'));
        this.classList.add('active');
        refreshPage(page);
      });
    });

    /* ══════════════════════════════════════════════════════════════
       🔍 LIGHTBOX
       ══════════════════════════════════════════════════════════════ */
    const lightbox      = document.getElementById('bannerLightbox');
    const lightboxImg   = lightbox.querySelector('.banner-lightbox__img');
    const lightboxClose = lightbox.querySelector('.banner-lightbox__close');
    function openLightbox(src) { lightboxImg.src = src; lightbox.classList.add('active'); }
    function closeLightbox()   { lightbox.classList.remove('active'); }

    document.addEventListener('click', e => {
      const viewBtn = e.target.closest('.banner-card__view');
      if (!viewBtn) return;
      e.stopPropagation();
      const img = viewBtn.closest('.banner-card')?.querySelector('.banner-card__img');
      if (img && img.src) openLightbox(img.src);
    });
    lightboxClose.addEventListener('click', closeLightbox);
    lightbox.addEventListener('click', e => { if (e.target === lightbox) closeLightbox(); });
    document.addEventListener('keydown', e => {
      if (e.key === 'Escape' && lightbox.classList.contains('active')) closeLightbox();
    });

    /* ══════════════════════════════════════════════════════════════
       ☰ MENU
       ══════════════════════════════════════════════════════════════ */
    function closeAllMenus() {
      document.querySelectorAll('.ff-menu-wrapper.active').forEach(w => {
        w.classList.remove('active');
        w.querySelector('.ff-menu-btn')?.setAttribute('aria-expanded', 'false');
        w.closest('.container')?.classList.remove('menu-active');
      });
    }
    document.querySelectorAll('.ff-menu-btn').forEach(btn => {
      btn.addEventListener('click', function (e) {
        e.stopPropagation();
        const wrapper  = this.closest('.ff-menu-wrapper');
        const container = wrapper.closest('.container');
        const wasActive = wrapper.classList.contains('active');
        if (!wasActive) closeAllMenus();
        const isOpen = !wasActive;
        wrapper.classList.toggle('active', isOpen);
        this.setAttribute('aria-expanded', isOpen ? 'true' : 'false');
        container?.classList.toggle('menu-active', isOpen);
      });
    });
    document.querySelectorAll('.ff-menu-item').forEach(item => {
      item.addEventListener('click', function (e) {
        e.stopPropagation();
        const targetId = this.dataset.target;
        document.querySelectorAll('.ff-menu-item').forEach(i => {
          i.classList.toggle('active', i.dataset.target === targetId);
        });
        document.querySelectorAll('.page-section').forEach(p => p.classList.remove('active'));
        document.getElementById(targetId)?.classList.add('active');
        closeAllMenus();
      });
    });
    document.querySelectorAll('.menu-backdrop').forEach(bd => {
      bd.addEventListener('click', e => { e.stopPropagation(); closeAllMenus(); });
    });
    document.addEventListener('click', e => {
      document.querySelectorAll('.ff-menu-wrapper.active').forEach(w => {
        if (!w.contains(e.target)) closeAllMenus();
      });
    });
    document.addEventListener('keydown', e => { if (e.key === 'Escape') closeAllMenus(); });

    /* ══════════════════════════════════════════════════════════════
       🚀 KHỞI TẠO
       ══════════════════════════════════════════════════════════════ */
    (function preloadAll() {
      Object.values(IMG).forEach(part => {
        if (typeof part === 'string') {
          if (part.startsWith('http')) { const im = new Image(); im.src = part; }
        } else if (part && typeof part === 'object') {
          Object.values(part).forEach(url => {
            if (typeof url === 'string' && url.startsWith('http')) {
              const im = new Image(); im.src = url;
            }
          });
        }
      });
    })();

    document.querySelectorAll('.page-section').forEach(page => {
      page.querySelector('.event-btn.active')?.click();
    });

    /* ══════════════════════════════════════════════════════════════
       🛠️ ADMIN TOOLKIT
       ══════════════════════════════════════════════════════════════ */
    (function initAdminToolkit() {
      const panel   = document.getElementById('adminPanel');
      const toastEl = document.getElementById('adminToast');
      const DEFAULT_IMG = JSON.parse(JSON.stringify(IMG));

      let currentEditEvent = '1';
      let currentEditCat   = 'assets';
      let healthToken = 0;

      function showToast(msg) {
        toastEl.textContent = msg;
        toastEl.classList.add('show');
        clearTimeout(showToast._t);
        showToast._t = setTimeout(() => toastEl.classList.remove('show'), 2200);
      }
      function getContext() {
        const page = document.querySelector('.page-section.active');
        if (!page) return null;
        const btn = page.querySelector('.event-btn.active');
        return { page, eventKey: btn ? btn.dataset.event : '1' };
      }
      function getPageName(page) {
        if (page.id === 'page-assets') return 'ASSETS';
        if (page.id === 'page-banner') return 'BANNER';
        return page.id;
      }
      function applyCurrentPage() {
        document.querySelectorAll('.page-section').forEach(p => refreshPage(p));
      }
      function escapeHtml(s) {
        return String(s).replace(/[&<>"']/g, c => ({
          '&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'
        })[c]);
      }

      function cancelHealthCheck(clearList = false) {
        healthToken++;
        const summary = document.getElementById('adminHealthSummary');
        if (summary) summary.hidden = true;
        if (clearList) {
          const list = document.getElementById('adminHealthList');
          if (list) list.innerHTML = '';
        }
      }

      function openPanel() {
        // 1. Tính toán transform-origin để "mọc" ra từ nút setting
        const dlg = panel.querySelector('.admin-panel__dialog');
        if (dlg) {
          const savedTransition = dlg.style.transition;
          const savedTransform = dlg.style.transform;
          dlg.style.transition = 'none';
          dlg.style.transform = 'none';
          
          const dlgRect = dlg.getBoundingClientRect();
          
          dlg.style.transform = savedTransform;
          dlg.style.transition = savedTransition;

          const activePage = document.querySelector('.page-section.active');
          const btn = activePage ? activePage.querySelector('.admin-toggle') : document.querySelector('.admin-toggle');
          
          if (btn) {
            const btnRect = btn.getBoundingClientRect();
            const originX = btnRect.left + btnRect.width / 2 - dlgRect.left;
            const originY = btnRect.top + btnRect.height / 2 - dlgRect.top;
            dlg.style.transformOrigin = `${originX}px ${originY}px`;
          }
        }

        // 2. Kích hoạt panel
        panel.classList.add('active');
        document.querySelectorAll('.admin-toggle').forEach(b => b.classList.add('is-open'));
        
        const ctx = getContext();
        if (ctx) {
          currentEditEvent = ctx.eventKey;
          currentEditCat = ctx.page.id === 'page-banner' ? 'banner' : 'assets';
        }
        const activeTab = panel.querySelector('[data-tab].active')?.dataset.tab || 'edit';
        if (activeTab === 'edit')   refreshEditForm();
        if (activeTab === 'health') runHealthCheck();
        if (activeTab === 'data')   refreshJson();
      }
      
      function closePanel() {
        cancelHealthCheck(false);
        panel.classList.remove('active');
        document.querySelectorAll('.admin-toggle').forEach(b => b.classList.remove('is-open'));
        document.querySelectorAll('.page-section').forEach(page => applyPageStyles(page));
      }

      document.querySelectorAll('.admin-toggle').forEach(btn => {
        btn.addEventListener('click', () => {
          panel.classList.contains('active') ? closePanel() : openPanel();
        });
      });
      panel.querySelectorAll('[data-admin-close]').forEach(el => el.addEventListener('click', closePanel));
      document.addEventListener('keydown', e => {
        if ((e.ctrlKey || e.metaKey) && e.shiftKey && e.key.toLowerCase() === 'a') {
          e.preventDefault();
          panel.classList.contains('active') ? closePanel() : openPanel();
        }
        if (e.key === 'Escape' && panel.classList.contains('active')) closePanel();
      });

      panel.querySelectorAll('[data-tab]').forEach(btn => {
        btn.addEventListener('click', () => {
          cancelHealthCheck(false);
          panel.querySelectorAll('[data-tab]').forEach(b => b.classList.toggle('active', b === btn));
          panel.querySelectorAll('[data-panel]').forEach(p => { p.hidden = p.dataset.panel !== btn.dataset.tab; });
          if (btn.dataset.tab === 'edit')   refreshEditForm();
          if (btn.dataset.tab === 'health') runHealthCheck();
          if (btn.dataset.tab === 'data')   refreshJson();
        });
      });

      const tagMainInput        = panel.querySelector('[data-admin-field="tagMain"]');
      const tagShineInput       = panel.querySelector('[data-admin-field="tagShine"]');
      const bannerMainInput     = panel.querySelector('[data-admin-field="bannerMain"]');
      const bannerShineInput    = panel.querySelector('[data-admin-field="bannerShine"]');
      const btnMainInput        = panel.querySelector('[data-admin-field="btnMain"]');
      const btnShineInput       = panel.querySelector('[data-admin-field="btnShine"]');
      const btnBannerMainInput  = panel.querySelector('[data-admin-field="btnBannerMain"]');
      const btnBannerShineInput = panel.querySelector('[data-admin-field="btnBannerShine"]');

      function fillFields() {
        panel.querySelectorAll('[data-admin-field]').forEach(input => {
          const part = input.dataset.adminField;
          if (part === 'tagMain')         { input.value = IMG.tagStyle?.main  || '#ff3a3a'; return; }
          if (part === 'tagShine')        { input.value = IMG.tagStyle?.shine || '#ffffff'; return; }
          if (part === 'bannerMain')      { input.value = IMG.bannerTitleStyle?.main  || '#ffb347'; return; }
          if (part === 'bannerShine')     { input.value = IMG.bannerTitleStyle?.shine || '#ffffff'; return; }
          if (part === 'btnMain')         { input.value = IMG.btnStyle?.main  || '#ffd23a'; return; }
          if (part === 'btnShine')        { input.value = IMG.btnStyle?.shine || '#fff8e0'; return; }
          if (part === 'btnBannerMain')   { input.value = IMG.btnBannerStyle?.main  || '#ff2d2d'; return; }
          if (part === 'btnBannerShine')  { input.value = IMG.btnBannerStyle?.shine || '#ffffff'; return; }
          if (part === 'bodyBg') { input.value = IMG.bodyBg ?? ''; return; }
          input.value = IMG[part]?.[currentEditEvent] ?? '';
        });
      }
      function updateCatView() {
        panel.querySelectorAll('[data-cat-tab]').forEach(b => {
          b.classList.toggle('active', b.dataset.catTab === currentEditCat);
        });
        panel.querySelectorAll('[data-cat-group]').forEach(g => {
          g.hidden = g.dataset.catGroup !== currentEditCat;
        });
      }
      function refreshEditForm() {
        panel.querySelectorAll('[data-event-tab]').forEach(b => {
          b.classList.toggle('active', b.dataset.eventTab === currentEditEvent);
        });
        const ctx = getContext();
        const pageName   = ctx ? getPageName(ctx.page) : '—';
        const viewingKey = ctx ? ctx.eventKey : '—';
        document.getElementById('adminCurrentInfo').textContent =
          `Đang sửa: Sự kiện #${currentEditEvent} · Trang hiển thị: ${pageName} (SK #${viewingKey})`;
        fillFields();
        updateCatView();
        previewAll();
      }

      function previewTagColor() {
        const tag = document.querySelector('#page-assets [data-tag]');
        if (tag) {
          tag.style.setProperty('--tag-main',  tagMainInput?.value  || '#ff3a3a');
          tag.style.setProperty('--tag-shine', tagShineInput?.value || '#ffffff');
        }
      }
      function previewAssetsBtnColor() {
        const btn = document.querySelector('#page-assets .event-btn.active');
        if (btn) {
          btn.style.setProperty('--btn-main',  btnMainInput?.value  || '#ffd23a');
          btn.style.setProperty('--btn-shine', btnShineInput?.value || '#fff8e0');
        }
      }
      function previewBannerTitleColor() {
        const label = document.querySelector('#page-banner [data-banner-label]');
        if (label) {
          label.style.setProperty('--banner-main',  bannerMainInput?.value  || '#ffb347');
          label.style.setProperty('--banner-shine', bannerShineInput?.value || '#ffffff');
        }
      }
      function previewBannerBtnColor() {
        const btn = document.querySelector('#page-banner .event-btn.active');
        if (btn) {
          btn.style.setProperty('--btn-main',  btnBannerMainInput?.value  || '#ff2d2d');
          btn.style.setProperty('--btn-shine', btnBannerShineInput?.value || '#ffffff');
        }
      }
      function previewAll() {
        previewTagColor();
        previewAssetsBtnColor();
        previewBannerTitleColor();
        previewBannerBtnColor();
      }

      tagMainInput?.addEventListener('input', previewTagColor);
      tagShineInput?.addEventListener('input', previewTagColor);
      btnMainInput?.addEventListener('input', previewAssetsBtnColor);
      btnShineInput?.addEventListener('input', previewAssetsBtnColor);
      bannerMainInput?.addEventListener('input', previewBannerTitleColor);
      bannerShineInput?.addEventListener('input', previewBannerTitleColor);
      btnBannerMainInput?.addEventListener('input', previewBannerBtnColor);
      btnBannerShineInput?.addEventListener('input', previewBannerBtnColor);

      function saveEditForm() {
        let changed = false;
        panel.querySelectorAll('[data-admin-field]').forEach(input => {
          const part = input.dataset.adminField;
          const val  = input.value.trim();

          if (part === 'tagMain')        { if (IMG.tagStyle.main  !== val) { IMG.tagStyle.main  = val; changed = true; } return; }
          if (part === 'tagShine')       { if (IMG.tagStyle.shine !== val) { IMG.tagStyle.shine = val; changed = true; } return; }
          if (part === 'bannerMain')     { if (IMG.bannerTitleStyle.main  !== val) { IMG.bannerTitleStyle.main  = val; changed = true; } return; }
          if (part === 'bannerShine')    { if (IMG.bannerTitleStyle.shine !== val) { IMG.bannerTitleStyle.shine = val; changed = true; } return; }
          if (part === 'btnMain')        { if (IMG.btnStyle.main  !== val) { IMG.btnStyle.main  = val; changed = true; } return; }
          if (part === 'btnShine')       { if (IMG.btnStyle.shine !== val) { IMG.btnStyle.shine = val; changed = true; } return; }
          if (part === 'btnBannerMain')  { if (IMG.btnBannerStyle.main  !== val) { IMG.btnBannerStyle.main  = val; changed = true; } return; }
          if (part === 'btnBannerShine') { if (IMG.btnBannerStyle.shine !== val) { IMG.btnBannerStyle.shine = val; changed = true; } return; }

          if (part === 'bodyBg') {
            if (IMG.bodyBg !== val) { IMG.bodyBg = val; applyBodyBg(); changed = true; }
            return;
          }

          if (!IMG[part]) IMG[part] = {};
          if (IMG[part][currentEditEvent] !== val) {
            IMG[part][currentEditEvent] = val;
            changed = true;
          }
        });
        if (changed) {
          applyCurrentPage();
          showToast('✅ Đã lưu');
        } else {
          showToast('Không có thay đổi');
        }
      }

      function revertEditForm() {
        refreshEditForm();
        document.querySelectorAll('.page-section').forEach(page => applyPageStyles(page));
        showToast('↺ Đã khôi phục giá trị');
      }

      panel.querySelectorAll('[data-event-tab]').forEach(btn => {
        btn.addEventListener('click', () => {
          currentEditEvent = btn.dataset.eventTab;
          refreshEditForm();
        });
      });
      panel.querySelectorAll('[data-cat-tab]').forEach(btn => {
        btn.addEventListener('click', () => {
          currentEditCat = btn.dataset.catTab;
          updateCatView();
        });
      });

      /* HEALTH CHECK */
      function runHealthCheck() {
        const myToken = ++healthToken;
        const list = document.getElementById('adminHealthList');
        const summaryEl = document.getElementById('adminHealthSummary');
        const okEl = document.getElementById('healthOkCount');
        const errEl = document.getElementById('healthErrCount');
        const totalEl = document.getElementById('healthTotalCount');

        list.innerHTML = '';
        summaryEl.hidden = true;

        const groups = [
          { title: '🌐 Toàn trang', items: [{ label: 'Body Background', url: IMG.bodyBg }] },
          { title: '📦 ASSETS · Sự kiện 1', items: [
            { label: 'Logo', url: IMG.logo?.[1] },
            { label: 'Tab', url: IMG.tab?.[1] },
            { label: 'Background', url: IMG.bg?.[1] },
          ]},
          { title: '📦 ASSETS · Sự kiện 2', items: [
            { label: 'Logo', url: IMG.logo?.[2] },
            { label: 'Tab', url: IMG.tab?.[2] },
            { label: 'Background', url: IMG.bg?.[2] },
          ]},
          { title: '📦 ASSETS · Sự kiện 3', items: [
            { label: 'Logo', url: IMG.logo?.[3] },
            { label: 'Tab', url: IMG.tab?.[3] },
            { label: 'Background', url: IMG.bg?.[3] },
          ]},
          { title: '🎨 BANNER · Sự kiện 1', items: [
            { label: '16:9', url: IMG.banner169?.[1] },
            { label: 'Portrait', url: IMG.bannerPortrait?.[1] },
            { label: '256×107', url: IMG.banner256?.[1] },
            { label: '512×182', url: IMG.banner512?.[1] },
          ]},
          { title: '🎨 BANNER · Sự kiện 2', items: [
            { label: '16:9', url: IMG.banner169?.[2] },
            { label: 'Portrait', url: IMG.bannerPortrait?.[2] },
            { label: '256×107', url: IMG.banner256?.[2] },
            { label: '512×182', url: IMG.banner512?.[2] },
          ]},
          { title: '🎨 BANNER · Sự kiện 3', items: [
            { label: '16:9', url: IMG.banner169?.[3] },
            { label: 'Portrait', url: IMG.bannerPortrait?.[3] },
            { label: '256×107', url: IMG.banner256?.[3] },
            { label: '512×182', url: IMG.banner512?.[3] },
          ]},
        ];

        let total = 0, ok = 0, err = 0;
        groups.forEach(g => total += g.items.length);
        totalEl.textContent = total;
        okEl.textContent = 0;
        errEl.textContent = 0;
        summaryEl.hidden = false;

        groups.forEach(group => {
          const section = document.createElement('div');
          section.className = 'admin-health-section';

          const title = document.createElement('div');
          title.className = 'admin-section-title';
          title.textContent = group.title;
          section.appendChild(title);

          group.items.forEach(({ label, url }) => {
            const item = document.createElement('div');
            item.className = 'admin-health-item admin-health-item--loading';
            item.innerHTML = `
              <span class="admin-health-item__name">${escapeHtml(label)}</span>
              <span class="admin-health-item__url" title="${escapeHtml(url || '')}">${escapeHtml(url || '(trống)')}</span>
              <span class="admin-health-item__status">…</span>
            `;
            section.appendChild(item);
            const statusEl = item.querySelector('.admin-health-item__status');

            if (!url) {
              item.className = 'admin-health-item admin-health-item--err';
              statusEl.textContent = '✕ Trống';
              err++; errEl.textContent = err;
              return;
            }
            const img = new Image();
            const start = Date.now();
            img.onload = () => {
              if (healthToken !== myToken) return;
              item.className = 'admin-health-item admin-health-item--ok';
              statusEl.textContent = `✓ ${img.naturalWidth}×${img.naturalHeight} · ${Date.now() - start}ms`;
              ok++; okEl.textContent = ok;
            };
            img.onerror = () => {
              if (healthToken !== myToken) return;
              item.className = 'admin-health-item admin-health-item--err';
              statusEl.textContent = '✕ Lỗi tải';
              err++; errEl.textContent = err;
            };
            img.src = url;
          });

          list.appendChild(section);
        });
      }

      function refreshJson() {
        document.getElementById('adminJson').value = JSON.stringify(IMG, null, 2);
      }
      function copyJson() {
        const ta = document.getElementById('adminJson');
        ta.select();
        const done = () => showToast('📋 Đã sao chép');
        if (navigator.clipboard?.writeText) {
          navigator.clipboard.writeText(ta.value).then(done, () => {
            document.execCommand('copy'); done();
          });
        } else {
          document.execCommand('copy'); done();
        }
      }
      function downloadJson() {
        const blob = new Blob([JSON.stringify(IMG, null, 2)], { type: 'application/json' });
        const a = document.createElement('a');
        a.href = URL.createObjectURL(blob);
        a.download = 'ff-config-' + Date.now() + '.json';
        a.click();
        URL.revokeObjectURL(a.href);
        showToast('⬇ Đã tải file');
      }
      function importJson() {
        try {
          const data = JSON.parse(document.getElementById('adminJson').value);
          if (!data || typeof data !== 'object') throw new Error('Không phải object');

          ['tagStyle', 'bannerTitleStyle', 'btnStyle', 'btnBannerStyle'].forEach(k => {
            if (data[k] && data[k][1] && !data[k].main) {
              data[k] = { main: data[k][1].main, shine: data[k][1].shine };
            }
          });

          Object.keys(data).forEach(k => {
            const isObj = data[k] && typeof data[k] === 'object' && !Array.isArray(data[k]);
            if (isObj && IMG[k] && typeof IMG[k] === 'object') {
              Object.assign(IMG[k], data[k]);
            } else {
              IMG[k] = data[k];
            }
          });
          applyBodyBg();
          applyCurrentPage();
          showToast('✅ Đã nhập cấu hình');
          refreshJson();
        } catch (err) {
          showToast('❌ JSON lỗi: ' + err.message);
        }
      }
      function resetAll() {
        if (!confirm('Reset toàn bộ cấu hình ảnh về mặc định?')) return;
        Object.keys(DEFAULT_IMG).forEach(k => {
          if (DEFAULT_IMG[k] && typeof DEFAULT_IMG[k] === 'object' && !Array.isArray(DEFAULT_IMG[k])) {
            IMG[k] = JSON.parse(JSON.stringify(DEFAULT_IMG[k]));
          } else {
            IMG[k] = DEFAULT_IMG[k];
          }
        });
        applyBodyBg();
        applyCurrentPage();
        showToast('⚠ Đã reset toàn bộ');
        refreshJson();
        refreshEditForm();
      }

      panel.querySelectorAll('[data-admin-action]').forEach(btn => {
        btn.addEventListener('click', () => {
          const a = btn.dataset.adminAction;
          if (a === 'save')          saveEditForm();
          else if (a === 'revert')   revertEditForm();
          else if (a === 'checkHealth')  runHealthCheck();
          else if (a === 'cancelHealth') { cancelHealthCheck(true); showToast('✕ Đã hủy kiểm tra'); }
          else if (a === 'copyJson')     copyJson();
          else if (a === 'downloadJson') downloadJson();
          else if (a === 'importJson')   importJson();
          else if (a === 'resetAll')     resetAll();
        });
      });
    })();

    /* ══════════════════════════════════════════════════════════════
       🛡️ CHỐNG LƯU ẢNH
       ══════════════════════════════════════════════════════════════ */
    document.querySelectorAll('img, .text-image-box').forEach(img => {
      img.addEventListener('contextmenu', e => e.preventDefault());
      img.addEventListener('dragstart',   e => e.preventDefault());
      img.addEventListener('selectstart', e => e.preventDefault());
    });
  </script>
</body>
</html>
