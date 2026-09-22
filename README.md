<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Little Sugar Case — เคสโทรศัพท์โทนพาสเทล</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@500;600;700;800&family=Quicksand:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --cream:#FBF4EA;
    --cream-deep:#F3E7D6;
    --paper:#FFFDF9;
    --ink:#6B4F3F;
    --ink-soft:#9A8072;
    --pink:#F6C7CE;
    --sage:#C6D6B6;
    --butter:#F3E1A0;
    --sky:#C2DCEE;
    --lavender:#D8CAEA;
    --peach:#F2C9A3;
    --mint:#CDE3D3;
    --cloud:#FFFFFF;
    --line:#EADFCB;
    --shadow: 0 10px 26px -14px rgba(107,79,63,0.35);
    --radius-lg: 26px;
    --radius-md: 18px;
    --radius-sm: 12px;
  }
  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    font-family:'Quicksand',sans-serif;
    background:var(--cream);
    color:var(--ink);
    -webkit-font-smoothing:antialiased;
    min-height:100vh;
  }
  h1,h2,h3,.display{font-family:'Baloo 2',sans-serif;}
  a{color:inherit;text-decoration:none;}
  button{font-family:inherit;cursor:pointer;}

  /* ---------- background texture ---------- */
  .bg-dots{
    position:fixed;inset:0;pointer-events:none;z-index:0;
    background-image: radial-gradient(circle, rgba(107,79,63,0.06) 1.4px, transparent 1.4px);
    background-size: 26px 26px;
  }

  /* ---------- top nav ---------- */
  header{
    position:sticky;top:0;z-index:50;
    background:rgba(251,244,234,0.92);
    backdrop-filter:blur(8px);
    border-bottom:1px solid var(--line);
  }
  .nav-wrap{
    max-width:1180px;margin:0 auto;
    display:flex;align-items:center;justify-content:space-between;
    padding:14px 22px;
    gap:16px;
  }
  .logo{display:flex;align-items:center;gap:10px;}
  .logo-mark{
    width:42px;height:42px;border-radius:50%;
    background:linear-gradient(160deg,var(--peach),var(--pink));
    display:flex;align-items:center;justify-content:center;
    box-shadow: var(--shadow);
    flex-shrink:0;
  }
  .logo-name{font-family:'Baloo 2';font-weight:700;font-size:1.25rem;line-height:1;}
  .logo-tag{font-size:0.68rem;color:var(--ink-soft);letter-spacing:.04em;}
  nav.pages{display:flex;gap:6px;background:var(--paper);padding:5px;border-radius:999px;border:1px solid var(--line);}
  nav.pages button{
    border:none;background:transparent;padding:9px 18px;border-radius:999px;
    font-weight:700;font-size:0.92rem;color:var(--ink-soft);
    transition:.2s;
  }
  nav.pages button.active{background:var(--ink);color:var(--paper);}
  .cart-btn{
    position:relative;
    display:flex;align-items:center;gap:8px;
    background:var(--ink);color:var(--paper);
    padding:10px 16px;border-radius:999px;border:none;font-weight:700;
    box-shadow: var(--shadow);
  }
  .cart-count{
    background:var(--pink);color:var(--ink);
    border-radius:999px;min-width:20px;height:20px;padding:0 5px;
    display:flex;align-items:center;justify-content:center;font-size:0.72rem;font-weight:800;
  }

  main{position:relative;z-index:1;max-width:1180px;margin:0 auto;padding:0 22px 90px;}
  .page{display:none;animation:fade .35s ease;}
  .page.active{display:block;}
  @keyframes fade{from{opacity:0;transform:translateY(6px);}to{opacity:1;transform:translateY(0);}}

  /* ---------- shared bits ---------- */
  .eyebrow{
    display:inline-flex;align-items:center;gap:8px;
    font-size:0.78rem;font-weight:700;letter-spacing:.06em;
    color:var(--ink-soft);text-transform:uppercase;
    margin-bottom:8px;
  }
  .eyebrow::before{content:"";width:16px;height:2px;background:var(--ink-soft);border-radius:2px;}
  .section-title{font-size:1.7rem;font-weight:700;margin:0 0 4px;}
  .section-sub{color:var(--ink-soft);margin:0 0 22px;font-size:0.96rem;}
  .pill{
    padding:5px 12px;border-radius:999px;font-size:0.76rem;font-weight:700;
    background:var(--cream-deep);color:var(--ink);border:1px solid var(--line);
  }

  /* ---------- HOME ---------- */
  .hero{
    display:grid;grid-template-columns:1.05fr 0.95fr;gap:36px;
    align-items:center;
    padding:52px 0 36px;
  }
  .hero-copy .display{font-size:2.6rem;line-height:1.08;margin:10px 0 14px;}
  .hero-copy .display em{
    font-style:normal;color:var(--pink);
    -webkit-text-stroke: 1.5px var(--ink);
  }
  .hero-copy p{color:var(--ink-soft);font-size:1.02rem;max-width:460px;margin:0 0 22px;}
  .hero-actions{display:flex;gap:12px;flex-wrap:wrap;}
  .btn-primary{
    background:var(--ink);color:var(--paper);border:none;
    padding:13px 24px;border-radius:999px;font-weight:700;font-size:0.95rem;
    box-shadow:var(--shadow);
  }
  .btn-ghost{
    background:var(--paper);color:var(--ink);border:1.5px solid var(--line);
    padding:12px 22px;border-radius:999px;font-weight:700;font-size:0.95rem;
  }
  .welcome-banner{
    margin-top:18px;padding:12px 16px;border-radius:var(--radius-sm);
    background:var(--sky);font-size:0.85rem;font-weight:600;
    display:flex;align-items:center;gap:8px;max-width:460px;
  }
  .hero-stage{position:relative;height:340px;}
  .stage-case{
    position:absolute;width:150px;height:280px;border-radius:34px;
    box-shadow:0 24px 40px -16px rgba(107,79,63,.4);
    border:5px solid rgba(255,255,255,.6);
  }
  .stage-case.c1{left:8%;top:10px;transform:rotate(-9deg);z-index:2;}
  .stage-case.c2{left:38%;top:44px;transform:rotate(4deg);z-index:3;}
  .stage-case.c3{left:64%;top:0;transform:rotate(14deg);z-index:1;}
  
  /* ---------- STOREFRONT ---------- */
  .storefront-section{
    margin:0 0 46px;
    border-radius:var(--radius-lg);
    overflow:hidden;
    box-shadow:var(--shadow);
    position:relative;
  }
  .storefront-img{
    width:100%;
    height:340px;
    object-fit:cover;
    display:block;
  }
  .storefront-caption{
    position:absolute;
    left:0;right:0;bottom:0;
    padding:20px 24px;
    background:linear-gradient(0deg, rgba(107,79,63,0.75), rgba(107,79,63,0));
    color:#fff;
  }
  .storefront-caption b{
    font-family:'Baloo 2',sans-serif;
    font-size:1.15rem;
    display:block;
    margin-bottom:2px;
  }
  .storefront-caption span{
    font-size:0.8rem;
    opacity:0.9;
  }
  @media(max-width:920px){
    .storefront-img{height:220px;}
  }

  .cat-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:16px;margin:20px 0 46px;}
  .cat-card{
    background:var(--paper);border:1px solid var(--line);border-radius:var(--radius-md);
    padding:18px;display:flex;flex-direction:column;gap:10px;
    cursor:pointer;transition:.2s;
  }
  .cat-card:hover{transform:translateY(-3px);box-shadow:var(--shadow);}
  .cat-swatch{width:44px;height:44px;border-radius:14px;display:flex;align-items:center;justify-content:center;font-size:1.3rem;}
  .cat-card b{font-size:1rem;}
  .cat-card span{font-size:0.8rem;color:var(--ink-soft);}

  .feat-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:18px;}
  .prod-card{
    background:var(--paper);border:1px solid var(--line);border-radius:var(--radius-md);
    overflow:hidden;display:flex;flex-direction:column;transition:.2s;
  }
  .prod-card:hover{transform:translateY(-4px);box-shadow:var(--shadow);}
  .prod-thumb{aspect-ratio:1/1;display:flex;align-items:center;justify-content:center;padding:14px;position:relative;}
  .prod-thumb svg{width:100%;height:100%;}
  .badge{
    position:absolute;top:10px;left:10px;font-size:0.68rem;font-weight:800;
    padding:4px 9px;border-radius:999px;background:var(--ink);color:var(--paper);
  }
  .prod-body{padding:12px 14px 16px;display:flex;flex-direction:column;gap:6px;flex:1;}
  .prod-name{font-weight:700;font-size:0.95rem;}
  .prod-meta{font-size:0.75rem;color:var(--ink-soft);}
  .prod-row{display:flex;align-items:center;justify-content:space-between;margin-top:auto;}
  .prod-price{font-weight:800;color:var(--ink);}
  .mini-btn{
    background:var(--cream-deep);border:1px solid var(--line);color:var(--ink);
    padding:7px 12px;border-radius:999px;font-weight:700;font-size:0.75rem;
  }
  .mini-btn:hover{background:var(--pink);}

  /* ---------- PRODUCTS PAGE ---------- */
  .products-layout{display:grid;grid-template-columns:250px 1fr;gap:26px;padding-top:34px;align-items:start;}
  .filter-panel{
    background:var(--paper);border:1px solid var(--line);border-radius:var(--radius-md);
    padding:18px;position:sticky;top:88px;
  }
  .filter-panel h4{margin:0 0 4px;font-size:0.95rem;}
  .filter-panel .filter-note{font-size:0.72rem;color:var(--ink-soft);margin:0 0 14px;line-height:1.5;}
  .filter-group{margin-bottom:18px;}
  .filter-group>b{display:block;font-size:0.8rem;margin-bottom:8px;color:var(--ink);}
  .chk-row{display:flex;align-items:center;gap:8px;font-size:0.85rem;margin-bottom:7px;cursor:pointer;}
  .chk-row input{accent-color:var(--ink);width:15px;height:15px;}
  select, input[type="text"]{
    width:100%;padding:9px 11px;border-radius:10px;border:1.4px solid var(--line);
    background:var(--cream);font-family:inherit;font-size:0.85rem;color:var(--ink);
  }
  .search-box{margin-bottom:18px;}
  .clear-filters{width:100%;padding:9px;border-radius:10px;border:1.4px solid var(--line);background:var(--cloud);font-weight:700;font-size:0.8rem;color:var(--ink-soft);}
  .results-head{display:flex;justify-content:space-between;align-items:baseline;margin-bottom:14px;}
  .results-head span{font-size:0.85rem;color:var(--ink-soft);}
  .prod-full-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:18px;}
  .empty-state{
    grid-column:1/-1;text-align:center;padding:50px 20px;color:var(--ink-soft);
    background:var(--paper);border:1px dashed var(--line);border-radius:var(--radius-md);
  }
  .model-select-row{display:flex;gap:8px;margin-top:8px;}
  .model-select-row select{flex:1;font-size:0.78rem;padding:7px 8px;}

  /* ---------- CHECKOUT PAGE ---------- */
  .checkout-layout{display:grid;grid-template-columns:1.5fr 1fr;gap:28px;padding-top:34px;align-items:start;}
  .cart-list{display:flex;flex-direction:column;gap:12px;}
  .cart-item{
    background:var(--paper);border:1px solid var(--line);border-radius:var(--radius-md);
    padding:12px;display:flex;gap:12px;align-items:center;
  }
  .cart-thumb{width:64px;height:64px;border-radius:12px;overflow:hidden;flex-shrink:0;background:var(--cream-deep);}
  .cart-thumb svg{width:100%;height:100%;}
  .cart-info{flex:1;min-width:0;}
  .cart-info b{font-size:0.9rem;display:block;}
  .cart-info span{font-size:0.75rem;color:var(--ink-soft);}
  .qty-ctrl{display:flex;align-items:center;gap:8px;background:var(--cream);border-radius:999px;padding:4px 8px;}
  .qty-ctrl button{border:none;background:var(--paper);width:22px;height:22px;border-radius:50%;font-weight:800;}
  .cart-price{font-weight:800;min-width:70px;text-align:right;}
  .remove-btn{background:none;border:none;color:var(--ink-soft);font-size:0.72rem;text-decoration:underline;margin-left:8px;}

  .summary-card{
    background:var(--paper);border:1px solid var(--line);border-radius:var(--radius-md);
    padding:20px;position:sticky;top:88px;
  }
  .summary-row{display:flex;justify-content:space-between;font-size:0.9rem;margin-bottom:10px;color:var(--ink-soft);}
  .summary-row.total{color:var(--ink);font-weight:800;font-size:1.15rem;border-top:1px dashed var(--line);padding-top:12px;margin-top:6px;}
  .promo-msg{font-size:0.78rem;padding:8px 10px;border-radius:10px;margin:4px 0;font-weight:700;}
  .promo-msg.ok{background:var(--mint);color:#3f5b45;}
  .promo-msg.no{background:var(--cream-deep);color:var(--ink-soft);}
  .coupon-row{display:flex;gap:8px;margin:14px 0;}
  .coupon-row button{padding:9px 14px;border-radius:10px;border:none;background:var(--ink);color:var(--paper);font-weight:700;font-size:0.8rem;}
  .checkout-btn{
    width:100%;padding:14px;border:none;border-radius:14px;background:var(--ink);color:var(--paper);
    font-weight:800;font-size:1rem;margin-top:10px;box-shadow:var(--shadow);
  }
  .cross-sell{margin-top:36px;}
  .cross-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:16px;}
  .empty-cart{
    background:var(--paper);border:1px dashed var(--line);border-radius:var(--radius-md);
    padding:50px 20px;text-align:center;color:var(--ink-soft);
  }

  footer{
    text-align:center;padding:26px;color:var(--ink-soft);font-size:0.78rem;
    border-top:1px solid var(--line);position:relative;z-index:1;
  }
  .toast{
    position:fixed;bottom:24px;left:50%;transform:translateX(-50%) translateY(20px);
    background:var(--ink);color:var(--paper);padding:12px 20px;border-radius:999px;
    font-weight:700;font-size:0.85rem;opacity:0;pointer-events:none;transition:.3s;z-index:200;
    box-shadow:var(--shadow);
  }
  .toast.show{opacity:1;transform:translateX(-50%) translateY(0);}

  /* ---------- PRODUCT DETAIL MODAL ---------- */
  .product-modal-overlay{
    display:none;
    position:fixed;inset:0;z-index:300;
    background:rgba(107,79,63,0.45);
    align-items:center;justify-content:center;
    padding:20px;
  }
  .product-modal-overlay.show{display:flex;}
  .product-modal{
    background:var(--paper);
    border-radius:var(--radius-lg);
    max-width:560px;width:100%;
    max-height:85vh;overflow-y:auto;
    display:grid;grid-template-columns:1fr 1fr;
    position:relative;
    box-shadow:var(--shadow);
  }
  .modal-close-btn{
    position:absolute;top:12px;right:12px;
    width:32px;height:32px;border-radius:50%;
    background:var(--cream-deep);border:none;
    font-size:1rem;font-weight:800;color:var(--ink);
    z-index:2;
  }
  .modal-img-wrap{
    background:var(--cream-deep);
    display:flex;align-items:center;justify-content:center;
    padding:24px;
  }
  .modal-img-wrap svg,.modal-img-wrap img{width:100%;height:100%;}
  .modal-info{padding:24px;display:flex;flex-direction:column;gap:10px;}
  .modal-info h3{margin:0;font-size:1.2rem;font-family:'Baloo 2',sans-serif;}
  .modal-meta{font-size:0.8rem;color:var(--ink-soft);}
  .modal-price{font-size:1.3rem;font-weight:800;color:var(--ink);}
  .modal-desc{font-size:0.85rem;color:var(--ink-soft);line-height:1.5;margin:0;}
  @media(max-width:560px){
    .product-modal{grid-template-columns:1fr;}
  }
  
  @media(max-width:920px){
    .hero{grid-template-columns:1fr;padding-top:30px;}
    .hero-stage{display:none;}
    .cat-grid{grid-template-columns:repeat(2,1fr);}
    .feat-grid{grid-template-columns:repeat(2,1fr);}
    .products-layout,.checkout-layout{grid-template-columns:1fr;}
    .filter-panel{position:static;}
    .prod-full-grid{grid-template-columns:repeat(2,1fr);}
    .cross-grid{grid-template-columns:repeat(2,1fr);}
    nav.pages button{padding:8px 12px;font-size:0.82rem;}
    .logo-tag{display:none;}
  }

     /* ---- ซ่อนหมายเหตุอธิบาย discrete math (ไม่ลบโค้ด) ---- */
    .section-sub   { display: none !important; }  /* 3 บรรทัดใต้หัวข้อทั้ง 3 หน้า */
    .filter-note   { display: none !important; }  /* หมวด(ทั้งหมด) ∪ ... ∩ สี(ทั้งหมด) */
    .dm-note       { display: none !important; }  /* ข้อความในวงเล็บที่จะ mark ในข้อ 2 */
  
