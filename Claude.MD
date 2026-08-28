# CLAUDE.md — Nou Segle 12 Website Prototype

## Wat is dit project?

Dit is een **interactief HTML/CSS-prototype** van de nieuwe website voor restaurant Nou Segle 12
in Capdepera, Mallorca. Het prototype dient als visuele referentie voor feedback van de eigenaar
én als directe bouwgids voor het nabouwen in **WordPress met Elementor (gratis versie)**.

Het prototype is GEEN productie-code. Het is een klikbaar voorbeeld dat:
- Snel itereerbaar is op basis van feedback van de eigenaar
- Alle layoutbeslissingen vastlegt vóór de bouw in Elementor begint
- Bewust binnen de grenzen blijft van wat Elementor gratis kan nabouwen

---

## Kritische beperking: Elementor gratis versie

**Dit is de belangrijkste technische beperking van het hele project.**
Elke layoutkeuze in dit prototype moet nabouwbaar zijn in Elementor met de gratis versie.

### Wat Elementor gratis WEL kan:
- Containers/secties met achtergrondkleur of achtergrondafbeelding
- Heading, Text Editor, Image, Button widgets
- Image Gallery widget (basisversie)
- Google Maps widget (embed)
- Kolommen naast elkaar (2- of 3-koloms grids)
- Eenvoudige hover-effecten via Elementor's eigen stijlopties
- Sticky header via My Sticky Bar plugin (al actief op de site)
- Padding/margin/spacing aanpassen
- Mobiel-responsief via Elementor's breakpoint-instellingen

### Wat Elementor gratis NIET kan (gebruik dit dus NIET in het prototype):
- CSS Grid-layouts met complexe spanning
- Parallax-scrolleffecten
- Complexe animaties bij scrollen (scroll-triggered animations)
- Overlappende elementen via absolute positioning (tenzij simpel)
- Custom cursor-effecten
- Video-achtergronden (technisch kan het, maar vermijd als het design ervan afhangt)
- Mega-menu's
- Filterable galleries (vereist Essential Addons of HT Mega Pro)
- Countdown-timers, pricing tables, tabs-widget

### Vuistregel:
Als je twijfelt of iets nabouwbaar is: kies de simpelere optie.
Een strak simpel design is beter dan een complex design dat in Elementor half mislukt.

---

## Paginastructuur

De website heeft 4 hoofdpagina's + 3 juridische pagina's.
Het prototype bouwt de 4 hoofdpagina's. Juridische pagina's zijn aparte tekstpagina's,
geen ontwerp nodig.

### Navigatie (alle talen, zelfde volgorde):
```
[Logo] | Inicio | Carta | Quiénes somos | Contacto | [Taalswitcher: ES/DE/EN/FR]
```

### Pagina 1: Home (Inicio)
Volgorde van secties van boven naar onder:
1. **Hero** — grote afbeelding van restaurant/terras/plein, met naam restaurant en 1 korte zin
2. **Michel-sectie** — foto van Michel Heijman + korte introductietekst, dit is het hart van de site
3. **Fotogalerij** — visueel, weinig tekst, sfeer van restaurant/eten/plek
4. **Praktisch blok** — openingstijden + locatie + WhatsApp-reserveerknop
5. **Footer** — minimaal: adres, telefoon, social media-iconen, links naar juridische pagina's

### Pagina 2: Carta (Menu)
- Geen PDF's — HTML-tekst
- Categorieën: Desayuno, Tapas, Ensaladas, Carnes, Pizzas, Postres, Bebidas
- Allergeneninformatie als aparte sectie onderaan
- Simpele, leesbare lay-out — geen fancy filters of tabs

### Pagina 3: Quiénes somos (Over ons)
Volgorde:
1. **Verhaal van het restaurant** — korte alinea, Capdepera/locatie centraal
2. **Michel Heijman** — uitgebreidere versie, foto, persoonlijk verhaal
3. **Manuel Herzog** — chef, foto, korte bio
4. **Teamfoto's** — galerij/slider van het team in actie
5. **Filosofie** — 3-4 korte zinnen over gastvrijheid, lokale ingrediënten, mediterrane sfeer

### Pagina 4: Contacto
1. **Google Maps embed** — restaurant is makkelijk te vinden op de kaart
2. **Adresgegevens + telefoon**
3. **Openingstijden**
4. **WhatsApp reserveerknop** — groot, prominent
5. **Korte routebeschrijving** (optioneel)

---

## Taalstructuur

De site is meertalig: **ES (standaard), DE, EN, FR**.

In het prototype: bouw in het **Spaans** als basistaal.
Voeg bovenaan de pagina een simpele taalswitcher toe als demonstratie
(bijv. 4 knoppen ES/DE/EN/FR die schakelen tussen verborgen div-blokken per taal,
OF een simpele opmerking dat dit in WordPress via Polylang werkt).

Het prototype hoeft niet volledig vertaald te zijn — Spaans als demo volstaat,
met [DE], [EN], [FR] placeholders waar relevant.

---

## Designrichtlijnen

### Kernprincipes (van de eigenaar):
- **Minimaal, visueel, intuïtief** — weinig tekst, veel beeld
- **Warm en mediterraan** — niet donker, niet urban, niet koel
- **Michel centraal** — hij is het gezicht, de ziel van het restaurant
- **Eenvoudige navigatie** — direct toegang tot menu, reservering, contact
- **Fotografie als hoofdrolspeler** — tekst ondersteunt, foto's overtuigen

