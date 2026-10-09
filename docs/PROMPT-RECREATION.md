# Prompt complet à copier-coller

Tu es un développeur senior spécialisé en **Next.js, React, TypeScript, Tailwind CSS et interfaces premium**. Je vais te fournir :

1. le fichier HTML de référence `pressea-mauritanie.html` ;
2. le nouvel export complet `pressea-mauritanie-60-photos.html` ;
3. environ **60 photos originales** de la marque Prèsséa Mauritanie.

Ta mission est de **recréer le site de A à Z**, le plus fidèlement possible, en utilisant réellement chaque photo à l’endroit où elle correspond le mieux. Ne crée pas une simple page d’inspiration et ne remplace pas les photos par des images génériques.

---

## 1. Objectif principal

Reproduis le site vitrine/catalogue **Prèsséa Mauritanie** à partir du fichier HTML de référence et des photos fournies.

Le résultat doit respecter :

- la même hiérarchie visuelle ;
- les mêmes pages et URLs ;
- les mêmes textes et libellés visibles ;
- les mêmes gammes, saveurs, prix et formats ;
- les mêmes couleurs de marque ;
- les mêmes cartes produits et galeries ;
- le même comportement responsive ;
- les mêmes interactions de navigation, filtres, carrousels et boutons WhatsApp ;
- les animations et transitions similaires, sans ralentir le site ;
- une vraie redirection fonctionnelle à chaque clic important ;
- une qualité visuelle professionnelle sur mobile, tablette et desktop.

**Important : le fichier `pressea-mauritanie-60-photos.html` est la source de vérité principale.** Il s’agit de l’export complet fourni via ClickUp, avec les références des photos, les composants, les routes, les interactions et les animations. Analyse ce fichier en priorité avant de coder. Utilise `pressea-mauritanie.html` comme référence complémentaire si nécessaire. Si une information existe dans les exports, réutilise-la au lieu de l’inventer.

Le fichier complet contient notamment les identifiants d’assets suivants, qui doivent être associés aux photos correspondantes et non remplacés par des images génériques : `logo`, `nec-caisse`, `nec-trio`, `nec-cocktail-fetes`, `nec-carre`, `nec-ananas`, `nec-bissap-gingembre`, `nec-cocoananas`, `sel-passion`, `sel-multifruits`, `sel-trio`, `sel-orange`, `sel-raisin`, `can-orange`, `can-cocoananas`, `can-goyave`, `can-tropical`, `fcan-goyave`, `fcan-orange`, `fcan-tropical`, `fcan-mangue`, `fcan-ananascoco`, `fb-orange`, `fb-tropical`, `fb-manguecoco`, `mini-ananas`, `mini-cocktail`, `mini-orange`, `mini-pomme`, `fb-femme`, `mini-rentree`, `nec-avis`, `gamme-complete`, `nec-cocoananas-fetes`, `fb-glacons` et `mini-petits-fruites`.

Les exports complets montrent notamment le hero animé, le ticker horizontal des saveurs, le header sticky avec effet de flou, les cartes de gammes avec zoom au survol, la sélection de gamme avec anneau jaune, le sélecteur de saveur précédent/suivant, le menu mobile animé et les boutons WhatsApp. Ne supprime aucune de ces animations pendant la conversion en Next.js.

## 1.1 Navigation obligatoire au clic

Ne livre pas une maquette statique avec des boutons qui ne font rien. **Chaque élément cliquable doit avoir un comportement réel et vérifié.**

Utilise `next/link` pour les navigations internes et des liens `<a>` fonctionnels pour les liens externes. N’utilise pas uniquement des `onClick` décoratifs et ne remplace pas une vraie page par une simple section vide.

Le comportement attendu est le suivant :

