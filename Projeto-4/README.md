# 🧩 Agrupamento de espécies de pinguins com K-Means

## Contexto do Projeto

Este projeto é um estudo aprofundado do algoritmo de agrupamento **K-Means**, uma das técnicas fundamentais do aprendizado de máquina não supervisionado. O objetivo principal não foi apenas aplicar o algoritmo, mas sim explorar todo o seu ecossistema: desde a preparação crucial dos dados e a seleção de hiperparâmetros até a avaliação e interpretação dos clusters resultantes.

Através de uma abordagem prática e comparativa, o projeto investiga como diferentes técnicas de pré-processamento, como a **Normalização** e a **Padronização**, impactam a performance do K-Means, oferecendo insights sobre a sensibilidade e o funcionamento interno do algoritmo.

## Metodologia e Etapas da Análise

O projeto foi desenvolvido seguindo um fluxo de trabalho estruturado para a aplicação de algoritmos de agrupamento.

### Pré-processamento e Preparação dos Dados
- **Análise e Tratamento de Outliers:** Foi realizada uma investigação de valores extremos, seguida de sua remoção. Esta etapa foi identificada como crítica, pois o K-Means, por ser um algoritmo baseado na média (centróides), é altamente sensível a outliers.
- **Escalonamento de Features (Scaling):** O passo mais importante na preparação. Foram aplicadas e comparadas duas técnicas distintas para colocar as variáveis na mesma escala:
    1.  **Padronização (`StandardScaler`):** Transforma os dados para terem média 0 e desvio padrão 1.
    2.  **Normalização (`MinMaxScaler`):** Transforma os dados para ficarem no intervalo de 0 a 1.

### Seleção do Número Ideal de Clusters (k)
- **Método do Cotovelo (Elbow Method):** Foi utilizada a métrica de **Inércia (WCSS)** para diferentes valores de `k`. A análise do gráfico permitiu identificar o "cotovelo", um ponto de inflexão que sugere um número ótimo de clusters.
- **Análise de Silhueta (Silhouette Analysis):** Como técnica de validação, foi calculado o **Coeficiente de Silhueta** para diferentes valores de `k`. O `k` que maximizou o score de silhueta foi considerado o mais robusto, pois leva em conta tanto a **coesão** (proximidade dentro de um cluster) quanto a **separação** (distância entre clusters).

### Modelagem e Avaliação Comparativa
- Foram treinados múltiplos modelos K-Means, variando o número de clusters `k` e, principalmente, a técnica de escalonamento aplicada aos dados.
- Os resultados dos clusters gerados com dados **padronizados** e **normalizados** foram comparados para entender o impacto de cada abordagem na estrutura final dos grupos.


## Principais Conceitos e Aprendizados

- **Centróides:** O K-Means funciona encontrando os centróides (o ponto médio de cada dimensão) que melhor representam o centro de cada cluster.
- **Coesão vs. Isolamento:** Um bom agrupamento exige alta coesão (pontos próximos ao seu centróide - `baixa inércia`) e alto isolamento/separação (clusters distantes entre si - `alto score de silhueta`).
- **Sensibilidade a Outliers:** Foi validado na prática que, por ser baseado em médias, o K-Means tem sua performance e a posição de seus centróides fortemente influenciada por valores extremos.