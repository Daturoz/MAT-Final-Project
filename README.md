<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>MAT Bakeshop – Artisan Bakery, Islamabad</title>
<meta name="description" content="MAT Bakeshop – Custom cakes, pastries & desserts baked with love in Islamabad by Maryam, Ali & Taloot."/>
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400&family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,400&family=Dancing+Script:wght@600;700&display=swap" rel="stylesheet"/>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"/>
<style>
/* ══════════════════════════════════════════
   DESIGN TOKENS
══════════════════════════════════════════ */
:root{
  --navy:      #07111f;
  --deep-blue: #0b1d38;
  --mid-blue:  #152d56;
  --gold:      #c9a84c;
  --gold-light:#e2bc6a;
  --gold-pale: #f0dfa0;
  --gold-muted:rgba(201,168,76,0.18);
  --cream:     #fdf8ee;
  --white:     #ffffff;
  --text-muted:rgba(240,223,160,0.72);
  --card-bg:   linear-gradient(160deg,#0e2140 0%,#081525 100%);
  --border-gold:1px solid rgba(201,168,76,0.22);
  --border-gold-strong:1px solid rgba(201,168,76,0.5);
  --radius:4px;
  --shadow-card:0 8px 40px rgba(0,0,0,0.5),0 0 0 1px rgba(201,168,76,0.08);
  --transition:all 0.3s cubic-bezier(0.4,0,0.2,1);
}

/* ══════════════════════════════════════════
   RESET & BASE
══════════════════════════════════════════ */
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth;font-size:16px}
body{font-family:'Cormorant Garamond',serif;background:var(--navy);color:var(--cream);overflow-x:hidden;line-height:1.7}
img{max-width:100%;display:block}
::-webkit-scrollbar{width:6px}
::-webkit-scrollbar-track{background:var(--navy)}
::-webkit-scrollbar-thumb{background:var(--gold);border-radius:3px}

/* ══════════════════════════════════════════
   UTILITY CLASSES
══════════════════════════════════════════ */
.gold{color:var(--gold)}
.gold-text{color:var(--gold)}
.text-muted-gold{color:var(--text-muted)}
.section-gap{padding:5.5rem 0}
.fade-in{opacity:0;transform:translateY(28px);transition:opacity 0.65s ease,transform 0.65s ease}
.fade-in.visible{opacity:1;transform:translateY(0)}
.fade-in.delay-1{transition-delay:0.1s}
.fade-in.delay-2{transition-delay:0.2s}
.fade-in.delay-3{transition-delay:0.3s}
.fade-in.delay-4{transition-delay:0.4s}

/* ══════════════════════════════════════════
   FLOATING BOWS (ambient decoration)
══════════════════════════════════════════ */
.bow-float{position:fixed;font-size:1.4rem;opacity:0.07;pointer-events:none;z-index:0;animation:floatBow 7s ease-in-out infinite}
.bow-float:nth-child(1){top:10%;left:0.8%;animation-delay:0s;font-size:2rem}
.bow-float:nth-child(2){top:28%;right:1%;animation-delay:2s;font-size:1.3rem}
.bow-float:nth-child(3){top:58%;left:0.5%;animation-delay:4s;font-size:1.7rem}
.bow-float:nth-child(4){top:80%;right:1%;animation-delay:1s;font-size:1rem}
@keyframes floatBow{0%,100%{transform:translateY(0) rotate(-8deg)}50%{transform:translateY(-18px) rotate(8deg)}}

/* ══════════════════════════════════════════
   NAVBAR
══════════════════════════════════════════ */
.navbar{
  background:rgba(7,17,31,0.97);
  backdrop-filter:blur(12px);
  -webkit-backdrop-filter:blur(12px);
  border-bottom:1px solid rgba(201,168,76,0.25);
  padding:0.75rem 0;
  position:sticky;top:0;z-index:1000;
  transition:box-shadow 0.3s
}
.navbar.scrolled{box-shadow:0 4px 24px rgba(0,0,0,0.6)}
.navbar-brand{
  font-family:'Dancing Script',cursive;
  font-size:1.85rem;
  color:var(--gold) !important;
  letter-spacing:0.5px;
  text-shadow:0 0 24px rgba(201,168,76,0.3)
}
.navbar-brand span{font-size:1.1rem;vertical-align:middle;margin-right:0.2rem}
.nav-link{
  font-family:'Cormorant Garamond',serif;
  font-size:0.88rem;
  font-weight:600;
  color:rgba(240,223,160,0.78) !important;
  letter-spacing:2.5px;
  text-transform:uppercase;
  padding:0.45rem 0.9rem !important;
  transition:color 0.25s;
  position:relative
}
.nav-link::after{
  content:'';position:absolute;bottom:-2px;left:50%;
  width:0;height:1.5px;background:var(--gold);
  transition:all 0.3s;transform:translateX(-50%)
}
.nav-link:hover{color:var(--gold) !important}
.nav-link:hover::after,.nav-link.active::after{width:65%}
.nav-link.active{color:var(--gold) !important}
.navbar-toggler{border:1px solid rgba(201,168,76,0.4);padding:0.3rem 0.5rem}
.navbar-toggler-icon{background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'%3e%3cpath stroke='rgba(201,168,76,0.9)' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e")}
.cart-btn{
  position:relative;cursor:pointer;
  color:var(--gold-light);font-size:1.2rem;
  background:none;border:none;padding:0.3rem 0.5rem;
  transition:var(--transition)
}
.cart-btn:hover{color:var(--gold);transform:scale(1.1)}
.cart-badge{
  position:absolute;top:-6px;right:-8px;
  background:var(--gold);color:var(--navy);
  border-radius:50%;width:18px;height:18px;
  font-size:0.68rem;font-weight:700;
  display:none;align-items:center;justify-content:center;
  font-family:'Cormorant Garamond',serif
}
.cart-badge.show{display:flex}

/* ══════════════════════════════════════════
   SECTION HEADERS
══════════════════════════════════════════ */
.section-eyebrow{
  font-size:0.78rem;letter-spacing:5px;text-transform:uppercase;
  color:var(--gold);opacity:0.85;
  text-align:center;margin-bottom:0.5rem;font-style:italic
}
.section-title{
  font-family:'Dancing Script',cursive;
  font-size:clamp(2.2rem,4.5vw,3.5rem);
  color:var(--white);text-align:center;
  margin-bottom:0.5rem;line-height:1.1
}
.section-title .gold-accent{color:var(--gold)}
.gold-rule{
  display:flex;align-items:center;justify-content:center;
  gap:0.75rem;margin-bottom:3.5rem
}
.gold-rule .line{
  width:80px;height:1px;
  background:linear-gradient(90deg,transparent,var(--gold))
}
.gold-rule .line.r{background:linear-gradient(90deg,var(--gold),transparent)}
.gold-rule .diamond{
  color:var(--gold);font-size:0.75rem;opacity:0.85
}

/* ══════════════════════════════════════════
   HERO
══════════════════════════════════════════ */
.hero{
  min-height:95vh;
  background:
    linear-gradient(165deg,rgba(7,17,31,0.82) 0%,rgba(11,29,56,0.6) 50%,rgba(7,17,31,0.9) 100%),
    url('https://images.unsplash.com/photo-1578985545062-69928b1d9587?w=1800&q=85') center/cover no-repeat;
  display:flex;align-items:center;justify-content:center;
  text-align:center;position:relative;overflow:hidden;padding:5rem 1rem 4rem
}
.hero-deco{
  position:absolute;border-radius:50%;
  border:1px solid rgba(201,168,76,0.08);
  top:50%;left:50%;transform:translate(-50%,-50%);
  pointer-events:none
}
.hero-deco-1{width:700px;height:700px}
.hero-deco-2{width:480px;height:480px;border-color:rgba(201,168,76,0.06)}
.hero-deco-3{width:280px;height:280px;border-color:rgba(201,168,76,0.12)}
.hero-stars{
  position:absolute;top:12%;left:50%;transform:translateX(-50%);
  color:var(--gold);font-size:0.7rem;letter-spacing:10px;
  opacity:0.28;white-space:nowrap;pointer-events:none
}
.hero-stars.bottom{top:auto;bottom:12%}
.hero-side-bow{
  position:absolute;font-size:3.5rem;opacity:0.3;
  pointer-events:none;animation:floatBow 6s ease-in-out infinite;
  filter:drop-shadow(0 0 12px rgba(201,168,76,0.2))
}
.hero-side-bow.left{left:5%;top:42%}
.hero-side-bow.right{right:5%;top:42%;animation-delay:1s}
.hero-eyebrow{
  display:inline-block;font-size:0.75rem;
  letter-spacing:6px;text-transform:uppercase;
  color:var(--gold);border:1px solid rgba(201,168,76,0.35);
  padding:0.4rem 2rem;margin-bottom:1.8rem;
  animation:fadeSlideDown 0.8s ease both
}
.hero-title{
  font-family:'Dancing Script',cursive;
  font-size:clamp(4rem,9vw,8rem);
  color:var(--white);line-height:1;
  margin-bottom:0.2rem;
  animation:fadeSlideDown 0.9s ease 0.08s both;
  text-shadow:0 4px 40px rgba(0,0,0,0.4)
}
.hero-title-sub{
  font-family:'Dancing Script',cursive;
  font-size:clamp(1.8rem,4vw,3.2rem);
  color:var(--gold);
  animation:fadeSlideDown 0.9s ease 0.14s both;
  margin-bottom:1.2rem;
  text-shadow:0 0 40px rgba(201,168,76,0.4)
}
.hero-tagline{
  font-size:clamp(1rem,2vw,1.2rem);
  color:var(--text-muted);font-style:italic;
  letter-spacing:1.5px;margin-bottom:0.6rem;
  animation:fadeSlideDown 1s ease 0.2s both
}
.hero-names{
  font-size:0.82rem;letter-spacing:4px;text-transform:uppercase;
  color:var(--gold);opacity:0.7;margin-bottom:2.5rem;
  animation:fadeSlideDown 1s ease 0.25s both
}
.hero-actions{
  display:flex;gap:1rem;flex-wrap:wrap;
  justify-content:center;
  animation:fadeSlideDown 1.1s ease 0.35s both
}
@keyframes fadeSlideDown{
  from{opacity:0;transform:translateY(-22px)}
  to{opacity:1;transform:translateY(0)}
}

/* ══════════════════════════════════════════
   BUTTONS
══════════════════════════════════════════ */
.btn-gold{
  font-family:'Cormorant Garamond',serif;
  font-size:0.88rem;font-weight:600;
  letter-spacing:3px;text-transform:uppercase;
  color:var(--navy);
  background:linear-gradient(135deg,var(--gold-light) 0%,var(--gold) 100%);
  border:none;padding:0.9rem 2.8rem;
  cursor:pointer;transition:var(--transition);
  text-decoration:none;display:inline-block;
  position:relative;overflow:hidden
}
.btn-gold::after{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(255,255,255,0.15),transparent);
  opacity:0;transition:opacity 0.3s
}
.btn-gold:hover{
  transform:translateY(-2px);
  box-shadow:0 12px 32px rgba(201,168,76,0.45);
  color:var(--navy)
}
.btn-gold:hover::after{opacity:1}
.btn-outline-gold{
  font-family:'Cormorant Garamond',serif;
  font-size:0.88rem;font-weight:600;
  letter-spacing:3px;text-transform:uppercase;
  color:var(--gold);background:transparent;
  border:1.5px solid var(--gold);
  padding:0.9rem 2.8rem;cursor:pointer;
  transition:var(--transition);text-decoration:none;
  display:inline-block
}
.btn-outline-gold:hover{
  background:var(--gold);color:var(--navy);
  transform:translateY(-2px);
  box-shadow:0 12px 32px rgba(201,168,76,0.3)
}