</style>
</head>
<body>
<div class="bg-dots"></div>

<header>
  <div class="nav-wrap">
    <div class="logo">
      <div class="logo-mark">
        <svg width="24" height="24" viewBox="0 0 24 24"><circle cx="12" cy="13" r="8" fill="#fff"/><circle cx="6" cy="6" r="3.2" fill="#fff"/><circle cx="18" cy="6" r="3.2" fill="#fff"/><circle cx="9.2" cy="12.5" r="1.1" fill="#6B4F3F"/><circle cx="14.8" cy="12.5" r="1.1" fill="#6B4F3F"/><ellipse cx="12" cy="15.4" rx="1.6" ry="1.1" fill="#6B4F3F"/></svg>
      </div>
      <div>
        <div class="logo-name">Little Sugar Case</div>
        <div class="logo-tag">เคสหวานละมุนทุกรุ่น iPhone</div>
      </div>
    </div>
    <nav class="pages">
      <button data-goto="home" class="active">หน้าแรก</button>
      <button data-goto="products">สินค้า</button>
      <button data-goto="checkout">ตะกร้า</button>
    </nav>
    <button class="cart-btn" data-goto="checkout">
      🛍️ ตะกร้า <span class="cart-count" id="navCartCount">0</span>
    </button>
  </div>
