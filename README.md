# temperatures-predictions

## Objectif

L’objectif de ce notebook est de tester la classe de modèles ARIMA afin de prédire l’évolution de la température à Paris. Un objectif secondaire est de voir si la performance des modèles se dégrade au cours des années, ce qui suggèrerait que le climat se "dérègle".
Les prédictions se feront à l’année dans un premier temps, puis potentiellement à la semaine.

## Sources des données

La donnée analysée est l’évolution de la température maximale à Paris jour par jour depuis le 1er janvier 1975.

Les sources de données sont:
https://www.historique-meteo.net/france/ile-de-france/paris pour les données récentes.
https://agri4cast.jrc.ec.europa.eu/dataportal/ pour les archives plus anciennes.

Ces données sont mises en forme dans le notebook **meteo_exploration** pour construire le fichier final *formatted_data/full_meteo.csv*.

Il n’est pas nécessaire de refaire tourner le notebook meteo_exploration (les données brutes n’étant pas fournies dans ce repo), on pourra se contenter d’utiliser directement *formatted_data/full_meteo.csv*.

## Démarche

Deux approches naïves sont testées dans un premier temps, afin d’isoler la valeur ajoutée des modèles ARIMA: une prédiction à la moyenne (la température prédite pour chaque date est égale à la moyenne de la température sur cette date sur les années d’entraînement), et une prédiction avec une random forest qui prend en features les températures des jours précédents ainsi que le numéro du jour dans l’année pour prédire la température du jour.

L’approche par la moyenne est développée dans le notebook **1_mean_prediction** est l’approche random forest dans le notebook **2_random_forest_prediction**.

Ces approches sont ensuite comparées à un modèle ARIMA dans le notebook **3_ARIMA_meteo**.