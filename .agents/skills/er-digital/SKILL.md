---
name: er-digital
description: Brand, design system, and content rules for the ER Digital studio site (er-digital-studio). Use when editing index.html, CSS, JS, copy, portfolio cards, SEO/OG, or deploying the static site.
---

# ER Digital — Skill projet

Site vitrine du studio **ER Digital** (Emmanuel-Roland Pregnon, Yamoussoukro).

**Live :** https://emmanuelrolandpregnon-design.github.io/er-digital-studio/  
**Repo :** emmanuelrolandpregnon-design/er-digital-studio  
**Stack :** HTML / CSS / JS vanilla, structure **plate** (pas de dossiers `assets/`), hébergement GitHub Pages.

## Identité

- **Positionnement :** sites vitrines et portfolios sur mesure pour docteurs, enseignants-chercheurs et professionnels.
- **Ton :** franc, direct, sans jargon marketing. Phrases courtes. « Du concret. Pas du blabla. »
- **Langue :** français (prioritaire). Pas de bilingue FR/EN sur cette version sauf demande explicite.
- **Contact :** WhatsApp +225 05 75 37 09 29 · email actuel `emmanuelrolandpregnon@gmail.com` (viser `contact@er-digital.studio` quand le domaine est prêt).
- **Localisation :** Yamoussoukro · à distance.

## Design system (ne pas diluer)

| Token | Valeur |
|-------|--------|
| Fond | `#EDE7DC` (light) / `#1A1614` (dark) |
| Encre | `#1A1614` / `#EDE7DC` |
| Orange | `#E8522B` |
| Jaune | `#F4C430` |
| Surface | `#F7F3EB` |
| Display | Archivo Black (self-hosted `.woff2`) |
| Body | Space Grotesk |
| Mono | Space Mono |

- Bordures nettes 1.5–2px, ombres hard offset (`box-shadow: 4px 4px 0` / `8px 8px 0`), pas de soft blur.
- Boutons uppercase, mono labels, hover = translate + shadow + fill orange/jaune.
- `mark` / highlights = fond orange, texte encre.
- Thème clair/sombre via `data-theme` + bouton `#theme-toggle`.
- Mobile-first ; menu burger sous ~700px.

## Structure fichiers (plate)

```
index.html
404.html
site-style.*.css
site-script.*.js
*.woff2 (4 polices)
*.webp (portfolio, trajectory, henock)
favicon.ico, favicon-32.png, apple-touch-icon.png, og-image.png
_headers, _redirects, robots.txt, sitemap.xml
README.md
```

**Interdit :** recréer des dossiers `assets/css|fonts|images` sauf décision explicite de restructurer. Chemins relatifs à la racine uniquement.

## Contenu / réalisations

Trois cartes projet (ordre) :
1. **Portfolio** — https://emmanuelrolandpregnon-design.github.io/
2. **ER Trajectory** — https://emmanuelrolandpregnon-design.github.io/trajectory/
3. **Henock Kouassi** (client) — https://henock-kouassi.netlify.app

Dialog modal `#project-dialog` alimenté par `projectData` dans le JS. Toute nouvelle réalisation = entrée dans `projectData` + carte HTML + image `.webp` à la racine.

## SEO & partage

- `og:image` / `twitter:image` / canonical / schema.org **doivent** utiliser l’URL absolue du déploiement actuel :
  `https://emmanuelrolandpregnon-design.github.io/er-digital-studio/…`
- Quand le domaine `er-digital.studio` pointera sur ce site, basculer canonical + OG vers ce domaine.
- Image partage : `og-image.png` (1200×630).

## Contraintes workflow

- L’auteur travaille **uniquement au téléphone** : pas de dossiers GitHub web, pas de `npx` local. Préférer commits API / fichiers plats / zip sans arborescence.
- Pas de bundler, pas de framework, pas de npm sur le site live.
- CSP stricte dans le meta + `_headers` : `style-src 'self'`, fonts self-hosted, pas de Google Fonts sur la page principale (sauf 404 legacy).
- Valider chaque étape avec l’utilisateur avant gros changements de design ou de message.

## Quand ce skill s’active

- Édition de `index.html`, CSS, JS, 404, headers, sitemap
- Ajout d’un projet / client
- Changement d’email, domaine, OG, tarifs, copy
- Déploiement GitHub Pages / Cloudflare Pages
- Toute demande « améliores le site ER Digital »

## Anti-patterns

- Soft UI, gradients kitsch, photos stock de « équipe qui sourit »
- Google Fonts sur la page d’accueil (casse CSP + perf)
- Chemins `assets/…` tant que le dépôt reste plat
- OG qui pointe vers un domaine non résolu
- Anglais non sollicité sur l’UI principale
