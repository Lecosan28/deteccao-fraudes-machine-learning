# Detecção de Fraudes em Transações Financeiras com Machine Learning

## Objetivo

Este projeto foi desenvolvido como parte de um desafio da plataforma DIO (Digital Innovation One) com o objetivo de aplicar técnicas de Machine Learning para identificar transações financeiras fraudulentas.

O desafio consiste em analisar um conjunto de dados de transações de cartão de crédito, preparar os dados para treinamento e comparar diferentes algoritmos de classificação para determinar qual apresenta melhor desempenho na detecção de fraudes.

---

## Dataset Utilizado

Foi utilizado o conjunto de dados público Credit Card Fraud Detection Dataset, disponibilizado pelo TensorFlow.

Características do dataset:

- 284.807 transações financeiras
- Variáveis anonimizadas utilizando PCA (V1 a V28)
- Coluna Amount contendo o valor da transação
- Coluna Class indicando:
  - 0 = Transação normal
  - 1 = Transação fraudulenta

O conjunto de dados apresenta forte desbalanceamento, com mais de 99% das transações pertencendo à classe normal.

---

## Tecnologias Utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-Learn
- XGBoost
- SHAP
- Jupyter Notebook
- VS Code

---

## Etapas do Projeto

### 1. Carregamento dos Dados

Importação do dataset e visualização das primeiras linhas para compreender a estrutura dos dados.

### 2. Análise Inicial

Verificação da distribuição das classes para identificar o desbalanceamento entre transações normais e fraudulentas.

### 3. Engenharia de Atributos (Feature Engineering)

Foram realizadas transformações para melhorar o desempenho dos modelos:

- Transformação logarítmica da variável Amount
- Padronização dos valores utilizando StandardScaler

### 4. Preparação dos Dados

Separação das variáveis:

- X → Variáveis de entrada
- y → Variável alvo (Class)

Divisão dos dados em:

- 70% para treinamento
- 30% para teste

### 5. Treinamento dos Modelos

Foram treinados diferentes algoritmos de Machine Learning para comparação de desempenho.

---

## Modelos Testados

### Logistic Regression

Modelo linear utilizado como baseline inicial para classificação das transações.

### Random Forest

Modelo baseado em múltiplas árvores de decisão, utilizando votação para realizar a classificação final.

### XGBoost

Modelo baseado em Gradient Boosting, no qual cada nova árvore procura corrigir os erros das árvores anteriores.

---

## Métricas Utilizadas

### Accuracy

Percentual total de acertos do modelo.

### Precision

Entre as transações classificadas como fraude, quantas realmente eram fraude.

### Recall

Entre todas as fraudes existentes, quantas foram identificadas pelo modelo.

### F1-Score

Média harmônica entre Precision e Recall.

### ROC Curve

Avalia a capacidade do modelo em separar as classes.

### Precision-Recall Curve

Importante para bases desbalanceadas, como o problema de detecção de fraudes.

---

## Balanceamento dos Dados

Foram apresentadas técnicas para lidar com o desbalanceamento do conjunto de dados:

### Undersampling

Redução da quantidade de exemplos da classe majoritária.

### Oversampling (SMOTE)

Geração de exemplos sintéticos da classe minoritária.

---

## Interpretabilidade

Foi utilizada a biblioteca SHAP para identificar quais variáveis possuem maior influência nas decisões do modelo.

Também foi realizada análise de importância das variáveis utilizando o XGBoost.

---

## Resultados Obtidos

### Logistic Regression

| Métrica | Classe Fraude |
|----------|----------|
| Precision | 0.86 |
| Recall | 0.66 |
| F1-Score | 0.75 |

### Random Forest

| Métrica | Classe Fraude |
|----------|----------|
| Precision | 0.74 |
| Recall | 0.80 |
| F1-Score | 0.77 |

### XGBoost

| Métrica | Classe Fraude |
|----------|----------|
| Precision | 0.94 |
| Recall | 0.78 |
| F1-Score | 0.85 |

### XGBoost com Grid Search

| Métrica | Classe Fraude |
|----------|----------|
| Precision | 0.95 |
| Recall | 0.74 |
| F1-Score | 0.83 |

---

## Comparação dos Modelos

| Modelo | Precision | Recall | F1-Score |
|----------|----------|----------|----------|
| Logistic Regression | 0.86 | 0.66 | 0.75 |
| Random Forest | 0.74 | 0.80 | 0.77 |
| XGBoost | 0.94 | 0.78 | 0.85 |
| XGBoost + Grid Search | 0.95 | 0.74 | 0.83 |

---

## Conclusão

O modelo XGBoost apresentou o melhor equilíbrio entre precisão e capacidade de detecção de fraudes, alcançando Precision de 0.94, Recall de 0.78 e F1-Score de 0.85.

Embora o Grid Search tenha aumentado ligeiramente a precisão para 0.95, houve redução do Recall e do F1-Score, indicando que o modelo original apresentou desempenho mais equilibrado para este conjunto de dados.

Os resultados demonstram a importância da comparação entre diferentes algoritmos e métricas, especialmente em problemas com classes desbalanceadas.

---

## Como Executar o Projeto

1. Clone este repositório:

```bash
git clone https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git
```

2. Instale as dependências:

```bash
pip install pandas numpy matplotlib scikit-learn xgboost shap imbalanced-learn
```

3. Abra o Jupyter Notebook:

```bash
jupyter notebook
```

4. Abra o arquivo:

```text
deteccao_fraudes.ipynb
```

5. Execute as células em sequência.
