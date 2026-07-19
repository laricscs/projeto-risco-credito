# Projeto de Predição de Risco de Crédito
![Python](https://img.shields.io/badge/Python-3.12-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen)
![License](https://img.shields.io/badge/License-MIT-green)

# Projeto de Predição de Risco de Crédito

## Objetivo

Este projeto tem como objetivo desenvolver um pipeline completo de Machine Learning para prever a inadimplência de clientes que solicitaram empréstimos.

O desenvolvimento contempla todas as principais etapas de um projeto de Ciência de Dados, incluindo:

- Análise Exploratória dos Dados (EDA);
- Tratamento e preparação dos dados;
- Engenharia de atributos (Feature Engineering);
- Preparação dos dados para modelagem;
- Balanceamento das classes;
- Treinamento e otimização de modelos de Machine Learning;
- Avaliação utilizando métricas estatísticas;
- Interpretação dos resultados sob a perspectiva do negócio.

O projeto foi desenvolvido como atividade avaliativa do módulo de **Machine Learning e Visão Computacional**, aplicando boas práticas de programação, versionamento com Git/GitHub e documentação técnica.

---

# Problema de Negócio

Instituições financeiras analisam diariamente milhares de solicitações de crédito.

Conceder empréstimos para clientes com alta probabilidade de inadimplência pode gerar prejuízos financeiros significativos. Por outro lado, negar crédito para clientes confiáveis representa perda de oportunidades de negócio.

Neste projeto foi desenvolvido um modelo capaz de prever se um cliente será:

- **0 → Adimplente** (pagará corretamente o empréstimo)
- **1 → Inadimplente** (possui risco de não pagamento)

Além da comparação entre modelos de Machine Learning, foi realizada uma análise dos impactos financeiros causados pelos **Falsos Positivos** e **Falsos Negativos**, permitindo recomendar qual algoritmo apresenta melhor custo-benefício para utilização em produção.

---

# Dataset

**Arquivo utilizado**

```
credit_risk_dataset.csv
```

**Download da base**

https://drive.google.com/file/d/1R4WCMc_56lv3fMaDalUBAz5jSxeZOcwI/view

Por questões de boas práticas de versionamento, o arquivo CSV não está incluído neste repositório.

Para reproduzir este projeto:

1. Faça o download do dataset.
2. Coloque o arquivo dentro da pasta `data/`.
3. Execute o notebook principal.

---

# Dicionário de Dados

| Coluna | Descrição |
|---------|-----------|
| person_age | Idade do cliente |
| person_income | Renda anual |
| person_home_ownership | Situação do imóvel (alugado, próprio, financiado etc.) |
| person_emp_length | Tempo de emprego |
| loan_intent | Finalidade do empréstimo |
| loan_grade | Classificação de risco do empréstimo |
| loan_amnt | Valor solicitado |
| loan_int_rate | Taxa de juros (%) |
| loan_status | Variável alvo (0 = Adimplente, 1 = Inadimplente) |
| loan_percent_income | Percentual da renda comprometida com o empréstimo |
| cb_person_default_on_file | Histórico anterior de inadimplência |
| cb_person_cred_hist_length | Tempo de histórico de crédito |

---

# Feature Engineering

Durante a etapa de engenharia de atributos foi criada a variável:

### comprometimento_renda

Calculada por:

```python
(loan_amnt / person_income) * 100
```

# Tecnologias Utilizadas

As principais bibliotecas e ferramentas utilizadas no desenvolvimento do projeto foram:

- Python 3.x
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn (SMOTE)
- Jupyter Notebook
- Git
- GitHub

---

# Estrutura do Projeto

```text
projeto-risco-credito/
│
├── data/
│   └── credit_risk_dataset.csv
│
├── notebooks/
│   └── 01_pipeline_machine_learning.ipynb
│
├── src/
│
├── images/
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

# Como Executar

## 1. Clone este repositório

```bash
git clone https://github.com/laricscs/projeto-risco-credito.git
```

---

## 2. Acesse a pasta do projeto

```bash
cd projeto-risco-credito
```

---

## 3. Crie um ambiente virtual

### Windows

```bash
py -m venv venv
```

### Linux / macOS

```bash
python3 -m venv venv
```

---

## 4. Ative o ambiente virtual

### Windows

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
source venv/bin/activate
```

Após a ativação, o terminal deverá exibir:

```text
(venv)
```

---

## 5. Instale as dependências

```bash
pip install -r requirements.txt
```

---

## 6. Faça o download do dataset

Baixe o arquivo:

```
credit_risk_dataset.csv
```

através do link:

https://drive.google.com/file/d/1R4WCMc_56lv3fMaDalUBAz5jSxeZOcwI/view

Depois mova o arquivo para a pasta:

```text
data/
```

A estrutura deverá ficar:

```text
projeto-risco-credito/
│
├── data/
│   └── credit_risk_dataset.csv
```

---

## 7. Execute o notebook

Abra o Jupyter Notebook ou Visual Studio Code e execute todas as células do notebook localizado em:

```text
notebooks/
```

---

# Pipeline de Machine Learning

O desenvolvimento do projeto seguiu as seguintes etapas:

## 1. Análise Exploratória dos Dados (EDA)

- Estatísticas descritivas
- Distribuição das variáveis
- Identificação de valores ausentes
- Identificação de valores inconsistentes
- Correlação entre variáveis

---

## 2. Pré-processamento

- Tratamento de valores ausentes
- Tratamento de valores inconsistentes
- Criação de novas variáveis
- Encoding das variáveis categóricas

---

## 3. Preparação para Modelagem

- Separação entre treino e teste
- Balanceamento das classes utilizando SMOTE
- Escalonamento dos dados (StandardScaler) para o modelo KNN

---

## 4. Modelagem

Foram treinados dois algoritmos de classificação:

- K-Nearest Neighbors (KNN)
- Árvore de Decisão (Decision Tree)

---

## 5. Otimização dos Hiperparâmetros

### KNN

Foram testados diferentes valores para o parâmetro **K**:

- K = 3
- K = 5
- K = 7
- K = 9

---

### Árvore de Decisão

Foram avaliadas diferentes profundidades máximas da árvore:

- max_depth = 3
- max_depth = 5
- max_depth = 7
- max_depth = None

---

## 6. Diagnóstico de Overfitting

Os modelos foram avaliados comparando o desempenho nas bases de treino e teste para verificar sua capacidade de generalização e identificar possíveis sinais de overfitting.

---

## 7. Avaliação Final

Os modelos foram comparados utilizando as seguintes métricas:

- Accuracy
- Precision
- Recall
- F1-Score
- Classification Report
- Matriz de Confusão

Além das métricas estatísticas, foi realizada uma análise dos impactos financeiros dos erros de classificação (Falsos Positivos e Falsos Negativos) para recomendar o modelo mais adequado ao problema de negócio.

---

Essa variável representa o percentual da renda anual comprometido com o empréstimo solicitado, permitindo fornecer uma nova informação ao modelo para auxiliar na identificação de clientes com maior risco de inadimplência.
---

# Análise Exploratória dos Dados (EDA)

Antes do treinamento dos modelos, foi realizada uma Análise Exploratória dos Dados (Exploratory Data Analysis - EDA) com o objetivo de compreender a estrutura da base, identificar possíveis inconsistências e obter insights que auxiliassem na etapa de modelagem.

Durante essa etapa foram analisadas as distribuições das variáveis, a presença de valores ausentes, valores inconsistentes, correlações entre atributos e o comportamento da variável alvo.

---

## Distribuição da Variável Alvo

A base de dados apresentou desbalanceamento entre as classes, com predominância de clientes adimplentes.

> **Inserir gráfico da distribuição da variável alvo**

```markdown
![Distribuição da variável alvo](images/distribuicao_target.png)
```

---

## Distribuição das Variáveis Numéricas

Foram analisadas as distribuições das principais variáveis numéricas para identificar assimetrias, dispersões e possíveis outliers.

> **Inserir histogramas ou boxplots**

```markdown
![Distribuição das variáveis numéricas](images/variaveis_numericas.png)
```

---

## Distribuição das Variáveis Categóricas

Também foram avaliadas as frequências das variáveis categóricas presentes na base de dados.

> **Inserir gráfico das variáveis categóricas**

```markdown
![Variáveis categóricas](images/variaveis_categoricas.png)
```

---

## Correlação entre Variáveis

Foi construída uma matriz de correlação para identificar relações lineares entre as variáveis numéricas e verificar quais atributos apresentavam maior associação com a variável alvo.

> **Inserir Heatmap**

```markdown
![Mapa de correlação](images/heatmap_correlacao.png)
```

---

## Principais Insights da EDA

Durante a análise exploratória foram identificados os seguintes pontos:

- A base apresentou classes desbalanceadas, com predominância de clientes adimplentes.
- Foram encontrados valores ausentes que precisaram ser tratados antes da modelagem.
- Também foram identificados valores inconsistentes em algumas variáveis, como idade e tempo de emprego.
- A variável `loan_percent_income` apresentou uma das maiores correlações com a inadimplência.
- Clientes com maior comprometimento da renda tendem a apresentar maior probabilidade de inadimplência.

---

# Otimização dos Modelos

Após o pré-processamento dos dados, foram realizados experimentos para encontrar a melhor configuração de hiperparâmetros para cada algoritmo.

---

## K-Nearest Neighbors (KNN)

Foram testados diferentes valores para o parâmetro **K**, comparando o desempenho nas bases de treino e teste.

### Tabela de Resultados

> **Inserir tabela dos resultados do KNN**

### Curva de Validação

> **Inserir gráfico da curva de validação do KNN**

```markdown
![Curva de validação KNN](images/curva_knn.png)
```

**Conclusão**

O melhor desempenho foi obtido com **K = 9**, apresentando maior capacidade de generalização e menor diferença entre as acurácias de treino e teste.

---

## Árvore de Decisão

Foram avaliadas diferentes profundidades máximas da árvore (`max_depth`).

### Tabela de Resultados

> **Inserir tabela dos resultados da Árvore de Decisão**

### Curva de Validação

> **Inserir gráfico da curva de validação da Árvore**

```markdown
![Curva de validação Árvore](images/curva_arvore.png)
```

**Conclusão**

A configuração **max_depth = 5** apresentou o melhor equilíbrio entre desempenho e generalização. Já a árvore sem limite de profundidade apresentou overfitting, atingindo 100% de acurácia na base de treinamento.

---

# Avaliação dos Modelos

Os melhores modelos encontrados foram avaliados utilizando métricas de classificação e matrizes de confusão.

---

## Classification Report

### KNN

> **Inserir o Classification Report do KNN**

```markdown
![Classification Report KNN](images/classification_knn.png)
```

---

### Árvore de Decisão

> **Inserir o Classification Report da Árvore**

```markdown
![Classification Report Árvore](images/classification_tree.png)
```

---

## Matrizes de Confusão

As matrizes de confusão permitem visualizar os acertos e erros de classificação dos modelos.

### KNN

```markdown
![Matriz de Confusão KNN](images/matriz_knn.png)
```

---

### Árvore de Decisão

```markdown
![Matriz de Confusão Árvore](images/matriz_tree.png)
```

---

# Resumo Executivo

Ao longo do projeto foi desenvolvido um pipeline completo de Machine Learning para predição de risco de crédito, desde a análise exploratória dos dados até a avaliação dos modelos sob a perspectiva do negócio.

Os experimentos demonstraram que ambos os algoritmos apresentaram bom desempenho. Entretanto, a **Árvore de Decisão com profundidade máxima igual a 5** apresentou o melhor equilíbrio entre desempenho e capacidade de generalização.

Embora os dois modelos tenham obtido acurácias semelhantes, a Árvore de Decisão apresentou maior **Recall** para a classe de inadimplentes, reduzindo a quantidade de falsos negativos. Esse resultado é especialmente relevante para instituições financeiras, pois diminui o risco de conceder crédito a clientes com maior probabilidade de inadimplência.

Dessa forma, considerando tanto as métricas estatísticas quanto os impactos financeiros associados aos erros de classificação, a **Árvore de Decisão** foi recomendada como modelo mais adequado para aplicação neste problema.

---

# Conclusão

Este projeto permitiu aplicar, na prática, todas as etapas de um pipeline de Machine Learning, desde o entendimento do problema de negócio até a seleção do modelo final.

Além da comparação entre algoritmos, foi possível compreender a importância do tratamento dos dados, da engenharia de atributos, do balanceamento das classes, da otimização de hiperparâmetros e da avaliação utilizando métricas além da acurácia.

A documentação do projeto e a interpretação dos resultados reforçam que a escolha de um modelo deve considerar não apenas seu desempenho estatístico, mas também o impacto que seus erros podem causar no contexto do negócio.

---

# Autor

**Larissa Souza**

Estudante de Engenharia da Computação

Foco em Ciência de Dados, Machine Learning e Visão Computacional.

🔗 GitHub: https://github.com/laricscs