| Élément cliqué | Comportement obligatoire |
|---|---|
| Logo / accueil | Aller vers `/` |
| « Découvrir nos gammes » | Aller vers `/gammes` |
| Carte d’une gamme | Aller vers `/gammes/[slug]` |
| Bouton « Toutes les gammes » | Aller vers `/gammes` |
| Une saveur | Aller vers `/gammes/[slug]?saveur=[id]` |
| « Voir les saveurs » | Aller vers `/saveurs` |
| « Je découvre les produits » | Aller vers `/particuliers` |
| « Je suis un professionnel » | Aller vers `/professionnels` |
| « À propos » | Aller vers `/a-propos` |
| « Contact » | Aller vers `/contact` |
| Navigation du header et du footer | Aller vers la page correspondante |
| Bouton WhatsApp | Ouvrir le lien WhatsApp avec un message prérempli |
| Flèches précédent / suivant | Changer réellement la saveur active |
| Filtres par gamme | Filtrer réellement les produits affichés |
| Menu mobile | S’ouvrir, fermer et naviguer correctement |

Les ancres comme `#gammes`, `#saveurs` et `#pros` peuvent être conservées uniquement lorsqu’elles correspondent à un lien de section prévu par le design. Elles ne doivent pas remplacer les pages demandées. Si un élément est présenté comme une carte produit, une gamme, une saveur ou une page du site, son clic doit ouvrir la route correspondante.

Après chaque clic, vérifie que :

- l’URL change lorsque le lien doit changer de page ;
- la page cible existe réellement ;
- la page ne donne pas une 404 inattendue ;
- le bon contenu et la bonne photo sont chargés ;
- le scroll revient en haut de la nouvelle page, sauf pour une ancre volontaire ;
- le bouton ou le lien garde son état visuel actif ;
- le bouton retour du navigateur fonctionne ;
- les liens fonctionnent aussi sur mobile.

Interdiction de laisser des `href="#"`, des boutons sans action, des routes inventées non implémentées ou des liens qui redirigent vers une page blanche.

## 1.2 Animations obligatoires à reproduire

Les animations ne doivent pas être supprimées au moment de convertir le site en Next.js. Reproduis l’intention et le rythme des animations visibles dans les exports :

- header sticky avec `backdrop-blur` et transition de fond ;
- apparition progressive du contenu du hero ;
- légère entrée verticale des titres, textes et boutons ;
- zoom lent des images au survol des cartes ;
- déplacement vertical subtil des cartes au survol ;
- ticker horizontal continu des saveurs ;
- transition fluide de la gamme active ;
- anneau jaune et changement de couleur sur la carte sélectionnée ;
- changement animé du packshot et du nom de la saveur ;
- transitions des flèches précédent/suivant ;
- ouverture et fermeture animées du menu mobile ;
- bouton WhatsApp flottant avec léger effet de scale au survol ;
- apparition des sections au scroll avec `whileInView` ou Intersection Observer ;
- vagues et formes décoratives sans provoquer de débordement horizontal.

Respecte les règles suivantes :

1. utilise Framer Motion ou des animations CSS propres ;
2. applique `prefers-reduced-motion` pour désactiver ou réduire les mouvements ;
3. ne transforme pas les animations en simples effets instantanés ;
4. ne mets pas d’animation lourde sur les images qui rendrait le site lent ;
5. vérifie les animations sur mobile tactile, sans dépendre uniquement du hover ;
6. utilise des transitions cohérentes, généralement entre 200 et 800 ms selon l’effet ;
7. conserve la lisibilité du texte pendant les transitions ;
8. fais fonctionner les animations en même temps que la navigation réelle.

---

## 2. Stack technique obligatoire

Utilise :

- **Next.js 14 ou supérieur**, App Router ;
- **TypeScript** strict ;
- **Tailwind CSS** ;
- **Framer Motion** pour les animations ;
- **Lucide React** ou une bibliothèque d’icônes équivalente ;
- composants réutilisables et architecture propre ;
- `next/image` pour toutes les images ;
- métadonnées SEO avec `generateMetadata` ;
- aucune dépendance inutile ;
- code propre, maintenable et typé.

Structure recommandée :

```text
app/
  layout.tsx
  page.tsx
  gammes/page.tsx
  gammes/[slug]/page.tsx
  saveurs/page.tsx
  particuliers/page.tsx
  professionnels/page.tsx
  a-propos/page.tsx
  contact/page.tsx
components/
  Header.tsx
  MobileMenu.tsx
  Footer.tsx
  Hero.tsx
  PageHeader.tsx
  RangeCard.tsx
  FlavorCard.tsx
  FlavorPicker.tsx
  PriceTable.tsx
  WhatsAppButton.tsx
  Gallery.tsx
  SectionTitle.tsx
  MotionWrapper.tsx
lib/
  data.ts
  images.ts
  whatsapp.ts
public/images/
```

