# Análise de Séries Temporais para Previsão de Demanda.
  
 [![author](https://img.shields.io/badge/author-wildt-red.svg)](https://www.linkedin.com/in/carlosfab) [![](https://img.shields.io/badge/python-3.7+-blue.svg)](https://www.python.org/downloads/release/python-365/) [![GPLv3 license](https://img.shields.io/badge/License-GPLv3-blue.svg)](http://perso.crans.org/besson/LICENSE.html) [![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/carlosfab/data_science/issues)


<p align="center"> 
  <img src="bild/data-analytics-696x464 (1).jpg">       
</p>  

# Alexandre Wildt Graziani 
<sub>*Lead Data Scientist*</sub>


Este projeto tem como objetivo desenvolver um modelo de previsão para a indústria de vinhos, a fim de otimizar as quantidades de pedidos com base em dados históricos de vendas. O Facebook Prophet é utilizado como modelo de série temporal para capturar padrões sazonais e tendências. Para otimizar os parâmetros do modelo, é empregado o Optuna, enquanto a qualidade do modelo é avaliada com Validação Cruzada (validação de série temporal). As principais métricas para avaliação do modelo são o MAPE (Erro Percentual Absoluto Médio) e o MAE (Erro Absoluto Médio), para medir a precisão da previsão tanto durante a otimização quanto em dados de teste.

<br>
<p align=center>
<img src="https://github.com/rafaelnduarte/sigmoidal_data/blob/master/Screen%20Shot%202021-04-01%20at%2012.04.22.png?raw=true" width="70%"></p>
<br/>


**Links:**
* [Notebook](https://colab.research.google.com/drive/1o_ijHL6dHLOSzrjyJuSo6KMShgGtTf9O?usp=sharing)
* [Medium](https://medium.com/@alexandrewildtgraziani/time-series-data-with-facebook-prophet-3d9ac21fef6c)
* [Blog](https://sigmoidal.ai)

### Obtenção dos Dados
Todos os dados utilizados aqui foram fornecidos por [Rafael Duarte](https://www.linkedin.com/in/rafael-n-duarte/?source=user_about----------------------95e660a7ce9---------------) e pela Sigmoidal..

Os dados estão divididos em dois arquivos: um contém os dados históricos de vendas, e o outro contém informações sobre os vinhos. Ambos os arquivos foram armazenados na nuvem::

- products.csv – Carta de vinhos de um e-commerce de vinhos. A carta de vinhos e os produtos nela contidos são baseados no catálogo real de um e-commerce de vinhos nos EUA. Os nomes, safras e preços são totalmente autênticos e foram convertidos para dólares americanos para permitir uma comparação e alcance internacionais.

- sales.csv – Este conjunto de dados originalmente abrangia 5 anos de vendas diárias, distribuídas em 10 lojas, com um catálogo de 50 produtos. No entanto, foi modificado e agora abrange 3 anos de vendas diárias, distribuídas em 3 lojas com 219 produtos diferentes em estoque.


<br>

### Ziel 

Das Unternehmen entwickelt eine KI-gestützte Lösung zur Optimierung des Bestandsmanagements in Weinhandlungen. Im Kern steht ein Machine-Learning-Modell, das die zukünftige Nachfrage basierend auf historischen Verkaufsdaten präzise prognostiziert.

Der Fokus liegt darauf, die Prognosemethodik weiter zu verfeinern, um den besonderen Herausforderungen des Weinmarktes gerecht zu werden. Dazu zählen Faktoren wie Jahrgangsschwankungen, saisonale Nachfrage, begrenzte Verfügbarkeit und Wertsteigerung einzelner Weine.

<br>

### Projektstruktur

Das Ziel das Projekt ist eine explorative Datenanalyse (EDA) durchzuführen. Wir werden die ersten Einblick in der Daten erhalten, Muster identifizieren und Hypothesen aufstellen.
Die folgenden schritt werden in der Analyse durch durchgeführt

**1.  Datenvorbereitung**

        1.1 Datenimport: Laden der Verkaufsdaten aus CSV-Dateien oder einer Datenbank.

        1.2 Erste Datenanalyse: Überblick über Spalten, Datentypen und erste visuelle Inspektion.

        1.3 Datenbereinigung: Behandlung fehlender Werte, Entfernen von Dubletten und Identifikation von Ausreißern.

**2. Explorative Datenanalyse (EDA)**

        2.1  Deskriptive Statistik: Berechnung von Mittelwert, Median, Standardabweichung etc.
  
        2.2  Datenvisualisierung: Erstellen von Diagrammen zur Verteilung und Trends der Verkaufszahlen.
  
        2.3  Korrelationsanalyse: Untersuchung der Beziehungen zwischen verschiedenen Variablen.

**3. Feature Engineering**

         3.1 Erstellung von Dummy-Variablen: Umwandlung von kategorischen Variablen in numerische Werte (One-Hot-Encoding).
  
         3.2 Hinzufügen externer Regressoren: Berücksichtigung von Feiertagen, Produzenten, Ländern und Regionen als erklärende Variablen.
  
         3.3 Erstellung zeitbasierter Features: Z. B. Wochentag, Monat, Quartal, Feiertage oder saisonale Effekte.

**4. Modellierung mit Facebook Prophet**
   
       4.1 Modellerstellung: Definition des Prophet-Modells mit saisonalen Komponenten und Regressoren.
   
       4.2 Hyperparameter-Tuning mit Optuna: Optimierung von changepoint_prior_scale und seasonality_prior_scale zur Verbesserung der Vorhersagegenauigkeit. 
  
       4.3 Train-Test-Split: Aufteilung der Daten für Modelltraining und Evaluierung.
  

**5. Modellbewertung**
   
       5.1 Cross-Validation (Zeitreihen-Validierung): Evaluierung des Modells mit zeitbasierten Splits.
   
       5.2 Fehlermetriken berechnen: MAPE, MAE und RMSE zur Beurteilung der Modellleistung.
  
       5.3 Ergebnisse visualisieren: Vergleich der Vorhersagen mit den tatsächlichen Verkaufswerten.

**6. Erkenntnisse & Optimierung**
   
       6.1 Analyse der Ergebnisse: Identifikation von Verbesserungspotenzialen.
    
       6.2 Modellanpassungen: Feinabstimmung der Hyperparameter und Feature-Engineering zur Optimierung.
 
       6.3 Dokumentation & Fazit: Zusammenfassung der wichtigsten Erkenntnisse und zukünftige Optimierungsmöglichkeiten.


<br>



### Analysis 

Basierend auf den Prognoseergebnissen und der Modellbewertung lassen sich gezielte Maßnahmen zur Optimierung der Bestandsverwaltung und Verkaufsstrategie ableiten. Die Analyse beantwortet zentrale.


**1. Welche Produkte sind die Bestseller, und welchen Beitrag leisten sie zum Geschäftserfolg?**
   
       + Identifikation der umsatzstärksten Produkte zur gezielten Sortimentssteuerung.
       + Fokus auf die Optimierung der Bestände dieser Artikel, um Nachfragespitzen abzudecken.
  
**2. Wie kann die Bestandsverwaltung verbessert werden?**
   
       + Anpassung der Bestellmengen basierend auf den Verkaufsprognosen, um Überbestände und Engpässe zu vermeiden.
       + Implementierung datengetriebener Lagerstrategien für eine effizientere Kapitalbindung.

**3. Wie rentabel sind einzelne Bestellungen?**
   
       + Analyse der Rentabilität pro Bestellung unter Berücksichtigung von durchschnittlichen Versandkosten und Warenkorbwerten.
       + Optimierung von Rabatt- und Lieferstrategien zur Steigerung der Gewinnmargen.
     
**4. Welchen Einfluss haben verschiedene Monate und Jahreszeiten auf den Umsatz?**
   
       + Identifikation saisonaler Nachfragemuster zur besseren Planung von Marketing- und Verkaufsstrategien.
       + Erhöhung des Lagerbestands in Hochsaison-Phasen, um Nachfragespitzen abzudecken.
     
**5. Welche Artikel haben eine längere Verkaufsdauer?**
    
       + Ermittlung von Produkten mit niedriger Umschlagshäufigkeit, um gezielte Verkaufsförderungen oder Sortimentsanpassungen vorzunehmen.
       + Reduzierung von Ladenhütern durch gezielte Preisstrategien oder Marketingmaßnahmen.
      
**6. Wie entwickelt sich die aktuelle Nachfrage im Vergleich zu früheren Perioden?**
    
        + Vergleich der aktuellen Verkaufszahlen mit historischen Daten zur Identifikation von Wachstumstrends oder Rückgängen.
        + Nutzung dieser Erkenntnisse zur langfristigen Strategieplanung und Angebotsoptimierung.
        
<br>
Diese datenbasierten Erkenntnisse ermöglichen eine präzisere Steuerung des Geschäfts, minimieren Risiken und maximieren die Rentabilität durch eine optimierte Bestandsplanung.
 

<br>
<br>

Background in Python, Machine Learning and Mathematical Optimisation.
<br>
<br>



### Insight


### Projetos:
Veja os tutoriais publicados do Sigmoidal:

* **Visualisierung von Daten aus der Fußball-Bundesliga 2011-2012:** http://bit.ly/3Smgnsn
* **Como Implementar Regressão Linear com Python:** https://bit.ly/2Li5pzY
* **Data Science: Investigando o naufrágio do Titanic:** https://bit.ly/2Ubr5SH
* **Como Tratar Dados Ausentes com Pandas:** https://bit.ly/31KWSMN
* **XGBoost: aprenda este algoritmo de Machine Learning em Python:** https://bit.ly/2UbRhws
* **Como criar uma Wordcloud em Python:** https://bit.ly/2OxsphM
