# Examples — Nou Segle 12 Prototype

Concrete voorbeelden van wat we willen én niet willen, per element.
Gebruik dit als snelle referentie naast CLAUDE.md en brand-assets.md.

---

## Homepage-structuur

### ✅ Wat we willen — gebaseerd op BRUT + El Camino + eigenaarswens

```
┌─────────────────────────────────────────────┐
│  [Logo]   Inicio  Carta  Quiénes  Contacto  │  ← sticky navigatie, wit, subtiel
│                                    ES/DE/EN/FR│
├─────────────────────────────────────────────┤
│                                             │
│         GROTE HERO-FOTO (volledig breed)    │  ← restaurant/terras/plein
│         terras, sfeer, Capdepera            │
│                                             │
│   Nou Segle 12                              │  ← naam groot, wit, links uitgelijnd
│   Corazón del plein de Capdepera            │  ← 1 zin, roze (#f4aeb7)
│                                             │
│   [ Reservar por WhatsApp ]                 │  ← groene pill-knop
├─────────────────────────────────────────────┤
│                                             │
│   [Foto Michel]  Michel Heijman             │  ← 2 kolommen: foto links, tekst rechts
│                  De ziel van het restaurant │
│                  Korte persoonlijke tekst   │
│                  [Meer over Michel →]       │
│                                             │
├─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─│  ← dunne lijn, geen kleurblok
│                                             │
│   [foto]  [foto]  [foto]  [foto]  [foto]   │  ← fotogalerij, breed, weinig tekst
│                                             │
├─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─│
│                                             │
│   Lu-Do 08:30–23:00   Plaza de L'Orient 1  │  ← praktisch blok, lichte achtergrond
│   [ Reservar por WhatsApp ]                 │
│                                             │
├─────────────────────────────────────────────┤
│  © Nou Segle 12  ·  Aviso Legal  ·  Privacy │  ← minimale footer, 1 regel
└─────────────────────────────────────────────┘
```

### ❌ Wat we NIET willen

```
┌─────────────────────────────────────────────┐
│          DONKERE HEADER MET LOGO            │  ← te donker, te zwaar
├─────────────────────────────────────────────┤
│  █████████ BORDEAUXROOD BLOK ██████████████ │  ← volle kleurvlakken
│  Welkom bij ons geweldige restaurant!        │
├─────────────────────────────────────────────┤
│  ██████████ PAARS BLOK ████████████████████ │  ← blok na blok na blok
│  Openingstijden en informatie               │
└─────────────────────────────────────────────┘
```

---

## Hero-sectie — goede vs. slechte implementatie

### ✅ Goed: foto als basis, tekst over overlay
```css
.hero {
  position: relative;
  height: 85vh;
  background-image: url('foto-terras.jpg');
  background-size: cover;
  background-position: center;
}

.hero-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to top,
    rgba(89, 16, 61, 0.55) 0%,
    transparent 60%
  );
}

.hero-content {
  position: absolute;
  bottom: 48px;
  left: 48px;
}
```

### ❌ Slecht: effen kleurvlak als "hero"
```css
/* NIET DOEN */
.hero {
  background: #7e1041;  /* effen bordeauxrood zonder foto */
  padding: 120px 40px;
  text-align: center;
}
```

---

## Michel-sectie — tweekolomsopzet

### ✅ Goed: foto en tekst naast elkaar, rustig
```html
<section class="michel">
  <div class="michel-foto">
    <img src="michel.jpg" alt="Michel Heijman, anfitrión de Nou Segle 12">
  </div>
  <div class="michel-tekst">
    <span class="label">El alma del restaurante</span>
    <h2>Michel Heijman</h2>
    <p>Lleva más de 20 años...</p>
    <a href="quienes-somos.html">Conoce a Michel →</a>
  </div>
</section>
```

```css
.michel {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 64px;
  align-items: center;
  padding: 80px 40px;
  max-width: 1100px;
  margin: 0 auto;
}

.michel-foto img {
  width: 100%;
  border-radius: 12px;
  aspect-ratio: 4/5;
  object-fit: cover;
}

.michel-tekst .label {
  font-size: 12px;
  font-weight: 300;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: #7a7a7a;
}

.michel-tekst h2 {
  font-size: 32px;
  font-weight: 800;
  color: #59103d;
  margin: 8px 0 16px;
}
```

---

## Knoppen — correct gebruik

