# 💳 Projeto: Segmentação e Classificação de Clientes de Cartão de Crédito

Este projeto aplica técnicas de **Aprendizado Não Supervisionado** para agrupar clientes por comportamento de consumo e **Aprendizado Supervisionado** para validar a consistência desses grupos. O objetivo é fornecer subsídios para estratégias de marketing personalizadas.

## 📂 Estrutura do Repositório

O projeto está organizado em três etapas principais, cada uma em seu respectivo notebook:

### 1. Limpeza e Tratamento de Dados (`01_project_cleaning_credit_card.ipynb`)
Foco na preparação da base de dados bruta (dados de aproximadamente 9.000 titulares).
* **Tratamento de Nulos:** Imputação de valores ausentes em colunas como `MINIMUM_PAYMENTS`.
* **Feature Engineering:** Remoção de identificadores não estatísticos (`CUST_ID`).
* **Escononamento:** Aplicação de `StandardScaler` para normalizar as grandezas financeiras.
[Image of StandardScaler normalization process]

### 2. Modelagem de Clustering (`02_Modelagem_Clustering_CreditCard.ipynb`)
Exploração de algoritmos para encontrar a melhor segmentação.
* **Algoritmos Testados:** K-Means, Agglomerative Clustering (Hierárquico), Gaussian Mixture Models e DBSCAN.
* **Métricas de Validação:**
    * **Método do Cotovelo (Elbow Method):** Para identificar o número ideal de clusters.
    * **Silhouette Score:** Para medir a coesão e separação dos grupos.
* **Definição:** Escolha dos cenários K=2, K=5 (K-Means) e K=6 (Hierárquico) para a fase de testes.
[Image of Elbow Method and Silhouette Score chart]

### 3. Classificação e Validação de Clusters (`03_Classificacao_Clusters.ipynb`)
Uso de algoritmos supervisionados para testar se os clusters são "previsíveis" e bem definidos.
* **Modelos Utilizados:** Naive Bayes, Decision Tree, Random Forest, KNN, Gradient Boosting e MLP (Redes Neurais).
* **Metodologia:** Validação Cruzada (10-Fold Cross-Validation) para garantir estabilidade.
* **Visualização:** Matrizes de Confusão detalhadas via biblioteca `Yellowbrick`.

---

## 📊 Performance dos Modelos

Os resultados mostram que os grupos gerados são altamente distinguíveis, com as Redes Neurais apresentando o melhor desempenho.

| Algoritmo | Dataset | Acurácia Média | F1-Score | Desvio Padrão |
| :--- | :--- | :--- | :--- | :--- |
| **MLP Neural Network** | K-Means K2 | **0.9951** | **0.9955** | 0.0018 |
| **MLP Neural Network** | K-Means K5 | **0.9899** | **0.9862** | 0.0016 |
