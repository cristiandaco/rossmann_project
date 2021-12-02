# Projeto Rossmann

## Contexto do problema de negócio

" A Rossmann é uma rede de farmácias com mais de 3000 lojas em 7 países da Europa. O CFO da Rossmann fez uma reunião com todos os Gerentes de Loja e pediu para que cada um deles trouxesse uma previsão diária das próximas 6 semanas de vendas. Depois dessa reunião os gerentes de loja entraram em contato com time de Data Science e requisitaram uma previsão de vendas de suas lojas. "


![rossmann_image](https://user-images.githubusercontent.com/81040797/142878319-7fe521ec-5b81-4eb5-96fe-e00e0bb471a0.jpg)

## Estrutura do projeto:

1. Descrição dos dados;
2. Feature engeneering;
3. Filtragem de variáveis;
4. Análise exploratória de dados ( geração de insights );
5. Preparação dos dados;
6. Seleção de variáveis;
7. Implementação de algoritmos de Machine Learning;
8. Hiperparameter fine tunning;
9. Interpretação e tradução do erro do modelo;
10. Deploy do modelo em produção.
## Premissas assumidas

- As vendas das lojas são influenciadas por vários fatores, incluindo competição, promoções, feriados escolares e estaduais, sazonalidade e localidade.
- Com milhares de requisições de Gerentes de Lojas basedas nas suas próprias circunstâncias, a acurácia do resultado pode ser variada para cada uma das lojas.

## Hipóteses ( geração de insights )

H1) Lojas com maior sortimento de produtos deveriam vender mais.
**FALSA. Lojas com maior sortimento vendem MENOS.**

H2) Lojas com competidores mais próximos deveriam vender menos.
**FALSA. Quanto maior a distancia dos competidores MENOR a venda.**

H3) Lojas com competidores a mais tempo deveriam vender mais.
**Falsa. Lojas com competidores a mais tempo vendem MENOS.**

H4) Lojas com promoções ativas por mais tempo deveriam vender mais.
**FALSA. Lojas com promoção ativa por mais tempo vendem MENOS, depois de um determinado período.**

H6) Lojas com mais promoções consecutivas deveriam vender mais.
**FALSA. Lojas com mais promoções consecutivas vendem MENOS.**

H7) Lojas abertas durante o feriado de Natal deveriam vender mais.
**VERDADEIRO. Lojas abertas durante o feriado de Natal vendem mais, em média.**

H8) Lojas deveriam vender mais ao longo dos anos.
**FALSA Lojas Vendem MENOS ao longo dos anos**

H9) Lojas deveriam vender mais durante o segundo semestre do ano.
**VERDADEIRO. Lojas vendem, em média, 4,62% a mais no segundo semestre.**

H10) Lojas deveriam vender mais antes do dia 10 de cada mês.
**VERDADEIRO. Em média, lojas vendem 7,08% a mais antes do 10 dia de cada mês.**

H11) Lojas deveriam vender menos durante os finais de semana.
**VERDADEIRO. Lojas vendem, em média, MENOS durante os finais de semana.**

H12) Lojas deveriam vender menos nos feriados escolares
**VERDADEIRO. Lojas vendem menos nos feriados escolares, exceto no mes de Agosto.**

## Machine Learning Performance:
![image](https://user-images.githubusercontent.com/81040797/144332294-f8fa0593-78ca-478f-8af5-0980ae372c33.png)

## Cross Validation

![image](https://user-images.githubusercontent.com/81040797/144333214-6e86dc79-af00-4868-a015-3febba0758ef.png)

Apesar do modelo Random Forest apresentar resultados ligeiramente melhores do que o os resultados obtidos com XGBoost, o modelo escolhido para ir para produção foi o modelo desenvolvido com base no XGBoost. Pareceu mais razoável utilizar um modelo mais simples, como o XGBoost, com exigçência computacional mais baixa em comparação ao Random Forest, 
mas que entrega resultados muito próximos dos resultados do modelo mais complexo.

Desempenho do modelo, graficamente:

![error_prev](https://user-images.githubusercontent.com/81040797/142909769-b8528c11-55df-4d54-a8dd-d05b636a6d65.png)

## Resultados financeiros
- Qual é a previsão de vendas das lojas da Rossmann?
- ![image](https://user-images.githubusercontent.com/81040797/144333472-a87ef74a-e5ef-49ca-880b-e56f3f920fad.png)

O resultado para as 1115 lojas da Rossmann que solicitaram a previsão de vendas, é que cada uma delas, em média, venda U$ 255.353,23 nas próximas 6 semanas. Valor que varia de U$ 95.360,91 a U$ 836.160,87 da loja que deve ter menor receita para loja que deve ter maior receita. O erro do modelo ficou em 13,3%, ou seja, na média o modelo erra a previsão 13,3% para cima ou para baixo do valor real. Abaixo gráfico com o desempenho do modelo: valor real de vendas em comparação com a previsão.

Expectativa de receita:

![image](https://user-images.githubusercontent.com/81040797/144333514-b31db814-8f2d-454b-9dad-e519c3c86cfa.png)

## Conlusão
- O objetivo foi alcançado? Sim? Não? Por que?

Sim. Baseado na metodologia de desenvolvimento de projetos CRISP-DS, que prevê ciclos de iteração para otimização dos projetos, após a solicitação do CFO da Rossmann, foi possível entregar o primeiro ciclo de desenvolvimento com bons resultados.

## Próximos passos
- O que pode ser melhorado?

Durante o primeiro ciclo de iterações já foi possível observar razoáveis pontos de melhoria dos resultados. Na seção 7.0., que aborda os modelos de machine learning, como a variável resposta não é linear, é possícel ao utilizar, nos próximos ciclos, algoritmos de ML mais complexos, como SVM e Redes Neurais, obter erro menor do que o erro entregue pelo algoritmo XGBoost. Na subseção 8.1., da seção 8.0. onde é abordado o ajuste fino dos parâmetros, com a utilização da otimização bayseana, que exige maior capaciadade computacional, mas que seleciona os parâmetros até que os melhores sejam encontrados, também é possível obter erro menor do que o obtido com utilização do método Random Search. Por fim, uma das premissas assumidas diz que "Com milhares de requisições de Gerentes de Lojas basedas nas suas próprias circunstâncias, a acurácia do resultado pode ser variada para cada uma das lojas". Com essa premissa assumida, é razóvel que ao analizar aquelas lojas que obtiveram erro maior, de forma indivídual, se obtenha resultados de negócio mais vantajosos do que analisá-las em conjunto com as demais.


|
Cristian Oliveira

|
cris.oliveira.95@hotmail.com
