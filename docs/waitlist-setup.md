# Venteliste (nForms) — intern oppsett

Kun for utviklere. Denne filen deployes **ikke** til numbr.no.

## nForms (EU)

1. [nforms.eu/dashboard](https://nforms.eu/dashboard) → opprett skjema.
2. GitHub → repo **numbr** → **Settings → Secrets → Actions** → `NFORMS_ACCESS_KEY` (kun nøkkelen, f.eks. `nf_…`).
3. Push til `main` — workflow genererer `waitlist.config.js` ved deploy.

## Lokal test

```bash
cp website/waitlist.config.example.js website/waitlist.config.js
# rediger med egen nøkkel — filen committes aldri
open website/index.html
```

Test helst på deployet URL (ikke bare `file://`).

## Roter nøkkel

Hvis nøkkelen har vært i git eller chat: regenerer i nForms → oppdater GitHub Secret.

```bash
gh secret set NFORMS_ACCESS_KEY --repo supremefeeder/numbr
```

## E-postvarsler

nForms dashboard → Notifications → legg til mottakere.
