# Previsao-de-renda
 


https://github.com/user-attachments/assets/54b1856e-97e7-4699-82d4-3fce1925158e

# Projeto #02 | Previsão de Renda

Este projeto utiliza técnicas de machine learning para prever a renda de novos clientes com base em variáveis disponíveis em uma instituição financeira. O objetivo é facilitar a tomada de decisões, como a concessão de crédito, sem a necessidade de comprovações documentais por parte dos clientes.

## Sumário

- [Entendimento do Negócio](#entendimento-do-negócio)
- [Entendimento dos Dados](#entendimento-dos-dados)
  - [Dicionário de Dados](#dicionário-de-dados)
  - [Análise Univariada](#análise-univariada)
  - [Análise Bivariada](#análise-bivariada)
- [Preparação dos Dados](#preparação-dos-dados)
- [Modelagem](#modelagem)
- [Avaliação](#avaliação)
- [Implantação](#implantação)
- [Como Executar](#como-executar)
- [Requisitos](#requisitos)

## Entendimento do Negócio

A instituição deseja prever a renda de seus clientes para melhorar decisões financeiras, como o limite de crédito oferecido. A ideia é construir um modelo preditivo que utilize variáveis como idade, posse de veículo, entre outras.

## Entendimento dos Dados

### Dicionário de Dados

| Variável              | Descrição                                                                                                  | Tipo             |
|-----------------------|------------------------------------------------------------------------------------------------------------|------------------|
| data_ref              | Data de referência da coleta                                                                                | object           |
| id_cliente            | Identificador exclusivo do cliente                                                                          | int              |
| sexo                  | Sexo do cliente (M/F)                                                                                      | object (binária) |
| posse_de_veiculo      | Indica se o cliente possui veículo (True/False)                                                             | bool (binária)   |
| posse_de_imovel       | Indica se o cliente possui imóvel (True/False)                                                              | bool (binária)   |
| qtd_filhos            | Quantidade de filhos                                                                                        | int              |
| tipo_renda            | Tipo de renda do cliente (Empresário, Assalariado, etc.)                                                    | object           |
| educacao              | Grau de instrução do cliente                                                                                | object           |
| estado_civil          | Estado civil do cliente                                                                                     | object           |
| tipo_residencia       | Tipo de residência do cliente                                                                               | object           |
| idade                 | Idade do cliente em anos                                                                                    | int              |
| tempo_emprego         | Tempo no emprego atual                                                                                      | float            |
| qt_pessoas_residencia | Quantidade de pessoas que moram na residência                                                               | float            |
| **renda**             | Valor da renda do cliente (variável alvo)                                                                   | float            |

### Análise Univariada

Foram realizadas análises estatísticas descritivas para entender melhor o comportamento das variáveis. Um relatório interativo gerado pelo **Pandas Profiling** ajuda a visualizar as distribuições.

### Análise Bivariada

Foi utilizada uma matriz de correlação para identificar relações entre as variáveis e a renda, além de gráficos de dispersão e linha de tendência para investigar os padrões de dados.

## Preparação dos Dados

Os dados foram pré-processados, removendo valores ausentes e transformando variáveis categóricas em numéricas através de codificação *one-hot*. Isso permitiu que o modelo pudesse trabalhar com as variáveis de forma eficiente.

## Modelagem

A modelagem foi feita utilizando a árvore de decisão **DecisionTreeRegressor**, explorando hiperparâmetros como a profundidade máxima e o número mínimo de amostras por folha. O melhor modelo foi treinado com profundidade máxima de 8 e um mínimo de 4 amostras por folha.

### Visualização da Árvore

A árvore de decisão foi visualizada graficamente e impressa, permitindo interpretar os caminhos de decisão para a previsão de renda.

## Avaliação

O desempenho do modelo foi avaliado através do coeficiente de determinação (R²), tanto na base de treino quanto na base de teste. A performance obtida foi:

- **R² (Treino):** 0,89
- **R² (Teste):** 0,57

Esses resultados indicam que o modelo se ajusta bem aos dados de treino, mas tem um desempenho moderado na previsão de novos dados.

## Implantação

O modelo foi implantado utilizando **Streamlit** para criar uma interface web interativa onde o usuário pode simular a previsão de renda. A aplicação está disponível neste [link](https://bruno-projeto02-previsao-renda-ebac.streamlit.app).

## Requisitos

- Python 3.7 ou superior
- Streamlit
- Pandas
- Scikit-learn
- Seaborn
- Matplotlib
- ydata-profiling

