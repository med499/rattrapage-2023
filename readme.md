# **Langages Web 3 ( JavaScript avancé )** 🌐

## **Projet final - rattrapage**

### Présentation

L’objectif de ce projet est de créer **une carte web des 15 plus grandes villes de la région d’Ile-de-france** avec les couches suivantes :

- Une couche de type raster : un **fond de carte Openstreetmaps**
- Une couche de polygones : **Les départements d’Ile-de-france**
- Une couche de points : **Les 15 plus grandes villes des départements d’Ile-de-france**

Le répertoire du projet est composé de :

- Le fichier **index.html** : le code HTML du projet
- Un dossier **/data** : contient le fichier de données

  - **departements.min.js** : le geojson des départements d’Ile-de-france **(NE PAS MODIFIER)**

- Le dossier **/js** :

  - **app.js** : contient la déclaration des variables de données geojson

- Le dossier **/css** :
  - **popup.css** : le code css de la popup

Le projet est basé sur les frameworks :

- Openlayers v6.5.0
- Bootstrap v 4.6.0

Les propriétés de l'objet geojson :

- **departements** :
  - code_chf
  - **_code_dept_**
  - code_reg
  - geo_point_2d
  - id_geofla
  - nom_chf
  - nom_dept
  - nom_reg
  - x_centroid
  - x_chf_lieu
  - y_centroid
  - y_chf_lieu

### Création de la carte

1. Créer une carte openlayers dans l'élément html _#map_ avec les options suivantes:
   - Le fond de carte OpenStreetMaps
   - Une vue centrée sur l'Ile de france
   - Un contrôleur de carte: l'échelle linéaire

### Première couche : Les départements de l'Ile-de-france

1. Transformer l'objet geojson **departements** _( voir app.js )_ à une couche de type vecteur avec le style suivant :

   - Bordure :
     - largeur : **1** ( pixel )
     - couleur : **#808080**
   - Remplissage :
     - opacité : **0.7**
     - couleur : utiliser **une couleur déferente pour chaque département** ( 8 couleurs ).

   > **_NOTE :_** Après la transformation de l'objet geojson **departements** à une liste de features. Chaque **feature** possèdera la propriété **_code_dept_** ( code département ). Utilisez cette propriété pour modifier la couleur du style.

2. Ajouter la couche des départements à la carte et lier sa visibilité à la checkbox **_Départements_**.

### Deuxième couche : Les villes

1. Créer la classe **City** avec les propriétés et les méthodes suivantes:

   - **Les propriétés**

     - Le nom
     - Le code du département
     - La population
     - La latitude
     - La longitude

   - **Les méthodes**
     - **getDescription:** retourne une description de la ville _( une chaîne de caractères )_

2. Transformer le tableau suivant à une liste d'objets de type **City**.

   | Ville                | Code département | Population | Latitude | Longitude |
   | -------------------- | ---------------- | ---------- | -------- | --------- |
   | Paris                | 75               | 2 206 488  | 48.85349 | 2.34839   |
   | Boulogne-Billancourt | 92               | 117 931    | 48.83530 | 2.24120   |
   | Saint-Denis          | 93               | 111 103    | 48.93577 | 2.35802   |
   | Argenteuil           | 95               | 110 388    | 48.94781 | 2.24928   |
   | Montreuil            | 93               | 106 691    | 48.86233 | 2.44121   |
   | Nanterre             | 92               | 93 742     | 48.89243 | 2.20732   |
   | Vitry-sur-Seine      | 94               | 92 531     | 48.78755 | 2.39221   |
   | Créteil              | 94               | 90 739     | 48.77703 | 2.45315   |
   | Asnières-sur-Seine   | 92               | 86 512     | 48.91071 | 2.28910   |
   | Versailles           | 78               | 85 771     | 48.80329 | 2.12690   |
   | Colombes             | 92               | 85 199     | 48.92286 | 2.25447   |
   | Aubervilliers        | 93               | 83 782     | 48.91440 | 2.38222   |
   | Aulnay-sous-Bois     | 93               | 83 584     | 48.93404 | 2.50005   |
   | Courbevoie           | 92               | 83 136     | 48.89530 | 2.25613   |
   | Rueil-Malmaison      | 92               | 78 794     | 48.87765 | 2.18024   |

3. Transformer **la liste des objets de type City** à une **couche de type vecteur**.

4. Ajouter **la couche des villes** à la carte et lier sa visibilité à la checkbox **_Villes_**.