---

## 3. Gestion obligatoire des 60 photos

Avant de coder les pages :

1. inspecte les 60 photos une par une ;
2. renomme-les avec des noms propres et stables ;
3. copie-les dans `public/images/originals/` ;
4. crée un fichier `lib/images.ts` contenant un mapping centralisé ;
5. associe chaque photo à son usage exact ;
6. contrôle pour chaque photo sa netteté, sa résolution, son ratio, son orientation, son cadrage, son exposition, ses couleurs et la visibilité du produit ;
7. conserve le cadrage, le sujet et l’ambiance de chaque photo lorsqu’ils sont exploitables ;
8. utilise `object-cover`, `object-contain`, un recadrage focalisé ou une version adaptée selon le composant qui reçoit l’image ;
9. ajoute un texte `alt` descriptif en français ;
10. crée les variantes nécessaires pour les formats hero, carte, carré, portrait, paysage et galerie ;
11. utilise les images optimisées finales dans le site et non les originaux trop lourds ;
12. documente chaque décision dans `IMAGE-MAPPING.md`.

### Règle impérative de remplacement des images

Si une photo est floue, pixelisée, trop petite, mal cadrée, déformée, surexposée, inutilisable dans le ratio demandé ou ne permet pas de voir correctement le produit, **ne l’intègre pas telle quelle**.

Dans ce cas :

1. essaie d’abord une correction non destructive : recadrage, redimensionnement, amélioration légère de netteté, correction de luminosité et conversion dans un format adapté ;
2. si la qualité reste insuffisante, génère **une nouvelle image de remplacement** qui respecte exactement le produit, l’emballage, les couleurs, le logo, le parfum et le contexte de la photo originale ;
3. si l’image montre un emballage ou un produit de marque, ne modifie jamais son texte, son logo, ses proportions ou ses couleurs ;
4. ne remplace pas une photo simplement parce qu’elle n’est pas parfaite : remplace-la seulement si elle ne peut pas produire un rendu professionnel dans son emplacement ;
5. place la nouvelle image dans `public/images/generated/` ;
6. utilise cette nouvelle image dans le mapping du site ;
7. indique dans `IMAGE-MAPPING.md` le nom de l’original, le problème détecté, la correction effectuée et le nom de la nouvelle image ;
8. ne laisse aucune image floue ou déformée apparaître dans la version finale.

Pour les images générées, respecte obligatoirement :

- le même produit et le même parfum que sur la photo source ;
- le même style visuel et la même identité Prèsséa ;
- une image nette en haute résolution ;
- un cadrage adapté à l’emplacement réel ;
- aucun texte inventé sur l’emballage ;
- aucun logo déformé ;
- aucun produit supplémentaire non demandé ;
- un ratio correspondant au composant qui l’utilise.

Les ratios à préparer sont notamment :

| Usage | Ratio recommandé |
|---|---:|
| Hero principal | 16:9 ou 4:3 selon la composition |
| Visuel produit vertical | 4:5 ou 3:4 |
| Carte de gamme | 1:1 ou 4:5 |
| Saveur / packshot | 1:1 ou 4:5 |
| Galerie lifestyle | 4:3, 3:2 ou 1:1 |
| Bannière pleine largeur | 16:9 |

Ne déforme jamais une photo pour forcer un ratio. Utilise un recadrage intelligent ou génère une variante dédiée.

Exemple de mapping attendu :

```ts
export const images = {
  hero: "/images/hero-fb-woman.jpg",
  nectarCover: "/images/nec-crate.jpg",
  nectarGallery: [
    "/images/nec-trio1l.jpg",
    "/images/nec-fetes.jpg",
    "/images/nec-avis.jpg",
  ],
  // ... toutes les autres images
} as const;
```

Le mapping doit aussi préciser si une image est originale, optimisée ou générée :

