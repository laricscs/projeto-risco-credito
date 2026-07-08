# Projeto de Predição de Risco de Crédito

## Objetivo

Este projeto tem como objetivo desenvolver um pipeline completo de Machine Learning para prever a inadimplência de clientes que solicitaram empréstimos. O desenvolvimento contempla todas as etapas de um projeto de Ciência de Dados, incluindo Análise Exploratória dos Dados (EDA), tratamento e preparação dos dados, engenharia de atributos, treinamento e otimização de modelos de Machine Learning, avaliação de desempenho e interpretação dos resultados sob a perspectiva do negócio.

O projeto foi desenvolvido como atividade avaliativa do módulo de **Machine Learning e Visão Computacional**, aplicando boas práticas de programação, versionamento com Git/GitHub e documentação técnica.

---

## Problema de Negócio

Instituições financeiras analisam diariamente milhares de solicitações de empréstimo. Tomar decisões corretas durante a concessão de crédito é essencial para reduzir prejuízos financeiros.

Neste projeto, o objetivo é construir um modelo capaz de prever se um cliente irá se tornar inadimplente (`loan_status = 1`) ou se pagará seu empréstimo corretamente (`loan_status = 0`).

Além do desempenho dos modelos, será realizada uma análise dos impactos financeiros causados pelos **Falsos Positivos** e **Falsos Negativos**, permitindo recomendar qual algoritmo apresenta melhor custo-benefício para utilização em produção.

---

## Dataset

**Nome do arquivo:**

`credit_risk_dataset.csv`

**Download da base de dados:**

https://drive.google.com/file/d/1R4WCMc_56lv3fMaDalUBAz5jSxeZOcwI/view

Por questões de organização do repositório e boas práticas de versionamento, o arquivo CSV não está incluído neste projeto.

---

## Dicionário de Dados

| Coluna | Descrição |
|---------|-----------|
| person_age | Idade do cliente |
| person_income | Renda anual do cliente |
| person_home_ownership | Situação do imóvel (alugado, próprio etc.) |
| person_emp_length | Tempo de emprego |
| loan_intent | Finalidade do empréstimo |
| loan_grade | Classificação de risco do empréstimo |
| loan_amnt | Valor solicitado do empréstimo |
| loan_int_rate | Taxa de juros |
| loan_status | Variável alvo (0 = adimplente, 1 = inadimplente) |
| loan_percent_income | Percentual da renda comprometida com o empréstimo |
| cb_person_default_on_file | Histórico anterior de inadimplência |
| cb_person_cred_hist_length | Tempo de histórico de crédito |

### Feature Engineering

Durante o projeto será criada a variável:

**comprometimento_renda**

Calculada da seguinte forma:

```text
(loan_amnt / person_income) * 100
```

Essa variável representa o percentual da renda anual comprometido com o valor solicitado no empréstimo.

---

## Tecnologias Utilizadas

- Python
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

## Estrutura do Projeto

```text
projeto-risco-credito/
│
├── data/
│   └── credit_risk_dataset.csv
│
├── notebooks/
│   └── 01_analise_exploratoria.ipynb
│
├── src/
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

## Como Executar

### 1. Clone o repositório

```bash
git clone https://github.com/laricscs/projeto-risco-credito.git
```

### 2. Entre na pasta do projeto

```bash
cd projeto-risco-credito
```

### 3. Crie um ambiente virtual

No Windows:

```bash
py -m venv venv
```

### 4. Ative o ambiente virtual

No Windows:

```bash
venv\Scripts\activate
```

Após a ativação, o terminal deverá exibir:

```text
(venv)
```

### 5. Instale as dependências

```bash
pip install -r requirements.txt
```

### 6. Faça o download do dataset

Baixe o arquivo **credit_risk_dataset.csv** através do link abaixo:

https://drive.google.com/file/d/1R4WCMc_56lv3fMaDalUBAz5jSxeZOcwI/view

Depois, mova o arquivo para a pasta `data/`, mantendo a seguinte estrutura:

```text
projeto-risco-credito/
│
├── data/
│   └── credit_risk_dataset.csv
```

### 7. Execute o projeto

Abra o Visual Studio Code ou o Jupyter Notebook e execute o notebook localizado na pasta `notebooks/`.

---

## Pipeline de Machine Learning

O projeto será desenvolvido seguindo as etapas abaixo:

1. Análise Exploratória dos Dados (EDA)
2. Tratamento e Limpeza dos Dados
3. Engenharia de Atributos (Feature Engineering)
4. Encoding das variáveis categóricas
5. Separação entre treino e teste
6. Balanceamento das classes utilizando SMOTE
7. Escalonamento dos dados para o modelo KNN
8. Treinamento dos modelos KNN e Árvore de Decisão
9. Otimização dos hiperparâmetros
10. Diagnóstico de Overfitting
11. Avaliação dos modelos
12. Veredito de Negócio

---

## Modelos Utilizados

- K-Nearest Neighbors (KNN)
- Árvore de Decisão (Decision Tree)

---

## Métricas de Avaliação

Os modelos serão avaliados utilizando:

- Accuracy
- Precision
- Recall
- F1-Score
- Classification Report
- Matriz de Confusão

Além das métricas tradicionais, será realizada uma análise dos impactos financeiros dos erros de classificação (Falsos Positivos e Falsos Negativos).

---

## Resultados

Esta seção será atualizada ao final do projeto com:

- Principais insights obtidos durante a EDA;
- Comparação entre os modelos;
- Melhor configuração encontrada;
- Matrizes de confusão;
- Análise dos erros;
- Recomendação do modelo para produção.

---

## Conclusão

Ao término do projeto será apresentado um resumo executivo contendo a recomendação final do modelo mais adequado para auxiliar instituições financeiras na tomada de decisão durante a concessão de crédito, considerando não apenas o desempenho estatístico, mas também os impactos financeiros associados aos erros de classificação.

---

## Autor

**Larissa Souza**

Estudante de Engenharia da Computação com foco em Ciência de Dados, Machine Learning e Visão Computacional.