/* ══════════════════════════════════════════
   SCROLLING GALLERY
══════════════════════════════════════════ */
.gallery-strip{
  height:240px;overflow:hidden;position:relative;
  border-top:1px solid rgba(201,168,76,0.12);
  border-bottom:1px solid rgba(201,168,76,0.12)
}
.gallery-strip::before,.gallery-strip::after{
  content:'';position:absolute;top:0;bottom:0;width:140px;z-index:2;pointer-events:none
}
.gallery-strip::before{left:0;background:linear-gradient(90deg,var(--navy),transparent)}
.gallery-strip::after{right:0;background:linear-gradient(-90deg,var(--navy),transparent)}
.gallery-track{display:flex;gap:4px;animation:scrollGallery 44s linear infinite;width:max-content}
.gallery-track:hover{animation-play-state:paused}
.gallery-track img{
  height:240px;width:200px;object-fit:cover;flex-shrink:0;
  filter:brightness(0.7) saturate(0.85);
  transition:filter 0.4s,transform 0.4s
}
.gallery-track img:hover{filter:brightness(1) saturate(1.05);transform:scale(1.03);z-index:1}
@keyframes scrollGallery{0%{transform:translateX(0)}100%{transform:translateX(-50%)}}

/* ══════════════════════════════════════════
   FEATURES STRIP
══════════════════════════════════════════ */
.features-strip{
  background:linear-gradient(135deg,var(--mid-blue),var(--deep-blue));
  border-top:1px solid rgba(201,168,76,0.18);
  border-bottom:1px solid rgba(201,168,76,0.18);
  padding:3rem 0
}
.feature-item{text-align:center;padding:1.2rem 1rem}
.feature-icon{
  width:54px;height:54px;border-radius:50%;
  background:rgba(201,168,76,0.1);border:1px solid rgba(201,168,76,0.25);
  display:flex;align-items:center;justify-content:center;
  margin:0 auto 1rem;transition:var(--transition)
}
.feature-item:hover .feature-icon{
  background:rgba(201,168,76,0.2);
  box-shadow:0 0 20px rgba(201,168,76,0.2)
}
.feature-icon i{font-size:1.4rem;color:var(--gold)}
.feature-item h6{
  font-family:'Playfair Display',serif;
  font-size:1rem;color:var(--white);
  margin-bottom:0.25rem;font-weight:600
}
.feature-item p{font-size:0.88rem;color:var(--text-muted);margin:0;font-style:italic}

/* ══════════════════════════════════════════
   MENU SECTION
══════════════════════════════════════════ */
.menu-section{
  padding:5.5rem 0;background:var(--navy);
  position:relative
}
.menu-section::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,var(--gold),transparent)
}
/* Category tabs */
.cat-tabs{display:flex;justify-content:center;flex-wrap:wrap;gap:0.6rem;margin-bottom:3rem}
.cat-tab{
  font-family:'Cormorant Garamond',serif;
  font-size:0.82rem;font-weight:600;letter-spacing:2px;text-transform:uppercase;
  color:var(--text-muted);background:transparent;
  border:1px solid rgba(201,168,76,0.28);
  padding:0.55rem 1.5rem;cursor:pointer;
  transition:var(--transition);border-radius:var(--radius)
}
.cat-tab:hover{color:var(--gold);border-color:var(--gold)}
.cat-tab.active{
  background:var(--gold);color:var(--navy);
  border-color:var(--gold);font-weight:700
}

/* Product card */
.product-card{
  background:var(--card-bg);
  border:var(--border-gold);
  border-radius:var(--radius);
  overflow:hidden;
  transition:var(--transition);
  height:100%;display:flex;flex-direction:column;
  position:relative
}
.product-card::before{
  content:'';position:absolute;top:0;left:0;right:0;
  height:2px;background:linear-gradient(90deg,transparent,var(--gold),transparent);
  transform:scaleX(0);transition:transform 0.4s;z-index:2
}
.product-card:hover{
  transform:translateY(-6px);
  border-color:rgba(201,168,76,0.4);
  box-shadow:var(--shadow-card)
}
.product-card:hover::before{transform:scaleX(1)}
.card-photo-wrap{
  overflow:hidden;position:relative;
  height:195px;flex-shrink:0
}
.card-photo-wrap::after{
  content:'';position:absolute;bottom:0;left:0;right:0;
  height:50px;background:linear-gradient(transparent,#0e2140);
  pointer-events:none
}
.card-photo{
  width:100%;height:195px;object-fit:cover;display:block;
  transition:transform 0.55s ease,filter 0.4s
}
.product-card:hover .card-photo{transform:scale(1.06);filter:brightness(1.08) saturate(1.1)}
.card-ribbon{
  position:absolute;top:10px;left:10px;
  background:var(--gold);color:var(--navy);
  font-size:0.62rem;font-weight:700;letter-spacing:2px;text-transform:uppercase;
  padding:0.2rem 0.7rem;z-index:3;border-radius:2px
}
.card-body-inner{padding:1rem 1.3rem 1.3rem;flex:1;display:flex;flex-direction:column}
.product-size{
  font-size:0.72rem;letter-spacing:2px;text-transform:uppercase;
  color:var(--gold);opacity:0.75;margin-bottom:0.4rem
}
.product-name{
  font-family:'Playfair Display',serif;
  font-size:1.1rem;color:var(--white);
  margin-bottom:0.4rem;font-weight:600
}
.product-desc{
  font-size:0.87rem;color:var(--text-muted);
  flex:1;font-style:italic;line-height:1.6;margin-bottom:0.75rem
}
.product-footer{
  display:flex;align-items:center;justify-content:space-between;
  margin-top:auto;padding-top:0.75rem;
  border-top:1px solid rgba(201,168,76,0.12)
}
.product-price{
  font-family:'Playfair Display',serif;
  font-size:1.15rem;font-weight:700;color:var(--gold)
}
.add-btn{
  background:transparent;
  border:1px solid rgba(201,168,76,0.5);
  color:var(--gold);width:32px;height:32px;
  border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  font-size:1.1rem;cursor:pointer;
  transition:var(--transition);flex-shrink:0
}
.add-btn:hover{background:var(--gold);color:var(--navy);transform:rotate(90deg)}

/* No-results state */
.no-results{
  text-align:center;padding:3rem;color:var(--text-muted);
  display:none
}
.no-results i{font-size:2.5rem;margin-bottom:1rem;color:var(--gold);opacity:0.4}

/* ══════════════════════════════════════════
   ABOUT SECTION
══════════════════════════════════════════ */
.about-section{
  padding:5.5rem 0;
  background:linear-gradient(160deg,var(--deep-blue),var(--navy));
  position:relative;overflow:hidden
}
.about-section::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,var(--gold),transparent)
}
.about-card{
  background:rgba(201,168,76,0.04);
  border:var(--border-gold);
  border-radius:var(--radius);
  padding:2.5rem;margin-bottom:2rem
}
.about-img-grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  grid-template-rows:185px 185px;
  gap:5px;border-radius:var(--radius);overflow:hidden
}
.about-img-grid img{
  width:100%;height:100%;object-fit:cover;
  transition:filter 0.4s,transform 0.45s;
  filter:brightness(0.8) saturate(0.9)
}
.about-img-grid img:hover{filter:brightness(1) saturate(1.05);transform:scale(1.03)}
.about-img-grid img:first-child{grid-row:span 2}
.about-stat{
  text-align:center;padding:1.4rem 1rem;
  border:var(--border-gold);
  border-radius:var(--radius);
  background:rgba(201,168,76,0.03);
  transition:var(--transition)
}
.about-stat:hover{
  background:rgba(201,168,76,0.08);
  border-color:rgba(201,168,76,0.4);
  transform:translateY(-3px)
}
.about-stat .number{
  font-family:'Dancing Script',cursive;
  font-size:2.8rem;color:var(--gold);line-height:1;display:block
}
.about-stat .label{
  font-size:0.78rem;letter-spacing:2.5px;text-transform:uppercase;
  color:var(--text-muted);margin-top:0.25rem;display:block
}
.promise-box{
  padding:1.5rem;text-align:center;
  background:rgba(201,168,76,0.04);
  border:var(--border-gold);border-radius:var(--radius);
  margin-top:1.5rem
}
.promise-box .quote{
  font-family:'Dancing Script',cursive;
  font-size:1.55rem;color:var(--gold);margin:0
}
.promise-box .attr{
  font-size:0.82rem;color:var(--text-muted);
  font-style:italic;margin-top:0.3rem
}

/* ══════════════════════════════════════════
   VIDEO SECTION
══════════════════════════════════════════ */
.video-section{
  padding:5.5rem 0;
  background:var(--navy);position:relative
}
.video-section::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,var(--gold),transparent)
}
.video-wrapper{
  position:relative;
  border:var(--border-gold);
  border-radius:var(--radius);
  overflow:hidden;
  box-shadow:0 24px 64px rgba(0,0,0,0.5)
}
.video-ratio{position:relative;padding-bottom:56.25%;height:0;overflow:hidden}
.video-ratio iframe{position:absolute;top:0;left:0;width:100%;height:100%;border:0}
.vid-label{
  font-family:'Playfair Display',serif;
  color:var(--gold);margin-bottom:0.75rem;font-size:0.98rem;
  letter-spacing:0.5px
}
.side-img-wrap{
  overflow:hidden;
  border:var(--border-gold);
  border-radius:var(--radius)
}
.side-img-wrap img{
  width:100%;height:100%;object-fit:cover;
  filter:brightness(0.72);
  transition:filter 0.4s,transform 0.4s
}
.side-img-wrap:hover img{filter:brightness(0.92);transform:scale(1.03)}

