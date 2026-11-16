# Identification et évaluation des zones vertes à Sherbrooke

## Présentation

Ce projet vise à localiser et à caractériser les zones vertes sur le territoire de la ville de Sherbrooke. Il devra s’appuyer sur des données en accès libre et des traitements en Python. Les sources, la méthode et les indicateurs seront choisis après l’analyse des données disponibles. Les résultats pourront contribuer à mieux comprendre la répartition des zones végétalisées et leur lien éventuel avec les îlots de chaleur urbains; ce lien ne sera pas évalué directement sans données et méthode adaptées.

### Problématique

Comment localiser et quantifier les zones végétalisées à Sherbrooke à partir des données disponibles, et quels indicateurs permettent de les caractériser ?

### Objectifs

- Définir ce qui sera considéré comme une zone verte.
- Identifier et vérifier les données utiles au projet.
- Cartographier les zones vertes et calculer leurs caractéristiques, notamment leur superficie.
- Choisir des indicateurs adaptés aux données et aux objectifs.
- Présenter les résultats et documenter la méthode.

### Périmètre et limites

- **Territoire :** ville de Sherbrooke.
- **Période envisagée :** été 2024.
- **Imagerie retenue :** Landsat pour l’été 2024. Le produit, les scènes exactes et leur source restent à documenter et à vérifier.
- **Éléments inclus :** éléments végétalisés visibles dans les images retenues, sous réserve de préciser leur définition et la taille minimale détectable.
- **Éléments exclus :** état de santé de la végétation et biodiversité.
- **Résultats envisagés :** carte des zones vertes, couche avec des attributs (par exemple superficie et catégorie), tableau de synthèse et documentation de la méthode. La liste définitive reste à valider.
- **Limites à examiner :** disponibilité, date, résolution, couverture, licence et qualité des données; effet de ces limites sur les zones détectées et les indicateurs.

## Équipe

| Membre | Rôle ou responsabilités |
| --- | --- |
| Pierre Perrais | Gestion du projet et architecture |
| Jean-Marc Tibo | Données et validation |

Les responsabilités principales sont réparties; le mode de communication reste à convenir.

## Prochaines étapes

1. **Finaliser le cadrage en équipe :** définir une zone verte, les catégories visées, la taille minimale à détecter et les livrables.
2. **Vérifier l’imagerie Landsat de l’été 2024** dans [l’analyse des données](docs/data-assessment.md) : source, produit, dates des scènes, couverture, format, résolution, CRS, conditions d’accès, qualité et limites; préciser aussi la date exacte de remise.
3. **Compléter l’inventaire et vérifier les autres données utiles** dans [l’analyse des données](docs/data-assessment.md) : provenance, licence, emprise, unités et adéquation aux objectifs.
4. **Choisir la méthode après l’analyse des données** et la décrire dans [la conception de la solution](docs/solution-design.md), avec les indicateurs, les formats de sortie et les vérifications prévues.
5. **Planifier les étapes** en tenant compte de l’échéance d’environ un mois; noter les décisions confirmées et les questions ouvertes dans [le journal du projet](docs/project-journal.md).
6. **Développer les traitements Python**, vérifier les cartes et les mesures, puis documenter les résultats et leurs limites.

Ne supposez pas que les données sont compatibles parce qu’elles s’ouvrent : vérifiez notamment leur CRS, leur emprise, leurs unités et leurs limites avant de les analyser.

### Validation des développements

Après chaque exécution de tests, l’assistant IA présente les résultats et demande au développeur de les valider, soit en consultant le rapport, soit en effectuant une vérification manuelle. Une tâche ou une milestone ne passe à `Terminé` qu’après cette confirmation. Si les tests automatisés ne sont pas disponibles, l’assistant propose des étapes de test manuel et attend le retour du développeur.

## Données et reproductibilité

- Le `.gitignore` exclut le contenu de `data/` ; seuls les fichiers `.gitkeep` des répertoires `raw/`, `processed/` et `outputs/` préservent la structure dans Git. Ne forcez pas l’ajout de données au dépôt.
- Ne commitez aucun jeu de données, même s’il est petit. Documentez plutôt sa provenance, sa licence et les étapes permettant de l’obtenir. L’assistant IA doit refuser d’aider à committer des données et peut aider à préparer cette documentation ou un procédé de récupération.
- Ne commitez jamais de secrets : mots de passe, jetons, clés privées ou fichiers de configuration contenant des identifiants. Le `.gitignore` exclut notamment les `.env`, fichiers `credentials.*` et `secrets.*`, ainsi que les clés et certificats privés. Un `.env.example` doit contenir uniquement des valeurs fictives ou vides ; l’assistant IA doit vérifier le contenu des fichiers avant un commit.
- Documentez la provenance, la date, la licence et les limites de chaque source de données.
- Ne versionnez pas de données confidentielles, personnelles ou dont la redistribution n’est pas autorisée.
- Évitez d’ajouter au dépôt de gros fichiers reproductibles ou téléchargeables ; expliquez plutôt où les obtenir et comment les préparer.
- Conservez les données originales sans les modifier. Placez les données préparées et les résultats dans les répertoires correspondants.
- Notez les versions des outils et les étapes nécessaires pour reproduire les résultats.

