# Venteliste (e-post påmelding)

Landingssiden er statisk (GitHub Pages). E-poster lagres via en ekstern form-tjeneste.

## Anbefalt: nForms (EU)

**nForms** ([nforms.eu](https://nforms.eu)) er laget for akkurat dette: HTML-skjema → POST → dashboard. Data i **Frankfurt (EU)**, GDPR-vennlig, ingen cookies på besøkende.

| | nForms (EU) | Formspree (US) |
|---|---|---|
| Data | EU (Frankfurt) | USA |
| Gratisnivå | 100 innsendinger/mnd | 50 innsendinger/mnd |
| Bot-beskyttelse | Innebygd (Shield) | Valgfri reCAPTCHA |
| Integrasjon | Samme mønster som Formspree | — |

### Oppsett med nForms

1. Registrer deg på [nforms.eu](https://nforms.eu/login) → opprett skjema.
2. Kopier **access key** / endpoint: `https://api.nforms.eu/f/DIN_NØKKEL`
3. I `website/waitlist.config.js`:

```javascript
window.NUMBR_WAITLIST = {
  enabled: true,
  endpoint: 'https://api.nforms.eu/f/DIN_NØKKEL',
};
```

4. Commit, push, test på live-URL.
5. Innsendinger: **nForms dashboard** (e-postvarsel kan slås på der).

**Egendefinert domene (numbr.no):** Under nForms kan du sette *trusted domains* på betalte planer; på gratis fungerer skjemaet uansett fra ditt domene via `fetch`.

---

## Andre EU-alternativer

| Tjeneste | Hvor | Passer for |
|----------|------|------------|
| [SubmitKit](https://submitkit.dev) | Tyskland (Hetzner) | Enkel POST-backend, 500 gratis/mnd |
| [StaticForm](https://staticform.app) | EU | Statiske sider, spam-filter |
| [Tally](https://tally.so) | Belgia | Raskt skjema; ofte embed i stedet for egen HTML |
| **Supabase** (region `eu-central-1`) | EU | Full kontroll over data; mer oppsett |

For **Numbr** (privacy-first, norsk): **nForms** eller **SubmitKit** er nærmest «drop-in» som Formspree. **Supabase** er best når dere vil eie databasen helt selv senere.

---

## Formspree (USA)

Fungerer teknisk likt, men data behandles i USA. Bruk bare hvis du bevisst vil det:

```javascript
endpoint: 'https://formspree.io/f/xxxxxxxx',
```

---

## Test

1. Test helst på **deployet URL** (`https://…github.io/numbr/` eller `numbr.no`), ikke bare `file://` lokalt.
2. Send test-epost → sjekk dashboard hos leverandør.
3. Oppdater **Personvern**-teksten på siden når innsamling er live.

## Feilsøking

| Symptom | Løsning |
|--------|---------|
| «Ventelisten er ikke aktivert ennå» | `enabled: true` + gyldig `endpoint` |
| Nettverksfeil | Test på live-URL; sjekk at nøkkel er riktig |
| 429 / rate limit | Vent eller oppgrader plan |
