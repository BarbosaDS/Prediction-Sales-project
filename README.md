# Sales Prediction Rossmann Project
Projeto de previsão de vendas da rede farmacêutica Rossmann

A Rossmann é uma das maiores cadeias de drogarias da Europa. Eles disponibilizaram dados de venda de sua rede para o site Kaggle, para uma competição de ciência de dados. 

Os dados contém cerca de 1.1017.209 registros de venda.

## 1.Problemas de Negócio

### 1.1 Problema

O CFO da empresa solicitou aos gerentes de cada loja a previsão de vendas (faturamento) das próximas 6 semanas. O objetivo disso é fazer um planejamento de quanto cada loja pode contribuir para uma reforma e padronização da rede.

Para mais acertividade na previsão, os gerentes me contataram, um cientista de dados. para fazer essa previsão usando dados da empresa e algoritimos de machine learning.

### 1.2 Objetivo

As quatro preocupações básicas do cientista de dados são disputa de dados, engenharia de recursos, modelagem e relatórios de resultados. O Objetivo desse projeto está em treinar um algoritimo de machine learning baseado nos dados disponibilizados, afim de prever o futuro com a menor taxa de erro possível. 

Dessa forma, a empresa poderá melhorar sua gestão financeira e aumentar o seu faturamento com estratégias feitas a partir do conhecimento do comportamento de seus dados.

## 2. Dados utilizados:

* O Dataset foi obtido no [Kaggle](https://www.kaggle.com/competitions/rossmann-store-sales)
* Importante se situar sobre as varíaveis originais do dataset.

Suas variáveis são: 

Variável | Definição
------------ | -------------
|store | id único de cada loja..|
|day_of_week	 | indica o dia da semana que era aquele dia (assumindo 1-Sun -> 7-Sat).|
|date | Data do registro.|
|sales | faturamento da loja naquele dia.|
|customers | número de clientes na loja naquele dia.|
|open | loja aberta ou fechada: (0 = closed, 1 = open).|
|state_holiday	 | feriado nacional (a = public holiday, b = Easter holiday, c = Christmas, 0 = Dia Comum).|
|school_holiday | indica se a loja naquele dia foi afetada pelo fechamento das escolas públicas.|
|store_type | indica qual dos 4 modelos distintos é esta loja: (a, b, c, d).|
|assortment | indica o nível de sortimento da loja: (a = basic, b = extra, c = extended).|
|competition_distance | indica a distancia em metros do competidor mais próximo.|
|competition_open_since_month	 | indica mês aproximado da abertura do competidor mais próximo.|
|competition_open_since_year | indica ano aproximado da abertura do competidor mais próximo.|
|promo | indica se a loja está com uma promoção ativa naquele dia.|
|promo2 | é uma promoção contínua e consecutiva: (0 = store not participating, 1 = store participating).|
|promo2_since_week | indica a semana do calendário onde a loja entrou em Promo2.|
|promo2_since_year | indica o ano onde a loja entrou em Promo2.|
|promo_interval | indica os meses de início anual onde Promo2 é iniciada (ex: "Feb,May,Aug,Nov").|

As variáveis criadas durante do desenvolvimento do projeto são: 

Variável | Definição
------------ | -------------
|year | Ano da data que ocorreu a venda.|
|month	 | Mês da data que ocorreu a venda.|
|day | Dia da data que ocorreu a venda.|
|week_of_year | Semana do ano que ocorreu a venda, considerando a primeira semana do ano como 1.|
|year_week' | Semana do ano que ocorreu a venda, considerando a primeira semana começando do 0.(object type, %Y-%W)|
|competition_since | Concatenação da competition_open_since_year e competition_open_since_month,indica a data exata em mês e ano que existem competidores.|
|promo2_since | data desde que a Promo2 está ativa.|
|promo2_time_week | números de semanas em que a Promo2 ficou ativa.|

## 3. Planejamento da Solução:














Esse projeto tem como objetivo entregar:
 
 - Um bot no telegram. O qual retorna o faturamento em reais das próximas 6 semanas ao botar o código da loja.
 - Entregar os melhores insights baseado na análise do comportamento dos dados.
