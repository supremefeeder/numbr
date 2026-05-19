# Numbr

Privacy-first virtuelle norske telefonnumre.

## Nettside

Landingssiden ligger i [`website/`](website/). Én `index.html` — ingen build-steg.

### Lokal forhåndsvisning

```bash
open website/index.html
```

### GitHub Pages

Ved push til `main` deployes `website/` automatisk via [`.github/workflows/deploy-website.yml`](.github/workflows/deploy-website.yml).

**Engangsoppsett på GitHub:**

1. Opprett repo og push (se under).
2. **Settings → Pages → Build and deployment:** velg **GitHub Actions**.
3. Etter første vellykkede workflow: siden er live på `https://<bruker>.github.io/<repo>/`.

**Egendefinert domene (f.eks. numbr.no):**

1. **Settings → Pages → Custom domain:** `numbr.no`
2. Legg til DNS hos domeneleverandør (GitHub viser nøyaktige poster).
3. Valgfritt: opprett `website/CNAME` med domenet for å holde det i repo (se `website/CNAME.example`).

### Venteliste (e-post)

Venteliste via [nForms](https://nforms.eu) (EU). Nøkkel lagres som GitHub Secret `NFORMS_ACCESS_KEY` — aldri i repo. Se [`website/WAITLIST.md`](website/WAITLIST.md).

**Repo:** privat. **GitHub Pages** på privat repo krever [GitHub Pro](https://github.com/pricing); ellers må repo være public for gratis Pages.

### Push til GitHub

```bash
git init
git add .
git commit -m "Add Numbr landing page and GitHub Pages deploy"
git branch -M main
git remote add origin https://github.com/<bruker>/numbr.git
git push -u origin main
```

Hvis `gh` er innlogget:

```bash
gh auth login
gh repo create numbr --public --source=. --remote=origin --push
```

## Referanse

Designspes og original HTML: [`website/reference/`](website/reference/).
