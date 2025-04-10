# 📊 Entrelinhas da Violência

> Visualizando e analisando dados sobre violência contra a mulher no Brasil com foco em reprodutibilidade, acessibilidade e impacto social.

Este projeto explora dados governamentais disponibilizados pelo serviço **Ligue 180** com o objetivo de identificar padrões demográficos, temporais e geográficos da violência contra a mulher no Brasil. A iniciativa alia **ciência de dados**, **visualização interativa** e **transparência metodológica** para apoiar políticas públicas e ampliar o entendimento sobre esse grave problema social.

---

## 🚀 Objetivos

- Desenvolver uma **metodologia reprodutível** para tratamento de dados do Ligue 180.
- Criar **dashboards interativos** que permitam exploração dos dados por pesquisadores, gestores públicos e sociedade civil.
- Aplicar técnicas de **clusterização** para identificar possíveis perfis de vítimas e suspeitos.
- **Disponibilizar publicamente** todas as ferramentas e códigos utilizados.
- Produzir **insights e recomendações** para melhorar a coleta e divulgação de dados governamentais.

---

## 🛠️ Tecnologias e Ferramentas

- **Python** (Pandas, NumPy)
- **Tableau Desktop / Tableau Public**
- Dados do **Ministério dos Direitos Humanos** e **IBGE**

---

## 📥 Coleta de Dados

Os dados foram obtidos a partir das seguintes fontes:

- [Portal de Dados Abertos do Ministério dos Direitos Humanos](https://www.gov.br/mdh/pt-br/acesso-a-informacao/dados-abertos/ligue180)  
  > Contém os dados de denúncias do Ligue 180 entre 2014 e 2023, organizados em arquivos CSV.

- [Censo Demográfico 2022 - IBGE](https://tinyurl.com/y32c879j)  
  > Utilizado para obtenção de dados complementares sobre população, raça e escolaridade por município.

---

## 🧹 Etapas do Pré-processamento

O pré-processamento foi estruturado em três etapas principais para garantir a qualidade e padronização dos dados:

### 🔹 Etapa 1 — Padronização e Limpeza Inicial
- Padronização dos nomes das colunas (com base em um dicionário comum).
- Filtragem dos registros para incluir apenas denúncias de **violência doméstica**.
- Remoção de registros duplicados.
- Conversão de todos os valores para **maiúsculas sem acento**.

### 🔹 Etapa 2 — Consolidação por Período
- Agrupamento dos dados em quatro grandes blocos, conforme mudanças no formato ao longo dos anos:
  - 2014 a nov/2018
  - Dez/2018 a 2019
  - 1º semestre de 2020
  - 2º semestre de 2020 a 2023
- Padronização de nomes de municípios e países.
- Classificação de profissões com base no [dicionário do ENEM](https://tinyurl.com/2s4f5f2k).

### 🔹 Etapa 3 — Dataset Unificado
- Integração dos quatro blocos em um único **dataset final consolidado**.
- Padronização das colunas comuns entre os períodos.
- Geração de um conjunto de dados final apto para análises temporais e geográficas.

---

## 📉 Dashboards Interativos

Visualizações públicas disponíveis no [Tableau Public] (https://public.tableau.com/app/profile/gabriel.zurawski/viz/GenderViolence-DataVis/Incio):

- Perfil da Vítima
- Perfil do Suspeito  
- Relação Vítima–Suspeito  
- Distribuição Geográfica  
- Frequência Temporal  
- Contexto da Violência  

## 🔬 Clusterização

Foram realizados testes com os algoritmos **K-Means** e **K-Modes**, utilizando diferentes combinações de variáveis. Apesar da proposta promissora, os resultados revelaram:

- Alta heterogeneidade dos dados  
- Baixa similaridade entre agrupamentos  
- Elevada taxa de valores ausentes  

**Conclusão:** os dados atuais não oferecem estrutura adequada para uma segmentação efetiva. A qualidade dos dados precisa ser aprimorada.

---

## 📚 Trabalho Original

Este projeto foi inspirado e expandido a partir do trabalho original [**"Explorando Dados Governamentais para Prevenção da Violência de Gênero: Uma Abordagem Visual"**](https://sol.sbc.org.br/index.php/wcge/article/view/29534), publicado e premiado como melhor artigo no **Workshop de Computação Aplicada em Governo Eletrônico (WCGE 2024)**.

PATRICIO, Eduarda; ZURAWSKI, Gabriel; ROLLWAGEN, André; MANSSOUR, Isabel. Explorando Dados Governamentais para Prevenção da Violência de Gênero: Uma Abordagem Visual. In: WORKSHOP DE COMPUTAÇÃO APLICADA EM GOVERNO ELETRÔNICO (WCGE), 12. , 2024, Brasília/DF. Anais [...]. Porto Alegre: Sociedade Brasileira de Computação, 2024 . p. 145-156. ISSN 2763-8723. DOI: https://doi.org/10.5753/wcge.2024.2966.

---

## 🤝 Agradecimentos

Agradecimentos especiais à **Isabel Harb Manssour** (orientadora) e aos colaboradores **Eduarda Patricio**, **André Rollwagen**, **Vinícius Pedroso** e **Giovanna Castro**.

---
