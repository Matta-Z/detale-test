# CLAUDE.md – DETALE Frontend Rules

## Prosjekt
DETALE SB – landingsside for PropTech-studentbedrift. Ren HTML + CSS (ingen React/Tailwind/bundler).
Filer: `index.html`, `style.css`. Åpnes direkte i browser via `open index.html`.

## Always Do First
- Invok `ui-ux-pro-max` skill før du skriver frontend-kode i nye sesjoner.

## Design-system (etablert)
- **Font:** Inter (Google Fonts, weights 300–800)
- **Primær:** `#1B3A6B` (navy), `#2563EB` (blå), `#DBEAFE` (lys blå)
- **CTA:** `#F59E0B` (amber), hover `#D97706`
- **Bakgrunn:** `#F8FAFC`, overflate `#FFFFFF`, tekst `#1E293B`, dempet `#64748B`
- **Border:** `#E2E8F0`, success `#22C55E`, danger `#EF4444`
- **Radius:** sm `8px`, md `12px`, lg `20px`
- **Shadows:** sm/md/lg definert i `:root` – aldri flat `box-shadow: 0 2px 4px`

## Anti-Generiske Regler
- **Farger:** Bruk alltid CSS-variablene fra `:root`. Ikke oppfinn nye hex-verdier uten grunn.
- **Skygger:** Bruk `var(--shadow-sm/md/lg)`. Aldri generisk `box-shadow: 0 2px 4px gray`.
- **Typografi:** Inter for alt. Tett tracking (`letter-spacing: -.02em`) på store headings, `line-height: 1.65` på brødtekst.
- **Gradienter:** Radiale gradienter for bakgrunner – ikke flate farger på seksjoner.
- **Animasjoner:** Animer kun `transform` og `opacity`. Aldri `transition: all`. Spring-easing: `cubic-bezier(0.34, 1.56, 0.64, 1)`.
- **Interaktive states:** Alle klikkbare elementer må ha hover, focus-visible og active. Ingen unntak.
- **Dybde:** Kort/modaler/navbar har et lagdelt z-system (base → elevated → floating).

## Hard Rules
- Ikke bruk `transition: all` – spesifiser alltid property
- Ikke legg til seksjoner eller innhold brukeren ikke har bedt om
- Ikke "forbedre" design uten at brukeren ber om det
- Ikke bruk generiske Tailwind-farger (vi bruker ikke Tailwind)
- Alltid `prefers-reduced-motion` i CSS når animasjoner legges til
- Alltid `aria-label` på icon-only knapper
- Alltid `focus-visible` outline på interaktive elementer

## Kjente Intensjonelle Valg
- Siden er ren HTML/CSS – ikke foreslo React/bundler med mindre brukeren ber om det
- Venteliste-skjema har ingen backend – submit-state håndteres i JS
- Sticky CTA vises kun på mobil og skjules når waitlist-seksjonen er synlig
- Scroll-animasjoner bruker IntersectionObserver med `.visible`-klasse

## Snarveier
- For å åpne siden: `open /Users/mathiasfossum/ÅSN1104/index.html`
