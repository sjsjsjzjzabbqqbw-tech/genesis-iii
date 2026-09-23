<!DOCTYPE html>
<html lang="fa" dir="rtl"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<title>Genesis III — آرشیو جهان‌ها</title>
<link rel="preconnect" href="https://fonts.googleapis.com/">
<link rel="preconnect" href="https://fonts.gstatic.com/" crossorigin="">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500&family=Vazirmatn:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#0a0908;
    --bg-alt:#131009;
    --panel:#1a1610;
    --panel-2:#211b13;
    --gold:#c9a227;
    --gold-bright:#e0be55;
    --gold-dim:rgba(201,162,39,0.35);
    --line:rgba(201,162,39,0.14);
    --crimson:#7d2b32;
    --text:#ece6d8;
    --text-dim:#9a9284;
    --text-faint:#65605a;
    --radius:2px;
    --ease:cubic-bezier(.22,.61,.36,1);
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--bg);
    color:var(--text);
    font-family:'Vazirmatn',sans-serif;
    line-height:1.75;
    overflow-x:hidden;
    -webkit-font-smoothing:antialiased;
  }
  ::selection{background:var(--gold-dim); color:var(--gold-bright);}
  a{color:inherit; text-decoration:none;}
  button{font-family:inherit; cursor:pointer;}
  .mono{font-family:'JetBrains Mono',monospace;}
  .wrap{max-width:1100px; margin:0 auto; padding:0 24px;}
  img{display:block; max-width:100%;}

  /* texture */
  body::before{
    content:'';
    position:fixed; inset:0;
    background-image:radial-gradient(circle at 1px 1px, rgba(255,255,255,0.025) 1px, transparent 0);
    background-size:3px 3px;
    pointer-events:none;
    z-index:1;
    opacity:.5;
  }

  /* ---------- NAV ---------- */
  .nav{
    position:fixed; top:0; right:0; left:0; z-index:100;
    display:flex; align-items:center; justify-content:space-between;
    padding:18px 24px;
    background:linear-gradient(to bottom, rgba(10,9,8,.92), rgba(10,9,8,0));
    backdrop-filter:blur(2px);
    transition:background .3s var(--ease), border-color .3s var(--ease);
    border-bottom:1px solid transparent;
  }
  .nav.scrolled{background:rgba(10,9,8,.88); border-color:var(--line);}
  .nav .brand{
    font-family:'JetBrains Mono',monospace;
    font-size:15px; letter-spacing:.14em; font-weight:500;
    color:var(--gold-bright);
  }
  .nav .brand span{color:var(--text-faint);}
  .nav-links{display:flex; gap:32px; font-size:14.5px; color:var(--text-dim);}
  .nav-links a{position:relative; padding:4px 0; transition:color .25s;}
  .nav-links a:hover, .nav-links a.active{color:var(--gold-bright);}
  .nav-links a::after{
    content:''; position:absolute; right:0; bottom:0; height:1px; width:0;
    background:var(--gold); transition:width .3s var(--ease);
  }
  .nav-links a:hover::after{width:100%;}
  .nav-burger{
    display:none; flex-direction:column; gap:5px; background:none; border:none; padding:8px; z-index:200;
  }
  .nav-burger span{width:22px; height:1.5px; background:var(--gold-bright); transition:.3s var(--ease);}
  .nav-burger.open span:nth-child(1){transform:translateY(6.5px) rotate(45deg);}
  .nav-burger.open span:nth-child(2){opacity:0;}
  .nav-burger.open span:nth-child(3){transform:translateY(-6.5px) rotate(-45deg);}

  .mobile-menu{
    position:fixed; inset:0; background:var(--bg); z-index:150;
    display:flex; flex-direction:column; align-items:center; justify-content:center; gap:34px;
    transform:translateY(-100%); transition:transform .45s var(--ease);
  }
  .mobile-menu.open{transform:translateY(0);}
  .mobile-menu a{font-size:22px; color:var(--text); letter-spacing:.02em;}

  /* ---------- HERO ---------- */
  .hero{
    position:relative; min-height:100svh; display:flex; flex-direction:column;
    align-items:center; justify-content:center; text-align:center;
    padding:120px 24px 60px; overflow:hidden;
  }
  #emberCanvas{position:absolute; inset:0; z-index:0; opacity:.55;}
  .sigil{
    position:absolute; top:50%; left:50%; z-index:0;
    width:min(70vw,560px); height:min(70vw,560px);
    transform:translate(-50%,-50%);
    opacity:.16;
    animation:spin 90s linear infinite;
    will-change:transform;
  }
  @keyframes spin{to{transform:translate(-50%,-50%) rotate(360deg);}}
  @media (prefers-reduced-motion:reduce){.sigil{animation:none;} #emberCanvas{display:none;}}

  .hero-inner{position:relative; z-index:2;}
  .eyebrow-line{
    display:flex; align-items:center; justify-content:center; gap:12px;
    margin-bottom:22px; opacity:0; transform:translateY(10px);
    animation:reveal .9s var(--ease) .1s forwards;
  }
  .eyebrow-line .dash{width:28px; height:1px; background:var(--gold-dim);}
  .eyebrow-line span{font-size:13px; color:var(--text-dim); letter-spacing:.08em;}
  .hero h1{
    font-size:clamp(42px,10vw,88px);
    font-weight:800; line-height:1.05;
    color:var(--text);
    opacity:0; transform:translateY(16px);
    animation:reveal 1s var(--ease) .25s forwards;
  }
  .hero h1 em{
    font-style:normal; color:transparent;
    -webkit-text-stroke:1.5px var(--gold-bright);
  }
  .hero p{
    max-width:520px; margin:22px auto 0; color:var(--text-dim); font-size:16.5px;
    opacity:0; transform:translateY(14px);
    animation:reveal 1s var(--ease) .45s forwards;
  }
  @keyframes reveal{to{opacity:1; transform:translateY(0);}}
  .hero-cta{
    margin-top:36px; display:inline-flex; align-items:center; gap:10px;
    padding:14px 30px; border:1px solid var(--gold-dim); color:var(--gold-bright);
    font-size:14.5px; letter-spacing:.04em; border-radius:var(--radius);
    opacity:0; transform:translateY(12px);
    animation:reveal 1s var(--ease) .62s forwards;
    transition:background .3s var(--ease), border-color .3s var(--ease);
  }
  .hero-cta:hover{background:rgba(201,162,39,.08); border-color:var(--gold);}

  .hero-stats{
    position:relative; z-index:2;
    display:flex; gap:0; margin-top:70px;
    border-top:1px solid var(--line);
    opacity:0; transform:translateY(10px);
    animation:reveal 1s var(--ease) .8s forwards;
  }
  .hero-stats div{
    padding:18px 30px; text-align:center; border-left:1px solid var(--line);
  }
  .hero-stats div:last-child{border-left:none;}
  .hero-stats .num{font-family:'JetBrains Mono',monospace; font-size:22px; color:var(--gold-bright);}
  .hero-stats .lbl{font-size:12px; color:var(--text-faint); margin-top:4px;}

  .scroll-hint{
    position:absolute; bottom:26px; right:50%; transform:translateX(50%);
    display:flex; flex-direction:column; align-items:center; gap:8px; z-index:2;
  }
  .scroll-hint .line{width:1px; height:34px; background:linear-gradient(var(--gold-dim), transparent); animation:scrollLine 2s ease-in-out infinite;}
  @keyframes scrollLine{0%,100%{opacity:.3;} 50%{opacity:1;}}

  /* ---------- SECTION SHELL ---------- */
  section{position:relative; z-index:2;}
  .section{padding:100px 0 40px;}
  .section-head{margin-bottom:44px;}
  .section-head .kicker{
    display:flex; align-items:center; gap:10px; margin-bottom:14px;
    font-family:'JetBrains Mono',monospace; font-size:12.5px; color:var(--gold);
  }
  .section-head .kicker .dash{width:20px; height:1px; background:var(--gold-dim);}
  .section-head h2{font-size:clamp(28px,5vw,40px); font-weight:700;}
  .section-head p{color:var(--text-dim); max-width:560px; margin-top:14px; font-size:15.5px;}

  .reveal{opacity:0; transform:translateY(24px); transition:opacity .7s var(--ease), transform .7s var(--ease);}
  .reveal.in{opacity:1; transform:translateY(0);}

  /* divider */
  .divider{position:relative; height:70px; display:flex; align-items:center; justify-content:center;}
  .divider .v{width:1px; height:0; background:var(--gold-dim); transition:height 1s var(--ease);}
  .divider.in .v{height:60px;}

  /* ---------- PROJECT TABS ---------- */
  .tabbar{
    display:flex; gap:8px; margin-bottom:38px; flex-wrap:wrap;
    border-bottom:1px solid var(--line); padding-bottom:0;
  }
  .tabbar button{
    background:none; border:none; color:var(--text-faint); font-size:14.5px;
    padding:10px 4px; margin-left:28px; position:relative;
    transition:color .25s;
  }
  .tabbar button::after{
    content:''; position:absolute; right:0; bottom:-1px; height:1.5px; width:0;
    background:var(--gold-bright); transition:width .3s var(--ease);
  }
  .tabbar button.active{color:var(--text);}
  .tabbar button.active::after{width:100%;}
  .tabbar .count{font-family:'JetBrains Mono',monospace; font-size:11px; color:var(--text-faint); margin-right:5px;}

  .panels{position:relative;}
  .panel{display:none;}
  .panel.active{display:block; animation:fadeIn .5s var(--ease);}
  @keyframes fadeIn{from{opacity:0; transform:translateY(8px);} to{opacity:1; transform:translateY(0);}}

  .empty-card{
    border:1px dashed var(--line); border-radius:var(--radius);
    padding:60px 24px; text-align:center; color:var(--text-faint);
  }
  .empty-card .glyph{font-size:26px; color:var(--gold-dim); margin-bottom:14px; font-family:'JetBrains Mono',monospace;}
  .empty-card h3{color:var(--text-dim); font-size:16px; font-weight:500; margin-bottom:8px;}
  .empty-card p{font-size:13.5px; max-width:340px; margin:0 auto; color:var(--text-faint);}

  /* project card - live */
  .proj-card{
    display:grid; grid-template-columns:1fr 1.3fr; gap:0;
    border:1px solid var(--line); border-radius:var(--radius);
    background:var(--panel); overflow:hidden; cursor:pointer;
    transition:border-color .35s var(--ease), transform .35s var(--ease);
    position:relative;
  }
  .proj-card:hover{border-color:var(--gold-dim); transform:translateY(-3px);}
  .proj-card .media{
    position:relative; min-height:220px;
    background:
      radial-gradient(circle at 30% 20%, rgba(201,162,39,.14), transparent 55%),
      linear-gradient(155deg, #241d13, #0d0b08 70%);
    display:flex; align-items:center; justify-content:center;
    border-left:1px solid var(--line);
    overflow:hidden;
  }
  .proj-card .media .glyph-big{
    font-size:70px; font-family:'JetBrains Mono',monospace; color:var(--gold-dim);
    transition:transform .5s var(--ease), color .5s var(--ease);
  }
  .proj-card:hover .media .glyph-big{transform:scale(1.08) rotate(4deg); color:var(--gold-bright);}
  .proj-card .media::after{
    content:''; position:absolute; inset:0;
    background:linear-gradient(180deg, transparent 60%, rgba(0,0,0,.5));
  }
  .proj-card .body{padding:28px 30px; display:flex; flex-direction:column;}
  .status-pill{
    display:inline-flex; align-items:center; gap:6px; align-self:flex-start;
    font-family:'JetBrains Mono',monospace; font-size:11px; letter-spacing:.05em;
    color:var(--gold-bright); border:1px solid var(--gold-dim); padding:4px 10px; border-radius:20px;
    margin-bottom:16px;
  }
  .status-pill .dot{width:6px; height:6px; border-radius:50%; background:var(--gold-bright); animation:pulse 2s ease-in-out infinite;}
  @keyframes pulse{0%,100%{opacity:1;} 50%{opacity:.35;}}
  .proj-card h3{font-size:24px; font-weight:700; margin-bottom:8px;}
  .proj-card .sub{color:var(--text-dim); font-size:14px; margin-bottom:18px;}
  .proj-card .meta{display:flex; gap:22px; margin-top:auto; padding-top:18px; border-top:1px solid var(--line); font-size:12.5px; color:var(--text-faint);}
  .proj-card .meta b{color:var(--text-dim); display:block; font-weight:500; margin-bottom:2px;}
  .proj-card .enter{
    margin-top:20px; display:inline-flex; align-items:center; gap:8px;
    color:var(--gold-bright); font-size:14px; align-self:flex-start;
  }
  .proj-card .enter .arrow{transition:transform .3s var(--ease);}
  .proj-card:hover .enter .arrow{transform:translateX(-4px);}

  @media (max-width:680px){
    .proj-card{grid-template-columns:1fr;}
    .proj-card .media{min-height:160px; border-left:none; border-bottom:1px solid var(--line);}
  }

  /* ---------- GENESIS SECTION ---------- */
  .principles{display:grid; grid-template-columns:repeat(2,1fr); gap:1px; background:var(--line); border:1px solid var(--line); margin-top:10px;}
  .principles div{background:var(--bg); padding:26px 24px;}
  .principles .n{font-family:'JetBrains Mono',monospace; font-size:12px; color:var(--gold);}
  .principles h4{margin-top:10px; font-size:16px; font-weight:600;}
  .principles p{margin-top:8px; font-size:13.5px; color:var(--text-dim);}
  @media (max-width:640px){.principles{grid-template-columns:1fr;}}

  .channel-cta{
    margin-top:56px; border:1px solid var(--line); border-radius:var(--radius);
    padding:34px 30px; display:flex; align-items:center; justify-content:space-between; gap:20px; flex-wrap:wrap;
    background:linear-gradient(120deg, rgba(201,162,39,.05), transparent);
  }
  .channel-cta div h4{font-size:18px; margin-bottom:6px;}
  .channel-cta div p{font-size:13.5px; color:var(--text-dim);}
  .btn-gold{
    background:var(--gold); color:#151006; font-weight:600; font-size:14px;
    padding:13px 26px; border-radius:var(--radius); border:none; display:inline-flex; gap:8px; align-items:center;
    transition:background .25s;
  }
  .btn-gold:hover{background:var(--gold-bright);}

  /* ---------- SUPPORT / FAQ ---------- */
  .faq-item{border-bottom:1px solid var(--line);}
  .faq-item button{
    width:100%; text-align:right; background:none; border:none; padding:20px 0;
    display:flex; justify-content:space-between; align-items:center; color:var(--text); font-size:15.5px;
  }
  .faq-item .plus{font-family:'JetBrains Mono',monospace; color:var(--gold); transition:transform .3s var(--ease); font-size:18px;}
  .faq-item.open .plus{transform:rotate(45deg);}
  .faq-a{max-height:0; overflow:hidden; transition:max-height .4s var(--ease);}
  .faq-item.open .faq-a{max-height:200px;}
  .faq-a p{padding-bottom:20px; color:var(--text-dim); font-size:14.5px; max-width:600px;}

  .support-grid{display:grid; grid-template-columns:1fr 1fr; gap:20px; margin-top:50px;}
  .support-card{border:1px solid var(--line); padding:26px; border-radius:var(--radius);}
  .support-card h4{font-size:16px; margin-bottom:8px;}
  .support-card p{font-size:13.5px; color:var(--text-dim); margin-bottom:16px;}
  .support-card a{font-size:13.5px; color:var(--gold-bright); display:inline-flex; align-items:center; gap:6px;}
  @media (max-width:640px){.support-grid{grid-template-columns:1fr;}}

  footer{
    border-top:1px solid var(--line); padding:34px 0 90px; margin-top:60px;
    display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:14px;
    font-size:12.5px; color:var(--text-faint); font-family:'JetBrains Mono',monospace;
  }

  /* ---------- LOTM OVERLAY ---------- */
  .overlay{
    position:fixed; inset:0; z-index:300; background:var(--bg);
    transform:translateY(100%); transition:transform .55s var(--ease);
    overflow-y:auto; -webkit-overflow-scrolling:touch;
  }
  .overlay.open{transform:translateY(0);}
  .overlay-head{
    position:sticky; top:0; z-index:5; background:rgba(10,9,8,.94); backdrop-filter:blur(4px);
    border-bottom:1px solid var(--line); padding:16px 24px;
  }
  .overlay-head .top{display:flex; justify-content:space-between; align-items:center;}
  .overlay-head .title{font-size:15px; font-weight:600;}
  .overlay-head .title span{display:block; font-family:'JetBrains Mono',monospace; font-size:11px; color:var(--gold); font-weight:400; margin-bottom:2px;}
  .close-btn{
    width:34px; height:34px; border:1px solid var(--line); border-radius:50%; background:none;
    color:var(--text-dim); font-size:16px; display:flex; align-items:center; justify-content:center;
    transition:.25s;
  }
  .close-btn:hover{color:var(--gold-bright); border-color:var(--gold-dim);}
  .otabs{display:flex; gap:22px; margin-top:16px; overflow-x:auto; scrollbar-width:none;}
  .otabs::-webkit-scrollbar{display:none;}
  .otabs button{background:none; border:none; color:var(--text-faint); font-size:13.5px; padding:6px 2px; white-space:nowrap; position:relative;}
  .otabs button.active{color:var(--gold-bright);}
  .otabs button.active::after{content:''; position:absolute; bottom:-1px; right:0; left:0; height:1.5px; background:var(--gold-bright);}

  .obody{padding:40px 24px 100px; max-width:780px; margin:0 auto;}
  .opanel{display:none;}
  .opanel.active{display:block; animation:fadeIn .5s var(--ease);}
  .opanel h3{font-size:22px; margin-bottom:16px; font-weight:700;}
  .opanel h4{font-size:16px; margin:28px 0 10px; font-weight:600; color:var(--gold-bright);}
  .opanel p{color:var(--text-dim); font-size:15px; margin-bottom:14px;}
  .lede{font-size:16.5px; color:var(--text); border-right:2px solid var(--gold-dim); padding-right:16px; margin-bottom:28px;}

  .path-chips{display:flex; flex-wrap:wrap; gap:8px; margin:18px 0 24px;}
  .path-chips button{
    border:1px solid var(--line); background:var(--panel); color:var(--text-dim); font-size:13px;
    padding:8px 16px; border-radius:20px; transition:.25s;
  }
  .path-chips button.active{border-color:var(--gold); color:var(--gold-bright); background:rgba(201,162,39,.08);}
  .path-detail{border:1px solid var(--line); border-radius:var(--radius); padding:22px; background:var(--panel);}
  .path-detail .seq{font-family:'JetBrains Mono',monospace; font-size:12px; color:var(--gold); margin-bottom:6px;}
  .path-detail h5{font-size:17px; margin-bottom:10px;}
  .path-detail p{font-size:14px; color:var(--text-dim); margin-bottom:0;}

  .flow{display:flex; flex-direction:column; gap:0; margin:20px 0;}
  .flow-step{display:flex; gap:16px; padding:14px 0; border-bottom:1px solid var(--line);}
  .flow-step:last-child{border-bottom:none;}
  .flow-step .n{font-family:'JetBrains Mono',monospace; color:var(--gold); font-size:13px; min-width:22px;}
  .flow-step b{display:block; font-size:14.5px; margin-bottom:3px;}
  .flow-step span{font-size:13.5px; color:var(--text-dim);}

  .dev-empty{border:1px dashed var(--line); padding:40px 20px; text-align:center; color:var(--text-faint); font-size:14px; border-radius:var(--radius);}

  @media (max-width:640px){
    .nav-links{display:none;}
    .nav-burger{display:flex;}
    .section{padding:70px 0 20px;}
    .tabbar button{margin-left:16px; font-size:13.5px;}
  }

/* ===== LOTM POWER GUI — TRI COLOR ===== */
:root{--pblue:#48a7ff;--pyellow:#f1c84e;--pred:#ff5063;--pwhite:#efe8d8;--pdim:#9d9587;--pline:rgba(255,255,255,.075)}
.power-intro{position:relative;padding:28px 26px;margin-bottom:18px;border:1px solid rgba(72,167,255,.18);border-radius:12px;overflow:hidden;background:linear-gradient(120deg,rgba(72,167,255,.065),rgba(241,200,78,.045),rgba(255,80,99,.055))}
.power-intro:before{content:"";position:absolute;inset:0;background:linear-gradient(110deg,transparent 10%,rgba(72,167,255,.12),rgba(241,200,78,.08),rgba(255,80,99,.10),transparent 90%);background-size:220% 100%;animation:powerSweep 8s linear infinite}
@keyframes powerSweep{0%{background-position:-120% 0}100%{background-position:120% 0}}
.power-intro>*{position:relative;z-index:1}.power-kicker{font:11px 'JetBrains Mono',monospace;letter-spacing:.14em;color:var(--pblue);margin-bottom:5px}.power-intro h3{font-size:26px;margin-bottom:8px}.power-intro .lede{margin:0;max-width:900px}
.power-modebar{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin:18px 0 24px;padding:5px;border:1px solid var(--pline);background:rgba(0,0,0,.13);border-radius:12px}
.power-mode{border:1px solid transparent;background:transparent;color:var(--pdim);padding:12px 15px;border-radius:9px;text-align:right;transition:.28s;position:relative;overflow:hidden}
.power-mode:before{content:"";position:absolute;inset:0;background:linear-gradient(90deg,rgba(72,167,255,.09),rgba(241,200,78,.07),rgba(255,80,99,.09));transform:translateX(110%);transition:.5s}
.power-mode:hover:before,.power-mode.active:before{transform:translateX(0)}
.power-mode>*{position:relative;z-index:1}.power-mode span{display:block;font-size:14px;font-weight:700}.power-mode small{display:block;margin-top:2px;font-size:10.5px;color:inherit}
.power-mode.active{color:var(--pwhite);border-color:rgba(241,200,78,.32);box-shadow:0 0 22px rgba(241,200,78,.06)}
.power-section-view{margin-bottom:20px}.power-section-title{display:flex;gap:12px;align-items:flex-start;margin:0 0 13px}.power-index{font:12px 'JetBrains Mono',monospace;color:var(--pyellow);padding-top:4px}.power-section-title h4{margin:0;font-size:18px}.power-section-title p{margin-top:2px;color:var(--pdim);font-size:12px}
.power-group-list{display:flex;flex-direction:column;gap:10px}
.power-group{border:1px solid var(--pline);border-radius:12px;overflow:hidden;background:rgba(255,255,255,.018);position:relative}
.power-group:after{content:"";position:absolute;inset:0;pointer-events:none;background:linear-gradient(115deg,transparent 12%,rgba(72,167,255,.045),rgba(241,200,78,.045),rgba(255,80,99,.045),transparent 86%);background-size:240% 100%;animation:groupFlow 10s linear infinite}
@keyframes groupFlow{0%{background-position:-120% 0}100%{background-position:120% 0}}
.power-group-btn{width:100%;border:0;background:transparent;color:var(--pwhite);padding:15px 16px;display:grid;grid-template-columns:auto 1fr auto;gap:12px;text-align:right;align-items:center;position:relative;z-index:2}
.power-orb{width:12px;height:12px;border-radius:50%;background:var(--pblue);box-shadow:0 0 16px rgba(72,167,255,.55);animation:orbTri 6s ease-in-out infinite}
@keyframes orbTri{0%,100%{background:var(--pblue);box-shadow:0 0 16px rgba(72,167,255,.6)}33%{background:var(--pyellow);box-shadow:0 0 16px rgba(241,200,78,.55)}66%{background:var(--pred);box-shadow:0 0 16px rgba(255,80,99,.55)}}
.power-group-name strong{display:block;font-size:14.5px}.power-group-name small{display:block;margin-top:2px;color:var(--pdim);font-size:11px}.power-plus{font-size:18px;color:var(--pdim);transition:.3s}
.power-group.open .power-plus{transform:rotate(45deg);color:var(--pyellow)}
.power-group-content{display:grid;grid-template-rows:0fr;position:relative;z-index:2;transition:grid-template-rows .48s var(--ease)}
.power-group.open .power-group-content{grid-template-rows:1fr}
.power-group-inner{min-height:0;overflow:hidden;padding:0 14px;transition:padding .48s var(--ease)}.power-group.open .power-group-inner{padding:0 14px 15px}
.power-path-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(195px,1fr));gap:8px}
.power-path-btn{border:1px solid rgba(255,255,255,.07);background:rgba(0,0,0,.16);color:var(--pdim);border-radius:9px;padding:10px 12px;text-align:right;min-height:44px;display:flex;align-items:center;justify-content:space-between;gap:10px;transition:.25s}
.power-path-btn:hover{border-color:rgba(72,167,255,.3);color:var(--pwhite);transform:translateY(-1px)}.power-path-btn.active{border-color:rgba(241,200,78,.38);color:var(--pwhite);background:linear-gradient(90deg,rgba(72,167,255,.07),rgba(241,200,78,.08),rgba(255,80,99,.06))}
.power-path-btn .arrow{color:var(--pblue);font-size:17px}.power-path-btn.active .arrow{color:var(--pyellow)}
.power-detail{margin-top:12px;border-top:1px solid var(--pline);padding-top:12px}
.path-banner{border:1px solid rgba(72,167,255,.16);background:linear-gradient(120deg,rgba(72,167,255,.04),rgba(241,200,78,.025),rgba(255,80,99,.035));padding:20px;border-radius:10px;margin-bottom:10px}
.path-banner h3{font-size:22px;margin-bottom:6px}.path-banner p{color:var(--pdim);font-size:13px;line-height:1.9}
.path-status{display:flex;gap:7px;flex-wrap:wrap;margin-top:10px}.path-status span{font-size:10px;color:var(--pdim);padding:4px 8px;border:1px solid var(--pline);border-radius:999px}
.missing-note{margin-top:10px;border:1px dashed rgba(255,80,99,.22);padding:12px 13px;color:#aa9e91;font-size:12px;border-radius:8px;background:rgba(255,80,99,.025)}
.rich-seqs{display:flex;flex-direction:column;gap:8px}.rich-seq{--accent:var(--pblue);border:1px solid color-mix(in srgb,var(--accent) 28%,transparent);border-radius:10px;overflow:hidden;background:rgba(255,255,255,.014);box-shadow:inset 3px 0 0 var(--accent)}
.rich-seq:nth-child(3n+2){--accent:var(--pyellow)}.rich-seq:nth-child(3n){--accent:var(--pred)}
.rich-seq-head{width:100%;border:0;background:transparent;color:var(--pwhite);padding:14px 15px;display:grid;grid-template-columns:auto 1fr auto;align-items:center;gap:12px;text-align:right}
.rich-seq-num{font:11px 'JetBrains Mono',monospace;color:var(--accent)}.rich-seq-name{font-size:13.5px;font-weight:700}.rich-seq-plus{color:var(--pdim);font-size:17px;transition:.3s}.rich-seq.open .rich-seq-plus{transform:rotate(45deg);color:var(--accent)}
.rich-seq-body{display:grid;grid-template-rows:0fr;transition:grid-template-rows .55s var(--ease)}.rich-seq.open .rich-seq-body{grid-template-rows:1fr}
.rich-seq-body-inner{min-height:0;overflow:hidden;padding:0 15px}.rich-seq.open .rich-seq-body-inner{padding:0 15px 18px}
.rich-text{border-top:1px solid var(--pline);padding-top:13px;color:#aaa194;font-size:13.1px;line-height:1.95}
.rich-text p{margin:0 0 10px}.rich-text p:last-child{margin-bottom:0}.rich-text h4{font-size:12px;color:var(--accent);margin:14px 0 7px}.rich-text strong{color:#eae2d4}
.rich-text .src-spacer{display:none}
.ns-card{border:1px solid var(--pline);border-radius:12px;overflow:hidden;background:rgba(255,255,255,.018);position:relative}.ns-card.open .power-plus{transform:rotate(45deg);color:var(--pred)}
.ns-content{display:grid;grid-template-rows:0fr;transition:grid-template-rows .48s var(--ease)}.ns-card.open .ns-content{grid-template-rows:1fr}.ns-inner{min-height:0;overflow:hidden;padding:0 14px}.ns-card.open .ns-inner{padding:0 14px 15px}
@media(max-width:760px){.power-modebar{grid-template-columns:1fr}.power-path-grid{grid-template-columns:1fr 1fr}.power-intro{padding:20px}.rich-text{font-size:12.8px}}
@media(max-width:480px){.power-path-grid{grid-template-columns:1fr}.power-intro h3{font-size:22px}}


/* ================= GLOBAL TRI-COLOR MOTION SYSTEM ================= */
:root{
  --theme-blue:#3d9cff;
  --theme-blue-soft:rgba(61,156,255,.17);
  --theme-yellow:#f2c94c;
  --theme-yellow-soft:rgba(242,201,76,.15);
  --theme-red:#ff5262;
  --theme-red-soft:rgba(255,82,98,.15);
  --tri-gradient:linear-gradient(90deg,var(--theme-blue),var(--theme-yellow),var(--theme-red),var(--theme-blue));
}
body{
  background:
    radial-gradient(circle at 8% 12%,rgba(61,156,255,.075),transparent 24%),
    radial-gradient(circle at 90% 24%,rgba(242,201,76,.06),transparent 23%),
    radial-gradient(circle at 48% 92%,rgba(255,82,98,.065),transparent 25%),
    var(--bg);
}
body::after{
  content:'';position:fixed;inset:-20%;z-index:0;pointer-events:none;
  background:
    radial-gradient(circle at 20% 30%,rgba(61,156,255,.10),transparent 24%),
    radial-gradient(circle at 78% 22%,rgba(242,201,76,.08),transparent 22%),
    radial-gradient(circle at 62% 76%,rgba(255,82,98,.09),transparent 24%);
  filter:blur(46px);animation:globalAurora 18s ease-in-out infinite alternate;
}
@keyframes globalAurora{0%{transform:translate3d(-2%,-1%,0) scale(1)}50%{transform:translate3d(2%,2%,0) scale(1.035)}100%{transform:translate3d(-1%,4%,0) scale(1.07)}}
main,footer,.section,.hero,.nav{position:relative;z-index:2}
.overlay{position:fixed!important;inset:0;z-index:300!important;}
.section-head .kicker,.section-head h2,.proj-card h3,.support-card h3,.opanel h3,.opanel h4{
  color:var(--text);
  animation:none;
}
@keyframes triText{0%{background-position:0% 50%}100%{background-position:240% 50%}}
.nav{border-image:var(--tri-gradient) 1;border-bottom-width:1px}
.nav .brand{color:var(--theme-blue)!important;text-shadow:0 0 14px rgba(61,156,255,.22)}
.nav .brand span{color:var(--theme-red)!important}
.nav-links a:hover,.nav-links a.active{color:var(--theme-yellow)!important}
.nav-links a::after{background:var(--tri-gradient)!important;background-size:300% 100%;animation:triShiftBar 6s linear infinite}
@keyframes triShiftBar{0%{background-position:0% 50%}100%{background-position:300% 50%}}
.hero h1 em{background:var(--tri-gradient);background-size:300% 100%;-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;-webkit-text-stroke:0}
.hero h1{
  color:var(--text)!important;
  -webkit-text-fill-color:var(--text)!important;
  background:none!important;
  -webkit-background-clip:border-box!important;
  background-clip:border-box!important;
  text-shadow:0 0 28px rgba(74,163,255,.08);
}
.hero h1 em{
  color:transparent!important;
  -webkit-text-fill-color:transparent!important;
  background:var(--tri-gradient)!important;
  background-size:300% 100%!important;
  -webkit-background-clip:text!important;
  background-clip:text!important;
  -webkit-text-stroke:0!important;
  animation:triText 8s linear infinite!important;
}

.hero-cta::before,.proj-card::before,.support-card::before,.empty-card::before,.flow-step::before,.dev-empty::before{
  content:'';position:absolute;inset:-1px;border-radius:inherit;padding:1px;background:var(--tri-gradient);background-size:300% 100%;
  animation:triBorder 8s linear infinite;-webkit-mask:linear-gradient(#000 0 0) content-box,linear-gradient(#000 0 0);-webkit-mask-composite:xor;mask-composite:exclude;pointer-events:none;
}
@keyframes triBorder{0%{background-position:0% 50%}100%{background-position:300% 50%}}
.hero-cta:hover{background:linear-gradient(90deg,var(--theme-blue-soft),var(--theme-yellow-soft),var(--theme-red-soft))!important;border-color:transparent!important}
.hero-stats div:nth-child(1) .num{color:var(--theme-blue)}.hero-stats div:nth-child(2) .num{color:var(--theme-yellow)}.hero-stats div:nth-child(3) .num{color:var(--theme-red)}
.status-pill{background:linear-gradient(90deg,var(--theme-blue-soft),transparent);border-color:rgba(61,156,255,.32)!important}.status-pill .dot{background:var(--theme-blue)!important;box-shadow:0 0 12px var(--theme-blue)}
.tabbar button.active{color:var(--theme-yellow)!important}.tabbar button::after{background:var(--tri-gradient)!important;background-size:300% 100%;animation:triShiftBar 6s linear infinite}
.divider .v{background:var(--tri-gradient)!important;background-size:100% 300%;animation:triVertical 5s linear infinite}
@keyframes triVertical{0%{background-position:50% 0}100%{background-position:50% 300%}}
.flow-step:nth-child(3n+1) .n{color:var(--theme-blue)!important}.flow-step:nth-child(3n+2) .n{color:var(--theme-yellow)!important}.flow-step:nth-child(3n) .n{color:var(--theme-red)!important}
.opanel .lede{border-right-color:var(--theme-blue)!important}
.otab-btn.active{color:var(--theme-yellow)!important}.otab-btn.active::after{background:var(--tri-gradient)!important;background-size:300% 100%;animation:triShiftBar 6s linear infinite}
.close-btn:hover{color:var(--theme-red)!important;border-color:rgba(255,82,98,.4)!important}
footer{border-top:1px solid rgba(61,156,255,.12)!important}footer div:first-child{color:var(--theme-blue)!important}footer div:last-child{color:var(--theme-red)!important}


.section-head .kicker,.section-head h2,.proj-card h3,.support-card h3,.opanel h3,.opanel h4{
  position:relative;
}
.section-head h2::after,.opanel h3::after,.opanel h4::after{
  content:'';display:block;width:54px;height:2px;margin-top:9px;border-radius:999px;
  background:var(--tri-gradient);background-size:300% 100%;animation:triShiftBar 7s linear infinite;
}

/* Ecosystem */
.ecosystem-intro{position:relative;overflow:hidden;border:1px solid rgba(61,156,255,.16);background:linear-gradient(135deg,rgba(61,156,255,.045),rgba(242,201,76,.025),rgba(255,82,98,.04));padding:28px;border-radius:12px;margin-bottom:22px}
.ecosystem-intro::after{content:'';position:absolute;inset:0;background:linear-gradient(110deg,transparent,rgba(61,156,255,.06),rgba(242,201,76,.05),rgba(255,82,98,.06),transparent);background-size:220% 100%;animation:ecoSweep 8s linear infinite;pointer-events:none}
@keyframes ecoSweep{0%{background-position:-120%}100%{background-position:120%}}
.eco-kicker{font-family:'JetBrains Mono',monospace;font-size:11px;letter-spacing:.08em;color:var(--theme-blue);margin-bottom:6px}
.eco-grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:12px}
.eco-card{position:relative;overflow:hidden;border:1px solid var(--line);background:linear-gradient(145deg,rgba(255,255,255,.025),rgba(255,255,255,.008));border-radius:12px;padding:22px;box-shadow:0 12px 30px rgba(0,0,0,.16);transition:transform .3s,border-color .3s,box-shadow .3s}
.eco-card:hover{transform:translateY(-2px);border-color:rgba(242,201,76,.27);box-shadow:0 18px 38px rgba(0,0,0,.2)}
.eco-card-wide{grid-column:1/-1}
.eco-card:nth-child(3n+1){box-shadow:inset 3px 0 0 var(--theme-blue),0 12px 30px rgba(0,0,0,.16)}
.eco-card:nth-child(3n+2){box-shadow:inset 3px 0 0 var(--theme-yellow),0 12px 30px rgba(0,0,0,.16)}
.eco-card:nth-child(3n){box-shadow:inset 3px 0 0 var(--theme-red),0 12px 30px rgba(0,0,0,.16)}
.eco-card-head{display:flex;align-items:center;gap:10px;margin-bottom:14px}.eco-num{font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--theme-yellow);min-width:27px}.eco-card:nth-child(3n+1) .eco-num{color:var(--theme-blue)}.eco-card:nth-child(3n) .eco-num{color:var(--theme-red)}
.eco-card h4{margin:0!important;font-size:18px!important}.eco-card p{font-size:14px!important;line-height:1.95!important}
.eco-bullets{display:grid;gap:10px;margin-top:12px}.eco-bullet{display:grid;grid-template-columns:120px 1fr;gap:10px;padding:11px 0;border-top:1px solid var(--line)}.eco-bullet:first-child{border-top:0;padding-top:0}.eco-bullet b{color:var(--text)}.eco-bullet span{color:var(--text-dim);font-size:13.5px;line-height:1.9}
.eco-timeline{position:relative;padding-right:16px}.eco-timeline::before{content:'';position:absolute;right:3px;top:6px;bottom:6px;width:1px;background:linear-gradient(var(--theme-blue),var(--theme-yellow),var(--theme-red))}
.eco-event{position:relative;padding:0 14px 18px 0}.eco-event::before{content:'';position:absolute;right:-1px;top:7px;width:7px;height:7px;border-radius:50%;background:var(--theme-blue);box-shadow:0 0 12px var(--theme-blue)}.eco-event:nth-child(2)::before{background:var(--theme-yellow);box-shadow:0 0 12px var(--theme-yellow)}.eco-event:nth-child(3)::before{background:var(--theme-red);box-shadow:0 0 12px var(--theme-red)}
.eco-event span{font-weight:700;color:var(--text);font-size:14px}.eco-event p{margin-top:5px}
.eco-mechanics{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin:16px 0}.eco-mech{border:1px solid var(--line);padding:15px;border-radius:10px;background:rgba(0,0,0,.12);display:flex;gap:10px}.eco-mech-no{font-family:'JetBrains Mono',monospace;color:var(--theme-yellow);font-size:12px}.eco-mech:nth-child(1) .eco-mech-no{color:var(--theme-blue)}.eco-mech:nth-child(3) .eco-mech-no{color:var(--theme-red)}.eco-mech b{display:block;font-size:13px;color:var(--text);margin-bottom:4px}.eco-mech p{font-size:12.5px!important;margin:0!important}.eco-note{border-top:1px solid var(--line);padding-top:14px;margin-top:12px}
.eco-footer-note{display:flex;gap:12px;align-items:flex-start;margin-top:16px;border:1px dashed rgba(242,201,76,.22);border-radius:12px;padding:16px;background:linear-gradient(90deg,rgba(61,156,255,.025),rgba(242,201,76,.025),rgba(255,82,98,.025))}.eco-footer-mark{font-size:22px;color:var(--theme-yellow)}.eco-footer-note b{color:var(--theme-yellow)}.eco-footer-note p{font-size:12.5px!important;margin:2px 0 0!important}
@media(max-width:760px){.eco-grid{grid-template-columns:1fr}.eco-card-wide{grid-column:auto}.eco-mechanics{grid-template-columns:1fr}.eco-bullet{grid-template-columns:1fr;gap:3px}}


/* HERO TITLE SAFETY OVERRIDE */
.hero .hero-inner h1{display:block;visibility:visible!important;opacity:0;color:var(--text)!important;}
.hero .hero-inner h1 em{display:inline-block;visibility:visible!important;}


/* Modal safety fixes */
.overlay{
  position:fixed!important;
  inset:0!important;
  z-index:300!important;
  transform:translateY(100%);
  pointer-events:none;
}
.overlay.open{
  transform:translateY(0);
  pointer-events:auto;
}
#lotmCard{position:relative;z-index:3;cursor:pointer;}
#lotmCard .enter{position:relative;z-index:4;}

.main-abilities{margin-top:14px;padding-top:14px;border-top:1px solid rgba(255,255,255,.07);position:relative;z-index:2}.main-abilities-title{font-size:12px;color:var(--live-yellow);font-weight:700;margin-bottom:9px}.main-ability-list{display:flex;flex-wrap:wrap;gap:7px}.main-ability-list span{display:inline-flex;align-items:center;padding:6px 10px;border:1px solid rgba(74,163,255,.17);border-radius:999px;background:linear-gradient(90deg,rgba(74,163,255,.055),rgba(240,200,75,.045),rgba(255,77,94,.055));font-size:11.5px;color:var(--text-dim);transition:.25s}.main-ability-list span:hover{color:var(--text);border-color:rgba(240,200,75,.28);transform:translateY(-1px)}

/* Stable route detail layer */
.power-detail{display:block;visibility:visible;opacity:1;min-width:0}.path-banner{border:1px solid rgba(241,200,78,.18);border-radius:12px;padding:20px;margin-top:12px;background:linear-gradient(135deg,rgba(72,167,255,.045),rgba(241,200,78,.035),rgba(255,80,99,.04));position:relative;overflow:hidden}.path-banner-kicker{font-size:10px;letter-spacing:.1em;color:var(--pyellow);margin-bottom:5px}.path-banner h3{font-size:24px;color:var(--pwhite);margin-bottom:12px}.main-abilities{border-top:1px solid var(--pline);padding-top:12px}.main-abilities-title{font-size:11px;color:var(--pwhite);font-weight:700;margin-bottom:8px}.main-ability-list{display:flex;flex-wrap:wrap;gap:6px}.main-ability-list span{font-size:11.5px;padding:5px 9px;border:1px solid rgba(72,167,255,.18);border-radius:999px;color:var(--pdim);background:rgba(72,167,255,.035)}.main-ability-list span:nth-child(3n+2){border-color:rgba(241,200,78,.22);background:rgba(241,200,78,.035)}.main-ability-list span:nth-child(3n){border-color:rgba(255,80,99,.2);background:rgba(255,80,99,.035)}.path-empty{margin-top:12px;border:1px dashed var(--pline);border-radius:10px;padding:26px;text-align:center;color:var(--pdim);background:rgba(255,255,255,.012)}.path-empty-icon{font:24px 'JetBrains Mono',monospace;color:var(--pred);margin-bottom:7px}.path-empty strong{display:block;color:var(--pwhite);font-size:13px;margin-bottom:4px}.path-empty p{font-size:12px}

/* Genesis global live palette stabilization */
:root{--live-blue:#4aa3ff;--live-yellow:#f0c84b;--live-red:#ff4d5e;}
body{background:radial-gradient(circle at 15% 10%,rgba(74,163,255,.06),transparent 25%),radial-gradient(circle at 80% 20%,rgba(240,200,75,.05),transparent 24%),radial-gradient(circle at 55% 85%,rgba(255,77,94,.05),transparent 28%),var(--bg);}
.nav a.active,.tab.active{border-color:rgba(240,200,75,.38)!important;box-shadow:0 0 20px rgba(74,163,255,.08),inset 0 0 18px rgba(255,77,94,.03);}
.button-primary,.btn-primary{background:linear-gradient(90deg,rgba(74,163,255,.16),rgba(240,200,75,.12),rgba(255,77,94,.14));border-color:rgba(240,200,75,.34);}
.card,.panel,.feature-card{border-color:rgba(255,255,255,.07);}
.overlay{position:fixed!important;inset:0;z-index:1000;}

  /* ---- v15: classes + friendlier sequence text ---- */
  .cls-en{font:500 10.5px 'JetBrains Mono',monospace;color:var(--pdim);letter-spacing:.08em;margin-inline-start:6px;font-style:normal}
  .power-path-btn > span:first-child{display:flex;flex-direction:column;gap:1px;text-align:right}
  .pgroup{font-size:10px;color:var(--pdim);font-weight:400}
  .path-tags{display:flex;flex-wrap:wrap;gap:6px;margin:0 0 10px}
  .ptag{font-size:10.5px;color:var(--pdim);padding:3px 9px;border:1px solid var(--pline);border-radius:999px}
  .ptag-class{color:var(--pyellow);border-color:rgba(241,200,78,.32)}
  .path-banner .path-line{color:var(--pwhite);font-size:14px;line-height:2;margin:0 0 4px}
  .rich-text .glance{background:rgba(255,255,255,.035);border-right:2px solid var(--accent);padding:9px 12px;border-radius:6px;color:var(--pwhite);margin-bottom:12px}
  .rich-text .glance b{color:var(--accent)}

  /* ---- v17: header + mobile menu ---- */
  .nav{position:fixed!important; top:0; right:0; left:0; z-index:400!important;}
  .nav.menu-open{background:transparent!important; backdrop-filter:none!important; -webkit-backdrop-filter:none!important; border-image:none!important; border-bottom-color:transparent!important;}
  html.menu-open body{overflow:hidden;}
  .nav-burger{
    display:none; position:relative; width:46px; height:46px; padding:0; margin:-4px 0;
    flex-direction:column; align-items:center; justify-content:center; gap:5px;
    background:rgba(255,255,255,.03); border:1px solid rgba(255,255,255,.1); border-radius:13px;
    -webkit-tap-highlight-color:transparent; cursor:pointer; z-index:5;
    transition:border-color .3s var(--ease), background .3s var(--ease), box-shadow .3s var(--ease), transform .2s var(--ease);
  }
  .nav-burger::before{
    content:''; position:absolute; inset:-1px; border-radius:inherit; padding:1px; pointer-events:none;
    background:var(--tri-gradient); background-size:300% 100%;
    -webkit-mask:linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0); -webkit-mask-composite:xor; mask-composite:exclude;
    opacity:0; transition:opacity .35s var(--ease);
  }
  .nav-burger:hover, .nav-burger:focus-visible, .nav-burger.open{background:rgba(255,255,255,.05); box-shadow:0 0 22px rgba(61,156,255,.10), 0 0 22px rgba(255,82,98,.07);}
  .nav-burger:hover::before, .nav-burger:focus-visible::before, .nav-burger.open::before{opacity:1; animation:triShiftBar 6s linear infinite;}
  .nav-burger:active{transform:scale(.94);}
  .nav-burger:focus-visible{outline:2px solid var(--theme-yellow); outline-offset:3px;}
  .nav-burger span{
    display:block; height:2px; border-radius:2px; background:var(--theme-yellow); transform-origin:center;
    transition:transform .38s var(--ease), opacity .2s var(--ease), width .3s var(--ease), background .3s var(--ease);
  }
  .nav-burger span:nth-child(1){width:20px;}
  .nav-burger span:nth-child(2){width:14px; align-self:flex-start; margin-inline-start:13px;}
  .nav-burger span:nth-child(3){width:20px;}
  .nav-burger:hover span:nth-child(2){width:20px; margin-inline-start:0; align-self:center;}
  .nav-burger.open span:nth-child(1){transform:translateY(7px) rotate(45deg); background:var(--theme-blue);}
  .nav-burger.open span:nth-child(2){opacity:0; transform:scaleX(0); width:20px; margin-inline-start:0; align-self:center;}
  .nav-burger.open span:nth-child(3){transform:translateY(-7px) rotate(-45deg); background:var(--theme-red);}
  @media (max-width:640px){ .nav-links{display:none;} .nav-burger{display:flex;} }
  @media (min-width:641px){ .mobile-menu{display:none!important;} }

  .mobile-menu{
    position:fixed; inset:0; z-index:350; overflow-y:auto; overscroll-behavior:contain;
    background:rgba(10,9,8,.97); -webkit-backdrop-filter:blur(16px); backdrop-filter:blur(16px);
    display:block; transform:none; visibility:hidden; pointer-events:none;
    clip-path:circle(0% at 46px 38px);
    transition:clip-path .7s var(--ease), visibility 0s linear .7s;
  }
  .mobile-menu.open{visibility:visible; pointer-events:auto; clip-path:circle(150% at 46px 38px); transition:clip-path .8s var(--ease), visibility 0s;}
  .mm-bg{position:absolute; inset:0; overflow:hidden; pointer-events:none;
    background:
      radial-gradient(circle at 8% 4%, rgba(61,156,255,.16), transparent 34%),
      radial-gradient(circle at 92% 46%, rgba(242,201,76,.08), transparent 30%),
      radial-gradient(circle at 70% 100%, rgba(255,82,98,.13), transparent 38%);}
  .mm-sigil{position:absolute; top:58%; left:50%; width:min(120vw,520px); height:min(120vw,520px); transform:translate(-50%,-50%); opacity:.07; animation:mmspin 90s linear infinite;}
  @keyframes mmspin{to{transform:translate(-50%,-50%) rotate(360deg);}}
  .mm-inner{position:relative; z-index:2; min-height:100%; display:flex; flex-direction:column; padding:104px 28px 34px; max-width:520px; margin:0 auto;}
  .mm-label{display:flex; align-items:center; gap:10px; font-size:11px; letter-spacing:.32em; color:var(--text-faint); margin-bottom:10px;
    opacity:0; transform:translateY(8px); transition:opacity .5s var(--ease) .25s, transform .5s var(--ease) .25s;}
  .mm-label span{width:26px; height:1px; background:var(--tri-gradient); background-size:300% 100%; animation:triShiftBar 6s linear infinite;}
  .mm-list{list-style:none; margin:0; padding:0;}
  .mm-list li{border-bottom:1px solid var(--line); opacity:0; transform:translateY(16px);
    transition:opacity .55s var(--ease), transform .55s var(--ease);}
  .mobile-menu.open .mm-label, .mobile-menu.open .mm-list li, .mobile-menu.open .mm-foot{opacity:1; transform:none;}
  .mobile-menu.open .mm-list li{transition-delay:calc(var(--i) * 70ms + 220ms);}
  .mm-list li:first-child{border-top:1px solid var(--line);}
  .mm-list a.m-link{position:relative; display:grid; grid-template-columns:34px 1fr auto; align-items:center; gap:14px; padding:20px 4px; color:var(--text); font-size:inherit; letter-spacing:0; -webkit-tap-highlight-color:transparent; transition:background .3s var(--ease);}
  .mm-no{font-size:12px; color:var(--theme-blue); opacity:.9;}
  .mm-list li:nth-child(3n+2) .mm-no{color:var(--theme-yellow);}
  .mm-list li:nth-child(3n) .mm-no{color:var(--theme-red);}
  .mm-txt b{display:block; font-size:26px; font-weight:700; line-height:1.3;}
  .mm-txt small{display:block; margin-top:1px; font-size:12.5px; color:var(--text-faint);}
  .mm-arrow{font-size:18px; color:var(--text-faint); transition:transform .3s var(--ease), color .3s var(--ease);}
  .mm-list a.m-link::after{content:''; position:absolute; right:0; bottom:-1px; height:1px; width:0; background:var(--tri-gradient); background-size:300% 100%; transition:width .45s var(--ease);}
  .mm-list a.m-link:active{background:rgba(255,255,255,.03);}
  .mm-list a.m-link:hover .mm-arrow, .mm-list a.m-link:focus-visible .mm-arrow{transform:translateX(-5px); color:var(--theme-yellow);}
  .mm-list a.m-link.active{color:var(--theme-yellow);}
  .mm-list a.m-link.active::after{width:100%; animation:triShiftBar 6s linear infinite;}
  .mm-list a.m-link.active .mm-arrow{color:var(--theme-yellow);}
  .mm-list a.m-link:focus-visible{outline:2px solid var(--theme-yellow); outline-offset:-2px; border-radius:6px;}
  .mm-foot{margin-top:auto; padding-top:38px; display:flex; flex-direction:column; align-items:stretch; gap:12px;
    opacity:0; transform:translateY(14px); transition:opacity .6s var(--ease) .55s, transform .6s var(--ease) .55s;}
  .mm-cta{display:block; text-align:center; padding:15px 20px;}
  .mm-handle{text-align:center; font-size:12px; letter-spacing:.14em; color:var(--text-faint);}
  @media (prefers-reduced-motion:reduce){
    .mobile-menu, .mobile-menu.open{transition:none; clip-path:none;}
    .mobile-menu:not(.open){opacity:0;} .mm-sigil{animation:none;}
    .mm-list li, .mm-label, .mm-foot{transition:none!important;}
    .nav-burger::before{animation:none!important;}
  }
</style>
</head>
<body style="">

<canvas id="emberCanvas" width="1626" style="height: 100%; width: 100%;" height="1486"></canvas>

<nav class="nav" id="nav" aria-label="ناوبری اصلی">
  <div class="brand">GENESIS <span>III</span></div>
  <div class="nav-links">
    <a href="#home" class="nav-link">خانه</a>
    <a href="#projects" class="nav-link active">پروژه‌ها</a>
    <a href="#genesis" class="nav-link">جنسیس</a>
    <a href="#support" class="nav-link">پشتیبانی</a>
  </div>
  <button class="nav-burger" id="burger" type="button" aria-label="باز کردن منو" aria-expanded="false" aria-controls="mobileMenu"><span></span><span></span><span></span></button>
</nav>

<div class="mobile-menu" id="mobileMenu" aria-hidden="true">
  <div class="mm-bg" aria-hidden="true">
    <svg class="mm-sigil" viewBox="0 0 200 200" fill="none">
      <circle cx="100" cy="100" r="92" stroke="#c9a227" stroke-width="0.6"></circle>
      <circle cx="100" cy="100" r="70" stroke="#c9a227" stroke-width="0.4"></circle>
      <polygon points="100,20 172,145 28,145" stroke="#c9a227" stroke-width="0.6"></polygon>
      <polygon points="100,180 28,55 172,55" stroke="#c9a227" stroke-width="0.6"></polygon>
      <circle cx="100" cy="100" r="6" fill="#c9a227"></circle>
    </svg>
  </div>
  <div class="mm-inner">
    <div class="mm-label mono"><span></span>MENU</div>
    <ul class="mm-list">
      <li style="--i:0"><a href="#home" class="m-link"><span class="mm-no mono">01</span><span class="mm-txt"><b>خانه</b><small>شروع</small></span><span class="mm-arrow" aria-hidden="true">←</span></a></li>
      <li style="--i:1"><a href="#projects" class="m-link"><span class="mm-no mono">02</span><span class="mm-txt"><b>پروژه‌ها</b><small>رول‌پلی‌ها و آرشیو</small></span><span class="mm-arrow" aria-hidden="true">←</span></a></li>
      <li style="--i:2"><a href="#genesis" class="m-link"><span class="mm-no mono">03</span><span class="mm-txt"><b>جنسیس</b><small>Genesis چیست؟</small></span><span class="mm-arrow" aria-hidden="true">←</span></a></li>
      <li style="--i:3"><a href="#support" class="m-link"><span class="mm-no mono">04</span><span class="mm-txt"><b>پشتیبانی</b><small>سوال، گزارش و تماس</small></span><span class="mm-arrow" aria-hidden="true">←</span></a></li>
    </ul>
    <div class="mm-foot">
      <a class="btn-gold mm-cta" href="https://t.me/Genesis_III" target="_blank" rel="noopener">عضویت در کانال تلگرام ←</a>
      <div class="mm-handle mono">t.me/Genesis_III</div>
    </div>
  </div>
</div>

<!-- HOME -->
<section id="home" class="hero">
  <svg class="sigil" viewBox="0 0 200 200" fill="none">
    <circle cx="100" cy="100" r="92" stroke="#c9a227" stroke-width="0.6"></circle>
    <circle cx="100" cy="100" r="70" stroke="#c9a227" stroke-width="0.4"></circle>
    <polygon points="100,20 172,145 28,145" stroke="#c9a227" stroke-width="0.6"></polygon>
    <polygon points="100,180 28,55 172,55" stroke="#c9a227" stroke-width="0.6"></polygon>
    <circle cx="100" cy="100" r="6" fill="#c9a227"></circle>
  </svg>
  <div class="hero-inner">
    <div class="eyebrow-line"><span class="mono">t.me/Genesis_III</span></div>
    <h1>GENESIS <em>III</em></h1>
    <p>ما فقط داستان تعریف نمی‌کنیم؛ جهان می‌سازیم — با سیستم‌های خودش، قانون‌های خودش و آدم‌هایی که داخلش زندگی می‌کنند.</p>
    <a href="#projects" class="hero-cta">مشاهده پروژه‌ها ←</a>
  </div>
  <div class="hero-stats">
    <div><div class="num mono" data-count="1">1</div><div class="lbl">در حال ساخت</div></div>
    <div><div class="num mono" data-count="0">0</div><div class="lbl">فعال</div></div>
    <div><div class="num mono">∞</div><div class="lbl">در آینده</div></div>
  </div>
  <div class="scroll-hint"><div class="line"></div></div>
</section>

<!-- PROJECTS -->
<section id="projects" class="section">
  <div class="wrap">
    <div class="section-head reveal in">
      <div class="kicker"><span class="dash"></span>پروژه‌های Genesis</div>
      <h2>رول‌پلی‌ها</h2>
      <p>هر پروژه یک جهان مستقل است، با سیستم قدرت و لور خودش. اینجا وضعیت واقعی هرکدام را می‌بینید — بدون اغراق.</p>
    </div>

    <div class="tabbar reveal in">
      <button class="tab-btn active" data-tab="building">در حال ساخت <span class="count mono">1</span></button>
      <button class="tab-btn" data-tab="active">فعال <span class="count mono">0</span></button>
      <button class="tab-btn" data-tab="future">آینده <span class="count mono">0</span></button>
      <button class="tab-btn" data-tab="archived">آرشیو <span class="count mono">0</span></button>
    </div>

    <div class="panels reveal in">
      <div class="panel active" data-panel="building">
        <div class="proj-card" id="lotmCard">
          <div class="media"><div class="glyph-big">✶</div></div>
          <div class="body">
            <div class="status-pill"><span class="dot"></span>در حال توسعه</div>
            <h3>ارباب اسرار</h3>
            <div class="sub">رول‌پلی تعاملی بر پایه‌ی دنیای ویکتوریایی و اسرارآمیز رمان</div>
            <div class="meta">
              <div><b>ژانر</b>معمایی / فانتزی</div>
              <div><b>فرمت</b>رول‌پلی تلگرامی</div>
              <div><b>منبع</b>هر دو کتاب</div>
            </div>
            <div class="enter">ورود به آرشیو پروژه <span class="arrow">←</span></div>
          </div>
        </div>
      </div>

      <div class="panel" data-panel="active">
        <div class="empty-card">
          <div class="glyph">∅</div>
          <h3>در حال حاضر پروژه‌ی فعالی وجود ندارد</h3>
          <p>پروژه‌های جدید Genesis پس از تکمیل مرحله‌ی توسعه، اینجا قرار می‌گیرند.</p>
        </div>
      </div>

      <div class="panel" data-panel="future">
        <div class="empty-card">
          <div class="glyph">◌</div>
          <h3>آرشیو پروژه‌های آینده</h3>
          <p>در حال حاضر پروژه‌ای برای معرفی در این بخش ثبت نشده است.</p>
        </div>
      </div>

      <div class="panel" data-panel="archived">
        <div class="empty-card">
          <div class="glyph">▢</div>
          <h3>هیچ پروژه‌ای در آرشیو نیست</h3>
          <p>این بخش برای پروژه‌های تکمیل‌شده یا متوقف‌شده استفاده خواهد شد.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="divider"><div class="v"></div></div>

<!-- GENESIS -->
<section id="genesis" class="section">
  <div class="wrap">
    <div class="section-head reveal">
      <div class="kicker"><span class="dash"></span>درباره</div>
      <h2>Genesis چیست؟</h2>
      <p>Genesis صرفاً یک گروه رول‌پلی نیست. هدف این است که یک اثر داستانی را به یک سیستم قابل‌بازی تبدیل کنیم — با قانون‌هایی که واقعاً روی سرنوشت شخصیت‌ها اثر می‌گذارند.</p>
    </div>
    <div class="principles reveal">
      <div><div class="n mono">جهان اول</div><h4>جهان، پایه‌ی همه‌چیز است</h4><p>قبل از هر شخصیت، جهانی طراحی می‌شود که منطق خودش را دارد.</p></div>
      <div><div class="n mono">سیستم مهم است</div><h4>قدرت بدون قانون معنی ندارد</h4><p>هر سیستم قدرت، مرز و هزینه‌ی مشخص دارد؛ نه فقط توانایی.</p></div>
      <div><div class="n mono">نتیجه دارد</div><h4>هر انتخاب، پیامد دارد</h4><p>داستان بر اساس تصمیم بازیکن‌ها شکل می‌گیرد، نه یک خط از پیش نوشته‌شده.</p></div>
      <div><div class="n mono">توسعه‌ی مداوم</div><h4>Genesis همیشه در حال ساخت است</h4><p>پروژه‌ها به‌مرور کامل‌تر می‌شوند؛ چیزی یک‌شبه منتشر نمی‌شود.</p></div>
    </div>

    <div class="channel-cta reveal">
      <div>
        <h4>کانال Genesis III در تلگرام</h4>
        <p>جهان‌ها، سیستم‌ها و اخبار پروژه‌ها اول از همه‌جا آنجا منتشر می‌شوند.</p>
      </div>
      <a href="https://t.me/Genesis_III" target="_blank" class="btn-gold">عضویت در کانال ←</a>
    </div>
  </div>
</section>

<!-- SUPPORT -->
<section id="support" class="section">
  <div class="wrap">
    <div class="section-head reveal">
      <div class="kicker"><span class="dash"></span>پشتیبانی</div>
      <h2>سوال یا مشکلی داری؟</h2>
      <p>پاسخ سوال‌های پرتکرار را اینجا ببین، یا مستقیم با تیم Genesis در تماس باش.</p>
    </div>

    <div class="reveal" style="margin-top:20px;">
      <div class="faq-item">
        <button>رول‌پلی ارباب اسرار کی شروع می‌شود؟<span class="plus">+</span></button>
        <div class="faq-a"><p>تاریخ دقیقی هنوز اعلام نشده. پیشرفت پروژه در کانال تلگرام و همین‌جا به‌روزرسانی می‌شود.</p></div>
      </div>
      <div class="faq-item">
        <button>چطور می‌توانم به پروژه بپیوندم؟<span class="plus">+</span></button>
        <div class="faq-a"><p>راه ورود از طریق کانال تلگرام Genesis III اعلام خواهد شد؛ فعلاً کافیست عضو کانال باشید.</p></div>
      </div>
      <div class="faq-item">
        <button>آیا می‌توانم در ساخت جهان یا سیستم کمک کنم؟<span class="plus">+</span></button>
        <div class="faq-a"><p>بله، از طریق راه‌های تماس زیر با تیم Genesis صحبت کنید.</p></div>
      </div>
    </div>

    <div class="support-grid">
      <div class="support-card reveal">
        <h4>گزارش مشکل</h4>
        <p>باگ، مشکل نمایش سایت یا ایراد در محتوای پروژه‌ها را گزارش بده.</p>
        <a href="https://t.me/Genesis_III" target="_blank">ارسال گزارش ←</a>
      </div>
      <div class="support-card reveal">
        <h4>ارتباط مستقیم</h4>
        <p>هر سوال دیگری داری، مستقیم از طریق تلگرام با ما در ارتباط باش.</p>
        <a href="https://t.me/Genesis_III" target="_blank">پیام در تلگرام ←</a>
      </div>
    </div>
  </div>
</section>

<footer class="wrap">
  <div>GENESIS III — ARCHIVE SYSTEM</div>
  <div>t.me/Genesis_III</div>
</footer>

<!-- LOTM OVERLAY -->
<div class="overlay" id="lotmOverlay">
  <div class="overlay-head">
    <div class="top">
      <div class="title"><span class="mono">آرشیو پروژه</span>ارباب اسرار — مسیرها و سکانس‌ها</div>
      <button class="close-btn" id="closeOverlay">✕</button>
    </div>
    <div class="otabs">
      <button class="otab-btn" data-otab="world">معرفی جهان</button>
      <button class="otab-btn active" data-otab="power">پاور سیستم</button>
      <button class="otab-btn" data-otab="rp">اکوسیستم رول‌پلی</button>
      <button class="otab-btn" data-otab="dev">روند توسعه</button>
    </div>
  </div>

  <div class="obody">
    <div class="opanel" data-opanel="world">
      <p class="lede">دنیایی در آستانه‌ی انقلاب صنعتی، جایی که پشت علم و مذهب، نیرویی اسرارآمیز به‌نام «فراسو» در جریان است.</p>
      <p>داستان از زاویه‌ی دید کسی روایت می‌شود که ناگهان وارد این دنیا می‌شود و باید بین بقا، قدرت و عقلانیت تعادل برقرار کند. کلیساها، سازمان‌های مخفی و قدرت‌های بزرگ همگی برای کنترل این نیروی اسرارآمیز رقابت می‌کنند.</p>
      <h4>ساختار جهان</h4>
      <p>لور این پروژه بر اساس هر دو بخش داستان اصلی ساخته شده — رمان اول و دنباله‌ی آن — و به‌مرور که تیم Genesis محتوای بیشتری آماده کند، اینجا تکمیل می‌شود.</p>
    </div>

    <div class="opanel active" data-opanel="power">
      <div class="power-intro">
        <div class="power-kicker">آرشیو مسیرها</div>
        <h3>سیستم قدرت ارباب اسرار</h3>
        <p class="lede">۳۲ مسیر در گروه‌های خودشان. هر مسیر یک کلاس هم دارد که نقش اصلی‌اش در بازی را نشان می‌دهد؛ مثلاً جنگجو، هکس یا پشتیبان. اول گروه را باز کن، بعد مسیر را انتخاب کن و آخر سر سکانس‌ها را یکی‌یکی باز کن.</p>
      </div>

      <div class="power-modebar" id="pathMode">
        <button class="power-mode active" data-mode="standard"><span>استاندارد</span><small>۲۲ مسیر اصلی</small></button>
        <button class="power-mode" data-mode="nonstandard"><span>غیراستاندارد</span><small>۱۰ مسیر ویژه</small></button>
      </div>

      <section id="standardView" class="power-section-view" style="display:block;">
        <div class="power-section-title">
          <span class="power-index">01</span>
          <div><h4>مسیرهای استاندارد</h4><p>گروه را باز کن تا مسیرهایش را ببینی. زیر اسم هر مسیر، کلاسش نوشته شده.</p></div>
        </div>
        <div class="power-group-list" id="gooGrid"></div>
      </section>

      <section id="nonstandardView" class="power-section-view" style="display:none;">
        <div class="power-section-title">
          <span class="power-index">02</span>
          <div><h4>مسیرهای غیراستاندارد</h4><p>این مسیرها کمیاب‌ترند و هرکدام برای خودشان یک گروه جدا دارند. زیر اسم هر مسیر، کلاسش نوشته شده.</p></div>
        </div>
        <div class="power-group-list" id="nonstdGrid"></div>
      </section>

      <div class="power-footnote">توضیح‌ها خلاصه شده‌اند: مثال‌های داستانی و تکرارها حذف شده تا فقط چیزی که برای بازی لازم است بماند.</div>
    </div>

    <div class="opanel" data-opanel="rp">

      <div class="ecosystem-intro">
        <div class="eco-kicker">اکوسیستم جهان</div>
        <h3>دنیای «ارباب اسرار»</h3>
        <p class="lede">دنیای <strong>«ارباب اسرار»</strong> یک جهان ویکتوریایی – اساطیری و فراواقعی است. هرکدام از انسان‌های قدرت‌مند به نام «بایندر» شناخته می‌شوند که از طریق «مسیرهای راز» ویژه به توانایی‌های خارق‌العاده دست می‌یابند. این مسیرها متأثر از آرکاناهای تاروت هستند و شامل 22 مسیر استاندارد و 10 مسیر غیر استاندارد می‌شود که هر مسیر با 9 سطح قدرت تعریف شده است. نظام قدرت در این جهان منطق درونی خاص خود را دارد: گرفتن قدرت با هزینه‌های روانی و فیزیکی همراه است.</p>
      </div>
      <div class="eco-grid">
        <article class="eco-card"><div class="eco-card-head"><span class="eco-num">01</span><h4>کیهان‌شناسی و ماوراطبیعی</h4></div>
        <p>در این جهان، سیستم قدرت با استعاره‌های تاروت شکل گرفته است: کاراکترهای داستان از طریق مراسم‌های روحانی و بطری‌های معجون که بر اساس تفسیر تاروت ساخته شده‌اند، قدرت می‌گیرند. خود «کلاین مورتری» قهرمان داستان، حلقه‌ای به نام «باشگاه تاروت» تشکیل می‌دهد و در آن‌ با کارت‌های تاروت دایره‌المعارفی از مهارت‌های متافیزیکی را مطالعه می‌کند.</p>
        <p>علاوه بر جهان مادی، ابعاد ماورایی متعددی وجود دارد. فضاهای روحانی همچون «مه خاکستری»، «آسمان‌ها»، «عالم مردگان» و «آبیس» از مهم‌ترین سطوح این کیهان‌اند. هر مسیر راز با یکی از قدرت‌های آرکانایی، مثل «فریبنده»، «روحانی»، «امپراتریس» و …، مرتبط است که گاه به شکل خدایان یا فرشتگان در اسطوره‌های داخلی نمود پیدا می‌کند. شخصیت‌های قدرتمند بالاتر از تئوری به عنوان «اربابان» خوانده می‌شوند و می‌توانند در ابعاد بالا ظاهر شوند. قدرت‌های مهیب‌تر مانند «پدر هرج‌ومرج» یا «قانون دوّم» نیز در تاریخ جهان تأثیرگذار بوده‌اند.</p></article>
        <article class="eco-card eco-card-wide"><div class="eco-card-head"><span class="eco-num">02</span><h4>گروه‌ها و سازمان‌ها</h4></div>
        <p>در گستره سیاسی–فرهنگی، چندین نهاد و فرقه مسلط‌اند. مهم‌ترین آن‌ها هفت <strong>کلیسای ارثوُدُکس</strong> است که هرکدام اقتدار مذهبی–سیاسی ویژه‌ای دارند. این کلیساها مانند کلیسای حاکم اشعاع یا کلیسای ارتکاب و … رهبران قدرتمندی دارند که پشتیبان مسیرهای مختلف جادو هستند. فرقه‌ها و تشکیلات سری دیگری نیز وجود دارند: «جمع‌برحشت» که به الهه مرگ وابسته است، «سازمان راز» که مجموعه‌ای از بایندرهای مخفی است و «انجمن سیاه» که اهداف گوناگونی در پس پرده جهانی دارد. در لایه دولت‌ها، بزرگ‌ترین قدرت، <strong>امپراتوری اقیانوسی</strong> با جغرافیای وسیع و روابط پیچیده سیاسی است که شهرهایی مانند <strong>تیگن</strong> را در بر می‌گیرد. همچنین یاغیان جادویی و فرقه‌های پیرو «قانون بیگانه» و «جنگجویان الکتریکی» در گوشه و کنار جهان شناخته می‌شوند.</p>
        <div class="eco-bullets">
          <div class="eco-bullet"><b>کلیساها و مذاهب:</b><span>هر کلیسا بر پایه اسطوره‌ای خاص شکل گرفته و پذیرش مسیرهای راز مشخص را ترویج می‌کند. مثلاً کلیسای Radiance بر تاریکی می‌تازد تا نیرو جذب کند و کلیسای نور بر قدرت‌های طبیعت تأکید دارد.</span></div>
          <div class="eco-bullet"><b>سازمان‌های مخفی:</b><span>انجمن راز، گردهمایی گروه‌های تحقیقاتی و قهرمانان سری است. جمع برحشت به دنبال تسلط بر مرگ و تاریکی است و گروه «آتلیر امپریالیسم» به جستجوی رازهای گمشده در ابعاد زمان اختصاص دارد.</span></div>
          <div class="eco-bullet"><b>دولت‌ها:</b><span>امپراتوری اقیانوس، چندین کشور کوچک‌و‌بزرگ اروپایی را تحت پوشش دارد. در نیم‌کره غربی، نویلان و بلادج قرار دارند که فرهنگ و تکنولوژی متفاوتی دارند. در فراماهیات، ارکان جدید قدرت شکل گرفته‌اند، مثل «حکومت کابال» در عرش، اما اطلاعات آن‌ها در رمان کم است.</span></div>
        </div></article>
        <article class="eco-card"><div class="eco-card-head"><span class="eco-num">03</span><h4>جغرافیا و مکان‌های مهم</h4></div>
        <p>نقشه زمین مشابه جهان ویکتوریایی است اما جزئیات خاص خود را دارد. قاره اصلی <strong>اروپا</strong> همچنان مرکز پیشرفت و ناشناخته‌های ماورایی است. شهر تیگن که آغاز ماجراست، توسط دودکش‌های قرمز کارخانه‌ها و <strong>کاخ پیچاره</strong> احاطه شده است. در <strong>آمریکای جدید</strong>، شهر «نیکوآیا» مرکز فعالی است که محققان و جادوگران فراوان دارد. منطقه «کاخ فانتوم» در ژاپن با مذهب و رسوم مختص به خود، و در <strong>اقیانوس‌آیا</strong> جزایر رازآلودی وجود دارد.</p></article>
        <article class="eco-card"><div class="eco-card-head"><span class="eco-num">04</span><h4>تاریخ و رویدادهای کلیدی</h4></div>
          <div class="eco-timeline">
            <div class="eco-event"><span>جنگ الهی</span><p>در هزاران سال پیش، نبردی بین خدایان و انسان‌ها رخ داد. این جنگ که در اساطیر «جنگ خدایی» نامیده می‌شود، باعث جدا شدن کامل دنیاهای مادی و ماورایی شد.</p></div>
            <div class="eco-event"><span>شورش آشوب</span><p>پس از آن، نیروهای هرج‌ومرج علیه خدایان شوریدند و جنگی کیهانی راه انداختند که نظم ساختار نیروی خدایان را بر هم زد. فرجام این نبرد آغاز عصر جدیدی بود.</p></div>
            <div class="eco-event"><span>ظهور اربابان اسرار</span><p>پس از هرج و مرج، گروهی از قدرتمندان به عنوان اربابان جهان ظاهر شدند و سلطه خود را پنهان آغاز کردند. هر یک دین و فرقه‌ای را پایه گذاشتند تا از پیشرفت انسان‌ها در مسیرهای راز جلوگیری کنند.</p></div>
            <div class="eco-event"><span>عصر کنونی</span><p>داستان اصلی در اوایل قرن بیستم، حدود 1908 میلادی، آغاز می‌شود؛ زمان آپارتمان‌های گازسوز، کارخانه‌های فورد و شهرهای بخار. فشار انقلاب صنعتی با ظهور علم نفوذپذیر بر خدایان و پدیده‌های فراطبیعی چیره می‌شود. کلاین مورتری، مسافری از دنیایی دیگر، در همین دوران وارد تیگن شده و شروع به رمزگشایی از اسرار اساطیری می‌کند.</p></div>
          </div>
        </article>
        <article class="eco-card eco-card-wide"><div class="eco-card-head"><span class="eco-num">05</span><h4>سیستم جادویی</h4></div>
          <p>جادو در این جهان علمی در لباس عرفان است. <em>مسیرهای راز</em> اساس نظام قدرت‌اند. فردی که به ترتیب مراحل 1 تا 9 مسیر خود را طی کند، توانایی‌های خارق‌العاده‌ای پیدا می‌کند. هر مسیر، مثل «مسیر احضار»، «مسیر حجت»، «مسیر شمن‌پرستی» و…، مختص یک کارت آرکانا است. دریافت توانایی از طریق سه روش اصلی است:</p>
          <div class="eco-mechanics">
            <div class="eco-mech"><span class="eco-mech-no">1</span><div><b>معجون‌ها</b><p>ترکیباتی شبیه سم‌درمان که از مواد طبیعی و اشیاء مقدس تهیه می‌شود. خوردن یا تزریق این معجون‌ها بلافاصله نقشی تعیین‌کننده در تعادل روانی فرد دارد.</p></div></div>
            <div class="eco-mech"><span class="eco-mech-no">2</span><div><b>مراسم و آئین‌ها</b><p>آیین‌های پیچیده‌ عرفانی که معمولاً چند نفره و با نقوش ویژه انجام می‌شوند. هر آیین سیگنالی به بُعد مشخصی می‌فرستد و یاری گرفتن از یک خدای آرکانا را ممکن می‌سازد.</p></div></div>
            <div class="eco-mech"><span class="eco-mech-no">3</span><div><b>اشیاء باستانی</b><p>اشیاء قدسی یا تبدیل‌شده به حامل قدرت، مثل «تاج کلیدآسا»، «رول‌دین» یا «کتاب‌های محافظت». داشتن این آیتم‌ها گاهی جایگزین یک یا چند سطح می‌شود.</p></div></div>
          </div>
          <p class="eco-note">کارکرد داخلی چنین سیستمی به نوعی علمی-روانشناسانه توضیح داده می‌شود: هر پیشرفت مسیری، توازن روان‌شناختی را بر هم می‌زند و هزینه‌هایی دارد. مثلاً مصرف یک معجون قوی، فرد را از خود دور می‌کند یا ترکیب اشتباه آن به یک کابوس مهلک منجر می‌شود. این ویژگی باعث می‌شود بایندرها پیش از هربارش به‌دقت بسنجند که چقدر قدرت برایشان می‌ارزد.</p></article>
        <article class="eco-card"><div class="eco-card-head"><span class="eco-num">06</span><h4>موجودات غیرانسانی و غیبی</h4></div>
          <div class="eco-bullets">
            <div class="eco-bullet"><b>ارواح و اسپیریت‌ها:</b><span>برخی انسان‌ها می‌توانند با اموات در ارتباط باشند. «دالی سیمونه»، دوست کلاین، یک واسطه مردگان است که به‌خوبی به دنیای ارواح وصل می‌شود. ارواح معمولاً بی‌زبان‌اند اما گاه پیام‌هایی اسرارآمیز می‌فرستند.</span></div>
            <div class="eco-bullet"><b>مخلوقات اسرارآمیز:</b><span><em>Ravager</em>ها شکارچیان جهش‌یافته عموماً در عمق جنگل‌ها و ابیس زندگی می‌کنند. <em>Rampager</em>ها موجوداتی استثنایی‌اند که با توده‌ای جهش‌یافته از موجودات مختلف ترکیب شده‌اند. یکی از شخصیت‌ها در ماجراها با «Rampager ماهی‌مانند» مواجه می‌شود.</span></div>
            <div class="eco-bullet"><b>غول‌ها و جانوران کلاسیک:</b><span>بُوم‌ها، مگوس‌ها و غول‌های طبیعی نیز بسته به محیط جغرافیایی و متافیزیکی به چشم می‌آیند. <em>مگوس</em>ها برخی انسان‌های کهن‌اند که تبدیل به موجودات نیمه‌خودآگاه شدند. از همه مهم‌تر، «عمش‌گاه»ها که نفرین‌شدگان مسیرها هستند، تهدیداتی رازآلود‌اند.</span></div>
          </div>
        </article>
        <article class="eco-card"><div class="eco-card-head"><span class="eco-num">07</span><h4>تأثیرات فرهنگی و اجتماعی</h4></div>
          <p>مسیرهای راز و وجود قدرت‌های ماورایی، هرروزه زندگی جامعه را متحول کرده است. ادبیات خفیه و هنر تئاتر این جهان پر از نمادهای رازآلود است. برای نمونه، کدهای مخفی آلفابت‌های خلق‌شده توسط بایندرها، مثل «آلکام» اند، در طراحی آرایش شهری یا نقاشی‌های خیابانی دیده می‌شوند.</p>
          <p>در سیاست، مذاهب رسمی به اندازه‌ای نفوذ دارند که هرکسی شغل یا موقعیتی می‌خواهد باید موافقت یکی از کلیساها را جلب کند. به همین دلیل، قانون‌گذاران و گرو‌ه‌های اجتماعی چهره‌های دینی را با خود همراه کرده‌اند. از سوی دیگر، دانشمندان صنعتی، مثلاً در مهندسی مکانیک بخار، اغلب زیر سایه این جریان‌های ماورایی موضوع تحقیق‌شان قرار می‌گیرند.</p>
          <p>در محافل مردمی، مسیرها به‌عنوان «حرفه»‌هایی پنهان خریدارانی دارند. این مسیرها لایه در لایه مفهوم اجتماعی دارند: افراد با عبور از مراحل بالاتر شخصیتشان تغییر می‌کند، مثلاً یک شخص عادی پس از رسیدن به سطح بالای مسیر «پادشاه دروغ» دیگر کم‌تر قابل تشخیص است. تاثیر اجتماعی آن‌چنان است که استناد به عضویت در مسیر یا داشتن برخی توانایی به یک کلاس اجتماعی جدید منجر شده، شبیه عصر اشراف و خادمان در دوران ویکتوریایی.</p>
        </article>
      </div>
      <div class="eco-footer-note"><span class="eco-footer-mark">◎</span><div><b>اکوسیستم</b><p>متن این بخش از توضیح ارائه‌شده برای پروژه گرفته شده و در قالب رابط کاربری سایت سازمان‌دهی شده است.</p></div></div>
    </div>

    <div class="opanel" data-opanel="dev">
      <p class="lede">این پروژه هنوز در مرحله‌ی ساخت است.</p>
      <div class="dev-empty">گزارش توسعه هنوز ثبت نشده — به‌محض شروع رسمی کار، پیشرفت پروژه اینجا و در کانال تلگرام منتشر می‌شود.</div>
    </div>
  </div>
</div>

<script>
(function(){
  // nav scroll state + active link
  const nav = document.getElementById('nav');
  const navLinks = document.querySelectorAll('.nav-link, .m-link');
  const sections = ['home','projects','genesis','support'].map(id=>document.getElementById(id));

  function updateNav(){
    nav.classList.toggle('scrolled', window.scrollY>40);
    let current='home';
    sections.forEach(s=>{ if(s && window.scrollY >= s.offsetTop-140) current=s.id; });
    navLinks.forEach(l=>{
      const on = l.getAttribute('href')==='#'+current;
      l.classList.toggle('active', on);
      if(on) l.setAttribute('aria-current','true'); else l.removeAttribute('aria-current');
    });
  }
  let ticking=false;
  window.addEventListener('scroll', ()=>{
    if(!ticking){ requestAnimationFrame(()=>{ updateNav(); ticking=false; }); ticking=true; }
  }, {passive:true});
  updateNav();

  // mobile menu
  const burger=document.getElementById('burger');
  const mmenu=document.getElementById('mobileMenu');
  function setMenu(open){
    burger.classList.toggle('open',open);
    mmenu.classList.toggle('open',open);
    nav.classList.toggle('menu-open',open);
    document.documentElement.classList.toggle('menu-open',open);
    burger.setAttribute('aria-expanded', open?'true':'false');
    burger.setAttribute('aria-label', open?'بستن منو':'باز کردن منو');
    mmenu.setAttribute('aria-hidden', open?'false':'true');
    if(open){ setTimeout(()=>{ if(mmenu.classList.contains('open')){ const f=mmenu.querySelector('.m-link'); if(f) f.focus({preventScroll:true}); } }, 380); }
  }
  burger.addEventListener('click', ()=> setMenu(!mmenu.classList.contains('open')));
  mmenu.querySelectorAll('a').forEach(a=>a.addEventListener('click', ()=> setMenu(false)));
  document.addEventListener('keydown', (e)=>{
    if(!mmenu.classList.contains('open')) return;
    if(e.key==='Escape'){ setMenu(false); burger.focus(); return; }
    if(e.key==='Tab'){
      const f=[burger, ...mmenu.querySelectorAll('a')];
      const i=f.indexOf(document.activeElement);
      if(e.shiftKey && i<=0){ e.preventDefault(); f[f.length-1].focus(); }
      else if(!e.shiftKey && i===f.length-1){ e.preventDefault(); f[0].focus(); }
    }
  });
  window.addEventListener('resize', ()=>{ if(window.innerWidth>640 && mmenu.classList.contains('open')) setMenu(false); }, {passive:true});

  // reveal on scroll
  const io = new IntersectionObserver((entries)=>{
    entries.forEach(e=>{ if(e.isIntersecting){ e.target.classList.add('in'); io.unobserve(e.target); } });
  }, {threshold:.15});
  document.querySelectorAll('.reveal, .divider').forEach(el=>io.observe(el));

  // count-up stats
  const counters = document.querySelectorAll('[data-count]');
  const cIo = new IntersectionObserver((entries)=>{
    entries.forEach(e=>{
      if(e.isIntersecting){
        const el=e.target, target=parseInt(el.dataset.count,10);
        let cur=0;
        const step=()=>{ cur++; el.textContent=cur; if(cur<target) requestAnimationFrame(step); };
        if(target>0) requestAnimationFrame(step); else el.textContent='0';
        cIo.unobserve(el);
      }
    });
  }, {threshold:.5});
  counters.forEach(c=>cIo.observe(c));

  // project tabs
  document.querySelectorAll('.tab-btn').forEach(btn=>{
    btn.addEventListener('click', ()=>{
      document.querySelectorAll('.tab-btn').forEach(b=>b.classList.remove('active'));
      btn.classList.add('active');
      const name=btn.dataset.tab;
      document.querySelectorAll('.panel').forEach(p=>p.classList.toggle('active', p.dataset.panel===name));
    });
  });

  // LOTM overlay
  const overlay=document.getElementById('lotmOverlay');
  const lotmCard=document.getElementById('lotmCard');
  if(lotmCard && overlay){
    lotmCard.addEventListener('click', ()=>{
      overlay.classList.add('open');
      document.body.style.overflow='hidden';
      overlay.scrollTop=0;
    });
  }
  const closeOverlayBtn=document.getElementById('closeOverlay');
  if(closeOverlayBtn) closeOverlayBtn.addEventListener('click', closeOv);
  document.addEventListener('keydown', (e)=>{ if(e.key==='Escape' && overlay.classList.contains('open')) closeOv(); });
  function closeOv(){
    overlay.classList.remove('open');
    document.body.style.overflow='';
  }

  document.querySelectorAll('.otab-btn').forEach(btn=>{
    btn.addEventListener('click', ()=>{
      document.querySelectorAll('.otab-btn').forEach(b=>b.classList.remove('active'));
      btn.classList.add('active');
      const name=btn.dataset.otab;
      document.querySelectorAll('.opanel').forEach(p=>p.classList.toggle('active', p.dataset.opanel===name));
      document.querySelector('.obody').scrollIntoView({block:'start', behavior:'instant' in window ? 'instant':'auto'});
    });
  });

  // ===== LOTM PATHWAY ARCHIVE =====
  const pathTitles = {"fool":"مسیر ابله","error":"مسیر خطا","door":"مسیر در","sun":"مسیر خورشید","visionary":"مسیر رویا پرداز","white_tower":"مسیر برج سفید","tyrant":"مسیر ظالم","hanged_man":"مسیر مرد آویخته","darkness":"مسیر تاریکی","death":"مسیر مرگ","twilight_giant":"مسیر غول سپیده دم","demoness":"مسیر اهریمن بانو","red_priest":"مسیر کشیش سرخ","hermit":"مسیر ذاهد","paragon":"مسیر پاراگون","wheel_of_fortune":"مسیر چرخ بخت","mother":"مسیر مادر","moon":"مسیر ماه","abyss":"مسیر مغاک","chained":"مسیر زنجیر شده","black_emperor":"مسیر امپراتور سیاه","justiciar":"مسیر داور","eternal_aeon":"مسیر عصر ابدی","chaos_primogenitor":"مسیر آشوب نخستین","patriarch":"مسیر پدرسالار","chaos_mist":"مسیر مه آشوب","condenser":"مسیر متراکم‌کننده","everlasting":"مسیر ابدی","second_law":"مسیر قانون دوم","sublunary_eye":"مسیر چشم زیرماه","eternal_edict":"مسیر فرمان ابدی","tail_devourer":"مسیر دم‌بلع"};
  const classes = [{"id":"warrior","name":"جنگجو","en":"Warrior","desc":"خط اول نبرد؛ بدن، سلاح، طوفان و قانون را برای زدن یا محدود کردن دشمن به کار می‌گیرند."},{"id":"mage","name":"جادوگر","en":"Mage","desc":"قدرتشان از دانش و آیین می‌آید؛ طلسم، فضا، ستاره و ساختن جهان‌های خیالی."},{"id":"hex","name":"هکس","en":"Hex","desc":"نفرین، بیماری، تباهی و کابوس؛ دشمن را از درون یا با بدشانسی و زوال از پا درمی‌آورند."},{"id":"trickster","name":"فریب‌کار","en":"Trickster","desc":"با دروغ، دزدی، قرارداد و بازی با میل آدم‌ها جلو می‌روند؛ نبرد رودررو کار اصلی‌شان نیست."},{"id":"mentalist","name":"ذهن‌گرا","en":"Mentalist","desc":"ذهن، رؤیا، دانش و تحلیل؛ قبل از شروع دعوا یک قدم جلوترند."},{"id":"summoner","name":"احضارگر","en":"Summoner","desc":"با ارواح، مرده‌ها و زیردستان می‌جنگند؛ خودشان کمتر وارد خط اول می‌شوند."},{"id":"support","name":"پشتیبان","en":"Support","desc":"درمان، معجون، پاک‌سازی و تقویت هم‌تیمی‌ها؛ ستون تیم."},{"id":"fate","name":"سرنوشت‌گر","en":"Fate","desc":"شانس، سرنوشت و چرخه‌ی رنج را دستکاری می‌کنند؛ کند ولی ترسناک."}];
  const pathInfo = {"fool":{"cls":"trickster","std":true,"group":"ارباب اسرار","line":"مسیر فریب و نمایش. با توهم و تغییر چهره گول می‌زنی، آدم‌ها را مثل عروسک هدایت می‌کنی و در سطح‌های بالا با تاریخ و معجزه بازی می‌کنی."},"error":{"cls":"trickster","std":true,"group":"ارباب اسرار","line":"مسیر دزدی و خراب‌کاری. از هر چیزی می‌دزدی، از اشیا گرفته تا توانایی و سرنوشت، و سیستم‌ها را به خطا می‌اندازی."},"door":{"cls":"mage","std":true,"group":"ارباب اسرار","line":"مسیر سفر و فضا. در باز می‌کنی، انتقال آنی داری و توانایی دیگران را ثبت و تکرار می‌کنی."},"sun":{"cls":"support","std":true,"group":"خدای قادر مطلق","line":"مسیر نور و پاک‌سازی. با آتش و نور مقدس می‌جنگی، آلودگی را پاک می‌کنی و با عدالت و قرارداد نظم می‌سازی."},"visionary":{"cls":"mentalist","std":true,"group":"خدای قادر مطلق","line":"مسیر ذهن و رؤیا. فکر آدم‌ها را می‌خوانی، رؤیا می‌بافی و در ذهن دیگران دست می‌بری."},"white_tower":{"cls":"mentalist","std":true,"group":"خدای قادر مطلق","line":"مسیر دانش و تحلیل. با مشاهده و استدلال همه‌چیز را زودتر از بقیه می‌فهمی و در سطح بالا تقریباً همه‌چیزدان می‌شوی."},"tyrant":{"cls":"warrior","std":true,"group":"خدای قادر مطلق","line":"مسیر دریا و طوفان. بدنی قوی داری و باد، آب، یخ و رعدوبرق را برای ویرانی به کار می‌گیری."},"hanged_man":{"cls":"hex","std":true,"group":"خدای قادر مطلق","line":"مسیر سایه و کفر. با سایه‌ها، ارواح و جادوی گوشت و خون کار می‌کنی و بار گناه دیگران را به دوش می‌کشی."},"darkness":{"cls":"hex","std":true,"group":"تاریکی ابدی","line":"مسیر شب و خواب. دشمن را به خواب و کابوس می‌کشی، روح‌ها را کنترل می‌کنی و بدشانسی می‌پراکنی."},"death":{"cls":"summoner","std":true,"group":"تاریکی ابدی","line":"مسیر مرگ و ارواح. با ارواح و مرده‌ها ارتباط داری و به آن‌ها فرمان می‌دهی؛ خودت هم به مرگ نزدیک‌تر و مقاوم‌تر می‌شوی."},"twilight_giant":{"cls":"warrior","std":true,"group":"تاریکی ابدی","line":"مسیر رزم. بدن قوی، سلاح و مهارت جنگی؛ مستقیم‌ترین راه برای قدرت."},"demoness":{"cls":"hex","std":true,"group":"فاجعه نابودی","line":"مسیر نفرین و فاجعه. تحریک، جذابیت، یخ و شعله‌ی سیاه؛ در سطح بالا بلا، بیماری و آخرالزمان می‌آورد."},"red_priest":{"cls":"warrior","std":true,"group":"فاجعه نابودی","line":"مسیر جنگ و توطئه. با آتش، فولاد و آب‌وهوا می‌جنگی و ضعف دشمن را شکار می‌کنی."},"hermit":{"cls":"mage","std":true,"group":"دیو دانش","line":"مسیر رازکاوی و جادو. طلسم و طومار می‌سازی، غیب می‌بینی و اطلاعات و دانش را دستکاری می‌کنی."},"paragon":{"cls":"mentalist","std":true,"group":"دیو دانش","line":"مسیر علم و ساخت. اشیای عرفانی می‌سازی، با فناوری کار می‌کنی و حتی حیات مصنوعی خلق می‌کنی."},"wheel_of_fortune":{"cls":"fate","std":true,"group":"کلید نور","line":"مسیر شانس و سرنوشت. بخت را به سمت خودت و بدشانسی را به سمت دشمن می‌کشی و آینده را پیش‌بینی می‌کنی."},"mother":{"cls":"support","std":true,"group":"الهه منشأ","line":"مسیر زندگی و طبیعت. درمان، گیاهان و ساخت موجودات ترکیبی؛ زندگی را رشد می‌دهد و دستکاری می‌کند."},"moon":{"cls":"support","std":true,"group":"الهه منشأ","line":"مسیر معجون و خون. معجون می‌سازی، احضار می‌کنی، بدنت خون‌آشام‌گونه می‌شود و از نور ماه قدرت می‌گیری."},"abyss":{"cls":"hex","std":true,"group":"پدر شیاطین","line":"مسیر هوس و تباهی. با کینه، فساد و نفرین قدرت می‌گیری و میل آدم‌ها را دستکاری می‌کنی."},"chained":{"cls":"summoner","std":true,"group":"پدر شیاطین","line":"مسیر جنون و زنجیر. به فرم‌های جهش‌یافته تبدیل می‌شوی، زیردست می‌سازی و نفرین و تسخیر به کار می‌بری."},"black_emperor":{"cls":"trickster","std":true,"group":"آنارشی","line":"مسیر رشوه و بی‌نظمی. قانون را دور می‌زنی، اوضاع را به‌هم می‌ریزی و از هرج‌ومرج سود می‌بری."},"justiciar":{"cls":"warrior","std":true,"group":"آنارشی","line":"مسیر قانون و حکم. قانون وضع می‌کنی، حکم می‌دهی و توانایی دشمن را از او می‌گیری."},"eternal_aeon":{"cls":"fate","std":false,"group":"حلقه اجتناب‌ناپذیری","line":"مسیر قرارداد و چرخه. با قراردادها، سرنوشت و تکرار رنج کار می‌کنی؛ اجتناب‌ناپذیری قدرت اصلی‌ات است."},"chaos_primogenitor":{"cls":"hex","std":false,"group":"مادر الهه تباهی","line":"مسیر بدعت و تولید. زندگی را دستکاری و تکثیر می‌کنی و با جادوی بدعت‌گذار قانون‌ها را می‌شکنی."},"patriarch":{"cls":"trickster","std":false,"group":"درخت مادر امیال","line":"مسیر میل و بازیگری. هوس و عشق را برمی‌انگیزی، نقش بازی می‌کنی و از میل‌ها قدرت می‌گیری."},"chaos_mist":{"cls":"trickster","std":false,"group":"مه آشوب","line":"مسیر دلالی و اتهام. زیرمیزی می‌دهی، اتهام می‌زنی، از سایه‌ها استفاده می‌کنی و در آشوب حقیقت را می‌بینی."},"condenser":{"cls":"mage","std":false,"group":"فرمانروای ابرنواختر","line":"مسیر ستاره و گرانش. با نجوم، ناوبری و گرانش کار می‌کنی؛ از ستاره‌ها تا نیروهای بنیادی."},"everlasting":{"cls":"mentalist","std":false,"group":"هذیان‌های خاموش‌نشدنی","line":"مسیر کلام و فلسفه. با خطابه، آواز و فلسفه، ذهن و آگاهی دیگران را شکل می‌دهی."},"second_law":{"cls":"hex","std":false,"group":"پادشاه زوال","line":"مسیر زوال. بیماری، پوسیدگی و فرسودگی؛ همه‌چیز را به سمت پایان می‌بری."},"sublunary_eye":{"cls":"mage","std":false,"group":"ناظر بُعدبالا","line":"مسیر نقاشی و جهان‌سازی. نقاشی عرفانی می‌کشی، خیال را واقعی می‌کنی و ابعاد را کنترل می‌کنی."},"eternal_edict":{"cls":"fate","std":false,"group":"الهه سرنوشت","line":"مسیر سرنوشت. سرنوشت را می‌بینی، می‌بافی و داوری می‌کنی؛ حتی مرگ جعلی هم از دستت برمی‌آید."},"tail_devourer":{"cls":"support","std":false,"group":"گرسنگی نخستین","line":"مسیر بلعیدن. هرچه می‌بلعی قدرتت می‌شود؛ آشپزی عرفانی می‌کنی و توانایی دیگران را می‌خوری."}};
  const standardGroups = [{"id":"lom","title":"ارباب اسرار","short":"3 مسیر • ابله، خطا، دروازه","paths":["fool","error","door"]},{"id":"ga","title":"خدای قادر مطلق","short":"5 مسیر • خیال‌پرداز، خورشید، ظالم، برج سفید، مرد آویخته","paths":["visionary","sun","tyrant","white_tower","hanged_man"]},{"id":"dark","title":"تاریکی ابدی","short":"3 مسیر • تاریکی، مرگ، غول سپیده دم","paths":["darkness","death","twilight_giant"]},{"id":"calamity","title":"فاجعه نابودی","short":"2 مسیر • اهریمن بانو، کشیش سرخ","paths":["demoness","red_priest"]},{"id":"knowledge","title":"دیو دانش","short":"2 مسیر • زاهد، پاراگون","paths":["hermit","paragon"]},{"id":"light","title":"کلید نور","short":"1 مسیر • چرخ بخت","paths":["wheel_of_fortune"]},{"id":"origin","title":"الهه منشأ","short":"2 مسیر • مادر، ماه","paths":["mother","moon"]},{"id":"devils","title":"پدر شیاطین","short":"2 مسیر • مغاک، زنجیر شده","paths":["abyss","chained"]},{"id":"anarchy","title":"آنارشی","short":"2 مسیر • امپراتور سیاه، داور","paths":["black_emperor","justiciar"]}];
  const nonstandardGroups = [{"id":"coi","title":"حلقه اجتناب‌ناپذیری","short":"مسیر غیر استاندارد • عصر ابدی","path":"eternal_aeon"},{"id":"mgod","title":"مادر الهه تباهی","short":"مسیر غیر استاندارد • آشوب نخستین","path":"chaos_primogenitor"},{"id":"mtod","title":"درخت مادر امیال","short":"مسیر غیر استاندارد • پدرسالار","path":"patriarch"},{"id":"cm","title":"مه آشوب","short":"مسیر غیر استاندارد • مه آشوب","path":"chaos_mist"},{"id":"hunger","title":"گرسنگی نخستین","short":"مسیر غیر استاندارد • دم‌بلع","path":"tail_devourer"},{"id":"supernova","title":"فرمانروای ابرنواختر","short":"مسیر غیر استاندارد • متراکم‌کننده","path":"condenser"},{"id":"ravings","title":"هذیان‌های خاموش‌نشدنی","short":"مسیر غیر استاندارد • ابدی","path":"everlasting"},{"id":"decay","title":"پادشاه زوال","short":"مسیر غیر استاندارد • قانون دوم","path":"second_law"},{"id":"overseer","title":"ناظر بُعدبالا","short":"مسیر غیر استاندارد • چشم زیرماه","path":"sublunary_eye"},{"id":"fate","title":"الهه سرنوشت","short":"مسیر غیر استاندارد • فرمان ابدی","path":"eternal_edict"}];
  const mainAbilities = {"fool":["پیشگویی","توهم","تغییرشکل","عروسک‌گردانی","پنهان‌سازی","تاریخ","معجزات","پیونددهی","فریب"],"error":["دزدی","فریب","رمزگشایی","انگل‌وارگی","ساخت آواتار","دستکاری سرنوشت","بهره‌برداری از رخنه‌ها","دستکاری زمان","ایجاد خطا"],"door":["گشودن در","طالع‌بینی","ثبت توانایی","انتقال آنی","دستکاری فضا","پنهان‌سازی","تکثیر","مهر و موم","مکان‌یابی","در"],"visionary":["ذهن‌خوانی","روان‌کاوی","دستکاری ذهن","کار با جهان ذهن","شخصیت‌های مجازی","بافتن رویا","تشخیص","ذهن و خیال","پیشگویی","تجسم"],"sun":["آوازهای نوازنده","دستکاری آتش و نور","جادوی خورشیدی","تنفیذ و ثبت رسمی","پاک‌سازی","عدالت","قداست، نظم و ایمان","خورشید و نور","نور خاموش‌نشدنی"],"tyrant":["تقویت جسمانی","دستکاری آب و یخ","دستکاری باد","دستکاری رعدوبرق","دستکاری امواج صوتی","القای ترس","کنترل موجودات دریایی","کنترل آب‌وهوا","ایجاد فاجعه","شتاب‌دهی ذرات","استبداد"],"white_tower":["جادوی آیینی","دانش","مشاهده","استدلال","تحلیل","تقلید توانایی","ساخت طلسم","پیشگویی","شناخت","خرد","دانای مطلقی"],"hanged_man":["جادوی آیینی","شنیدن","دستکاری سایه","جادوی گوشت و خون","به‌بردگی‌گرفتن ارواح","کلمات کفرآمیز","فساد","جهش","تباهی","قربانی","بردوش‌کشیدن گناه"],"darkness":["شب‌زیستی","شعر نیمه‌شب","القاء خواب","دستکاری رویا","مرثیه","کنترل روح","بدشانسی","پنهان‌سازی","القاء وحشت","دستکاری تاریکی"],"death":["بدن نامرده","ارتباط با ارواح","کنترل ارواح","نکرومنسی","رستاخیز","کنترل جهان زیرین","به‌بردگی‌گرفتن","رنگ‌پریدگی","نقطه پایان","دستکاری مرگ"],"twilight_giant":["نبرد","استادی سلاح","مقاومت در برابر عرفان","تقویت فیزیکی","بدن غول‌آسا","نور سپیده‌دم","محافظت","کیمیا","پنهان‌سازی ذهن","مایع‌شدن به جیوه","پنهان‌سازی نور","برکت خدا یا فرشته","عبور زمان","پوسیدگی سپیده‌دم","قداست","نیابت"],"demoness":["پنهان‌سازی سایه","تحریک","جذابیت","جادوی تاریک","جادوی یخ","جادوی شعله سیاه","جادوی آینه","نفرین‌ها","دستکاری رشته‌ها","کنترل بیماری و طاعون","سنگ‌شدن","بلایای طبیعی","فاجعه","آخرالزمان","آشوب","نخستین‌بودن"],"red_priest":["آتش‌افروزی","دستکاری فولاد","توطئه","تحریک و دروغ","بررسی و شکار ضعف","تقویت جسمی و ذهنی","تقویت سلاح","کنترل جمعیت","توزیع قدرت","کنترل آب‌وهوا","فتح","نابودی"],"hermit":["پیشگویی","رازکاوی","جادوی آیینی","ساخت طلسم","ساخت طومار","بازسازی عرفانی","غیب‌بینی","دستکاری اطلاعات","دستکاری دانش","نمادگرایی اعداد"],"paragon":["دانش","یادآوری","جادوی آیینی","ارزیابی اشیای عرفانی","ساخت اشیای عرفانی","خلق حیات مصنوعی","ازهم‌گسیختن ساختار","دستکاری فیزیک","فناوری","جوهر و ماهیت"],"wheel_of_fortune":["غیب‌بینی","پیشگویی","جذب فاجعه","دستکاری بخت","دستکاری سرنوشت","پیش‌بینی","بازنشانی سرنوشت","چرخه سرنوشت","تناسخ","دستکاری احتمال"],"mother":["گیاه‌شناسی","درمان","دورگه‌سازی","جهش زیستی","خلق کایمرا","کیمیا","باروری و تولیدمثل","برهوت","دستکاری حیات"],"moon":["معجون‌سازی","روحانیت","بدن خون‌آشامی","جادوی تاریک","احضار","دستکاری حیات","زیبایی","دستکاری نور ماه"],"abyss":["جادوی آیینی","طلسم‌های شیطانی","ادراک کینه","دگردیسی اهریمنی","دستکاری میل","فساد","کینه","خون و مایعات بدن","خوردگی","نفرین‌ها","پلیدی","تباهی"],"chained":["جنون","فرم‌های جهش‌یافته","جادوی یخ","طلسم‌های مرتبط با مرگ","خلق زیردستان","تسخیر","نفرین‌ها","به‌بندی و زنجیر","منحرفان","اشیاء"],"black_emperor":["رشوه","بی‌نظمی","اعوجاج","بخشش","بزرگ‌نمایی","بهره‌برداری","هیبت","رستاخیز"],"justiciar":["کاریزما","کنترل قلمرو","ردیابی و تشخیص","حملات ذهنی و روحی","وضع و اجرای قوانین","حکم","مجازات","محروم‌کردن از توانایی","تعادل","قانون و نظم"],"eternal_aeon":["جادوی آیینی","پیشگویی","قراردادها","فشرده‌سازی","دستکاری سرنوشت","ساکن حلقه","بازاجرای رنج","گذشته، حال و آینده","علت، معلول و سرنوشت","چرخه و اجتناب‌ناپذیری"],"chaos_primogenitor":["ارعاب","درمان","کیمیا","نیای نخستین","دستکاری حیات","جادوی بدعت‌گذار","پارامیتا","الوهیت ضعیف","واقعیت","تولیدمثل و تکثیر","گناه نخستین"],"patriarch":["برانگیختن میل","بازیگری","تقلید","نفوذ در رویا","نیایش درخت","اجرای میل","عشق","حسادت","عقلانیت","موجودات هوشمند"],"chaos_mist":["دلالی","ادراک خاکستری","استفاده از سایه","اتهام","زیرمیزی","نظارت","بافتن گرداب","کفرگویی","واکاوی ساختار","حقیقت","آشوب و عدم‌قطعیت"],"condenser":["نجوم","ناوبری","بینش سرنوشت","آیین‌های قربانی","دستکاری گرانش","دستکاری فیزیک هسته‌ای","گرانش","جرم و چگالی","نیروهای بنیادی"],"everlasting":["جادوی آیینی","تفسیر","خطابه","آواز","انتقال دانش","قدرت فلسفی","ذهن و صدا","آگاهی و روح"],"second_law":["بیماری","فساد","اصابت قطعی","مرگ قطعی","پوسیدگی","زمان","فرسودگی","آنتروپی"],"sublunary_eye":["خلق قلمرو","دید حقیقی","خلق نقاشی‌های عرفانی","واقعی‌کردن امور خیالی","خلق جهان‌های نقاشی","دستکاری رشته‌ها","کنترل ابعاد","مشاهده","حقیقت"],"eternal_edict":["پیشگویی","مرگ جعلی","ادراک سرنوشت","سمفونی سرنوشت","رازکاوی سرنوشت","دستکاری سرنوشت","بافتن سرنوشت","داوری سرنوشت","زندگی ابدی"],"tail_devourer":["تقویت گوارش","تحلیل مواد اولیه","پردازش مواد اولیه","آشپزی عرفانی","سلب قدرت","بلعیدن","محوکردن","همگرایی"]};
  const detailedPathways = {"fool":[{"n":"9","name":"پیشگو","html":"<h4>ویژگی‌های کلی<\/h4><p>تمام امتیازهای آماری پیشگو در روحانیت، ذهن، شهود و تفسیر متمرکز شده‌اند و سهم بسیار کمی به مبارزه و تقویت جسمانی اختصاص دارد.<\/p><p><strong>حافظه تقویت‌شده<\/strong>: در ابتدا، کسانی که معجون پیشگو را می‌نوشند، افزایش اندکی در قدرت حافظه خود به دست می‌آورند؛ این توانایی در طول هضم معجون به‌تدریج بهتر می‌شود.<\/p><p>این حافظه تقویت‌شده به پیشگو اجازه می‌دهد مراحل گونه‌های مختلف جادوی آیینی و فنون پیشگویی را به خاطر بسپارد و بیاموزد.<\/p><p><strong>روحانیت<\/strong>: روحانیت یک پیشگو پس از نوشیدن این معجون افزایش می‌یابد.<\/p><p><strong>بینش روح<\/strong>: آن‌ها می‌توانند از بینش روح برای دیدن چیزهای غیرجسمانی، مانند ارواح و شبح‌ها استفاده کنند. همچنین قادرند بخش‌های مختلف یک روح را ببینند، از طریق آن وضعیت جسمانی و احساسات یک فرد را استنباط کنند و تشخیص دهند که چیزی دارای هاله‌ای جادویی هست یا نه.<\/p><p>آن‌ها می‌توانند اشیای پشت موانع را «ببینند» و صدای گام‌های بسیار ضعیف را «بشنوند» و از این طریق پیشاپیش درباره موقعیت داوری کنند. ولی رویا پردازی، شنوایی و حس لامسه آن‌ها به‌طور مستقیم تقویت نمی‌شود.<\/p><p>بینش روح یک پیشگو در تاریکی مطلق تنها به اندازه‌ای است که بتواند طرح محوی از پله‌ای را که زیر پایش قرار دارد تشخیص دهد. باقی محیط برای او چیزی جز خاکستریِ مه‌آلود و بسیار تار به نظر نمی‌رسد.<\/p><p><strong>فنون پیشگویی و جادوی آیینی<\/strong>: آن‌ها می‌توانند بر انواع روش‌های پیشگویی، از جمله طالع‌بینی، اعداد روحانی و غیب‌بینی، مسلط شوند و در زمینه جادوی آیینی حتی از یک رازکاو نیز دانش بیشتری به دست آورند.<\/p><p>پیشگوها دانش چگونگی استفاده مستقیم از این هنرهای اسرارآمیز را به دست نمی‌آورند؛ بلکه توانایی و استعداد انجام دادن آن‌ها را در سطحی متخصصانه کسب می‌کنند. میزان تسلطشان به مدت‌زمانی که صرف یادگیری کرده‌اند بستگی دارد.<\/p><p>پیشگوها می‌توانند با استفاده از روحانیت و از طریق اصطکاک، فتیله شمع را در یک لحظه شعله‌ور کنند و انجام آیین‌ها را آسان‌تر سازند. از این توانایی همچنین می‌توان برای سوزاندن کاغذی که در دست دارند استفاده کرد.<\/p><p><strong>شهود خطر<\/strong>: آن‌ها می‌توانند با اتکا به روحانیت خود، خطر را به‌صورت غریزی تشخیص دهند.<\/p>"},{"n":"8","name":"دلقک","html":"<p class=\"glance\"><b>در یک نگاه:<\/b> خنجرهای کاغذی<\/p><h4>ویژگی‌های کلی<\/h4><p><strong>تقویت جسمانی<\/strong>: پس از ارتقا به دلقک، کنترل بسیار نیرومندی بر بدن خود به دست می‌آورند؛ تا جایی که می‌توان آن‌ها را مانند یک بندباز و هنرمند سیرک حرفه‌ای دانست.<\/p><p>یک دلقک تقریباً کنترل کاملی بر عملکردهای بدنی و حالات چهره خود دارد.<\/p><p>چهره او تنها حالت‌هایی را نشان می‌دهد که خودش می‌خواهد؛ تنها شرایطی مانند شوک یا درد شدید می‌توانند احساسات واقعی او را آشکار کنند و همین موضوع دلقک را به دشمن طبیعی تماشاگران تبدیل می‌کند. این کنترل شامل اندام‌ها و دیگر بخش‌های بدن نیز می‌شود.<\/p><p>آن‌ها همچنین می‌توانند با آرام کردن ذهن خود، ظاهر فعلی‌شان را حفظ و همان حالت را به‌صورت بیرونی بازتاب دهند.<\/p><p>چابکی و سرعت آن‌ها به سطحی استثنایی می‌رسد و قدرت بدنی‌شان نیز به میزان قابل‌توجهی افزایش می‌یابد.<\/p><p><strong>روحانیت<\/strong>: روحانیت آن‌ها اندکی افزایش می‌یابد.<\/p><p><strong>شهود خطر<\/strong>: شهود خطر دلقک به‌طور چشمگیری تقویت می‌شود و حتی نوعی پیش‌آگاهی کوتاه‌مدت به آن‌ها می‌دهد؛ هرچند این پیش‌آگاهی اغلب مبهم و نامشخص است.<\/p><p>آن‌ها می‌توانند به‌شکلی فراطبیعی ظاهر شخص یا گروهی از افراد را که پشت یک در ایستاده‌اند، بدون آنکه خود در را باز کنند ببینند. این توانایی به بینش روح وابسته نیست.<\/p><p>گاهی می‌توانند به‌صورت غریزی عمل بعدی فردی را پیش‌بینی کنند. چون این اتفاق چندان مکرر رخ نمی‌دهد، چنین توانایی‌ای صرفاً فرصتی برای بهره‌برداری فراهم می‌کند.<\/p><p>درست مانند پیشگویی، این توانایی درباره اقداماتی که به دلقک آسیب می‌رسانند، بسیار قابل‌اعتمادتر است. به همین دلیل دلقک اغلب می‌تواند پیشاپیش از حملاتی که احتمالاً مرگبار خواهند بود جاخالی دهد.<\/p><h4>چه توانایی‌هایی می‌گیری<\/h4><p><strong>خنجرهای کاغذی<\/strong>: دلقک می‌تواند برای مدتی موقت، ورق‌های کاغذ را به سختی و تیزی فولاد درآورد و آن‌ها را مانند خنجرهای پرتابی یا چاقو به کار گیرد.<\/p><p>خنجرهای کاغذی ساخته‌شده توسط دلقک آن‌قدر قدرتمندند که می‌توانند در سنگ جامد فرو بروند و از گوشت و استخوان یک شکارچی عبور کنند.<\/p>"},{"n":"7","name":"جادوگر","html":"<p class=\"glance\"><b>در یک نگاه:<\/b> انتقال آسیب، پرش شعله، گلوله هوا، جایگزین آدمک کاغذی، کنترل شعله<\/p><h4>ویژگی‌های کلی<\/h4><p><strong>تقویت جسمانی<\/strong>: دست‌های آن‌ها چابک‌تر و انعطاف‌پذیرتر می‌شوند. حتی بدون داشتن قدرت‌های بیاندر، اگر به اندازه کافی تلاش کنند، می‌توانند به جادوگرانی در سطح عالی تبدیل شوند.<\/p><p><strong>بینش روح<\/strong>: توانایی آن‌ها برای دیدن امور روحانی اندکی بهتر می‌شود، اما این افزایش چندان چشمگیر نیست.<\/p><h4>چه توانایی‌هایی می‌گیری<\/h4><p>جادوگران 9 توانایی شبیه به طلسم در اختیار دارند که می‌توانند آن‌ها را با سرعت بالا اجرا کنند، بدون اینکه برای فعال‌سازی به وردخوانی یا تزریق روحانیت نیاز داشته باشند.<\/p><p><strong>انتقال آسیب<\/strong>: تا زمانی که یک جادوگر نمرده باشد و هنوز بتواند دستش را حرکت دهد، می‌تواند زخم‌های خود را به بخش‌های دیگری مانند دست‌ها یا پاها منتقل کند و در نتیجه زخم‌های مرگبار را به آسیب‌هایی جزئی تبدیل نماید.<\/p><p><strong>پرش شعله<\/strong>: یک جادوگر می‌تواند از میان جرقه آتشی که پیش‌تر بر جای گذاشته است و همچنین هر شعله‌ای که در فاصله 30 متری وجود داشته باشد، گذر کند. این برد به‌مرور و با هضم معجون افزایش می‌یابد.<\/p><p><strong>گلوله هوا<\/strong>: جادوگران می‌توانند تنها با بشکن زدن یا تقلید صدای شلیک اسلحه، پرتابه‌هایی از هوا ایجاد کنند که قدرت و سرعتشان با گلوله‌های شلیک‌شده از یک هفت‌تیر سفارشی قابل مقایسه است.<\/p><p><strong>جایگزین آدمک کاغذی<\/strong>: جادوگران می‌توانند یک آدمک کاغذی را به شکل خود درآورند و با آن جای خود را عوض کنند. این توانایی نه‌تنها می‌تواند ضربه‌ای مرگبار را مهار کند، بلکه می‌تواند شدت آسیب نفرین‌ها را نیز کاهش دهد.<\/p><p><strong>کنترل شعله<\/strong>: جادوگران می‌توانند شعله‌ها را آزادانه دستکاری کنند و مواد قابل‌اشتعال معینی را در محدوده 30 متری تنها با یک حرکت ساده مشتعل سازند.<\/p><p><strong>تنفس زیر آب<\/strong>: جادوگر می‌تواند لوله‌ای باریک و نامرئی از هوا ایجاد کند که به او اجازه می‌دهد آزادانه زیر آب نفس بکشد و ظاهراً به چیزی شبیه مردماهی تبدیل شود.<\/p><p><strong>نرم‌کردن استخوان<\/strong>: این توانایی به جادوگر اجازه می‌دهد استخوان‌هایش را تا حدی نرم کند. از آن می‌توان برای فرار از انواع مهارها، مانند دست‌بند، طناب و صندوق، استفاده کرد.<\/p><p><strong>تبدیل کاغذ به سلاح<\/strong>: این توانایی تکامل خنجرهای کاغذی دلقک است. اکنون به جادوگر اجازه می‌دهد کاغذ را به انواع گوناگون سلاح، مانند چوب بیسبال، آجر، عصا و مانند آن تبدیل کند.<\/p><p><strong>ایجاد توهم<\/strong>: آن‌ها می‌توانند بر محیط اثر بگذارند و توهماتی از رنگ، صدا و بو ایجاد کنند که تا حد زیادی به واقعیت نزدیک باشند؛ به‌گونه‌ای که دروغ بتواند به‌عنوان حقیقت جلوه کند.<\/p>"},{"n":"6","name":"بی‌چهره","html":"<p class=\"glance\"><b>در یک نگاه:<\/b> تغییرشکل<\/p><h4>ویژگی‌های کلی<\/h4><p>آن‌ها در زمینه پیشگویی و مهارت‌های مبارزه نیز بهبودهایی پیدا می‌کنند.<\/p><h4>چه توانایی‌هایی می‌گیری<\/h4><p><strong>تغییرشکل<\/strong>: آن‌ها می‌توانند هر زمان که بخواهند به هر شخصی تبدیل شوند؛ زیرا قادرند بدن و گوشت خود را آزادانه شکل دهند و چهره، اندام، صدا و حتی تا حدی بوی هدف را به شکلی کامل تقلید کنند.<\/p><p>یک بی‌چهره می‌تواند ویژگی‌های صورت و تناسبات بدنی فردی از جنسیت مخالف را تقلید کند، اما نمی‌تواند جنسیت فیزیکی واقعی خود را تغییر دهد.<\/p><p>محدودیت‌های تغییرشکل بی‌چهره شامل قد و جرم بدن نیز می‌شود. او نمی‌تواند تناسبات بدنی فردی را تقلید کند که اندازه‌اش بیش از حد با بدن اصلی او تفاوت دارد.<\/p><p>قد جدید او نمی‌تواند بیش از اندازه‌ای برابر با یک سر بلندتر یا کوتاه‌تر از قد اصلی‌اش باشد.<\/p><p>برای بزرگ و کوچک کردن سر، پاها، دست‌ها، استخوان‌ها و دیگر بخش‌ها نیز محدودیت‌هایی وجود دارد.<\/p><p>یک بی‌چهره کنترل کاملی بر دگرگونی بدن خود دارد.<\/p><p>او می‌تواند جای چشم‌ها و دیگر اجزای صورتش را آزادانه روی چهره جابه‌جا کند.<\/p><p>حتی می‌تواند صورت خود را کاملاً بی‌ویژگی کند؛ به‌گونه‌ای که هیچ چشم، بینی یا دهانی نداشته باشد.<\/p><p>همچنین قادر است ویژگی‌های «جعلی» روی چهره خود ایجاد کند؛ برای مثال چشم‌های دروغین.<\/p><p>او می‌تواند با تنظیم منافذ پوست، بوی بدن خود را تغییر دهد.<\/p><p>ولی همچنان قادر به تغییر بخش پایینی بدن خود نیست.<\/p><p>تغییرشکل و کنترل کامل بدن باعث می‌شود یک بی‌چهره در بازیگری مهارت بالایی داشته باشد.<\/p><p>آن‌ها می‌توانند شکل ظاهری و خلق‌وخوی تمام کسانی را که می‌شناسند با دقت به یاد بیاورند و آنان را صرف‌نظر از اینکه چقدر خوب تغییر چهره داده باشند، تشخیص دهند.<\/p><p>ترکیب مهارت‌های معجون‌های پیشین با تغییرشکل باعث می‌شود در مبارزه، ردیابی و ضدردیابی مهارت خوبی داشته باشند.<\/p><h4>چه چیزهایی قوی‌تر می‌شود<\/h4><p>توانایی‌های قبلی آن‌ها تقویت می‌شوند.<\/p><p>کنترل شعله، پرش شعله و دیگر قدرت‌های بیاندر حدود 30 درصد نیرومندتر می‌شوند.<\/p><p>قدرت اولیه گلوله‌های هوای آن‌ها و طول لوله نامرئیِ مورد استفاده برای تنفس زیر آب چندین برابر افزایش می‌یابد.<\/p><p>به دلیل افزایش روحانیت، تعداد دفعاتی که یک بی‌چهره می‌تواند از جایگزین آدمک کاغذی و انتقال آسیب استفاده کند نیز بیشتر می‌شود.<\/p>"},{"n":"5","name":"عروسک‌گردان","html":"<p class=\"glance\"><b>در یک نگاه:<\/b> دستکاری رشته‌های بدن روح، عروسک<\/p><h4>چه توانایی‌هایی می‌گیری<\/h4><p><strong>دستکاری رشته‌های بدن روح<\/strong>: این قدرت، توانایی محوری عروسک‌گردان است. به کمک آن، می‌تواند رشته‌های بدن روح را از فاصله‌ای تا 100 متر ادراک و دستکاری کند.<\/p><p>با دستکاری رشته‌های بدن روح یک موجود، او مستقیماً بر کالبد روح، فرافکنی اختری، بدن قلب و ذهن و بدن اثیری هدف اثر می‌گذارد. سپس با استفاده از بدن اثیری به‌عنوان واسطه، می‌تواند بدن هدف را کنترل کند.<\/p><p>در یک سطح سکانسی یکسان، اهدافی که به عروسک بدل شده‌اند دیگر نمی‌توانند از روش‌های رستاخیز خود برای زنده شدن و فرار از وضعیت عروسکی استفاده کنند.<\/p><p>این موضوع شامل توانایی‌های رستاخیز جاودانه، بی‌پیر، دوک خونین، شوالیه بداقبالی و امپراتور سیاه می‌شود، هرچند ممکن است تنها به این موارد محدود نباشد.<\/p><p>یک عروسک می‌تواند با استفاده از توانایی‌های مسیر اصلی خود رستاخیز کند؛ اما همچنان عروسک باقی خواهد ماند.<\/p><p>اگر وضعیت عروسکی برطرف شود و سپس عروسک بمیرد، مالک اصلی همچنان قادر به رستاخیز نخواهد بود.<\/p><p>در عوض، او عروسک باقی می‌ماند و بارها به مرگ خود ادامه می‌دهد تا زمانی که تمام دفعات رستاخیزش به پایان برسد.<\/p><p><strong>عروسک<\/strong>: عروسک همانند یک خیمه‌شب‌بازیک است و کاملاً تحت کنترل عروسک‌گردان خود قرار دارد. از هر نظر مرده محسوب می‌شود، هرچند همچنان روح دارد.<\/p><p>به‌جز افکار سطحی و سطح بیرونی ذهن، عروسک نمی‌تواند از جزئیات زندگی گذشته خود آگاه باشد؛ مگر اینکه با چیزی یا کسی آشنا روبه‌رو شود.<\/p><p>تنها در چنین شرایطی است که جزئیات مربوط به آن مکان یا شخص آشنا را «به یاد می‌آورد».<\/p><p>عروسک‌گردان در ابتدا تنها می‌تواند یک عروسک را هم‌زمان کنترل کند. پس از هضم کامل معجون، این تعداد می‌تواند به حداکثر 3 عروسک برسد.<\/p><p>او همچنان می‌تواند رشته‌های بدن روح دیگران را کنترل کند، اما بدون عبور از حد فعلی خود نمی‌تواند آن‌ها را به‌طور کامل به عروسک تبدیل کند.<\/p><p>عروسک‌ها می‌توانند به هر زبانی که در زمان حیات آموخته‌اند سخن بگویند، حتی زبان‌هایی که عروسک‌گردان در حال حاضر نمی‌داند.<\/p><p>ولی عروسک‌گردان از این طریق خودِ آن زبان را یاد نمی‌گیرد و نمی‌تواند شخصاً به آن زبان سخن بگوید.<\/p><h4>چه چیزهایی قوی‌تر می‌شود<\/h4><p>عروسک‌گردان‌ها همچنین دست‌کم 50 درصد افزایش در قدرت‌های بیاندر خود دریافت می‌کنند.<\/p><p><strong>گلوله هوا<\/strong>: قدرت آن اکنون با گلوله شلیک‌شده از یک تفنگ بخاری قابل مقایسه است.<\/p>"},{"n":"4","name":"جادوگر عجیب‌وغریب","html":"<p class=\"glance\"><b>در یک نگاه:<\/b> اعطا، پنهان‌سازی<\/p><h4>ویژگی‌های کلی<\/h4><p><strong>روحانیت<\/strong>: روحانیت آن‌ها افزایش یافته است.<\/p><p><strong>پیشگویی<\/strong>: جادوگران عجیب‌وغریب می‌توانند با استفاده از روش‌های ساده پیشگویی، مانند پیشگویی آنی از خواب با انداختن یک سکه، اطلاعات بیشتری به دست آورند.<\/p><p><strong>بینش روح<\/strong>: محدودیتی که پیش‌تر ایجاب می‌کرد برای فعال‌کردن بینش روح دست به عملی متناسب بزنند، اکنون از بین رفته است و می‌توانند هر زمان که بخواهند آن را فعال کنند.<\/p><h4>چه توانایی‌هایی می‌گیری<\/h4><p><strong>اعطا<\/strong>: جادوگران عجیب‌وغریب می‌توانند کرم‌های روح خود را به عروسک‌هایشان «هدیه» دهند و از این طریق به عروسک‌های اعطاشده اجازه دهند از قدرت‌های بیاندر جادوگر عجیب‌وغریب استفاده کنند.<\/p><p>در ابتدا، جادوگر عجیب‌وغریب فقط می‌تواند 50 کرم روح را از فرم موجود اسطوره‌ای خود جدا کند. این تعداد با هضم معجون افزایش می‌یابد.<\/p><p><strong>پنهان‌سازی<\/strong>: جادوگران عجیب‌وغریب تا حدی از توانایی‌های پنهان‌سازی برخوردارند.<\/p><p>آن‌ها می‌توانند سطح سکانس خود را از بیاندرِ مسیر داور که در همان 
