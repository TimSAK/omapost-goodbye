# Omapost — afscheidspagina

De statische afscheidspagina die de Ionic-app op omapost.nl vervangt. Omapost is
na ruim 10 jaar gestopt; deze pagina is wat er overblijft.

## Wat het is

Eén HTML-bestand met inline CSS, zonder JavaScript, zonder build-stap en zonder
externe requests. Alles bij elkaar ongeveer 100 KB.

```
index.html
assets/
├── fonts/   Asap Regular / Bold / Italic (woff2)
└── img/     logo, vier personages, favicon
```

## Look and feel

De vormgeving komt uit de oude Ionic-app (`kick-ass-kaart-platform`), zodat de
pagina niet lijkt op de app maar er daadwerkelijk mee overeenkomt:

- **Kleuren** uit `theme/variables.scss` — lucht `#bfd6ed → #cfe6ed`,
  tekst `#525465`, de olijfgroene grasrand `#7E7D49`.
- **Fonts** — dezelfde Asap-webfonts. `Asap-Bold` voor de kop, `Asap-Italic`
  voor de lopende tekst.
- **Personages** — de originele `header-image-*.svg` op hun oude posities,
  inclusief de breakpoints die ze op smalle schermen naar de randen schuiven.
- **Logo** — de postzegel rechtsboven, verborgen onder 768px.

Getest op 1440px, 820px en 390px. De `fadeIn`-animaties staan uit op telefoons
en bij `prefers-reduced-motion`.

## Deployen

Zet de inhoud van deze map in de webroot. Verder is er niets nodig — geen PHP,
geen Node, geen database.

Draait de webserver nog een Laravel-config, zorg dan dat `index.html` vóór
`index.php` staat:

```nginx
index index.html index.php;
```

Lokaal bekijken:

```bash
python3 -m http.server 8000
```
