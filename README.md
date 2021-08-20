![question22](/images/Insurance.jpg)

# Insurance All Company

**Aviso:** O seguinte contexto é completamente fictício, a empresa, o contexto, o CEO, as questões de negócios existem apenas na minha imaginação.

A Insurance All é uma empresa que oferece seguro saúde para seus clientes e a equipe de produtos está analisando a possibilidade de oferecer aos segurados um novo produto: o seguro de automóveis.

Tal como acontece com o seguro saúde, os clientes deste novo plano de seguro de automóveis precisam pagar um valor anualmente à Insurance All para obter um valor segurado pela empresa, destinado a custear um eventual sinistro ou dano ao veículo.

A Insurance All conduziu uma pesquisa com cerca de 380.000 clientes sobre seu interesse em ingressar em um novo produto de seguro de automóveis no ano passado. Todos os clientes manifestaram interesse ou não em adquirir seguro de automóveis e essas respostas foram salvas em um banco de dados junto com outros atributos do cliente.

A equipe de produtos selecionou 127 mil novos clientes que não responderam à pesquisa para participar de uma campanha, na qual receberão a oferta do novo produto de seguro de automóveis. A oferta será feita pela equipe de vendas por meio de ligações telefônicas.

Porém, a equipe de vendas tem capacidade para realizar 20 mil ligações no período da campanha.

# Problema de Negócio

Nesse contexto, você foi contratado como consultor de Data Science para construir um modelo que prevê se o cliente estaria ou não interessado em seguro de automóveis.

Com a solução, a equipe de vendas espera poder priorizar as pessoas com maior interesse no novo produto e, assim, otimizar a campanha fazendo apenas contatos com os clientes mais propensos a realizar a compra.

Como resultado de sua consultoria, você precisará entregar um relatório contendo algumas análises e respostas para as seguintes perguntas:

- Principais insights sobre os atributos mais relevantes dos clientes interessados em adquirir seguro de automóveis.
- Que porcentagem de clientes interessados em comprar seguro de automóveis a equipe de vendas poderá atingir com 20.000 ligações?
- E se a capacidade da equipe de vendas aumentar para 40.000 chamadas, que porcentagem de clientes interessados em adquirir seguro de automóveis a equipe de vendas poderá entrar em contato?
- Quantas ligações a equipe de vendas precisa fazer para contatar 80% dos clientes interessados em adquirir seguro de automóveis?

Os Dados do conjunto estão disponível em um banco de dados Postgresql e cada linha representa um cliente e cada coluna contém alguns atributos que descrevem aquele cliente, além de sua resposta à pesquisa, na qual ela mencionou interesse ou não no novo produto de seguro.

# Planejamento da Solução

## Qual é a solução?
É necessário desenvolver um modelo de aprendizado de máquina que classifique os clientes com base em sua probabilidade de aquisição de seguro de veículos.

## Como será a solução?
Este Modelo estará disponível em uma API, podendo ser utilizado pelo cliente a qualquer momento que ele precise.

## Hospedagem
A API será hospedada na plataforma Heroku e está disponível neste url: https://lujanrr-healthinsurance.herokuapp.com.

## Tabela - Método de Entrega

Recebe os atributos referente aos clientes do seguro de saúde e volta os mesmos atributos com uma nova coluna 'Score', que indica a probabilidade do cliente realizar a aquisição do seguro de automóvel.

## Planilha no Google Sheets com botão de Previsão- Método de Entrega

Acesso ao resultado da previsão do modelo direto em uma planilha do Google Sheets, facilitando a utilização pela equipe de ligações, pode ser acessada através
da url: https://docs.google.com/spreadsheets/d/1W7ArDkOMPC2Zz72PY5A5KPqxZZx3_oLL8ZV9AhDhfR0/edit?usp=sharing


# Estratégia da Solução:

**Etapa 01. Descrição dos dados:** Meu objetivo é usar métricas estatísticas para identificar dados fora do escopo do negócio.

**Etapa 02. Feature Engineering:** Derive novos atributos com base nas variáveis originais para descrever melhor o fenômeno que será modelado.

**Passo 03. Filtragem de Dados:** Filtre linhas e selecione colunas que não contenham informações para modelagem ou que não correspondam ao escopo do negócio.

**Etapa 04. Análise exploratória de dados:** Explore os dados para encontrar insights e entender melhor o impacto das variáveis no aprendizado do modelo.

**Etapa 05. Preparação dos dados:** Prepare os dados para que os modelos de aprendizado de máquina possam aprender o comportamento específico.

**Etapa 06. Seleção de recursos:** Seleção dos atributos mais significativos para treinar o modelo.

**Etapa 07. Machine Learning Modelling:** treinamento do modelo de aprendizado de máquina

**Etapa 08. Hyperparameter Fine Tunning:** Escolha os melhores valores para cada um dos parâmetros do modelo selecionado na etapa anterior.

**Etapa 09. Conversão do desempenho do modelo em valores de negócios:** Converta o desempenho do modelo em um resultado de negócios.