</header>

<main>

  <!-- ============ PAGE 1: HOME ============ -->
  <section class="page active" id="page-home">
    <div class="hero">
      <div class="hero-copy">
        <div class="eyebrow">Pastel Phone Case Studio</div>
        <h1 class="display">เคสน่ารัก โทน<em>พาสเทล</em><br>สำหรับ iPhone ทุกรุ่น</h1>
        <p class="dm-note">ตั้งแต่ iPhone 11 ถึง 17 รวม Pro และ Pro Max — ลายหมีน้อย ลายดอกไม้ และลายข้อความน้อย ๆ ให้เลือกครบทุกสี ทุกรุ่น</p> 
        <div class="hero-actions">
          <button class="btn-primary" data-goto="products">เลือกซื้อเคสทั้งหมด</button>
          <button class="btn-ghost" data-goto="products" data-scroll-cat="bear">ดูลายหมียอดฮิต</button>
        </div>
        <div class="welcome-banner" id="welcomeBanner"></div>
      </div>
      
      <div class="hero-stage">
        <div class="stage-case c1" style="background:var(--pink)"></div>
        <div class="stage-case c2" style="background:var(--sky)"></div>
        <div class="stage-case c3" style="background:var(--butter)"></div>
      </div>
    </div>
    
 <div class="storefront-section">                              
      <img class="storefront-img" src="" id="storefrontImg" alt="หน้าร้าน Little Sugar Case">
      <div class="storefront-caption">
        <b>หน้าร้าน Little Sugar Case</b>
        <span>แวะมาเลือกเคสตัวเป็นๆ ได้ที่หน้าร้านของเรา</span>
      </div>
    </div>
    
    <div class="eyebrow">หมวดหมู่สินค้า</div>
    <h2 class="section-title">เลือกช้อปตามลาย</h2>
    <p class="section-sub">แต่ละหมวดคือ <b>เซต</b> ของสินค้า — จำนวนชิ้นต่อหมวดคำนวณสดจาก <code>Set.size</code></p>
    <div class="cat-grid" id="catGrid"></div>

    <div class="eyebrow">สินค้าแนะนำ</div>
    <h2 class="section-title">ยอดนิยมประจำร้าน</h2>
    <p class="section-sub">คัดจากเซตสินค้าที่ติดแท็ก <code>bestseller</code></p>
    <div class="feat-grid" id="featGrid"></div>
  </section>

  <!-- ============ PAGE 2: PRODUCTS ============ -->
  <section class="page" id="page-products">
    <div class="eyebrow">สินค้าทั้งหมด</div>
    <h2 class="section-title">เลือกลาย เลือกสี เลือกรุ่นของคุณ</h2>
    <p class="section-sub">กรองสินค้าด้วยการดำเนินการของเซต: <b>Union</b> (รวมหมวด), <b>Intersection</b> (ตัดกับสี), <b>Difference</b> (ตัดลายเคสใสออก)</p>

    <div class="products-layout">
      <aside class="filter-panel">
        <h4>ค้นหา</h4>
        <div class="search-box">
          <input type="text" id="searchInput" placeholder="พิมพ์ชื่อลาย เช่น หมี, ดอกไม้...">
        </div>

                <div class="filter-group">
          <b>ลาย <span class="dm-note">(เลือกได้หลายลาย = Union)</span></b>
          <div id="catFilters"></div>
        </div>

        <div class="filter-group">
          <b>โทนสี <span class="dm-note">(Intersection กับลาย)</span></b>
          <div id="colorFilters"></div>
        </div> 

        <div class="filter-group">
          <b>รุ่น iPhone</b>
          <select id="modelFilter"><option value="">ทุกรุ่น</option></select>
        </div>

                <div class="filter-group">
          <label class="chk-row">
            <input type="checkbox" id="excludeClear">
            ไม่เอาเคสใส <span class="dm-note">(Difference)</span>
          </label>
        </div> 

        <button class="clear-filters" id="clearFiltersBtn">ล้างตัวกรองทั้งหมด</button>
        <p class="filter-note" id="filterFormula"></p>
      </aside>

      <div>
        <div class="results-head">
          <span id="resultsCount"></span>
        </div>
        <div class="prod-full-grid" id="productGrid"></div>
      </div>
    </div>
  </section>

  <!-- ============ PAGE 3: CHECKOUT ============ -->
  <section class="page" id="page-checkout">
    <div class="eyebrow">ตะกร้าสินค้า</div>
    <h2 class="section-title">สรุปคำสั่งซื้อ</h2>
    <p class="section-sub">คำนวณราคาด้วย <code>reduce()</code> และตรวจโปรโมชั่นด้วยตรรกศาสตร์ <code>if–else</code>, <code>&amp;&amp;</code>, <code>||</code></p>

    <div class="checkout-layout">
      <div>
        <div class="cart-list" id="cartList"></div>

        <div class="cross-sell" id="crossSellWrap" style="display:none;">
          <div class="eyebrow">แนะนำเพิ่มเติมสำหรับคุณ</div>
          <h3 class="section-title" style="font-size:1.2rem;">อาจถูกใจด้วยนะ (Set Difference จากตะกร้า)</h3>
          <div class="cross-grid" id="crossSellGrid"></div>
        </div>
      </div>

      <div class="summary-card">
        <h4 style="margin:0 0 14px;">สรุปยอด</h4>
        <div class="summary-row"><span>ราคารวมสินค้า</span><span id="sumSubtotal">฿0</span></div>
        <div class="summary-row"><span>ส่วนลด</span><span id="sumDiscount">-฿0</span></div>
        <div class="summary-row"><span>ค่าจัดส่ง</span><span id="sumShipping">฿0</span></div>
        <div class="summary-row total"><span>ยอดชำระ</span><span id="sumTotal">฿0</span></div>

        <div id="promoMessages"></div>

        <div class="coupon-row">
          <input type="text" id="couponInput" placeholder="ใส่โค้ดส่วนลด เช่น SUGAR10">
          <button id="applyCouponBtn">ใช้โค้ด</button>
        </div>

        <button class="checkout-btn" id="placeOrderBtn">ยืนยันคำสั่งซื้อ</button>
      </div>
    </div>
  </section>

