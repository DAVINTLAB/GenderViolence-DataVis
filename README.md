# Explorando Dados Governamentais para Prevenção da Violência de Gênero: Uma Abordagem Visual

Este repositório serve como um guia detalhado sobre como processar e analisar dados governamentais abertos relacionados à violência contra as mulheres. Aqui você encontrará informações sobre o processo de coleta de dados e pré-processamento, permitindo reproduzir nossa pesquisa.


## Preparação de Dados

A preparação dos dados envolveu o uso do Tableau Prep Builder e Python. O Tableau Prep Builder foi usado para processar e organizar diversas etapas de processamento de dados, como limpeza e união de linhas ou colunas de conjuntos de dados em um único arquivo. Python, com bibliotecas como Pandas e NumPy, facilitou a manipulação de dados e métodos estatísticos.

São fornecidas duas formas de tratamento: através do uso do programa Tableau Prep Builder e outra com o uso apenas da linguagem Python - a qual foi realizada posteriormente buscando tornar o processo mais acessível àqueles que não possuíssem uma licença para o uso do programa. 

## Coleta de Dados

Os dados foram coletados do portal de dados abertos do Ministério dos Direitos Humanos e da Cidadania. Inicialmente, 16 arquivos .csv estavam disponíveis a partir de 2014, organizados por ano ou semestre. No entanto, apenas 15 arquivos foram usados neste trabalho, pois o arquivo "Resumo 2019" foi excluído devido ao seu resumo consolidado. Os dados incluíam informações como cidade, estado, horário do relato, identidade do relator, status de risco da vítima, local da violência e dados demográficos como idade, educação, renda e profissão da vítima e suspeito.
- [Ministério dos Direitos Humanos e da Cidadania](https://www.gov.br/mdh/pt-br/acesso-a-informacao/dados-abertos)
- [Central de Atendimento à Mulher (Ligue 180)](https://www.gov.br/mdh/pt-br/acesso-a-informacao/dados-abertos/ligue180)
- [Disque Direitos Humanos (Disque 100)](https://www.gov.br/mdh/pt-br/acesso-a-informacao/dados-abertos/disque100)



## Etapas de Pré-processamento com o Tableau Prep Builder

1. `Filtragem e Conversão`: Dados a partir de 2020 incluíam relatos além da violência doméstica. Um filtro foi aplicado para focar nos dados de violência doméstica, e os arquivos foram convertidos para o formato .xlsx usando o Tableau Prep Builder.

| Arquivos de Entrada               | Arquivos de Saída   |
|-----------------------------------|---------------------|
| ligue180-2014.csv                 | 2014.xlsx           |
| ligue180-2015.csv                 | 2015.xlsx           |
| ligue180-2016.csv                 | 2016.xlsx           |
| ligue180-2017.csv                 | 2017.xlsx           |
| ligue180-2018.csv                 | 2018-1.xlsx         |
| ligue180-nov-2018.csv             | 2018-2.xlsx         |
| ligue180-2019.csv                 | 2019.xlsx           |
| primeiro-semestre-2020.csv        | 2020-1.xlsx         |
| segundo-semestre-2020.csv         | 2020-2.xlsx         |
| primeiro-semestre-2021.csv        | 2021-1.xlsx         |
| segundo-semestre-2021.csv         | 2021-2.xlsx         |
| primeiro-semestre-2022.csv        | 2022-1.xlsx         |
| segundo-semestre-2022.csv         | 2022-2.xlsx         |
| primeiro-semestre-2023.csv        | 2023-1.xlsx         |
| segundo-semestre-2023.csv         | 2023-2.xlsx         |

2. `Remoção de Hashes Repetidos`: Scripts em Python foram usados para remover hashes de relatos repetidos a partir de 2020.

| Arquivos de Entrada   | Arquivos de Saída                 |
|-----------------------|-----------------------------------|
| 2020-1.xlsx           | 2020-1 (hashs filtrados).xlsx     |
| 2020-2.xlsx           | 2020-2 (hashs filtrados).xlsx     |
| 2021-1.xlsx           | 2021-1 (hashs filtrados).xlsx     |
| 2021-2.xlsx           | 2021-2 (hashs filtrados).xlsx     |
| 2022-1.xlsx           | 2022-1 (hashs filtrados).xlsx     |
| 2022-2.xlsx           | 2022-2 (hashs filtrados).xlsx     |
| 2023-1.xlsx           | 2023-1 (hashs filtrados).xlsx     |
| 2023-2.xlsx           | 2023-2 (hashs filtrados).xlsx     |

3. `União e Limpeza de Tabelas`: As tabelas eram anuais até 2019 e, depois, passaram a ser semestrais. Quatro mudanças nos métodos de coleta de dados ocorreram durante o período. Tabelas com o mesmo formato foram unidas e limpas para remover inconsistências ou dados faltantes, gerando quatro conjuntos de dados cobrindo diferentes períodos.

| Arquivos de Entrada               | Arquivos de Saída                 |
|-----------------------------------|-----------------------------------|
| 2014.xlsx                         | 2014 a 2018-1.xlsx                |
| 2015.xlsx                         | -                                 |
| 2016.xlsx                         | -                                 |
| 2017.xlsx                         | -                                 |
| 2018-1.xlsx                       | -                                 |
| 2018-2.xlsx                       | 2018-2 a 2019.xlsx                |
| 2019.xlsx                         | -                                 |
| 2020-1 (hashs filtrados).xlsx     | 2020-1.xlsx                       |
| 2020-2 (hashs filtrados).xlsx     | 2020-2 a 2023.xlsx                |
| 2021-1 (hashs filtrados).xlsx     | -                                 |
| 2021-2 (hashs filtrados).xlsx     | -                                 |
| 2022-1 (hashs filtrados).xlsx     | -                                 |
| 2022-2 (hashs filtrados).xlsx     | -                                 |
| 2023-1 (hashs filtrados).xlsx     | -                                 |
| 2023-2 (hashs filtrados).xlsx     | -                                 | 

4. `Padronização de Profissões e Locais`: Scripts em Python padronizaram nomes de municípios e agruparam profissões em seis categorias, equivalentes às categorias usadas em dados do ENEM.

| Arquivos de Entrada               | Arquivos de Saída                 |
|-----------------------------------|-----------------------------------|
| 2020-2 a 2023.xlsx                | 2020-2 a 2023 (padronizado).xlsx  |

5. `Combinação de Tabelas de Formatos Diferentes`: Os quatro conjuntos de dados foram combinados para criar um conjunto abrangente de 2014 a 2023, embora algumas colunas tenham perdido consistência, especialmente em relação aos níveis de educação.

| Arquivos de Entrada               | Arquivos de Saída                 |
|-----------------------------------|-----------------------------------|
| 2014 a 2018-1.xlsx                | 2014 a 2023.xlsx                  |
| 2018-2 a 2019.xlsx                | -                                 |
| 2020-1.xlsx                       | -                                 |
| 2020-2 a 2023.xlsx                | -                                 |

> Essas etapas de pré-processamento permitiram a criação de conjuntos de dados abrangentes e limpos para análise e visualização.

## Referência

Referencie este trabalho citando o artigo indicado abaixo.

PATRICIO, Eduarda; ZURAWSKI, Gabriel; ROLLWAGEN, André; MANSSOUR, Isabel. Explorando Dados Governamentais para Prevenção da Violência de Gênero: Uma Abordagem Visual.  In Anais do XII Workshop de Computação Aplicada em Governo Eletrônico (WCGE), julho 21, 2024, Brasília/DF, Brasil. SBC, Porto Alegre, Brasil, p. 145-156. ISSN 2763-8723. DOI: https://doi.org/10.5753/wcge.2024.2966.

## Autores

Somos membros do Laboratório de Visualização e Interação de Dados (DaVInt) na PUCRS:
- Isabel H. Manssour - Coordenador
- Eduarda dos Santos Patricio - Integrante
- Gabriel Zurawski de Souza - Integrante

Mais informações podem ser encontradas [aqui](https://www.inf.pucrs.br/davint/).

