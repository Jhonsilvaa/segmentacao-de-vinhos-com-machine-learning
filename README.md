# Segmentação de Vinhos com Machine Learning

O vinho é uma das bebidas alcoólicas mais antigas e apreciadas do mundo, estimado como a quinta bebida mais consumida globalmente. É produzido a partir da fermentação natural do sumo da uva, refletindo características únicas de região, clima e técnicas de produção.

Em um mercado globalizado e com consumidores cada vez mais exigentes, a indústria vinícola tem avançado com o uso de dados. Neste projeto, o objetivo é segmentar vinhos exclusivamente com base em suas propriedades químicas — acidez, pH, teor alcoólico, concentração de sulfatos, entre outras.

<p align="center">
<img src="https://github.com/user-attachments/assets/0f451a73-b9dd-404d-9424-6acd37d6ba97" width="60%">
</p>

---

## 📖 Visão Geral

| | |
|---|---|
| **Problema** | Clustering — segmentar vinhos por propriedades químicas |
| **Dataset** | Wine Quality Dataset (UCI) - 338.436 entradas |

---

## 🔍 Abordagem

### 1. Análise Exploratória
- Distribuição das propriedades químicas dos vinhos
- Análise de correlação entre variáveis — relação entre densidade e teor alcoólico
- Identificação de outliers via boxplot

### 2. Pré-processamento
- **StandardScaler** para normalização das features
- **PCA** para redução de dimensionalidade e visualização dos clusters

### 3. Modelagem
Três algoritmos de clustering foram comparados:

- **KMeans** — otimização do número de clusters via Elbow Method e Silhouette Score
- **DBSCAN** — determinação do epsilon via k-Distance Plot com **KneeLocator** + otimização de hiperparâmetros com **Optuna**
- **AgglomerativeClustering** — dendrograma para definição do número de clusters

### 4. Avaliação
Três métricas simultâneas para comparação robusta dos modelos:

| Métrica | O que mede |
|---|---|
| **Silhouette Score** | Coesão e separação dos clusters |
| **Calinski-Harabasz** | Razão entre dispersão inter e intra cluster |
| **Davies-Bouldin** | Similaridade média entre clusters (menor = melhor) |

---

## 📈 Resultados

| Modelo | Silhouette | Calinski-Harabasz | Davies-Bouldin |
|---|---|---|---|
| KMeans | **0.52** | **4381** | **0.8775** |
| DBSCAN | 0.8604 | 152 | 0.173 |
| AgglomerativeClustering | 0.786 | 343.74 | 0.330 |

---

## 📓 Notebook

🔗 [Ver projeto completo no Colab](http://bit.ly/3Gn6Z4c)

---

## ⚡️ Tecnologias

`Python` `Scikit-learn` `Optuna` `Pandas` `Seaborn` `Matplotlib`

---

## 👨‍💻 Autor

**Jhonatas Assumpção**

[![GitHub](https://img.shields.io/badge/GitHub-Jhonsilvaa-181717?style=flat&logo=github)](https://github.com/Jhonsilvaa)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Jhonatas-0A66C2?style=flat&logo=linkedin)](https://linkedin.com/in/jhonatas-assumpção-da-silva-62a7931b3)
[![Medium](https://img.shields.io/badge/Medium-@jhonatasassumpcao-000000?style=flat&logo=medium)](https://medium.com/@jhonatasassumpcao)

---

## 📄 Licença

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

Este projeto está licenciado sob a **[GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0)** — consulte o arquivo [LICENSE](https://github.com/Jhonsilvaa/segmentacao-de-vinhos-com-machine-learning/blob/main/LICENSE) para mais detalhes.