/* ══════════════════════════════════════════
   TESTIMONIALS
══════════════════════════════════════════ */
.testi-section{
  padding:5.5rem 0;
  background:linear-gradient(160deg,var(--deep-blue),var(--navy));
  position:relative
}
.testi-section::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,var(--gold),transparent)
}
.testi-card{
  background:rgba(11,29,56,0.6);
  border:var(--border-gold);
  border-radius:var(--radius);
  padding:2rem;position:relative;
  transition:var(--transition);height:100%
}
.testi-card:hover{
  border-color:rgba(201,168,76,0.45);
  transform:translateY(-4px);
  box-shadow:0 16px 40px rgba(0,0,0,0.4)
}
.quote-mark{
  font-family:'Playfair Display',serif;
  font-size:4.5rem;color:var(--gold);opacity:0.15;
  line-height:1;position:absolute;top:0.5rem;left:1.2rem;
  pointer-events:none
}
.stars{color:var(--gold);font-size:0.78rem;margin-bottom:0.6rem;letter-spacing:2px}
.testi-text{
  font-style:italic;color:var(--text-muted);
  line-height:1.8;font-size:1rem;margin-bottom:1rem;
  padding-top:1.5rem;position:relative;z-index:1
}
.testi-author{
  font-family:'Playfair Display',serif;
  color:var(--gold);font-size:0.9rem;font-weight:600
}
.testi-role{font-size:0.8rem;color:var(--text-muted);font-style:italic;margin-top:0.1rem}

/* ══════════════════════════════════════════
   CONTACT SECTION
══════════════════════════════════════════ */
.contact-section{
  padding:5.5rem 0;background:var(--navy);position:relative
}
.contact-section::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
  background:linear-gradient(90deg,transparent,var(--gold),transparent)
}
.form-card{
  background:rgba(201,168,76,0.03);
  border:var(--border-gold);
  border-radius:var(--radius);
  padding:2.5rem
}
.form-label-gold{
  font-size:0.78rem;letter-spacing:2.5px;text-transform:uppercase;
  color:var(--text-muted);margin-bottom:0.4rem;display:block
}
.form-control-gold{
  background:rgba(7,17,31,0.7);
  border:1px solid rgba(201,168,76,0.25);
  color:var(--cream);padding:0.8rem 1.1rem;
  border-radius:var(--radius);
  font-family:'Cormorant Garamond',serif;font-size:1rem;
  transition:border-color 0.3s,box-shadow 0.3s;width:100%
}
.form-control-gold:focus{
  background:rgba(7,17,31,0.9);
  border-color:var(--gold);color:var(--cream);
  box-shadow:0 0 0 3px rgba(201,168,76,0.12);outline:none
}
.form-control-gold::placeholder{color:rgba(240,223,160,0.28)}
.contact-info-box{
  background:rgba(201,168,76,0.03);
  border:var(--border-gold);
  border-radius:var(--radius);
  padding:2rem
}
.contact-info-item{
  display:flex;gap:1rem;margin-bottom:1.4rem;align-items:flex-start
}
.contact-info-item:last-child{margin-bottom:0}
.contact-icon{
  width:38px;height:38px;flex-shrink:0;
  border-radius:50%;background:var(--gold-muted);
  border:1px solid rgba(201,168,76,0.25);
  display:flex;align-items:center;justify-content:center
}
.contact-icon i{color:var(--gold);font-size:0.9rem}
.contact-info-item h6{
  font-family:'Playfair Display',serif;
  color:var(--gold);margin-bottom:0.15rem;font-size:0.88rem;font-weight:600
}
.contact-info-item p{color:var(--text-muted);font-size:0.88rem;margin:0;font-style:italic;line-height:1.5}
.social-wrap{
  background:rgba(201,168,76,0.03);border:var(--border-gold);
  border-radius:var(--radius);padding:1.5rem;text-align:center;margin-top:1.2rem
}
.social-wrap p{
  font-family:'Dancing Script',cursive;
  color:var(--gold);font-size:1.3rem;margin-bottom:0.3rem
}
.social-wrap small{
  color:var(--text-muted);font-size:0.85rem;font-style:italic;display:block;margin-bottom:1rem
}
.social-links{display:flex;gap:0.7rem;justify-content:center}
.social-link{
  width:38px;height:38px;
  border:1px solid rgba(201,168,76,0.35);
  border-radius:50%;display:flex;align-items:center;justify-content:center;
  color:var(--gold);text-decoration:none;font-size:0.9rem;
  transition:var(--transition)
}
.social-link:hover{
  background:var(--gold);color:var(--navy);
  transform:translateY(-3px);border-color:var(--gold)
}

