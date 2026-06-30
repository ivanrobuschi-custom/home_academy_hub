# Academy Hub — Custom S.p.A.

Sito indice (mkdocs-material + GitHub Pages) che raccoglie i link ai portali di formazione tecnica e commerciale dei singoli prodotti Custom S.p.A.

## Struttura

```
docs/
  index.md                    # Home con griglia di tutte le card
  registratori-telematici.md  # Menu: Registratori Telematici → EDGE N/N+
  normativa.md                # Menu: Normativa → Collegamento POS-RT
  hyperbeauty.md              # Menu: HyperBeauty → Formazione Commerciale + Level 1
  hyperretailcloud.md         # Menu: HyperRetailCloud → Formazione Commerciale
  stylesheets/extra.css       # Branding + stile card
  assets/icons/               # ⚠️ Da popolare: logo.png e favicon.png
mkdocs.yml
.github/workflows/ci.yml      # Deploy automatico su push a main/master
```

## ⚠️ Prima del primo deploy

`mkdocs.yml` fa riferimento a `assets/icons/logo.png` e `assets/icons/favicon.png`, che non sono inclusi in questa consegna. Copiali da uno dei repository esistenti (es. `corso-tecnico-edge-n/docs/assets/icons/`) dentro `docs/assets/icons/` di questo repository prima di fare il primo push, altrimenti la build potrebbe fallire o mostrare icone mancanti.

Se usi anche il font Titillium Web personalizzato, copia la cartella `fonts/` con `TitilliumWeb-Regular.ttf` allo stesso livello di `docs/` (come negli altri repository), oppure rimuovi il blocco `@font-face` da `extra.css` se preferisci il font di sistema.

## URL dei 5 corsi collegati

| Voce di menu | Repository | URL GitHub Pages |
|---|---|---|
| Registratori Telematici | `corso-tecnico-edge-n` | https://ivanrobuschi-custom.github.io/corso-tecnico-edge-n/ |
| Normativa | `COLLEGAMENTO-POS_RT-2026` | https://ivanrobuschi-custom.github.io/COLLEGAMENTO-POS_RT-2026/ |
| HyperBeauty (Formazione Commerciale) | `hyperbeauty-corso-commerciale` | https://ivanrobuschi-custom.github.io/hyperbeauty-corso-commerciale/ |
| HyperBeauty (Level 1) | `Hyperbeauty-corso-Level1` | https://ivanrobuschi-custom.github.io/Hyperbeauty-corso-Level1/ |
| HyperRetailCloud | `hypercloud-corso-commercial` | https://ivanrobuschi-custom.github.io/hypercloud-corso-commercial/ |

Se uno di questi nomi di repository o URL non è esatto, aggiorna i link nei file `docs/*.md` corrispondenti.

## Deploy

```bash
git init
git remote add origin https://github.com/ivanrobuschi-custom/home_academy_hub.git
git add .
git commit -m "Setup Academy Hub"
git push -u origin main
```

Il workflow in `.github/workflows/ci.yml` esegue automaticamente `mkdocs gh-deploy --force` ad ogni push su `main`/`master`, pubblicando il sito sul branch `gh-pages`.

Ricorda di attivare GitHub Pages nelle impostazioni del repository (Settings → Pages → Source: branch `gh-pages`), e di configurare il sottodominio di terzo livello aziendale quando sarà pronto (campo `CNAME` in `docs/` o nelle impostazioni Pages del repo).

## Test in locale

```bash
pip install mkdocs-material
mkdocs serve
```