</main>

<footer>© 2026 Little Sugar Case — ทำด้วยความน่ารักในทุกออเดอร์ 🧸</footer>
<div class="toast" id="toast"></div>

  <div class="product-modal-overlay" id="productModal">
  <div class="product-modal">
    <button class="modal-close-btn" id="modalCloseBtn">✕</button>
    <div class="modal-img-wrap" id="modalImgWrap"></div>
    <div class="modal-info">
      <h3 id="modalName"></h3>
      <span class="modal-meta" id="modalMeta"></span>
      <span class="modal-price" id="modalPrice"></span>
      <p class="modal-desc" id="modalDesc"></p>
      <div class="model-select-row">
        <select id="modalModelSelect"></select>
      </div>
      <button class="btn-primary" id="modalAddBtn">หยิบใส่ตะกร้า</button>
    </div>
  </div>
</div>
  
<script>
/* =========================================================================
   LITTLE SUGAR CASE — DATA LAYER
   ใช้ Set() ในการจัดกลุ่มสินค้า (categories, colors, tags)
   ========================================================================= */

// ---- iPhone models: 7 generations x (base / Pro / Pro Max) = 21 รุ่น ----
const GENERATIONS = [11,12,13,14,15,16,17];
const TIERS = ["", "Pro", "Pro Max"];
const MODELS = [];
GENERATIONS.forEach(gen=>{
  TIERS.forEach(tier=>{
    MODELS.push(tier ? `iPhone ${gen} ${tier}` : `iPhone ${gen}`);
  });
});

// ---- Colors ----
const COLORS = {
  pink:   {label:"ชมพูละมุน",   hex:"#F6C7CE"},
  sage:   {label:"เขียวเซจ",    hex:"#C6D6B6"},
  butter: {label:"เหลืองบัตเตอร์",hex:"#F3E1A0"},
  sky:    {label:"ฟ้าหวาน",     hex:"#C2DCEE"},
  lavender:{label:"ม่วงลาเวนเดอร์",hex:"#D8CAEA"},
  peach:  {label:"สีส้ม", hex:"#F2C9A3"},
  mint:   {label:"เขียวมิ้นต์",  hex:"#CDE3D3"},
  cream:  {label:"ครีมนุ่ม",    hex:"#F2E9DA"},
  clear:  {label:"ใสพิเศษ",     hex:"#FFFFFF"}
};

// ---- Categories ----
  const CATEGORIES = {
  bear:   { label: "หมีน้อย",     desc: "ลายหมีน่ารัก อบอุ่นละมุน",   icon: "🐻" },
  floral: { label: "สวนดอกไม้",   desc: "ลายดอกไม้พาสเทลสดใส",       icon: "🌸" },
  quote:  { label: "คำน้อยๆ",     desc: "ข้อความน่ารักให้กำลังใจ",    icon: "💬" },
  clear:  { label: "ใสน่ารัก",    desc: "เคสใสพิมพ์ลายน่ารัก",        icon: "🎈" }
};
  
// ---- URL รูปภาพจริงทั้งหมด (โฮสต์บน GitHub Pages) ----
const IMG_BASE = "https://s69122202028-sketch.github.io/LittleSugar-Case/images/";
const STOREFRONT_IMG = IMG_BASE + "storefront.png";
const PRODUCT_IMAGES = {
  // หมีน้อย 7 สี
  bear_pink:    IMG_BASE + "bear-pink.png",
  bear_sage:    IMG_BASE + "bear-light-green.png",
  bear_butter:  IMG_BASE + "bear-yellow.png",
  bear_sky:     IMG_BASE + "bear-blue.png",
  bear_lavender:IMG_BASE + "bear-purple.png",
  bear_peach:   IMG_BASE + "bear-peach.png",
  bear_mint:    IMG_BASE + "bear-green.png",
  // สวนดอกไม้ 7 สี
  floral_pink:    IMG_BASE + "flower-pink.png",
  floral_sage:    IMG_BASE + "flower-light-green.png",
  floral_butter:  IMG_BASE + "flower-yellow.png",
  floral_sky:     IMG_BASE + "flower-blue.png",
  floral_lavender:IMG_BASE + "flower-purple.png",
  floral_peach:   IMG_BASE + "flower-peach.png",
  floral_mint:    IMG_BASE + "flower-green.png",
  // คำน้อยๆ 7 สีคำน้อยๆ (5 สี) + ใสน่ารัก (2 ลาย)
  quote_cream:    IMG_BASE + "cream-text.png",
  quote_sage:     IMG_BASE + "light-green-text.png",
  quote_butter:   IMG_BASE + "yellow-text.png",
  quote_sky:      IMG_BASE + "blue-text.png",
  quote_lavender: IMG_BASE + "purple-text.png",
  quote_mint:     IMG_BASE + "green-text.png",   // "Keep Growing" — ลายที่ 6 ของหมวดคำน้อยๆ
  quote_peach:    IMG_BASE + "peach-text.png",   // "Stay Sunny"   — ลายที่ 7 ของหมวดคำน้อยๆ
  // ใสน่ารัก
  clear_cutebear:  IMG_BASE + "bear-pastel.png",
  clear_goodvibes: IMG_BASE + "flower-pastel.png",
  clear_balloon:   IMG_BASE + "balloon-pastel.png",
  clear_star:      IMG_BASE + "star-pastel.png",
  clear_heart:     IMG_BASE + "heart-pastel.png",
  clear_bloom:     IMG_BASE + "flower-bow-pastel.png",
  clear_cuddle:    IMG_BASE + "bear-heart-pastel.png",
};

// ---- สร้างรายชื่อสินค้า 28 ลาย (ตามภาพอ้างอิง 3 แถว x 7 คอลัมน์) ----
const PRODUCTS = [];
let pid = 1;