## Travail avec Git

### Pour tous les projets

- Au début de chaque séance de travail, récupérez les changements du dépôt distant avec `git pull --ff-only`. Si vous avez des modifications locales non enregistrées ou si Git signale un conflit, sauvegardez votre travail et résolvez la situation avant de poursuivre ; ne l’écrasez pas.
- Après validation des changements, publiez-les dans le dépôt distant avec des commits structurés : un changement cohérent par commit et un message concis, par exemple `docs: préciser le démarrage` ou `feat: suivre les décisions`.
- L’assistant IA peut aider à vérifier l’état Git, préparer les messages et exécuter les commandes si le dépôt le permet et si vous l’autorisez.
- Ne remplacez pas le travail d’une autre personne sans en discuter.
- Gardez les décisions sur les données, le CRS, les unités et les méthodes documentées.

### En équipe

- Décidez ensemble de la répartition des tâches et de la façon de signaler les blocages.
- Si vous connaissez les branches Git, utilisez une branche par tâche et faites relire les changements avant de les intégrer à la branche principale.
- Évitez de modifier simultanément les mêmes fichiers ; prévenez l’équipe si un fichier partagé doit changer.
- En cas de conflit, comparez les changements et convenez de la version à conserver au lieu de choisir au hasard.

### En projet individuel

Utilisez aussi des commits comme points de sauvegarde et notez les décisions importantes. Cela facilite le suivi et le retour à une version antérieure.

## Structure du dépôt

Adaptez cette structure si le projet le nécessite.

```text
.
├── data/
│   ├── raw/         # Données sources (non modifiées)
│   ├── processed/   # Données préparées
│   └── outputs/     # Résultats produits
├── docs/            # Cadrage, données, conception et journal
├── src/             # Code source
├── tests/           # Tests
└── dashboard/       # Page HTML et données du tableau de bord
    ├── index.html
    └── dashboard-data.json
```

## Afficher le tableau de bord

La page charge automatiquement `dashboard-data.json`. Pour l’afficher dans un navigateur :

1. Installez l’extension **Live Server** dans VS Code, si nécessaire.
2. Ouvrez `dashboard/index.html`, puis cliquez sur **Go Live** dans la barre d’état ou choisissez **Open with Live Server** dans le menu contextuel.
3. La page s’ouvre dans votre navigateur. Vous pouvez aussi ouvrir l’adresse locale fournie par Live Server dans le navigateur intégré de VS Code, si disponible.

Les milestones qui contiennent des sous-étapes se replient et se déplient en cliquant sur leur titre. Survolez leur nom pour afficher l’indication « Cliquer pour voir les sous-étapes ». Un seul milestone peut être ouvert à la fois.

## Identifiants de suivi

Utilisez des identifiants stables dans le journal et le tableau de bord : `M-01` pour une milestone, `T-001` pour une tâche et `D-001` pour une décision. Attribuez les numéros dans l’ordre, ne les réutilisez pas et conservez-les si le libellé ou le statut change.

Les sous-étapes du cadrage reprennent les rubriques des documents de définition, d’analyse des données et de conception. Les autres milestones contiennent des sous-étapes génériques à adapter. Modifiez `dashboard/dashboard-data.json` pour ajuster chaque statut (`À faire`, `En cours`, `Terminé`), ainsi que la phase et la progression globale.

Les décisions à suivre sont les choix qui ont un impact structurant sur l’architecture de la solution, les formats de données ou le flux de traitement ; les petits choix opérationnels n’ont pas besoin d’être listés. Utilisez le statut `Confirmée`, `En attente`, `Reportée` ou `Suspendue`. Le tableau sépare les décisions confirmées des points à suivre ; les décisions ouvertes ne sont pas présentées comme des choix pris. Le tableau de bord contient quatre décisions marquées `EXEMPLE FICTIF` pour illustrer les statuts : supprimez-les ou remplacez-les avant de l’utiliser pour un projet réel.

```json
{
  "id": "D-001",
  "date": "AAAA-MM-JJ",
  "decision": "[Décision confirmée]",
  "status": "Confirmée",
  "reason": "[Raison de la décision]"
}
```

Ajoutez les décisions confirmées et les points structurants à suivre au journal, en distinguant clairement leur statut. Laissez `decisions` vide si le projet n’a encore aucun de ces éléments.

## Outils et exécution

- **Langage :** Python (exigé pour le projet).
- **Bibliothèques et logiciels :** à choisir après la définition de la méthode.
- **Installation et exécution :** à documenter lorsque l’environnement et les traitements auront été définis.

## Documentation du projet

- [Définition du projet](docs/project-definition.md)
- [Analyse des données](docs/data-assessment.md)
- [Conception de la solution](docs/solution-design.md)
- [Journal du projet](docs/project-journal.md)

## Références et remerciements

Les sources de données, références méthodologiques et licences seront ajoutées après l’inventaire et la sélection des données.