### Wat NIET te doen:
- Geen donkere kleurpaletten (eigenaar wijst BRUT-stijl af als te donker)
- Geen blokkerige kleurvlakken die de pagina in harde stukken knippen
- Geen volle bordeauxrode of paarse achtergronden over grote vlakken
- Geen lange tekstblokken
- Geen corporate/formele toon
- Geen drukke, overvolle lay-out

### Scrollervaring:
- Vloeiend en rustig — witte ruimte is je vriend
- Secties gaan geleidelijk in elkaar over, niet abrupt
- Kleur zit in accenten (knoppen, kleine details, dunne lijnen), niet in blokken

---

## Brand Assets — samenvatting

Zie `brand-assets.md` voor de volledige specificatie.
Korte referentie:

| Rol | Hex | Gebruik |
|---|---|---|
| Primary | `#7e1041` | Knoppen, koppen, accenten |
| Primary Dark | `#59103d` | Hover-states |
| Secondary | `#6b5770` | Spaarzaam, max 1 sectie als achtergrond |
| Accent | `#f4aeb7` | Kleine details, subtiele highlights |
| Neutraal | `#cfc0c0` | Achtergrondvlakken (spaarzaam) |
| Tekst | `#3a3a3a` | Hoofdtekst |
| Tekst licht | `#7a7a7a` | Bijschriften, labels |
| WhatsApp-knop | `#61a229` | Alleen voor de reserveer-knop |

**Lettertype:** Heebo (Google Font)
```html
<link href="https://fonts.googleapis.com/css2?family=Heebo:wght@300;400;600;800&display=swap" rel="stylesheet">
```

---

## Bestandsstructuur van het prototype

```
/
├── index.html          (Homepage)
├── carta.html          (Menukaart)
├── quienes-somos.html  (Over ons)
├── contacto.html       (Contact)
├── style.css           (Gedeelde stijlen)
└── assets/
    └── (placeholder-afbeeldingen)
```

Gebruik **placeholder-afbeeldingen** van https://picsum.photos/ voor sfeerbeelden
totdat de eigenaar echte foto's aanlevert. Gebruik warme/mediterrane foto's
(zoek op: `picsum.photos/seed/mediterranean/` of gebruik `unsplash.it`).

---

## WhatsApp-reserveerknop

De primaire call-to-action op de hele site.

Kleur: `#61a229` (groen, WhatsApp-herkenbaar)
Tekst per taal:
- ES: "Reservar por WhatsApp"
- DE: "Per WhatsApp reservieren"
- EN: "Reserve via WhatsApp"
- FR: "Réserver par WhatsApp"

Link-formaat (vervang XXXXXXXXX door het echte nummer):
```
https://wa.me/34XXXXXXXXX?text=Hola!%20Quisiera%20reservar%20una%20mesa%20para%20%5Bn%C2%BA%20personas%5D%20personas%2C%20el%20d%C3%ADa%20%5Bfecha%5D%20a%20las%20%5Bhora%5D.%20A%20nombre%20de%3A%20%5Bnombre%5D.%20%C2%A1Gracias!
```

Zet de knop op:
- Hero-sectie (homepage)
- Einde van elke pagina
- Contactpagina (groot en prominent)

---

## Placeholder-content (totdat eigenaar content aanlevert)

### Michel Heijman
"Michel Heijman es el alma de Nou Segle 12. Nacido en los Países Bajos, lleva más de 20 años
ligado a la gastronomía de Capdepera y la Cala Ratjada. Para Michel, recibir a los clientes
no es un trabajo — es una vocación. Muchos huéspedes vuelven año tras año, no solo por la
comida, sino por la forma en que Michel hace que cada visita se sienta especial."

### Manuel Herzog
"Manuel Herzog es nuestro cocinero. Formado en Alemania, lleva 15 años en Mallorca
perfeccionando una cocina de mercado fresca, honesta y llena de sabor mediterráneo."

### Restaurant intro
"Nou Segle 12 se encuentra en la Plaza de L'Orient, en el corazón de Capdepera.
Una terraza grande, una cocina abierta y un equipo apasionado — así es como entendemos
la hospitalidad mediterránea."

### Openingstijden
Lunes – Domingo: 08:30 – 23:00

### Adres
Plaza de L'Orient 1, 07850 Capdepera, Mallorca

---

## Instructies voor nabouwen in WordPress Elementor

Na goedkeuring van het prototype door de eigenaar wordt dit **sectie voor sectie**
nagebouwd in WordPress Elementor (gratis versie) op de staging-site.

Elke sectie in het prototype correspondeert met één Elementor-container:
- Hero = Container met achtergrondafbeelding + overlay + Heading + Button widgets
- Michel-sectie = 2-koloms container: Image widget links, Text Editor widget rechts
- Galerij = Image Gallery widget (standaard Elementor, geen addon nodig)
- Praktisch blok = 3-koloms container: Maps widget, Text widget, Button widget
- Footer = Container met Text widgets + Icon List widget voor social media

**Gebruik geen CSS of HTML widgets in Elementor** tenzij het puur decoratief
en taalneutraal is — alles met tekst moet in native Elementor-widgets staan
zodat Polylang het per taal kan vertalen.
