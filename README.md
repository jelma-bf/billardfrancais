# 🎱 Billard Tracker

Application web pour suivre et analyser les parties de **billard français** (carambole) entre deux joueurs : score en direct, statistiques, historique et rapport d'analyse.

Tout fonctionne dans le navigateur, sans serveur, sans compte et sans connexion une fois la page chargée. Les données restent sur votre appareil.

## Fonctionnalités

- **Nouvelle partie** : choix du type de billard (petit ou grand), de l'objectif en points et du joueur qui commence.
- **Compteur** : saisie des points au clavier numérique, gestion des reprises, moyenne en direct pour chaque joueur, annulation de la dernière reprise.
- **Statistiques** : moyennes, victoires, évolution des performances.
- **Historique** : liste de toutes les parties enregistrées.
- **Analyse** : page séparée qui génère un rapport texte comparant les deux joueurs (verdict par type de billard, parties serrées, forme récente), enregistrable en fichier `.txt`.
- **Export et import JSON** : sauvegarde et restauration des données.
- **Adapté tablette et ordinateur** : mise en page en deux colonnes en mode paysage, plein écran, utilisable comme une app depuis l'écran d'accueil.

## Utilisation

### En ligne

Ouvrez l'adresse du site publié sur GitHub Pages :

```
https://<votre-pseudo>.github.io/<nom-du-depot>/
```

### En local

Téléchargez le dépôt et ouvrez `index.html` dans un navigateur. Pour un usage complet, servez le dossier avec un petit serveur local :

```
python3 -m http.server 8000
```

puis ouvrez `http://localhost:8000`.

### Installer sur iPad ou iPhone

1. Ouvrez le site dans Safari.
2. Touchez **Partager**, puis **Sur l'écran d'accueil**.
3. Lancez l'application depuis l'icône : elle s'ouvre sans la barre du navigateur.

## Données et sauvegarde

- Les parties sont enregistrées dans le **stockage local du navigateur** (`localStorage`). Elles ne sont envoyées nulle part.
- Le stockage dépend de l'adresse du site et de l'appareil : changer d'adresse, de navigateur ou d'appareil donne un tracker vide.
- Pensez à **exporter régulièrement vos données en JSON**. Le fichier sert de sauvegarde et permet de transférer les parties d'un appareil à un autre via **Importer**.
- Effacer les données du site dans le navigateur supprime aussi les parties enregistrées.

Format du fichier JSON :

```json
{
  "players": { "player1": "Joueur A", "player2": "Joueur B" },
  "matches": [ ]
}
```

## Structure du dépôt

| Fichier | Rôle |
| --- | --- |
| `index.html` | Le tracker (compteur, statistiques, historique) |
| `analyse.html` | L'analyseur de données, qui lit les parties du tracker ou un fichier JSON importé |

Chaque page est un fichier HTML autonome : le style et le code sont intégrés, il n'y a rien à installer ni à compiler.

## Mise à jour

Remplacez le fichier concerné dans le dépôt (**Add file → Upload files**, avec le même nom). GitHub Pages redéploie le site automatiquement en une à deux minutes.

## Compatibilité

- **Ordinateur** : Chrome, Edge, Safari et Firefox récents. Sur Chrome et Edge, l'export peut proposer le choix de l'emplacement du fichier.
- **iPad et iPhone** : Safari. L'export passe par la feuille de partage (*Enregistrer dans Fichiers*).

## Licence

À définir.