// แถว 1: หมีน้อย (7 สี)
["pink","sage","butter","sky","lavender","peach","mint"].forEach((c,i)=>{
  PRODUCTS.push({
    id: pid++,
    name: `หมีน้อย ${COLORS[c].label}`,
    category: "bear",
    color: c,
    price: 259,
    tags: new Set(i<2 ? ["bestseller"] : (i===6?["new"]:[])),
    models: [...MODELS],
    image: PRODUCT_IMAGES[`bear_${c}`]
  });
});

// แถว 2: สวนดอกไม้ (7 สี)
["pink","sage","butter","sky","lavender","peach","mint"].forEach((c,i)=>{
  PRODUCTS.push({
    id: pid++,
    name: `สวนดอกไม้ ${COLORS[c].label}`,
    category: "floral",
    color: c,
    price: 289,
    tags: new Set(i===0||i===3 ? ["bestseller"] : []),
    models: [...MODELS],
    image: PRODUCT_IMAGES[`floral_${c}`]
  });
});

// แถว 3 (ส่วนแรก): คำน้อยๆ (5 สี) + ใสน่ารัก (2 ลาย)
const quoteSet = [
  {c:"cream",   text:"minimal"},
  {c:"sage",    text:"keep simple"},
  {c:"butter",  text:"be kind"},
  {c:"sky",     text:"day dream"},
  {c:"lavender",text:"little things"},
  {c:"mint",    text:"keep growing"},
  {c:"peach",   text:"stay sunny"}
];
quoteSet.forEach((q,i)=>{
  PRODUCTS.push({
    id: pid++,
    name: `คำน้อยๆ "${q.text}" ${COLORS[q.c].label}`,
    category: "quote",
    color: q.c,
    price: 249,
    tags: new Set(i===2 ? ["bestseller"] : []),
    models: [...MODELS],
    quoteText: q.text,
    image: PRODUCT_IMAGES[`quote_${q.c}`]
  });
});

const clearSet = [
  {text:"cute day",    motif:"bear",   image:"clear_cutebear"},
  {text:"good vibes",  motif:"floral", image:"clear_goodvibes"},
  {text:"party time",  motif:"balloon",image:"clear_balloon"},
  {text:"night sky",   motif:"star",   image:"clear_star"},
  {text:"sweet heart", motif:"heart",  image:"clear_heart"},
  {text:"sweet bloom", motif:"floral", image:"clear_bloom"},
  {text:"cuddle time", motif:"bear",   image:"clear_cuddle"}
];
clearSet.forEach((cl,i)=>{
  PRODUCTS.push({
    id: pid++,
    name: `ใสน่ารัก "${cl.text}"`,
    category: "clear",
    color: "clear",
    price: 299,
    tags: new Set(["new"]),
    models: [...MODELS],
    quoteText: cl.text,
    motif: cl.motif,
    image: PRODUCT_IMAGES[cl.image]
  });
});

// =========================================================================
// เซตพื้นฐานของสินค้าทั้งร้าน (ใช้ทั่วทั้งเว็บ)
// =========================================================================
const ALL_PRODUCT_IDS = new Set(PRODUCTS.map(p=>p.id));

// เซตของสินค้าตามหมวดหมู่ — Set ต่อ Category
function productSetByCategory(cat){
  return new Set(PRODUCTS.filter(p=>p.category===cat).map(p=>p.id));
}
function productSetByColor(color){
  return new Set(PRODUCTS.filter(p=>p.color===color).map(p=>p.id));
}
function productSetByTag(tag){
  return new Set(PRODUCTS.filter(p=>p.tags.has(tag)).map(p=>p.id));
}

// ---- Set operation helpers (Union / Intersection / Difference) ----
function setUnion(sets){
  const result = new Set();
  sets.forEach(s=> s.forEach(v=>result.add(v)));
  return result;
}
function setIntersection(a,b){
  return new Set([...a].filter(v=>b.has(v)));
}
function setDifference(a,b){
  return new Set([...a].filter(v=>!b.has(v)));
}

function productById(id){ return PRODUCTS.find(p=>p.id===id); }

/* =========================================================================
   ไอคอน SVG ของแต่ละลายเคส (วาดจาก path พื้นฐาน ไม่ใช้ไฟล์ภาพภายนอก)
   ========================================================================= */
// ใช้รูปจริงถ้าสินค้ามี p.image ไม่งั้น fallback ไปวาด SVG แบบเดิม
function caseThumb(p){
  if(p.image){
    return `<img src="${p.image}" alt="${p.name}" style="width:100%;height:100%;object-fit:contain;">`;
  }
  return caseSVG(p);
}
  function caseSVG(p, size=200){
  const hex = COLORS[p.color].hex;
  const isClear = p.category === "clear";
  const bodyFill = isClear ? "url(#glassGrad)" : hex;

  let overlay = "";
  if(p.category === "bear" || (isClear && p.motif==="bear")){
    const stroke = isClear ? "#C9A27A" : "#8A6A52";
    const face = isClear ? "none" : "#8A6A52";
    const faceFill = isClear ? "none" : "#F3E3D3";
    overlay = `
      <g transform="translate(100,118)">
        <circle cx="-28" cy="-46" r="15" fill="${isClear?'none':'#A9835F'}" stroke="${stroke}" stroke-width="${isClear?2:0}"/>
        <circle cx="28" cy="-46" r="15" fill="${isClear?'none':'#A9835F'}" stroke="${stroke}" stroke-width="${isClear?2:0}"/>
        <circle cx="0" cy="0" r="46" fill="${isClear?'none':'#B8926B'}" stroke="${stroke}" stroke-width="${isClear?2:0}"/>
        <circle cx="-16" cy="6" r="7" fill="${isClear?'none':'#F3E3D3'}" stroke="${isClear?stroke:'none'}" stroke-width="${isClear?1.4:0}"/>
        <circle cx="16" cy="6" r="7" fill="${isClear?'none':'#F3E3D3'}" stroke="${isClear?stroke:'none'}" stroke-width="${isClear?1.4:0}"/>
        <circle cx="-6" cy="4" r="2.6" fill="${stroke}"/>
        <circle cx="6" cy="4" r="2.6" fill="${stroke}"/>
        <ellipse cx="0" cy="16" rx="6" ry="4" fill="${stroke}"/>
      </g>`;
  } else if(p.category === "floral" || (isClear && p.motif==="floral")){
    const petal = isClear ? "#EBAFC0" : "#FFFFFF";
    const petalStroke = isClear ? "#D98CA6" : "none";
    const centers = [[60,70],[145,60],[95,120],[40,150],[150,150],[100,185]];
    overlay = centers.map(([x,y],idx)=>{
      const scale = idx%2===0 ? 1 : 0.8;
      return `
      <g transform="translate(${x},${y}) scale(${scale})">
        ${[0,72,144,216,288].map(a=>`<ellipse cx="0" cy="-8" rx="5.2" ry="8" fill="${petal}" stroke="${petalStroke}" stroke-width="1" transform="rotate(${a})"/>`).join("")}
        <circle r="3.4" fill="#E8C15A"/>
      </g>`;
    }).join("") + `<g stroke="#9DBB8B" stroke-width="2" opacity="${isClear?0.5:0.55}">
        <path d="M60 78 L55 100" fill="none"/><path d="M145 68 L150 92" fill="none"/>
        <path d="M40 158 L36 178" fill="none"/><path d="M150 158 L155 178" fill="none"/>
      </g>`;
  } else if(p.category === "quote"){
    overlay = `
      <g font-family="Baloo 2, sans-serif">
        <path d="M92 96 q8 -14 16 0 q4 8 -8 14 q-12 -6 -8 -14 Z" fill="#E79BAE"/>
        <text x="100" y="150" text-anchor="middle" font-size="15" font-weight="700" fill="#7A5C4E">${p.quoteText}</text>
      </g>`;
  }

  return `
  <svg viewBox="0 0 200 260" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <linearGradient id="glassGrad" x1="0" y1="0" x2="1" y2="1">
        <stop offset="0" stop-color="#ffffff" stop-opacity="0.9"/>
        <stop offset="1" stop-color="#f2ecdf" stop-opacity="0.55"/>
      </linearGradient>
    </defs>
    <rect x="14" y="6" width="172" height="248" rx="46" fill="${bodyFill}" stroke="${isClear?'#E3D6BE':'rgba(0,0,0,0.05)'}" stroke-width="${isClear?2:1}"/>
    <rect x="28" y="20" width="60" height="60" rx="18" fill="rgba(255,255,255,${isClear?0.35:0.28})"/>
    <circle cx="46" cy="38" r="11" fill="rgba(255,255,255,${isClear?0.5:0.4})"/>
    <circle cx="72" cy="38" r="11" fill="rgba(255,255,255,${isClear?0.5:0.4})"/>
    <circle cx="46" cy="64" r="7" fill="rgba(255,255,255,${isClear?0.5:0.4})"/>
    ${overlay}
  </svg>`;
}

