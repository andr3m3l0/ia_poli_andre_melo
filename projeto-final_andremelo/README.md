
# 💨 Predição e Classificação da Qualidade do Ar (Air Quality UCI)

Este projeto aplica algoritmos de **Machine Learning supervisionado** para realizar **classificação** e **regressão** sobre o dataset *Air Quality* da UCI, com foco em prever e classificar a concentração de CO (monóxido de carbono) com base em leituras de sensores ambientais.

---

## 📁 Dataset

- Fonte: [UCI Machine Learning Repository – Air Quality](https://archive.ics.uci.edu/ml/datasets/Air+quality)
- Formato: CSV compactado (`.zip`)
- Atributos: Leituras de sensores (CO, NOx, NO₂), temperatura, umidade relativa, etc.
- Target:
  - **Classificação**: Nível de CO (baixa, média, alta)
  - **Regressão**: Previsão contínua de CO(GT)

---

## ⚙️ Etapas Executadas

### 🔹 1. Pré-processamento

- Leitura do `.zip` direto da URL
- Tratamento de valores faltantes e negativos
- Conversão de colunas `Date` e `Time` em `datetime`
- Remoção de colunas irrelevantes

### 🔹 2. Análise Exploratória

- Histogramas das variáveis principais
- Matriz de correlação entre sensores

### 🔹 3. Classificação de CO

- Criadas 3 classes: `0 = baixa`, `1 = média`, `2 = alta`
- Balanceamento com **SMOTE** (`k_neighbors=3`)
- Escalonamento com **StandardScaler**
- Modelos usados:
  - Regressão Logística
  - Random Forest
  - XGBoost

### 🔹 4. Ajuste de Hiperparâmetros

- Aplicado **GridSearchCV** com validação cruzada (cv=5)
- Métrica de avaliação: **accuracy**
- Selecionado o melhor modelo por performance

### 🔹 5. Avaliação da Classificação

- Métricas macro: Accuracy, Precision, Recall, F1-score
- Matriz de Confusão
- Visualização comparativa com gráficos de barras

### 🔹 6. PCA (Classificação)

- Aplicado **PCA (n_components=0.95)** para reduzir dimensionalidade
- Treinamento do melhor modelo com os dados reduzidos
- Comparação do desempenho com e sem PCA

### 🔹 7. Regressão

- Target: valores contínuos de `CO(GT)`
- Modelos utilizados:
  - Regressão Linear
  - Random Forest
  - XGBoost
- Métricas avaliadas: **R², RMSE, MAE**
- Ajuste de hiperparâmetros com **GridSearchCV**

### 🔹 8. PCA (Regressão)

- Aplicado PCA com todos os componentes
- Comparação de desempenho (com vs sem PCA)
- Gráficos de dispersão dos valores reais vs preditos

---

## 📊 Resultados

### Classificação
- Modelos baseados em árvore (Random Forest e XGBoost) superaram a Regressão Logística
- SMOTE melhorou a distribuição das classes
- PCA reduziu dimensionalidade com desempenho semelhante

### Regressão
- Random Forest obteve o melhor R² geral
- PCA manteve desempenho semelhante, reduzindo dimensionalidade

---

## 🔍 Conclusões

- O uso de **SMOTE** e ajuste de hiperparâmetros via **GridSearchCV** foram cruciais para melhorar o desempenho.
- **Redes neurais ou modelos como CatBoost** podem ser explorados no futuro.
- Avaliações por classe e uso de **AUC-ROC multiclasse** também são possibilidades de expansão.