**Etapa 10. Deploy Model to Production:** Publique o modelo em um ambiente de nuvem para que outras pessoas ou serviços possam usar os resultados para melhorar a decisão de negócios.

**Etapa 11. Previsão por Google Sheets:** Criação de uma planilha no Google Sheets com um botão de previsão do modelo.

# Top 3 Data Insights

**Hipótese 4** - Clientes que ja sofreram algum acidente tem mais interesse em adquirir seguro de veículos.

**VERDADEIRA**: 98% dos clientes interessados no seguro ja sofreram algum tipo de acidentes.

**Hipótese 1.** - Mulheres tem mais interesse em comprar seguro de veículos que homens.

**FALSA**: Homens tem mais interesse (61,17%) em comprar seguro de veículos do que mulheres (38,83%).

**Hipótese 5.** - Clientes acima de 30 anos são mais interessados em adquirir seguro de veículos.

**VERDADEIRA**: Aproximadamente 87% dos clientes interessados tem mais que 30 anos de idade.

#  Modelos de Machine Learning aplicados
Os Testes foram realizados usando os seguintes algoritmos:

**KNN Classifier**

**Logistic Regression**

**Gaussian Naive Bayes**

**Random Forest**

**Light Gradient Boosting Machine Classifier**

**XGBoost Classifier**

##  Performance dos Modelos

**Real Performance - Cross Validation**

| Model Name |Accuracy Mean | Precision Mean | Precision STD | Recall Mean | Recall STD | Precision@K Mean | Precision@K STD | Recall@K Mean | Recall@K STD |
|------------|--------------|-----------------|--------------|-------------|------------|------------------|-----------------|---------------|--------------|
LGBMClassifier|	0.8876|	0.8704|	0.0023|	0.9107|0.0018|	0.9995|	0.0001|	0.4762|	0.0000|
KNeighborsClassifier|	0.8460|	0.7900|	0.0017|	0.9425|	0.0015|	0.8959|	0.0052|	0.4268|	0.0025|
RandomForestClassifier|	0.8005|	0.7418|	0.0019|	0.9219|	0.0041|	0.8354|	0.0009|	0.3980|	0.0004|
XGBClassifier|	0.7798|	0.7524|	0.0021|	0.8340|	0.0009|	0.8236|	0.0315|	0.3924|	0.0150|
LogisticRegression|	0.7959|	0.7332|	0.0010|	0.9305|	0.0013|	0.7954|	0.0012|	0.3789|	0.0006|
GaussianNB	|0.7899|0.7112|	0.0013|	0.9761|	0.0007|	0.7874|	0.0022|	0.3751|	0.0011|

## Modelo Final
Ao final dos testes realizados o Modelo de **Light Gradient Boosting Machine Classifier** foi selecionado como modelo final, devido a sua alta performance e também
pelo tamanho reduzido (354.847 bytes) quando comparado a outros modelos de árvores que podem facilmente ultrapassar o tamanho de 1Gb (1e+9 bytes)

# Conversão do desempenho do modelo em valores de negócios

## Que porcentagem de clientes interessados em comprar seguro de automóveis a equipe de vendas poderá atingir com 20.000 ligações?
Ao utilizar 32,80% dos dados de validação, o que se traduziria em 20 mil ligações da equipe de vendas, o modelo seria capaz de identificar 81,82% do total de interessados em adquirir o seguro.

![question1](/images/Cumulative_gain@20k.png)

Ao realizar 20 mil ligações, o modelo proposto é cerca de 2,5 vezes melhor do que a escolha aleatória.

![question12](/images/Lift_curve@20k.png)

Considerando o preço de seguro veicular como uma média mensal de R$2000, o resultado em cima da nova base de **127.000** clientes seria de:

Receita Anual com o modelo aleatório: 1.005.840.000

Receita Anual com o modelo proposto: 2.468.880.000

Diferença em R$: 1.463.040.000 

## E se a capacidade da equipe de vendas aumentar para 40.000 chamadas?
Ao utilizar 65,65% dos dados de validação, que seriam traduzidos em 40 mil ligações da equipe de vendas, o modelo seria capaz de identificar 99,91% de pessoas do total de interessadas em adquirir o seguro.

![question21](/images/Cumulative_gain@40k.png)

Ao realizar 40 mil ligações, o modelo proposto é cerca de 1,6 vezes melhor do que a escolha aleatória.

![question22](/images/Lift_curve@40k.png)

Considerando o preço de seguro veicular como uma média mensal de R$2000, o resultado em cima da nova base de **127.000** clientes seria de:

Receita Anual com o modelo aleatório: 1.981.200.000

Receita Anual com o modelo proposto: 3.017.520.000

Diferença em R$: 1.036.320.000

# Quantas ligações a equipe de vendas precisa fazer para contatar 80% dos clientes interessados em adquirir seguro de automóveis?
Para atingir 80% dos clientes interessados seriam necessárias pelo menos 19500 ligações.

![question22](/images/calls_to80.png)
                      
#  Conclusão




#  Próximos Passos


