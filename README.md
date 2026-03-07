# SPANISH


# 💳 Proyecto: Segmentación y Clasificación de Clientes de Tarjetas de Crédito

Este proyecto aplica técnicas de **Aprendizaje No Supervisado** para agrupar clientes según su comportamiento de consumo y **Aprendizaje Supervisado** para validar la consistencia de estos grupos. El objetivo es proporcionar información estratégica para campañas de marketing personalizadas y gestión de riesgos.

## 📂 Estructura del Repositorio

El proyecto está organizado en cuatro etapas principales, cada una en su respectivo notebook:

### 1. Limpieza y Tratamiento de Datos (`01_project_cleaning_credit_card.ipynb`)
Preparación de la base de datos bruta (datos de aproximadamente 9,000 titulares).
* **Tratamiento de Nulos:** Imputación de valores ausentes en columnas como `MINIMUM_PAYMENTS`.
* **Ingeniería de Características:** Eliminación de identificadores no estadísticos (`CUST_ID`) y traducción de atributos.
* **Escalamiento:** Aplicación de `StandardScaler` para normalizar las magnitudes financieras.


### 2. Modelado de Clustering (`02_Modelagem_Clustering_CreditCard.ipynb`)
Exploración de algoritmos para encontrar la mejor segmentación.
* **Algoritmos Probados:** K-Means, Clustering Jerárquico (Aglomerativo), Gaussian Mixture Models y DBSCAN.
* **Métricas de Validación:**
    * **Método del Codo (Elbow Method):** Identificación del número ideal de clusters.
    * **Silhouette Score:** Medición de la cohesión y separación de los grupos.
* **Definición:** Selección de los escenarios K=2, K=5 (K-Means) y K=6 (Jerárquico) para un análisis profundo.


### 3. Clasificación y Validación de Clusters (`03_Classificacao_Clusters.ipynb`)
Uso de algoritmos supervisados para probar si los clusters son "predecibles".
* **Modelos:** Naive Bayes, Decision Tree, Random Forest, KNN, Gradient Boosting y Redes Neuronales (MLP).
* **Metodología:** Validación Cruzada (10-Fold Cross-Validation).
* **Rendimiento:** Las Redes Neuronales presentaron el mejor desempeño en la distinción de los grupos.

### 4. Análisis de Perfilado e Insights (`04_Credit_Card_Customer_Segmentation.ipynb`)
Inspección estadística y visual de los grupos formados para extraer valor de negocio.
* **Métricas:** Uso de Medianas (tendencia central robusta) y Desviación Estándar (indicador de dispersión).
* **Visualización:** Gráficos de barras agrupados separando atributos monetarios de comportamentales para mayor precisión de escala.

---

## 📊 Comparativa de los Modelos de Segmentación

Al comparar los tres enfoques, identificamos diferentes utilidades para el negocio:

| Modelo | Resumen del Perfilado | Mejor Uso para el Negocio |
| :--- | :--- | :--- |
| **K-Means (K=2)** | Visión binaria: Clientes **Gastadores** (Alto uso) vs. **Ahorradores** (Uso conservador). | Campañas masivas y activación de base inactiva. |
| **K-Means (K=5)** | División estratégica: 1 grupo inactivo y **4 grupos de alto gasto** con motivaciones distintas (ej. a plazos vs. al contado). | Estrategias de Cross-sell y ofertas de Cashback dirigidas. |
| **Jerárquico (K=6)** | Visión granular: Diferencia entre **Económicos Antiguos** y **Económicos Nuevos**, además de aislar anomalías de pago. | Gestión de Riesgos, Prevención de Churn y Atención VIP (High Spenders). |



---

## 💡 Principales Insights de Negocio

* **Cluster de Riesgo Crítico:** Identificamos un grupo (H6 - Cluster 5) con pagos mínimos astronómicos en relación al saldo, lo que indica un sobreendeudamiento severo.
* **El Grupo "Ballena" (Whales):** Clientes cuyos gastos superan el límite de crédito mensual, lo que sugiere una alta rotación financiera y necesidad de mayores límites.
* **Fidelidad vs. Gasto:** El modelo Jerárquico reveló que los clientes nuevos (Cluster 3) actúan de forma distinta a los clientes antiguos de bajo gasto, requiriendo estrategias de *onboarding* diferenciadas.

---
## 🛠️ Tecnologías Utilizadas
* **Python** (Pandas, NumPy)
* **Scikit-Learn** (Clustering y Clasificación)
* **Matplotlib & Seaborn** (Visualización de Datos)
* **IPython Display** (Informes Dinámicos en HTML)

