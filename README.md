# header-harley-v2
/*
  FICHIER: assets/header-harley-v2.css
  EMPLACEMENT: /assets/header-harley-v2.css
  
  Header Harley Vape avec :
  - Effet fumée autour du logo
  - Mobile sticky fonctionnel
  - Relief authentique conservé
  - Z-index optimisé
*/

/* === 🎯 HEADER RELIEF AUTHENTIQUE OPTIMISÉ === */
.site-header {
  background: linear-gradient(180deg, 
    #f8f4e6 0%,
    #f0e8d0 25%, 
    #e8dab8 50%,
    #e0cc9f 75%,
    #d8bf86 100%
  );
  position: relative;
  z-index: 50; /* RÉDUIT pour éviter conflicts */
  padding: 20px 0 24px;
  
  /* Relief authentique - multiples couches d'ombres */
  box-shadow: 
    /* Ombre principale forte */
    0 4px 12px rgba(0, 0, 0, 0.15),
    /* Ombre colorée brand */
    0 8px 24px rgba(139, 69, 19, 0.12),
    /* Ombre profonde */
    0 12px 40px rgba(160, 82, 45, 0.08),
    /* Inset top pour relief */
    inset 0 2px 0 rgba(255, 255, 255, 0.6),
    /* Inset bottom pour profondeur */
    inset 0 -2px 0 rgba(139, 69, 19, 0.15),
    /* Inset sides pour volume */
    inset 4px 0 8px rgba(218, 191, 134, 0.25),
    inset -4px 0 8px rgba(218, 191, 134, 0.25);
  
  /* Bordure solide avec relief */
  border-top: 3px solid #f5f1e3;
  border-bottom: 4px solid #8b4513;
  border-left: none;
  border-right: none;
  
  transition: all 0.3s ease;
}

/* Bandes décoratives pour relief supplémentaire */
.site-header::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 2px;
  background: linear-gradient(90deg, 
    transparent,
    rgba(245, 241, 227, 0.8) 20%,
    rgba(255, 255, 255, 0.9) 50%,
    rgba(245, 241, 227, 0.8) 80%,
    transparent
  );
  z-index: 5;
}

.site-header::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 20px;
  right: 20px;
  height: 1px;
  background: linear-gradient(90deg, 
    rgba(139, 69, 19, 0.2),
    rgba(139, 69, 19, 0.6) 50%,
    rgba(139, 69, 19, 0.2)
  );
  z-index: 5;
}

/* === 🎯 LOGO AVEC EFFET FUMÉE/NUAGE === */
.header-item--logo {
  position: relative;
  display: flex;
  align-items: center;
  z-index: 60; /* Plus haut que header mais contrôlé */
  overflow: visible;
}

/* 💨 EFFET FUMÉE - Nuage 1 (gauche) */
.header-item--logo::before {
  content: '';
  position: absolute;
  top: -8px;
  left: -15px;
  width: 25px;
  height: 25px;
  background: radial-gradient(circle, 
    rgba(255, 255, 255, 0.8) 0%,
    rgba(248, 244, 230, 0.6) 40%,
    rgba(240, 232, 208, 0.3) 70%,
    transparent 100%
  );
  border-radius: 50% 60% 40% 50%;
  filter: blur(1px);
  opacity: 0.8;
  z-index: -1;
  
  /* Animation flottante */
  animation: float-left 4s ease-in-out infinite;
}

/* 💨 EFFET FUMÉE - Nuage 2 (droite) */
.header-item--logo::after {
  content: '';
  position: absolute;
  top: -12px;
  right: -20px;
  width: 30px;
  height: 20px;
  background: radial-gradient(ellipse, 
    rgba(255, 255, 255, 0.7) 0%,
    rgba(248, 244, 230, 0.5) 50%,
    rgba(232, 218, 184, 0.2) 80%,
    transparent 100%
  );
  border-radius: 60% 40% 50% 60%;
  filter: blur(0.8px);
  opacity: 0.7;
  z-index: -1;
  
  /* Animation flottante décalée */
  animation: float-right 5s ease-in-out infinite reverse;
}

/* 🌊 ANIMATIONS FLOTTANTES */
@keyframes float-left {
  0%, 100% { 
    transform: translateY(0px) scale(1);
    opacity: 0.8;
  }
  25% { 
    transform: translateY(-3px) scale(1.05);
    opacity: 0.9;
  }
  50% { 
    transform: translateY(-2px) scale(0.95);
    opacity: 0.7;
  }
  75% { 
    transform: translateY(-4px) scale(1.02);
    opacity: 0.85;
  }
}

