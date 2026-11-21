# SENAI-2026-2

Trabalhos práticos da **Graduação em Tecnologia de Dados** — Faculdade SENAI / SENAI-MG, semestre **2026/2**.

![Python](https://img.shields.io/badge/Python-3.13-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikitlearn&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-Data-150458?logo=pandas&logoColor=white)

---

## Sumário
- [Informações acadêmicas](#informações-acadêmicas)
- [Disciplinas do semestre](#disciplinas-do-semestre)
- [Estrutura do repositório](#estrutura-do-repositório)
- [TP3 – SENTINEL-AI](#tp3--sentinel-ai)
  - [Contexto de negócio](#contexto-de-negócio)
  - [Dataset](#dataset)
  - [Metodologia](#metodologia)
  - [Resultados](#resultados)
  - [Recomendação para produção](#recomendação-para-produção)
  - [Limitações e próximos passos](#limitações-e-próximos-passos)
- [Como executar](#como-executar)
- [Tecnologias](#tecnologias)

---

## Informações acadêmicas

| Item | Descrição |
|---|---|
| **Instituição** | Faculdade SENAI – SENAI-MG |
| **Curso** | Graduação em Tecnologia de Dados |
| **Semestre** | 2026/2 |
| **Ambiente virtual** | Canvas (senai-mg.instructure.com) + Plataforma A (Grupo A / SAGAH) |
| **Autores** | Mário Cezar Gouveia de Souza e Wellington dos Santos Luzzi |

## Disciplinas do semestre

| Disciplina | Principais conteúdos | Avaliações |
|---|---|---|
| **Aprendizagem de Máquina** | Fundamentos de ML, qualidade e pré-processamento de dados, regressão linear, árvores de decisão, kNN, SVM, Naive Bayes, redes neurais (MLP), k-means, PCA, avaliação de modelos, classificação de textos, linguagem R, DevOps | TP1 a TP4, Prova Intermediária, Prova Final Integrada |
| **Limpeza e Integração de Dados** | Banco de dados e SQL, Python, Git, Big Data, ETL, armazenamento semiestruturado e não estruturado, análise exploratória, valores faltantes, outliers, normalização, discretização, correlações, HTML, web crawlers, JSON, XML, REST, CI/CD | TP1 a TP3, Prova Intermediária, Prova Final Integrada |
| **Gestão de Negócios Baseados em Dados** | Plano de negócios, processo decisório, estratégia e BI, ETL, OLAP, ITIL, BABOK, LGPD, legislação de segurança da informação | Trabalho Prático, Prova Intermediária, Prova Integradora |
| **Governança de Dados** | Governança digital, LGPD, administração de dados e de banco de dados, pré-processamento e qualidade para visualização, COBIT, ética e discriminação algorítmica | Trabalho, Resenha, Prova Intermediária, Prova Integradora |

## Estrutura do repositório

```
SENAI-2026-2/
├── README.md                 # Este arquivo
└── tp3_sentinel_ai.ipynb     # TP3 – Aprendizagem de Máquina: SENTINEL-AI (kNN, SVM, Naive Bayes)
```

| Trabalho | Disciplina | Arquivo | Status |
|---|---|---|---|
| TP3 – Situação de Aprendizagem: SENTINEL-AI | Aprendizagem de Máquina | [`tp3_sentinel_ai.ipynb`](tp3_sentinel_ai.ipynb) | Concluído (prazo: 28/11/2026) |

---

## TP3 – SENTINEL-AI
**Classificação Avançada: Distâncias (kNN), Margens Máximas (SVM) e Probabilidades (Naive Bayes)**

### Contexto de negócio
Uma fintech precisa decidir se uma proposta de crédito representa **Risco Aceitável / Baixo Risco (Classe 0)** ou **Risco Crítico / Inadimplência Potencial (Classe 1)**. Como os custos de erro são **assimétricos** — conceder crédito a um inadimplente gera prejuízo direto, enquanto recusar um bom pagador gera apenas custo de oportunidade —, o sistema **Sentinel-AI** compara três famílias de algoritmos supervisionados e emite um parecer técnico para produção.

| Família | Algoritmo | Ideia central |
|---|---|---|
| Instâncias e distância | k-Nearest Neighbors (kNN) | Votação dos K vizinhos mais próximos (distância euclidiana) |
| Margens máximas | Support Vector Machines (SVM) | Hiperplano de margem máxima, com kernel linear e RBF |
| Probabilidade condicional | Naive Bayes Gaussiano | Teorema de Bayes + independência condicional dos atributos |

### Dataset
- **Fonte:** *Statlog German Credit* — [`GermanCredit.csv`](https://raw.githubusercontent.com/selva86/datasets/master/GermanCredit.csv) (1.000 clientes).
- **Atributos usados:**
  - Numéricos: `Duration` (meses), `Amount` (marcos alemães), `Age` (anos), `InstallmentRatePercentage` (parcela em relação à renda);
  - Categóricos: `savings` (faixas de poupança – ordinal) e `housing` (moradia – nominal).
- **Alvo:** `CreditHistory.Critical` (1 = histórico crítico; 0 = histórico regular) — **29,3%** da Classe 1 (base desbalanceada).

> **Observação técnica:** a versão atual do CSV no link do enunciado traz as colunas em minúsculas (`duration`, `amount`, `age`, `installment_rate`) e o histórico de crédito em uma única coluna categórica (`credit_history`). O notebook mantém o código de ingestão obrigatório, renomeia as colunas para os nomes do enunciado e deriva `CreditHistory.Critical` = 1 quando `credit_history == "critical account/other credits existing"`.

### Metodologia
| Fase | Etapas |
|---|---|
| **1 – Engenharia de atributos** | Ordinal Encoding em `savings` (sem poupança → ≥ 1000 DM); One-Hot Encoding em `housing` com `drop_first=True`; holdout 80/20 com `stratify=y` e `random_state=42`; `StandardScaler` ajustado **somente no treino** (evita *data leakage*) |
| **2 – kNN** | Curva de sensibilidade com K ∈ {1, 3, 5, 7, 9, 11, 15, 21, 25}; escolha do K pelo F1 da Classe 1; matriz de confusão; análise de overfitting (K baixo) x underfitting (K alto) |
| **3 – SVM** | Kernel linear (C = 1,0) x kernel RBF (C = 1,0, `gamma='scale'`); análise do *kernel trick*; matriz de confusão do melhor modelo |
| **4 – Naive Bayes** | GaussianNB; `predict_proba` das 5 primeiras amostras de teste; discussão da premissa "ingênua" em dados financeiros |
| **5 – Benchmark** | Tabela comparativa; análise complementar sensível ao custo (SVM com `class_weight='balanced'` e Naive Bayes com limiar escolhido por validação cruzada estratificada de 5 folds no treino); parecer de negócio |

### Resultados
Métricas na base de teste (200 clientes; Classe 1 = risco crítico):

| Algoritmo | Configuração | Acurácia | Precisão (C1) | Recall (C1) | F1 (C1) |
|---|---|:---:|:---:|:---:|:---:|
| kNN | K = 3 (euclidiana) | 0,620 | 0,351 | 0,339 | 0,345 |
| SVM | RBF, C = 1,0, `gamma='scale'` | 0,705 | 0,500 | 0,017 | 0,033 |
| Naive Bayes | GaussianNB padrão (limiar 0,5) | 0,630 | 0,273 | 0,153 | 0,196 |
| SVM (sensível ao custo) | RBF, `class_weight='balanced'` | 0,520 | 0,330 | 0,610 | 0,429 |
| **Naive Bayes (limiar ajustado)** | **GaussianNB, limiar 0,20 (CV no treino)** | 0,455 | 0,331 | **0,831** | **0,473** |

Principais achados:
- **kNN:** a taxa de erro cai com K maior, mas o Recall da Classe 1 despenca (0,34 com K = 3 → 0,05 com K = 25), porque a classe majoritária passa a dominar a votação.
- **SVM:** o kernel linear classificou todos os clientes como Classe 0 (Recall 0); o RBF melhorou muito pouco. O limite está na **sobreposição das classes** e no **desbalanceamento**, não na forma da fronteira.
- **Naive Bayes:** mesmo violando a independência entre atributos (valor, duração, idade e poupança são correlacionados), é rápido, interpretável e fornece probabilidades que permitem calibrar o limiar de decisão.
- A **acurácia é enganosa** neste problema: prever sempre "baixo risco" já atinge ~70%.

### Recomendação para produção
- **Métrica prioritária:** **Recall da Classe 1**, pois o falso negativo (aprovar um inadimplente) gera perda direta de capital; o F1 acompanha o equilíbrio com a precisão.
- **Entre as configurações exigidas**, o **kNN (K = 3)** foi o melhor (maior Recall e F1 da Classe 1).
- **Modelo recomendado:** **Naive Bayes Gaussiano com limiar 0,20**, que detecta **83%** dos clientes de risco (49 de 59, apenas 10 falsos negativos), com o melhor F1 (0,473).
- Como a precisão é baixa (≈ 0,33), os clientes sinalizados devem ir para **análise manual ou exigência de garantias**, e não para recusa automática.

### Limitações e próximos passos
- Poucos atributos (7) e base pequena (1.000 clientes, 200 no teste).
- Incluir mais variáveis (status da conta, emprego, propósito do crédito, outros créditos).
- Usar validação cruzada para todos os hiperparâmetros e validar o limiar em dados mais recentes.
- Monitorar o modelo em produção (*data drift*).
- Garantir explicabilidade e revisão humana de decisões automatizadas (LGPD, art. 20).

---

## Como executar

```bash
# 1. Clonar o repositório
git clone https://github.com/mariocezarsouza/SENAI-2026-2.git
cd SENAI-2026-2

# 2. Instalar as dependências
pip install pandas numpy scikit-learn matplotlib jupyter

# 3. Abrir o notebook
jupyter notebook tp3_sentinel_ai.ipynb
```

O dataset é baixado automaticamente da URL pública no início do notebook (é necessário acesso à internet). Também é possível abrir o notebook no **Google Colab** ou no **VS Code**.

## Tecnologias
- **Python 3** e **Jupyter Notebook**
- **pandas** e **NumPy** — manipulação e engenharia de atributos
- **scikit-learn** — `KNeighborsClassifier`, `SVC`, `GaussianNB`, `StandardScaler`, `OrdinalEncoder`, `train_test_split`, `StratifiedKFold`, `cross_val_predict`, métricas
- **Matplotlib** — curvas de sensibilidade, matrizes de confusão e gráficos comparativos

---

<sub>Trabalhos acadêmicos desenvolvidos para fins de estudo — Graduação em Tecnologia de Dados, Faculdade SENAI / SENAI-MG, 2026/2.</sub>