```ts
export const imageMeta = {
  hero: {
    src: "/images/generated/hero-fb-woman-4x3.jpg",
    source: "generated",
    original: "/images/originals/photo-12.jpg",
    ratio: "4:3",
    alt: "Jeune femme en jaune à côté d’une bouteille Prèsséa Fresh Mangue Coco",
  },
} as const;
```

Pour déterminer la destination d’une photo, utilise dans cet ordre :

1. son contenu visuel réel ;
2. son nom de fichier éventuel ;
3. sa relation avec une gamme ou une saveur ;
4. les emplacements visibles dans le HTML de référence ;
5. la qualité finale nécessaire pour le composant concerné.

Crée si nécessaire un fichier `IMAGE-MAPPING.md` expliquant quelle photo a été placée dans chaque section.

---

## 4. Identité visuelle à reproduire

Reprends exactement l’esprit du site de référence :

- marque : **Prèsséa Mauritanie** ;
- signature : **« Le fruit de vos beaux moments »** ;
- style éditorial, joyeux, premium, chaleureux et familial ;
- grandes typographies expressives ;
- titres arrondis et très visibles ;
- textes secondaires lisibles et aérés ;
- cartes aux coins fortement arrondis ;
- formes organiques et vagues SVG entre les sections ;
- textures légères de type grain ;
- ombres douces et profondes ;
- animations d’apparition au scroll ;
- petits effets de parallaxe sur le hero desktop ;
- boutons fortement contrastés ;
- grille responsive avec beaucoup d’espace blanc.

### Palette à utiliser

```text
Vert profond / forest : #0D4526
Vert nuit : #072B17
Jaune soleil : #FFD000
Orange : #F39200
Orange vif : #FF8A00
Rose / framboise : #D4145A
Crème : #FFF8E6
Fond papier : #FCF7EA
Texte secondaire : #637064
Or sélection : #E2B850
```

Utilise les polices proches de la référence :

- titres : **Bricolage Grotesque** ;
- texte courant : **Work Sans**.

---

## 5. Pages à créer

Le périmètre comprend **8 pages principales**, les pages dynamiques des **5 gammes** et une page 404.

### A. Accueil `/`

Reproduis toutes les sections de l’accueil :

1. header responsive avec logo, navigation et bouton menu mobile ;
2. hero principal avec :
   - « Prèsséa en Mauritanie · Nouakchott » ;
   - titre « Le fruit de vos beaux moments » ;
   - texte de présentation ;
   - bouton « Découvrir nos gammes » ;
   - bouton « Vous êtes professionnel ? » ;
   - composition visuelle avec la photo principale et plusieurs packshots superposés ;
3. vague décorative en bas du hero ;
4. bandeau défilant des saveurs ;
5. deux grandes cartes :
   - « Je découvre les produits » ;
   - « Je suis un professionnel » ;
6. section « Un format pour chaque moment » ;
7. aperçu des cinq gammes ;
8. section tarifs « Les prix, sans détour » ;
9. section espace professionnels ;
10. footer complet ;
11. bouton flottant WhatsApp ;
12. gestion correcte du bouton de validation éditoriale si celui-ci existe dans le HTML.

### B. Gammes `/gammes`

Créer :

- hero « Cinq gammes, un même goût du partage » ;
- grille des cinq gammes ;
- cartes avec image, couleur, format, nombre de saveurs et lien ;
- tableau comparatif des formats et prix ;
- navigation vers chaque page dynamique de gamme.

### C. Page dynamique de gamme `/gammes/[slug]`

Créer une vraie page dynamique pour chacune des gammes :

- `/gammes/nectar` ;
- `/gammes/nouvelle-collection` ;
- `/gammes/canette` ;
- `/gammes/fresh-bouteille` ;
- `/gammes/mini`.

Chaque page doit inclure :

- hero coloré propre à la gamme ;
- nom, format, tagline et introduction ;
- visuel de couverture ;
- sélecteur de saveurs interactif ;
- image principale de la saveur active ;
- boutons précédent/suivant ;
- accès direct par query string, par exemple `?saveur=mangue` ;
- grille de toutes les saveurs ;
- galerie lifestyle propre à la gamme ;
- prix à l’unité et prix du pack ;
- bloc de contact particuliers ;
- bloc de contact professionnels ;
- liens vers les autres gammes ;
- fil d’Ariane.

