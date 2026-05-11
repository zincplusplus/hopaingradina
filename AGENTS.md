# Hopa Țopa Land — reguli pentru agenți

Reguli scurte pentru orice agent (Claude Code, Codex etc.) care lucrează în acest repo.

## Limba

Răspunde și scrie comentarii în limba română.

## Cu cine vorbește agentul

Site-ul îl folosește și îl editează proprietarul Hopa Țopa Land — care **nu este programator și nu este designer**. Cunoaște businessul, nu codul.

În consecință, când vorbești cu el sau îi explici o decizie:

- **Nu folosi jargon tehnic.** Termeni ca *font-family*, *border-radius*, *flexbox*, *viewport*, *media query*, *hex code*, *DOM*, *grid*, *padding* nu spun nimic. Înlocuiește cu echivalent de zi cu zi.
  - „font-family" → „tipul de literă"
  - „border-radius" → „cât de rotunjite sunt colțurile"
  - „media query" → „cum se așază pe telefon vs pe desktop"
  - „padding" → „spațiul gol din jur"
  - „hex code" → „cod de culoare"
- **Descrie efectul vizual, nu mecanismul.** „Fac titlurile mai mari pe ecran mare" în loc de „adaug un media query la min-width 768px care crește font-size-ul lui h1."
- **Când îi ceri o decizie, dă-i variante cu preview vizibil**, nu doar nume tehnice. Exemplu: pentru fonturi, fă-i un selector live în pagină ca să vadă diferența cu ochii, nu o listă de nume.
- **Confirmă cu el înainte să schimbi paleta, fonturile, structura paginilor sau textele lungi.** Detaliile tehnice (CSS, structura claselor, refactor de cod) le poți face singur.

Codul scris stă în engleză (nume de clase, variabile, tokens) — acolo nu schimbăm nimic. Doar conversația cu omul e în limba lui.

## Ce construim

Site pentru Hopa Țopa Land — loc de joacă și spațiu de petreceri pentru copii în București. Conversia principală a siteului este **rezervarea unei petreceri** (lead → telefon / email / formular). Locul de joacă în weekend e secundar. Mai multe în `BRIEF.md`.

## Stack

- HTML, CSS și JavaScript pur. **Fără build step. Fără framework.** Niciun npm / yarn / vite.
- Iconițe: **Lucide**, inline SVG (nu via CDN). Lista celor folosite în `STYLEGUIDE.md`.
- Fonturi: prin `<link>` din Google Fonts în `<head>`-ul fiecărei pagini. Numele exact în `STYLEGUIDE.md`.

## Surse de adevăr

Înainte să modifici ceva, citește:

- `BRIEF.md` — businessul, audiența, ce trebuie să facă siteul
- `structura.md` — structura paginilor și a navigării
- `STYLEGUIDE.md` — design system: paletă, tipografie, voice, componente
- `styles.css` — token-uri CSS și componente concrete

Dacă faci o decizie nouă de design (paletă, componentă, layout), updatează `STYLEGUIDE.md` în aceeași modificare. Codul fără styleguide divergează rapid.

## Reguli de design

- **Mobile-first.** Scrie CSS pentru mobil, adaugă media queries pentru desktop. Nu invers.
- **Tokens, nu valori hardcodate.** Toate culorile, font-size-urile, spacing-urile, radius-urile trec prin `var(--...)` din `:root` în `styles.css`. Dacă ai nevoie de o valoare nouă, adaug-o ca token, nu hardcoda.
- **Imagini lipsă** → slot colorat (`background: var(--color-…)`) cu o iconiță Lucide centrată ca placeholder. Nu inventa URL-uri și nu folosi stock photos.

## Reguli de cod

- Un singur fișier `styles.css`. Nu spargem pe componente decât dacă depășește ~800 de linii.
- JavaScript doar unde HTML/CSS nu rezolvă (ex: lightbox dacă alegem JS; scroll smooth e deja nativ).
- HTML semantic: `<header>`, `<main>`, `<section>`, `<nav>`, `<footer>`. Nu `<div>` peste tot.
- Accesibilitate: `alt` pe imagini, contrast suficient, focus vizibil pe butoane și linkuri.

## Ce să NU faci

- Nu instala dependențe (npm, yarn, pip).
- Nu adăuga build tools (Vite, Webpack, Tailwind CLI, SASS).
- Nu folosi framework-uri JS (React, Vue, Alpine etc.).
- Nu schimba paleta sau tipografia fără să updatezi `STYLEGUIDE.md` și să confirmi cu proprietarul.