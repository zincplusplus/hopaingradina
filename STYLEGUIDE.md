# Styleguide — Hopa Țopa Land

Specificația scrisă a brandului. Pentru regulile vizibile live, vezi [index.html](index.html).

## Paletă

Trei culori de bază (derivate din siglă) + un crem ca pat + un negru cald pentru text. Atât. Fără gradients, fără pasteluri, fără gri rece.

### Principale

| Token | Hex | Folosit pentru |
|---|---|---|
| `--magenta` | `#E5478F` | Butoane primare, link-uri, accenți. Cantitate **mică**, mereu împotriva crem-ului. Nu fundal de secțiune. |
| `--green` | `#82B440` | Accent secundar. Iconițe USP, checkmarks, badge "ISU autorizat". |
| `--cream` | `#FFF8EE` | Fundalul paginii. Cald, nu galben. |

### Neutrale

| Token | Hex | Folosit pentru |
|---|---|---|
| `--ink` | `#2E1A2A` | Textul. Negru cu picătură de prună — se așază mai bine cu magenta-ul decât negrul pur. |
| `--ink-soft` | `#6B5563` | Subtitle, label-uri, meta. |
| `--paper` | `#FFFFFF` | Carduri pe fundalul crem. |
| `--border` | `#EFE3D9` | Linii, separatoare, contur input. |

### Accent rar

| Token | Hex | Folosit pentru |
|---|---|---|
| `--sun` | `#F5C648` | Highlight de ofertă, "nou", "popular". Maximum un loc pe pagină. |

### Image slots

Cât timp nu avem fotografii, slot-urile de imagine sunt blocuri colorate cu o iconiță Lucide centrată.

| Token | Hex |
|---|---|
| `--slot-pink` | `#FCE2EE` |
| `--slot-green` | `#E6F2D6` |
| `--slot-cream` | `#FFF0DC` |
| `--slot-sun` | `#FDEBC2` |

## Typography

Două familii. Atât.

- **Display: DynaPuff** (400/500/600/700). Pentru titluri, butoane, label-uri scurte. Rotunjit, prietenos, citibil. Păstrează energia jucăușă a brandului fără să piardă lizibilitatea.
- **Body: Inter** (400/500/600). Pentru paragrafe, navigație, formulare. Neutral, lizibil pe ecrane mici.

Încărcate de la Google Fonts cu `display=swap` — paginile randerează imediat, font-ul "pică" peste când se descarcă.

### Scală

| Token | Mărime | Pentru |
|---|---|---|
| `--text-xs` | 12px | Meta, badge-uri |
| `--text-sm` | 14px | Label, secondary |
| `--text-base` | 16px | Body |
| `--text-lg` | 19px | Lead, body emphasized |
| `--text-xl` | 24px | Section subtitle |
| `--text-2xl` | 32px | Section title |
| `--text-3xl` | 44px | Page title |
| `--text-4xl` | 56px (40 pe mobil) | Hero |

Line-height: `1.5` pe body, `1.1` pe titluri.

## Shape

- **Carduri**: `border-radius: 20px`
- **Butoane**: `border-radius: 999px` (pill complet, mereu)
- **Inputs**: `border-radius: 12px`
- **Iconițe**: Lucide, stroke 2px

Colțurile rotunde sunt parte din ton. Sigla e rotundă. Lumea pe care o vinde Hopa Țopa e rotundă.

## Spacing

Scală 4px-based. Tokenuri în CSS de la `--space-1` (4px) la `--space-24` (96px).

Folosește mereu tokens, niciodată valori magice. Dacă ai nevoie de o valoare care nu există în scală, ai o problemă de design, nu de CSS.

## Iconițe — Lucide

Le folosim via CDN (`unpkg.com/lucide@latest`), inițializate cu o singură linie de JS la sfârșitul body-ului. În HTML:

```html
<i data-lucide="phone"></i>
```

Lucide se potrivește perfect cu brandul: stroke-based, rotunjit, prietenos, neutru cromatic (preia `currentColor`).

Iconițe pe care le folosim acum: `phone`, `mail`, `map-pin`, `clock`, `calendar`, `wifi`, `car-front`, `snowflake`, `shield-check`, `sparkles`, `images`, `cake`, `chef-hat`, `gift`, `party-popper`, `school`, `leaf`, `plus-circle`, `check`, `chevron-left`, `chevron-right`, `menu`, `x`.