/* =========================================================================
   NAVIGATION (Logic: if-else แสดง/ซ่อนหน้า)
   ========================================================================= */
function goToPage(name){
  document.querySelectorAll(".page").forEach(el=>{
    if(el.id === "page-"+name){ el.classList.add("active"); }
    else{ el.classList.remove("active"); }
  });
  document.querySelectorAll("nav.pages button").forEach(btn=>{
    if(btn.dataset.goto === name){ btn.classList.add("active"); } else { btn.classList.remove("active"); }
  });
  window.scrollTo({top:0,behavior:"smooth"});
  if(name === "products") renderProducts();
  if(name === "checkout") renderCheckout();
}
document.querySelectorAll("[data-goto]").forEach(el=>{
  el.addEventListener("click", ()=>{ 
    if(el.dataset.scrollCat){
    pendingCategoryFilter = el.dataset.scrollCat;
    }
    goToPage(el.dataset.goto);
  });
});

/* =========================================================================
   CART (เก็บใน localStorage, ใช้ Set เพื่อกันรายการซ้ำ)
   โครงสร้างที่เก็บจริง: array ของ {key, id, model, qty}
   แต่ "key" (id+model) ถูกตรวจสอบผ่าน Set เพื่อไม่ให้ซ้ำ
   ========================================================================= */
function loadCart(){
  try{
    const raw = localStorage.getItem("lsc_cart");
    return raw ? JSON.parse(raw) : [];
  }catch(e){ return []; }
}
function saveCart(cart){
  localStorage.setItem("lsc_cart", JSON.stringify(cart));
  updateNavCartCount();
}
let cart = loadCart();

function cartKeySet(){
  return new Set(cart.map(item=>item.key));
}

function addToCart(productId, model, qty=1){
  const key = productId + "::" + model;
  const existingKeys = cartKeySet();
  if(existingKeys.has(key)){
    // มีอยู่แล้ว -> เพิ่มจำนวน (if-else)
    const item = cart.find(i=>i.key===key);
    item.qty += qty;
  } else {
    cart.push({key, id: productId, model, qty});
  }
  saveCart(cart);
  showToast("เพิ่มลงตะกร้าแล้ว 🧺");
}
function removeFromCart(key){
  cart = cart.filter(i=>i.key!==key);
  saveCart(cart);
  renderCheckout();
}
function changeQty(key, delta){
  const item = cart.find(i=>i.key===key);
  if(!item) return;
  item.qty += delta;
  if(item.qty <= 0){
    removeFromCart(key);
  } else {
    saveCart(cart);
    renderCheckout();
  }
}
function updateNavCartCount(){
  const totalQty = cart.reduce((sum,i)=> sum + i.qty, 0);
  document.getElementById("navCartCount").textContent = totalQty;
}

function showToast(msg){
  const t = document.getElementById("toast");
  t.textContent = msg;
  t.classList.add("show");
  clearTimeout(showToast._timer);
  showToast._timer = setTimeout(()=>t.classList.remove("show"), 1800);
}

/* =========================================================================
   PAGE 1: HOME
   ========================================================================= */
function renderHome(){
  // ---- แสดงรูปหน้าร้านจริง ----
  document.getElementById("storefrontImg").src = STOREFRONT_IMG;
  
  // ---- Logic: ลูกค้าใหม่ / ลูกค้าเก่า (if-else + localStorage) ----
  const banner = document.getElementById("welcomeBanner");
  const visited = localStorage.getItem("lsc_visited");
  if(!visited){
    banner.textContent = "🎉 ยินดีต้อนรับลูกค้าใหม่! รับส่วนลด 10% เมื่อกรอกโค้ด SUGAR10 ตอนเช็คเอาต์";
    localStorage.setItem("lsc_visited","1");
  } else {
    banner.textContent = "🧸 ยินดีต้อนรับกลับมาอีกครั้งนะคะ ลองดูลายใหม่ ๆ ของเราได้เลย";
  }

  // ---- Category cards: ใช้ Set.size นับจำนวนสินค้าในแต่ละหมวด ----
  const catGrid = document.getElementById("catGrid");
  catGrid.innerHTML = Object.entries(CATEGORIES).map(([key,cat])=>{
    const count = productSetByCategory(key).size; // <-- Set.size
    return `
    <div class="cat-card" data-goto="products" data-precat="${key}">
      <div class="cat-swatch" style="background:${key==='clear'?'linear-gradient(135deg,#fff,#e8e0cf)':'var(--'+ (key==='bear'?'peach':key==='floral'?'pink':'sky') +')'}">${cat.icon}</div>
      <b>${cat.label}</b>
      <span>${cat.desc}</span>
      <span class="pill">${count} ลาย</span>
    </div>`;
  }).join("");
  catGrid.querySelectorAll(".cat-card").forEach(el=>{
    el.addEventListener("click", ()=>{
      pendingCategoryFilter = el.dataset.precat;
      goToPage("products");
    });
  });

  // ---- Featured: เซตของสินค้าที่ติดแท็ก bestseller ----
  const bestsellerIds = productSetByTag("bestseller"); // Set
  const featGrid = document.getElementById("featGrid");
  featGrid.innerHTML = [...bestsellerIds].slice(0,4).map(id=>{
    const p = productById(id);
    return productCardHTML(p, true);
  }).join("");
  attachAddToCartHandlers(featGrid);
}

function productCardHTML(p, compact=false){
  const badge = p.tags.has("bestseller") ? '<span class="badge">ขายดี</span>' : (p.tags.has("new") ? '<span class="badge" style="background:var(--ink-soft)">ลายใหม่</span>' : "");
  return `
  <div class="prod-card" data-id="${p.id}">
    <div class="prod-thumb" style="background:var(--cream-deep);">
      ${badge}
      ${caseThumb(p)}
    </div>
    <div class="prod-body">
      <div class="prod-name">${p.name}</div>
      <div class="prod-meta">${CATEGORIES[p.category].label} · รองรับทุกรุ่น iPhone 11–17</div>
      <div class="model-select-row">
        <select>${p.models.map(m=>`<option value="${m}">${m}</option>`).join("")}</select>
      </div>
      <div class="prod-row">
        <span class="prod-price">฿${p.price}</span>
        <button class="mini-btn add-to-cart-btn" data-id="${p.id}">หยิบใส่ตะกร้า</button>
      </div>
    </div>
  </div>`;
}
function attachAddToCartHandlers(scopeEl){
  scopeEl.querySelectorAll(".add-to-cart-btn").forEach(btn=>{
    btn.addEventListener("click", ()=>{
      const id = Number(btn.dataset.id);
      const modelSelect = btn.closest(".prod-card")?.querySelector(".model-select-row select");
      const model = modelSelect ? modelSelect.value : MODELS[6]; // fallback เผื่อไม่เจอ dropdown จริงๆ (ปกติจะไม่เกิด) — MODELS[6] = "iPhone 13"
      addToCart(id, model, 1);
    });
  });
}
  
  // ---- แสดงรายละเอียดสินค้าใน modal ----
