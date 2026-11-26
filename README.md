# SENAI-2026-2

Trabalhos práticos da **Graduação em Tecnologia de Dados** — **Faculdade SENAI Centro 4.0** (SENAI-MG), turma **3º PTCD**, semestre **2026/2**.

![Python](https://img.shields.io/badge/Python-3-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-Data-150458?logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikitlearn&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-DB-003B57?logo=sqlite&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-API-009688?logo=fastapi&logoColor=white)

> **Status:** todos os trabalhos práticos das disciplinas **Limpeza e Integração de Dados (TP1 a TP3)** e **Aprendizagem de Máquina (TP2 a TP4)** estão concluídos e entregues.

---

## Sumário
- [Informações acadêmicas](#informações-acadêmicas)
- [Disciplinas do semestre](#disciplinas-do-semestre)
- [Estrutura do repositório](#estrutura-do-repositório)
- [Limpeza e Integração de Dados](#limpeza-e-integração-de-dados)
  - [TP1 – Data Ingestion & Profiling Engine](#tp1--data-ingestion--profiling-engine)
  - [TP2 – Pipeline Inteligente de Higienização de Crédito](#tp2--pipeline-inteligente-de-higienização-de-crédito)
  - [TP3 – Automated Web Crawler & ML-Ready Data Preparation Hub](#tp3--automated-web-crawler--ml-ready-data-preparation-hub)
- [Aprendizagem de Máquina](#aprendizagem-de-máquina)
  - [TP2 – Predição para Imobiliárias](#tp2--predição-para-imobiliárias)
  - [TP3 – SENTINEL-AI](#tp3--sentinel-ai)
  - [TP4 – Customer-Persona Clustering](#tp4--customer-persona-clustering)
- [Como executar](#como-executar)
- [Tecnologias](#tecnologias)

---

## Informações acadêmicas

| Item | Descrição |
|---|---|
| **Instituição** | Faculdade SENAI Centro 4.0 – SENAI-MG |
| **Curso** | Graduação em Tecnologia de Dados |
| **Turma** | 3º PTCD |
| **Semestre** | 2026/2 |
| **Ambiente virtual** | Canvas (senai-mg.instructure.com) + Plataforma A (Grupo A / SAGAH) |
| **Autor** | Mário Cezar Gouveia de Souza |
| **Colaboradores (duplas)** | Wellington dos Santos Luzzi e Marcos Júnio dos Santos |

## Disciplinas do semestre

| Disciplina | Principais conteúdos | Avaliações |
|---|---|---|
| **Limpeza e Integração de Dados** | Banco de dados e SQL, Python, Git, Big Data, ETL, armazenamento semiestruturado e não estruturado, análise exploratória, valores faltantes, outliers, normalização, discretização, correlações, HTML, web crawlers, JSON, XML, REST, CI/CD | TP1 a TP3, Prova Intermediária, Prova Final Integrada |
| **Aprendizagem de Máquina** | Fundamentos de ML, qualidade e pré-processamento de dados, regressão linear, árvores de decisão, kNN, SVM, Naive Bayes, redes neurais (MLP), k-means, PCA, avaliação de modelos, classificação de textos, linguagem R, DevOps | TP1 a TP4, Prova Intermediária, Prova Final Integrada |
| **Gestão de Negócios Baseados em Dados** | Plano de negócios, processo decisório, estratégia e BI, ETL, OLAP, ITIL, BABOK, LGPD, legislação de segurança da informação | Trabalho Prático, Prova Intermediária, Prova Integradora |
| **Governança de Dados** | Governança digital, LGPD, administração de dados e de banco de dados, pré-processamento e qualidade para visualização, COBIT, ética e discriminação algorítmica | Trabalho, Resenha, Prova Intermediária, Prova Integradora |

## Estrutura do repositório

```
SENAI-2026-2/
├── README.md
│
│   # Limpeza e Integração de Dados (LID)
├── TP1_Data_Ingestion_Profiling_Engine-main.zip                       # TP1: ETL omnicanal com SQLite e profiling
├── TP2 - Higienizacao de Credito.zip                                  # TP2: higienização de base de crédito (Model-Ready)
├── TP3 - Automated Web Crawler & ML-Ready Data Preparation Hub.zip    # TP3: entrega final (BookScrape ETL & ML Pipeline)
├── Entregáveis_TP3_limpeza_e_integração.zip                           # TP3: mesma entrega final (cópia com outro nome)
├── TP3_Crawler_ML.zip                                                 # TP3: versões Books to Scrape e Estante Virtual
│
│   # Aprendizagem de Máquina (AM)
├── TP2 - Situação de Aprendizagem Predição para Imobiliárias.zip      # TP2: regressão linear e árvore de decisão
├── tp3_sentinel_ai.ipynb                                              # TP3: SENTINEL-AI (kNN, SVM, Naive Bayes)
└── tp4_customer_clustering.ipynb                                      # TP4: Customer-Persona Clustering (k-Means e PCA)
```

| Trabalho | Disciplina | Arquivo | Autores | Principais técnicas |
|---|---|---|---|---|
| TP1 – Data Ingestion & Profiling Engine | LID | [`TP1_Data_Ingestion_Profiling_Engine-main.zip`](TP1_Data_Ingestion_Profiling_Engine-main.zip) | Mário Cezar e Wellington Luzzi | ETL, SQLite, Pandas, profiling, Seaborn |
| TP2 – Pipeline Inteligente de Higienização de Crédito | LID | [`TP2 - Higienizacao de Credito.zip`](<TP2 - Higienizacao de Credito.zip>) | Mário Cezar Gouveia de Souza | Nulos, regras de domínio, IQR/capping, KNNImputer, binning, correlação, encoding, Z-Score |
| TP3 – Automated Web Crawler & ML-Ready Data Preparation Hub | LID | [`TP3 - Automated Web Crawler & ML-Ready Data Preparation Hub.zip`](<TP3 - Automated Web Crawler & ML-Ready Data Preparation Hub.zip>) e [`TP3_Crawler_ML.zip`](TP3_Crawler_ML.zip) | Mário Cezar Gouveia de Souza | Web crawling, BeautifulSoup, limpeza, escalonamento, binning, API REST (FastAPI) |
| TP2 – Predição para Imobiliárias | AM | [`TP2 - Situação de Aprendizagem Predição para Imobiliárias.zip`](<TP2 - Situação de Aprendizagem Predição para Imobiliárias.zip>) | Mário Cezar e Wellington Luzzi | Regressão linear múltipla, árvore de decisão, overfitting |
| TP3 – SENTINEL-AI | AM | [`tp3_sentinel_ai.ipynb`](tp3_sentinel_ai.ipynb) | Mário Cezar e Marcos Júnio dos Santos | kNN, SVM, Naive Bayes, matriz de confusão, custo assimétrico |
| TP4 – Customer-Persona Clustering | AM | [`tp4_customer_clustering.ipynb`](tp4_customer_clustering.ipynb) | Mário Cezar e Marcos Júnio dos Santos | StandardScaler, Método do Cotovelo, k-Means, PCA, personas |

---

## Limpeza e Integração de Dados

### TP1 – Data Ingestion & Profiling Engine
**Pipeline automatizado (ETL) de carga, limpeza e integração de dados de vendas omnicanais** (e-commerce e loja física) com Python, SQLite, Pandas, Seaborn e Matplotlib.

| Fase | O que faz |
|---|---|
| **1 – Banco de dados local** | Cria o banco SQLite `varejo.db` com tabela DDL e chave primária `id_transacao` |
| **2 – ETL em Python** (`src/ingestion_pipeline.py`) | Ingestão de `vendas_web.json` (e-commerce) e `vendas_lojas.csv` (lojas físicas); padronização de schemas; tratamento de nulos e vazios; remoção de quantidades ≤ 0; normalização de datas para `YYYY-MM-DD`; carga limpa no SQLite |
| **3 – Análise e profiling** (`notebooks/analise_vendas.ipynb`) | Exporta `vendas_ecommerce_limpo.json` (somente e-commerce); calcula faturamento total, preço unitário médio e faturamento por canal; gera o histograma `histograma_vendas.png` |

### TP2 – Pipeline Inteligente de Higienização de Crédito
**FinCredit Analytics:** transforma a base histórica corrompida `clientes_credito_bruto.csv` (**2.500 clientes, 8 colunas**) em um dataset *Model-Ready* (`clientes_credito_higienizado.csv`), com notebook reprodutível, figuras e relatório técnico (DOCX e PDF).

| Fase | Etapas e resultados |
|---|---|
| **1 – Diagnóstico de nulos** | Nulos em idade (4%), renda (6%), tempo de emprego, estado civil e escolaridade (5% cada); 567 linhas com algum nulo. Lacunas dispersas (padrão MCAR/MAR) → **imputar** é melhor que descartar (~25% da base seria perdida) |
| **2 – Regras de domínio e outliers** | **15 registros descartados** com idade impossível (< 0 ou > 120 anos). **Capping de Tukey (IQR)** em renda (61 outliers, com valores-sentinela como 999.999.999), dívida (81) e tempo de emprego (98), sem perder clientes: a média da renda caiu de ~R$ 821 mil para **~R$ 5,7 mil** |
| **Imputação** | **Moda** para estado civil (Casado) e escolaridade (Médio); **mediana** para idade (38,3) e tempo de emprego (3,2); **KNNImputer (k = 5)** para a renda (149 valores), com erro médio 25% menor que a mediana (MAE R$ 1.411 × R$ 1.890) |
| **3 – Engenharia de features** | Discretização da idade em **Jovem (18–29), Adulto (30–59) e Sênior (60+)**; correlação de Pearson: **renda × dívida r ≈ 0,75**, relação que estava oculta na base bruta (r ≈ 0,01) pelos outliers; nenhum par com multicolinearidade severa (\|r\| > 0,85); escolaridade ordinal, estado civil one-hot (`drop_first`) e **Z-Score** (`StandardScaler`) nas contínuas |
| **4 – Validação e exportação** | Checagens finais e exportação da base *Model-Ready* (2.485 registros) e de `metricas_pipeline.json` |

Figuras geradas: mapa de nulos, boxplots antes/depois do capping, heatmap de correlação, correlação antes × depois e efeito do escalonamento.

### TP3 – Automated Web Crawler & ML-Ready Data Preparation Hub
**Robô de coleta (web crawler) + pipeline de higienização que transforma dados brutos da web em uma base pronta para machine learning**, com exportação em CSV/JSON e API REST.

| Versão | Site alvo | Registros finais | Destaques |
|---|---|:---:|---|
| **Entrega final** – `TP3 - Automated Web Crawler & ML-Ready Data Preparation Hub.zip` (igual a `Entregáveis_TP3_limpeza_e_integração.zip`) | [Books to Scrape](https://books.toscrape.com/) – categorias **Horror, Thriller e Science Fiction** | 44 livros × 13 colunas | *BookScrape ETL & ML Pipeline*: seletores, preço GBP → BRL, z-score e min-max, binning (faixa de preço e popularidade), histogramas, heatmap, boxplot e relatório em PDF |
| `TP3_Crawler_ML/` (em `TP3_Crawler_ML.zip`) | Books to Scrape – catálogo completo (1.000 livros, 50 páginas) | 200 livros × 31 colunas | Paginação, página de detalhe, amostragem sistemática (1 a cada 5), repetição em erros 429/5xx, *timeout* e pausa entre requisições |
| `TP3_Crawler_ML_EstanteVirtual/` (em `TP3_Crawler_ML.zip`) | [Estante Virtual](https://www.estantevirtual.com.br/) | 264 livros × 26 colunas | Dados reais do mercado brasileiro, baixo volume (3 s de pausa), parada imediata em caso de bloqueio, transformação log |

| Fase | Etapas |
|---|---|
| **Inspeção do HTML** | Mapeamento dos seletores (card, título, preço, avaliação, estoque, paginação), com prints anotados |
| **1 – Coleta automatizada** | `requests` + `BeautifulSoup4`, `Session` com `User-Agent`, pausa entre requisições, dado bruto em `dados_brutos_web.json` |
| **2 – Higienização (Model-Ready)** | Limpeza de strings e *parsing* de tipos, valores faltantes, `StandardScaler`, `MinMaxScaler`, discretização (*binning*) |
| **3 – Exportação e integração** | `dados_modelo_pronto.csv/.json`; **API REST** com FastAPI (`GET /dados` com paginação e filtro) |
| **4 – Análises gráficas** | Histogramas antes/depois do escalonamento, correlação de Pearson e boxplot por categoria |

Conclusões da entrega final: o escalonamento não distorce a distribuição (correlação 1,00 entre preço original, z-score e min-max); preço e avaliação não têm correlação; **Horror** tem o maior preço mediano (R$ 264,34), seguido de **Science Fiction** (R$ 252,50).

---

## Aprendizagem de Máquina

### TP2 – Predição para Imobiliárias
**Motor de precificação e previsão de venda rápida para uma PropTech**, com **1.000 imóveis de São Paulo** (`imoveis_saopaulo.csv`).

- **Regressão linear múltipla** (preço): **R² = 0,933** e **RMSE ≈ R$ 47.620** (~7,4% do preço médio de R$ 643 mil). Maior impacto: **quartos** (+R$ 34,2 mil cada); cada km do centro reduz ~R$ 6,3 mil.
- **Árvore de decisão** (venda em até 30 dias, 24,4% de vendas rápidas): diagnóstico de overfitting por `max_depth`.

| `max_depth` | F1 treino | F1 teste | Gap |
|:---:|:---:|:---:|:---:|
| **1** | 0,548 | **0,465** | **0,08** |
| 3 | 0,566 | 0,381 | 0,19 |
| 5 | 0,629 | 0,418 | 0,21 |
| 10 | 0,899 | 0,323 | 0,58 |
| None | 0,997 | 0,356 | 0,64 |

**Veredito:** `max_depth = 1` (regra única: **área ≤ 66,5 m²** → imóveis menores vendem mais rápido).

### TP3 – SENTINEL-AI
**Classificação Avançada: Distâncias (kNN), Margens Máximas (SVM) e Probabilidades (Naive Bayes)** para decidir se uma proposta de crédito de uma fintech é **Baixo Risco (Classe 0)** ou **Risco Crítico (Classe 1)**, com custos de erro assimétricos.

- **Dataset:** *Statlog German Credit* (1.000 clientes); atributos `Duration`, `Amount`, `Age`, `InstallmentRatePercentage`, `savings` (ordinal) e `housing` (one-hot); alvo `CreditHistory.Critical` (29,3% da Classe 1).
- **Pipeline:** holdout 80/20 estratificado, `StandardScaler` ajustado só no treino, curva de K do kNN, SVM linear × RBF, GaussianNB com `predict_proba`, benchmark e análise sensível ao custo.

| Algoritmo | Configuração | Acurácia | Precisão (C1) | Recall (C1) | F1 (C1) |
|---|---|:---:|:---:|:---:|:---:|
| kNN | K = 3 (euclidiana) | 0,620 | 0,351 | 0,339 | 0,345 |
| SVM | RBF, C = 1,0, `gamma='scale'` | 0,705 | 0,500 | 0,017 | 0,033 |
| Naive Bayes | GaussianNB padrão (limiar 0,5) | 0,630 | 0,273 | 0,153 | 0,196 |
| SVM (sensível ao custo) | RBF, `class_weight='balanced'` | 0,520 | 0,330 | 0,610 | 0,429 |
| **Naive Bayes (limiar ajustado)** | **GaussianNB, limiar 0,20 (CV no treino)** | 0,455 | 0,331 | **0,831** | **0,473** |

**Recomendação:** priorizar o **Recall da Classe 1** (o falso negativo gera perda direta de capital). Entre as configurações exigidas, o **kNN (K = 3)** foi o melhor; para produção, recomenda-se o **Naive Bayes com limiar 0,20**, que detecta **83%** dos clientes de risco, encaminhando os casos sinalizados para análise manual.

### TP4 – Customer-Persona Clustering
**Segmentação não supervisionada de clientes** para identificar os grupos naturais de consumo e orientar ações de marketing, sem rótulos prévios.

| Fase | Etapas e resultados |
|---|---|
| **1 – Padronização** | `StandardScaler` em `Duration`, `Amount`, `Age` e `InstallmentRatePercentage` (1.000 clientes do German Credit), evitando que `Amount` domine a distância euclidiana |
| **2 – Cotovelo e k-Means** | Inércia para K = 1 a 8 (`random_state=42`, `n_init=10`); as quedas são de 28%, 25% e 21% até K = 4 e de apenas 13%, 10%… depois → **K = 4** (silhueta 0,322 contra 0,316 com K = 3) |
| **3 – PCA e personas** | PCA com 2 componentes preserva **68,3%** da variância: Componente 1 = porte do financiamento (duração e valor); Componente 2 = peso da parcela e idade |

| Cluster | Clientes | Persona | Características marcantes |
|:---:|:---:|---|---|
| 0 | 252 (25%) | **Jovens de parcela leve** | ~31 anos, prazo curto, menor peso da parcela na renda (−47% vs. média) |
| 1 | 171 (17%) | **Maduros e conservadores** | ~54 anos, créditos pequenos (~2,2 mil) e curtos |
| 2 | 419 (42%) | **Jovens comprometidos** | Maior grupo; valores baixos, mas a parcela mais pesada em relação à renda |
| 3 | 158 (16%) | **Alto valor / longo prazo** | ~41 meses (+94%) e ~8,2 mil (+151% vs. média) |

> **Observação técnica (TP3 e TP4 de AM):** a versão atual do `GermanCredit.csv` no link dos enunciados usa nomes de colunas em minúsculas (`duration`, `amount`, `age`, `installment_rate`, `credit_history`). Os notebooks mantêm o código de ingestão obrigatório e compatibilizam os nomes. No TP4, isso evita que o *fallback* do enunciado gere silenciosamente uma base sintética no lugar dos dados reais.

---

## Como executar

```bash
# 1. Clonar o repositório
git clone https://github.com/mariocezarsouza/SENAI-2026-2.git
cd SENAI-2026-2

# 2. Extrair os trabalhos compactados (Windows: botão direito > Extrair tudo)
unzip "*.zip"

# 3. Instalar as dependências
pip install pandas numpy scikit-learn matplotlib seaborn jupyter requests beautifulsoup4 fastapi uvicorn httpx

# 4. Abrir os notebooks
jupyter notebook
```

| Trabalho | Como rodar |
|---|---|
| LID – TP1 | `python src/ingestion_pipeline.py` e depois `notebooks/analise_vendas.ipynb` |
| LID – TP2 | `pipeline_higienizacao.ipynb` (lê `clientes_credito_bruto.csv` da mesma pasta) |
| LID – TP3 | `pipeline_crawler_preparacao.ipynb`; API: `uvicorn api_dados:app --port 8000` |
| AM – TP2 | `tp2_real_estate.ipynb` (com `imoveis_saopaulo.csv` na mesma pasta) |
| AM – TP3 | `tp3_sentinel_ai.ipynb` (o dataset é baixado da internet) |
| AM – TP4 | `tp4_customer_clustering.ipynb` (o dataset é baixado da internet) |

## Tecnologias
- **Linguagem e ambiente:** Python 3, Jupyter Notebook, Google Colab
- **Dados:** pandas, NumPy, SQLite3
- **Coleta web:** requests, BeautifulSoup4
- **Machine learning:** scikit-learn — `LinearRegression`, `DecisionTreeClassifier`, `KNeighborsClassifier`, `SVC`, `GaussianNB`, `KMeans`, `PCA`, `KNNImputer`, `StandardScaler`, `MinMaxScaler`, `OrdinalEncoder`, validação cruzada e métricas
- **Visualização:** Matplotlib, Seaborn
- **API:** FastAPI, Uvicorn

---

<sub>Trabalhos acadêmicos desenvolvidos para fins de estudo — Graduação em Tecnologia de Dados, Faculdade SENAI Centro 4.0 / SENAI-MG, 2026/2.</sub>
