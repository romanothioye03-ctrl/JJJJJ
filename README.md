# Prèsséa Mauritanie — site vitrine

Site vitrine/catalogue autonome de Prèsséa Mauritanie avec les photos, animations, gammes, saveurs, tarifs MRU et boutons WhatsApp.

## Utilisation locale

Le site est contenu dans `index.html` et peut être ouvert directement dans un navigateur. Pour éviter les restrictions liées aux scripts et aux ressources distantes, il est recommandé de lancer un serveur HTTP simple :

```bash
python3 -m http.server 8000
```

Puis ouvrir `http://localhost:8000`.

## WhatsApp

Les boutons WhatsApp redirigent vers **SMP Smart Pro Solution**, au numéro mauritanien **+222 31 31 45 47** :

```text
https://wa.me/22231314547
```

## Contenu du dépôt

- `index.html` : version finale autonome du site avec les 60 photos intégrées/référencées et la configuration WhatsApp mise à jour ;
- `pressea-mauritanie-60-photos.html` : copie nommée de l’export final ;
- `references/` : exports HTML précédents utilisés comme références ;
- `docs/PROMPT-RECREATION.md` : prompt complet pour reconstruire le site en Next.js avec navigation, animations et gestion des images.

Le site est une présentation sans panier ni paiement en ligne.
