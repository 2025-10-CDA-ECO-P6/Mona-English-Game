# English game - Intégration front-end
Ce projet consiste à réaliser une intégration front-end fidèle à une maquette graphique fournie par un client. L’objectif est de produire une interface responsive, propre, structurée, en respectant les bonnes pratiques HTML et SCSS.

## Technologies
- HTML5
- SCSS
- pnpm et Sass pour la compilation
- Git pour le versionning
- GitHub Pages pour l’hébergement

## Responsive 
### Approche Mobile First
Le CSS est écrit **d’abord pour les petits écrans (mobile)**, puis amélioré progressivement pour les écrans plus larges.

### Système de Breakpoints
Les breakpoints sont centralisés afin de garder une cohérence sur tout le projet :

```scss
$bp-sm: 576px;
$bp-md: 768px;
$bp-lg: 1024px;
$bp-xl: 1280px;
$bp-xxl: 1440px;
```

### Mixins pour le Responsive
Afin d’éviter de répéter les media queries, un mixin est utilisé :
```scss 
@use "breakpoints" as *;

@mixin respond($bp) {
  @if $bp ==sm {
    @media (min-width: $bp-sm) {
      @content;
    }
  }

  @else if $bp ==md {
    @media (min-width: $bp-md) {
      @content;
    }
  }

  @else if $bp ==lg {
    @media (min-width: $bp-lg) {
      @content;
    }
  }

  @else if $bp ==xl {
    @media (min-width: $bp-xl) {
      @content;
    }
  }

  @else if $bp ==xxl {
    @media (min-width: $bp-xxl) {
      @content;
    }
  }
}
```
Utilisation :  

```scss 
@include respond(md) { .container { padding: 2rem; } }
```

Cela permet de :
- D’avoir un code plus lisible.
- De centraliser la logique responsive.
- De modifier les breakpoints à un seul endroit.
- D’éviter les erreurs et les répétitions.

## Aperçu de l'intégration 
<div align="center">
  <img src="public/assets/images_git/homepage-desktop.png" width="60%" alt="Homepage Desktop">
  <img src="public/assets/images_git/homepage-mobile.png" width="5.5%" alt="Homepage Mobile">
</div>

## Deploiement
[!GithubPages] https://2025-10-cda-eco-p6.github.io/Mona-English-Game/