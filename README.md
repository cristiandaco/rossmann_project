# Projeto Rossmann

## Metodologia
O método CRISP-DS foi o método empregado no desevolvimento do projeto. No que consiste o método CRISP-DS? - Chamado Cross Industry Process - Data Science, o método CRISP-DS é um método cíclico de desenvolvimento, ou seja, ele possui etapas bem definidas que formam um cíclo, isso significa que para desenvolver o projeto o desenvolvedor deve passar várias vezes pelas mesmas tarefas. Vantagens do método CRISP-DS: com um cíclo completo o desenvolverdor consegue entregar uma versão da solução End-to-End com mais velocidade em comparação com o método linear, além do mapeamento de possíveis problemas.

## Estrutura do projeto:

1. Descrição dos dados;
2. Feature engeneering;
3. Filtragem de variáveis;
4. Análise exploratória de dados ( geração de insights );
5. Preparação dos dados;
6. Seleção de variáveis;
7. Implementação de Machine Learning;
8. Hiperparameter fine tunning;
9. Interpretação e tradução do erro do modelo;
10. Deploy do modelo em produção.

## Contexto do problema de negócio

" A Rossmann é uma rede de farmácias com mais de 3000 lojas em 7 países da Europa. O CFO da Rossmann fez uma reunião com todos os Gerentes de Loja e pediu para que cada um deles trouxesse uma previsão diária das próximas 6 semanas de vendas. Depois dessa reunião os gerentes de loja entraram em contato com time de Data Science e requisitaram uma previsão de vendas de suas lojas. "


![rossmann_image](https://user-images.githubusercontent.com/81040797/142878319-7fe521ec-5b81-4eb5-96fe-e00e0bb471a0.jpg)

## Premissas assumidas

- As vendas das lojas são influenciadas por vários fatores, incluindo competição, promoções, feriados escolares e estaduais, sazonalidade e localidade.
- Com milhares de requisições de Gerentes de Lojas basedas nas suas próprias circunstâncias, a acurácia do resultado pode ser variada para cada uma das lojas.

## Hipóteses ( geração de insights )

H1) Lojas com maior sortimento de produtos deveriam vender mais.
**FALSA. Lojas com maior sortimento vendem MENOS**.
