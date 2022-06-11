# Sales Prediction Rossmann Project

<img src="https://github.com/BarbosaDS/Prediction-Sales-project/blob/main/rossmann.jpg" width=80% height=80%/>


Projeto de previsão de vendas da rede farmacêutica Rossmann.


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

## 3. Planejamento da Solução

### 3.1 Produto final

Esse projeto tem como objetivo entregar:
 
 - Um bot no telegram. O qual retorna o faturamento em reais das próximas 6 semanas ao botar o código da loja.
 - Entregar os melhores insights baseado na análise do comportamento dos dados.

### 3.2 Ferramentas

Quais ferramentas serão usadas no processo?

 - Python 3.10.5;
 - Jupyter Notebook;
 - Git e Github
 - Heroku Cloud
 - Algoritmos de Classificação e Regressão
 - Pacotes de Machine Learning Sklearn e Scipy;
 - Técnicas de Seleção de Atributos e Redução de Dimensionalidade
 - Flask e Python API's

### 3.3 Estratégia da Solução

Como cientista de dados, acredito na metodologia CRISP-DS para a resolução de projetos e rápida entrega de valores. Meu projeto seguiu as seguintes etapas baseadas nesta metodologia:

#### 3.3.1. Entendimento do negócio.

Antes de tudo, fui entender o problema do negócio. Ler sobre e decidir se a previsão de vendas realmente era a melhor forma de resolução. Decidi que era e resolvi seguir para a próxima etapa

#### 3.3.2. Descrição dos dados

Esta etapa, consiste em estudar os dados disponiblizados e fazer as devidas limpezas prévias:

 - Estudar as dimensões dos dados
 - Converter tipos, principalemnte datas e números.
 - Checar a quantidade de variáveis categoricas e númericas temos.
 - Checar e tratar NA's

#### 3.3.3.Filtragem de variáveis

Filtrar as variáveis, afim de deixar apenas aquelas que fazem sentido trabalhar par ao nosso objetivo.

#### 3.3.4. Feature Engineering

Criação junto ao time de negócio, hipóteses para válidar e gerar insights de negócio. Além de criar variáveis que imapctam no fenômeno das vendas.

#### 3.3.5. Analise exploratória de Dados

Através das variáveis criadas junto das hipóteses. Realizar a análise bivariada e multivariada afim de validar as premissas e começar a entender quais variáveis tem mais relação com a variável resposta: Sales(vendas)

#### 3.3.6. Preparação dos dados

Nessa etapa fizemos a  reescala dos dados (MinMaxScaler e RobustScaler), e a transformação de dados categóricos através de encoding.

#### 3.3.7. Seleção de variáveis

Uma das mais importantes etapas. Fizemos a separação dos dados em treino e teste e selecionamos o Boruta como ferramenta de seleção de atributos relevantes para o modelo.

#### 3.3.8. Modelos de Machine Learning

Aqui, treinamos 5 modelos : Average Model; Linear Regression Model; Lasso; Random Forest; XGBoost. E calculamos seu erro MAE, MAPE e RMSE com a tecnica de cross validation. Segue os resultados abaixo

<img src= "https://github.com/BarbosaDS/Prediction-Sales-project/blob/main/IMAGES/error-print.png">

#### 3.3.9 Hiperparameter fine tunning

Essa etapa consiste em encontrar melhores parametros para o modelo, afim de melhorar seu erro. 

Utilizei o método de Random Search, que define seus valores aleatoriamente. Após alguns dias usando esse método para todos os modelos, o que encontrei um RMSE menor foi o XGBoost, conforfme imagem abaixo:

<img src= "https://github.com/BarbosaDS/Prediction-Sales-project/blob/main/IMAGES/xgboost.png">

#### 3.3.10. Avaliação do Modelo e deploy.

Na ultima etapa do projeto, verifico se o resultado do modelo já entrega um valor significativo para o time de negócio, ou preciso passar por outro ciclo de melhorias.

Após a análise de performance der positiva, eu fiz o deploy do modelo no heroku e criei um robô no Telegram que acesse a previsão em tempo real, de qualquer lugar.

## 4. Top 3 Insights dos dados

Na etapa de análise exploratória de dados, gerei alguns insights para apresentar ao time de negócio.

Insights são informações que adquirimos através da análise exploratória dos dados. Que podem ser classificados como apenas uma curiosidade ou que contrapõe cren

#### 4.1. Lojas com competidores mais próximos vendem mais"

<img src= "https://github.com/BarbosaDS/Prediction-Sales-project/blob/main/IMAGES/1.png">

O time de negócios acreditava que vendiam menos, por gerar uma concorrencia muito próxima. Mas através da análise consideramos essa hipotése falsas e vimos que a concentração de maiores vendas por loja está onde se tem mais lojas próximas.


#### 4.2. Lojas com promoções ativas a mais tempo vendem menos.

<img src= "https://github.com/BarbosaDS/Prediction-Sales-project/blob/main/IMAGES/2.png">

Com essa afirmativa, vemos que o comportamento dos clientes faz não valer a pena manter promoções por muito tempo. A Loja teria um lucro maior se encerrasse a promoção depois de um determinado tempo e retomasse ao preço normal.


#### 4.3. Lojas vendem menos no segundo semestre do ano.

<img src= "https://github.com/BarbosaDS/Prediction-Sales-project/blob/main/IMAGES/3.png">

Com esse insight, o time pode considerar esse declínio de faturamento sazonal para compensar com ações de marketing.

## 5. Telegram Bot

Acesse o bot do telegram por aqui.


<img src= "https://github.com/BarbosaDS/Prediction-Sales-project/blob/main/IMAGES/telegram-photo.jpeg" width=70% height=70%/>