/* ══════════════════════════════════════════
   FOOTER
══════════════════════════════════════════ */
footer{
  background:linear-gradient(160deg,#030a14,#07111f);
  border-top:1px solid rgba(201,168,76,0.25);
  padding:4rem 0 1.5rem;position:relative
}
.footer-top-deco{
  text-align:center;color:var(--gold);
  opacity:0.22;font-size:0.8rem;letter-spacing:10px;
  margin-bottom:3rem
}
.footer-brand{font-family:'Dancing Script',cursive;font-size:2rem;color:var(--gold)}
.footer-tagline{
  font-style:italic;color:var(--text-muted);
  font-size:0.9rem;margin-top:0.4rem;line-height:1.6
}
.footer-heading{
  font-family:'Playfair Display',serif;color:var(--gold);
  font-size:0.82rem;letter-spacing:3px;text-transform:uppercase;
  margin-bottom:1.2rem;padding-bottom:0.6rem;
  border-bottom:1px solid rgba(201,168,76,0.2);font-weight:600
}
.footer-links{list-style:none;padding:0}
.footer-links li{margin-bottom:0.45rem}
.footer-links a{
  color:var(--text-muted);text-decoration:none;
  font-size:0.9rem;transition:all 0.2s;
  display:inline-flex;align-items:center;gap:0.4rem
}
.footer-links a:hover{color:var(--gold);padding-left:4px}
.footer-bottom{
  text-align:center;padding-top:2rem;margin-top:2.5rem;
  border-top:1px solid rgba(201,168,76,0.15);
  color:var(--text-muted);font-size:0.82rem
}

/* ══════════════════════════════════════════
   CART SIDEBAR
══════════════════════════════════════════ */
.cart-overlay{
  position:fixed;inset:0;
  background:rgba(0,0,0,0.65);
  z-index:2000;opacity:0;pointer-events:none;
  transition:opacity 0.3s;backdrop-filter:blur(3px)
}
.cart-overlay.open{opacity:1;pointer-events:all}
.cart-sidebar{
  position:fixed;top:0;right:-420px;
  width:400px;max-width:96vw;height:100vh;
  background:var(--deep-blue);
  border-left:1px solid rgba(201,168,76,0.3);
  z-index:2001;transition:right 0.4s cubic-bezier(0.4,0,0.2,1);
  display:flex;flex-direction:column
}
.cart-sidebar.open{right:0}
.cart-header{
  padding:1.4rem 1.5rem;
  border-bottom:1px solid rgba(201,168,76,0.2);
  display:flex;align-items:center;justify-content:space-between;
  flex-shrink:0
}
.cart-header h4{
  font-family:'Dancing Script',cursive;
  color:var(--gold);font-size:1.7rem;margin:0
}
.cart-close{
  background:none;
  border:1px solid rgba(201,168,76,0.3);
  color:var(--gold);width:34px;height:34px;
  border-radius:50%;display:flex;align-items:center;
  justify-content:center;cursor:pointer;transition:var(--transition)
}
.cart-close:hover{background:var(--gold);color:var(--navy)}
.cart-items{flex:1;overflow-y:auto;padding:0.75rem}
.cart-item{
  display:flex;gap:0.9rem;padding:0.9rem;
  border-bottom:1px solid rgba(201,168,76,0.1);
  align-items:center
}
.ci-emoji{font-size:2rem;flex-shrink:0}
.ci-info{flex:1;min-width:0}
.ci-name{
  font-family:'Playfair Display',serif;
  color:var(--white);font-size:0.9rem;
  white-space:nowrap;overflow:hidden;text-overflow:ellipsis
}
.ci-price{color:var(--gold);font-size:0.85rem;font-weight:600;margin-top:0.15rem}
.ci-qty{display:flex;align-items:center;gap:0.45rem;flex-shrink:0}
.qty-btn{
  background:transparent;
  border:1px solid rgba(201,168,76,0.35);
  color:var(--gold);width:26px;height:26px;
  border-radius:50%;cursor:pointer;
  font-size:1rem;display:flex;align-items:center;
  justify-content:center;transition:var(--transition)
}
.qty-btn:hover{background:var(--gold);color:var(--navy)}
.qty-num{color:var(--white);font-size:0.88rem;min-width:18px;text-align:center}
.cart-footer{
  padding:1.4rem 1.5rem;
  border-top:1px solid rgba(201,168,76,0.2);
  flex-shrink:0
}
.cart-total-row{display:flex;justify-content:space-between;margin-bottom:1.2rem;align-items:baseline}
.cart-total-row .label{
  font-size:0.78rem;color:var(--text-muted);
  text-transform:uppercase;letter-spacing:2.5px
}
.cart-total-row .amount{
  font-family:'Playfair Display',serif;
  font-size:1.35rem;color:var(--gold);font-weight:700
}
.cart-empty-state{
  text-align:center;padding:3.5rem 1rem;color:var(--text-muted)
}
.cart-empty-state i{font-size:2.8rem;color:var(--gold);opacity:0.3;margin-bottom:1rem;display:block}
.cart-empty-state p{margin-bottom:0.3rem}
.cart-empty-state small{color:var(--gold);opacity:0.6;font-size:0.85rem}

/* ══════════════════════════════════════════
   TOAST NOTIFICATION
══════════════════════════════════════════ */
.toast-custom{
  position:fixed;bottom:2rem;right:2rem;
  background:linear-gradient(135deg,var(--mid-blue),var(--deep-blue));
  border:var(--border-gold);
  border-radius:var(--radius);
  color:var(--gold-pale);
  padding:0.85rem 1.4rem;z-index:9999;
  font-family:'Cormorant Garamond',serif;font-size:0.98rem;
  opacity:0;transform:translateY(16px);
  transition:all 0.3s;pointer-events:none;
  display:flex;align-items:center;gap:0.6rem;
  box-shadow:0 8px 32px rgba(0,0,0,0.4)
}
.toast-custom.show{opacity:1;transform:translateY(0)}

/* ══════════════════════════════════════════
   MODAL
══════════════════════════════════════════ */
.modal-content{
  background:var(--deep-blue);
  border:1px solid rgba(201,168,76,0.35);
  border-radius:var(--radius)
}
.modal-header{border-bottom:1px solid rgba(201,168,76,0.2);padding:1.25rem 1.5rem}
.modal-title{font-family:'Dancing Script',cursive;color:var(--gold);font-size:1.7rem}
.modal-footer{border-top:1px solid rgba(201,168,76,0.2)}
.btn-close{filter:invert(1) brightness(0.7)}
.order-summary-item{
  display:flex;justify-content:space-between;
  padding:0.5rem 0;border-bottom:1px solid rgba(201,168,76,0.1);
  color:var(--text-muted);font-size:0.92rem
}
.order-grand-total{
  display:flex;justify-content:space-between;
  padding:0.85rem 0;
  color:var(--gold);font-family:'Playfair Display',serif;
  font-size:1.15rem;font-weight:700
}

/* ══════════════════════════════════════════
   WHATSAPP BUTTON (floating)
══════════════════════════════════════════ */
.wa-float{
  position:fixed;bottom:2rem;left:2rem;
  width:52px;height:52px;border-radius:50%;
  background:#25D366;color:#fff;
  display:flex;align-items:center;justify-content:center;
  font-size:1.5rem;text-decoration:none;z-index:999;
  box-shadow:0 6px 20px rgba(37,211,102,0.4);
  transition:var(--transition);cursor:pointer
}
.wa-float:hover{transform:scale(1.1);color:#fff}
.wa-tooltip{
  position:fixed;bottom:2.4rem;left:5rem;
  background:var(--deep-blue);border:var(--border-gold);
  color:var(--cream);padding:0.5rem 1rem;
  border-radius:var(--radius);font-size:0.85rem;
  white-space:nowrap;opacity:0;pointer-events:none;
  transition:opacity 0.3s;z-index:999
}
.wa-float:hover ~ .wa-tooltip{opacity:1}

/* ══════════════════════════════════════════
   SPARKLE ANIMATION
══════════════════════════════════════════ */
@keyframes sparkleUp{
  0%{opacity:0;transform:scale(0) translateY(0)}
  40%{opacity:1;transform:scale(1.2) translateY(-18px)}
  100%{opacity:0;transform:scale(0.4) translateY(-40px)}
}
@keyframes fadeInUp{
  from{opacity:0;transform:translateY(10px)}
  to{opacity:1;transform:translateY(0)}
}

/* ══════════════════════════════════════════
   RESPONSIVE
══════════════════════════════════════════ */
@media(max-width:991px){
  .hero-side-bow{display:none}
  .about-img-grid{grid-template-rows:150px 150px}
}
@media(max-width:767px){
  .cart-sidebar{width:100vw}
  .section-gap{padding:4rem 0}
  .hero-deco-1,.hero-deco-2{display:none}
  .wa-tooltip{display:none}
}
@media(max-width:480px){
  .hero-eyebrow{letter-spacing:3px}
  .toast-custom{right:1rem;left:1rem;bottom:1rem}
}
</style>
</head>
<body>

<!-- Ambient decoration -->
<div class="bow-float" aria-hidden="true">🎀</div>
<div class="bow-float" aria-hidden="true">🎀</div>
<div class="bow-float" aria-hidden="true">🎀</div>
<div class="bow-float" aria-hidden="true">🎀</div>

<!-- ═══════════════ NAVBAR ═══════════════ -->
<nav class="navbar navbar-expand-lg" id="mainNav" role="navigation" aria-label="Main navigation">
  <div class="container">
    <a class="navbar-brand" href="#home" aria-label="MAT Bakeshop home">
      <span aria-hidden="true">🎀</span> MAT Bakeshop
    </a>
    <button class="navbar-toggler" type="button"
      data-bs-toggle="collapse" data-bs-target="#navMenu"
      aria-controls="navMenu" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navMenu">
      <ul class="navbar-nav ms-auto align-items-center gap-1">
        <li class="nav-item"><a class="nav-link active" href="#home">Home</a></li>
        <li class="nav-item"><a class="nav-link" href="#menu">Menu</a></li>
        <li class="nav-item"><a class="nav-link" href="#about">About</a></li>
        <li class="nav-item"><a class="nav-link" href="#video">Watch Us Bake</a></li>
        <li class="nav-item"><a class="nav-link" href="#contact">Order</a></li>
        <li class="nav-item ms-2">
          <button class="cart-btn" onclick="openCart()" aria-label="Open shopping cart">
            <i class="fas fa-shopping-bag" aria-hidden="true"></i>
            <span class="cart-badge" id="cartBadge" aria-live="polite">0</span>
          </button>
        </li>
      </ul>
    </div>
  </div>
</nav>

<!-- ═══════════════ HERO ═══════════════ -->
<section class="hero" id="home" aria-label="Welcome to MAT Bakeshop">
  <div class="hero-deco hero-deco-1" aria-hidden="true"></div>
  <div class="hero-deco hero-deco-2" aria-hidden="true"></div>
  <div class="hero-deco hero-deco-3" aria-hidden="true"></div>
  <div class="hero-stars" aria-hidden="true">✦ &nbsp; ✧ &nbsp; ✦ &nbsp; ✧ &nbsp; ✦ &nbsp; ✧ &nbsp; ✦</div>
  <div class="hero-stars bottom" aria-hidden="true">✦ &nbsp; ✧ &nbsp; ✦ &nbsp; ✧ &nbsp; ✦ &nbsp; ✧ &nbsp; ✦</div>
  <div class="hero-side-bow left" aria-hidden="true">🎀</div>
  <div class="hero-side-bow right" aria-hidden="true">🎀</div>
  <div class="position-relative" style="z-index:1;max-width:720px">
    <div class="hero-eyebrow">✦ Est. 2024 &nbsp;·&nbsp; Islamabad ✦</div>
    <h1 class="hero-title">MAT</h1>
    <p class="hero-title-sub">Bakeshop</p>
    <p class="hero-tagline">Artisan Cakes &amp; Pastries, Baked with Love</p>
    <p class="hero-names">Maryam &nbsp;·&nbsp; Ali &nbsp;·&nbsp; Taloot</p>
    <div class="hero-actions">
      <a href="#menu" class="btn-gold">Explore Menu</a>
      <a href="#contact" class="btn-outline-gold">Place an Order</a>
    </div>
  </div>
</section>

<!-- ═══════════════ GALLERY STRIP ═══════════════ -->
<div class="gallery-strip" aria-hidden="true" role="presentation">
  <div class="gallery-track">
    <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1571115177098-24ec42ed204d?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1464349095431-e9a21285b5f3?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1486427944299-d1955d23e34d?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1587241321921-91a834d6d191?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1602351447937-745cb720612f?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1519915028121-7d3463d20b13?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1621303837174-89787a7d4729?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1567620905732-2d1ec7ab7445?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1550617931-e17a7b70dce2?w=440&q=80" alt="" loading="lazy">
    <!-- Duplicate for seamless loop -->
    <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1571115177098-24ec42ed204d?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1464349095431-e9a21285b5f3?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1486427944299-d1955d23e34d?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1587241321921-91a834d6d191?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1602351447937-745cb720612f?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1519915028121-7d3463d20b13?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1621303837174-89787a7d4729?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1567620905732-2d1ec7ab7445?w=440&q=80" alt="" loading="lazy">
    <img src="https://images.unsplash.com/photo-1550617931-e17a7b70dce2?w=440&q=80" alt="" loading="lazy">
  </div>
</div>

<!-- ═══════════════ FEATURES ═══════════════ -->
<section class="features-strip" aria-label="Our features">
  <div class="container">
    <div class="row g-3">
      <div class="col-6 col-md-3">
        <div class="feature-item fade-in">
          <div class="feature-icon" aria-hidden="true"><i class="fas fa-birthday-cake"></i></div>
          <h6>Custom Cakes</h6>
          <p>Made to order for every occasion</p>
        </div>
      </div>
      <div class="col-6 col-md-3">
        <div class="feature-item fade-in delay-1">
          <div class="feature-icon" aria-hidden="true"><i class="fas fa-seedling"></i></div>
          <h6>Baked Fresh Daily</h6>
          <p>Every item made fresh each morning</p>
        </div>
      </div>
      <div class="col-6 col-md-3">
        <div class="feature-item fade-in delay-2">
          <div class="feature-icon" aria-hidden="true"><i class="fas fa-motorcycle"></i></div>
          <h6>Free Delivery</h6>
          <p>On orders above Rs.&nbsp;3,000</p>
        </div>
      </div>
      <div class="col-6 col-md-3">
        <div class="feature-item fade-in delay-3">
          <div class="feature-icon" aria-hidden="true"><i class="fas fa-award"></i></div>
          <h6>Premium Ingredients</h6>
          <p>Belgian chocolate &amp; imported cream</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════════ MENU ═══════════════ -->
<section class="menu-section" id="menu" aria-label="Our menu">
  <div class="container">
    <p class="section-eyebrow fade-in">🎀 Our Specialties 🎀</p>
    <h2 class="section-title fade-in">Our Delicious <span class="gold-accent">Menu</span></h2>
    <div class="gold-rule fade-in" aria-hidden="true">
      <div class="line"></div><span class="diamond">✦</span><div class="line r"></div>
    </div>

    <!-- Search + Filter -->
    <div class="row g-3 justify-content-center mb-4 fade-in">
      <div class="col-12 col-md-5">
        <input type="search" class="form-control-gold w-100" id="menuSearch"
          placeholder="Search menu items…" aria-label="Search menu items"
          oninput="handleSearch(this.value)" style="padding:0.65rem 1.1rem;font-size:0.9rem">
      </div>
    </div>
    <div class="cat-tabs fade-in" role="tablist" aria-label="Menu categories">
      <button class="cat-tab active" onclick="filterMenu('all',this)" role="tab" aria-selected="true">All Items</button>
      <button class="cat-tab" onclick="filterMenu('cakes',this)" role="tab" aria-selected="false">🎂 Cakes</button>
      <button class="cat-tab" onclick="filterMenu('pastry',this)" role="tab" aria-selected="false">🥐 Pastries</button>
      <button class="cat-tab" onclick="filterMenu('cheesecake',this)" role="tab" aria-selected="false">🍰 Cheesecakes</button>
      <button class="cat-tab" onclick="filterMenu('chocolate',this)" role="tab" aria-selected="false">🍫 Chocolate</button>
    </div>

    <div class="row g-4" id="menuGrid">

      <!-- CAKES -->
      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes" data-name="lotus three milk">
        <div class="product-card h-100">
          <div class="card-ribbon">Bestseller</div>
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1621303837174-89787a7d4729?w=600&q=80" alt="Lotus Three Milk cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Lotus Three Milk</h3>
            <p class="product-desc">Lotus Biscoff spread cream cheese on a fluffy vanilla milky sponge, finished with Lotus crumbs on the sides.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 2,700</span>
              <button class="add-btn" onclick="addToCart('Lotus Three Milk',2700,'🎂')" aria-label="Add Lotus Three Milk to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes" data-name="lotus cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=600&q=80" alt="Lotus Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Lotus</h3>
            <p class="product-desc">Lotus Biscoff spread cream cheese on a fluffy vanilla sponge, with crushed Lotus biscuits on top.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 2,400</span>
              <button class="add-btn" onclick="addToCart('Lotus Cake',2400,'🍰')" aria-label="Add Lotus Cake to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate" data-name="belgian chocolate cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1606313564200-e75d5e30476c?w=600&q=80" alt="Belgian Chocolate Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Belgian Chocolate</h3>
            <p class="product-desc">Made from the purest Belgian chocolate — rich, deep, and utterly indulgent.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 2,200</span>
              <button class="add-btn" onclick="addToCart('Belgian Chocolate',2200,'🍫')" aria-label="Add Belgian Chocolate to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate" data-name="ferrero rocher cake">
        <div class="product-card h-100">
          <div class="card-ribbon">Popular</div>
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1486427944299-d1955d23e34d?w=600&q=80" alt="Ferrero Rocher Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Ferrero Rocher</h3>
            <p class="product-desc">100% Ferrero hazelnut chocolate &amp; roasted nuts, crowned with Ferrero Rocher bonbons on top.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 2,700</span>
              <button class="add-btn" onclick="addToCart('Ferrero Rocher',2700,'🎂')" aria-label="Add Ferrero Rocher to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate" data-name="ferrero classic cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1571115177098-24ec42ed204d?w=600&q=80" alt="Ferrero Classic" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Ferrero Classic</h3>
            <p class="product-desc">100% Ferrero hazelnut chocolate &amp; roasted nuts — the classic, no frills, pure indulgence.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 1,900</span>
              <button class="add-btn" onclick="addToCart('Ferrero Classic',1900,'🍮')" aria-label="Add Ferrero Classic to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate" data-name="nutella cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1574085733277-851d9d856a3a?w=600&q=80" alt="Nutella Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Nutella</h3>
            <p class="product-desc">100% pure Nutella &amp; imported cream — heaven for hazelnut lovers.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 1,800</span>
              <button class="add-btn" onclick="addToCart('Nutella Cake',1800,'🍫')" aria-label="Add Nutella Cake to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes" data-name="red velvet cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1602351447937-745cb720612f?w=600&q=80" alt="Red Velvet Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Red Velvet</h3>
            <p class="product-desc">Cream cheese frosting on a velvety-soft red sponge — a timeless classic.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 1,600</span>
              <button class="add-btn" onclick="addToCart('Red Velvet',1600,'❤️')" aria-label="Add Red Velvet to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes" data-name="salted caramel cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1562440499-64c9a111f713?w=600&q=80" alt="Salted Caramel Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Salted Caramel</h3>
            <p class="product-desc">Salted caramel, cream cheese &amp; moist vanilla sponge — the perfect sweet-salty balance.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 2,000</span>
              <button class="add-btn" onclick="addToCart('Salted Caramel',2000,'🍯')" aria-label="Add Salted Caramel to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes" data-name="raffaello cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1549931319-a545dcf3bc7c?w=600&q=80" alt="Raffaello Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Raffaello</h3>
            <p class="product-desc">Super moist vanilla sponge with loads of Raffaello &amp; white chocolate throughout.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 2,100</span>
              <button class="add-btn" onclick="addToCart('Raffaello',2100,'🎂')" aria-label="Add Raffaello to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate" data-name="kitkat cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1587241321921-91a834d6d191?w=600&q=80" alt="KitKat Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">KitKat</h3>
            <p class="product-desc">Creamy milk chocolate with crunchy KitKat frosting on a velvety vanilla sponge.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 2,100</span>
              <button class="add-btn" onclick="addToCart('KitKat Cake',2100,'🍫')" aria-label="Add KitKat Cake to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes" data-name="carrot nut cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1576618148400-f54bed99fcfd?w=600&q=80" alt="Carrot Nut Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Carrot Nut</h3>
            <p class="product-desc">Cream cheese frosting on a sponge made from organic carrots, walnuts &amp; nutmeg.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 1,600</span>
              <button class="add-btn" onclick="addToCart('Carrot Nut',1600,'🥕')" aria-label="Add Carrot Nut to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate" data-name="malteser cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1511381939415-e44db5e4b3c3?w=600&q=80" alt="Malteser Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Malteser</h3>
            <p class="product-desc">Premium Belgian chocolate &amp; Maltesers — irresistibly crunchy and smooth.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 2,500</span>
              <button class="add-btn" onclick="addToCart('Malteser',2500,'🍫')" aria-label="Add Malteser to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate" data-name="german fudge cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1588195538326-c5b1e9f80a1b?w=600&q=80" alt="German Fudge Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">German Fudge</h3>
            <p class="product-desc">Authentic fudge so light it melts on your tongue — a true European classic.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 1,500</span>
              <button class="add-btn" onclick="addToCart('German Fudge',1500,'🍰')" aria-label="Add German Fudge to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate" data-name="chocolate mousse cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1564355808539-22fda35bed7e?w=600&q=80" alt="Chocolate Mousse Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Chocolate Mousse</h3>
            <p class="product-desc">The lightest chocolate cake in town — airy, cloud-like, yet deeply chocolatey.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 1,500</span>
              <button class="add-btn" onclick="addToCart('Chocolate Mousse',1500,'🍫')" aria-label="Add Chocolate Mousse to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes" data-name="coffee cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1497534446932-c925b458314e?w=600&q=80" alt="Coffee Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Coffee</h3>
            <p class="product-desc">Light cream cheese icing with a sweet, aromatic sense of coffee woven throughout.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 1,700</span>
              <button class="add-btn" onclick="addToCart('Coffee Cake',1700,'☕')" aria-label="Add Coffee Cake to cart">+</button>
            </div>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes" data-name="honey cake medovik">
        <div class="product-card h-100">
          <div class="card-ribbon">Signature</div>
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1563729784474-d77dbb933a9e?w=600&q=80" alt="Honey Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Honey Cake</h3>
            <p class="product-desc">7 layers of soft caramelised honey cakes sandwiched between cloud-like burnt honey &amp; dulce de leche whipped cream.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 2,000</span>
              <button class="add-btn" onclick="addToCart('Honey Cake',2000,'🍯')" aria-label="Add Honey Cake to cart">+</button>
            </div>
          </div>
        </div>
      </div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cakes chocolate" data-name="chocolate decadence cake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1578985545062-69928b1d9587?w=600&q=80" alt="Chocolate Decadence" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">2.5 lbs</div>
            <h3 class="product-name">Chocolate Decadence</h3>
            <p class="product-desc">Flourless sponge with triple chocolate layers &amp; whipped cream — for the true chocoholic.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 1,700</span>
              <button class="add-btn" onclick="addToCart('Chocolate Decadence',1700,'🎂')" aria-label="Add Chocolate Decadence to cart">+</button>
            </div>
          </div>
        </div>
      </div>

  <!-- PASTRIES -->
 <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="pastry chocolate" data-name="chocolate lava cake pastry">
        <div class="product-card h-100">
          <div class="card-ribbon">Popular</div>
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1607478900766-efe13248b125?w=600&q=80" alt="Chocolate Lava Cake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">Individual</div>
            <h3 class="product-name">Chocolate Lava Cake</h3>
            <p class="product-desc">Warm Belgian chocolate cake with a molten flowing centre. Served with vanilla cream.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 450</span>
              <button class="add-btn" onclick="addToCart('Chocolate Lava Cake',450,'🌋')" aria-label="Add Chocolate Lava Cake to cart">+</button>
            </div>
          </div>
        </div>
      </div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="pastry" data-name="lotus croissant pastry">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1555507036-ab1f4038808a?w=600&q=80" alt="Lotus Croissant" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">Individual</div>
            <h3 class="product-name">Lotus Croissant</h3>
            <p class="product-desc">Buttery flaky croissant filled with rich Lotus Biscoff spread and cream cheese.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 380</span>
              <button class="add-btn" onclick="addToCart('Lotus Croissant',380,'🥐')" aria-label="Add Lotus Croissant to cart">+</button>
            </div>
          </div>
        </div>
      </div>

 <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="pastry chocolate" data-name="ferrero cupcake pastry">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1464349095431-e9a21285b5f3?w=600&q=80" alt="Ferrero Cupcake" loading="lazy">
          </div>
       <div class="card-body-inner">
            <div class="product-size">Individual</div>
            <h3 class="product-name">Ferrero Cupcake</h3>
            <p class="product-desc">Moist chocolate cupcake topped with Ferrero Rocher buttercream &amp; a whole Ferrero on top.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 320</span>
              <button class="add-btn" onclick="addToCart('Ferrero Cupcake',320,'🧁')" aria-label="Add Ferrero Cupcake to cart">+</button>
            </div>
          </div>
        </div>
      </div>

   <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="pastry" data-name="belgian waffle">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1567620905732-2d1ec7ab7445?w=600&q=80" alt="Belgian Waffle" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">Individual</div>
            <h3 class="product-name">Belgian Waffle</h3>
            <p class="product-desc">Crispy golden waffle drizzled with Belgian chocolate and fresh whipped cream.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 350</span>
              <button class="add-btn" onclick="addToCart('Belgian Waffle',350,'🧇')" aria-label="Add Belgian Waffle to cart">+</button>
            </div>
          </div>
        </div>
      </div>

   <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="pastry chocolate" data-name="nutella donut">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1550617931-e17a7b70dce2?w=600&q=80" alt="Nutella Donut" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">Individual</div>
            <h3 class="product-name">Nutella Donut</h3>
            <p class="product-desc">Soft fluffy donut stuffed with 100% pure Nutella and dusted with powdered sugar.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 280</span>
              <button class="add-btn" onclick="addToCart('Nutella Donut',280,'🍩')" aria-label="Add Nutella Donut to cart">+</button>
            </div>
          </div>
        </div>
      </div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="pastry chocolate" data-name="death by chocolate brownie">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1606313564200-e75d5e30476c?w=600&q=80" alt="Death by Chocolate Brownie" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">Individual</div>
            <h3 class="product-name">Death by Chocolate</h3>
            <p class="product-desc">Triple layered dark chocolate brownie with chocolate fudge drizzle — dangerously good.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 500</span>
              <button class="add-btn" onclick="addToCart('Death by Chocolate',500,'🍫')" aria-label="Add Death by Chocolate to cart">+</button>
            </div>
          </div>
        </div>
      </div>
        <!-- CHEESECAKES -->
      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cheesecake" data-name="nyc new york cheesecake">
        <div class="product-card h-100">
          <div class="card-ribbon">Bestseller</div>
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1533134242443-d4fd215305ad?w=600&q=80" alt="NYC Cheesecake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">7 Inches</div>
            <h3 class="product-name">NYC Cheesecake</h3>
            <p class="product-desc">Imported French cheese baked to perfection — dense, creamy, classically New York.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 1,700</span>
              <button class="add-btn" onclick="addToCart('NYC Cheesecake',1700,'🍰')" aria-label="Add NYC Cheesecake to cart">+</button>
            </div>
          </div>
        </div>
      </div>

  <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="cheesecake" data-name="lemon cheesecake">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1508737027454-e6454ef45afd?w=600&q=80" alt="Lemon Cheesecake" loading="lazy">
          </div>
          <div class="card-body-inner">
            <div class="product-size">7 Inches</div>
            <h3 class="product-name">Lemon Cheese</h3>
            <p class="product-desc">International-recipe cheesecake with a bright hint of lemon — refreshing and elegant.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 1,600</span>
              <button class="add-btn" onclick="addToCart('Lemon Cheesecake',1600,'🍋')" aria-label="Add Lemon Cheesecake to cart"></button>
            </div>
          </div>
        </div>
      </div>

      <!-- CHOCOLATE EXTRAS -->
      <div class="col-12 col-sm-6 col-lg-4 menu-item" data-cat="chocolate" data-name="chocolate truffles box">
        <div class="product-card h-100">
          <div class="card-photo-wrap">
            <img class="card-photo" src="https://images.unsplash.com/photo-1481391319762-47dff72954d9?w=600&q=80" alt="Chocolate Truffles Box" loading="lazy">
            
</div>
          <div class="card-body-inner">
            <div class="product-size">Box of 12</div>
            <h3 class="product-name">Chocolate Truffles</h3>
            <p class="product-desc">Handmade Belgian chocolate truffles — hazelnut, caramel &amp; raspberry fillings.</p>
            <div class="product-footer">
              <span class="product-price">Rs. 1,200</span>
              <button class="add-btn" onclick="addToCart('Chocolate Truffles',1200,'🫖')" aria-label="Add Chocolate Truffles to cart">+</button>
            </div>
          </div>
        </div>
      </div>

    </div><!-- /menuGrid -->

 <div class="no-results" id="noResults" role="status" aria-live="polite">
      <i class="fas fa-search" aria-hidden="true"></i>
      <p>No items found. Try a different search or category.</p>
    </div>

  </div>
</section>

<!-- ═══════════════ ABOUT ═══════════════ -->
<section class="about-section" id="about" aria-label="About MAT Bakeshop">
  <div class="container">
    <p class="section-eyebrow fade-in">🎀 Our Story 🎀</p>
    <h2 class="section-title fade-in">About <span class="gold-accent">MAT Bakeshop</span></h2>
    <div class="gold-rule fade-in" aria-hidden="true">
      <div class="line"></div><span class="diamond">❤</span><div class="line r"></div>
    </div>
    <div class="row g-4 g-lg-5 align-items-center">
      <div class="col-lg-5 fade-in">
        <div class="about-img-grid">
          <img src="https://images.unsplash.com/photo-1556909114-f6e7ad7d3136?w=600&q=80" alt="Baker at work" loading="lazy">
          <img src="https://images.unsplash.com/photo-1542124948-dc391252a940?w=400&q=80" alt="Cake decorating" loading="lazy">
          <img src="https://images.unsplash.com/photo-1599785209707-a456fc1337bb?w=400&q=80" alt="Finished cakes" loading="lazy">
        </div>
      </div>
      <div class="col-lg-7 fade-in delay-1">
        <div class="about-card">
          <h3 style="font-family:'Dancing Script',cursive;color:var(--gold);font-size:1.9rem;margin-bottom:1rem">
            Baked with Heart, Served with Love 🎀
          </h3>
          <p style="color:var(--text-muted);line-height:1.9;font-size:1.05rem;margin-bottom:1rem">
            MAT Bakeshop was born from a shared passion between three friends —
            <strong style="color:var(--gold)">Maryam, Ali, and Taloot</strong> — who believed every celebration deserves something truly extraordinary.
          </p>
          <p style="color:var(--text-muted);line-height:1.9;font-size:1.05rem;margin-bottom:1rem">
            Based in Islamabad, we craft each cake, pastry, and dessert using the finest Belgian chocolate, imported ingredients, and time-honoured recipes passed down with love.
          </p>
          <p style="color:var(--text-muted);line-height:1.9;font-size:1.05rem">
            From intimate birthdays to grand celebrations — let MAT Bakeshop be part of your sweetest moments. 🎀
          </p>
        </div>
        <div class="row g-3 mt-1">
          <div class="col-6 fade-in delay-1"><div class="about-stat"><span class="number">500+</span><span class="label">Happy Customers</span></div></div>
          <div class="col-6 fade-in delay-2"><div class="about-stat"><span class="number">25+</span><span class="label">Menu Items</span></div></div>
          <div class="col-6 fade-in delay-3"><div class="about-stat"><span class="number">3</span><span class="label">Expert Bakers</span></div></div>
          <div class="col-6 fade-in delay-4"><div class="about-stat"><span class="number">100%</span><span class="label">Fresh &amp; Pure</span></div></div>
        </div>
        <div class="promise-box fade-in">
          <p class="quote">"Every layer tells a story"</p>
          <p class="attr">— The MAT Promise</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════════ VIDEO ═══════════════ -->
<section class="video-section" id="video" aria-label="Watch us bake">
  <div class="container">
    <p class="section-eyebrow fade-in">🎀 Behind the Magic 🎀</p>
    <h2 class="section-title fade-in">Watch Us <span class="gold-accent">Bake</span></h2>
    <div class="gold-rule fade-in" aria-hidden="true">
      <div class="line"></div><span class="diamond">▶</span><div class="line r"></div>
    </div>
    <div class="row g-4 align-items-stretch mb-4">
      <div class="col-lg-7 fade-in">
        <p class="vid-label">🎂 Cake Decorating in Style</p>
        <div class="video-wrapper">
          <div class="video-ratio">
            <iframe src="https://www.youtube.com/embed/fMpJ6nCRBDg?rel=0&modestbranding=1"
              title="Cake Decorating Tutorial"
              allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"></iframe>
          </div>
        </div>
      </div>
      <div class="col-lg-5 fade-in delay-1">
        <div class="d-flex flex-column gap-3 h-100">
          <div class="side-img-wrap" style="flex:1;min-height:150px">
            <img src="https://images.unsplash.com/photo-1542124948-dc391252a940?w=800&q=80" alt="Baker decorating a cake" loading="lazy" style="width:100%;height:100%;object-fit:cover">
          </div>
          <div class="row g-3" style="flex-shrink:0">
            <div class="col-6">
              <div class="side-img-wrap" style="height:155px">
                <img src="https://images.unsplash.com/photo-1486427944299-d1955d23e34d?w=400&q=80" alt="Layered cakes" loading="lazy" style="width:100%;height:155px;object-fit:cover">
              </div>
            </div>
            <div class="col-6">
              <div class="side-img-wrap" style="height:155px">
                <img src="https://images.unsplash.com/photo-1571115177098-24ec42ed204d?w=400&q=80" alt="Pastries" loading="lazy" style="width:100%;height:155px;object-fit:cover">
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="row g-4">
      <div class="col-md-6 fade-in">
        <p class="vid-label">🍫 Belgian Chocolate Artistry</p>
        <div class="video-wrapper">
          <div class="video-ratio">
            <iframe src="https://www.youtube.com/embed/ekPFSZB0Kxo?rel=0&modestbranding=1"
              title="Belgian Chocolate Work"
              allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"></iframe>
          </div>
        </div>
      </div>
      <div class="col-md-6 fade-in delay-1">
        <p class="vid-label">🥐 Pastry &amp; Croissant Magic</p>
        <div class="video-wrapper">
          <div class="video-ratio">
            <iframe src="https://www.youtube.com/embed/GrSEFTMKEXA?rel=0&modestbranding=1"
              title="Pastry and Croissant Baking"
              allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen loading="lazy"></iframe>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════════ TESTIMONIALS ═══════════════ -->
<section class="testi-section" aria-label="Customer testimonials">
  <div class="container">
    <p class="section-eyebrow fade-in">🎀 What People Say 🎀</p>
    <h2 class="section-title fade-in">Sweet Words from Our <span class="gold-accent">Customers</span></h2>
    <div class="gold-rule fade-in" aria-hidden="true">
      <div class="line"></div><span class="diamond">★</span><div class="line r"></div>
    </div>
    <div class="row g-4">
      <div class="col-md-4 fade-in">
        <div class="testi-card" role="article">
          <div class="quote-mark" aria-hidden="true">"</div>
          <div class="stars" aria-label="5 stars">★★★★★</div>
          <p class="testi-text">The Ferrero Rocher cake was absolutely divine! The layers were perfect and the taste was out of this world. MAT Bakeshop never disappoints!</p>
          <div class="testi-author">Ayesha K.</div>
          <div class="testi-role">Islamabad</div>
        </div>
      </div>
      <div class="col-md-4 fade-in delay-1">
        <div class="testi-card" role="article">
          <div class="quote-mark" aria-hidden="true">"</div>
          <div class="stars" aria-label="5 stars">★★★★★</div>
          <p class="testi-text">Ordered the Chocolate Lava Cake for my birthday — warm, gooey perfection! The delivery was on time and the packaging was beautiful too.</p>
          <div class="testi-author">Bilal M.</div>
          <div class="testi-role">Rawalpindi</div>
        </div>
      </div>
      <div class="col-md-4 fade-in delay-2">
        <div class="testi-card" role="article">
          <div class="quote-mark" aria-hidden="true">"</div>
          <div class="stars" aria-label="5 stars">★★★★★</div>
          <p class="testi-text">The Red Velvet and Lotus Three Milk cakes were incredible. MAT Bakeshop is now our go-to for all family celebrations — highly recommended!</p>
          <div class="testi-author">Sara T.</div>
          <div class="testi-role">Islamabad</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════════ CONTACT ═══════════════ -->
<section class="contact-section" id="contact" aria-label="Order and contact">
  <div class="container">
    <p class="section-eyebrow fade-in">🎀 Get in Touch 🎀</p>
    <h2 class="section-title fade-in">Order &amp; <span class="gold-accent">Contact</span></h2>
    <div class="gold-rule fade-in" aria-hidden="true">
      <div class="line"></div><span class="diamond">✉</span><div class="line r"></div>
    </div>
    <div class="row g-4 g-lg-5">
      <div class="col-lg-7 fade-in">
        <div class="form-card">
          <h3 style="font-family:'Dancing Script',cursive;color:var(--gold);font-size:1.75rem;margin-bottom:1.5rem">
            Place Your Order 🎀
          </h3>
          <div class="row g-3 mb-3">
            <div class="col-md-6">
              <label class="form-label-gold" for="fname">Your Name <span style="color:var(--gold)">*</span></label>
              <input type="text" class="form-control-gold" id="fname" placeholder="Enter your name" autocomplete="name" required>
            </div>
            <div class="col-md-6">
              <label class="form-label-gold" for="fphone">Phone / WhatsApp <span style="color:var(--gold)">*</span></label>
              <input type="tel" class="form-control-gold" id="fphone" placeholder="+92 300 0000000" autocomplete="tel" required>
            </div>
          </div>
          <div class="mb-3">
            <label class="form-label-gold" for="femail">Email Address</label>
            <input type="email" class="form-control-gold" id="femail" placeholder="your@email.com" autocomplete="email">
          </div>
          <div class="mb-3">
            <label class="form-label-gold" for="faddress">Delivery Address <span style="color:var(--gold)">*</span></label>
            <input type="text" class="form-control-gold" id="faddress" placeholder="Street, sector, city" autocomplete="street-address" required>
          </div>
          <div class="mb-3">
            <label class="form-label-gold" for="fmessage">Your Order / Special Request <span style="color:var(--gold)">*</span></label>
            <textarea class="form-control-gold" rows="4" id="fmessage"
              placeholder="E.g. 'One Ferrero Rocher cake (2.5 lbs), custom message: Happy Birthday Sara'" required></textarea>
          </div>
          <div class="row g-3 mb-4">
            <div class="col-md-6">
              <label class="form-label-gold" for="fdate">Preferred Delivery Date</label>
              <input type="date" class="form-control-gold" id="fdate">
            </div>
            <div class="col-md-6">
              <label class="form-label-gold" for="ftime">Preferred Time</label>
              <input type="time" class="form-control-gold" id="ftime">
            </div>
          </div>
          <div class="d-flex gap-3 flex-wrap">
            <button class="btn-gold flex-grow-1" onclick="submitOrder()">
              <i class="fas fa-paper-plane" aria-hidden="true" style="margin-right:0.5rem"></i>Send Order Request
            </button>
            <button class="btn-outline-gold" onclick="orderWhatsApp()" style="flex-shrink:0" title="Order via WhatsApp">
              <i class="fab fa-whatsapp" aria-hidden="true" style="margin-right:0.4rem"></i>WhatsApp
            </button>
          </div>
          <p style="font-size:0.8rem;color:var(--text-muted);margin-top:1rem;font-style:italic">
            <i class="fas fa-info-circle" aria-hidden="true" style="color:var(--gold);margin-right:0.3rem"></i>
            Fields marked <span style="color:var(--gold)">*</span> are required. We'll confirm your order within 2 hours.
          </p>
        </div>
      </div>

<div class="col-lg-5 fade-in delay-1">
       <div style="overflow:hidden;height:180px;margin-bottom:1.2rem;border-radius:var(--radius);border:var(--border-gold)">
          <img src="https://images.unsplash.com/photo-1517433670267-08bbd4be890f?w=800&q=80"
            alt="MAT Bakeshop interior" loading="lazy"
            style="width:100%;height:180px;object-fit:cover;filter:brightness(0.72);transition:filter 0.4s"
            onmouseover="this.style.filter='brightness(0.9)'" onmouseout="this.style.filter='brightness(0.72)'">
        </div>
        <div class="contact-info-box mb-3">
          <h4 style="font-family:'Dancing Script',cursive;color:var(--gold);font-size:1.5rem;margin-bottom:1.25rem">
            Find Us 🎀
          </h4>
          <div class="contact-info-item">
            <div class="contact-icon" aria-hidden="true"><i class="fas fa-map-marker-alt"></i></div>
            <div>
              <h6>Location</h6>
              <p>Islamabad, Pakistan</p>
            </div>
          </div>
          <div class="contact-info-item">
            <div class="contact-icon" aria-hidden="true"><i class="fab fa-whatsapp"></i></div>
            <div>
              <h6>WhatsApp / Phone</h6>
              <p><a href="https://wa.me/923000000000" style="color:var(--text-muted);text-decoration:none" target="_blank" rel="noopener">+92 300 0000000</a></p>
            </div>
          </div>
          <div class="contact-info-item">
            <div class="contact-icon" aria-hidden="true"><i class="fas fa-envelope"></i></div>
            <div>
              <h6>Email</h6>
              <p><a href="mailto:matbakeshop@gmail.com" style="color:var(--text-muted);text-decoration:none">matbakeshop@gmail.com</a></p>
            </div>
          </div>
          <div class="contact-info-item">
            <div class="contact-icon" aria-hidden="true"><i class="fas fa-clock"></i></div>
            <div>
              <h6>Opening Hours</h6>
              <p>Mon–Sat: 9am – 9pm<br>Sun: 10am – 7pm</p>
            </div>
          </div>
        </div>
        <div class="social-wrap">
          <p>Follow Us 🎀</p>
          <small>Stay updated with our latest creations</small>
          <div class="social-links">
            <a href="#" class="social-link" aria-label="Follow us on Instagram"><i class="fab fa-instagram" aria-hidden="true"></i></a>
            <a href="#" class="social-link" aria-label="Follow us on Facebook"><i class="fab fa-facebook-f" aria-hidden="true"></i></a>
            <a href="https://wa.me/923000000000" class="social-link" aria-label="Message us on WhatsApp" target="_blank" rel="noopener"><i class="fab fa-whatsapp" aria-hidden="true"></i></a>
            <a href="#" class="social-link" aria-label="Follow us on TikTok"><i class="fab fa-tiktok" aria-hidden="true"></i></a>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══════════════ FOOTER ═══════════════ -->
<footer role="contentinfo">
  <div class="footer-top-deco" aria-hidden="true">🎀 &nbsp; ✦ &nbsp; 🎀 &nbsp; ✦ &nbsp; 🎀 &nbsp; ✦ &nbsp; 🎀</div>
  <div class="container">
    <div class="row g-4">
      <div class="col-lg-4 col-md-6">
        <div class="footer-brand">🎀 MAT Bakeshop</div>
        <p class="footer-tagline mt-2">
          Maryam · Ali · Taloot<br>
          Baked with Love, Served with Joy
        </p>
        <div class="social-links mt-3">
          <a href="#" class="social-link" aria-label="Instagram"><i class="fab fa-instagram" aria-hidden="true"></i></a>
          <a href="#" class="social-link" aria-label="Facebook"><i class="fab fa-facebook-f" aria-hidden="true"></i></a>
          <a href="https://wa.me/923000000000" class="social-link" aria-label="WhatsApp" target="_blank" rel="noopener"><i class="fab fa-whatsapp" aria-hidden="true"></i></a>
          <a href="#" class="social-link" aria-label="TikTok"><i class="fab fa-tiktok" aria-hidden="true"></i></a>
        </div>
      </div>
      <div class="col-lg-2 col-md-6">
        <h6 class="footer-heading">Quick Links</h6>
        <ul class="footer-links">
          <li><a href="#home">Home</a></li>
          <li><a href="#menu">Our Menu</a></li>
          <li><a href="#about">About Us</a></li>
          <li><a href="#video">Watch Us Bake</a></li>
          <li><a href="#contact">Order Now</a></li>
        </ul>
      </div>
      <div class="col-lg-3 col-md-6">
        <h6 class="footer-heading">Our Specialties</h6>
        <ul class="footer-links">
          <li><a href="#menu">Signature Cakes</a></li>
          <li><a href="#menu">Chocolate Lava Cake</a></li>
          <li><a href="#menu">Cheesecakes</a></li>
          <li><a href="#menu">Pastries &amp; Croissants</a></li>
          <li><a href="#menu">Chocolate Truffles</a></li>
        </ul>
      </div>
      <div class="col-lg-3 col-md-6">
        <h6 class="footer-heading">Contact</h6>
        <ul class="footer-links">
          <li><a href="#contact">📍 Islamabad, Pakistan</a></li>
          <li><a href="https://wa.me/923000000000" target="_blank" rel="noopener">📞 +92 300 0000000</a></li>
          <li><a href="mailto:matbakeshop@gmail.com">✉️ matbakeshop@gmail.com</a></li>
          <li><a href="#contact">⏰ Mon–Sat: 9am – 9pm</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>© 2024 MAT Bakeshop — Maryam · Ali · Taloot 🎀 All Rights Reserved</p>
      <p style="margin-top:0.25rem;font-size:0.78rem">Made with ❤️ in Islamabad, Pakistan</p>
    </div>
  </div>
</footer>

<!-- ═══════════════ CART SIDEBAR ═══════════════ -->
<div class="cart-overlay" id="cartOverlay" onclick="closeCart()" aria-hidden="true"></div>
<aside class="cart-sidebar" id="cartSidebar" aria-label="Shopping cart" aria-hidden="true">
  <div class="cart-header">
    <h4>🎀 My Cart</h4>
    <button class="cart-close" onclick="closeCart()" aria-label="Close cart">
      <i class="fas fa-times" aria-hidden="true"></i>
    </button>
  </div>
  <div class="cart-items" id="cartItems" role="list">
    <div class="cart-empty-state">
      <i class="fas fa-shopping-bag" aria-hidden="true"></i>
      <p>Your cart is empty</p>
      <small>Add some treats! 🎀</small>
    </div>
  </div>
  <div class="cart-footer">
    <div class="cart-total-row">
      <span class="label">Order Total</span>
      <span class="amount" id="cartTotal">Rs. 0</span>
    </div>
    <button class="btn-gold w-100 mb-2" onclick="checkout()">
      <i class="fas fa-check-circle" aria-hidden="true" style="margin-right:0.4rem"></i>Place Order 🎀
    </button>
    <button class="btn-outline-gold w-100" onclick="orderWhatsAppCart()">
      <i class="fab fa-whatsapp" aria-hidden="true" style="margin-right:0.4rem"></i>Order via WhatsApp
    </button>
    <button onclick="clearCart()" style="background:none;border:none;color:var(--text-muted);font-size:0.8rem;width:100%;margin-top:0.75rem;cursor:pointer;font-family:'Cormorant Garamond',serif;letter-spacing:1px">
      Clear cart
    </button>
  </div>
</aside>

<!-- ═══════════════ TOAST ═══════════════ -->
<div class="toast-custom" id="toast" role="status" aria-live="polite">
  <span aria-hidden="true">🎀</span><span id="toastMsg">Added to cart!</span>
</div>

<!-- WhatsApp floating button -->
<a href="https://wa.me/923000000000" class="wa-float" target="_blank" rel="noopener"
   aria-label="Chat on WhatsApp">
  <i class="fab fa-whatsapp" aria-hidden="true"></i>
</a>
<div class="wa-tooltip" aria-hidden="true">Chat with us on WhatsApp</div>

<!-- ═══════════════ ORDER MODAL ═══════════════ -->
<div class="modal fade" id="orderModal" tabindex="-1" aria-labelledby="orderModalLabel" aria-modal="true">
  <div class="modal-dialog modal-dialog-centered">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="orderModalLabel">Order Request Sent! 🎀</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body" style="padding:2rem">
        <div style="text-align:center;margin-bottom:1.5rem">
          <div style="font-size:3.5rem;margin-bottom:0.5rem">🎂</div>
          <p style="font-family:'Dancing Script',cursive;color:var(--gold);font-size:1.6rem;margin:0">Thank you!</p>
          <p style="color:var(--text-muted);font-style:italic;font-size:0.95rem;margin-top:0.4rem">
            We'll contact you within 2 hours to confirm your order.
          </p>
        </div>
        <div id="orderSummaryContent" role="list"></div>
      </div>
      <div class="modal-footer" style="gap:0.75rem">
        <button class="btn-outline-gold" onclick="orderWhatsAppCart()" data-bs-dismiss="modal">
          <i class="fab fa-whatsapp" aria-hidden="true" style="margin-right:0.4rem"></i>Confirm on WhatsApp
        </button>
        <button class="btn-gold" data-bs-dismiss="modal">Continue Shopping</button>
      </div>
    </div>
  </div>
</div>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
<script>
/* ═══════════════════════════════════════════
   CART STATE
═══════════════════════════════════════════ */
let cart = [];
try { cart = JSON.parse(localStorage.getItem('matCart') || '[]'); } catch(e) { cart = []; }

function saveCart() {
  try { localStorage.setItem('matCart', JSON.stringify(cart)); } catch(e) {}
}

function updateBadge() {
  const total = cart.reduce((s, i) => s + i.qty, 0);
  const badge = document.getElementById('cartBadge');
  badge.textContent = total;
  badge.classList.toggle('show', total > 0);
  badge.style.display = total > 0 ? 'flex' : 'none';
}

/* ═══════════════════════════════════════════
   CART OPERATIONS
═══════════════════════════════════════════ */
function addToCart(name, price, emoji) {
  const existing = cart.find(i => i.name === name);
  if (existing) {
    existing.qty++;
  } else {
    cart.push({ name, price, emoji, qty: 1 });
  }
  saveCart();
  updateBadge();
  renderCart();
  showToast(name + ' added to cart!');
  spawnSparkles();
}

function changeQty(name, delta) {
  const item = cart.find(i => i.name === name);
  if (!item) return;
  item.qty += delta;
  if (item.qty <= 0) cart = cart.filter(i => i.name !== name);
  saveCart();
  updateBadge();
  renderCart();
}

function clearCart() {
  cart = [];
  saveCart();
  updateBadge();
  renderCart();
}

function renderCart() {
  const container = document.getElementById('cartItems');
  const totalEl = document.getElementById('cartTotal');
  if (!container) return;

  if (cart.length === 0) {
    container.innerHTML = `
      <div class="cart-empty-state">
        <i class="fas fa-shopping-bag" aria-hidden="true"></i>
        <p>Your cart is empty</p>
        <small>Add some treats! 🎀</small>
      </div>`;
    if (totalEl) totalEl.textContent = 'Rs. 0';
    return;
  }

  container.innerHTML = cart.map(item => `
    <div class="cart-item" role="listitem">
      <span class="ci-emoji" aria-hidden="true">${item.emoji}</span>
      <div class="ci-info">
        <div class="ci-name">${escapeHtml(item.name)}</div>
        <div class="ci-price">Rs. ${(item.price * item.qty).toLocaleString()}</div>
      </div>
      <div class="ci-qty">
        <button class="qty-btn" onclick="changeQty('${escapeHtml(item.name)}',-1)" aria-label="Remove one ${escapeHtml(item.name)}">−</button>
        <span class="qty-num" aria-label="Quantity">${item.qty}</span>
        <button class="qty-btn" onclick="changeQty('${escapeHtml(item.name)}',1)" aria-label="Add one more ${escapeHtml(item.name)}">+</button>
      </div>
    </div>`).join('');

  const total = cart.reduce((s, i) => s + i.price * i.qty, 0);
  if (totalEl) totalEl.textContent = 'Rs. ' + total.toLocaleString();
}

function openCart() {
  document.getElementById('cartSidebar').classList.add('open');
  document.getElementById('cartSidebar').setAttribute('aria-hidden', 'false');
  document.getElementById('cartOverlay').classList.add('open');
  document.body.style.overflow = 'hidden';
  renderCart();
}

function closeCart() {
  document.getElementById('cartSidebar').classList.remove('open');
  document.getElementById('cartSidebar').setAttribute('aria-hidden', 'true');
  document.getElementById('cartOverlay').classList.remove('open');
  document.body.style.overflow = '';
}

/* ═══════════════════════════════════════════
   CHECKOUT
═══════════════════════════════════════════ */
function checkout() {
  if (cart.length === 0) { showToast('Your cart is empty! Add something first. 🎀'); return; }
  const total = cart.reduce((s, i) => s + i.price * i.qty, 0);
  const rows = cart.map(i =>
    `<div class="order-summary-item" role="listitem">
      <span>${i.emoji} ${escapeHtml(i.name)} × ${i.qty}</span>
      <span>Rs. ${(i.price * i.qty).toLocaleString()}</span>
    </div>`
  ).join('');
  document.getElementById('orderSummaryContent').innerHTML =
    `<div role="list">${rows}</div>
     <div class="order-grand-total"><span>Grand Total</span><span>Rs. ${total.toLocaleString()}</span></div>`;
  closeCart();
  new bootstrap.Modal(document.getElementById('orderModal')).show();
  clearCart();
}

/* ═══════════════════════════════════════════
   WHATSAPP ORDER
═══════════════════════════════════════════ */
function buildWhatsAppMessage() {
  if (cart.length === 0) return null;
  const lines = cart.map(i => `• ${i.name} × ${i.qty} = Rs. ${(i.price * i.qty).toLocaleString()}`).join('\n');
  const total = cart.reduce((s, i) => s + i.price * i.qty, 0);
  return `Hello MAT Bakeshop! 🎀\n\nI'd like to place an order:\n\n${lines}\n\n*Total: Rs. ${total.toLocaleString()}*\n\nPlease confirm availability and delivery details. Thank you!`;
}

function orderWhatsAppCart() {
  const msg = buildWhatsAppMessage();
  if (!msg) { showToast('Add items to cart first! 🎀'); return; }
  window.open('https://wa.me/923000000000?text=' + encodeURIComponent(msg), '_blank', 'noopener');
}

function orderWhatsApp() {
  const name    = document.getElementById('fname').value.trim();
  const phone   = document.getElementById('fphone').value.trim();
  const address = document.getElementById('faddress').value.trim();
  const order   = document.getElementById('fmessage').value.trim();
  const date    = document.getElementById('fdate').value;
  const time    = document.getElementById('ftime').value;

  if (!name || !phone || !order) {
    showToast('Please fill in Name, Phone & Order first! 🎀');
    return;
  }
  let msg = `Hello MAT Bakeshop! 🎀\n\n*Name:* ${name}\n*Phone:* ${phone}`;
  if (address) msg += `\n*Address:* ${address}`;
  msg += `\n\n*Order:* ${order}`;
  if (date) msg += `\n*Delivery Date:* ${date}`;
  if (time) msg += `\n*Preferred Time:* ${time}`;
  msg += '\n\nPlease confirm! Thank you 🎀';
  window.open('https://wa.me/923000000000?text=' + encodeURIComponent(msg), '_blank', 'noopener');
}

/* ═══════════════════════════════════════════
   CONTACT FORM SUBMIT
═══════════════════════════════════════════ */
function submitOrder() {
  const name  = document.getElementById('fname').value.trim();
  const phone = document.getElementById('fphone').value.trim();
  const addr  = document.getElementById('faddress').value.trim();
  const msg   = document.getElementById('fmessage').value.trim();

  if (!name)  { showToast('Please enter your name. 🎀'); document.getElementById('fname').focus(); return; }
  if (!phone) { showToast('Please enter your phone number. 🎀'); document.getElementById('fphone').focus(); return; }
  if (!addr)  { showToast('Please enter your delivery address. 🎀'); document.getElementById('faddress').focus(); return; }
  if (!msg)   { showToast('Please describe your order. 🎀'); document.getElementById('fmessage').focus(); return; }

  showToast('Order sent! We\'ll contact you within 2 hours. 🎀');
  ['fname','fphone','femail','faddress','fmessage','fdate','ftime'].forEach(id => {
    const el = document.getElementById(id);
    if (el) el.value = '';
  });
}

/* ═══════════════════════════════════════════
   MENU FILTERING & SEARCH
═══════════════════════════════════════════ */
let currentCat = 'all';
let currentSearch = '';

function filterMenu(cat, btn) {
  currentCat = cat;
  document.querySelectorAll('.cat-tab').forEach(b => {
    b.classList.remove('active');
    b.setAttribute('aria-selected', 'false');
  });
  btn.classList.add('active');
  btn.setAttribute('aria-selected', 'true');
  applyFilters();
}

function handleSearch(query) {
  currentSearch = query.toLowerCase().trim();
  applyFilters();
}

function applyFilters() {
  const items = document.querySelectorAll('.menu-item');
  let visibleCount = 0;

  items.forEach(item => {
    const catMatch = currentCat === 'all' || item.dataset.cat.includes(currentCat);
    const nameMatch = !currentSearch || item.dataset.name.includes(currentSearch);
    const show = catMatch && nameMatch;

    if (show) {
      item.style.display = '';
      item.style.animation = 'fadeInUp 0.35s ease';
      visibleCount++;
    } else {
      item.style.display = 'none';
    }
  });

  const noResults = document.getElementById('noResults');
  noResults.style.display = visibleCount === 0 ? 'block' : 'none';
}

/* ═══════════════════════════════════════════
   TOAST
═══════════════════════════════════════════ */
let toastTimer;
function showToast(msg) {
  const toast = document.getElementById('toast');
  document.getElementById('toastMsg').textContent = msg;
  toast.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer = setTimeout(() => toast.classList.remove('show'), 3200);
}

/* ═══════════════════════════════════════════
   SPARKLE EFFECT
═══════════════════════════════════════════ */
function spawnSparkles() {
  const emojis = ['✨', '🎀', '⭐', '💫'];
  for (let i = 0; i < 5; i++) {
    setTimeout(() => {
      const el = document.createElement('div');
      el.setAttribute('aria-hidden', 'true');
      el.style.cssText = [
        'position:fixed',
        'pointer-events:none',
        `font-size:${(Math.random() * 0.9 + 0.7).toFixed(1)}rem`,
        `left:${(Math.random() * 100).toFixed(1)}vw`,
        `top:${(Math.random() * 100).toFixed(1)}vh`,
        'z-index:9999',
        'animation:sparkleUp 1.3s ease forwards'
      ].join(';');
      el.textContent = emojis[Math.floor(Math.random() * emojis.length)];
      document.body.appendChild(el);
      setTimeout(() => el.remove(), 1300);
    }, i * 80);
  }
}

/* ═══════════════════════════════════════════
   SCROLL-BASED EFFECTS
═══════════════════════════════════════════ */
// Fade-in observer
const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
      observer.unobserve(entry.target);
    }
  });
}, { threshold: 0.08 });
document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));

