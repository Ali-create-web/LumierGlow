<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>LumierGlow — Glow Naturally</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,500;0,600;0,700;1,600&family=Nunito+Sans:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --white:#ffffff;
    --blush:#fff5f7;
    --pink:#ff6fa0;
    --pink-soft:#ffd6e4;
    --rose-deep:#c2185b;
    --plum:#2b2130;
    --plum-soft:#6e5c68;
    --shadow: 0 10px 30px rgba(194, 24, 91, 0.12);
    --radius: 20px;
  }

  *{ box-sizing:border-box; }
  html{ scroll-behavior:smooth; }
  body{
    margin:0;
    font-family:'Nunito Sans', sans-serif;
    color:var(--plum);
    background:var(--white);
    -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3{
    font-family:'Playfair Display', serif;
    margin:0;
    color:var(--rose-deep);
  }
  a{ text-decoration:none; }
  img{ max-width:100%; display:block; }
  .container{
    max-width:1140px;
    margin:0 auto;
    padding:0 24px;
  }

  /* NAV */
  .nav{
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:20px 24px;
    max-width:1140px;
    margin:0 auto;
  }
  .logo{
    font-family:'Playfair Display', serif;
    font-weight:700;
    font-size:1.5rem;
    color:var(--rose-deep);
    letter-spacing:0.5px;
  }
  .logo span{ color:var(--pink); }
  .nav-links{
    display:flex;
    gap:28px;
    font-weight:600;
    font-size:0.95rem;
  }
  .nav-links a{ color:var(--plum-soft); transition:color .2s; }
  .nav-links a:hover{ color:var(--rose-deep); }

  /* HERO */
  .hero{
    position:relative;
    text-align:center;
    padding:90px 24px 110px;
    overflow:hidden;
    background:linear-gradient(180deg, var(--blush) 0%, #ffffff 100%);
  }
  .glow-blob{
    position:absolute;
    top:-120px;
    left:50%;
    transform:translateX(-50%);
    width:520px;
    height:520px;
    border-radius:50%;
    background:radial-gradient(circle, rgba(255,111,160,0.45) 0%, rgba(255,111,160,0.18) 45%, rgba(255,255,255,0) 72%);
    animation:pulseGlow 6s ease-in-out infinite;
    pointer-events:none;
  }
  @keyframes pulseGlow{
    0%,100%{ opacity:0.7; transform:translateX(-50%) scale(1); }
    50%{ opacity:1; transform:translateX(-50%) scale(1.08); }
  }
  @media (prefers-reduced-motion: reduce){
    .glow-blob{ animation:none; }
  }
  .hero-content{ position:relative; z-index:2; }
  .eyebrow{
    display:inline-block;
    font-size:0.78rem;
    font-weight:800;
    letter-spacing:2px;
    text-transform:uppercase;
    color:var(--pink);
    background:var(--pink-soft);
    padding:6px 16px;
    border-radius:999px;
    margin-bottom:22px;
  }
  .hero h1{
    font-size:clamp(2.2rem, 5vw, 3.6rem);
    line-height:1.15;
    font-weight:700;
    max-width:780px;
    margin:0 auto 18px;
  }
  .hero p.subtitle{
    font-size:1.15rem;
    color:var(--plum-soft);
    max-width:560px;
    margin:0 auto 34px;
    font-weight:600;
  }
  .btn-primary{
    display:inline-block;
    background:var(--pink);
    color:#fff;
    font-weight:800;
    font-size:1rem;
    padding:15px 36px;
    border-radius:999px;
    box-shadow:var(--shadow);
    transition:transform .2s ease, box-shadow .2s ease, background .2s ease;
  }
  .btn-primary:hover{
    transform:translateY(-3px);
    background:var(--rose-deep);
    box-shadow:0 14px 34px rgba(194,24,91,0.22);
  }

  /* SECTION HEADINGS */
  .section{ padding:80px 24px; }
  .section-head{
    text-align:center;
    max-width:640px;
    margin:0 auto 48px;
  }
  .section-head .eyebrow{ margin-bottom:14px; }
  .section-head h2{
    font-size:clamp(1.8rem, 3.5vw, 2.4rem);
    margin-bottom:10px;
  }
  .section-head p{
    color:var(--plum-soft);
    font-weight:600;
    margin:0;
  }

  /* PRODUCTS */
  .products{ background:var(--white); }
  .product-grid{
    display:grid;
    grid-template-columns:repeat(3, 1fr);
    gap:28px;
  }
  .product-card{
    background:var(--white);
    border:1px solid #ffe3ec;
    border-radius:var(--radius);
    padding:22px;
    display:flex;
    flex-direction:column;
    transition:transform .25s ease, box-shadow .25s ease;
  }
  .product-card:hover{
    transform:translateY(-6px);
    box-shadow:var(--shadow);
  }
  .product-image{
    width:100%;
    aspect-ratio:1/1;
    border-radius:14px;
    overflow:hidden;
    margin-bottom:18px;
    background:var(--blush);
  }
  .product-image img{ width:100%; height:100%; object-fit:cover; }
  .product-name{
    font-family:'Playfair Display', serif;
    font-size:1.15rem;
    font-weight:600;
    color:var(--plum);
    margin-bottom:6px;
  }
  .product-desc{
    font-size:0.92rem;
    color:var(--plum-soft);
    font-weight:600;
    line-height:1.5;
    margin-bottom:14px;
    flex-grow:1;
  }
  .product-footer{
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:10px;
  }
  .product-price{
    font-family:'Playfair Display', serif;
    font-size:1.25rem;
    font-weight:700;
    color:var(--rose-deep);
  }
  .btn-buy{
    background:var(--plum);
    color:#fff;
    font-size:0.85rem;
    font-weight:800;
    padding:10px 18px;
    border-radius:999px;
    white-space:nowrap;
    transition:background .2s ease, transform .2s ease;
  }
  .btn-buy:hover{
    background:var(--pink);
    transform:translateY(-2px);
  }

  /* ABOUT */
  .about{
    background:linear-gradient(180deg, #ffffff 0%, var(--blush) 100%);
    text-align:center;
  }
  .about-card{
    max-width:680px;
    margin:0 auto;
    padding:0 12px;
  }
  .about-card p{
    font-size:1.15rem;
    line-height:1.7;
    color:var(--plum);
    font-weight:600;
  }
  .about-card p:first-of-type{ margin-bottom:14px; }

  /* FOOTER */
  footer{
    background:var(--plum);
    color:#f4e9ee;
    padding:44px 24px 30px;
    text-align:center;
  }
  footer .logo-foot{
    font-family:'Playfair Display', serif;
    font-size:1.3rem;
    font-weight:700;
    color:#fff;
    margin-bottom:12px;
  }
  footer .logo-foot span{ color:var(--pink); }
  footer .disclaimer{
    max-width:560px;
    margin:0 auto 16px;
    font-size:0.85rem;
    line-height:1.6;
    color:#d9c3cd;
  }
  footer .copyright{
    font-size:0.8rem;
    color:#b89aa5;
    border-top:1px solid rgba(255,255,255,0.12);
    padding-top:18px;
    margin-top:18px;
  }

  /* RESPONSIVE */
  @media (max-width:900px){
    .product-grid{ grid-template-columns:repeat(2, 1fr); }
  }
  @media (max-width:640px){
    .nav-links{ display:none; }
    .product-grid{ grid-template-columns:1fr; }
    .hero{ padding:70px 20px 90px; }
    .section{ padding:60px 20px; }
    .product-footer{ flex-direction:row; }
  }

  /* Focus visibility */
  a:focus-visible, button:focus-visible{
    outline:3px solid var(--rose-deep);
    outline-offset:2px;
  }
</style>
</head>
<body>

  <!-- NAV -->
  <nav class="nav">
    <div class="logo">Lumier<span>Glow</span></div>
    <div class="nav-links">
      <a href="#products">Products</a>
      <a href="#about">About</a>
      <a href="#footer">Contact</a>
    </div>
  </nav>

  <!-- HERO -->
  <section class="hero">
    <div class="glow-blob" aria-hidden="true"></div>
    <div class="hero-content">
      <span class="eyebrow">Skincare, Simplified</span>
      <h1>Glow Naturally with LumierGlow</h1>
      <p class="subtitle">Best Skincare Products Recommended by Experts</p>
      <a href="#products" class="btn-primary">Shop the Glow Edit</a>
    </div>
  </section>

  <!-- PRODUCTS -->
  <section class="section products" id="products">
    <div class="container">
      <div class="section-head">
        <span class="eyebrow">Curated Picks</span>
        <h2>Our Top Skincare Favorites</h2>
        <p>Hand-picked products loved for real, visible results.</p>
      </div>

      <div class="product-grid">

        <div class="product-card">
          <div class="product-image">
            <img src="https://placehold.co/400x400/ffd6e4/c2185b?text=Vitamin+C+Serum" alt="Vitamin C Serum">
          </div>
          <div class="product-name">Vitamin C Brightening Serum</div>
          <p class="product-desc">Lightweight serum that brightens skin tone and fades dark spots over time.</p>
          <div class="product-footer">
            <span class="product-price">$18.99</span>
            <a href="#" class="btn-buy" target="_blank" rel="nofollow sponsored noopener">Buy on Amazon</a>
          </div>
        </div>

        <div class="product-card">
          <div class="product-image">
            <img src="https://placehold.co/400x400/ffd6e4/c2185b?text=Hydrating+Moisturizer" alt="Hydrating Moisturizer">
          </div>
          <div class="product-name">Aqua Glow Daily Moisturizer</div>
          <p class="product-desc">24-hour hydration with hyaluronic acid for soft, plump, dewy skin.</p>
          <div class="product-footer">
            <span class="product-price">$14.49</span>
            <a href="#" class="btn-buy" target="_blank" rel="nofollow sponsored noopener">Buy on Amazon</a>
          </div>
        </div>

        <div class="product-card">
          <div class="product-image">
            <img src="https://placehold.co/400x400/ffd6e4/c2185b?text=Sunscreen+SPF+50" alt="Sunscreen SPF 50">
          </div>
          <div class="product-name">Daily Defense Sunscreen SPF 50</div>
          <p class="product-desc">No white-cast, non-greasy sun protection for everyday wear.</p>
          <div class="product-footer">
            <span class="product-price">$12.99</span>
            <a href="#" class="btn-buy" target="_blank" rel="nofollow sponsored noopener">Buy on Amazon</a>
          </div>
        </div>

        <div class="product-card">
          <div class="product-image">
            <img src="https://placehold.co/400x400/ffd6e4/c2185b?text=Gentle+Cleanser" alt="Gentle Cleanser">
          </div>
          <div class="product-name">Pure Petal Gentle Cleanser</div>
          <p class="product-desc">Sulfate-free foaming cleanser that removes impurities without drying skin.</p>
          <div class="product-footer">
            <span class="product-price">$11.50</span>
            <a href="#" class="btn-buy" target="_blank" rel="nofollow sponsored noopener">Buy on Amazon</a>
          </div>
        </div>

        <div class="product-card">
          <div class="product-image">
            <img src="https://placehold.co/400x400/ffd6e4/c2185b?text=Under+Eye+Cream" alt="Under Eye Cream">
          </div>
          <div class="product-name">Bright Eyes Renewal Cream</div>
          <p class="product-desc">Reduces puffiness and dark circles with caffeine and peptides.</p>
          <div class="product-footer">
            <span class="product-price">$16.25</span>
            <a href="#" class="btn-buy" target="_blank" rel="nofollow sponsored noopener">Buy on Amazon</a>
          </div>
        </div>

        <div class="product-card">
          <div class="product-image">
            <img src="https://placehold.co/400x400/ffd6e4/c2185b?text=Exfoliating+Mask" alt="Exfoliating Mask">
          </div>
          <div class="product-name">Rose Clay Exfoliating Mask</div>
          <p class="product-desc">Weekly treatment that smooths texture and unclogs pores gently.</p>
          <div class="product-footer">
            <span class="product-price">$19.99</span>
            <a href="#" class="btn-buy" target="_blank" rel="nofollow sponsored noopener">Buy on Amazon</a>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section class="section about" id="about">
    <div class="container about-card">
      <span class="eyebrow">About Us</span>
      <p>LumierGlow is a passion project born from a love of skin that feels as good as it looks.</p>
      <p>We test, research, and recommend only the skincare products that genuinely earn a spot in your routine.</p>
    </div>
  </section>

  <!-- FOOTER -->
  <footer id="footer">
    <div class="logo-foot">Lumier<span>Glow</span></div>
    <p class="disclaimer">As an Amazon Associate I earn from qualifying purchases.</p>
    <p class="copyright">&copy; <span id="year"></span> LumierGlow. All rights reserved.</p>
  </footer>

  <script>
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>

</body>
</html>