@keyframes float-right {
  0%, 100% { 
    transform: translateY(0px) translateX(0px) scale(1);
    opacity: 0.7;
  }
  30% { 
    transform: translateY(-2px) translateX(2px) scale(1.08);
    opacity: 0.8;
  }
  60% { 
    transform: translateY(-5px) translateX(-1px) scale(0.92);
    opacity: 0.6;
  }
  80% { 
    transform: translateY(-3px) translateX(1px) scale(1.03);
    opacity: 0.75;
  }
}

/* 🎯 EFFET AU HOVER - Fumée plus intense */
.header-item--logo:hover::before {
  width: 30px;
  height: 30px;
  opacity: 1;
  filter: blur(0.8px);
  animation-duration: 2.5s;
}

.header-item--logo:hover::after {
  width: 35px;
  height: 25px;
  opacity: 0.9;
  filter: blur(0.6px);
  animation-duration: 3s;
}

/* 🎨 AJUSTEMENT DU LOGO */
.header-item--logo img {
  height: auto !important;
  max-height: 65px !important; 
  width: auto !important;
  transform: scale(1.7); 
  transform-origin: center;
  
  /* Relief logo authentique */
  filter: 
    drop-shadow(3px 3px 0 #ff9900) 
    drop-shadow(-2px -2px 0 #cc5500)
    drop-shadow(0 6px 12px rgba(0, 0, 0, 0.3))
    drop-shadow(0 12px 24px rgba(139, 69, 19, 0.2))
    contrast(1.15)
    saturate(1.2);
  
  position: relative;
  z-index: 10;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.header-item--logo:hover img {
  transform: scale(1.8) rotate(1deg);
  filter: 
    drop-shadow(4px 4px 0 #ff9900) 
    drop-shadow(-3px -3px 0 #cc5500)
    drop-shadow(0 8px 16px rgba(0, 0, 0, 0.35))
    drop-shadow(0 16px 32px rgba(139, 69, 19, 0.25))
    contrast(1.2)
    saturate(1.25);
}

/* === 🔥 BADGE PROMO === */
.badge-promo {
  position: absolute;
  top: -12px;
  right: -25px;
  
  background: linear-gradient(145deg, 
    #e53935 0%, 
    #d32f2f 50%, 
    #c62828 100%
  );
  color: white;
  font-size: 10px;
  font-weight: 800;
  padding: 4px 8px 3px;
  border-radius: 12px;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  
  box-shadow: 
    0 3px 8px rgba(211, 47, 47, 0.4),
    0 6px 16px rgba(211, 47, 47, 0.25),
    inset 0 1px 0 rgba(255, 255, 255, 0.4),
    inset 0 -1px 0 rgba(139, 69, 19, 0.3);
  
  transform: rotate(-6deg);
  z-index: 25;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.badge-promo:hover {
  transform: rotate(-4deg) scale(1.05);
  box-shadow: 
    0 4px 12px rgba(211, 47, 47, 0.5),
    0 8px 24px rgba(211, 47, 47, 0.3),
    inset 0 1px 0 rgba(255, 255, 255, 0.5),
    inset 0 -1px 0 rgba(139, 69, 19, 0.4);
}

/* === 🎯 NAVIGATION STYLÉE === */
.site-header .site-nav {
  display: flex;
  align-items: center;
  gap: 30px;
}

.site-header .site-nav__link {
  position: relative;
  color: #5d4037;
  font-weight: 600;
  font-size: 16px;
  text-decoration: none;
  padding: 8px 16px;
  border-radius: 8px;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  text-transform: uppercase;
  letter-spacing: 0.5px;
  font-family: 'Helvetica Neue', Arial, sans-serif;
}

/* Effet hover sophistiqué */
.site-header .site-nav__link::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, 
    transparent,
    rgba(139, 69, 19, 0.1),
    transparent
  );
  border-radius: 8px;
  transition: left 0.5s ease;
}

.site-header .site-nav__link:hover::before {
  left: 100%;
}

/* Underline animée */
.site-header .site-nav__link::after {
  content: '';
  position: absolute;
  bottom: 2px;
  left: 50%;
  width: 0;
  height: 2px;
  background: linear-gradient(90deg, #8b4513, #d2691e);
  border-radius: 1px;
  transform: translateX(-50%);
  transition: width 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.site-header .site-nav__link:hover {
  color: #8b4513;
  background: rgba(139, 69, 19, 0.08);
  transform: translateY(-1px);
  box-shadow: 0 2px 8px rgba(139, 69, 19, 0.15);
}

.site-header .site-nav__link:hover::after {
  width: 80%;
}

/* Style actif */
.site-header .site-nav__link.site-nav__link--active {
  color: #8b4513;
  background: rgba(139, 69, 19, 0.12);
  box-shadow: inset 0 1px 3px rgba(139, 69, 19, 0.2);
}

.site-header .site-nav__link.site-nav__link--active::after {
  width: 90%;
  background: linear-gradient(90deg, #8b4513, #a0522d);
}

/* === 🎯 ICÔNES DROITE === */
.header-item--icons {
  display: flex;
  align-items: center;
  gap: 20px;
}

.header-item--icons a {
  position: relative;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 10px;
  border-radius: 10px;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  background: rgba(255, 255, 255, 0.6);
  box-shadow: 
    0 2px 6px rgba(139, 69, 19, 0.1),
    inset 0 1px 0 rgba(255, 255, 255, 0.8);
}

.header-item--icons a:hover {
  transform: translateY(-2px);
  box-shadow: 
    0 4px 12px rgba(139, 69, 19, 0.15),
    inset 0 1px 0 rgba(255, 255, 255, 0.9);
}

.header-item--icons svg {
  width: 20px !important;
  height: 20px !important;
  color: #5d4037;
  transition: all 0.3s ease;
}

.header-item--icons a:hover svg {
  color: #8b4513;
  transform: scale(1.1);
}

/* === 📱 MOBILE STICKY & RESPONSIVE === */
@media (max-width: 768px) {
  .site-header {
    position: sticky;
    top: 0;
    z-index: 40; /* Plus bas sur mobile */
    padding: 12px 0 16px;
    
    /* Box-shadow plus légère pour mobile */
    box-shadow: 
      0 2px 8px rgba(0, 0, 0, 0.12),
      0 4px 16px rgba(139, 69, 19, 0.08),
      inset 0 1px 0 rgba(255, 255, 255, 0.5),
      inset 0 -1px 0 rgba(139, 69, 19, 0.12);
  }
  
  .header-item--logo img {
    max-height: 45px !important;
    transform: scale(1.2);
  }
  
  .badge-promo {
    font-size: 7px;
    padding: 2px 5px;
    top: -6px;
    right: -12px;
  }
  
  /* Fumée plus petite sur mobile */
  .header-item--logo::before {
    width: 20px;
    height: 20px;
    top: -6px;
    left: -12px;
  }
  
  .header-item--logo::after {
    width: 24px;
    height: 16px;
    top: -8px;
    right: -16px;
  }
  
  .site-header .site-nav {
    gap: 15px;
  }
  
  .site-header .site-nav__link {
    font-size: 14px;
    padding: 6px 12px;
  }
}

@media (max-width: 480px) {
  .header-item--logo img {
    max-height: 40px !important;
    transform: scale(1.1);
  }
  
  .badge-promo {
    font-size: 6px;
    padding: 2px 4px;
    top: -4px;
    right: -8px;
  }
  
  /* Fumée encore plus petite */
  .header-item--logo::before {
    width: 16px;
    height: 16px;
    top: -4px;
    left: -8px;
  }
  
  .header-item--logo::after {
    width: 20px;
    height: 12px;
    top: -6px;
    right: -12px;
  }
}

/* === 🎯 ANNOUNCEMENT BAR === */
.announcement-bar {
  background-color: #8b4513 !important; 
  color: #f8f4e6 !important;
  z-index: 30;
  position: relative;
}

@media (max-width: 768px) {
  .announcement-bar {
    position: sticky;
    top: 0;
    z-index: 35;
  }
  
  /* Si header sticky ET announcement bar sticky */
  .site-header.has-announcement {
    top: 40px; /* Ajuster selon hauteur announcement */
  }
}

/* === 🎯 HIÉRARCHIE Z-INDEX === */
/*
HIÉRARCHIE Z-INDEX CLAIRE :
- 10 : Contenu principal, diaporama
- 30 : Announcement bar
- 35 : Announcement bar mobile
- 40 : Header mobile 
- 45 : Navigation thumb mobile
- 50 : Header desktop
- 60 : Logo avec fumée
- 80 : Navigation ouverte
- 90 : Cart/Drawer overlays
*/

/* === 🎯 ESPACEMENT CONTENU === */
.slideshow, 
.slider-section, 
.hero-slider,
.main-content,
.index-sections {
  position: relative;
  z-index: 10;
}

/* Thumb menu mobile */
@media (max-width: 768px) {
  .site-nav__thumb-menu {
    z-index: 45;
  }
  
  .slide-nav {
    z-index: 80;
  }
  
  .cart-drawer,
  .drawer {
    z-index: 90;
  }
}

/* === 🎯 CORRECTIONS DIVERSES === */

/* Page width container */
.page-width {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Header layout */
.header-layout {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
}

@media (max-width: 768px) {
  .header-layout {
    flex-direction: column;
    gap: 15px;
  }
  
  .header-layout--mobile-logo-only .header-item--icons {
    order: -1;
  }
}