### ✅ Primaire CTA (WhatsApp)
```html
<a href="https://wa.me/34XXXXXXXXX?text=..." class="btn-whatsapp">
  Reservar por WhatsApp
</a>
```
```css
.btn-whatsapp {
  display: inline-block;
  background: #61a229;
  color: #ffffff;
  font-family: 'Heebo', sans-serif;
  font-weight: 600;
  font-size: 14px;
  padding: 14px 32px;
  border-radius: 28px;
  text-decoration: none;
}
```

### ✅ Secundaire knop (meer info)
```html
<a href="quienes-somos.html" class="btn-secundair">
  Conoce a Michel →
</a>
```
```css
.btn-secundair {
  color: #7e1041;
  font-weight: 600;
  font-size: 14px;
  text-decoration: none;
  border-bottom: 1px solid #7e1041;
  padding-bottom: 2px;
}
```

### ❌ Fout: knop met volle Primary-kleur voor iets dat geen reservering is
```css
/* NIET DOEN voor een "lees meer"-knop */
.btn {
  background: #7e1041;  /* reserveer hier de groene knop voor WhatsApp */
}
```

---

## Fotogalerij — simpel grid

### ✅ Goed: clean grid, geen tekst, foto's spreken voor zich
```html
<section class="galerij">
  <div class="galerij-grid">
    <img src="foto1.jpg" alt="Tapas Nou Segle 12">
    <img src="foto2.jpg" alt="Terras Capdepera">
    <img src="foto3.jpg" alt="Sfeer restaurant">
    <img src="foto4.jpg" alt="Gerecht Michel">
    <img src="foto5.jpg" alt="Plaza de L'Orient">
    <img src="foto6.jpg" alt="Team Nou Segle 12">
  </div>
</section>
```

```css
.galerij {
  padding: 48px 40px;
  max-width: 1100px;
  margin: 0 auto;
}

.galerij-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 8px;
}

.galerij-grid img {
  width: 100%;
  aspect-ratio: 1;
  object-fit: cover;
  border-radius: 4px;
}
```

---

## Footer — minimaal

### ✅ Goed: één regel, subtiel
```html
<footer class="footer">
  <div class="footer-content">
    <span>Plaza de L'Orient 1, Capdepera · +34 871 201 276</span>
    <div class="footer-links">
      <a href="#">Aviso Legal</a>
      <a href="#">Privacidad</a>
      <a href="#">Cookies</a>
    </div>
    <div class="footer-social">
      <!-- Instagram icoon -->
      <!-- Facebook icoon -->
    </div>
  </div>
</footer>
```

```css
.footer {
  border-top: 1px solid #e8e0e0;
  padding: 24px 40px;
  font-size: 12px;
  color: #7a7a7a;
}

.footer-content {
  max-width: 1100px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

### ❌ Fout: grote gekleurde footer-balk
```css
/* NIET DOEN — dit was de oude site, dit bouwen we weg */
footer {
  background: #6b5770;
  padding: 60px;
  color: white;
}
```

---

## Responsief gedrag (mobiel)

De meeste bezoekers zijn toeristen op een telefoon.
Gebruik deze breakpoints als referentie:

```css
/* Desktop: > 768px — twee kolommen, ruime padding */
/* Tablet: 480–768px — één kolom, kolommen stapelen */
/* Mobiel: < 480px — één kolom, kleinere padding (20px) */

@media (max-width: 768px) {
  .michel {
    grid-template-columns: 1fr;  /* stapelen, foto boven tekst */
  }

  .galerij-grid {
    grid-template-columns: repeat(2, 1fr);  /* 2 kolommen op mobiel */
  }

  .hero-content {
    left: 20px;
    bottom: 32px;
  }

  .hero h1 {
    font-size: 32px;  /* kleiner op mobiel */
  }
}
```

---

## Wat dit prototype NIET hoeft te kunnen

- Echte taalwisseling (Polylang doet dat in WordPress — prototype toont alleen Spaans)
- Echte WhatsApp-verbinding (link mag placeholder zijn met `XXXXXXXXX` als nummer)
- Echte Google Maps (mag een screenshot of statische afbeelding zijn)
- Animaties bij scrollen (niet nabouwbaar in Elementor gratis)
- Inloggen, winkelwagen, formulierverwerking
- Perfecte pixel-exacte mobiele optimalisatie (globale aanpak volstaat voor prototype)