// Navbar scroll state + active link
const navSections = ['home', 'menu', 'about', 'video', 'contact'];
window.addEventListener('scroll', () => {
  // Navbar shadow
  document.getElementById('mainNav').classList.toggle('scrolled', window.scrollY > 50);

  // Active link
  let current = '';
  navSections.forEach(id => {
    const el = document.getElementById(id);
    if (el && window.scrollY >= el.offsetTop - 120) current = id;
  });
  document.querySelectorAll('.nav-link').forEach(link => {
    link.classList.remove('active');
    if (link.getAttribute('href') === '#' + current) link.classList.add('active');
  });
}, { passive: true });

/* ═══════════════════════════════════════════
   ESCAPE HTML (XSS prevention)
═══════════════════════════════════════════ */
function escapeHtml(str) {
  return String(str)
    .replace(/&/g, '&amp;')
    .replace(/</g, '&lt;')
    .replace(/>/g, '&gt;')
    .replace(/"/g, '&quot;')
    .replace(/'/g, '&#39;');
}

/* ═══════════════════════════════════════════
   KEYBOARD: close cart on Escape
═══════════════════════════════════════════ */
document.addEventListener('keydown', e => {
  if (e.key === 'Escape') closeCart();
});

/* ═══════════════════════════════════════════
   INJECT KEYFRAME ANIMATIONS
═══════════════════════════════════════════ */
const style = document.createElement('style');
style.textContent = `
  @keyframes sparkleUp{
    0%{opacity:0;transform:scale(0) translateY(0)}
    40%{opacity:1;transform:scale(1.3) translateY(-16px)}
    100%{opacity:0;transform:scale(0.4) translateY(-38px)}
  }
  @keyframes fadeInUp{
    from{opacity:0;transform:translateY(10px)}
    to{opacity:1;transform:translateY(0)}
  }
`;
document.head.appendChild(style);

/* ═══════════════════════════════════════════
   INIT
═══════════════════════════════════════════ */
updateBadge();
renderCart();
</script>
</body>
</html>
