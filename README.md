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
      border:1px solid var(--line);
      background:rgba(255,255,255,.55);
      width:42px;height:42px;border-radius:14px;
      display:grid;place-items:center;color:var(--green);
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
        <button class="icon-btn" id="favoriteNav" title="Show favorite recipes">♡</button>
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
            </div>
          </div>
        </div>
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
          <button class="filter" data-filter="Dessert">Dessert</button>
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
        id:'adobo',
        title:'Chicken Adobo',
        category:'Chicken',
        tags:['Easy','Chicken'],
        region:'Luzon',
        difficulty:'Easy',
        time:'55 mins',
        servings:'4 servings',
        description:'Tender chicken simmered in a savory, tangy sauce with garlic and peppercorn.',
        image:'https://images.unsplash.com/photo-1604908177522-4023ab1b7a9d?auto=format&fit=crop&w=1200&q=85',
        ingredients:['1 kg chicken pieces','½ cup soy sauce','½ cup vinegar','8 cloves garlic, crushed','3 bay leaves','1 tsp whole peppercorns','1 cup water','1 tbsp cooking oil'],
        steps:[
          ['Prep the chicken','Pat the chicken dry and set aside. Gather the garlic, bay leaves, peppercorns, soy sauce, and vinegar.'],
          ['Brown for flavor','Heat oil in a pot, then lightly brown the chicken pieces on both sides.'],
          ['Build the sauce','Add garlic, soy sauce, vinegar, bay leaves, peppercorns, and water. Bring to a boil.'],
          ['Simmer','Lower the heat and simmer uncovered for about 35–40 minutes, turning the chicken once or twice.'],
          ['Reduce & serve','Let the sauce reduce until glossy and flavorful. Serve hot with rice.']
        ]
      },
      {
        id:'sinigang',
        title:'Sinigang na Baboy',
        category:'Soup',
        tags:['Pork','Soup'],
        region:'Luzon',
        difficulty:'Medium',
        time:'1 hr 15 mins',
        servings:'5 servings',
        description:'A comforting sour tamarind soup packed with pork, vegetables, and deep savory flavor.',
        image:'https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1200&q=85',
        ingredients:['750 g pork belly or ribs','1.5 L water','2 tomatoes, quartered','1 onion, sliced','1 cup string beans','1 radish, sliced','1 eggplant, sliced','1–2 cups tamarind broth','2 cups kangkong','Fish sauce to taste'],
        steps:[
          ['Start the broth','Place pork, water, onion, and tomatoes in a pot. Bring to a boil and skim off excess foam.'],
          ['Tenderize','Cover and simmer until the pork is tender, around 45–55 minutes depending on the cut.'],
          ['Add vegetables','Add radish and eggplant first, then string beans. Simmer until just tender.'],
          ['Make it sour','Pour in tamarind broth gradually and adjust the sourness to your taste.'],
          ['Finish','Add kangkong and season with fish sauce. Cook for another 1–2 minutes, then serve.']
        ]
      },
      {
        id:'karekare',
        title:'Kare-Kare',
        category:'Pork',
        tags:['Pork'],
        region:'Luzon',
        difficulty:'Hard',
        time:'2 hrs',
        servings:'6 servings',
        description:'Rich peanut stew made special with tender meat, vegetables, and bagoong on the side.',
        image:'https://images.unsplash.com/photo-1601050690117-94f5f6fa8bd7?auto=format&fit=crop&w=1200&q=85',
        ingredients:['1 kg oxtail or beef chunks','½ cup peanut butter','¼ cup ground toasted peanuts','1 onion, chopped','4 cloves garlic','2 tbsp annatto oil','2 tbsp rice flour','4 cups beef broth','Eggplant, pechay, and string beans','Bagoong alamang, for serving'],
        steps:[
          ['Tenderize the meat','Simmer oxtail or beef in water until tender. Reserve the broth.'],
          ['Build the base','Sauté garlic and onion in annatto oil until fragrant.'],
          ['Thicken','Add peanut butter, ground peanuts, rice flour, and reserved broth. Stir until smooth.'],
          ['Combine','Return the tender meat to the sauce and simmer until rich and thick.'],
          ['Add vegetables','Blanch the vegetables separately and arrange beside the kare-kare. Serve with bagoong.']
        ]
      },
      {
        id:'inasal',
        title:'Chicken Inasal',
        category:'Chicken',
        tags:['Chicken','Easy'],
        region:'Visayas',
        difficulty:'Easy',
        time:'50 mins',
        servings:'4 servings',
        description:'Char-grilled chicken marinated in calamansi, vinegar, garlic, and annatto oil.',
        image:'https://images.unsplash.com/photo-1527477396000-e27163b481c2?auto=format&fit=crop&w=1200&q=85',
        ingredients:['1 kg chicken thighs or drumsticks','½ cup vinegar','½ cup calamansi juice','6 cloves garlic, minced','1 tbsp ginger, grated','1 tsp salt','1 tsp black pepper','Annatto oil for basting'],
        steps:[
          ['Marinate','Combine vinegar, calamansi, garlic, ginger, salt, and pepper. Marinate chicken for at least 2 hours.'],
          ['Heat the grill','Prepare a medium-hot grill and oil the grates lightly.'],
          ['Grill','Cook chicken slowly, turning often so it cooks evenly without burning.'],
          ['Baste','Brush generously with annatto oil while grilling for color and flavor.'],
          ['Rest & serve','Let the chicken rest for a few minutes, then serve with rice and your favorite dipping sauce.']
        ]
      },
      {
        id:'sinigang-hipon',
        title:'Sinigang na Hipon',
        category:'Seafood',
        tags:['Seafood','Soup','Easy'],
        region:'Visayas',
        difficulty:'Easy',
        time:'35 mins',
        servings:'4 servings',
        description:'Bright, sour tamarind soup with juicy shrimp and crisp vegetables.',
        image:'https://images.unsplash.com/photo-1562565652-a0d8f0c59eb4?auto=format&fit=crop&w=1200&q=85',
        ingredients:['500 g large shrimp','1.2 L water','2 tomatoes, quartered','1 onion, sliced','1 cup radish','1 cup okra','1 cup string beans','1–2 cups tamarind broth','2 cups kangkong','Fish sauce to taste'],
        steps:[
          ['Make the broth','Boil water with onion and tomatoes until the vegetables soften and the broth smells savory.'],
          ['Add sturdy vegetables','Add radish and okra. Simmer until nearly tender.'],
          ['Add shrimp','Drop in the shrimp and cook just until pink and opaque, usually 3–5 minutes.'],
          ['Add sourness','Stir in tamarind broth and adjust to taste.'],
          ['Finish','Add kangkong and season with fish sauce. Serve immediately.']
        ]
      },
      {
        id:'leche-flan',
        title:'Leche Flan',
        category:'Dessert',
        tags:['Dessert','Easy'],
        region:'Nationwide',
        difficulty:'Easy',
        time:'1 hr 10 mins',
        servings:'8 servings',
        description:'Silky steamed custard with a deep caramel topping—a Filipino celebration classic.',
        image:'https://images.unsplash.com/photo-1551024506-0bccd828d307?auto=format&fit=crop&w=1200&q=85',
        ingredients:['10 egg yolks','1 can condensed milk','1 can evaporated milk','1 tsp vanilla','¾ cup sugar for caramel','2 tbsp water'],
        steps:[
          ['Make caramel','Melt sugar and water in a pan over low heat until amber. Pour into a llanera or small mold.'],
          ['Mix gently','Combine egg yolks, condensed milk, evaporated milk, and vanilla. Stir gently to avoid too many bubbles.'],
          ['Strain','Pass the custard through a fine sieve for a smoother texture.'],
          ['Steam','Pour into the mold, cover with foil, and steam for about 35–45 minutes.'],
          ['Chill & unmold','Cool completely, refrigerate, then invert onto a plate and let the caramel run over the flan.']
        ]
      }
    ];

    const categories = [
      ['🍚','Rice & Meals','All'],
      ['🍲','Soups','Soup'],
      ['🍗','Chicken','Chicken'],
      ['🥩','Beef & Pork','Pork'],
      ['🐟','Seafood','Seafood'],
      ['🍰','Desserts','Dessert']
    ];

    const categoryGrid = document.getElementById('categoryGrid');
    categoryGrid.innerHTML = categories.map(([icon,name,filter]) =>
      `<button class="quick-card" data-category="${filter}">
        <span class="quick-icon">${icon}</span><strong>${name}</strong>
      </button>`
    ).join('');

    const recipeGrid = document.getElementById('recipeGrid');
    let currentFilter = 'All';
    let favorites = JSON.parse(localStorage.getItem('kainTayoFavorites') || '[]');

    function renderRecipes(list = getFilteredRecipes()){
      if(!list.length){
        recipeGrid.innerHTML = `<div class="empty"><strong>No recipes found.</strong><br>Try another search or category.</div>`;
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
              <span>⏱ ${r.time}</span><span>👥 ${r.servings}</span><span>🔥 ${r.difficulty}</span>
            </div>
            <button class="view-recipe" data-view="${r.id}">View Recipe →</button>
          </div>
        </article>
      `).join('');
    }

    function getFilteredRecipes(){
      return recipes.filter(r => currentFilter === 'All' || r.tags.includes(currentFilter) || r.category === currentFilter);
    }

    function setFilter(filter){
      currentFilter = filter;
      document.querySelectorAll('.filter').forEach(btn => btn.classList.toggle('active', btn.dataset.filter===filter));
      renderRecipes();
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

    function saveFavorite(id){
      favorites = favorites.includes(id) ? favorites.filter(x=>x!==id) : [...favorites,id];
      localStorage.setItem('kainTayoFavorites', JSON.stringify(favorites));
      renderRecipes();
    }
    recipeGrid.addEventListener('click', e => {
      const save = e.target.closest('[data-save]');
      if(save){ saveFavorite(save.dataset.save); return; }
      const view = e.target.closest('[data-view]');
      if(view) openRecipe(view.dataset.view);
    });

    const modal = document.getElementById('recipeModal');
    let currentRecipe = null;

    function openRecipe(id){
      const r = recipes.find(x=>x.id===id);
      if(!r) return;
      currentRecipe = r;
      document.getElementById('modalImg').src = r.image;
      document.getElementById('modalImg').alt = r.title;
      document.getElementById('modalTitle').textContent = r.title;
      document.getElementById('modalDescription').textContent = r.description;
      document.getElementById('modalChips').innerHTML = r.tags.map(t=>`<span class="chip">${t}</span>`).join('') + `<span class="chip">${r.region}</span>`;
      document.getElementById('modalMeta').innerHTML = `
        <span>⏱ ${r.time}</span><span>👥 ${r.servings}</span><span>🔥 ${r.difficulty}</span>
      `;
      document.getElementById('modalIngredients').innerHTML = r.ingredients.map(i=>`<div class="ingredient-item">${i}</div>`).join('');
      document.getElementById('modalSteps').innerHTML = r.steps.map((s,i)=>`
        <div class="step"><div class="step-num">${String(i+1).padStart(2,'0')}</div><div><strong>${s[0]}</strong><div style="margin-top:3px;color:var(--muted);font-size:.9rem">${s[1]}</div></div></div>
      `).join('');
      modal.classList.add('open');
      modal.setAttribute('aria-hidden','false');
      document.body.style.overflow='hidden';
    }

    function closeRecipe(){
      modal.classList.remove('open');
      modal.setAttribute('aria-hidden','true');
      document.body.style.overflow='';
    }

    document.getElementById('closeModal').onclick = closeRecipe;
    modal.addEventListener('click', e => { if(e.target===modal) closeRecipe(); });

    // Search
    document.getElementById('searchForm').addEventListener('submit', e => {
      e.preventDefault();
      const q = document.getElementById('searchInput').value.trim().toLowerCase();
      if(!q){ setFilter('All'); return; }
      currentFilter = 'Search';
      document.querySelectorAll('.filter').forEach(btn => btn.classList.remove('active'));
      const result = recipes.filter(r => [r.title,r.category,r.region,r.description,...r.tags,...r.ingredients].join(' ').toLowerCase().includes(q));
      renderRecipes(result);
      document.getElementById('recipes').scrollIntoView({behavior:'smooth'});
    });

    // Favorites view
    function showFavorites(){
      document.querySelectorAll('.filter').forEach(btn=>btn.classList.remove('active'));
      const favs = recipes.filter(r=>favorites.includes(r.id));
      renderRecipes(favs);
      document.getElementById('recipes').scrollIntoView({behavior:'smooth'});
    }
    document.getElementById('favoriteNav').onclick = showFavorites;
    document.getElementById('footerFavorites').onclick = e => { e.preventDefault(); showFavorites(); };

    // Ingredient suggestions
    function showSuggestions(){
      const q = document.getElementById('ingredientInput').value.trim().toLowerCase();
      const terms = q.split(',').map(s=>s.trim()).filter(Boolean);
      const scored = recipes.map(r=>{
        const hay = (r.title+' '+r.description+' '+r.ingredients.join(' ')+' '+r.tags.join(' ')).toLowerCase();
        const score = terms.length ? terms.reduce((n,t)=>n+(hay.includes(t)?1:0),0) : 0;
        return {r,score};
      }).filter(x=>x.score>0).sort((a,b)=>b.score-a.score);

      const list = scored.length ? scored.slice(0,4).map(({r})=>`
        <button class="suggestion" data-suggest="${r.id}">
          <div style="text-align:left"><strong>${r.title}</strong><br><small>${r.ingredients.slice(0,3).join(' • ')}</small></div><span>→</span>
        </button>
      `).join('') : `<div class="suggestion"><div><strong>No exact match yet.</strong><br><small>Try chicken, pork, shrimp, garlic, or soy sauce.</small></div></div>`;
      document.getElementById('suggestions').innerHTML = list;
    }
    document.getElementById('suggestBtn').onclick = showSuggestions;
    document.getElementById('suggestions').addEventListener('click', e=>{
      const b=e.target.closest('[data-suggest]');
      if(b) openRecipe(b.dataset.suggest);
    });

    // Cook Mode
    const cookOverlay = document.getElementById('cookOverlay');
    let cookIndex = 0;
    function startCook(r){
      currentRecipe = r;
      cookIndex = 0;
      closeRecipe();
      updateCook();
      cookOverlay.classList.add('open');
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
    document.getElementById('modalCookBtn').onclick = () => currentRecipe && startCook(currentRecipe);
    document.getElementById('heroCookBtn').onclick = () => startCook(recipes[0]);
    document.getElementById('nextStep').onclick = () => {
      if(cookIndex < currentRecipe.steps.length-1){ cookIndex++; updateCook(); }
      else { cookOverlay.classList.remove('open'); }
    };
    document.getElementById('prevStep').onclick = () => { if(cookIndex>0){cookIndex--;updateCook();} };
    document.getElementById('closeCook').onclick = () => cookOverlay.classList.remove('open');

    // keyboard
    document.addEventListener('keydown', e => {
      if(e.key==='Escape'){
        closeRecipe();
        cookOverlay.classList.remove('open');
      }
      if(cookOverlay.classList.contains('open')){
        if(e.key==='ArrowRight') document.getElementById('nextStep').click();
        if(e.key==='ArrowLeft') document.getElementById('prevStep').click();
      }
    });

    renderRecipes();
  </script>
</body>
</html>