function openProductModal(id){
  const p = productById(id);
  if(!p) return;
  document.getElementById("modalImgWrap").innerHTML = caseThumb(p);
  document.getElementById("modalName").textContent = p.name;
  document.getElementById("modalMeta").textContent = `${CATEGORIES[p.category].label} · ${COLORS[p.color].label}`;
  document.getElementById("modalPrice").textContent = `฿${p.price}`;
  document.getElementById("modalDesc").textContent = p.quoteText
    ? `ข้อความบนเคส: "${p.quoteText}"`
    : `ลายน่ารักโทนพาสเทล รองรับ iPhone ${p.models.length} รุ่น`;
  document.getElementById("modalModelSelect").innerHTML =
    p.models.map(m=>`<option value="${m}">${m}</option>`).join("");
  document.getElementById("modalAddBtn").dataset.id = p.id;
  document.getElementById("productModal").classList.add("show");
}
function closeProductModal(){
  document.getElementById("productModal").classList.remove("show");
}

/* =========================================================================
   PAGE 2: PRODUCTS — Set operations: Union / Intersection / Difference
   ========================================================================= */
let pendingCategoryFilter = null;

function buildFilterControls(){
  const catWrap = document.getElementById("catFilters");
  catWrap.innerHTML = Object.entries(CATEGORIES).map(([key,cat])=>`
    <label class="chk-row">
      <input type="checkbox" class="cat-chk" value="${key}">
      ${cat.icon} ${cat.label}
    </label>`).join("");

  const colorWrap = document.getElementById("colorFilters");
  colorWrap.innerHTML = Object.entries(COLORS).filter(([k])=>k!=='clear').map(([key,c])=>`
    <label class="chk-row">
      <input type="checkbox" class="color-chk" value="${key}">
      <span style="width:14px;height:14px;border-radius:50%;background:${c.hex};display:inline-block;border:1px solid var(--line);"></span>
      ${c.label}
    </label>`).join("");

  const modelSelect = document.getElementById("modelFilter");
  MODELS.forEach(m=>{
    const opt = document.createElement("option");
    opt.value = m; opt.textContent = m;
    modelSelect.appendChild(opt);
  });

  document.querySelectorAll(".cat-chk,.color-chk").forEach(el=>el.addEventListener("change", renderProducts));
  document.getElementById("modelFilter").addEventListener("change", renderProducts);
  document.getElementById("excludeClear").addEventListener("change", renderProducts);
  document.getElementById("searchInput").addEventListener("input", renderProducts);
  document.getElementById("clearFiltersBtn").addEventListener("click", ()=>{
    document.querySelectorAll(".cat-chk,.color-chk").forEach(el=>el.checked=false);
    document.getElementById("modelFilter").value = "";
    document.getElementById("excludeClear").checked = false;
    document.getElementById("searchInput").value = "";
    renderProducts();
  });
}

function renderProducts(){
  // ถ้ามาจาก Home ด้วยหมวดที่เลือกไว้ล่วงหน้า
  if(pendingCategoryFilter){
    document.querySelectorAll(".cat-chk").forEach(chk=>{
      chk.checked = (chk.value === pendingCategoryFilter);
    });
    pendingCategoryFilter = null;
  }

  const checkedCats = [...document.querySelectorAll(".cat-chk:checked")].map(c=>c.value);
  const checkedColors = [...document.querySelectorAll(".color-chk:checked")].map(c=>c.value);
  const model = document.getElementById("modelFilter").value;
  const excludeClear = document.getElementById("excludeClear").checked;
  const query = document.getElementById("searchInput").value.trim().toLowerCase();

  // ---- STEP 1: Union ของหมวดที่เลือก (ถ้าไม่เลือกเลย = สินค้าทั้งหมด) ----
  let categoryResult = checkedCats.length
    ? setUnion(checkedCats.map(productSetByCategory))
    : new Set(ALL_PRODUCT_IDS);

  // ---- STEP 2: Union ของสีที่เลือก แล้ว Intersection กับผลลัพธ์ข้อ 1 ----
  let colorUnion = checkedColors.length
    ? setUnion(checkedColors.map(productSetByColor))
    : new Set(ALL_PRODUCT_IDS);
  let result = setIntersection(categoryResult, colorUnion);

  // ---- STEP 3: Difference ตัดลายเคสใสออก ถ้าติ๊ก "ไม่เอาเคสใส" ----
  if(excludeClear){
    result = setDifference(result, productSetByCategory("clear"));
  }

  // ---- STEP 4: filter ด้วยคำค้นหา (includes) และรุ่นที่รองรับ (some/has) ----
  let finalList = [...result]
    .map(productById)
    .filter(p=> query ? p.name.toLowerCase().includes(query) : true)
    .filter(p=> model ? p.models.some(m=>m===model) : true);

  // แสดงสูตรที่ใช้จริง ณ ตอนนี้ (ให้เห็นภาพ discrete math)
  const formulaEl = document.getElementById("filterFormula");
  formulaEl.textContent =
    `หมวด(${checkedCats.length||'ทั้งหมด'}) ∪ ... ∩ สี(${checkedColors.length||'ทั้งหมด'})`
    + (excludeClear ? "  −  เคสใส" : "");

  document.getElementById("resultsCount").textContent = `พบ ${finalList.length} ลาย จากทั้งหมด ${PRODUCTS.length} ลาย`;

  const grid = document.getElementById("productGrid");
  if(finalList.length === 0){
    grid.innerHTML = `<div class="empty-state">ไม่พบสินค้าตามเงื่อนไขนี้ ลองปรับตัวกรองดูนะคะ 🐻</div>`;
    return;
  }
  grid.innerHTML = finalList.map(p=>{
    return `
    <div class="prod-card" data-id="${p.id}">
      <div class="prod-thumb" style="background:var(--cream-deep);">
        ${p.tags.has("bestseller") ? '<span class="badge">ขายดี</span>' : (p.tags.has("new") ? '<span class="badge" style="background:var(--ink-soft)">ลายใหม่</span>' : "")}
        ${caseThumb(p)}
      </div>
      <div class="prod-body">
        <div class="prod-name">${p.name}</div>
        <div class="prod-meta">${CATEGORIES[p.category].label} · ${COLORS[p.color].label}</div>
        <div class="model-select-row">
          <select>${p.models.map(m=>`<option value="${m}" ${model===m?'selected':''}>${m}</option>`).join("")}</select>
        </div>
        <div class="prod-row">
          <span class="prod-price">฿${p.price}</span>
          <button class="mini-btn add-to-cart-btn" data-id="${p.id}">หยิบใส่ตะกร้า</button>
        </div>
      </div>
    </div>`;
  }).join("");
  attachAddToCartHandlers(grid);
}

/* =========================================================================
   PAGE 3: CHECKOUT — reduce() + if-else logic โปรโมชั่น + Set difference
   ========================================================================= */
