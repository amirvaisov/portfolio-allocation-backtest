# Comparaison de 5 méthodes d'allocation de portefeuille

Backtest walk-forward sur 13 ETFs (2006-2025) comparant cinq méthodes d'allocation : Equal-weight, Max Sharpe, Min Variance, Risk Parity et Hierarchical Risk Parity (HRP).

## Résultat principal

Au coût de 10 points de base, **HRP obtient le meilleur Sharpe net (0,99)**, devant Risk Parity et Min Variance (0,83), Max Sharpe (0,80) et Equal-weight (0,65). HRP reste en tête jusqu'à 50 pb de frais.

Ce résultat s'explique surtout par une allocation concentrée sur les obligations courtes (environ 91 % en moyenne), ce qui réduit fortement la volatilité et les pertes en crise. Le Sharpe est calculé avec un taux sans risque de 0, ce qui favorise les portefeuilles obligataires : c'est une limite à garder en tête.

## Question

Une méthode d'allocation sophistiquée améliore-t-elle réellement la performance nette, face à une allocation simple ?

## Méthode

- Univers : 13 ETFs, depuis 2006
- Rééquilibrage mensuel, fenêtre glissante de 252 jours
- Covariance estimée par Ledoit-Wolf
- Frais de transaction : 10 pb
- Poids maximum par actif : 40 %

## Fichiers

- `allocation_portefeuille (1).ipynb` : notebook complet (données, méthodes, backtest, stress tests, sensibilité aux frais, surface de volatilité)

## Limites

- Taux sans risque fixé à 0 (un taux réel favoriserait moins les obligations)
- Comparaison non équilibrée en levier et en contrainte de poids
- Résultats sur une seule période et un seul univers
- Pas de prise en compte des impôts ni des frais de gestion

## Ouvrir le notebook

[Ouvrir dans Colab](https://colab.research.google.com/github/amirvaisov/portfolio-allocation-backtest/blob/main/allocation_portefeuille%20(1).ipynb)
