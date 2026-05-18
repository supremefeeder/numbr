# Numbr — Cursor Handover
*Versjon 3.4.0 — Mai 2025*

---

## Prosjektoversikt

**Numbr** er en norsk privacy-first telefonapp som lar brukere opprette og slette virtuelle norske telefonnumre. Konseptet er bygget og designet i Claude, og er klart til å videreføres i Cursor.

---

## Filer

| Fil | Beskrivelse |
|---|---|
| `numbr-v3.4.0.html` | Komplett landingsside — én enkelt HTML-fil med all CSS og JS inline |

Gi filen nytt navn `index.html` og legg den i `numbr/website/`.

---

## Teknisk stack

Én enkelt `index.html` — ingen dependencies, ingen build-steg, ingen npm.

**Fonter** (Google Fonts CDN):
- `Cormorant Garamond` — display/headings (300, italic)
- `DM Sans` — body/UI (300, 400, 500)

**JavaScript** — vanilla, inline i bunnen av filen:
- FAQ accordion
- Scroll reveal (IntersectionObserver)
- FAB scroll-knapp (vises etter hero, snur ved bunn)
- Venteliste e-post validering

For å kjøre lokalt — åpne `index.html` direkte i browser. Ingen server nødvendig.

---

## Design system

### Fargepalett (CSS-variabler)
```css
--bg:      #0e0a12   /* dyp aubergine-sort — bakgrunn */
--mid:     #2a1c3e   /* plomme — elevated surfaces */
--gold:    #c4a864   /* champagne — labels, tags, ikoner */
--gold-lt: #e0c88c   /* lys champagne — hover-states */
--white:   #e1d7eb   /* kjølig hvit — all tekst */
--dim:     rgba(225,215,235,0.42)   /* dempet tekst */
--dimmer:  rgba(225,215,235,0.2)    /* veldig dempet */
--line:    rgba(225,215,235,0.08)   /* skillelinjer */
```

### Typografisystem (4 nivåer)
```css
--f-display: 'Cormorant Garamond', serif
--f-sans:    'DM Sans', sans-serif

--fs-display: clamp(46px, 11vw, 84px)   /* hero h1 */
--fs-heading: clamp(32px, 4vw, 48px)    /* section h2 */
--fs-title:   17px                       /* h3, kortere titler */
--fs-body:    14px                       /* all brødtekst */
--fs-micro:   11px                       /* labels, tags, nav */

--fw-light:   300
--fw-regular: 400
--fw-medium:  500
```

### Bakgrunn
Fast (`position: fixed`) radial-gradient i tre lag — aubergine/plomme toner.
**Ingen animasjoner på bakgrunnen** — animasjoner skapte synlige sømmer.

---

## Sidestruktur

```
1. Hero          — fullskjerm, tekst nederst til venstre
2. Intro         — én stor setning om produktet
3. Bruksområder  — tre rader (burner / rolle / bekjentskaper)
4. Personvern    — ett løfte + FAQ accordion
5. Venteliste    — fullskjerm, e-postskjema
6. Footer        — logo, lenker, copyright
```

### Konsistent seksjonsmal
Alle seksjoner bruker samme hierarki:
```html
<div class="section-label">Navn på seksjon</div>
<h2 class="section-h2">Overskrift med <em>kursiv</em></h2>
[innhold]
```

---

## Neste steg (prioritert)

### Teknisk MVP
1. **BankID-integrasjon** via [Signicat](https://www.signicat.com) eller [Criipto](https://www.criipto.com)
2. **VoIP/SIP-numre** via [Telnyx](https://telnyx.com) — kjøp norske numre enkeltvis
3. **Backend** — Node.js/Python, enkel SIP-ruter
4. **Pseudonymisert dataarkitektur** — BankID-hash adskilt fra nummerdata

### Produkt
- Native iOS/Android app (React Native)
- Burner-numre med automatisk utløp
- Rolle-merking i appen (jobb / familie / venner)

### Business
- Registrer **Numbr AS** på Brønnøysund
- Kjøp **numbr.no** og **numbr.me** (begge trolig ledige)
- Søk **Innovasjon Norge Oppstartstilskudd fase 1** (maks 100–200k kr)
- Vurder **Skattefunn** parallelt

---

## Viktige avgjørelser tatt

| Beslutning | Valg | Begrunnelse |
|---|---|---|
| Navn | Numbr | Direkte, nordisk, ingen kjent konkurrent |
| Farge | Aubergine + champagne | Uvanlig for tech, premium-følelse |
| Font | Cormorant + DM Sans | Serif/sans kontrast gjør hierarki-jobben |
| Animasjon bakgrunn | Ingen | Skapte synlige sømmer |
| "Slik fungerer det"-side | Fjernet | Dekkes av FAQ |
| Prisside | Fjernet | For tidlig for en teaser-side |
| Finn.no-referanser | Fjernet | Gratis reklame, begrenser nordisk skala |

---

## Juridisk (huskeliste)

- Ekomloven § 2-8 — ID-registrering av abonnenter (løses via BankID)
- GDPR — dataminimering, pseudonymisering, rett til sletting
- Nkom — nummerblokker tildeles i min. 1000-blokker (bruk grossist i MVP)
- Re-identifisering kun ved rettslig kjennelse — bygg arkitekturen deretter

---

*Laget i Claude (Anthropic) — Mai 2025*
