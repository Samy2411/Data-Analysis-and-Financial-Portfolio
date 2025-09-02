# Data Analysis and Financial Portfolio
This repository showcases a comprehensive collection of data analysis and Financial projects completed during my Master's program in International Trade and Finance. The projects demonstrate Financial Knowledge, proficiency in statistical analysis, econometric modeling, and data visualization techniques applied to real-world economic and financial datasets.

# Project 1: Analyse de Portefeuille et Évaluation d'Actifs avec le Modèle CAPM

## Résumé Exécutif

Ce projet est une analyse quantitative complète d'un portefeuille d'actions françaises du CAC 40, menée en **Python**. L'objectif est de passer de données de marché brutes à une évaluation du risque systématique et du rendement attendu pour chaque actif, en utilisant le **Modèle d'Évaluation des Actifs Financiers (CAPM)**.

**Portefeuille Analysé :**
*   LVMH (`MC.PA`)
*   TotalEnergies (`TTE.PA`)
*   BNP Paribas (`BNP.PA`)
*   Airbus (`AIR.PA`)
*   **Indice de Marché :** CAC 40 (`^FCHI`)

**Méthodologie :**
1.  **Collecte de Données :** Téléchargement de 7 ans de données de prix journaliers via l'API `yfinance`.
2.  **Analyse Exploratoire :** Visualisation des performances normalisées (Base 100) pour une comparaison juste.
3.  **Calcul des Rendements :** Transformation des prix en rendements journaliers avec `pandas`.
4.  **Calcul du Bêta :** Pour chaque action, le Bêta a été déterminé par une **régression linéaire** (Moindres Carrés Ordinaires) de ses rendements sur ceux du marché, en utilisant la librairie `statsmodels`.
5.  **Application du CAPM :** Estimation du rendement annuel attendu pour chaque actif en fonction de son Bêta et d'hypothèses de marché (Taux sans risque, Prime de risque du marché).

**Principales Conclusions :**
*   L'analyse a révélé que les actions **Airbus (Bêta = 1.45)** et **BNP Paribas (Bêta = 1.32)** présentent le risque systématique le plus élevé, amplifiant les mouvements du marché.
*   Conformément à la théorie financière, ces actions à plus haut risque sont aussi celles qui offrent le **rendement attendu le plus élevé** selon le modèle CAPM (10.26% et 9.60% respectivement).
*   **TotalEnergies** s'est avérée être l'action la plus "défensive" du portefeuille, avec un Bêta proche de 1.
---
