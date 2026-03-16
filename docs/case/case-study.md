# Case Study – Criminalidade no Rio de Janeiro

Projeto desenvolvido utilizando Power BI para análise de dados de criminalidade no estado do Rio de Janeiro.

## Objetivo do Case

O Secretário de Segurança Pública deseja apresentar à mídia um indicador positivo de redução da criminalidade em alguma região do estado, considerando o histórico dos últimos 3 anos.

A hipótese inicial é que a Região Sul apresenta maior potencial para essa redução.

O desafio consiste em:

* Validar se essa hipótese é verdadeira
* Identificar outra região caso necessário
* Identificar o tipo de crime que melhor representa a redução
* Construir um ranking de regiões
* Criar um dashboard analítico para apoiar decisões estratégicas

---

## Fontes de Dados

Dados públicos utilizados:

* https://www.ispdados.rj.gov.br/
* https://dados.gov.br/

---

## Modelagem de Dados

Durante o projeto foram utilizados:

* Power Query para tratamento e transformação dos dados
* DAX para cálculos e métricas analíticas
* Criação de tabela calendário para análise temporal

Exemplo de criação de data no Power Query:

#date([ano],[mes],1)

---

## Métricas Utilizadas

Indicadores de letalidade foram construídos com base em:

* Homicídio doloso
* Latrocínio
* Intervenção policial
* Lesão corporal seguida de morte

Exemplo de cálculo:

Homicidios =
hom_culposo + hom_doloso + hom_por_interv_policial + tentat_hom

---

## Exemplos de Cálculos em DAX

Filtro simples:

Total_Latrocinio_2017 =
CALCULATE(
SUM(UppEvolucaoMensalDeTitulos[latrocinio]),
UppEvolucaoMensalDeTitulos[ano] = 2017
)

Filtro múltiplo:

CDD_2021 =
CALCULATE(
SUM(UppEvolucaoMensalDeTitulos[registro_ocorrencias]),
UppEvolucaoMensalDeTitulos[upp] = "Cidade de Deus",
UppEvolucaoMensalDeTitulos[ano] = 2021
)

---

## Análises Desenvolvidas

O dashboard apresenta análises como:

* Ranking de regiões com maior criminalidade
* Classificação de risco
* Percentil de ocorrências
* Evolução temporal dos crimes
* Comparação com períodos anteriores

---

## Técnicas de DAX utilizadas

* RANKX
* IF
* SWITCH
* PERCENTILE
* SAMEPERIODLASTYEAR
* CALCULATE
* FILTER

---

## Resultado Esperado

O dashboard permite que a equipe de segurança pública:

* identifique regiões prioritárias
* avalie tendências de criminalidade
* analise indicadores de risco
* proponha políticas públicas para redução de crimes
