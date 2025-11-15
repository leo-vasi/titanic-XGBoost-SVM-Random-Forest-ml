# Comparação de Modelos — Titanic Survival Prediction

Este projeto implementa um pipeline completo de Machine Learning utilizando o dataset **Titanic**, disponível pelo *Seaborn*.  
O objetivo é comparar três modelos de classificação, **SVM (RBF)**, **Random Forest** e **XGBoost**, após otimização de hiperparâmetros via **RandomizedSearchCV**.

---

## 1. Sobre o Projeto

O pipeline foi construído com foco em:

- Pré-processamento adequado dos dados  
- Normalização de variáveis numéricas  
- Codificação de variáveis categóricas  
- Treino e otimização de três algoritmos distintos  
- Avaliação baseada em métricas e visualizações  
- Comparação final do desempenho

O objetivo é identificar qual modelo apresenta o melhor equilíbrio entre desempenho, velocidade de treinamento e capacidade de generalização.

---

##  2. Preparação e Tratamento dos Dados

As seguintes etapas foram aplicadas ao dataset:

### Seleção de Features
Foram selecionadas 8 variáveis relevantes:  
`survived`, `pclass`, `sex`, `age`, `sibsp`, `parch`, `fare`, `embarked`.

### Tratamento de valores ausentes
- `age`: substituída pela **mediana**  
- `embarked`: substituída pela **moda**

### Normalização
Variáveis numéricas padronizadas com **StandardScaler**:  
`age`, `fare`

### Codificação
Variáveis categóricas transformadas com **One-Hot Encoding**:  
`sex`, `embarked`, `pclass`

### Garantia de consistência
Treino e teste foram alinhados para manter **as mesmas colunas** após a codificação.

---

## 3. Modelos Treinados

Os seguintes algoritmos foram configurados e otimizados:

###  SVM (RBF)
- Kernel RBF  
- Busca por `C` e `gamma` em escalas logarítmicas  
- Indicado para separações não lineares

### Random Forest
- Combinação de múltiplas árvores  
- Hiperparâmetros variados de profundidade, divisão e amostragem  
- Forte robustez e bom desempenho geral

### XGBoost
- Técnica de boosting gradiente  
- Geralmente superior em dados tabulares  
- Treinamento rápido e eficiente

Cada modelo passou por **RandomizedSearchCV** com validação cruzada **StratifiedKFold (5 folds)**.

---

## 4. Métricas de Avaliação

Os modelos foram avaliados utilizando:

- **Acurácia**  
- **F1-Score**  
- **ROC-AUC**  
- **Matriz de Confusão**  
- **Curva ROC**  
- **Curva Precision–Recall**  
- **Tempo de Treinamento**

Essas métricas permitem compreender não apenas o desempenho geral, mas também o comportamento dos modelos em termos de equilíbrio entre classes, taxa de acertos e capacidade discriminativa.

---

## 5. Visualizações

Foram gerados gráficos comparativos para:

- **Curvas ROC**  
- **Curvas Precision–Recall**

Essas visualizações reforçam as diferenças de desempenho entre os três algoritmos e oferecem uma análise mais intuitiva do comportamento de cada modelo.

---

## 6. Comparação Final dos Modelos

Para facilitar a interpretação, foi criado um DataFrame de comparação contendo:

- Acurácia  
- F1-Score  
- ROC-AUC  
- Tempo de Treinamento  

Essa tabela sintetiza os resultados obtidos e possibilita identificar qual modelo performou melhor no contexto analisado.

---

## 7. Estrutura do Código

O pipeline segue esta estrutura lógica:

1. Importação de bibliotecas  
2. Carregamento do dataset Titanic  
3. Seleção e preparação das features  
4. Tratamento de valores ausentes  
5. Divisão em treino e teste  
6. Normalização e codificação  
7. Configuração dos hiperparâmetros  
8. Otimização e treinamento dos modelos  
9. Avaliação individual  
10. Comparação final entre SVM, Random Forest e XGBoost  

---

## 8. Tecnologias Utilizadas

- **Python**
- **Pandas, Numpy, Seaborn, Matplotlib**
- **Scikit-Learn**
- **XGBoost**
- **RandomizedSearchCV / StratifiedKFold**

---

## 9. Objetivo Principal

Demonstrar, de forma clara e organizada, um pipeline completo de classificação aplicado ao Titanic, permitindo:

- Analisar o desempenho de diferentes modelos  
- Comparar técnicas amplamente usadas na área  
- Interpretar resultados visuais e numéricos  
- Obter insights sobre escolha de algoritmos em cenários reais  

---

## Colaboradores

**Orientador:** Prof. Dr. Fabiano B. Menegidio
  
- [Anny Gabriely Souza do Nascimento](https://www.linkedin.com/in/anny-gabriely-5233b8294)  
- [Antonio Luiz Lins Neto](https://github.com/imLins)  
- [Fábio Yuuki Saruwataru](https://github.com/FabioYS)  
- [Leonardo Valdir Silva](https://github.com/leo-vasi)  
