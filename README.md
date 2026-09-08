<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="theme-color" content="#183c2d" />
  <title>KAIN TAYO — Lutong Pinoy, Kwentong Atin</title>
  <meta name="description" content="Discover Filipino dishes, recipes, regional food, and step-by-step Cook Mode." />
  <style>
    :root{
      --green:#183c2d;
      --green-2:#285540;
      --cream:#f8f3e8;
      --cream-2:#fffdf8;
      --orange:#c9683f;
      --orange-2:#e18a5c;
      --ink:#1d2721;
      --muted:#6d756f;
      --line:rgba(29,39,33,.12);
      --card:#fffdf9;
      --shadow:0 20px 50px rgba(27,48,37,.10);
      --radius:24px;
      --diff-easy:#3f7d55;
      --diff-medium:#c9683f;
      --diff-hard:#a23b34;
    }

    *{box-sizing:border-box}
    html{scroll-behavior:smooth}
    body{
      margin:0;
      font-family:Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      color:var(--ink);
      background:
        radial-gradient(circle at 8% 6%, rgba(201,104,63,.09), transparent 26%),
        radial-gradient(circle at 90% 20%, rgba(40,85,64,.08), transparent 25%),
        var(--cream);
      line-height:1.5;
    }
    button,input{font:inherit}
    button{cursor:pointer}
    img{display:block;max-width:100%}
    a{text-decoration:none;color:inherit}

    .container{width:min(1180px,92%);margin:auto}
    .topline{
      background:var(--green);
      color:#eef4ef;
      text-align:center;
      font-size:.78rem;
      padding:8px 16px;
      letter-spacing:.08em;
      text-transform:uppercase;
    }

    header{
      position:sticky;
      top:0;
      z-index:50;
      backdrop-filter: blur(16px);
      background:rgba(248,243,232,.86);
      border-bottom:1px solid var(--line);
    }
    .nav{
      min-height:76px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:20px;
    }
    .brand{
      display:flex;
      align-items:center;
      gap:10px;
      font-weight:900;
      letter-spacing:.04em;
      font-size:1.13rem;
    }
    .brand-mark{
      width:38px;height:38px;border-radius:13px;
      display:grid;place-items:center;
      background:var(--green);
      color:white;
      box-shadow:0 9px 24px rgba(24,60,45,.2);
    }
    .navlinks{display:flex;gap:25px;align-items:center;font-size:.93rem;color:#3d493f}
    .navlinks a{transition:.2s}
    .navlinks a:hover{color:var(--orange)}
    .nav-actions{display:flex;gap:10px;align-items:center}
    .icon-btn{
      position:relative;
      border:1px solid var(--line);
      background:rgba(255,255,255,.55);
      width:42px;height:42px;border-radius:14px;
      display:grid;place-items:center;color:var(--green);
    }
    .badge{
      position:absolute;top:-5px;right:-5px;min-width:17px;height:17px;padding:0 4px;
      border-radius:99px;background:var(--orange);color:#fff;
      font-size:.62rem;font-weight:900;display:flex;align-items:center;justify-content:center;line-height:1;
    }

    .hero{
      padding:48px 0 28px;
    }
    .hero-card{
      position:relative;
      overflow:hidden;
      min-height:560px;
      border-radius:34px;
      background:
        linear-gradient(90deg, rgba(12,27,20,.88) 0%, rgba(12,27,20,.57) 44%, rgba(12,27,20,.16) 72%, rgba(12,27,20,.04) 100%),
        url("https://images.unsplash.com/photo-1601050690597-df0568f70950?auto=format&fit=crop&w=1800&q=85") center/cover;
      box-shadow:var(--shadow);
      display:flex;
      align-items:center;
    }
    .hero-content{
      width:min(620px,90%);
      color:#fff;
      padding:60px;
    }
    .eyebrow{
      display:inline-flex;align-items:center;gap:7px;
      padding:7px 12px;border:1px solid rgba(255,255,255,.25);
      background:rgba(255,255,255,.1);backdrop-filter:blur(10px);
      border-radius:99px;font-size:.76rem;text-transform:uppercase;
      letter-spacing:.1em;font-weight:800;
    }
    h1,h2,h3{font-family:Georgia, "Times New Roman", serif;line-height:1.04;margin:0}
    h1{font-size:clamp(3rem,7vw,6.3rem);letter-spacing:-.05em;margin:18px 0 16px}
    .hero p{font-size:1.06rem;color:rgba(255,255,255,.86);max-width:530px}
    .search{
      margin-top:26px;
      display:flex;align-items:center;
      padding:8px;
      background:white;border-radius:18px;
      max-width:610px;
      box-shadow:0 15px 40px rgba(0,0,0,.18);
    }
    .search span{padding:0 13px;font-size:1.15rem}
    .search input{
      border:0;outline:0;flex:1;min-width:0;
      padding:14px 3px;font-size:.98rem;color:var(--ink);
    }
    .search button{
      border:0;background:var(--orange);color:white;
      padding:13px 18px;border-radius:13px;font-weight:800;
    }
    .hero-buttons{display:flex;gap:12px;margin-top:18px;flex-wrap:wrap}
    .btn{
      border:0;border-radius:14px;padding:13px 18px;font-weight:800;
      transition:.2s;display:inline-flex;align-items:center;gap:8px;
    }
    .btn-primary{background:var(--orange);color:#fff}
    .btn-secondary{background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.25);color:#fff}
    .btn:hover{transform:translateY(-2px)}

    section{padding:70px 0}
    .section-head{display:flex;align-items:end;justify-content:space-between;gap:18px;margin-bottom:24px}
    .section-head h2{font-size:clamp(2rem,4vw,3.35rem)}
    .section-head p{margin:0;color:var(--muted);max-width:500px}
    .small-link{color:var(--orange);font-weight:800;font-size:.9rem;white-space:nowrap}

    .quick-grid{
      display:grid;grid-template-columns:repeat(6,1fr);gap:14px;
    }
    .quick-card{
      background:rgba(255,255,255,.6);
      border:1px solid var(--line);
      border-radius:20px;
      padding:19px 15px;
      text-align:center;
      transition:.2s;
    }
    .quick-card:hover{transform:translateY(-4px);box-shadow:var(--shadow);background:#fffdf8}
    .quick-icon{font-size:1.75rem;display:block;margin-bottom:8px}
    .quick-card strong{font-size:.9rem}

    .filterbar{
      display:flex;flex-wrap:wrap;gap:10px;
      margin-bottom:24px;
    }
    .filter{
      background:rgba(255,255,255,.65);border:1px solid var(--line);
      color:var(--ink);border-radius:99px;padding:10px 14px;font-weight:700;
    }
    .filter.active{background:var(--green);color:#fff;border-color:var(--green)}

    .recipe-grid{
      display:grid;grid-template-columns:repeat(3,1fr);gap:22px;
    }
    .recipe-card{
      background:var(--card);
      border:1px solid var(--line);
      border-radius:24px;
      overflow:hidden;
      box-shadow:0 8px 30px rgba(27,48,37,.05);
      transition:.25s;
    }
    .recipe-card:hover{transform:translateY(-5px);box-shadow:var(--shadow)}
    .recipe-img-wrap{position:relative;aspect-ratio:16/11;overflow:hidden}
    .recipe-img{width:100%;height:100%;object-fit:cover;transition:.35s}
    .recipe-card:hover .recipe-img{transform:scale(1.04)}
    .save{
      position:absolute;right:12px;top:12px;
      width:40px;height:40px;border:0;border-radius:50%;
      background:rgba(255,255,255,.92);color:var(--green);
      display:grid;place-items:center;font-size:1.15rem;
    }
    .save.saved{background:var(--green);color:white}
    .recipe-body{padding:19px}
    .chips{display:flex;flex-wrap:wrap;gap:7px;margin-bottom:10px}
    .chip{
      background:#edf1eb;color:var(--green);
      padding:5px 9px;border-radius:99px;
      font-size:.7rem;font-weight:800;text-transform:uppercase;letter-spacing:.05em;
    }
    .recipe-body h3{font-size:1.55rem;margin-bottom:8px}
    .recipe-body p{margin:0;color:var(--muted);font-size:.89rem}
    .meta{display:flex;gap:14px;margin-top:14px;font-size:.8rem;color:#5c665f;flex-wrap:wrap}
    .meta span{display:inline-flex;align-items:center;gap:5px}
    .view-recipe{
      width:100%;margin-top:15px;border:0;
      background:var(--green);color:#fff;border-radius:13px;padding:11px;
      font-weight:800;
    }

    .story{
      display:grid;grid-template-columns:1.05fr .95fr;gap:24px;align-items:stretch;
    }
    .story-copy,.story-image{
      border-radius:28px;overflow:hidden;
    }
    .story-copy{
      background:var(--green);color:#fff;padding:44px;
      position:relative;
    }
    .story-copy:after{
      content:"✦";
      position:absolute;right:35px;top:22px;
      font-size:4rem;opacity:.12;
    }
    .story-copy h2{font-size:3rem;margin:13px 0 15px}
    .story-copy p{color:rgba(255,255,255,.78)}
    .story-image{
      min-height:420px;
      background:url("https://images.unsplash.com/photo-1604908176997-125f25cc6f3d?auto=format&fit=crop&w=1400&q=85") center/cover;
    }

    .regions{
      display:grid;grid-template-columns:repeat(3,1fr);gap:18px;
    }
    .region{
      min-height:210px;border-radius:24px;overflow:hidden;position:relative;
      background-size:cover;background-position:center;
      display:flex;align-items:end;
      box-shadow:0 12px 30px rgba(27,48,37,.08);
    }
    .region:after{content:"";position:absolute;inset:0;background:linear-gradient(0deg,rgba(0,0,0,.76),rgba(0,0,0,.04))}
    .region-content{position:relative;z-index:2;color:#fff;padding:22px}
    .region-content h3{font-size:2rem}
    .region-content p{margin:4px 0 0;color:rgba(255,255,255,.78);font-size:.86rem}

    .planner{
      background:#efe6d2;border:1px solid rgba(55,45,28,.09);
      border-radius:30px;padding:34px;
      display:grid;grid-template-columns:1fr 1fr;gap:30px;align-items:center;
    }
    .planner h2{font-size:2.8rem}
    .planner p{color:#6c6659}
    .ingredient-box{
      background:#fffdf8;border-radius:22px;padding:18px;border:1px solid var(--line);
    }
    .ingredient-row{display:flex;gap:9px;flex-wrap:wrap}
    .ingredient-row input{
      flex:1;min-width:180px;padding:13px 14px;border:1px solid var(--line);
      border-radius:13px;outline:0;background:white;
    }
    .suggestions{margin-top:13px;display:grid;gap:9px}
    .suggestion{
      display:flex;align-items:center;justify-content:space-between;gap:12px;
      border:1px solid var(--line);border-radius:13px;padding:11px 13px;
      background:#fff;
    }
    .suggestion small{color:var(--muted)}

    footer{
      margin-top:30px;background:var(--green);color:#dce7df;padding:46px 0;
    }
    .footer-grid{display:grid;grid-template-columns:1.3fr 1fr 1fr;gap:30px}
    .footer-grid h3{font-size:1.35rem;margin-bottom:10px}
    .footer-grid p,.footer-grid a{color:#adc0b4;font-size:.88rem}
    .footer-links{display:grid;gap:7px}
    .copy{border-top:1px solid rgba(255,255,255,.14);margin-top:26px;padding-top:16px;font-size:.76rem;color:#91a69a}

    /* Modal */
    .modal{
      position:fixed;inset:0;background:rgba(9,17,12,.68);
      display:none;align-items:center;justify-content:center;
      padding:20px;z-index:100;
      backdrop-filter:blur(8px);
    }
    .modal.open{display:flex}
    .modal-card{
      background:var(--cream-2);width:min(980px,100%);max-height:92vh;overflow:auto;
      border-radius:30px;box-shadow:0 25px 80px rgba(0,0,0,.28);
      position:relative;
    }
    .close{
      position:absolute;right:18px;top:18px;z-index:3;
      width:42px;height:42px;border-radius:50%;border:0;
      background:rgba(255,255,255,.9);color:var(--green);font-size:1.1rem;
    }
    .modal-hero{display:grid;grid-template-columns:1.05fr .95fr}
    .modal-hero img{width:100%;height:100%;min-height:300px;object-fit:cover}
    .modal-info{padding:38px}
    .modal-info h2{font-size:3rem;margin:12px 0 10px}
    .modal-meta{display:flex;gap:10px;flex-wrap:wrap;margin:16px 0}
    .modal-meta span{padding:8px 11px;border-radius:10px;background:#eff2ed;font-size:.82rem;font-weight:800}
    .modal-grid{padding:0 38px 38px;display:grid;grid-template-columns:.72fr 1.28fr;gap:28px}
    .modal-grid h3{font-size:1.55rem;margin-bottom:13px}
    .ingredients{display:grid;gap:9px}
    .ingredient-item{
      padding:10px 12px;border:1px solid var(--line);border-radius:12px;background:#fff;
      font-size:.9rem;
    }
    .steps{display:grid;gap:11px}
    .step{
      display:grid;grid-template-columns:42px 1fr;gap:11px;
      padding:14px;border-radius:14px;background:#fff;border:1px solid var(--line);
    }
    .step-num{
      width:38px;height:38px;border-radius:11px;background:var(--orange);
      color:#fff;display:grid;place-items:center;font-weight:900;
    }

    /* Cook mode */
    .cook-overlay{
      position:fixed;inset:0;background:#102319;color:#f5f1e7;
      z-index:140;display:none;flex-direction:column;
    }
    .cook-overlay.open{display:flex}
    .cook-top{display:flex;justify-content:space-between;align-items:center;padding:22px 24px;border-bottom:1px solid rgba(255,255,255,.1)}
    .cook-main{width:min(920px,90%);margin:auto;display:flex;flex-direction:column;align-items:center;text-align:center;padding-bottom:30px}
    .cook-main .step-counter{text-transform:uppercase;letter-spacing:.13em;font-size:.8rem;color:#9fafa5;font-weight:800}
    .cook-main h2{font-size:clamp(3rem,7vw,6.5rem);margin:16px 0 20px;max-width:850px}
    .cook-main p{font-size:1.3rem;color:#b9c6be;max-width:760px}
    .cook-controls{display:flex;gap:10px;flex-wrap:wrap;justify-content:center;margin-top:28px}
    .cook-controls button{min-width:130px}
    .progress{width:min(720px,86%);height:8px;background:rgba(255,255,255,.12);border-radius:99px;overflow:hidden;margin-top:16px}
    .progress i{display:block;height:100%;width:0;background:var(--orange);transition:.25s}

    .empty{grid-column:1/-1;text-align:center;padding:50px 20px;border:1px dashed var(--line);border-radius:22px;color:var(--muted)}

    @media(max-width:950px){
      .navlinks{display:none}
      .quick-grid{grid-template-columns:repeat(3,1fr)}
      .recipe-grid{grid-template-columns:repeat(2,1fr)}
      .story,.planner,.modal-hero,.modal-grid{grid-template-columns:1fr}
      .modal-hero img{max-height:380px}
      .regions{grid-template-columns:1fr}
      .footer-grid{grid-template-columns:1fr 1fr}
    }
    @media print{
      header,.topline,.hero,section:not(#recipes),footer,.utility-bar,.filterbar,.section-head,.close,.modal-toolbar,#modalCookBtn,#recipeGrid,.shopping-drawer,.toast,.cook-overlay{display:none!important}
      .modal.open{position:static;background:none!important;display:block!important;padding:0}
      .modal-card{box-shadow:none;max-height:none;width:100%}
      .modal-hero{grid-template-columns:1fr}
      .modal-hero img{max-height:300px}
      body{background:#fff!important}
    }
    @media(max-width:640px){
      .hero{padding-top:20px}
      .hero-card{min-height:620px;border-radius:26px}
      .hero-content{padding:30px 24px}
      h1{font-size:3.4rem}
      .quick-grid{grid-template-columns:repeat(2,1fr)}
      .recipe-grid{grid-template-columns:1fr}
      section{padding:52px 0}
      .story-copy{padding:30px}
      .story-copy h2,.planner h2{font-size:2.3rem}
      .planner{padding:23px}
      .footer-grid{grid-template-columns:1fr}
      .modal-info,.modal-grid{padding:25px}
      .modal-info h2{font-size:2.3rem}
    }

    /* Enhanced app features */
    .utility-bar{display:flex;gap:10px;flex-wrap:wrap;margin:0 0 24px;align-items:center}
    .utility-btn{border:1px solid var(--line);background:#fffdf8;color:var(--green);border-radius:13px;padding:10px 13px;font-weight:800}
    .utility-btn:hover{transform:translateY(-2px);box-shadow:0 10px 22px rgba(27,48,37,.08)}
    .sort-select{border:1px solid var(--line);background:#fffdf8;color:var(--green);border-radius:13px;padding:10px 13px;font-weight:800;cursor:pointer}
    .recipe-extra{display:flex;justify-content:space-between;align-items:center;gap:10px;margin-top:13px}
    .rating{font-size:.82rem;color:#9b6a22;font-weight:800}
    .diff-dot{display:inline-block;width:8px;height:8px;border-radius:50%;margin-right:5px;vertical-align:middle}

    /* Recently viewed */
    .recent-section{padding:34px 0 0}
    .recent-head{display:flex;align-items:center;justify-content:space-between;gap:14px;margin-bottom:14px}
    .recent-strip{display:flex;gap:12px;overflow-x:auto;padding-bottom:8px;scrollbar-width:thin}
    .recent-card{
      flex:0 0 auto;width:180px;text-align:left;border:1px solid var(--line);
      background:var(--card);border-radius:16px;overflow:hidden;transition:.2s;
    }
    .recent-card:hover{transform:translateY(-3px);box-shadow:var(--shadow)}
    .recent-card img{width:100%;height:100px;object-fit:cover}
    .recent-card strong{display:block;padding:9px 11px 11px;font-size:.83rem;line-height:1.3}
    .modal-toolbar{display:flex;gap:8px;flex-wrap:wrap;margin:16px 0}
    .mini-btn{border:1px solid var(--line);background:#fff;border-radius:11px;padding:9px 11px;font-weight:800;color:var(--green)}
    .serving-control{display:flex;align-items:center;gap:9px;padding:7px 10px;border:1px solid var(--line);border-radius:11px;background:#fff;font-weight:800}
    .serving-control button{width:28px;height:28px;border:0;border-radius:8px;background:#edf1eb;color:var(--green);font-weight:900}
    .shopping-drawer{position:fixed;right:18px;bottom:18px;width:min(390px,calc(100% - 36px));background:var(--cream-2);border:1px solid var(--line);border-radius:22px;box-shadow:0 25px 70px rgba(0,0,0,.2);z-index:120;display:none;overflow:hidden}
    .shopping-drawer.open{display:block}
    .shopping-head{display:flex;justify-content:space-between;align-items:center;padding:16px 18px;background:var(--green);color:#fff}
    .shopping-list{max-height:310px;overflow:auto;padding:12px 16px;display:grid;gap:8px}
    .shopping-item{display:flex;gap:9px;align-items:center;padding:9px;border-bottom:1px solid var(--line);font-size:.9rem}
    .shopping-item input{accent-color:var(--orange)}
    .drawer-actions{display:flex;gap:8px;padding:12px 16px;border-top:1px solid var(--line)}
    .toast{position:fixed;left:50%;bottom:22px;transform:translate(-50%,20px);background:var(--green);color:#fff;padding:11px 16px;border-radius:99px;box-shadow:0 15px 35px rgba(0,0,0,.18);opacity:0;pointer-events:none;transition:.25s;z-index:250;font-weight:800}
    .toast.show{opacity:1;transform:translate(-50%,0)}
    .theme-dark{--cream:#111812;--cream-2:#172119;--ink:#eef5ef;--muted:#aab7ae;--line:rgba(255,255,255,.11);--card:#172119}
    .theme-dark body{background:var(--cream)}
    .theme-dark .quick-card,.theme-dark .utility-btn,.theme-dark .sort-select,.theme-dark .filter,.theme-dark .mini-btn,.theme-dark .serving-control,.theme-dark .ingredient-box,.theme-dark .suggestion,.theme-dark .recipe-card,.theme-dark .recent-card,.theme-dark .modal-card{background:var(--card);color:var(--ink)}
    .theme-dark .search{background:#fff;color:#1d2721}
    .theme-dark header{background:rgba(17,24,18,.88)}
    .theme-dark .topline{background:#0b100c}
    @media(max-width:640px){
      .utility-bar{display:grid;grid-template-columns:1fr 1fr}
      .utility-btn,.sort-select{width:100%}
      .shopping-drawer{right:10px;bottom:10px;width:calc(100% - 20px)}
    }

  </style>
</head>
<body>
  <div class="topline">🇵🇭 Proudly Filipino recipes • Simple ingredients • Stories from home</div>

  <header>
    <div class="container nav">
      <a href="#" class="brand">
        <span class="brand-mark">🍴</span>
        <span>KAIN TAYO</span>
      </a>
      <nav class="navlinks">
        <a href="#recipes">Recipes</a>
        <a href="#regions">Regions</a>
        <a href="#discover">Discover</a>
        <a href="#planner">What Can I Cook?</a>
      </nav>
      <div class="nav-actions">
        <button class="icon-btn" id="randomNav" title="Surprise me">🎲</button>
        <button class="icon-btn" id="shoppingNav" title="Shopping list">🛒</button>
        <button class="icon-btn" id="themeNav" title="Toggle theme">☾</button>
        <button class="icon-btn" id="favoriteNav" title="Show favorite recipes">♡<span class="badge" id="favBadge" hidden>0</span></button>
      </div>
    </div>
  </header>

  <main>
    <section class="hero">
      <div class="container">
        <div class="hero-card">
          <div class="hero-content">
            <span class="eyebrow">Lutong Pinoy, Kwentong Atin</span>
            <h1>What are we cooking today?</h1>
            <p>Discover comforting Filipino dishes, regional favorites, and easy step-by-step recipes made for everyday cooking.</p>

            <form class="search" id="searchForm">
              <span>⌕</span>
              <input id="searchInput" type="search" placeholder="Search Adobo, Sinigang, Kare-Kare..." aria-label="Search recipes" />
              <button type="submit">Search</button>
            </form>

            <div class="hero-buttons">
              <a href="#recipes" class="btn btn-primary">Explore Recipes →</a>
              <button class="btn btn-secondary" id="heroCookBtn">👨‍🍳 Cook Mode</button>
              <button class="btn btn-secondary" id="heroRandomBtn">🎲 Surprise Me</button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="recentSection" class="recent-section" style="display:none">
      <div class="container">
        <div class="recent-head">
          <div class="eyebrow" style="background:#fff;color:var(--green);border-color:var(--line)">Pick up where you left off</div>
          <button class="small-link" id="clearRecentBtn" type="button" style="border:0;background:none">Clear</button>
        </div>
        <div class="recent-strip" id="recentStrip"></div>
      </div>
    </section>

    <section id="discover">
      <div class="container">
        <div class="section-head">
          <div>
            <div class="eyebrow" style="background:#fff;color:var(--green);border-color:var(--line)">Find your craving</div>
            <h2 style="margin-top:12px">Cook by category</h2>
          </div>
          <p>From everyday ulam to special-occasion favorites—start with the kind of food you’re craving.</p>
        </div>
        <div class="quick-grid" id="categoryGrid"></div>
      </div>
    </section>

    <section id="recipes">
      <div class="container">
        <div class="section-head">
          <div>
            <div class="eyebrow" style="background:#fff;color:var(--green);border-color:var(--line)">Popular at home</div>
            <h2 style="margin-top:12px">Filipino favorites</h2>
          </div>
          <a class="small-link" href="#recipes">View all →</a>
        </div>

        <div class="filterbar" id="filterBar">
          <button class="filter active" data-filter="All">All</button>
          <button class="filter" data-filter="Easy">Easy</button>
          <button class="filter" data-filter="Chicken">Chicken</button>
          <button class="filter" data-filter="Pork">Pork</button>
          <button class="filter" data-filter="Seafood">Seafood</button>
          <button class="filter" data-filter="Soup">Soup</button>
          <button class="filter" data-filter="Rice">Rice</button>
          <button class="filter" data-filter="Beef">Beef</button>
          <button class="filter" data-filter="Vegetable">Vegetables</button>
          <button class="filter" data-filter="Noodles">Noodles</button>
          <button class="filter" data-filter="Dessert">Dessert</button>
        </div>
        <div class="utility-bar">
          <button class="utility-btn" id="randomBtn">🎲 Surprise Me</button>
          <button class="utility-btn" id="favoritesBtn">♥ My Favorites</button>
          <button class="utility-btn" id="clearSearchBtn">↺ Reset Filters</button>
          <button class="utility-btn" id="shoppingBtn">🛒 Shopping List</button>
          <select class="sort-select" id="sortSelect" aria-label="Sort recipes">
            <option value="featured">Sort: Featured</option>
            <option value="quick">Sort: Quickest first</option>
            <option value="easy">Sort: Easiest first</option>
          </select>
        </div>

        <div class="recipe-grid" id="recipeGrid"></div>
      </div>
    </section>

    <section>
      <div class="container story">
        <div class="story-copy">
          <span class="eyebrow">More than a recipe</span>
          <h2>Food carries a piece of home.</h2>
          <p>Learn the story, place, and little traditions behind the dishes we grew up loving. KAIN TAYO brings Filipino food closer to curious cooks—whether you’re in Manila or thousands of kilometers away.</p>
          <a href="#regions" class="btn btn-primary" style="margin-top:16px">Explore Food Stories →</a>
        </div>
        <div class="story-image"></div>
      </div>
    </section>

    <section id="regions">
      <div class="container">
        <div class="section-head">
          <div>
            <div class="eyebrow" style="background:#fff;color:var(--green);border-color:var(--line)">A taste of the islands</div>
            <h2 style="margin-top:12px">Explore by region</h2>
          </div>
          <p>Every region has its own flavors, ingredients, and stories worth tasting.</p>
        </div>
        <div class="regions">
          <div class="region" style="background-image:url('https://images.unsplash.com/photo-1585032226651-759b368d7246?auto=format&fit=crop&w=1100&q=85')">
            <div class="region-content"><h3>Luzon</h3><p>Hearty stews, sour soups, rich sauces &amp; more.</p></div>
          </div>
          <div class="region" style="background-image:url('https://images.unsplash.com/photo-1516685018646-549198525c1b?auto=format&fit=crop&w=1100&q=85')">
            <div class="region-content"><h3>Visayas</h3><p>Grilled favorites, noodles, seafood &amp; bold flavors.</p></div>
          </div>
          <div class="region" style="background-image:url('https://images.unsplash.com/photo-1511690743698-d9d85f2fbf38?auto=format&fit=crop&w=1100&q=85')">
            <div class="region-content"><h3>Mindanao</h3><p>Warm spices, coconut, beef dishes &amp; food traditions.</p></div>
          </div>
        </div>
      </div>
    </section>

    <section id="planner">
      <div class="container">
        <div class="planner">
          <div>
            <div class="eyebrow" style="background:rgba(255,255,255,.55);color:var(--green);border-color:var(--line)">Have ingredients already?</div>
            <h2 style="margin-top:13px">Let’s see what you can cook.</h2>
            <p>Type ingredients you have at home and get recipe ideas without starting a grocery trip from scratch.</p>
          </div>
          <div class="ingredient-box">
            <div class="ingredient-row">
              <input id="ingredientInput" placeholder="e.g. chicken, garlic, soy sauce" />
              <button class="btn btn-primary" id="suggestBtn">Find dishes</button>
            </div>
            <div class="suggestions" id="suggestions">
              <div class="suggestion"><div><strong>Chicken Adobo</strong><br><small>Chicken • garlic • soy sauce • vinegar</small></div><span>→</span></div>
              <div class="suggestion"><div><strong>Garlic Butter Shrimp</strong><br><small>Shrimp • garlic • butter</small></div><span>→</span></div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      <div class="footer-grid">
        <div>
          <div class="brand"><span class="brand-mark" style="background:#f0e8d8;color:var(--green)">🍴</span><span>KAIN TAYO</span></div>
          <p style="max-width:420px;margin-top:12px">A modern Filipino food discovery site made to celebrate recipes, regional flavors, and the stories that make food feel like home.</p>
        </div>
        <div>
          <h3>Explore</h3>
          <div class="footer-links">
            <a href="#recipes">Popular Recipes</a>
            <a href="#regions">Regions</a>
            <a href="#planner">What Can I Cook?</a>
          </div>
        </div>
        <div>
          <h3>About</h3>
          <div class="footer-links">
            <a href="#discover">Categories</a>
            <a href="#" id="footerFavorites">My Favorites</a>
            <a href="#">Contact</a>
          </div>
        </div>
      </div>
      <div class="copy">© 2026 KAIN TAYO. Designed with love for Filipino food.</div>
    </div>
  </footer>

  <!-- Recipe Modal -->
  <div class="modal" id="recipeModal" aria-hidden="true">
    <div class="modal-card">
      <button class="close" id="closeModal" aria-label="Close">✕</button>
      <div class="modal-hero">
        <img id="modalImg" src="" alt="">
        <div class="modal-info">
          <div class="chips" id="modalChips"></div>
          <h2 id="modalTitle"></h2>
          <p id="modalDescription" style="color:var(--muted)"></p>
          <div class="modal-meta" id="modalMeta"></div>
          <div class="modal-toolbar">
            <div class="serving-control"><button id="servMinus">−</button><span id="servingText">4 servings</span><button id="servPlus">+</button></div>
            <button class="mini-btn" id="addShopBtn">🛒 Add ingredients</button>
            <button class="mini-btn" id="shareBtn">↗ Share</button>
            <button class="mini-btn" id="printBtn">🖨 Print</button>
          </div>
          <button class="btn btn-primary" id="modalCookBtn">👨‍🍳 Start Cook Mode</button>
        </div>
      </div>
      <div class="modal-grid">
        <div>
          <h3>Ingredients</h3>
          <div class="ingredients" id="modalIngredients"></div>
        </div>
        <div>
          <h3>How to cook</h3>
          <div class="steps" id="modalSteps"></div>
        </div>
      </div>
    </div>
  </div>

  <div class="shopping-drawer" id="shoppingDrawer" aria-hidden="true">
    <div class="shopping-head"><strong>🛒 My Shopping List</strong><button class="close" id="closeShopping" style="position:static;width:34px;height:34px">✕</button></div>
    <div class="shopping-list" id="shoppingList"><div class="empty" style="padding:26px 12px;border:0">Your shopping list is empty.</div></div>
    <div class="drawer-actions"><button class="mini-btn" id="clearShopping">Clear</button><button class="mini-btn" id="copyShopping">Copy list</button></div>
  </div>
  <div class="toast" id="toast" role="status" aria-live="polite"></div>

  <!-- Cook Mode -->
  <div class="cook-overlay" id="cookOverlay">
    <div class="cook-top">
      <strong id="cookTitle">Cook Mode</strong>
      <button class="btn btn-secondary" id="closeCook">✕ Exit</button>
    </div>
    <div class="cook-main">
      <div class="step-counter" id="cookCounter"></div>
      <h2 id="cookStepTitle"></h2>
      <p id="cookStepText"></p>
      <div class="progress"><i id="cookProgress"></i></div>
      <div class="cook-controls">
        <button class="btn btn-secondary" id="prevStep">← Previous</button>
        <button class="btn btn-primary" id="nextStep">Next Step →</button>
      </div>
    </div>
  </div>

  <script>
    const recipes = [
      {
        id:'adobo', title:'Chicken Adobo', category:'Chicken', tags:['Easy','Chicken','Dinner'], region:'Luzon',
        difficulty:'Easy', time:'55 mins', servings:'4 servings', description:'Tender chicken simmered in a savory, tangy sauce with garlic and peppercorn.',
        image:'https://images.unsplash.com/photo-1604908177522-4023ab1b7a9d?auto=format&fit=crop&w=1200&q=85',
        ingredients:['1 kg chicken pieces','½ cup soy sauce','½ cup vinegar','8 cloves garlic, crushed','3 bay leaves','1 tsp whole peppercorns','1 cup water','1 tbsp cooking oil'],
        steps:[['Prep the chicken','Pat the chicken dry and gather the aromatics and sauces.'],['Brown for flavor','Heat oil and lightly brown the chicken pieces.'],['Build the sauce','Add garlic, soy sauce, vinegar, bay leaves, peppercorns, and water. Bring to a boil.'],['Simmer','Lower the heat and cook until the chicken is tender, about 35–40 minutes.'],['Reduce & serve','Let the sauce become glossy. Serve hot with rice.']]
      },
      {
        id:'sinigang', title:'Sinigang na Baboy', category:'Soup', tags:['Pork','Soup','Dinner'], region:'Luzon',
        difficulty:'Medium', time:'1 hr 15 mins', servings:'5 servings', description:'A comforting sour tamarind soup packed with pork, vegetables, and deep savory flavor.',
        image:'https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1200&q=85',
        ingredients:['750 g pork belly or ribs','1.5 L water','2 tomatoes, quartered','1 onion, sliced','1 cup string beans','1 radish, sliced','1 eggplant, sliced','1–2 cups tamarind broth','2 cups kangkong','Fish sauce to taste'],
        steps:[['Start the broth','Simmer pork with water, onion, and tomatoes; skim foam.'],['Tenderize','Cover and simmer until the pork is tender.'],['Add vegetables','Add radish and eggplant, then string beans.'],['Make it sour','Add tamarind broth gradually and adjust the sourness.'],['Finish','Add kangkong and fish sauce, then serve.']]
      },
      {
        id:'karekare', title:'Kare-Kare', category:'Pork', tags:['Pork','Special Occasion'], region:'Luzon',
        difficulty:'Hard', time:'2 hrs', servings:'6 servings', description:'Rich peanut stew made special with tender meat, vegetables, and bagoong on the side.',
        image:'https://images.unsplash.com/photo-1601050690117-94f5f6fa8bd7?auto=format&fit=crop&w=1200&q=85',
        ingredients:['1 kg oxtail or beef chunks','½ cup peanut butter','¼ cup ground toasted peanuts','1 onion, chopped','4 cloves garlic','2 tbsp annatto oil','2 tbsp rice flour','4 cups beef broth','Eggplant, pechay, and string beans','Bagoong alamang, for serving'],
        steps:[['Tenderize the meat','Simmer oxtail or beef until tender and reserve the broth.'],['Build the base','Sauté garlic and onion in annatto oil.'],['Thicken','Add peanut butter, peanuts, rice flour, and broth.'],['Combine','Return the meat and simmer until rich and thick.'],['Add vegetables','Blanch vegetables separately and serve with bagoong.']]
      },
      {
        id:'inasal', title:'Chicken Inasal', category:'Chicken', tags:['Chicken','Easy','Grilled'], region:'Visayas',
        difficulty:'Easy', time:'50 mins', servings:'4 servings', description:'Char-grilled chicken marinated in calamansi, vinegar, garlic, and annatto oil.',
        image:'https://images.unsplash.com/photo-1527477396000-e27163b481c2?auto=format&fit=crop&w=1200&q=85',
        ingredients:['1 kg chicken thighs or drumsticks','½ cup vinegar','½ cup calamansi juice','6 cloves garlic, minced','1 tbsp ginger, grated','1 tsp salt','1 tsp black pepper','Annatto oil for basting'],
        steps:[['Marinate','Combine marinade ingredients and marinate chicken for at least 2 hours.'],['Heat the grill','Prepare a medium-hot grill and oil the grates lightly.'],['Grill','Cook slowly, turning often for even browning.'],['Baste','Brush with annatto oil while grilling.'],['Rest & serve','Rest briefly, then serve with rice and dipping sauce.']]
      },
      {
        id:'sinigang-hipon', title:'Sinigang na Hipon', category:'Seafood', tags:['Seafood','Soup','Easy'], region:'Visayas',
        difficulty:'Easy', time:'35 mins', servings:'4 servings', description:'Bright, sour tamarind soup with juicy shrimp and crisp vegetables.',
        image:'https://images.unsplash.com/photo-1562565652-a0d8f0c59eb4?auto=format&fit=crop&w=1200&q=85',
        ingredients:['500 g large shrimp','1.2 L water','2 tomatoes, quartered','1 onion, sliced','1 cup radish','1 cup okra','1 cup string beans','1–2 cups tamarind broth','2 cups kangkong','Fish sauce to taste'],
        steps:[['Make the broth','Boil water with onion and tomatoes.'],['Add sturdy vegetables','Add radish and okra until nearly tender.'],['Add shrimp','Cook shrimp just until pink and opaque, 3–5 minutes.'],['Add sourness','Stir in tamarind broth and adjust to taste.'],['Finish','Add kangkong and season with fish sauce.']]
      },
      {
        id:'leche-flan', title:'Leche Flan', category:'Dessert', tags:['Dessert','Easy','Celebration'], region:'Nationwide',
        difficulty:'Easy', time:'1 hr 10 mins', servings:'8 servings', description:'Silky steamed custard with a deep caramel topping—a Filipino celebration classic.',
        image:'https://images.unsplash.com/photo-1551024506-0bccd828d307?auto=format&fit=crop&w=1200&q=85',
        ingredients:['10 egg yolks','1 can condensed milk','1 can evaporated milk','1 tsp vanilla','¾ cup sugar for caramel','2 tbsp water'],
        steps:[['Make caramel','Melt sugar and water until amber and pour into a mold.'],['Mix gently','Combine yolks, milks, and vanilla without whipping in air.'],['Strain','Pass the custard through a fine sieve.'],['Steam','Cover and steam about 35–45 minutes.'],['Chill & unmold','Cool, refrigerate, then invert onto a plate.']]
      },
      {
        id:'pancit-canton', title:'Pancit Canton', category:'Noodles', tags:['Noodles','Easy','Quick'], region:'Luzon',
        difficulty:'Easy', time:'35 mins', servings:'4 servings', description:'Stir-fried egg noodles tossed with vegetables, chicken, and savory sauce.',
        image:'https://images.unsplash.com/photo-1557872943-16a5ac26437e?auto=format&fit=crop&w=1200&q=85',
        ingredients:['400 g pancit canton noodles','250 g chicken breast, sliced','1 carrot, julienned','1 cup cabbage, sliced','½ cup green beans','4 cloves garlic','1 onion','¼ cup soy sauce','1 cup chicken stock','2 tbsp cooking oil'],
        steps:[['Cook aromatics','Sauté garlic and onion in oil.'],['Cook chicken','Add chicken and stir-fry until cooked through.'],['Add vegetables','Toss in carrot, beans, and cabbage.'],['Sauce it','Add soy sauce and stock and bring to a simmer.'],['Toss noodles','Add noodles and stir-fry until the sauce is absorbed.']]
      },
      {
        id:'sisig', title:'Sizzling Pork Sisig', category:'Pork', tags:['Pork','Grilled','Pulutan'], region:'Luzon',
        difficulty:'Medium', time:'1 hr 20 mins', servings:'4 servings', description:'Crispy chopped pork with calamansi, onion, chili, and a sizzling finish.',
        image:'https://images.unsplash.com/photo-1603133872878-684f208fb84b?auto=format&fit=crop&w=1200&q=85',
        ingredients:['700 g pork belly or cheeks','1 onion, finely chopped','3 cloves garlic','2–3 chilies, sliced','2 tbsp soy sauce','2 tbsp calamansi juice','1 tbsp mayonnaise, optional','Salt and pepper'],
        steps:[['Boil the pork','Simmer pork until tender, then drain and dry well.'],['Char it','Grill or pan-sear until the outside is deeply browned.'],['Chop','Finely chop the pork and set aside.'],['Season','Toss with onion, garlic, chili, soy sauce, and calamansi.'],['Sizzle','Cook briefly on a hot pan or sizzling plate and serve.']]
      },
      {
        id:'tinola', title:'Chicken Tinola', category:'Soup', tags:['Chicken','Soup','Healthy'], region:'Luzon',
        difficulty:'Easy', time:'50 mins', servings:'4 servings', description:'Light ginger broth with tender chicken, green papaya, and leafy greens.',
        image:'https://images.unsplash.com/photo-1547592166-23ac45744acd?auto=format&fit=crop&w=1200&q=85',
        ingredients:['1 kg chicken pieces','1 thumb ginger, sliced','1 onion, sliced','4 cloves garlic','1 green papaya, sliced','2 cups chili leaves or malunggay','6 cups water','2 tbsp fish sauce','1 tbsp cooking oil'],
        steps:[['Sauté aromatics','Cook garlic, onion, and ginger until fragrant.'],['Brown chicken','Add chicken and cook until lightly browned.'],['Add broth','Pour in water and simmer until chicken is tender.'],['Add papaya','Cook green papaya until just tender.'],['Finish','Add leafy greens and fish sauce; cook 1–2 minutes.']]
      },
      {
        id:'menudo', title:'Pork Menudo', category:'Pork', tags:['Pork','Dinner','Meal Prep'], region:'Luzon',
        difficulty:'Medium', time:'1 hr 10 mins', servings:'6 servings', description:'Tomato-rich pork stew with potatoes, carrots, liver, and bright bell peppers.',
        image:'https://images.unsplash.com/photo-1601050690117-94f5f6fa8bd7?auto=format&fit=crop&w=1200&q=85',
        ingredients:['700 g pork shoulder, cubed','200 g pork liver, cubed','2 potatoes, cubed','2 carrots, cubed','1 bell pepper','1 onion','5 cloves garlic','1 cup tomato sauce','1 cup water','2 tbsp soy sauce'],
        steps:[['Brown pork','Sear pork cubes until lightly browned.'],['Sauté aromatics','Add garlic and onion and cook until soft.'],['Simmer','Add tomato sauce, water, and soy sauce; simmer until tender.'],['Add vegetables','Add potatoes and carrots until cooked.'],['Finish','Add liver and bell pepper and cook briefly.']]
      },
      {
        id:'caldereta', title:'Beef Caldereta', category:'Beef', tags:['Beef','Special Occasion','Dinner'], region:'Luzon',
        difficulty:'Medium', time:'1 hr 45 mins', servings:'6 servings', description:'Slow-simmered beef in a rich tomato sauce with vegetables and a creamy, savory finish.',
        image:'https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=1200&q=85',
        ingredients:['1 kg beef chuck, cubed','1 onion','5 cloves garlic','1½ cups tomato sauce','2 cups beef stock','2 potatoes','2 carrots','1 bell pepper','2 tbsp peanut butter','2 tbsp cooking oil'],
        steps:[['Brown beef','Sear beef in batches until browned.'],['Sauté base','Cook garlic and onion until fragrant.'],['Simmer','Add tomato sauce and stock; cover and simmer until tender.'],['Add vegetables','Add potatoes and carrots and cook until tender.'],['Enrich','Stir in peanut butter and bell pepper and simmer briefly.']]
      },
      {
        id:'bangus-relyeno', title:'Relyenong Bangus', category:'Seafood', tags:['Seafood','Celebration'], region:'Visayas',
        difficulty:'Hard', time:'2 hrs', servings:'6 servings', description:'Stuffed milkfish with savory sautéed filling, prepared for special family occasions.',
        image:'https://images.unsplash.com/photo-1516685018646-549198525c1b?auto=format&fit=crop&w=1200&q=85',
        ingredients:['1 large bangus, cleaned','1 onion, chopped','4 cloves garlic','1 carrot, minced','1 bell pepper, minced','2 eggs, beaten','½ cup breadcrumbs','2 tbsp soy sauce','Cooking oil'],
        steps:[['Prepare fish','Carefully remove the fish meat and keep the skin intact.'],['Cook filling','Sauté garlic, onion, carrot, and pepper, then mix with flaked fish.'],['Bind','Add eggs, breadcrumbs, and soy sauce.'],['Stuff','Fill the fish skin evenly and secure the opening.'],['Cook','Bake or fry until golden and cooked through, then slice.']]
      },
      {
        id:'laing', title:'Laing', category:'Vegetable', tags:['Vegetable','Spicy','Budget'], region:'Bicol',
        difficulty:'Easy', time:'45 mins', servings:'5 servings', description:'Slow-cooked taro leaves in coconut milk with shrimp paste and chili.',
        image:'https://images.unsplash.com/photo-1601050690597-df0568f70950?auto=format&fit=crop&w=1200&q=85',
        ingredients:['2 cups dried taro leaves','2 cups coconut milk','1 cup coconut cream','4 cloves garlic','1 onion','1 thumb ginger','2 tbsp bagoong alamang','4–6 chilies'],
        steps:[['Start aromatics','Combine garlic, onion, ginger, and bagoong.'],['Add coconut milk','Pour in coconut milk and bring to a gentle simmer.'],['Add leaves','Add taro leaves and let them soften without vigorous stirring.'],['Add heat','Add chilies and simmer until tender.'],['Finish','Pour in coconut cream and cook until thick and rich.']]
      },
      {
        id:'pinakbet', title:'Pinakbet', category:'Vegetable', tags:['Vegetable','Healthy','Budget'], region:'Ilocos',
        difficulty:'Easy', time:'40 mins', servings:'4 servings', description:'Colorful vegetables cooked with bagoong for a simple, deeply savory Filipino classic.',
        image:'https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1200&q=85',
        ingredients:['1 cup squash, cubed','1 cup eggplant','1 cup bitter melon','1 cup okra','1 cup string beans','1 tomato','1 onion','4 cloves garlic','2 tbsp bagoong','½ cup water'],
        steps:[['Sauté base','Cook garlic, onion, and tomato until soft.'],['Add savory flavor','Stir in bagoong and water.'],['Layer vegetables','Add squash first, then eggplant and the firmer vegetables.'],['Cover','Steam-cook until vegetables are tender but not mushy.'],['Serve','Taste and adjust seasoning before serving with rice.']]
      },
      {
        id:'batchoy', title:'La Paz Batchoy', category:'Noodles', tags:['Noodles','Soup','Comfort Food'], region:'Visayas',
        difficulty:'Medium', time:'1 hr 30 mins', servings:'4 servings', description:'Iloilo-style noodle soup with pork, liver, egg noodles, and aromatic broth.',
        image:'https://images.unsplash.com/photo-1562565652-a0d8f0c59eb4?auto=format&fit=crop&w=1200&q=85',
        ingredients:['300 g pork shoulder','150 g pork liver','300 g fresh egg noodles','1.5 L pork stock','1 onion','5 cloves garlic','1 tsp shrimp paste','Spring onions','Crushed pork cracklings'],
        steps:[['Build stock','Simmer pork with stock, onion, and garlic until tender.'],['Cook liver','Add sliced liver and cook gently.'],['Season','Stir in a little shrimp paste to deepen the broth.'],['Add noodles','Cook egg noodles separately or directly in the broth.'],['Garnish','Top with pork, spring onions, and crushed cracklings.']]
      },
      {
        id:'chicken-barbecue', title:'Pinoy Chicken Barbecue', category:'Chicken', tags:['Chicken','Grilled','Easy'], region:'Nationwide',
        difficulty:'Easy', time:'1 hr', servings:'4 servings', description:'Sweet-savory skewers with soy sauce, citrus, garlic, and a caramelized glaze.',
        image:'https://images.unsplash.com/photo-1527477396000-e27163b481c2?auto=format&fit=crop&w=1200&q=85',
        ingredients:['1 kg boneless chicken thighs','½ cup soy sauce','¼ cup banana ketchup','¼ cup calamansi juice','4 cloves garlic','2 tbsp brown sugar','1 tbsp oil','Bamboo skewers'],
        steps:[['Marinate','Mix all marinade ingredients and coat the chicken.'],['Skewer','Thread chicken pieces onto soaked skewers.'],['Grill','Cook over medium heat, turning often.'],['Baste','Brush with reserved marinade while cooking, making sure raw marinade is cooked through.'],['Finish','Grill until charred at the edges and serve hot.']]
      },
      {
        id:'halo-halo', title:'Halo-Halo', category:'Dessert', tags:['Dessert','Cold','Easy'], region:'Nationwide',
        difficulty:'Easy', time:'15 mins', servings:'2 servings', description:'A colorful icy dessert layered with sweet fruits, beans, jellies, milk, and ube.',
        image:'https://images.unsplash.com/photo-1551024506-0bccd828d307?auto=format&fit=crop&w=1200&q=85',
        ingredients:['1 cup shaved ice','½ cup sweetened beans','½ cup nata de coco','½ cup sweet fruit or kaong','2 tbsp ube halaya','Evaporated milk','Leche flan, optional','1 scoop ube or vanilla ice cream, optional'],
        steps:[['Layer', 'Add fruits, beans, and jellies to a tall glass.'],['Add ice','Pile shaved ice generously on top.'],['Pour milk','Drizzle evaporated milk over the ice.'],['Top','Add ube, flan, and ice cream if desired.'],['Mix & enjoy','Stir from the bottom up before eating.']]
      },
      {
        id:'arroz-caldo', title:'Arroz Caldo', category:'Rice', tags:['Rice','Soup','Comfort Food'], region:'Luzon',
        difficulty:'Easy', time:'1 hr', servings:'4 servings', description:'Ginger-scented chicken rice porridge topped with toasted garlic, egg, and calamansi.',
        image:'https://images.unsplash.com/photo-1516685018646-549198525c1b?auto=format&fit=crop&w=1200&q=85',
        ingredients:['1 cup glutinous rice or regular rice','500 g chicken pieces','1 onion','1 thumb ginger','5 cloves garlic','6 cups chicken stock','2 tbsp fish sauce','4 eggs','Calamansi and spring onions'],
        steps:[['Sauté aromatics','Cook garlic, onion, and ginger until fragrant.'],['Brown chicken','Add chicken and cook until lightly browned.'],['Add rice & stock','Stir in rice and chicken stock.'],['Simmer','Cook until the rice breaks down into a thick porridge.'],['Finish','Season with fish sauce and top with egg, calamansi, and spring onions.']]
      },
      {
        id:'turon', title:'Turon', category:'Dessert', tags:['Dessert','Snack','Budget'], region:'Nationwide',
        difficulty:'Easy', time:'30 mins', servings:'6 rolls', description:'Crispy caramelized banana spring rolls, perfect for merienda.',
        image:'https://images.unsplash.com/photo-1551024506-0bccd828d307?auto=format&fit=crop&w=1200&q=85',
        ingredients:['6 saba bananas, halved','½ cup brown sugar','½ cup sliced jackfruit, optional','6 spring roll wrappers','Oil for frying'],
        steps:[['Fill','Place banana and jackfruit on a wrapper and sprinkle with brown sugar.'],['Roll','Fold tightly and seal the edge with water.'],['Heat oil','Warm enough oil for shallow or deep frying.'],['Fry','Fry until crisp and golden.'],['Caramelize','Let excess oil drain while the sugar coating sets.']]
      },
      {
        id:'ginataang-gulay', title:'Ginataang Gulay', category:'Vegetable', tags:['Vegetable','Budget','Easy'], region:'Nationwide',
        difficulty:'Easy', time:'35 mins', servings:'4 servings', description:'Creamy coconut vegetables with squash, beans, and chili for everyday ulam.',
        image:'https://images.unsplash.com/photo-1604908176997-125f25cc6f3d?auto=format&fit=crop&w=1200&q=85',
        ingredients:['2 cups squash, cubed','1 cup string beans','1 cup eggplant','2 cups coconut milk','3 cloves garlic','1 onion','2 chilies','1 tbsp bagoong or salt'],
        steps:[['Sauté','Cook garlic and onion until fragrant.'],['Add vegetables','Add squash, eggplant, and beans and toss briefly.'],['Pour coconut milk','Add coconut milk and bring to a simmer.'],['Season','Add chili and bagoong or salt.'],['Reduce','Simmer until vegetables are tender and the sauce is creamy.']]
      }
    ];

    const categories = [
      ['🍚','Rice & Meals','Rice'],['🍲','Soups','Soup'],['🍗','Chicken','Chicken'],
      ['🥩','Beef & Pork','Beef'],['🐟','Seafood','Seafood'],['🥬','Vegetables','Vegetable'],
      ['🍜','Noodles','Noodles'],['🍰','Desserts','Dessert']
    ];

    const categoryGrid = document.getElementById('categoryGrid');
    categoryGrid.innerHTML = categories.map(([icon,name,filter]) =>
      `<button class="quick-card" data-category="${filter}">
        <span class="quick-icon">${icon}</span><strong>${name}</strong>
      </button>`
    ).join('');

    const recipeGrid = document.getElementById('recipeGrid');
    const modal = document.getElementById('recipeModal');
    const cookOverlay = document.getElementById('cookOverlay');

    // ---------- Safe localStorage helpers ----------
    // Private browsing / disabled storage / quota errors should never crash the app.
    function safeGetJSON(key, fallback){
      try{
        const v = localStorage.getItem(key);
        return v === null ? fallback : JSON.parse(v);
      }catch{ return fallback; }
    }
    function safeGet(key, fallback){
      try{
        const v = localStorage.getItem(key);
        return v === null ? fallback : v;
      }catch{ return fallback; }
    }
    function safeSet(key, value){
      try{ localStorage.setItem(key, value); }catch{ /* storage unavailable — continue without persistence */ }
    }

    let favorites = safeGetJSON('kainTayoFavorites', []);
    let shoppingItems = safeGetJSON('kainTayoShopping', []);
    let recent = safeGetJSON('kainTayoRecent', []);
    let servingCount = 4;
    let currentRecipe = null;
    let lastFocusedElement = null;
    let cookIndex = 0;

    // ---------- Single source of truth for what the recipe grid shows ----------
    // Category filter, search text, and the favorites-only view all combine
    // (AND together) instead of silently overwriting one another.
    const state = { filter:'All', query:'', favoritesOnly:false, sort:'featured' };

    function computeVisibleRecipes(){
      let list = recipes;
      if(state.favoritesOnly) list = list.filter(r=>favorites.includes(r.id));
      if(state.filter !== 'All') list = list.filter(r=>r.tags.includes(state.filter) || r.category===state.filter);
      if(state.query){
        const q = state.query;
        list = list.filter(r=>[r.title,r.category,r.region,r.description,...r.tags,...r.ingredients].join(' ').toLowerCase().includes(q));
      }
      return applySort(list);
    }

    function parseMinutes(t){
      const h = /(\d+)\s*hr/.exec(t);
      const m = /(\d+)\s*min/.exec(t);
      return (h?parseInt(h[1],10)*60:0) + (m?parseInt(m[1],10):0);
    }
    function applySort(list){
      const arr = [...list];
      if(state.sort === 'quick') arr.sort((a,b)=>parseMinutes(a.time)-parseMinutes(b.time));
      else if(state.sort === 'easy'){
        const rank = {Easy:0, Medium:1, Hard:2};
        arr.sort((a,b)=>(rank[a.difficulty]??1)-(rank[b.difficulty]??1));
      }
      return arr;
    }

    function difficultyDot(level){
      const color = level==='Easy' ? 'var(--diff-easy)' : level==='Hard' ? 'var(--diff-hard)' : 'var(--diff-medium)';
      return `<span class="diff-dot" style="background:${color}"></span>`;
    }

    function render(){
      renderRecipes(computeVisibleRecipes());
    }

    function syncFilterChipsUI(){
      document.querySelectorAll('.filter').forEach(btn=>{
        btn.classList.toggle('active', !state.favoritesOnly && btn.dataset.filter===state.filter);
      });
    }

    function updateFavoritesBadge(){
      const b = document.getElementById('favBadge');
      if(!b) return;
      if(favorites.length){ b.hidden=false; b.textContent = favorites.length>9 ? '9+' : String(favorites.length); }
      else b.hidden = true;
    }

    function resetAllFilters(){
      document.getElementById('searchInput').value = '';
      document.getElementById('sortSelect').value = 'featured';
      state.query = '';
      state.filter = 'All';
      state.favoritesOnly = false;
      state.sort = 'featured';
      syncFilterChipsUI();
      render();
    }

    function renderRecipes(list){
      if(!list.length){
        recipeGrid.innerHTML = `
          <div class="empty">
            <strong>No recipes found.</strong><br>Try another search or category.<br>
            <button class="utility-btn" id="emptyResetBtn" type="button" style="margin-top:14px">↺ Reset Filters</button>
          </div>`;
        document.getElementById('emptyResetBtn')?.addEventListener('click', resetAllFilters);
        return;
      }
      recipeGrid.innerHTML = list.map(r => `
        <article class="recipe-card">
          <div class="recipe-img-wrap">
            <img class="recipe-img" src="${r.image}" alt="${r.title}" loading="lazy">
            <button class="save ${favorites.includes(r.id) ? 'saved':''}" data-save="${r.id}" aria-label="Save ${r.title}">${favorites.includes(r.id) ? '♥':'♡'}</button>
          </div>
          <div class="recipe-body">
            <div class="chips">${r.tags.map(t=>`<span class="chip">${t}</span>`).join('')}<span class="chip">${r.region}</span></div>
            <h3>${r.title}</h3>
            <p>${r.description}</p>
            <div class="meta">
              <span>⏱ ${r.time}</span><span>👥 ${r.servings}</span><span>${difficultyDot(r.difficulty)}${r.difficulty}</span>
            </div>
            <div class="recipe-extra"><span class="rating">★★★★★ ${r.difficulty==='Easy'?'4.9':'4.8'}</span><span style="font-size:.75rem;color:var(--muted)">🇵🇭 ${r.region}</span></div>
            <button class="view-recipe" data-view="${r.id}">View Recipe →</button>
          </div>
        </article>
      `).join('');
    }

    function setFilter(filter){
      state.filter = filter;
      state.favoritesOnly = false;
      syncFilterChipsUI();
      render();
    }

    document.getElementById('filterBar').addEventListener('click', e => {
      const btn = e.target.closest('.filter');
      if(btn) setFilter(btn.dataset.filter);
    });

    categoryGrid.addEventListener('click', e => {
      const card = e.target.closest('.quick-card');
      if(!card) return;
      setFilter(card.dataset.category);
      document.getElementById('recipes').scrollIntoView({behavior:'smooth'});
    });

    document.getElementById('sortSelect').addEventListener('change', e=>{
      state.sort = e.target.value;
      render();
    });

    function saveFavorite(id){
      favorites = favorites.includes(id) ? favorites.filter(x=>x!==id) : [...favorites,id];
      safeSet('kainTayoFavorites', JSON.stringify(favorites));
      updateFavoritesBadge();
      render();
      toast(favorites.includes(id) ? 'Saved to My Favorites ♥' : 'Removed from favorites');
    }
    recipeGrid.addEventListener('click', e => {
      const save = e.target.closest('[data-save]');
      if(save){ saveFavorite(save.dataset.save); return; }
      const view = e.target.closest('[data-view]');
      if(view) openRecipe(view.dataset.view);
    });

    function openRecipe(id){
      const r = recipes.find(x=>x.id===id);
      if(!r) return;
      lastFocusedElement = document.activeElement;
      currentRecipe = r;
      servingCount = parseInt((r.servings||'4').match(/\d+/)?.[0] || 4, 10);

      document.getElementById('modalImg').src = r.image;
      document.getElementById('modalImg').alt = r.title;
      document.getElementById('modalTitle').textContent = r.title;
      document.getElementById('modalDescription').textContent = r.description;
      document.getElementById('modalChips').innerHTML = r.tags.map(t=>`<span class="chip">${t}</span>`).join('') + `<span class="chip">${r.region}</span>`;
      document.getElementById('modalMeta').innerHTML = `
        <span>⏱ ${r.time}</span><span>👥 ${r.servings}</span><span>${difficultyDot(r.difficulty)}${r.difficulty}</span>
      `;
      setServingDisplay();
      document.getElementById('modalSteps').innerHTML = r.steps.map((s,i)=>`
        <div class="step"><div class="step-num">${String(i+1).padStart(2,'0')}</div><div><strong>${s[0]}</strong><div style="margin-top:3px;color:var(--muted);font-size:.9rem">${s[1]}</div></div></div>
      `).join('');

      modal.classList.add('open');
      modal.setAttribute('aria-hidden','false');
      document.body.style.overflow='hidden';
      document.getElementById('closeModal').focus();

      recent = [id, ...recent.filter(x=>x!==id)].slice(0,6);
      safeSet('kainTayoRecent', JSON.stringify(recent));
      renderRecent();
    }

    function closeRecipe(restoreFocus=true){
      modal.classList.remove('open');
      modal.setAttribute('aria-hidden','true');
      document.body.style.overflow='';
      if(restoreFocus && lastFocusedElement) lastFocusedElement.focus();
    }

    document.getElementById('closeModal').onclick = () => closeRecipe();
    modal.addEventListener('click', e => { if(e.target===modal) closeRecipe(); });

    // Search — combines with whatever category filter / favorites view is active
    let searchHasScrolled = false;
    function runSearch(q){
      state.query = q;
      render();
    }
    document.getElementById('searchForm').addEventListener('submit', e => {
      e.preventDefault();
      runSearch(document.getElementById('searchInput').value.trim().toLowerCase());
      document.getElementById('recipes').scrollIntoView({behavior:'smooth'});
    });
    document.getElementById('searchInput').addEventListener('input', e=>{
      const q = e.target.value.trim().toLowerCase();
      runSearch(q);
      if(q && !searchHasScrolled){
        document.getElementById('recipes').scrollIntoView({behavior:'smooth'});
        searchHasScrolled = true;
      } else if(!q){
        searchHasScrolled = false;
      }
    });

    // Favorites view
    function showFavorites(){
      state.favoritesOnly = true;
      syncFilterChipsUI();
      render();
      document.getElementById('recipes').scrollIntoView({behavior:'smooth'});
    }
    document.getElementById('favoriteNav').onclick = showFavorites;
    document.getElementById('favoritesBtn').onclick = showFavorites;
    document.getElementById('footerFavorites').onclick = e => { e.preventDefault(); showFavorites(); };
    document.getElementById('clearSearchBtn').onclick = resetAllFilters;

    // "What can I cook?" ingredient finder
    function tokenizeIngredients(q){
      let parts = q.split(/,|\band\b/i).map(s=>s.trim()).filter(Boolean);
      if(parts.length <= 1){
        // No commas or "and" used — fall back to splitting on whitespace so
        // plain phrasing like "chicken garlic soy sauce" still finds matches.
        parts = q.split(/\s+/).map(s=>s.trim()).filter(Boolean);
      }
      return parts;
    }
    function showSuggestions(){
      const raw = document.getElementById('ingredientInput').value.trim().toLowerCase();
      const terms = tokenizeIngredients(raw);
      const scored = recipes.map(r=>{
        const hay = (r.title+' '+r.description+' '+r.ingredients.join(' ')+' '+r.tags.join(' ')).toLowerCase();
        const score = terms.length ? terms.reduce((n,t)=>n+(hay.includes(t)?1:0),0) : 0;
        return {r,score};
      }).filter(x=>x.score>0).sort((a,b)=>b.score-a.score);

      const list = scored.length ? scored.slice(0,4).map(({r})=>`
        <button class="suggestion" data-suggest="${r.id}" type="button">
          <div style="text-align:left"><strong>${r.title}</strong><br><small>${r.ingredients.slice(0,3).join(' • ')}</small></div><span>→</span>
        </button>
      `).join('') : `<div class="suggestion"><div><strong>No exact match yet.</strong><br><small>Try chicken, pork, shrimp, garlic, or soy sauce.</small></div></div>`;
      document.getElementById('suggestions').innerHTML = list;
    }
    document.getElementById('suggestBtn').onclick = showSuggestions;
    document.getElementById('ingredientInput').addEventListener('keydown', e=>{
      if(e.key === 'Enter'){ e.preventDefault(); showSuggestions(); }
    });
    document.getElementById('suggestions').addEventListener('click', e=>{
      const b=e.target.closest('[data-suggest]');
      if(b) openRecipe(b.dataset.suggest);
    });

    // Cook Mode
    function startCook(r){
      currentRecipe = r;
      cookIndex = 0;
      closeRecipe(false);
      updateCook();
      cookOverlay.classList.add('open');
      document.body.style.overflow='hidden';
      document.getElementById('closeCook').focus();
    }
    function updateCook(){
      const total = currentRecipe.steps.length;
      const [title,text] = currentRecipe.steps[cookIndex];
      document.getElementById('cookTitle').textContent = `KAIN TAYO • ${currentRecipe.title}`;
      document.getElementById('cookCounter').textContent = `Step ${cookIndex+1} of ${total}`;
      document.getElementById('cookStepTitle').textContent = title;
      document.getElementById('cookStepText').textContent = text;
      document.getElementById('cookProgress').style.width = `${((cookIndex+1)/total)*100}%`;
      document.getElementById('prevStep').disabled = cookIndex===0;
      document.getElementById('nextStep').textContent = cookIndex===total-1 ? 'Finish ✓' : 'Next Step →';
    }
    function exitCook(){
      cookOverlay.classList.remove('open');
      document.body.style.overflow='';
      if(lastFocusedElement) lastFocusedElement.focus();
    }
    document.getElementById('modalCookBtn').onclick = () => currentRecipe && startCook(currentRecipe);
    document.getElementById('heroCookBtn').onclick = () => startCook(recipes[0]);
    document.getElementById('nextStep').onclick = () => {
      if(cookIndex < currentRecipe.steps.length-1){ cookIndex++; updateCook(); }
      else { exitCook(); }
    };
    document.getElementById('prevStep').onclick = () => { if(cookIndex>0){cookIndex--;updateCook();} };
    document.getElementById('closeCook').onclick = exitCook;

    // Keyboard shortcuts
    document.addEventListener('keydown', e => {
      if(e.key==='Escape'){
        if(cookOverlay.classList.contains('open')) exitCook();
        if(modal.classList.contains('open')) closeRecipe();
        const drawer = document.getElementById('shoppingDrawer');
        if(drawer.classList.contains('open')){ drawer.classList.remove('open'); drawer.setAttribute('aria-hidden','true'); }
      }
      if(cookOverlay.classList.contains('open')){
        if(e.key==='ArrowRight') document.getElementById('nextStep').click();
        if(e.key==='ArrowLeft') document.getElementById('prevStep').click();
      }
    });

    function toast(message){
      const t=document.getElementById('toast'); t.textContent=message; t.classList.add('show');
      clearTimeout(window.__toast); window.__toast=setTimeout(()=>t.classList.remove('show'),1900);
    }

    function showRandomRecipe(){
      const pool = computeVisibleRecipes();
      const r = pool[Math.floor(Math.random()*pool.length)] || recipes[Math.floor(Math.random()*recipes.length)];
      openRecipe(r.id);
    }

    function openShopping(){
      renderShopping();
      const d=document.getElementById('shoppingDrawer');
      d.classList.add('open'); d.setAttribute('aria-hidden','false');
    }
    function renderShopping(){
      const el=document.getElementById('shoppingList');
      if(!shoppingItems.length){
        el.innerHTML='<div class="empty" style="padding:26px 12px;border:0">Your shopping list is empty.<br>Add ingredients from any recipe.</div>';
        return;
      }
      el.innerHTML=shoppingItems.map((item,i)=>`<label class="shopping-item"><input type="checkbox" ${item.done?'checked':''} data-shop-check="${i}"><span>${item.text}</span></label>`).join('');
      el.querySelectorAll('[data-shop-check]').forEach(c=>c.addEventListener('change',e=>{
        shoppingItems[+e.target.dataset.shopCheck].done=e.target.checked;
        safeSet('kainTayoShopping',JSON.stringify(shoppingItems));
      }));
    }
    function addIngredients(r){
      r.ingredients.forEach(x=>{ if(!shoppingItems.some(i=>i.text===x)) shoppingItems.push({text:x,done:false}); });
      safeSet('kainTayoShopping',JSON.stringify(shoppingItems));
      renderShopping(); toast(`${r.ingredients.length} ingredients added to your list`);
    }

    // Recently viewed
    function renderRecent(){
      const wrap = document.getElementById('recentSection');
      const strip = document.getElementById('recentStrip');
      const items = recent.map(id=>recipes.find(r=>r.id===id)).filter(Boolean);
      if(!items.length){ wrap.style.display='none'; return; }
      wrap.style.display='block';
      strip.innerHTML = items.map(r=>`
        <button class="recent-card" data-recent="${r.id}" type="button">
          <img src="${r.image}" alt="${r.title}" loading="lazy">
          <strong>${r.title}</strong>
        </button>
      `).join('');
    }
    document.getElementById('recentStrip').addEventListener('click', e=>{
      const b=e.target.closest('[data-recent]');
      if(b) openRecipe(b.dataset.recent);
    });
    document.getElementById('clearRecentBtn').addEventListener('click', ()=>{
      recent = [];
      safeSet('kainTayoRecent','[]');
      renderRecent();
      toast('Recently viewed cleared');
    });

    // Theme preference
    function syncThemeIcon(){
      document.getElementById('themeNav').textContent = document.documentElement.classList.contains('theme-dark') ? '☀' : '☾';
    }
    if(safeGet('kainTayoTheme','light') === 'dark') document.documentElement.classList.add('theme-dark');
    syncThemeIcon();
    document.getElementById('themeNav').onclick = () => {
      document.documentElement.classList.toggle('theme-dark');
      safeSet('kainTayoTheme', document.documentElement.classList.contains('theme-dark') ? 'dark' : 'light');
      syncThemeIcon();
    };

    // Random recipe buttons
    ['randomBtn','randomNav','heroRandomBtn'].forEach(id=>document.getElementById(id)?.addEventListener('click',showRandomRecipe));

    // Shopping list buttons
    ['shoppingBtn','shoppingNav'].forEach(id=>document.getElementById(id)?.addEventListener('click',openShopping));
    document.getElementById('closeShopping').onclick=()=>{
      const d=document.getElementById('shoppingDrawer');
      d.classList.remove('open'); d.setAttribute('aria-hidden','true');
    };
    document.getElementById('clearShopping').onclick=()=>{
      shoppingItems=[];
      safeSet('kainTayoShopping','[]');
      renderShopping();
      toast('Shopping list cleared');
    };
    document.getElementById('copyShopping').onclick=async()=>{
      const txt=shoppingItems.map(x=>`☐ ${x.text}`).join('\n');
      try{await navigator.clipboard.writeText(txt);toast('Shopping list copied');}catch{toast('Copy is not available in this browser');}
    };

    // Serving control with fraction-aware ingredient scaling
    const FRACTIONS = {'⅛':.125,'¼':.25,'⅓':1/3,'⅜':.375,'⅖':.4,'½':.5,'⅗':.6,'⅝':.625,'⅔':2/3,'¾':.75,'⅘':.8,'⅚':5/6,'⅞':.875};
    const FRACTION_CHARS = Object.keys(FRACTIONS).join('');
    const LEADING_QTY = new RegExp(`^(\\d+(?:\\.\\d+)?)?\\s*([${FRACTION_CHARS}])?(?=\\s|$)`);

    function formatQty(n){
      if(Math.abs(n-Math.round(n)) < 0.01) return String(Math.round(n));
      const whole = Math.floor(n);
      const remainder = n - whole;
      let best = null, bestDiff = 0.06;
      for(const [ch,val] of Object.entries(FRACTIONS)){
        const diff = Math.abs(remainder-val);
        if(diff < bestDiff){ best = ch; bestDiff = diff; }
      }
      if(best) return (whole>0 ? whole+' ' : '') + best;
      return String(Math.round(n*100)/100);
    }

    function scaleIngredient(text){
      if(!currentRecipe) return text;
      if(text.includes('–')) return text; // ranges ("1–2 cups") aren't safely scalable — leave as written
      const base = parseInt((currentRecipe.servings||'4').match(/\d+/)?.[0] || 4, 10) || 4;
      const factor = servingCount / base;
      if(factor === 1) return text;
      const m = text.match(LEADING_QTY);
      if(!m || (!m[1] && !m[2])) return text; // no leading quantity to scale
      const qty = (m[1] ? parseFloat(m[1]) : 0) + (m[2] ? FRACTIONS[m[2]] : 0);
      if(!qty) return text;
      return formatQty(qty*factor) + text.slice(m[0].length);
    }

    function setServingDisplay(){
      if(!currentRecipe) return;
      document.getElementById('servingText').textContent = `${servingCount} ${servingCount===1?'serving':'servings'}`;
      document.getElementById('modalIngredients').innerHTML = currentRecipe.ingredients
        .map(i=>`<div class="ingredient-item">${scaleIngredient(i)}</div>`).join('');
    }
    document.getElementById('servMinus').onclick=()=>{if(servingCount>1){servingCount--;setServingDisplay();}};
    document.getElementById('servPlus').onclick=()=>{if(servingCount<20){servingCount++;setServingDisplay();}};
    document.getElementById('addShopBtn').onclick=()=>currentRecipe&&addIngredients(currentRecipe);
    document.getElementById('shareBtn').onclick=async()=>{
      if(!currentRecipe) return;
      const shareData={title:currentRecipe.title,text:`${currentRecipe.title} — KAIN TAYO`,url:location.href};
      try{if(navigator.share) await navigator.share(shareData); else {await navigator.clipboard.writeText(location.href);toast('Recipe link copied');}}catch{}
    };
    document.getElementById('printBtn').onclick=()=>window.print();

    // Initial render
    updateFavoritesBadge();
    renderRecent();
    render();
  </script>
</body>
</html>
