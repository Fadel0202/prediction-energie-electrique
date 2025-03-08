# Prévision de la Production d'Énergie en France

Ce projet vise à analyser et prédire la production d'énergie en France en utilisant des données publiques collectées via le site RTE. L'objectif final est de fournir des prévisions précises pour la production totale d'énergie pour juin 2024.

## Objectifs

1. **Collecte de données** : Récupération des données de production et de consommation d'énergie depuis le site RTE pour la période de janvier 2012 à mai 2024.
2. **Analyse des données** : Visualisation des tendances, identification de la part de chaque technologie de production, et analyse des périodes de haute production/consommation.
3. **Modélisation prédictive** : Développement d'un modèle SARIMA pour prévoir la production totale d'énergie pour juin 2024.


## Méthodologie

### 1. Collecte de Données
- Utilisation de techniques de web scraping pour extraire les données du site RTE
- Récupération des données historiques de production par filière et de consommation
- Stockage des données dans un format structuré pour l'analyse

### 2. Analyse Exploratoire
- Visualisation des tendances de production et consommation au fil du temps
- Analyse de la répartition des différentes technologies de production
- Identification des variations saisonnières et des pics de production/consommation

### 3. Modélisation Prédictive
- Préparation des séries temporelles pour la modélisation
- Implémentation d'un modèle SARIMA pour capturer à la fois les dépendances temporelles et la saisonnalité
- Évaluation du modèle à l'aide de la métrique MAPE (Mean Absolute Percentage Error)
- Génération de prévisions pour juin 2024

## Résultats

Le modèle SARIMA développé présente une performance solide avec une MAPE de 2,77% sur l'ensemble de test, ce qui est considéré comme une excellente précision pour ce type de prévision. Les prévisions pour juin 2024 prennent en compte les tendances historiques, les variations saisonnières, et les facteurs temporels affectant la production d'énergie.

## Dépendances

- Python 3.8+
- pandas
- numpy
- matplotlib
- seaborn
- statsmodels
- scikit-learn
- beautifulsoup4
- requests

## Installation

```bash
git clone https://github.com/username/energy-production-forecast.git
cd energy-production-forecast
pip install -r requirements.txt
```

## Utilisation

1. Exécutez les notebooks dans l'ordre pour reproduire l'analyse complète:
   ```
   jupyter notebook notebooks/01_data_collection.ipynb
   ```

2. Pour utiliser directement le modèle de prévision:
   ```python
   from src.models.sarima_model import SARIMAPredictor
   
   predictor = SARIMAPredictor()
   predictor.load_model('results/sarima_model.pkl')
   forecasts = predictor.forecast(steps=30)  # 30 jours pour juin 2024
   ```

## Conclusion

Le modèle SARIMA se révèle être un outil puissant pour la prévision de la production d'énergie en France, offrant une précision remarquable. Cette approche, combinant une préparation minutieuse des données, un choix judicieux des paramètres et une évaluation rigoureuse des résultats, permet une prise de décision éclairée dans le domaine énergétique.
