# 🚗 Previsão de Preços de Veículos com Regressão Linear

## Contexto do Projeto

Este projeto representa uma imersão profunda na aplicação e diagnóstico de modelos de **Regressão Linear** para um problema clássico de previsão de preços de veículos. O objetivo principal não foi apenas construir um modelo, mas sim executar um ciclo completo e iterativo de Data Science, compreendendo os desafios reais do pré-processamento, da seleção de features e da avaliação crítica dos resultados.

A análise documenta uma jornada de **14 iterações de modelagem**, explorando os limites do modelo linear e destacando a importância de cada etapa do processo para a construção de um modelo robusto e confiável.

##  Metodologia e Jornada Analítica

Este projeto foi muito mais do que um simples treinamento de modelo. Foi um exercício completo que passou pelas seguintes etapas:

## a. Limpeza e Pré-processamento de Dados
- **Tratamento de Dados Ausentes:** Análise e remoção de valores nulos (`NaN`) para garantir a integridade do dataset.
- **Detecção de "Dados Sujos":** Utilização de técnicas de análise de padrões e frequência (`.value_counts()`, `.str.len()`) para identificar e limpar registros que, embora não nulos, não continham informação relevante.
- **Análise e Tratamento de Outliers:** Identificação de valores extremos nas variáveis `mileage` e `price` através de box plots. A decisão estratégica de manter os outliers inicialmente e removê-los em iterações posteriores foi crucial para entender seu impacto no modelo.

## b. Engenharia e Transformação de Features
- **Encoding de Variáveis Categóricas:**
    - **Experimentação com `LabelEncoder`:** Uma análise inicial foi feita, mas concluiu-se que este método criava uma ordem numérica falsa e prejudicial ao modelo.
    - **Implementação de `One-Hot Encoding`:** A técnica correta (`pd.get_dummies`) foi aplicada, incluindo estratégias para lidar com **alta cardinalidade** (agrupamento de categorias raras), o que resultou em uma melhora drástica no desempenho do modelo.
- **Criação de Intervalos (Binning):** Uso da função `pd.cut()` para transformar variáveis numéricas contínuas (como quilometragem) em faixas categóricas, facilitando análises e visualizações.

## c. Análise Exploratória de Dados (EDA)
- Análise aprofundada das medidas de tendência central e dispersão, com foco na comparação entre **média e mediana** para entender a assimetria das distribuições.
- Verificação da distribuição de cada variável com **histogramas** e testes de normalidade (**Shapiro-Wilk**), concluindo que as variáveis não seguiam uma distribuição normal.
- Análise de correlação utilizando o **Teste de Spearman** (adequado para dados não-normais) e visualização com **heatmaps** para identificar as features mais promissoras.

## d. Modelagem Iterativa e Avaliação
- **Construção de 14 Modelos:** O coração do projeto foi o processo iterativo de treinar, avaliar e refinar.
- **Seleção de Features:** Utilização do **p-valor** dos coeficientes do modelo (extraído dos resultados da regressão OLS) para remover variáveis não significativas.
- **Diagnóstico de Multicolinearidade:** Análise da correlação entre features e investigação de avisos de `Condition Number` alto, com cálculo do **VIF (Variance Inflation Factor)** para confirmar a redundância entre variáveis.
- **Avaliação de Métricas:** Análise criteriosa do **R²** e do **R² Ajustado**. A comparação entre o score de treino e o de teste foi fundamental para identificar um caso real de **overfitting** em um dos modelos.
- **Análise de Resíduos:** Verificação dos resíduos do modelo final, incluindo a análise de sua soma (`SQE`) e o teste de normalidade, que confirmou a natureza não-linear do problema.

## Principais Descobertas e Conclusões

1.  **Impacto do Encoding:** A troca do `LabelEncoder` pelo `One-Hot Encoding` foi a otimização mais impactante, fazendo o **R² do modelo saltar de ~40% para ~65%**. Isso provou na prática a importância de representar corretamente os dados categóricos.
2.  **Limites da Regressão Linear:** Mesmo após todas as otimizações, o modelo final estabilizou com um **R² de 63%**. A análise dos resíduos (que não se mostraram normais) confirmou a tese de que a relação entre as características dos carros e seus preços é intrinsecamente **não-linear**, e um modelo linear, por melhor que seja ajustado, tem um teto de performance.
3.  **Overfitting na Prática:** A comparação entre um modelo com R² de treino de 0.70 (com variáveis não significativas) e o modelo final com R² de treino de 0.63 (apenas com variáveis significativas) demonstrou um caso claro de overfitting. O modelo mais simples (0.63) **generalizou melhor e teve um desempenho superior nos dados de teste**.
4.  **A Importância do Processo:** A maior conclusão do projeto é o valor do processo iterativo. Cada uma das 14 iterações revelou uma nova característica dos dados ou uma limitação do modelo, guiando para o próximo passo lógico e construindo um entendimento profundo do problema.

## Habilidades Demonstradas

- **Pré-processamento de Dados Completo:** Limpeza, transformação, tratamento de outliers e encoding.
- **Análise Exploratória e Estatística:** Testes de hipótese (Teste T, Shapiro-Wilk), análise de correlação (Spearman, p-valor).
- **Modelagem Preditiva com Regressão Linear:** Treinamento, avaliação de métricas (R², R² Ajustado, SQE).
- **Diagnóstico Avançado de Modelos:** Análise de resíduos, diagnóstico de multicolinearidade (VIF), identificação de overfitting.
- **Resolução de Problemas e Raciocínio Crítico:** Iteração e formulação de hipóteses para explicar o comportamento do modelo.