<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>MAT Bakeshop</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet"/>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Cormorant+Garamond:wght@300;400;500;600&family=Dancing+Script:wght@600;700&display=swap" rel="stylesheet"/>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"/>
  <style>
    :root {
      --navy:      #0a1628;
      --deep-blue: #0d2045;
      --mid-blue:  #1a3a6b;
      --gold:      #c9a84c;
      --gold-light:#e8c96d;
      --gold-pale: #f5e6b8;
      --cream:     #fdf8ee;
      --white:     #ffffff;
    }
    *,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
    html{scroll-behavior:smooth}
    body{font-family:'Cormorant Garamond',serif;background:var(--navy);color:var(--cream);overflow-x:hidden}
    ::-webkit-scrollbar{width:8px}
    ::-webkit-scrollbar-track{background:var(--navy)}
    ::-webkit-scrollbar-thumb{background:var(--gold);border-radius:4px}
    .page{display:none}
    .page.active{display:block}
    .bow-float{position:fixed;font-size:1.6rem;opacity:0.12;pointer-events:none;animation:floatBow 6s ease-in-out infinite;z-index:0}
    .bow-float:nth-child(1){top:8%;left:1%;animation-delay:0s;font-size:2.2rem}
    .bow-float:nth-child(2){top:22%;right:2%;animation-delay:1.5s;font-size:1.5rem}
    .bow-float:nth-child(3){top:55%;left:0.5%;animation-delay:3s;font-size:1.9rem}
    .bow-float:nth-child(4){top:78%;right:1.5%;animation-delay:0.8s;font-size:1.2rem}
    .bow-float:nth-child(5){top:42%;left:2%;animation-delay:2.2s;font-size:1rem}
    @keyframes floatBow{0%,100%{transform:translateY(0) rotate(-6deg)}50%{transform:translateY(-20px) rotate(6deg)}}
    .navbar{background:linear-gradient(135deg,var(--navy),var(--deep-blue));border-bottom:2px solid var(--gold);padding:0.9rem 0;position:sticky;top:0;z-index:1000;box-shadow:0 4px 30px rgba(201,168,76,0.2)}
    .navbar-brand{font-family:'Dancing Script',cursive;font-size:2rem;color:var(--gold)!important;text-shadow:0 0 20px rgba(201,168,76,0.5);cursor:pointer}
    .nav-link{font-family:'Cormorant Garamond',serif;font-size:1.05rem;font-weight:600;color:var(--gold-pale)!important;letter-spacing:1.5px;text-transform:uppercase;padding:0.4rem 1rem!important;transition:color 0.3s;position:relative;cursor:pointer;background:none;border:none}
    .nav-link::after{content:'';position:absolute;bottom:0;left:50%;width:0;height:2px;background:var(--gold);transition:all 0.3s;transform:translateX(-50%)}
    .nav-link:hover{color:var(--gold)!important}
    .nav-link:hover::after{width:70%}
    .nav-link.active{color:var(--gold)!important}
    .nav-link.active::after{width:70%}
    .navbar-toggler{border-color:var(--gold)}
    .navbar-toggler-icon{background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'%3e%3cpath stroke='rgba(201,168,76,1)' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e")}
    .cart-icon{position:relative;cursor:pointer;color:var(--gold-light);font-size:1.3rem;transition:transform 0.2s}
    .cart-icon:hover{transform:scale(1.15)}
    .cart-badge{position:absolute;top:-8px;right:-10px;background:var(--gold);color:var(--navy);border-radius:50%;width:20px;height:20px;font-size:0.72rem;font-weight:700;display:none;align-items:center;justify-content:center}
    .btn-gold{font-family:'Cormorant Garamond',serif;font-size:1rem;font-weight:600;letter-spacing:3px;text-transform:uppercase;color:var(--navy);background:linear-gradient(135deg,var(--gold-light),var(--gold));border:none;padding:0.85rem 2.5rem;cursor:pointer;transition:all 0.3s;text-decoration:none;display:inline-block}
    .btn-gold:hover{transform:translateY(-3px);box-shadow:0 10px 30px rgba(201,168,76,0.4);color:var(--navy)}
    .btn-outline-gold{font-family:'Cormorant Garamond',serif;font-size:1rem;font-weight:600;letter-spacing:3px;text-transform:uppercase;color:var(--gold);background:transparent;border:1.5px solid var(--gold);padding:0.85rem 2.5rem;cursor:pointer;transition:all 0.3s;text-decoration:none;display:inline-block}
    .btn-outline-gold:hover{background:var(--gold);color:var(--navy);transform:translateY(-3px)}
    .section-title{font-family:'Dancing Script',cursive;font-size:clamp(2.4rem,5vw,3.8rem);color:var(--gold);text-align:center;margin-bottom:0.4rem}
    .section-sub{font-size:1.05rem;color:var(--gold-pale);text-align:center;letter-spacing:3px;text-transform:uppercase;margin-bottom:0.6rem;font-style:italic}
    .gold-divider{display:flex;align-items:center;justify-content:center;gap:0.8rem;margin-bottom:3rem}
    .gdl{width:100px;height:1px}
    .gdl.l{background:linear-gradient(90deg,transparent,var(--gold))}
    .gdl.r{background:linear-gradient(90deg,var(--gold),transparent)}
    .gold-divider i{color:var(--gold);font-size:1.1rem}
    .hero{min-height:92vh;background:linear-gradient(160deg,rgba(10,22,40,0.78) 0%,rgba(13,32,69,0.65) 50%,rgba(10,22,40,0.85) 100%),url('https://images.unsplash.com/photo-1578985545062-69928b1d9587?w=1600&q=80') center/cover no-repeat;display:flex;align-items:center;justify-content:center;text-align:center;position:relative;overflow:hidden;padding:4rem 1rem}
    .hero::before{content:'✦ ✧ ✦ ✧ ✦ ✧ ✦ ✧ ✦ ✧ ✦';position:absolute;top:10%;left:50%;transform:translateX(-50%);color:var(--gold);font-size:0.85rem;opacity:0.3;letter-spacing:8px;white-space:nowrap}
    .hero::after{content:'✦ ✧ ✦ ✧ ✦ ✧ ✦ ✧ ✦ ✧ ✦';position:absolute;bottom:10%;left:50%;transform:translateX(-50%);color:var(--gold);font-size:0.85rem;opacity:0.3;letter-spacing:8px;white-space:nowrap}
    .hero-bow-l{position:absolute;left:6%;top:38%;font-size:4rem;opacity:0.45;animation:floatBow 5s ease-in-out infinite}
    .hero-bow-r{position:absolute;right:6%;top:38%;font-size:4rem;opacity:0.45;animation:floatBow 5s ease-in-out infinite 1s}
    .hero-ring{position:absolute;border-radius:50%;border:1px solid rgba(201,168,76,0.12);top:50%;left:50%;transform:translate(-50%,-50%)}
    .hero-ring-1{width:640px;height:640px}
    .hero-ring-2{width:450px;height:450px;border-color:rgba(201,168,76,0.08)}
    .hero-tag{display:inline-block;font-size:0.82rem;letter-spacing:5px;text-transform:uppercase;color:var(--gold);border:1px solid rgba(201,168,76,0.4);padding:0.4rem 1.6rem;margin-bottom:1.5rem;animation:fadeDown 0.8s ease both}
    .hero-title{font-family:'Dancing Script',cursive;font-size:clamp(3.5rem,8vw,7rem);color:var(--white);line-height:1.05;animation:fadeDown 0.9s ease 0.1s both}
    .hero-title .gold-text{color:var(--gold);display:block;text-shadow:0 0 40px rgba(201,168,76,0.45)}
    .hero-sub{font-size:clamp(1rem,2.5vw,1.4rem);color:var(--gold-pale);font-style:italic;margin:1rem 0 2rem;letter-spacing:1px;animation:fadeDown 1s ease 0.2s both}
    .hero-divider{display:flex;align-items:center;justify-content:center;gap:1rem;margin:0.5rem 0 2.5rem;animation:fadeDown 1.1s ease 0.3s both}
    .hero-divider span{color:var(--gold);font-size:1.2rem}
    .hdl{width:80px;height:1px;background:linear-gradient(90deg,transparent,var(--gold),transparent)}
    @keyframes fadeDown{from{opacity:0;transform:translateY(-25px)}to{opacity:1;transform:translateY(0)}}
    .gallery-strip{display:flex;height:260px;overflow:hidden;position:relative}
    .gallery-strip::before,.gallery-strip::after{content:'';position:absolute;top:0;bottom:0;width:120px;z-index:2;pointer-events:none}
    .gallery-strip::before{left:0;background:linear-gradient(90deg,var(--navy),transparent)}
    .gallery-strip::after{right:0;background:linear-gradient(-90deg,var(--navy),transparent)}
    .gallery-track{display:flex;gap:6px;animation:scrollGallery 40s linear infinite;width:max-content}
    .gallery-track:hover{animation-play-state:paused}
    .gallery-track img{height:260px;width:220px;object-fit:cover;flex-shrink:0;filter:brightness(0.75) sepia(0.1);transition:filter 0.4s,transform 0.4s}
    .gallery-track img:hover{filter:brightness(1) sepia(0);transform:scale(1.04);z-index:1}
    @keyframes scrollGallery{0%{transform:translateX(0)}100%{transform:translateX(-50%)}}
    .features-strip{background:linear-gradient(135deg,var(--mid-blue),var(--deep-blue));border-top:1px solid rgba(201,168,76,0.3);border-bottom:1px solid rgba(201,168,76,0.3);padding:2.5rem 0}
    .feature-item{text-align:center;padding:1rem}
    .feature-item i{font-size:2rem;color:var(--gold);margin-bottom:0.7rem;display:block}
    .feature-item h6{font-family:'Playfair Display',serif;font-size:1rem;color:var(--white);margin-bottom:0.3rem}
    .feature-item p{font-size:0.88rem;color:var(--gold-pale);margin:0;font-style:italic}
    .testi-section{padding:5rem 0;background:var(--navy);position:relative}
    .testi-section::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,var(--gold),transparent)}
    .testi-card{background:linear-gradient(135deg,var(--deep-blue),rgba(26,58,107,0.4));border:1px solid rgba(201,168,76,0.2);padding:2rem;position:relative;transition:all 0.3s;height:100%}
    .testi-card:hover{border-color:rgba(201,168,76,0.5);transform:translateY(-5px)}
    .quote-mark{font-family:'Playfair Display',serif;font-size:5rem;color:var(--gold);opacity:0.2;line-height:1;position:absolute;top:0.5rem;left:1.2rem}
    .testi-text{font-style:italic;color:var(--gold-pale);line-height:1.7;font-size:1rem;margin-bottom:1rem;padding-top:2rem}
    .testi-author{font-family:'Playfair Display',serif;color:var(--gold);font-size:0.95rem}
    .stars{color:var(--gold);font-size:0.9rem;margin-bottom:0.5rem}
    .menu-section{padding:5rem 0;background:var(--navy);position:relative}
    .menu-section::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,var(--gold),transparent)}
    .cat-tabs{display:flex;justify-content:center;flex-wrap:wrap;gap:0.8rem;margin-bottom:3rem}
    .cat-tab{font-family:'Cormorant Garamond',serif;font-size:0.9rem;font-weight:600;letter-spacing:2px;text-transform:uppercase;color:var(--gold-pale);background:transparent;border:1px solid rgba(201,168,76,0.35);padding:0.6rem 1.6rem;cursor:pointer;transition:all 0.3s}
    .cat-tab:hover,.cat-tab.active{background:var(--gold);color:var(--navy);border-color:var(--gold)}
    .product-card{background:linear-gradient(160deg,var(--deep-blue) 0%,rgba(10,22,40,0.95) 100%);border:1px solid rgba(201,168,76,0.2);overflow:hidden;transition:all 0.35s;height:100%;display:flex;flex-direction:column;position:relative}
    .product-card::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--gold),var(--gold-light),var(--gold));transform:scaleX(0);transition:transform 0.4s;z-index:2}
    .product-card:hover{transform:translateY(-8px);border-color:rgba(201,168,76,0.5);box-shadow:0 20px 50px rgba(0,0,0,0.5),0 0 30px rgba(201,168,76,0.1)}
    .product-card:hover::before{transform:scaleX(1)}
    .card-photo-wrap{overflow:hidden;position:relative;height:200px;flex-shrink:0}
    .card-photo-wrap::after{content:'';position:absolute;bottom:0;left:0;right:0;height:60px;background:linear-gradient(transparent,var(--deep-blue));pointer-events:none}
    .card-photo{width:100%;height:200px;object-fit:cover;display:block;transition:transform 0.5s ease,filter 0.4s}
    .product-card:hover .card-photo{transform:scale(1.07);filter:brightness(1.1) saturate(1.1)}
    .card-bow{position:absolute;top:10px;right:10px;font-size:1.4rem;opacity:0.75;z-index:3;text-shadow:0 2px 8px rgba(0,0,0,0.7);pointer-events:none}
    .card-body-inner{padding:1rem 1.4rem 1.4rem;flex:1;display:flex;flex-direction:column}
    .product-name{font-family:'Playfair Display',serif;font-size:1.15rem;color:var(--white);margin-bottom:0.4rem}
    .product-desc{font-size:0.88rem;color:var(--gold-pale);opacity:0.8;flex:1;font-style:italic;line-height:1.5;margin-bottom:0.8rem}
    .product-size{font-size:0.78rem;color:var(--gold);letter-spacing:1px;text-transform:uppercase;margin-bottom:0.5rem}
    .product-footer{display:flex;align-items:center;justify-content:space-between;margin-top:auto;padding-top:0.8rem;border-top:1px solid rgba(201,168,76,0.15)}
    .product-price{font-family:'Playfair Display',serif;font-size:1.2rem;font-weight:700;color:var(--gold)}
    .add-btn{background:transparent;border:1px solid var(--gold);color:var(--gold);width:34px;height:34px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:1.2rem;cursor:pointer;transition:all 0.25s;flex-shrink:0}
    .add-btn:hover{background:var(--gold);color:var(--navy);transform:rotate(90deg)}
    .about-section{padding:5rem 0;background:linear-gradient(160deg,var(--deep-blue),var(--navy));position:relative;overflow:hidden}
    .about-section::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,var(--gold),transparent)}
    .about-card{background:rgba(201,168,76,0.05);border:1px solid rgba(201,168,76,0.2);padding:2.5rem;position:relative}
    .about-card::before{content:'🎀';position:absolute;top:-1rem;left:50%;transform:translateX(-50%);font-size:2rem}
    .about-img-grid{display:grid;grid-template-columns:1fr 1fr;grid-template-rows:190px 190px;gap:6px}
    .about-img-grid img{width:100%;height:100%;object-fit:cover;transition:filter 0.4s,transform 0.4s}
    .about-img-grid img:hover{filter:brightness(1.05);transform:scale(1.02)}
    .about-img-grid img:first-child{grid-row:span 2}
    .about-stat{text-align:center;padding:1.5rem;border:1px solid rgba(201,168,76,0.2);background:rgba(201,168,76,0.04);transition:all 0.3s}
    .about-stat:hover{background:rgba(201,168,76,0.1);border-color:var(--gold)}
    .about-stat .number{font-family:'Dancing Script',cursive;font-size:3rem;color:var(--gold);line-height:1;display:block}
    .about-stat .label{font-size:0.85rem;letter-spacing:2px;text-transform:uppercase;color:var(--gold-pale)}
    .video-section{padding:5rem 0;background:linear-gradient(160deg,var(--deep-blue),var(--navy));position:relative}
    .video-section::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,var(--gold),transparent)}
    .video-wrapper{position:relative;border:2px solid rgba(201,168,76,0.4);box-shadow:0 0 60px rgba(201,168,76,0.1),0 30px 80px rgba(0,0,0,0.5);overflow:hidden}
    .video-ratio{position:relative;padding-bottom:56.25%;height:0;overflow:hidden}
    .video-ratio iframe{position:absolute;top:0;left:0;width:100%;height:100%;border:0}
    .vid-label{font-family:'Playfair Display',serif;color:var(--gold);margin-bottom:0.8rem;font-size:1.1rem}
    .contact-section{padding:5rem 0;background:var(--navy)}
    .form-control-gold{background:rgba(10,22,40,0.8);border:1px solid rgba(201,168,76,0.3);color:var(--cream);padding:0.85rem 1.2rem;border-radius:0;font-family:'Cormorant Garamond',serif;font-size:1rem;transition:border-color 0.3s;width:100%}
    .form-control-gold:focus{background:rgba(10,22,40,0.9);border-color:var(--gold);color:var(--cream);box-shadow:0 0 0 3px rgba(201,168,76,0.1);outline:none}
    .form-control-gold::placeholder{color:rgba(245,230,184,0.4)}
    .form-label-gold{font-size:0.88rem;letter-spacing:2px;text-transform:uppercase;color:var(--gold-pale);margin-bottom:0.4rem;display:block}
    .contact-info-box{background:rgba(201,168,76,0.05);border:1px solid rgba(201,168,76,0.2);padding:2rem}
    .contact-info-item{display:flex;gap:1rem;margin-bottom:1.5rem;align-items:flex-start}
    .contact-info-item i{color:var(--gold);font-size:1.3rem;margin-top:0.2rem}
    .contact-info-item h6{font-family:'Playfair Display',serif;color:var(--gold);margin-bottom:0.2rem;font-size:0.95rem}
    .contact-info-item p{color:var(--gold-pale);font-size:0.9rem;margin:0;font-style:italic}
    footer{background:linear-gradient(160deg,#050d1a,var(--navy));border-top:2px solid var(--gold);padding:3.5rem 0 1.5rem;position:relative}
    footer::before{content:'🎀 ✦ 🎀 ✦ 🎀 ✦ 🎀 ✦ 🎀';display:block;text-align:center;color:var(--gold);opacity:0.3;font-size:0.9rem;letter-spacing:8px;margin-bottom:2.5rem}
    .footer-brand{font-family:'Dancing Script',cursive;font-size:2.2rem;color:var(--gold);cursor:pointer}
    .footer-tagline{font-style:italic;color:var(--gold-pale);font-size:0.95rem;opacity:0.8}
    .footer-heading{font-family:'Playfair Display',serif;color:var(--gold);font-size:1rem;letter-spacing:2px;text-transform:uppercase;margin-bottom:1.2rem;padding-bottom:0.5rem;border-bottom:1px solid rgba(201,168,76,0.3)}
    .footer-links{list-style:none;padding:0}
    .footer-links li{margin-bottom:0.5rem}
    .footer-links a{color:var(--gold-pale);opacity:0.75;text-decoration:none;font-size:0.92rem;transition:all 0.2s;cursor:pointer}
    .footer-links a:hover{opacity:1;color:var(--gold);padding-left:5px}
    .social-links{display:flex;gap:0.8rem;margin-top:1rem}
    .social-link{width:38px;height:38px;border:1px solid rgba(201,168,76,0.4);border-radius:50%;display:flex;align-items:center;justify-content:center;color:var(--gold);text-decoration:none;font-size:1rem;transition:all 0.25s}
    .social-link:hover{background:var(--gold);color:var(--navy);transform:translateY(-3px)}
    .footer-bottom{text-align:center;padding-top:2rem;margin-top:2rem;border-top:1px solid rgba(201,168,76,0.2);color:var(--gold-pale);opacity:0.6;font-size:0.85rem}
    .cart-overlay{position:fixed;inset:0;background:rgba(0,0,0,0.6);z-index:2000;opacity:0;pointer-events:none;transition:opacity 0.3s}
    .cart-overlay.open{opacity:1;pointer-events:all}
    .cart-sidebar{position:fixed;top:0;right:-420px;width:400px;max-width:95vw;height:100vh;background:var(--deep-blue);border-left:2px solid var(--gold);z-index:2001;transition:right 0.4s cubic-bezier(0.4,0,0.2,1);display:flex;flex-direction:column}
    .cart-sidebar.open{right:0}
    .cart-header{padding:1.5rem;border-bottom:1px solid rgba(201,168,76,0.3);display:flex;align-items:center;justify-content:space-between}
    .cart-header h4{font-family:'Dancing Script',cursive;color:var(--gold);font-size:1.8rem;margin:0}
    .cart-close{background:none;border:1px solid rgba(201,168,76,0.4);color:var(--gold);width:36px;height:36px;border-radius:50%;display:flex;align-items:center;justify-content:center;cursor:pointer;transition:all 0.2s}
    .cart-close:hover{background:var(--gold);color:var(--navy)}
    .cart-items{flex:1;overflow-y:auto;padding:1rem}
    .cart-item{display:flex;gap:1rem;padding:1rem;border-bottom:1px solid rgba(201,168,76,0.15);align-items:center}
    .ci-emoji{font-size:2.2rem}
    .ci-info{flex:1}
    .ci-name{font-family:'Playfair Display',serif;color:var(--white);font-size:0.95rem}
    .ci-price{color:var(--gold);font-size:0.9rem;font-weight:600}
    .ci-qty{display:flex;align-items:center;gap:0.5rem}
    .qty-btn{background:transparent;border:1px solid rgba(201,168,76,0.4);color:var(--gold);width:26px;height:26px;border-radius:50%;cursor:pointer;font-size:1rem;display:flex;align-items:center;justify-content:center;transition:all 0.2s}
    .qty-btn:hover{background:var(--gold);color:var(--navy)}
    .qty-num{color:var(--white);font-size:0.9rem;min-width:20px;text-align:center}
    .cart-footer{padding:1.5rem;border-top:1px solid rgba(201,168,76,0.3)}
    .cart-total-row{display:flex;justify-content:space-between;margin-bottom:1rem}
    .cart-total-row span:first-child{font-size:1.1rem;color:var(--gold-pale);text-transform:uppercase;letter-spacing:2px}
    .cart-total-row span:last-child{font-family:'Playfair Display',serif;font-size:1.3rem;color:var(--gold);font-weight:700}
    .cart-empty{text-align:center;padding:3rem 1rem;color:var(--gold-pale);opacity:0.6}
    .cart-empty i{font-size:3rem;margin-bottom:1rem;display:block}
    .toast-custom{position:fixed;bottom:2rem;right:2rem;background:linear-gradient(135deg,var(--mid-blue),var(--deep-blue));border:1px solid var(--gold);color:var(--gold-pale);padding:1rem 1.5rem;z-index:9999;font-family:'Cormorant Garamond',serif;font-size:1rem;opacity:0;transform:translateY(20px);transition:all 0.3s;pointer-events:none;display:flex;align-items:center;gap:0.7rem}
    .toast-custom.show{opacity:1;transform:translateY(0)}
    .modal-content{background:var(--deep-blue);border:2px solid var(--gold);border-radius:0}
    .modal-header{border-bottom:1px solid rgba(201,168,76,0.3)}
    .modal-title{font-family:'Dancing Script',cursive;color:var(--gold);font-size:1.8rem}
    .modal-footer{border-top:1px solid rgba(201,168,76,0.3)}
    .btn-close{filter:invert(1)}
    .order-summary-item{display:flex;justify-content:space-between;padding:0.5rem 0;border-bottom:1px solid rgba(201,168,76,0.1);color:var(--gold-pale);font-size:0.95rem}
    .order-grand-total{display:flex;justify-content:space-between;padding:0.8rem 0;color:var(--gold);font-family:'Playfair Display',serif;font-size:1.2rem;font-weight:700}
    .fade-in{opacity:0;transform:translateY(30px);transition:opacity 0.6s ease,transform 0.6s ease}
    .fade-in.visible{opacity:1;transform:translateY(0)}
    @media(max-width:768px){.hero-bow-l,.hero-bow-r{display:none}.cart-sidebar{width:100vw}.about-img-grid{grid-template-rows:160px 160px}}
  </style>
</head>
<body>

<div class="bow-float">🎀</div>
<div class="bow-float">🎀</div>
<div class="bow-float">🎀</div>
<div class="bow-float">🎀</div>
<div class="bow-float">🎀</div>

<nav class="navbar navbar-expand-lg">
  <div class="container">
    <span class="navbar-brand" onclick="showPage('home')">🎀 MAT Bakeshop</span>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navMenu">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navMenu">
      <ul class="navbar-nav ms-auto align-items-center gap-1">
        <li class="nav-item"><span class="nav-link active" id="nav-home" onclick="showPage('home')">Home</span></li>
        <li class="nav-item"><span class="nav-link" id="nav-menu" onclick="showPage('menu')">Menu</span></li>
        <li class="nav-item"><span class="nav-link" id="nav-about" onclick="showPage('about')">About</span></li>
        <li class="nav-item"><span class="nav-link" id="nav-video" onclick="showPage('video')">Watch Us Bake</span></li>
        <li class="nav-item"><span class="nav-link" id="nav-contact" onclick="showPage('contact')">Contact</span></li>
        <li class="nav-item ms-3">
          <div class="cart-icon" onclick="openCart()">
            <i class="fas fa-shopping-bag"></i>
            <span class="cart-badge" id="cartBadge">0</span>
          </div>
        </li>
      </ul>
    </div>
  </div>
</nav>

<!-- ========== PAGE: HOME ========== -->
<div class="page active" id="page-home">
  <section class="hero">
    <div class="hero-ring hero-ring-1"></div>
    <div class="hero-ring hero-ring-2"></div>
    <div class="hero-bow-l">🎀</div>
    <div class="hero-bow-r">🎀</div>
    <div class="position-relative" style="z-index:1">
      <div class="hero-tag">✦ Est. 2024 · Islamabad ✦</div>
      <h1 class="hero-title">MAT<span class="gold-text">Bakeshop</span></h1>
      <p class="hero-sub">Maryam · Ali · Taloot &nbsp;|&nbsp; Baked with Love 🎀</p>
      <div class="hero-divider"><div class="hdl"></div><span>🎂</span><div class="hdl"></div></div>
      <div class="d-flex gap-3 flex-wrap justify-content-center" style="animation:fadeDown 1.2s ease 0.4s both">
        <button class="btn-gold" onclick="showPage('menu')">Explore Menu</button>
        <button class="btn-outline-gold" onclick="showPage('contact')">Order Now</button>
      </div>
    </div>
  </section>

  <div class="gallery-strip">
    <div class="gallery-track">
      <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=440&q=80" alt="Cake">
      <img src="https://images.unsplash.com/photo-1571115177098-24ec42ed204d?w=440&q=80" alt="Bakery">
      <img src="https://images.unsplash.com/photo-1464349095431-e9a21285b5f3?w=440&q=80" alt="Cupcakes">
      <img src="https://images.unsplash.com/photo-1486427944299-d1955d23e34d?w=440&q=80" alt="Birthday cake">
      <img src="https://images.unsplash.com/photo-1587241321921-91a834d6d191?w=440&q=80" alt="Pastries">
      <img src="https://images.unsplash.com/photo-1602351447937-745cb720612f?w=440&q=80" alt="Red velvet">
      <img src="https://images.unsplash.com/photo-1519915028121-7d3463d20b13?w=440&q=80" alt="Croissants">
      <img src="https://images.unsplash.com/photo-1621303837174-89787a7d4729?w=440&q=80" alt="Cheesecake">
      <img src="https://images.unsplash.com/photo-1567620905732-2d1ec7ab7445?w=440&q=80" alt="Waffles">
      <img src="https://images.unsplash.com/photo-1550617931-e17a7b70dce2?w=440&q=80" alt="Donuts">
      <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=440&q=80" alt="Cake">
      <img src="https://images.unsplash.com/photo-1571115177098-24ec42ed204d?w=440&q=80" alt="Bakery">
      <img src="https://images.unsplash.com/photo-1464349095431-e9a21285b5f3?w=440&q=80" alt="Cupcakes">
      <img src="https://images.unsplash.com/photo-1486427944299-d1955d23e34d?w=440&q=80" alt="Birthday cake">
      <img src="https://images.unsplash.com/photo-1587241321921-91a834d6d191?w=440&q=80" alt="Pastries">
      <img src="https://images.unsplash.com/photo-1602351447937-745cb720612f?w=440&q=80" alt="Red velvet">
      <img src="https://images.unsplash.com/photo-1519915028121-7d3463d20b13?w=440&q=80" alt="Croissants">
      <img src="https://images.unsplash.com/photo-1621303837174-89787a7d4729?w=440&q=80" alt="Cheesecake">
      <img src="https://images.unsplash.com/photo-1567620905732-2d1ec7ab7445?w=440&q=80" alt="Waffles">
      <img src="https://images.unsplash.com/photo-1550617931-e17a7b70dce2?w=440&q=80" alt="Donuts">
    </div>
  </div>

  <section class="features-strip">
    <div class="container">
      <div class="row g-3 text-center">
        <div class="col-6 col-md-3"><div class="feature-item fade-in"><i class="fas fa-birthday-cake"></i><h6>Custom Cakes</h6><p>Made to order, every occasion</p></div></div>
        <div class="col-6 col-md-3"><div class="feature-item fade-in"><i class="fas fa-leaf"></i><h6>Fresh Daily</h6><p>Baked fresh every morning</p></div></div>
        <div class="col-6 col-md-3"><div class="feature-item fade-in"><i class="fas fa-truck"></i><h6>Free Delivery</h6><p>On orders above Rs. 3000</p></div></div>
        <div class="col-6 col-md-3"><div class="feature-item fade-in"><i class="fas fa-heart"></i><h6>Made with Love</h6><p>Premium Belgian ingredients</p></div></div>
      </div>
    </div>
  </section>

  <section class="testi-section">
    <div class="container">
      <p class="section-sub fade-in">🎀 What People Say 🎀</p>
      <h2 class="section-title fade-in">Sweet Words from Our Customers</h2>
      <div class="gold-divider fade-in"><div class="gdl l"></div><i class="fas fa-star"></i><div class="gdl r"></div></div>
      <div class="row g-4">
        <div class="col-md-4 fade-in"><div class="testi-card"><div class="quote-mark">"</div><div class="stars">★★★★★</div><p class="testi-text">The Ferrero Rocher cake was absolutely divine! The layers were perfect and the taste was out of this world!</p><div class="testi-author">— Ayesha K., Islamabad</div></div></div>
        <div class="col-md-4 fade-in"><div class="testi-card"><div class="quote-mark">"</div><div class="stars">★★★★★</div><p class="testi-text">Ordered the Chocolate Lava Cake for my birthday — warm, gooey perfection! MAT never disappoints!</p><div class="testi-author">— Bilal M., Rawalpindi</div></div></div>
        <div class="col-md-4 fade-in"><div class="testi-card"><div class="quote-mark">"</div><div class="stars">★★★★★</div><p class="testi-text">The Red Velvet and Lotus Three Milk cakes were incredible. MAT Bakeshop is our go-to for all occasions!</p><div class="testi-author">— Sara T., Islamabad</div></div></div>
      </div>
    </div>
  </section>
</div>

<!-- ========== PAGE: MENU ========== -->
<div class="page" id="page-menu">
  <section class="menu-section">
    <div class="container">
      <p class="section-sub fade-in">🎀 Our Specialties 🎀</p>
      <h2 class="section-title fade-in">Our Delicious Menu</h2>
      <div class="gold-divider fade-in"><div class="gdl l"></div><i class="fas fa-star"></i><div class="gdl r"></div></div>
      <div class="cat-tabs fade-in">
        <button class="cat-tab active" onclick="filterMenu('all',this)">All Items</button>
        <button class="cat-tab" onclick="filterMenu('cakes',this)">🎂 Cakes</button>
        <button class="cat-tab" onclick="filterMenu('pastry',this)">🥐 Pastries</button>
        <button class="cat-tab" onclick="filterMenu('cheesecake',this)">🍰 Cheesecakes</button>
        <button class="cat-tab" onclick="filterMenu('chocolate',this)">🍫 Chocolate</button>
      </div>
      <div class="row g-4" id="menuGrid">

 <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1621303837174-89787a7d4729?w=600&q=80" alt="Lotus Three Milk" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Lotus Three Milk</h5><p class="product-desc">Lotus Biscoff Spread Cream Cheese on a Fluffy Vanilla Milky Sponge with Lotus Crumbs on sides.</p>
            <div class="product-footer"><span class="product-price">Rs. 2,700</span><button class="add-btn" onclick="addToCart('Lotus Three Milk',2700,'🎂')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=600&q=80" alt="Lotus" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Lotus</h5><p class="product-desc">Lotus Biscoff Spread Cream Cheese on a Fluffy Vanilla Sponge & Crushed Lotus Biscuits on Top.</p>
            <div class="product-footer"><span class="product-price">Rs. 2,400</span><button class="add-btn" onclick="addToCart('Lotus Cake',2400,'🍰')">+</button></div></div></div></div>

   <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1606313564200-e75d5e30476c?w=600&q=80" alt="Belgian Chocolate" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Belgian Chocolate</h5><p class="product-desc">Made from the Purest Belgian Chocolate.</p>
            <div class="product-footer"><span class="product-price">Rs. 2,200</span><button class="add-btn" onclick="addToCart('Belgian Chocolate',2200,'🍫')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1486427944299-d1955d23e34d?w=600&q=80" alt="Ferrero Rocher" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Ferrero Rocher</h5><p class="product-desc">Made From 100% Ferrero Hazelnut Chocolate & Roasted Nuts with Ferrero Rocher's on Top.</p>
            <div class="product-footer"><span class="product-price">Rs. 2,700</span><button class="add-btn" onclick="addToCart('Ferrero Rocher',2700,'🎂')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1571115177098-24ec42ed204d?w=600&q=80" alt="Ferrero Classic" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Ferrero Classic</h5><p class="product-desc">Made From 100% Ferrero Hazelnut Chocolate & Roasted Nuts.</p>
            <div class="product-footer"><span class="product-price">Rs. 1,900</span><button class="add-btn" onclick="addToCart('Ferrero Classic',1900,'🍮')">+</button></div></div></div></div>

 <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1574085733277-851d9d856a3a?w=600&q=80" alt="Nutella" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Nutella</h5><p class="product-desc">Made From 100% Nutella & Imported Cream.</p>
            <div class="product-footer"><span class="product-price">Rs. 1,800</span><button class="add-btn" onclick="addToCart('Nutella Cake',1800,'🍫')">+</button></div></div></div></div>

   <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1602351447937-745cb720612f?w=600&q=80" alt="Red Velvet" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Red Velvet</h5><p class="product-desc">Cream Cheese Frosting on Velvety Soft Red Sponge.</p>
            <div class="product-footer"><span class="product-price">Rs. 1,600</span><button class="add-btn" onclick="addToCart('Red Velvet',1600,'❤️')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1562440499-64c9a111f713?w=600&q=80" alt="Salted Caramel" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Salted Caramel</h5><p class="product-desc">Salted Caramel, Cream Cheese & Moist Vanilla Sponge.</p>
            <div class="product-footer"><span class="product-price">Rs. 2,000</span><button class="add-btn" onclick="addToCart('Salted Caramel',2000,'🍯')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1464305795204-6f5bbfc7fb81?w=600&q=80" alt="Raffaello" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Raffaello</h5><p class="product-desc">Super Moist Vanilla Sponge with Loads of Raffaello & White Chocolate.</p>
            <div class="product-footer"><span class="product-price">Rs. 2,100</span><button class="add-btn" onclick="addToCart('Raffaello',2100,'🎂')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1587241321921-91a834d6d191?w=600&q=80" alt="KitKat" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">KitKat</h5><p class="product-desc">Creamy Milk Chocolate with Crunchy KitKat Frosting on a velvety vanilla cake sponge.</p>
            <div class="product-footer"><span class="product-price">Rs. 2,100</span><button class="add-btn" onclick="addToCart('KitKat Cake',2100,'🍫')">+</button></div></div></div></div
                                                                                                                                                                                       
   <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1576618148400-f54bed99fcfd?w=600&q=80" alt="Carrot Nut" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Carrot Nut</h5><p class="product-desc">Crème Cheese Frosting with a Sponge made from Organic Carrots, Walnuts & Nutmeg.</p>
            <div class="product-footer"><span class="product-price">Rs. 1,600</span><button class="add-btn" onclick="addToCart('Carrot Nut',1600,'🥕')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1588195538326-c5b1e9f80a1b?w=600&q=80" alt="Malteser" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Malteser</h5><p class="product-desc">Made from Premium Belgian Chocolate & Maltesers.</p>
            <div class="product-footer"><span class="product-price">Rs. 2,500</span><button class="add-btn" onclick="addToCart('Malteser',2500,'🍫')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1564355808539-22fda35bed7e?w=600&q=80" alt="German Fudge" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">German Fudge</h5><p class="product-desc">Authentic Fudge so Light that it Melts in your mouth.</p>
            <div class="product-footer"><span class="product-price">Rs. 1,500</span><button class="add-btn" onclick="addToCart('German Fudge',1500,'🍰')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1578985545062-69928b1d9587?w=600&q=80" alt="Chocolate Mousse" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Chocolate Mousse</h5><p class="product-desc">The Lightest Chocolate Cake in town.</p>
            <div class="product-footer"><span class="product-price">Rs. 1,500</span><button class="add-btn" onclick="addToCart('Chocolate Mousse',1500,'🍫')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1497534446932-c925b458314e?w=600&q=80" alt="Coffee" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Coffee</h5><p class="product-desc">Light Cream Cheese Icing with a Sweet Sense of Coffee.</p>
            <div class="product-footer"><span class="product-price">Rs. 1,700</span><button class="add-btn" onclick="addToCart('Coffee Cake',1700,'☕')">+</button></div></div></div></div>

 <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1563729784474-d77dbb933a9e?w=600&q=80" alt="Honey Cake" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Honey Cake</h5><p class="product-desc">7 Layers of Soft, Caramelized Honey Cakes Sandwiched between Cloud-Like Burnt Honey & Dulce De Leche Whipped Cream.</p>
            <div class="product-footer"><span class="product-price">Rs. 2,000</span><button class="add-btn" onclick="addToCart('Honey Cake',2000,'🍯')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1606313564200-e75d5e30476c?w=600&q=80" alt="Chocolate Decadence" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">2.5 lbs</div><h5 class="product-name">Chocolate Decadence</h5><p class="product-desc">Flourless Sponge with Triple Chocolate Layers & Whipped Cream.</p>
            <div class="product-footer"><span class="product-price">Rs. 1,700</span><button class="add-btn" onclick="addToCart('Chocolate Decadence',1700,'🎂')">+</button></div></div></div></div>

 <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="pastry chocolate">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1607478900766-efe13248b125?w=600&q=80" alt="Chocolate Lava Cake" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">Individual</div><h5 class="product-name">Chocolate Lava Cake</h5><p class="product-desc">Warm Belgian chocolate cake with a molten flowing center. Served with vanilla cream.</p>
            <div class="product-footer"><span class="product-price">Rs. 450</span><button class="add-btn" onclick="addToCart('Chocolate Lava Cake',450,'🌋')">+</button></div></div></div></div>

 <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="pastry">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1555507036-ab1f4038808a?w=600&q=80" alt="Lotus Croissant" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">Individual</div><h5 class="product-name">Lotus Croissant</h5><p class="product-desc">Buttery flaky croissant filled with rich Lotus Biscoff spread and cream cheese.</p>
            <div class="product-footer"><span class="product-price">Rs. 380</span><button class="add-btn" onclick="addToCart('Lotus Croissant',380,'🥐')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="pastry chocolate">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1464349095431-e9a21285b5f3?w=600&q=80" alt="Ferrero Cupcake" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">Individual</div><h5 class="product-name">Ferrero Cupcake</h5><p class="product-desc">Moist chocolate cupcake topped with Ferrero Rocher buttercream and whole Ferrero on top.</p>
            <div class="product-footer"><span class="product-price">Rs. 320</span><button class="add-btn" onclick="addToCart('Ferrero Cupcake',320,'🧁')">+</button></div></div></div></div>

 <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="pastry">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1567620905732-2d1ec7ab7445?w=600&q=80" alt="Belgian Waffle" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">Individual</div><h5 class="product-name">Belgian Waffle</h5><p class="product-desc">Crispy golden waffle drizzled with Belgian chocolate and fresh whipped cream.</p>
            <div class="product-footer"><span class="product-price">Rs. 350</span><button class="add-btn" onclick="addToCart('Belgian Waffle',350,'🧇')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="pastry chocolate">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1550617931-e17a7b70dce2?w=600&q=80" alt="Nutella Donut" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">Individual</div><h5 class="product-name">Nutella Donut</h5><p class="product-desc">Soft fluffy donut stuffed with 100% pure Nutella and dusted with powdered sugar.</p>
            <div class="product-footer"><span class="product-price">Rs. 280</span><button class="add-btn" onclick="addToCart('Nutella Donut',280,'🍩')">+</button></div></div></div></div>

 <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="chocolate pastry">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1481391319762-47dff72954d9?w=600&q=80" alt="Death by Chocolate" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">Individual</div><h5 class="product-name">Death by Chocolate</h5><p class="product-desc">Triple layered dark chocolate brownie with chocolate fudge drizzle.</p>
            <div class="product-footer"><span class="product-price">Rs. 500</span><button class="add-btn" onclick="addToCart('Death by Chocolate',500,'🍫')">+</button></div></div></div></div>

 <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cheesecake">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1533134242443-d4fd215305ad?w=600&q=80" alt="NYC Cheesecake" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">7 Inches</div><h5 class="product-name">NYC Cheesecake</h5><p class="product-desc">Imported French Cheese baked to perfection.</p>
            <div class="product-footer"><span class="product-price">Rs. 1,700</span><button class="add-btn" onclick="addToCart('NYC Cheesecake',1700,'🍰')">+</button></div></div></div></div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cheesecake">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1508737027454-e6454ef45afd?w=600&q=80" alt="Lemon Cheese" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">7 Inches</div><h5 class="product-name">Lemon Cheese</h5><p class="product-desc">International Recipe of Cheesecake with a 'Hint of Lemon'.</p>
            <div class="product-footer"><span class="product-price">Rs. 1,600</span><button class="add-btn" onclick="addToCart('Lemon Cheesecake',1600,'🍋')">+</button></div></div></div></div>

   <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="chocolate">
          <div class="product-card h-100"><div class="card-bow">🎀</div>
            <div class="card-photo-wrap"><img class="card-photo" src="https://images.unsplash.com/photo-1481391319762-47dff72954d9?w=600&q=80" alt="Chocolate Truffles" loading="lazy"></div>
            <div class="card-body-inner"><div class="product-size">Box of 12</div><h5 class="product-name">Chocolate Truffles</h5><p class="product-desc">Handmade Belgian chocolate truffles — hazelnut, caramel & raspberry fillings.</p>
            <div class="product-footer"><span class="product-price">Rs. 1,200</span><button class="add-btn" onclick="addToCart('Chocolate Truffles',1200,'🍫')">+</button></div></div></div></div>

      </div>
    </div>
  </section>
</div>
<!-- ========== PAGE: ABOUT ========== -->
<div class="page" id="page-about">
  <section class="about-section">
    <div class="container">
      <p class="section-sub fade-in">🎀 Our Story 🎀</p>
      <h2 class="section-title fade-in">About MAT Bakeshop</h2>
      <div class="gold-divider fade-in"><div class="gdl l"></div><i class="fas fa-heart"></i><div class="gdl r"></div></div>
      <div class="row g-4 align-items-center">
        <div class="col-lg-5 fade-in">
          <div class="about-img-grid">
            <img src="https://images.unsplash.com/photo-1556909114-f6e7ad7d3136?w=600&q=80" alt="Baker">
            <img src="https://images.unsplash.com/photo-1542124948-dc391252a940?w=400&q=80" alt="Decorating">
            <img src="https://images.unsplash.com/photo-1599785209707-a456fc1337bb?w=400&q=80" alt="Cakes">
          </div>
        </div>
        <div class="col-lg-7 fade-in">
          <div class="about-card mb-4">
            <h3 style="font-family:'Dancing Script',cursive;color:var(--gold);font-size:2rem;margin-bottom:1rem">Baked with Heart, Served with Love 🎀</h3>
            <p style="color:var(--gold-pale);line-height:1.9;font-size:1.05rem;margin-bottom:1rem">MAT Bakeshop was born from a shared passion between three friends — <strong style="color:var(--gold)">Maryam, Ali, and Taloot</strong> — who believed that every celebration deserves something truly extraordinary.</p>
            <p style="color:var(--gold-pale);line-height:1.9;font-size:1.05rem;margin-bottom:1rem">Based in Islamabad, we craft each cake, pastry, and dessert using the finest Belgian chocolate, imported ingredients, and time-honored recipes.</p>
            <p style="color:var(--gold-pale);line-height:1.9;font-size:1.05rem">From intimate birthdays to grand celebrations — let MAT Bakeshop be part of your sweetest moments. 🎀</p>
          </div>
          <div class="row g-3">
            <div class="col-6 fade-in"><div class="about-stat"><span class="number">500+</span><span class="label">Happy Customers</span></div></div>
            <div class="col-6 fade-in"><div class="about-stat"><span class="number">30+</span><span class="label">Menu Items</span></div></div>
            <div class="col-6 fade-in"><div class="about-stat"><span class="number">3</span><span class="label">Expert Bakers</span></div></div>
            <div class="col-6 fade-in"><div class="about-stat"><span class="number">100%</span><span class="label">Fresh & Pure</span></div></div>
          </div>
          <div class="mt-3 text-center fade-in" style="padding:1.5rem;background:rgba(201,168,76,0.05);border:1px solid rgba(201,168,76,0.2)">
            <p style="font-family:'Dancing Script',cursive;font-size:1.6rem;color:var(--gold);margin:0">"Every layer tells a story"</p>
            <p style="color:var(--gold-pale);font-style:italic;font-size:0.9rem;margin-top:0.3rem">— The MAT Promise</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</div>

<!-- ========== PAGE: VIDEO ========== -->
<div class="page" id="page-video">
  <section class="video-section">
    <div class="container">
      <p class="section-sub fade-in">🎀 Behind the Magic 🎀</p>
      <h2 class="section-title fade-in">Watch Us Bake</h2>
      <div class="gold-divider fade-in"><div class="gdl l"></div><i class="fas fa-play-circle"></i><div class="gdl r"></div></div>
      <div class="row g-4 align-items-stretch mb-4">
        <div class="col-lg-7 fade-in">
          <p class="vid-label">🎂 Cake Decorating in Style</p>
          <div class="video-wrapper"><div class="video-ratio">
            <iframe src="https://www.youtube.com/embed/fMpJ6nCRBDg?rel=0&modestbranding=1" title="Cake Decorating" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
          </div></div>
        </div>
        <div class="col-lg-5 fade-in">
          <div class="d-flex flex-column gap-3 h-100">
            <div style="overflow:hidden;flex:1;border:1px solid rgba(201,168,76,0.3)">
              <img src="https://images.unsplash.com/photo-1542124948-dc391252a940?w=800&q=80" alt="Baking" style="width:100%;height:100%;min-height:150px;object-fit:cover;filter:brightness(0.75);transition:filter 0.4s" onmouseover="this.style.filter='brightness(0.95)'" onmouseout="this.style.filter='brightness(0.75)'">
            </div>
            <div class="row g-3" style="flex-shrink:0">
              <div class="col-6" style="overflow:hidden;border:1px solid rgba(201,168,76,0.3)">
                <img src="https://images.unsplash.com/photo-1486427944299-d1955d23e34d?w=400&q=80" alt="Cakes" style="width:100%;height:160px;object-fit:cover;filter:brightness(0.75);transition:filter 0.4s" onmouseover="this.style.filter='brightness(0.95)'" onmouseout="this.style.filter='brightness(0.75)'">
              </div>
              <div class="col-6" style="overflow:hidden;border:1px solid rgba(201,168,76,0.3)">
                <img src="https://images.unsplash.com/photo-1571115177098-24ec42ed204d?w=400&q=80" alt="Pastries" style="width:100%;height:160px;object-fit:cover;filter:brightness(0.75);transition:filter 0.4s" onmouseover="this.style.filter='brightness(0.95)'" onmouseout="this.style.filter='brightness(0.75)'">
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="row g-4">
        <div class="col-md-6 fade-in">
          <p class="vid-label">🍫 Belgian Chocolate Artistry</p>
          <div class="video-wrapper"><div class="video-ratio">
            <iframe src="https://www.youtube.com/embed/ekPFSZB0Kxo?rel=0&modestbranding=1" title="Belgian Chocolate" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
          </div></div>
        </div>
        <div class="col-md-6 fade-in">
          <p class="vid-label">🥐 Pastry & Croissant Magic</p>
          <div class="video-wrapper"><div class="video-ratio">
            <iframe src="https://www.youtube.com/embed/GrSEFTMKEXA?rel=0&modestbranding=1" title="Pastry Magic" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
          </div></div>
        </div>
      </div>
    </div>
  </section>
</div>

<!-- ========== PAGE: CONTACT ========== -->
<div class="page" id="page-contact">
  <section class="contact-section">
    <div class="container">
      <p class="section-sub fade-in">🎀 Get in Touch 🎀</p>
      <h2 class="section-title fade-in">Order & Contact</h2>
      <div class="gold-divider fade-in"><div class="gdl l"></div><i class="fas fa-envelope"></i><div class="gdl r"></div></div>
      <div class="row g-4">
        <div class="col-lg-7 fade-in">
          <div style="background:rgba(201,168,76,0.04);border:1px solid rgba(201,168,76,0.2);padding:2.5rem">
            <h4 style="font-family:'Dancing Script',cursive;color:var(--gold);font-size:1.8rem;margin-bottom:1.5rem">Place Your Order 🎀</h4>
            <div class="mb-3"><label class="form-label-gold">Your Name</label><input type="text" class="form-control-gold" placeholder="Enter your name" id="fname"/></div>
            <div class="mb-3"><label class="form-label-gold">Phone Number</label><input type="tel" class="form-control-gold" placeholder="+92 300 0000000" id="fphone"/></div>
            <div class="mb-3"><label class="form-label-gold">Email Address</label><input type="email" class="form-control-gold" placeholder="your@email.com" id="femail"/></div>
            <div class="mb-3"><label class="form-label-gold">Delivery Address</label><input type="text" class="form-control-gold" placeholder="Your delivery address" id="faddress"/></div>
            <div class="mb-3"><label class="form-label-gold">Your Order / Special Request</label><textarea class="form-control-gold" rows="4" placeholder="Tell us what you'd like to order..." id="fmessage"></textarea></div>
            <div class="mb-4"><label class="form-label-gold">Preferred Delivery Date</label><input type="date" class="form-control-gold" id="fdate"/></div>
            <button class="btn-gold w-100" onclick="submitOrder()">Send Order Request 🎀</button>
          </div>
        </div>
        <div class="col-lg-5 fade-in">
          <div style="overflow:hidden;height:200px;margin-bottom:1.5rem;border:1px solid rgba(201,168,76,0.3)">
            <img src="https://images.unsplash.com/photo-1517433670267-08bbd4be890f?w=800&q=80" alt="MAT Bakeshop" style="width:100%;height:200px;object-fit:cover;filter:brightness(0.75);transition:filter 0.4s" onmouseover="this.style.filter='brightness(0.95)'" onmouseout="this.style.filter='brightness(0.75)'">
          </div>
          <div class="contact-info-box mb-4">
            <h4 style="font-family:'Dancing Script',cursive;color:var(--gold);font-size:1.6rem;margin-bottom:1.5rem">Find Us 🎀</h4>
            <div class="contact-info-item"><i class="fas fa-map-marker-alt"></i><div><h6>Location</h6><p>Islamabad, Pakistan</p></div></div>
            <div class="contact-info-item"><i class="fas fa-phone"></i><div><h6>Phone / WhatsApp</h6><p>+92 300 0000000</p></div></div>
            <div class="contact-info-item"><i class="fas fa-envelope"></i><div><h6>Email</h6><p>matbakeshop@gmail.com</p></div></div>
            <div class="contact-info-item"><i class="fas fa-clock"></i><div><h6>Hours</h6><p>Mon–Sat: 9am – 9pm<br/>Sun: 10am – 7pm</p></div></div>
          </div>
          <div style="background:rgba(201,168,76,0.05);border:1px solid rgba(201,168,76,0.2);padding:1.5rem;text-align:center">
            <p style="font-family:'Dancing Script',cursive;color:var(--gold);font-size:1.4rem;margin-bottom:0.5rem">Follow Us 🎀</p>
            <p style="color:var(--gold-pale);font-size:0.9rem;font-style:italic;margin-bottom:1rem">Stay updated with our latest creations</p>
            <div class="social-links justify-content-center">
              <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
              <a href="#" class="social-link"><i class="fab fa-facebook"></i></a>
              <a href="#" class="social-link"><i class="fab fa-whatsapp"></i></a>
              <a href="#" class="social-link"><i class="fab fa-tiktok"></i></a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</div>

<!-- ========== FOOTER ========== -->
<footer>
  <div class="container">
    <div class="row g-4">
      <div class="col-lg-4 col-md-6">
        <div class="footer-brand" onclick="showPage('home')">🎀 MAT Bakeshop</div>
        <p class="footer-tagline mt-2">Maryam · Ali · Taloot<br/>Baked with Love, Served with Joy</p>
        <div class="social-links mt-3">
          <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
          <a href="#" class="social-link"><i class="fab fa-facebook"></i></a>
          <a href="#" class="social-link"><i class="fab fa-whatsapp"></i></a>
          <a href="#" class="social-link"><i class="fab fa-tiktok"></i></a>
        </div>
      </div>
      <div class="col-lg-2 col-md-6">
        <h6 class="footer-heading">Quick Links</h6>
        <ul class="footer-links">
          <li><a onclick="showPage('home')">Home</a></li>
          <li><a onclick="showPage('menu')">Our Menu</a></li>
          <li><a onclick="showPage('about')">About Us</a></li>
          <li><a onclick="showPage('video')">Watch Us Bake</a></li>
          <li><a onclick="showPage('contact')">Order Now</a></li>
        </ul>
      </div>
      <div class="col-lg-3 col-md-6">
        <h6 class="footer-heading">Our Specialties</h6>
        <ul class="footer-links">
          <li><a onclick="showPage('menu')">Signature Cakes</a></li>
          <li><a onclick="showPage('menu')">Chocolate Lava Cake</a></li>
          <li><a onclick="showPage('menu')">Cheesecakes</a></li>
          <li><a onclick="showPage('menu')">Pastries & Croissants</a></li>
        </ul>
      </div>
      <div class="col-lg-3 col-md-6">
        <h6 class="footer-heading">Contact</h6>
        <ul class="footer-links">
          <li><a>📍 Islamabad, Pakistan</a></li>
          <li><a>📞 +92 300 0000000</a></li>
          <li><a>✉️ matbakeshop@gmail.com</a></li>
          <li><a>⏰ Mon–Sat: 9am–9pm</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>© 2024 MAT Bakeshop — Maryam · Ali · Taloot 🎀 All Rights Reserved</p>
      <p style="margin-top:0.3rem;font-size:0.8rem">Made with ❤️ in Islamabad</p>
    </div>
  </div>
</footer>

<!-- Cart Sidebar -->
<div class="cart-overlay" id="cartOverlay" onclick="closeCart()"></div>
<div class="cart-sidebar" id="cartSidebar">
  <div class="cart-header">
    <h4>🎀 My Cart</h4>
    <button class="cart-close" onclick="closeCart()"><i class="fas fa-times"></i></button>
  </div>
  <div class="cart-items" id="cartItems">
    <div class="cart-empty"><i class="fas fa-shopping-bag"></i><p>Your cart is empty</p><small style="color:var(--gold);opacity:0.7">Add some treats! 🎀</small></div>
  </div>
  <div class="cart-footer">
    <div class="cart-total-row"><span>Total</span><span id="cartTotal">Rs. 0</span></div>
    <button class="btn-gold w-100 mb-2" onclick="checkout()">Place Order 🎀</button>
    <button class="btn-outline-gold w-100" onclick="clearCart()">Clear Cart</button>
  </div>
</div>

<!-- Toast -->
<div class="toast-custom" id="toast"><span>🎀</span><span id="toastMsg">Added to cart!</span></div>

<!-- Order Modal -->
<div class="modal fade" id="orderModal" tabindex="-1">
  <div class="modal-dialog modal-dialog-centered">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title">Order Confirmed! 🎀</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal"></button>
      </div>
      <div class="modal-body" style="padding:2rem">
        <div style="text-align:center;margin-bottom:1.5rem">
          <div style="font-size:4rem">🎂</div>
          <p style="font-family:'Dancing Script',cursive;color:var(--gold);font-size:1.6rem;margin:0.5rem 0">Thank you!</p>
          <p style="color:var(--gold-pale);font-style:italic">We'll contact you shortly to confirm your order.</p>
        </div>
        <div id="orderSummaryContent"></div>
      </div>
      <div class="modal-footer">
        <button class="btn-gold" data-bs-dismiss="modal">Continue Shopping 🎀</button>
      </div>
    </div>
  </div>
</div>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
<script>
  function showPage(pageId) {
    document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
    document.getElementById('page-' + pageId).classList.add('active');
    document.querySelectorAll('.nav-link').forEach(l => l.classList.remove('active'));
    const navEl = document.getElementById('nav-' + pageId);
    if (navEl) navEl.classList.add('active');
    window.scrollTo({top: 0, behavior: 'smooth'});
    setTimeout(initFadeIn, 100);
    const navCollapse = document.getElementById('navMenu');
    if (navCollapse.classList.contains('show')) new bootstrap.Collapse(navCollapse).hide();
  }
  let cart = JSON.parse(localStorage.getItem('matCart') || '[]');
  function saveCart(){localStorage.setItem('matCart',JSON.stringify(cart))}
  function updateBadge(){const t=cart.reduce((s,i)=>s+i.qty,0);const b=document.getElementById('cartBadge');b.textContent=t;b.style.display=t>0?'flex':'none'}
  function addToCart(name,price,emoji){const ex=cart.find(i=>i.name===name);if(ex){ex.qty++}else{cart.push({name,price,emoji,qty:1})}saveCart();updateBadge();renderCart();showToast(name+' added! 🎀');spawnSparkles()}
  function changeQty(name,delta){const item=cart.find(i=>i.name===name);if(!item)return;item.qty+=delta;if(item.qty<=0)cart=cart.filter(i=>i.name!==name);saveCart();updateBadge();renderCart()}
  function clearCart(){cart=[];saveCart();updateBadge();renderCart()}
  function renderCart(){const c=document.getElementById('cartItems');const t=document.getElementById('cartTotal');if(!c)return;if(cart.length===0){c.innerHTML='<div class="cart-empty"><i class="fas fa-shopping-bag"></i><p>Your cart is empty</p><small style="color:var(--gold);opacity:0.7">Add some treats! 🎀</small></div>';if(t)t.textContent='Rs. 0';return}c.innerHTML=cart.map(i=>`<div class="cart-item"><span class="ci-emoji">${i.emoji}</span><div class="ci-info"><div class="ci-name">${i.name}</div><div class="ci-price">Rs. ${(i.price*i.qty).toLocaleString()}</div></div><div class="ci-qty"><button class="qty-btn" onclick="changeQty('${i.name}',-1)">−</button><span class="qty-num">${i.qty}</span><button class="qty-btn" onclick="changeQty('${i.name}',1)">+</button></div></div>`).join('');const total=cart.reduce((s,i)=>s+i.price*i.qty,0);if(t)t.textContent='Rs. '+total.toLocaleString()}
  function openCart(){document.getElementById('cartSidebar').classList.add('open');document.getElementById('cartOverlay').classList.add('open');renderCart()}
  function closeCart(){document.getElementById('cartSidebar').classList.remove('open');document.getElementById('cartOverlay').classList.remove('open')}
  function checkout(){if(cart.length===0){showToast('Cart is empty! 🎀');return}const total=cart.reduce((s,i)=>s+i.price*i.qty,0);const summary=cart.map(i=>`<div class="order-summary-item"><span>${i.emoji} ${i.name} x${i.qty}</span><span>Rs. ${(i.price*i.qty).toLocaleString()}</span></div>`).join('')+`<div class="order-grand-total"><span>Grand Total</span><span>Rs. ${total.toLocaleString()}</span></div>`;document.getElementById('orderSummaryContent').innerHTML=summary;closeCart();new bootstrap.Modal(document.getElementById('orderModal')).show();clearCart()}
  function submitOrder(){const n=document.getElementById('fname').value.trim();const p=document.getElementById('fphone').value.trim();const m=document.getElementById('fmessage').value.trim();if(!n||!p||!m){showToast('Please fill required fields! 🎀');return}showToast('Order sent! We will contact you soon 🎀');['fname','fphone','femail','faddress','fmessage','fdate'].forEach(id=>{const el=document.getElementById(id);if(el)el.value=''})}
  function filterMenu(cat,btn){document.querySelectorAll('.cat-tab').forEach(b=>b.classList.remove('active'));btn.classList.add('active');document.querySelectorAll('.menu-item').forEach(item=>{if(cat==='all'||item.dataset.cat.includes(cat)){item.style.display='';item.style.animation='fadeIn 0.4s ease'}else{item.style.display='none'}})}
  function showToast(msg){const t=document.getElementById('toast');document.getElementById('toastMsg').textContent=msg;t.classList.add('show');setTimeout(()=>t.classList.remove('show'),3000)}
  function spawnSparkles(){const e=['✨','🎀','⭐','💫','🌟'];for(let i=0;i<6;i++){setTimeout(()=>{const s=document.createElement('div');s.style.cssText=`position:fixed;pointer-events:none;font-size:${Math.random()*1.2+0.8}rem;left:${Math.random()*100}vw;top:${Math.random()*100}vh;z-index:9999;animation:sparkleAnim 1.4s ease forwards`;s.textContent=e[Math.floor(Math.random()*e.length)];document.body.appendChild(s);setTimeout(()=>s.remove(),1400)},i*80)}}
  function initFadeIn(){const observer=new IntersectionObserver(entries=>{entries.forEach(e=>{if(e.isIntersecting)e.target.classList.add('visible')})},{threshold:0.1});document.querySelectorAll('.fade-in:not(.visible)').forEach(el=>observer.observe(el))}
  updateBadge();
  initFadeIn();
  const ss=document.createElement('style');
  ss.textContent='@keyframes sparkleAnim{0%{opacity:0;transform:scale(0) translateY(0)}50%{opacity:1;transform:scale(1.2) translateY(-20px)}100%{opacity:0;transform:scale(0.5) translateY(-40px)}}@keyframes fadeIn{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}';
  document.head.appendChild(ss);
</script>
</body>
</html>
