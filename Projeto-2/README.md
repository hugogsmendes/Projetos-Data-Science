# 📊 Análise de Transações com Cartão Corporativo do Governo (Junho/2018)

## Contexto do Projeto

Este projeto realiza uma análise exploratória de dados (EDA) sobre os gastos realizados através de Cartões de Pagamento do Governo Federal (CPGF) durante o mês de **junho de 2018**. O objetivo é explorar os padrões de transação, identificar os órgãos com maiores despesas, analisar os diferentes tipos de transações e gerar insights sobre o uso dos recursos públicos neste período específico.

Este trabalho serve como um exercício prático do ciclo de vida de um projeto de Data Science, desde a limpeza e preparação dos dados até a análise estatística e a comunicação de resultados.


## Principais Insights e Conclusões

A análise aprofundada do dataset de transações de junho de 2018 revelou padrões significativos no uso dos cartões de pagamento, com um destaque especial para o volume e a natureza das despesas sigilosas.

### a. Panorama Geral: Transações Sigilosas vs. Não Sigilosas

- Do total de **11.260 transações** analisadas no mês, **1.739 (aproximadamente 15,4%)** foram classificadas como sigilosas.
- Embora as **9.521 transações não sigilosas** somem um valor maior (R$ 2.284.076,95), as **1.739 transações sigilosas** representam um montante expressivo de **R$ 1.749.347,32**.

### b. Análise das Transações Sigilosas

- **Alta Concentração de Gastos:** A análise demonstrou que os gastos sigilosos estão massivamente concentrados em dois órgãos: o **Ministério da Justiça** (R$ 896.070,59) e a **Presidência da República** (R$ 846.276,73). Juntos, eles são responsáveis por **99% de todo o valor gasto** em transações sigilosas.
- **Transações Extremas (Outliers):** O uso de box plots permitiu identificar que estes dois órgãos também realizaram transações com valores extremamente altos em comparação com os demais, caracterizados como outliers.
- **Maior Transação Individual:** A maior despesa unitária registrada foi uma compra sigilosa de **R$ 30.591,00**, realizada pela "SECRETARIA DE ADMINISTRACAO/PR", uma unidade gestora da Presidência da República.
- **Valor Médio por Transação Sigilosa:** Apesar do volume total, a média por transação varia entre os principais órgãos:
    - **Presidência da República:** Média de **R$ 1.469,00** por transação (576 transações).
    - **Ministério da Justiça:** Média de **R$ 776,00** por transação (1154 transações).
    - **Ministério da Fazenda:** Média de **R$ 777,00** por transação 
    (9 transações).


### c. Estudo de Caso: Presidência da República

- **Predominância de Gastos Sigilosos:** Do total de 984 transações realizadas pelo órgão, 576 (58,5%) foram sigilosas. Em termos de valor, o sigilo é ainda mais expressivo: **89% (R$ 846.276,73)** de todo o gasto do órgão no período foi confidencial.
- **Confirmação Estatística:** Um **Teste T de hipótese** confirmou com significância estatística que a média de valor das transações sigilosas da Presidência é, de fato, diferente da média geral de transações do mesmo órgão.

### d. Análise Temporal e Setorial

- **Pico de Atividade:** O dia **21 de junho de 2018** foi o de maior atividade financeira, registrando **614 transações** que somaram **R$ 148.074,00**.
- **Principal Gasto do Dia:** Neste dia de pico, o **Ministério da Defesa** foi o principal gastador, com R$ 30.251,11 distribuídos entre seus comandos. Notavelmente, **50,58%** deste valor (R$ 15.302,45) foi destinado ao **Comando do Exército**, que utilizou 45,3% dessa fatia (R$ 6.932,75) em despesas com linhas aéreas.

### e. Análise por Tipo de Transação

- **Volume vs. Valor:** As "Compras à vista no Brasil" foram o tipo de transação mais frequente (7.838 ocorrências). No entanto, um insight crucial emergiu da análise: mesmo com um volume **55% vezes menor** que as compras comuns, o valor total das **transações sigilosas (R$ 1.749 milhão)** foi ligeiramente **superior** ao valor total das compras à vista (R$ 1,741 milhão), indicando um ticket médio muito mais elevado para os gastos sigilosos.

### f. Análise Preditiva (Probabilidade)

- Utilizando a Distribuição Binomial, foi calculado que, para um cenário hipotético de 11.000 transações no mês seguinte (julho), a probabilidade de se obter **mais de 1.700 transações sigilosas** seria de aproximadamente **47%**, indicando uma chance considerável de que o alto volume de gastos sigilosos se mantivesse.
