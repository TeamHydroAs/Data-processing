# Data-processing
Nettoyage et prétraitement des données pour la prédiction des inondations

## 1. Analyse et Nettoyage Initial des Données

**Statistiques Descriptives :** Pour commencer, nous avons générer des statistiques descriptives pour toutes les variables, ce qui a permis de comprendre la distribution, la moyenne, la médiane, et l'écart-type des données, établissant ainsi une base pour identifier les anomalies.

**Traitement des Valeurs Négatives :** Il a été observé que les données de précipitation contenaient des valeurs négatives, ce qui est incohérent avec leur nature. Ces valeurs ont été traitées comme des erreurs et ont été remplacées par des valeurs manquantes pour correction ultérieure.

**Visualisation des Données :** Des graphiques de séries temporelles ont été tracés pour étudier le comportement des données de précipitation, température, pression et débit, révélant des tendances et des saisonnalités. Ces graphiques montrent l'évolution des variables de facon journalière, mensuelle et annuelle la période d'étude.

**Détection des Valeurs Aberrantes :** L'utilisation de boxplots a permis d'identifier des valeurs aberrantes, qui pourraient être dues à des erreurs de mesure ou à des événements extrêmes (Ainsi, le traitement pourra être fait cas par cas).

**Imputation des Valeurs Manquantes :** Pour combler les lacunes causées par les valeurs négatives maintenant manquantes et d'autres lacunes existantes, nous avons appliqué une interpolation par la méthode du plus proche voisin, préservant ainsi la structure temporelle des données.

## 2. Normalisation des Données

**Application du MinMax Scaler :** Afin d'uniformiser l'échelle des variables numériques, nous avons utilisé le MinMax Scaler de sklearn. Cela garantit que toutes les variables numériques sont maintenant comprises entre 0 et 1, éliminant ainsi les biais dus à la différence d'échelles.

## 3. Analyse des Corrélations et Ingénierie des Caractéristiques

**Matrice de Corrélation :** Une analyse de corrélation a été effectuée pour évaluer la force et la direction des relations entre les caractéristiques et entre les caractéristiques et la variable cible.

**Évaluation de l'Importance des Variables :** Nous avons utilisé la fonctionnalité de sélection de caractéristiques intégrée dans l'algorithme RandomForest pour déterminer l'importance de chaque variable dans la prédiction des résultats.

**Création de Nouvelles Variables :** Sur la base des poids fournis par les résultats de RandomForest, nous avons combiné les précipitations de plusieurs stations pour créer une nouvelle variable composite qui représente les précipitations sur l'ensemble de la zone d'étude.

## 4. Fractionnement des Données

**Division des Ensembles de Données :** Les données ont été divisées en ensembles d'entraînement, de test et de validation dans les proportions de 70 %, 15 % et 15 % respectivement. Cette division stratégique assure que chaque ensemble est représentatif de l'ensemble des données et maintient l'intégrité de la distribution des données pour une évaluation fiable des modèles.