function renderCheckout(){
  const listEl = document.getElementById("cartList");
  const crossWrap = document.getElementById("crossSellWrap");

  if(cart.length === 0){
    listEl.innerHTML = `<div class="empty-cart">ตะกร้ายังว่างอยู่เลย 🧸<br><br><button class="btn-primary" data-goto="products">ไปเลือกเคสกันเถอะ</button></div>`;
    listEl.querySelector("[data-goto]").addEventListener("click", ()=>goToPage("products"));
    crossWrap.style.display = "none";
    renderSummary([]);
    return;
  }

  listEl.innerHTML = cart.map(item=>{
    const p = productById(item.id);
    const lineTotal = lineItemPrice(p, item.model) * item.qty;
    return `
    <div class="cart-item">
    <div class="cart-thumb">${caseThumb(p)}</div>
      <div class="cart-info">
        <b>${p.name}</b>
        <span>${item.model}</span>
      </div>
      <div class="qty-ctrl">
        <button data-act="minus" data-key="${item.key}">−</button>
        <span>${item.qty}</span>
        <button data-act="plus" data-key="${item.key}">+</button>
      </div>
      <div class="cart-price">฿${lineTotal}</div>
      <button class="remove-btn" data-remove="${item.key}">ลบ</button>
    </div>`;
  }).join("");

  listEl.querySelectorAll("[data-act]").forEach(btn=>{
    btn.addEventListener("click", ()=> changeQty(btn.dataset.key, btn.dataset.act==="plus"?1:-1));
  });
  listEl.querySelectorAll("[data-remove]").forEach(btn=>{
    btn.addEventListener("click", ()=> removeFromCart(btn.dataset.remove));
  });

  renderCrossSell();
  renderSummary(cart);
}

// ราคาต่อชิ้น: ตรรกะ if-else เพิ่มราคาถ้าเป็นรุ่น Pro Max
function lineItemPrice(p, model){
  let price = p.price;
  if(model.includes("Pro Max")){
    price += 30;
  } else if(model.includes("Pro")){
    price += 15;
  } else {
    price += 0;
  }
  return price;
}

function renderCrossSell(){
  // เซตสินค้าที่อยู่ในตะกร้า
  const cartProductIds = new Set(cart.map(i=>i.id));
  // เซตหมวดที่มีอยู่ในตะกร้า
  const cartCategories = new Set(cart.map(i=>productById(i.id).category));
  // เซตสินค้าที่ "อยู่ในหมวดเดียวกับตะกร้า" 
  const relatedByCategory = setUnion([...cartCategories].map(productSetByCategory));
  // Difference: แนะนำเฉพาะสินค้าที่ "เกี่ยวข้อง" แต่ "ยังไม่อยู่ในตะกร้า"
  const suggestions = setDifference(relatedByCategory, cartProductIds);

  const wrap = document.getElementById("crossSellWrap");
  const grid = document.getElementById("crossSellGrid");
  if(suggestions.size === 0){
    wrap.style.display = "none";
    return;
  }
  wrap.style.display = "block";
  grid.innerHTML = [...suggestions].slice(0,4).map(id=>productCardHTML(productById(id))).join("");
  attachAddToCartHandlers(grid);
}

let appliedCoupon = null;

function renderSummary(cartItems){
  const subtotal = cartItems.reduce((sum,item)=>{
    const p = productById(item.id);
    return sum + lineItemPrice(p, item.model) * item.qty;
  }, 0);

  const distinctCategories = new Set(cartItems.map(i=>productById(i.id).category));
  const totalQty = cartItems.reduce((s,i)=>s+i.qty,0);

  // ---- Logic โปรโมชั่น (if-else, &&, ||) ----
  let discount = 0;
  const messages = [];

  if(subtotal >= 1500){
    discount += Math.round(subtotal * 0.15);
    messages.push({ok:true, text:"ลด 15% เมื่อซื้อครบ ฿1,500"});
  } else if(subtotal >= 900){
    discount += Math.round(subtotal * 0.10);
    messages.push({ok:true, text:"ลด 10% เมื่อซื้อครบ ฿900"});
  } else {
    messages.push({ok:false, text:"ซื้อเพิ่มให้ครบ ฿900 เพื่อรับส่วนลด 10%"});
  }

  if(distinctCategories.size >= 3 && totalQty >= 3){
    discount += 50;
    messages.push({ok:true, text:"ลดเพิ่ม ฿50 เมื่อเลือกลายต่างหมวดกัน 3 แบบขึ้นไป"});
  }

  if(appliedCoupon === "SUGAR10"){
    discount += Math.round(subtotal * 0.10);
    messages.push({ok:true, text:'ใช้โค้ด "SUGAR10" ลดเพิ่ม 10%'});
  }

  let shipping = 0;
  if(subtotal === 0){
    shipping = 0;
  } else if(subtotal >= 700 || appliedCoupon === "FREESHIP"){
    shipping = 0;
    messages.push({ok:true, text:"จัดส่งฟรี"});
  } else {
    shipping = 50;
  }

  const total = Math.max(subtotal - discount, 0) + shipping;

  document.getElementById("sumSubtotal").textContent = `฿${subtotal}`;
  document.getElementById("sumDiscount").textContent = `-฿${discount}`;
  document.getElementById("sumShipping").textContent = shipping===0 ? "ฟรี" : `฿${shipping}`;
  document.getElementById("sumTotal").textContent = `฿${total}`;

  document.getElementById("promoMessages").innerHTML = messages.map(m=>
    `<div class="promo-msg ${m.ok?'ok':'no'}">${m.ok?'✓':'ℹ'} ${m.text}</div>`
  ).join("");
}

document.getElementById("applyCouponBtn").addEventListener("click", ()=>{
  const code = document.getElementById("couponInput").value.trim().toUpperCase();
  if(code === "SUGAR10" || code === "FREESHIP"){
    appliedCoupon = code;
    showToast(`ใช้โค้ด ${code} สำเร็จ 🎁`);
  } else if(code === ""){
    showToast("กรุณากรอกโค้ดก่อนนะคะ");
  } else {
    appliedCoupon = null;
    showToast("โค้ดไม่ถูกต้อง ลองใหม่อีกครั้ง");
  }
  renderSummary(cart);
});

document.getElementById("placeOrderBtn").addEventListener("click", ()=>{
  if(cart.length === 0){
    showToast("ตะกร้ายังว่างอยู่นะคะ 🧸");
    return;
  }
  showToast("สั่งซื้อสำเร็จ! ขอบคุณที่อุดหนุน Little Sugar Case 💌");
  cart = [];
  appliedCoupon = null;
  saveCart(cart);
  renderCheckout();
});

/* =========================================================================
   INIT
   ========================================================================= */
  
  // ---- คลิกที่การ์ดสินค้า (ไม่ใช่ปุ่ม/dropdown) เพื่อเปิด modal รายละเอียด ----
document.addEventListener("click", (e)=>{
  const card = e.target.closest(".prod-card");
  if(!card) return;
  if(e.target.closest("button") || e.target.closest("select")) return;
  openProductModal(Number(card.dataset.id));
});

// ---- ปุ่มปิด modal / คลิกพื้นหลังเพื่อปิด ----
document.getElementById("modalCloseBtn").addEventListener("click", closeProductModal);
document.getElementById("productModal").addEventListener("click", (e)=>{
  if(e.target.id === "productModal") closeProductModal();
});

// ---- ปุ่มหยิบใส่ตะกร้าจากใน modal ----
document.getElementById("modalAddBtn").addEventListener("click", ()=>{
  const id = Number(document.getElementById("modalAddBtn").dataset.id);
  const model = document.getElementById("modalModelSelect").value;
  addToCart(id, model, 1);
  closeProductModal();
});
  
buildFilterControls();
renderHome();
updateNavCartCount();
</script>
</body>
</html>