---
# PORTUGUESE

# 💳 Projeto: Segmentação e Classificação de Clientes de Cartão de Crédito

Este projeto aplica técnicas de **Aprendizado Não Supervisionado** para agrupar clientes por comportamento de consumo e **Aprendizado Supervisionado** para validar a consistência desses grupos. O objetivo é fornecer subsídios para estratégias de marketing personalizadas e gestão de risco.

## 📂 Estrutura do Repositório

O projeto está organizado em quatro etapas principais, cada uma em seu respectivo notebook:

### 1. Limpeza e Tratamento de Dados (`01_project_cleaning_credit_card.ipynb`)
Foco na preparação da base de dados bruta (dados de aproximadamente 9.000 titulares).
* **Tratamento de Nulos:** Imputação de valores ausentes em colunas como `MINIMUM_PAYMENTS`.
* **Feature Engineering:** Remoção de identificadores não estatísticos (`CUST_ID`) e tradução de atributos para o português.
* **Escalonamento:** Aplicação de `StandardScaler` para normalizar as grandezas financeiras.


### 2. Modelagem de Clustering (`02_Modelagem_Clustering_CreditCard.ipynb`)
Exploração de algoritmos para encontrar a melhor segmentação.
* **Algoritmos Testados:** K-Means, Agglomerative Clustering (Hierárquico), Gaussian Mixture Models e DBSCAN.
* **Métricas de Validação:**
    * **Método do Cotovelo (Elbow Method):** Identificação do "k" ideal.
    * **Silhouette Score:** Medição da coesão e separação dos grupos.
* **Definição:** Escolha dos cenários K=2, K=5 (K-Means) e K=6 (Hierárquico) para análise profunda.


### 3. Classificação e Validação de Clusters (`03_Classificacao_Clusters.ipynb`)
Uso de algoritmos supervisionados para testar se os clusters são "previsíveis".
* **Modelos:** Naive Bayes, Decision Tree, Random Forest, KNN, Gradient Boosting e Redes Neurais (MLP).
* **Metodologia:** Validação Cruzada (10-Fold Cross-Validation).
* **Performance:** As Redes Neurais apresentaram o melhor desempenho na distinção dos grupos.

### 4. Análise de Perfilamento e Insights (`04_Credit_Card_Customer_Segmentation.ipynb`)
Inspeção estatística e visual dos grupos formados para extrair valor de negócio.
* **Métricas:** Uso de Medianas (tendência central robusta) e Desvio Padrão (termômetro de dispersão).
* **Visualização:** Gráficos de barras agrupados separando atributos monetários de comportamentais para precisão de escala.

---

## 📊 Comparativo dos Modelos de Segmentação

Ao compararmos as três abordagens, identificamos diferentes utilidades para o negócio:

| Modelo | Resumo do Perfilamento | Melhor Uso para o Negócio |
| :--- | :--- | :--- |
| **K-Means (K=2)** | Visão binária: Clientes **Gastadores** (Alto uso) vs. **Poupadores** (Baixo uso). | Campanhas de massa e ativação de base inativa. |
| **K-Means (K=5)** | Divisão estratégica: 1 grupo inativo e **4 grupos de alto gasto** com motivações distintas (ex: parcelados vs. à vista). | Estratégias de Cross-sell e ofertas de Cashback direcionadas. |
| **Hierárquico (K=6)** | Visão granular: Diferencia **Econômicos Antigos** de **Econômicos Novos**, além de isolar anomalias de pagamento. | Gestão de Risco, Prevenção de Churn e Atendimento VIP (High Spenders). |



---

## 💡 Principais Insights de Negócio

* **Cluster de Risco Crítico:** Identificamos um grupo (H6 - Cluster 5) com pagamentos mínimos astronômicos em relação ao saldo, sinalizando endividamento severo.
* **O Grupo "Baleia":** Clientes com gastos que superam o limite de crédito mensal, indicando alta rotatividade financeira e necessidade de limites maiores.
* **Fidelidade vs. Gasto:** O modelo Hierárquico revelou que clientes novos (Cluster 3) agem de forma diferente de clientes antigos de baixo gasto, exigindo abordagens de *onboarding* distintas.

---
## 🛠️ Tecnologias Utilizadas
* **Python** (Pandas, NumPy)
* **Scikit-Learn** (Clustering e Classificação)
* **Matplotlib & Seaborn** (Visualização de Dados)
* **IPython Display** (Relatórios Dinâmicos em HTML)
