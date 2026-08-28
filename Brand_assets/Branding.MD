# Brand Assets — Nou Segle 12

Geëxtraheerd uit live CSS van nousegle12.com op 25 augustus 2026.
Gebruikt als stijlreferentie voor het HTML-prototype én de Elementor-bouw.

---

## Kleurenpalet

### Gebruik-hiërarchie (belangrijk)
Gebruik Primary + wit als hoofdcombinatie.
Secondary en Accent zijn spaarzame accenten — niet als grote vlakken.
De eigenaar wil een **warm, mediterraan, licht** gevoel — niet donker, niet urban.

| Naam | Hex | RGB | Gebruik |
|---|---|---|---|
| Primary | `#7e1041` | rgb(126,16,65) | Knoppen, koppen, actieve links, dunne accentlijnen |
| Primary Dark | `#59103d` | rgb(89,16,61) | Hover-states van knoppen en links |
| Secondary | `#6b5770` | rgb(107,87,112) | Max 1 achtergrondblok per pagina, spaarzaam |
| Accent | `#f4aeb7` | rgb(244,174,183) | Kleine highlights, subtiele details, icoon-kleuren |
| Neutraal | `#cfc0c0` | rgb(207,192,192) | Lichte achtergrondvlakken, foto-placeholders |
| Tekst donker | `#3a3a3a` | rgb(58,58,58) | Alle hoofdtekst |
| Tekst grijs | `#7a7a7a` | rgb(122,122,122) | Bijschriften, labels, datum/tijd |
| Wit | `#ffffff` | rgb(255,255,255) | Hoofdachtergrond, tekst op donkere vlakken |
| WhatsApp groen | `#61a229` | rgb(97,162,41) | Uitsluitend voor de WhatsApp-reserveerknop |

### Wat NIET te doen met kleuren:
- Geen volle Primary-achtergrond (`#7e1041`) over grote secties — dit maakt het donker en zwaar
- Niet meer dan 2 niet-witte achtergrondkleuren per pagina
- Secondary (`#6b5770`) nooit twee secties na elkaar gebruiken
- Neutraal (`#cfc0c0`) alleen als subtiele achtergrond, nooit als tekstkleur

---

## Typografie

### Lettertype
**Heebo** — Google Font, sans-serif, geometrisch maar warm

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Heebo:wght@300;400;600;800&display=swap" rel="stylesheet">
```

```css
font-family: 'Heebo', sans-serif;
```

### Gewichten en gebruik

| Gewicht | Naam | Gebruik |
|---|---|---|
| 300 | Light | Subtitels, kleine labels, datum/tijd |
| 400 | Regular | Alle lopende tekst, alinea's |
| 600 | Semibold | Sectietitels, menucategorieën, knoppen |
| 800 | Extrabold | Hero-kop, restaurantnaam, grote paginatitels |

### Tekstgroottes (referentie voor prototype)

| Element | Grootte | Gewicht | Kleur |
|---|---|---|---|
| Hero-titel | 48–56px | 800 | #ffffff (op foto) |
| Paginatitel (H1) | 32–40px | 800 | #59103d |
| Sectietitel (H2) | 24–28px | 600 | #59103d |
| Naam teamlid (H3) | 18–20px | 600 | #3a3a3a |
| Hoofdtekst | 15–16px | 400 | #3a3a3a |
| Label/bijschrift | 12–13px | 300 | #7a7a7a |
| Knoptekst | 14px | 600 | #ffffff |
| Navigatie | 14px | 400 | #3a3a3a |

---

## Componenten

### Primaire knop (reserveren / CTA)
```css
background: #61a229;        /* WhatsApp groen — alleen voor reserveerknop */
color: #ffffff;
font-family: 'Heebo', sans-serif;
font-weight: 600;
font-size: 14px;
padding: 14px 32px;
border-radius: 28px;        /* Volledig afgerond — pill-shape */
border: none;
cursor: pointer;
```

### Secundaire knop (menu bekijken, meer info)
```css
background: transparent;
color: #7e1041;
font-family: 'Heebo', sans-serif;
font-weight: 600;
font-size: 14px;
padding: 12px 28px;
border-radius: 28px;
border: 2px solid #7e1041;
cursor: pointer;
```

### Navigatiebalk
```css
background: #ffffff;
border-bottom: 1px solid #f0eded;
padding: 16px 40px;
position: sticky;
top: 0;
z-index: 100;
```

### Dunne accentlijn (sectie-scheiding)
```css
border: none;
border-top: 1px solid #e8e0e0;
margin: 48px 0;
```

### Foto-overlay (tekst leesbaar over foto)
```css
background: linear-gradient(
  to top,
  rgba(89, 16, 61, 0.6) 0%,
  rgba(89, 16, 61, 0.1) 50%,
  transparent 100%
);
```

---

## Spacing / witruimte

Witruimte is een kernonderdeel van het ontwerp — de eigenaar wil minimaal en luchtig.

| Element | Waarde |
|---|---|
| Sectie padding (boven/onder) | 64–80px |
| Container max-breedte | 1100px, gecentreerd |
| Container zijkanten padding | 40px (desktop), 20px (mobiel) |
| Ruimte tussen tekstelementen | 16px |
| Ruimte tussen secties | 48px dunne lijn of gewoon witruimte |
| Ruimte tussen kolommen | 32px |

---

## Logo

- Bestandsnaam (uit bestaande site): `Logo-DEF-Nou-Segle-12.png`
- Stijl: circulair, handgeschreven/kalligrafisch, bordeauxrood op wit
- Gebruik altijd op witte of lichte achtergrond
- Minimale hoogte in navigatie: 48px
- Nooit uitrekken of vervormen

---

## Referentiesites (van eigenaar)

De eigenaar heeft twee referentiesites aangeleverd. Gebruik deze als inspiratie
voor **structuur en gevoel**, niet als directe kopie.

### 1. BRUT Restaurant (www.brutrestaurante.com)
**Wat overnemen:** chef/persoon centraal op homepage, visueel zwaar (veel foto, weinig tekst)
**Wat NIET overnemen:** donkere kleurenpalet (zwart/donkergrijs), urban/fine-dining sfeer
**Reden eigenaar:** Nou Segle 12 is mediterraan, licht, toeristisch — niet donker en urban

### 2. El Camino Palma (www.elcaminopalma.es)
**Wat overnemen:** simpele navigatiestructuur, directe toegang tot menu/reservering/galerie,
  weinig tekst, gevoel van helderheid en intuïtiviteit
**Wat NIET overnemen:** lettertype (Hoefler Txt serif — wij gebruiken Heebo sans-serif),
  kleurenpalet (donker warm terra)
**Reden eigenaar:** de structuur en eenvoud zijn het voorbeeld, niet de visuele stijl

### Gecombineerde les voor het ontwerp:
- BRUT: chef centraal, visueel gedreven → structuur
- El Camino: simpel, direct, intuïtief → navigatie en UX
- Nou Segle 12 eigenaar: warm, mediterraan, licht → kleur en sfeer

---

## Toon en stijl van teksten

- Warm, persoonlijk, niet corporate
- Michel staat centraal — schrijf over hem als een persoon, niet als een functie
- Kort en krachtig — de eigenaar wil weinig tekst
- Mediterraans gevoel — noem Capdepera, het plein, de Mallorcaanse sfeer
- Geen superlatieven of marketingclichés ("de beste", "unieke ervaring")
- Directe aanspreking in meervoud ("bienvenidos", "os esperamos")