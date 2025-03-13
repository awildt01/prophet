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
* [Notebook](https://colab.research.google.com/drive/1KNwTnRGif0esIZ8zrPeZRG1BvyP9YbuM?usp=sharing)
* [Medium](https://medium.com/@alexandrewildtgraziani/previs%C3%A3o-de-demanda-utilizando-s%C3%A9ries-temporais-8d3efc0cd388)
* [Blog](https://sigmoidal.ai)

### Obtenção dos Dados
Todos os dados utilizados aqui foram fornecidos por [Rafael Duarte](https://www.linkedin.com/in/rafael-n-duarte/?source=user_about----------------------95e660a7ce9---------------) e pela Sigmoidal..

Os dados estão divididos em dois arquivos: um contém os dados históricos de vendas, e o outro contém informações sobre os vinhos. Ambos os arquivos foram armazenados na nuvem::

- products.csv

      - country: país de origem do vinho

      - item_id: número de identificação do item

      - kind: tipo do vinho: sparkling: espumante, rose sparkling: espumante rosé, white: branco, rosé: rosé, red: tinto

      - name: nome do vinho

      - price_brl: preço em reais

      -  price_usd: preço em dólar americano

      - producer: nome do produtor do vinho

      - region: região de produção do vinho

       - vintage: ano da safra

- sales.csv – Este conjunto de dados originalmente abrangia 5 anos de vendas diárias, distribuídas em 10 lojas, com um catálogo de 50 produtos. No entanto, foi modificado e agora abrange 3 anos de vendas diárias, distribuídas em 3 lojas com 219 produtos diferentes em estoque.


<br>

## Objetivo
A empresa está desenvolvendo uma solução baseada em IA para otimizar a gestão de estoques em lojas de vinhos. No centro dessa solução está um modelo de machine learning que prevê com precisão a demanda futura com base em dados históricos de vendas.

O foco está em refinar ainda mais a metodologia de previsão para atender aos desafios específicos do mercado de vinhos. Isso inclui fatores como variações de safra, demanda sazonal, disponibilidade limitada e valorização de vinhos individuais.

<br>

### Estrutura do Projeto


O objetivo do projeto é realizar uma análise exploratória de dados (EDA). Vamos obter os primeiros insights dos dados, identificar padrões e formular hipóteses. Os seguintes passos serão realizados na análise:

**1. Preparação dos Dados**

    1.1 Importação dos Dados: Carregar os dados de vendas a partir de arquivos CSV ou de uma base de dados.

    1.2 Primeira Análise dos Dados: Visão geral das colunas, tipos de dados e primeira inspeção visual.

    1.3 Limpeza dos Dados: Tratamento de valores ausentes, remoção de duplicatas e identificação de outliers.

**2. Análise Exploratória de Dados (EDA)**

     2.1 Estatística Descritiva: Cálculo de média, mediana, desvio padrão, etc.

    2.2 Visualização de Dados: Criação de gráficos para distribuição e tendências dos números de vendas.

    2.3 Análise de Correlação: Investigação das relações entre diferentes variáveis.

**3. Feature Engineering**

    3.1 Criação de Variáveis Dummy: Transformação de variáveis categóricas em valores numéricos (One-Hot-Encoding).

    3.2 Adição de Regressores Externos: Consideração de feriados, produtores, países e regiões como variáveis explicativas.

    3.3 Criação de Features Baseadas no Tempo: Por exemplo, dia da semana, mês, trimestre, feriados ou efeitos sazonais.

**4. Modelagem com Facebook Prophet**
   
    4.1 Criação do Modelo: Definição do modelo Prophet com componentes sazonais e regressores.

    4.2 Ajuste de Hiperparâmetros com Optuna: Otimização de changepoint_prior_scale e seasonality_prior_scale para melhorar a precisão das previsões.

    4.3 Divisão Train-Test: Separação dos dados para treinamento e avaliação do modelo.
  

**5. Avaliação do Modelo**
   
     5.1 Validação Cruzada (Validação de Séries Temporais): Avaliação do modelo com divisões baseadas no tempo.

    5.2 Cálculo de Métricas de Erro: MAPE, MAE e RMSE para avaliar o desempenho do modelo.

    5.3 Visualização dos Resultados: Comparação das previsões com os valores reais de vendas.

**6. Conclusões e Otimização**
   
    6.1 Análise dos Resultados: Identificação de potenciais melhorias.

    6.2 Ajustes no Modelo: Ajuste fino dos hiperparâmetros e engenharia de features para otimização.

    6.3 Documentação e Conclusão: Resumo das principais descobertas e possibilidades futuras de otimização.


<br>


### Análise
Com base nos resultados das previsões e na avaliação do modelo, é possível derivar medidas específicas para otimizar a gestão de estoques e a estratégia de vendas. A análise responde a questões centrais e fornece insights valiosos que podem contribuir para a melhoria dos processos operacionais. Aqui estão alguns dos aspectos mais importantes que emergem da análise:


**1. Quais produtos são os mais vendidos e qual é a sua contribuição para o sucesso do negócio?**
   
        + Identificação dos produtos que geram maior receita para uma gestão direcionada do sortimento.
        + Foco na otimização dos estoques desses itens para cobrir picos de demanda.
   
**2. Como a gestão de estoque pode ser melhorada?**

        + Ajuste das quantidades de pedidos com base nas previsões de vendas para evitar excessos e faltas de estoque.
        + Implementação de estratégias de armazenamento baseadas em dados para uma alocação de capital mais eficiente.
**3. Quão rentáveis são os pedidos individuais?**


       + Análise da rentabilidade por pedido, considerando custos médios de envio e valores do carrinho de compras.
       + Otimização de estratégias de descontos e entrega para aumentar as margens de lucro.
**4. Qual é o impacto de diferentes meses e estações do ano nas vendas?**


       + Identificação de padrões sazonais de demanda para um melhor planejamento de estratégias de marketing e vendas.
       + Aumento dos estoques durante períodos de alta temporada para cobrir picos de demanda.
**5. Quais itens têm um ciclo de venda mais longo?**


       + Identificação de produtos com baixa rotatividade para implementar promoções direcionadas ou ajustes no sortimento.
       + Redução de itens encalhados por meio de estratégias de preços ou ações de marketing direcionadas.
**6. Como a demanda atual se compara a períodos anteriores?**

       + Comparação dos números de vendas atuais com dados históricos para identificar tendências de crescimento ou declínio.
       + Uso desses insights para planejamento de estratégias de longo prazo e otimização da oferta.
        
<br>
Esses insights baseados em dados permitem uma gestão mais precisa do negócio, minimizam riscos e maximizam a rentabilidade por meio de um planejamento de estoque otimizado.
 

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
