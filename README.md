# Numbr

Privacy-first virtuelle norske telefonnumre.

## Nettside

Produksjon: [`website/index.html`](website/index.html) → deployes til GitHub Pages.

```bash
open website/index.html
```

Live (etter deploy): https://supremefeeder.github.io/numbr/

## Utvikler

| Dokument | Innhold |
|----------|---------|
| [docs/repository-layout.md](docs/repository-layout.md) | Hva som er offentlig vs. lokalt |
| [docs/waitlist-setup.md](docs/waitlist-setup.md) | nForms + GitHub Secret |

Ventelisten: secret `NFORMS_ACCESS_KEY` i repo Settings → Secrets → Actions.

## Domene

`numbr.no`: GitHub **Settings → Pages → Custom domain**, og `website/CNAME` med domenet (se `website/CNAME.example`).
