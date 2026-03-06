# Análise de Perfil Comportamental e Feature Engineering com SQL
Este projeto visa utilizar SQL para transformar os dados brutos, retirados do Kaggle, em uma tabela de perfil comportamental dos clientes. O objetivo é criar features que descrevam o engajamento e a preferência de consumo dos usuários em diferentes períodos de tempo (últimos 2 meses, último mês, últimos 28, 14 e 7 dias)

## Técnicas usadas:
CTEs: organização de consultas complexas em etapas modulares e legíveis. 

Window Functions (row_number): utilizada para identificar o produto mais resgatado por cada cliente nos diferentes períodos analisados. 

Agregações Condicionais: uso do CASE WHEN para calcular saldos de pontos positivos e negativos simultaneamente. 

Manipulação de Datas: funções de datas (julianday, strftime) para cálculo de transações recentes nos períodos específicados, juntamente do período do dia e dia da semana com mais transações, para identificar padrões de comportamento.

## Principais Features criadas: 
Engajamento Por Período de Tempo; Preferência de Produtos; Comportamento de Horário.

## Dicionário:
Abaixo estão descritas as principais features geradas pelo script na tabela:

| Coluna | Descrição | Observações |
| :--- | :--- | :--- |
| qtdeTransacoesVida | Total de transações realizadas desde a criação do usuário | 
| qtdeTransacoes*X* | Total de transações realizadas nos últimos X dias |
| diasUltimaInteracao	| Dias desde a última interação do usuário |
| saldoPontos | Quantidade de pontos total atual do usuário |
| qtdePontosPosVida | Quantidade de pontos positivos totais desde a criação do usuário |
| qtdePontosPos*X* | Quantidade de pontos positivos total com base nos últimos X dias |
| qtdePontosNegVida | Quantidade de pontos negativos totais desde a criação do usuário |
| qtdePontosNeg*X* | Quantidade de pontos negativos total com base nos últimos X dias |
| idadeBase | Quanto tempo o usuário existe desde que foi criado |
| produtoVida | Produto mais resgatado desde a criação do usuário |
| produto*X* | Produto mais resgatado nos últimos X dias |
| dtDia | Dia da semana com maior transação | -1 significa que não há um dia |
| periodoMaisTransacao28 | Período do dia em que houve mais transações nos últimos 28 dias |
| engajamento28Vida | % de engajamento nos últimos 28 dias em relação ao total da vida | Indica se o ritmo de uso atual está acima ou abaixo da média do usuário desde sua criação |

## Fonte dos dados:
([kaggle.com/datasets/teocalvo](https://www.kaggle.com/datasets/teocalvo/teomewhy-loyalty-system/versions/1245))