## Voice

**Persoană**: noi (echipa Hopa Țopa), tu (părintele).

**Ton**: cald, direct, prietenos cu părintele. Părintele e clientul, copilul e bucuria.

### Fă

- Vorbește părintelui ca unui prieten care planifică o aniversare.
- Promisiuni concrete: 3 ore, exclusivitate, ISU, parcare.
- Nume reale: "Caffe Latte", "Prosecco fără alcool" — au valoare evocativă.
- Sentinele scurte. Lăsă albul să respire.
- Folosește diacritice. Te citește un părinte la 11 seara cu copilul în brațe.

### Nu fă

- Majuscule de stadion ("CELE MAI TARI PETRECERI").
- Emoji înțepenite la fiecare linie.
- Cliché corporate ("experiență memorabilă", "soluții personalizate", "echipa noastră de profesioniști").
- Texte care vând copilului. Părintele plătește, părintele citește.
- "Click aici" — nu spune niciodată "click aici."

## Componente

Vezi [index.html](index.html) pentru fiecare componentă vizibilă, cu HTML-ul ei.

- **Header plutitor** — logo + nav + telefon + CTA. Pe telefon, meniul rămâne vizibil ca bară orizontală derulabilă sub logo și buton. Sticky, cu blur pe scroll.
- **Hero** — titlu + lead + CTA + image slot pe dreapta. Pe mobil, totul stacked, image slot sub. CTA-ul principal din hero poate fi ușor mai vizibil decât restul butoanelor, cu contur și umbră mai clară.
- **Buton Hopa în Grădină peste hero** — mică invitație poziționată în dreapta sus peste fotografia de start din indoor, cu verdele și galbenul locației outdoor, pentru trimitere rapidă spre pagina Mogoșoaia.
- **Colaj foto** — patru fotografii mai mici, ușor suprapuse, cu margine albă și umbră, folosite pentru a arăta clar spațiul, părinții, joaca și activitățile.
- **USP strip** — 4 iconițe + label + meta. 2 coloane pe mobil, 4 pe desktop.
- **Card eveniment** — image slot, titlu, dată, descriere scurtă, buton. În indoor, cardurile au dată internă, sunt așezate automat cu cel mai recent primul și pe pagină apar doar ultimele 3.
- **Listă ofertă școli/grădinițe** — rânduri compacte, unul sub altul, cu iconiță mică, numele categoriei și buton discret; detaliile rămân doar în pop-up.
- **Galerie slideshow** — carusel foto mai compact, cu controale stânga/dreapta și puncte de navigare, folosit pentru mixuri reprezentative de spațiu, activități și petreceri. Imaginile se văd întregi, fără tăieri importante.
- **Review slideshow** — carusel text pentru opinia clienților, cu stele, text central și controale simple. Se folosește pentru mesaje scurte, ușor de citit, nu pentru paragrafe lungi.
- **Card pachet** — featured cu border magenta, listă cu checkmarks verde, preț mare, CTA.
- **Banner extra opțiuni** — bandă compactă sub pachete, cu CTA către pop-upul de extra opțiuni.
- **Dialog personaje** — pop-up centrat peste pagină, declanșat din pachetul Hopa, cu închidere pe `x` sau click pe fundal.
- **Dialog teme** — pop-up centrat peste pagină, fundal alb, header crem, închidere cu iconița `x`, liste de teme în blocuri compacte cu imagine scurtă.
- **Dialog extra opțiuni** — pop-up centrat peste pagină, organizat pe extra opțiuni copii și adulți.
- **Dialog ofertă serbări** — pop-up centrat peste pagină, pe același model vizual ca dialogul de teme, cu oferta grupată pe copii, extra copii și adulți.
- **Formular contact** — vertical, label deasupra input-ului, focus magenta.
- **Footer** — fundal ink, 3 coloane pe desktop.

## Reguli de aplicare

- O singură culoare dominantă pe ecran. Magenta-ul *taie* o pagină crem, nu o saturează.
- Maximum un singur CTA primar vizibil simultan. Restul sunt secondary sau ghost.
- White space e parte din design, nu lipsă de conținut.
- Pe mobil, nimic sub 16px font-size (zoom forțat de iOS).
- Pe mobil, tap targets minimum 44×44px.