### D. Saveurs `/saveurs`

Créer :

- hero « À chacun sa saveur Prèsséa » ;
- filtres par gamme ;
- compteur de saveurs affichées ;
- grille responsive de toutes les saveurs ;
- image, nom, ligne produit, prix unitaire et prix pack ;
- animation de filtrage ;
- clic vers la page de gamme avec la bonne saveur sélectionnée.

### E. Particuliers `/particuliers`

Créer :

- hero dédié aux particuliers ;
- section « Quel Prèsséa pour quel moment ? » ;
- sections famille, pause, goûter ;
- photos lifestyle appropriées ;
- cartes et liens vers les gammes ;
- rappel des tarifs ;
- appel à contacter Prèsséa sur WhatsApp.

### F. Professionnels `/professionnels`

Créer :

- hero espace professionnels ;
- onglets d’activité : distributeur, revendeur/boutique, café/snack, restaurant, hôtel ;
- pour chaque activité, afficher les gammes recommandées ;
- tableau des prix à l’unité et packs ;
- bouton « Contacter l’équipe professionnelle » ;
- mention que le site ne prend pas de commande en ligne ;
- section finale « Parlons de votre activité à Nouakchott ».

### G. À propos `/a-propos`

Créer :

- hero « Avec vous depuis 20 ans » ;
- présentation de Prèsséa et du groupe Kirène ;
- section « Une marque, cinq gammes » ;
- boutons colorés vers les gammes ;
- galerie dédiée aux Mini Prèsséa ;
- photos correspondantes parmi les 60 images.

### H. Contact `/contact`

Créer :

- hero « Une question ? Écrivez-nous » ;
- carte particuliers ;
- carte professionnels ;
- bouton WhatsApp pour chaque public ;
- bloc avec numéro WhatsApp configurable ;
- texte indiquant que le site ne prend pas de commande ;
- ne pas inventer d’adresse, d’e-mail ou de réseaux sociaux absents de la référence.

### I. Page 404

Créer une page 404 avec :

- « Oups. » ;
- « Cette page n’existe pas. » ;
- bouton « Retour à l’accueil ».

---

## 6. Données produits à intégrer

Utilise une architecture data-driven dans `lib/data.ts`.

### Gamme 1 — Prèsséa Nectar & Mix

- slug : `nectar`
- format : Brique 1 L
- prix unitaire : 150 MRU
- prix pack : 1 500 MRU
- pack : 12
- couleur : `#F39200`
- saveurs : Mangue, Orange, Cocktail, Goyave, Ananas, Jus de Bissap, Coco Ananas, Cocktail Mango, Mangue Passion, Ananas Gingembre

### Gamme 2 — Nouvelle collection Prèsséa

- slug : `nouvelle-collection`
- format : Brique 1 L · Sélection Prèsséa
- prix unitaire : 200 MRU
- prix pack : 2 250 MRU
- pack : 12
- couleur : `#0D4526`
- saveurs : Passion, Multifruits, Ananas, Orange, Raisin

### Gamme 3 — Prèsséa en canette

- slug : `canette`
- format : Canette · Prèsséa et Prèsséa Fresh
- prix unitaire : 35 MRU
- prix pack : 750 MRU
- pack : 24
- couleur : `#FFD000`
- saveurs : Orange, Coco Ananas, Goyave, Tropical, Goyave Fresh, Orange Fresh, Tropical Fresh, Mangue Fresh, Ananas Coco Fresh

### Gamme 4 — Prèsséa Fresh en bouteille

- slug : `fresh-bouteille`
- format : Bouteille · Prèsséa Fresh
- prix unitaire : 25 MRU
- prix pack : 250 MRU
- pack : 12
- couleur : `#FF8A00`
- saveurs : Orange, Tropical, Mangue Coco

### Gamme 5 — Mini Prèsséa

- slug : `mini`
- format : Mini brique 200 ml
- prix unitaire : 20 MRU
- prix pack : 450 MRU
- pack : 24
- couleur : `#D4145A`
- saveurs : Ananas, Cocktail, Orange, Pomme

Ne transforme pas le site en marketplace : **il s’agit d’un site de présentation sans panier et sans paiement en ligne**. Les boutons de contact doivent ouvrir WhatsApp.

