# Hva som er offentlig vs. lokalt

## Offentlig på GitHub (og synlig i repo-browser)

| Sti | Innhold |
|-----|---------|
| `website/index.html` | Landingsside |
| `website/waitlist.config.example.js` | Mal uten hemmeligheter |
| `.github/workflows/` | Deploy (nøkkel fra GitHub Secret) |
| `README.md` | Kort prosjektinfo |
| `docs/` | Intern dokumentasjon (leses på GitHub, ikke hostet som nettside) |

## Publiseres på numbr.no (kun dette)

Deploy-workflow kopierer **bare**:

- `index.html`
- `waitlist.config.js` (generert i CI, inneholder nForms-endpoint)

Ingen `docs/`, `mockup/`, `reference/` eller README på den live URL-en.

## Lokalt i Dropbox — skal aldri committes

| Mappe | Formål |
|-------|--------|
| `design/` | Designfiler |
| `archive/` | Arkiv |
| `assets/` | Råfiler |
| `website/mockup/` | Prototyper |
| `website/reference/` | Gamle versjoner / handover |
| `*.pages` | Apple Pages-dokumenter |

Disse er listet i `.gitignore`.

## Hemmeligheter

- **nForms-nøkkel:** kun GitHub Secret `NFORMS_ACCESS_KEY`
- **Aldri** i `index.html`, commits eller offentlige filer
