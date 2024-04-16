# Entrelinhas da Violência: Explorando Visualmente Dados de Violência contra a Mulher

Este repositório serve como um guia detalhado sobre como processar e analisar dados governamentais abertos relacionados à violência contra as mulheres. Aqui você encontrará informações sobre o processo de coleta de dados e pré-processamento, permitindo recriar nossa pesquisa.


## Preparação de Dados

A preparação dos dados envolveu o uso do Tableau Prep Builder e Python. O Tableau Prep Builder foi usado para processar e organizar diversas etapas de processamento de dados, como limpeza e união de linhas ou colunas de conjuntos de dados em um único arquivo. Python, com bibliotecas como Pandas e NumPy, facilitou a manipulação de dados e métodos estatísticos.

## Coleta de Dados

Os dados foram coletados do portal de dados abertos do Ministério dos Direitos Humanos e da Cidadania. Inicialmente, 16 arquivos .csv estavam disponíveis a partir de 2014, organizados por ano ou semestre. No entanto, apenas 15 arquivos foram usados neste trabalho, pois o arquivo "Resumo 2019" foi excluído devido ao seu resumo consolidado. Os dados incluíam informações como cidade, estado, horário do relato, identidade do relator, status de risco da vítima, local da violência e dados demográficos como idade, educação, renda e profissão da vítima e suspeito.
- [Ministério dos Direitos Humanos e da Cidadania](https://www.gov.br/mdh/pt-br/acesso-a-informacao/dados-abertos)
- [Central de Atendimento à Mulher (Ligue 180)](https://www.gov.br/mdh/pt-br/acesso-a-informacao/dados-abertos/ligue180)
- [Disque Direitos Humanos (Disque 100)](https://www.gov.br/mdh/pt-br/acesso-a-informacao/dados-abertos/disque100)



## Etapas de Pré-processamento

1. `Filtragem e Conversão`: Dados a partir de 2020 incluíam relatos além da violência doméstica. Um filtro foi aplicado para focar nos dados de violência doméstica, e os arquivos foram convertidos para o formato .xlsx usando o Tableau Prep Builder.
2. `Remoção de Hashes Repetidos`: Scripts em Python foram usados para remover hashes de relatos repetidos a partir de 2020.
3. `União e Limpeza de Tabelas`: As tabelas eram anuais até 2019 e, depois, passaram a ser semestrais. Quatro mudanças nos métodos de coleta de dados ocorreram durante o período. Tabelas com o mesmo formato foram unidas e limpas para remover inconsistências ou dados faltantes, gerando quatro conjuntos de dados cobrindo diferentes períodos.
4. `Padronização de Profissões e Locais`: Scripts em Python padronizaram nomes de municípios e agruparam profissões em seis categorias com base em dados do ENEM.
5. `Combinação de Tabelas de Formatos Diferentes`: Os quatro conjuntos de dados foram combinados para criar um conjunto abrangente de 2014 a 2023, embora algumas colunas tenham perdido consistência, especialmente em relação aos níveis de educação.

> Essas etapas de pré-processamento permitiram a criação de conjuntos de dados abrangentes e limpos para análise e visualização.

## Autores

Somos membros do Laboratório de Visualização e Interação de Dados (DaVInt) na PUCRS:
- Isabel H. Manssour - Coordenador
- Eduarda dos Santos Patricio - Integrante
- Gabriel Zurawski de Souza - Integrante

More information can be found [here](https://www.inf.pucrs.br/davint/).