---

## 7. WhatsApp

Configure WhatsApp pour **SMP Smart Pro Solution** avec le numéro mauritanien **+222 31 31 45 47**. Le numéro sans espaces ni signe `+` à utiliser dans `wa.me` est `22231314547`.

Le numéro doit rester configurable dans une variable d’environnement :

```env
NEXT_PUBLIC_WHATSAPP_NUMBER=22231314547
```

Utilise des messages contextuels :

- général : « Bonjour SMP Smart Pro Solution, je souhaite obtenir des informations sur les produits Prèsséa. » ;
- professionnel : « Bonjour SMP Smart Pro Solution, je suis un professionnel à Nouakchott et je souhaite obtenir des informations sur les gammes Prèsséa. » ;
- gamme : message contenant le nom de la gamme ;
- saveur : message contenant la gamme et la saveur sélectionnée.

Les liens doivent utiliser `https://wa.me/` avec un texte encodé proprement.

---

## 8. Responsive et accessibilité

Le site doit être excellent sur :

- mobile 320 px et plus ;
- tablette ;
- desktop 1440 px et plus.

Obligatoire :

- menu mobile fonctionnel ;
- navigation clavier ;
- focus visible ;
- textes alternatifs ;
- liens et boutons accessibles ;
- `aria-current` sur la page active ;
- `aria-pressed` pour les filtres et saveurs ;
- respect de `prefers-reduced-motion` ;
- contrastes lisibles ;
- aucun débordement horizontal non prévu ;
- tableaux utilisables sur petit écran avec scroll horizontal contrôlé.

---

## 9. SEO et performance

Ajoute :

- titres et descriptions propres à chaque page ;
- Open Graph ;
- favicon et identité Prèsséa si disponibles ;
- URLs propres ;
- `sitemap.ts` ;
- `robots.ts` ;
- images optimisées avec `next/image` ;
- lazy loading des galeries ;
- aucun layout shift important ;
- composants serveur par défaut lorsque possible ;
- composants client uniquement pour les interactions.

---

## 10. Méthode de travail obligatoire

Travaille dans cet ordre :

1. lis et analyse entièrement `pressea-mauritanie.html` ;
2. inspecte les 60 photos ;
3. produis une table de correspondance photo → emplacement ;
4. initialise le projet Next.js ;
5. crée les données centralisées ;
6. crée les composants réutilisables ;
7. implémente le layout, le header et le footer ;
8. implémente l’accueil ;
9. implémente les pages publiques ;
10. implémente les pages dynamiques des gammes ;
11. branche toutes les photos ;
12. ajoute les animations ;
13. ajoute WhatsApp ;
14. ajoute SEO et accessibilité ;
15. lance le projet et vérifie chaque URL ;
16. corrige les erreurs TypeScript, console et responsive ;
17. termine uniquement lorsque toutes les pages sont navigables.

Ne t’arrête pas après avoir créé une maquette. Je veux un **projet complet qui fonctionne**.

---

## 11. Critères de validation finale

Avant de livrer :

- vérifie que `npm run build` fonctionne ;
- vérifie que `npm run lint` fonctionne ;
- vérifie que toutes les images chargent ;
- vérifie les 8 pages principales et les 5 pages dynamiques ;
- vérifie les liens des filtres et des saveurs ;
- vérifie les boutons WhatsApp ;
- vérifie l’affichage mobile ;
- vérifie qu’aucune image n’est utilisée au mauvais endroit ;
- vérifie que les prix sont en MRU ;
- vérifie qu’il n’y a ni panier, ni paiement, ni fausse commande ;
- vérifie que les textes restent en français ;
- vérifie que la navigation ne recharge pas inutilement les pages ;
- fournis un résumé des fichiers créés et des commandes de lancement.

Si une donnée ou une photo est ambiguë, **ne l’invente pas** : conserve la donnée du HTML, choisis l’emplacement visuellement le plus cohérent et signale l’ambiguïté dans `IMAGE-MAPPING.md`.

Le rendu final doit donner l’impression que le site original a été reconstruit proprement avec Next.js, et non qu’un nouveau site approximatif a été imaginé.
