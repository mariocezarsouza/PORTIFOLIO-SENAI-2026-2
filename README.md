# SENAI-2026-2

Trabalhos práticos da **Graduação em Tecnologia de Dados** — **Faculdade SENAI Centro 4.0** (SENAI-MG), turma **3º PTCD**, semestre **2026/2**.

![Python](https://img.shields.io/badge/Python-3-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-Data-150458?logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikitlearn&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-DB-003B57?logo=sqlite&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-API-009688?logo=fastapi&logoColor=white)

---

## Sumário
- [Informações acadêmicas](#informações-acadêmicas)
- [Disciplinas do semestre](#disciplinas-do-semestre)
- [Estrutura do repositório](#estrutura-do-repositório)
- [Limpeza e Integração de Dados](#limpeza-e-integração-de-dados)
  - [TP1 – Data Ingestion & Profiling Engine](#tp1--data-ingestion--profiling-engine)
  - [TP3 – Automated Web Crawler & ML-Ready Data Preparation Hub](#tp3--automated-web-crawler--ml-ready-data-preparation-hub)
- [Aprendizagem de Máquina](#aprendizagem-de-máquina)
  - [TP2 – Predição para Imobiliárias](#tp2--predição-para-imobiliárias)
  - [TP3 – SENTINEL-AI](#tp3--sentinel-ai)
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
| **Autores** | Mário Cezar Gouveia de Souza e Wellington dos Santos Luzzi |

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
├── TP1_Data_Ingestion_Profiling_Engine-main.zip                   # LID – TP1: ETL omnicanal com SQLite e profiling
├── TP2 - Situação de Aprendizagem Predição para Imobiliárias.zip  # AM – TP2: regressão linear e árvore de decisão
├── TP3_Crawler_ML.zip                                             # LID – TP3: crawlers Books to Scrape e Estante Virtual
├── Entregáveis_TP3_limpeza_e_integração.zip                       # LID – TP3: BookScrape ETL & ML Pipeline (entrega)
└── tp3_sentinel_ai.ipynb                                          # AM – TP3: SENTINEL-AI (kNN, SVM, Naive Bayes)
```

| Trabalho | Disciplina | Arquivo | Principais técnicas |
|---|---|---|---|
| TP1 – Data Ingestion & Profiling Engine | Limpeza e Integração de Dados | [`TP1_Data_Ingestion_Profiling_Engine-main.zip`](TP1_Data_Ingestion_Profiling_Engine-main.zip) | ETL, SQLite, Pandas, profiling, Seaborn |
| TP2 – Predição para Imobiliárias | Aprendizagem de Máquina | [`TP2 - Situação de Aprendizagem Predição para Imobiliárias.zip`](<TP2 - Situação de Aprendizagem Predição para Imobiliárias.zip>) | Regressão linear múltipla, árvore de decisão, overfitting |
| TP3 – Automated Web Crawler & ML-Ready Data Preparation Hub | Limpeza e Integração de Dados | [`TP3_Crawler_ML.zip`](TP3_Crawler_ML.zip) e [`Entregáveis_TP3_limpeza_e_integração.zip`](<Entregáveis_TP3_limpeza_e_integração.zip>) | Web crawling, BeautifulSoup, limpeza, escalonamento, binning, API REST (FastAPI) |
| TP3 – SENTINEL-AI | Aprendizagem de Máquina | [`tp3_sentinel_ai.ipynb`](tp3_sentinel_ai.ipynb) | kNN, SVM, Naive Bayes, matriz de confusão, custo assimétrico |

---

## Limpeza e Integração de Dados

### TP1 – Data Ingestion & Profiling Engine
**Pipeline automatizado (ETL) de carga, limpeza e integração de dados de vendas omnicanais** (e-commerce e loja física) com Python, SQLite, Pandas, Seaborn e Matplotlib.

| Fase | O que faz |
|---|---|
| **1 – Banco de dados local** | Cria o banco SQLite `varejo.db` com tabela DDL e chave primária `id_transacao` |
| **2 – ETL em Python** (`src/ingestion_pipeline.py`) | Ingestão de `vendas_web.json` (e-commerce) e `vendas_lojas.csv` (lojas físicas); padronização de schemas; tratamento de nulos e vazios; remoção de quantidades ≤ 0; normalização de datas para `YYYY-MM-DD`; carga limpa no SQLite |
| **3 – Análise e profiling** (`notebooks/analise_vendas.ipynb`) | Exporta `vendas_ecommerce_limpo.json` (somente e-commerce); calcula faturamento total, preço unitário médio e faturamento por canal; gera o histograma `histograma_vendas.png` |

```
TP1_Data_Ingestion_Profiling_Engine-main/
├── data/              # vendas_web.json, vendas_lojas.csv, vendas_ecommerce_limpo.json
├── src/               # ingestion_pipeline.py
├── notebooks/         # analise_vendas.ipynb
├── varejo.db          # banco SQLite
├── histograma_vendas.png
└── README.md
```

### TP3 – Automated Web Crawler & ML-Ready Data Preparation Hub
**Robô de coleta (web crawler) + pipeline de higienização que transforma dados brutos da web em uma base pronta para machine learning**, com exportação em CSV/JSON e disponibilização via API REST.

O repositório traz três versões do trabalho:

| Versão | Site alvo | Registros finais | Destaques |
|---|---|:---:|---|
| `TP3_Crawler_ML/` (`TP3_Crawler_ML.zip`) | [Books to Scrape](https://books.toscrape.com/) – catálogo de 1.000 livros em 50 páginas | 200 livros × 31 colunas | Crawler com paginação (`li.next a`), página de detalhe, amostragem sistemática (1 a cada 5 livros), repetição em erros 429/5xx, *timeout* e pausa entre requisições |
| `TP3_Crawler_ML_EstanteVirtual/` (`TP3_Crawler_ML.zip`) | [Estante Virtual](https://www.estantevirtual.com.br/) – marketplace brasileiro de livros novos e usados | 264 livros × 26 colunas | Dados reais do mercado brasileiro (preços `R$`), baixo volume (1 requisição por tema, 3 s de pausa), parada imediata em caso de bloqueio, sem técnicas de contorno |
| `Entregáveis_TP3_limpeza_e_integração.zip` | Books to Scrape – categorias **Horror, Thriller e Science Fiction** | 44 livros × 13 colunas | *BookScrape ETL & ML Pipeline*: mapeamento de seletores, conversão de preço (GBP → BRL), z-score e min-max, binning em faixa de preço e nível de popularidade, histogramas, heatmap e boxplot por categoria |

**Fases do pipeline:**

| Fase | Etapas |
|---|---|
| **Inspeção do HTML** | Mapeamento dos seletores (card `article.product_pod` / `.product-item`, título, preço, avaliação, estoque, paginação), com prints anotados em `prints/` |
| **1 – Coleta automatizada** | `requests` + `BeautifulSoup4`, `Session` com `User-Agent` de navegador, respeito ao site (pausa entre requisições), dado bruto preservado em `dados_brutos_web.json` |
| **2 – Higienização (Model-Ready)** | Limpeza de strings e *parsing* de tipos (preço, nota em estrelas → número, estoque), tratamento de valores faltantes (com indicadores de ausência), padronização (`StandardScaler`) e normalização (`MinMaxScaler`), transformação log, discretização (*binning*) |
| **3 – Exportação e integração** | `dados_modelo_pronto.csv` e `dados_modelo_pronto.json`; **API REST** com FastAPI (`api_dados.py`): `GET /`, `GET /dados` com paginação (`limit`, `offset`) e filtro por faixa de preço, documentação em `/docs` |
| **4 – Análises gráficas** | Histogramas antes/depois do escalonamento, matriz de correlação de Pearson e boxplot de preços por categoria |
| **Relatório** | `relatorio_tp3_crawler_ml.pdf` com a documentação completa |

Principais conclusões da entrega (Horror, Thriller e Science Fiction):
- O escalonamento **não distorce** a distribuição: correlação de 1,00 entre o preço original, o z-score e o min-max.
- A correlação entre **preço e avaliação é próxima de zero**: livros mais caros não recebem notas melhores.
- **Horror** tem o maior preço mediano (R$ 264,34), seguido de **Science Fiction** (R$ 252,50); **Thriller** tem a menor mediana.

Para subir a API (dentro da pasta da versão):
```bash
pip install -r requirements.txt
uvicorn api_dados:app --port 8000   # depois acesse http://localhost:8000/docs
```

---

## Aprendizagem de Máquina

### TP2 – Predição para Imobiliárias
**Motor de precificação e previsão de venda rápida para uma PropTech**, usando uma base de **1.000 imóveis de São Paulo** (`imoveis_saopaulo.csv`: área, quartos, banheiros, idade do imóvel, distância do centro, preço de venda e venda em até 30 dias).

| Fase | Etapas |
|---|---|
| **1 – Dados** | Carga do CSV, análise exploratória, descarte do identificador, divisão treino/teste 80/20 com `random_state=42` (estratificada para a classificação) |
| **2 – Regressão linear múltipla** | Previsão de `preco_venda_reais`; coeficientes, intercepto, métricas e gráfico real × predito |
| **3 – Árvore de decisão** | Classificação de `venda_rapida_30_dias` (classe desbalanceada: 24,4% de vendas rápidas); acurácia, precisão, recall e F1 |
| **4 – Otimização de `max_depth`** | Comparação de árvores com profundidade 1, 3, 5, 10 e livre para diagnosticar overfitting |

**Resultados da regressão:** **R² = 0,933** no teste (93,3% da variação do preço explicada) e **RMSE ≈ R$ 47.620**, cerca de 7,4% do preço médio (R$ 643 mil).

| Atributo | Coeficiente | Interpretação |
|---|---:|---|
| `quartos` | +R$ 34.184,44 | Maior impacto individual: cada quarto adicional agrega ~R$ 34,2 mil |
| `banheiros` | +R$ 6.328,75 | Cada banheiro adicional agrega ~R$ 6,3 mil |
| `distancia_centro_km` | −R$ 6.263,73 | Cada km de distância do centro reduz ~R$ 6,3 mil |
| `area_m2` | +R$ 5.912,49 | Cada m² adicional agrega ~R$ 5,9 mil |
| `idade_imovel_anos` | −R$ 2.153,92 | Cada ano de construção reduz ~R$ 2,2 mil |

**Árvore de decisão – diagnóstico de overfitting:**

| `max_depth` | F1 treino | F1 teste | Gap |
|:---:|:---:|:---:|:---:|
| **1** | 0,548 | **0,465** | **0,08** |
| 3 | 0,566 | 0,381 | 0,19 |
| 5 | 0,629 | 0,418 | 0,21 |
| 10 | 0,899 | 0,323 | 0,58 |
| None | 0,997 | 0,356 | 0,64 |

**Veredito:** `max_depth = 1` é o ideal para produção — maior F1 de teste e menor gap. A árvore usa uma única regra (**área ≤ 66,5 m²**): imóveis menores tendem a vender mais rápido, pelo menor ticket de entrada. Árvores mais profundas decoram ruído do treino.

### TP3 – SENTINEL-AI
**Classificação Avançada: Distâncias (kNN), Margens Máximas (SVM) e Probabilidades (Naive Bayes)**

#### Contexto de negócio
Uma fintech precisa decidir se uma proposta de crédito representa **Risco Aceitável / Baixo Risco (Classe 0)** ou **Risco Crítico / Inadimplência Potencial (Classe 1)**. Como os custos de erro são **assimétricos** — conceder crédito a um inadimplente gera prejuízo direto, enquanto recusar um bom pagador gera apenas custo de oportunidade —, o sistema **Sentinel-AI** compara três famílias de algoritmos supervisionados e emite um parecer técnico para produção.

| Família | Algoritmo | Ideia central |
|---|---|---|
| Instâncias e distância | k-Nearest Neighbors (kNN) | Votação dos K vizinhos mais próximos (distância euclidiana) |
| Margens máximas | Support Vector Machines (SVM) | Hiperplano de margem máxima, com kernel linear e RBF |
| Probabilidade condicional | Naive Bayes Gaussiano | Teorema de Bayes + independência condicional dos atributos |

#### Dataset
- **Fonte:** *Statlog German Credit* — [`GermanCredit.csv`](https://raw.githubusercontent.com/selva86/datasets/master/GermanCredit.csv) (1.000 clientes).
- **Atributos:** `Duration`, `Amount`, `Age`, `InstallmentRatePercentage` (numéricos), `savings` (ordinal) e `housing` (nominal).
- **Alvo:** `CreditHistory.Critical` (1 = histórico crítico; 0 = regular) — **29,3%** da Classe 1 (base desbalanceada).

> **Observação técnica:** a versão atual do CSV no link do enunciado traz as colunas em minúsculas e o histórico de crédito em uma única coluna categórica (`credit_history`). O notebook mantém o código de ingestão obrigatório, renomeia as colunas e deriva `CreditHistory.Critical` = 1 quando `credit_history == "critical account/other credits existing"`.

#### Metodologia
| Fase | Etapas |
|---|---|
| **1 – Engenharia de atributos** | Ordinal Encoding em `savings`; One-Hot Encoding em `housing` (`drop_first=True`); holdout 80/20 com `stratify=y` e `random_state=42`; `StandardScaler` ajustado **somente no treino** |
| **2 – kNN** | Curva de sensibilidade com K ∈ {1, 3, 5, 7, 9, 11, 15, 21, 25}; escolha do K pelo F1 da Classe 1; análise de overfitting (K baixo) × underfitting (K alto) |
| **3 – SVM** | Kernel linear × RBF (C = 1,0, `gamma='scale'`); análise do *kernel trick* |
| **4 – Naive Bayes** | GaussianNB; `predict_proba` das 5 primeiras amostras; premissa "ingênua" em dados financeiros |
| **5 – Benchmark** | Tabela comparativa; análise sensível ao custo (SVM com `class_weight='balanced'` e Naive Bayes com limiar escolhido por validação cruzada de 5 folds no treino); parecer de negócio |

#### Resultados (base de teste, 200 clientes; C1 = risco crítico)

| Algoritmo | Configuração | Acurácia | Precisão (C1) | Recall (C1) | F1 (C1) |
|---|---|:---:|:---:|:---:|:---:|
| kNN | K = 3 (euclidiana) | 0,620 | 0,351 | 0,339 | 0,345 |
| SVM | RBF, C = 1,0, `gamma='scale'` | 0,705 | 0,500 | 0,017 | 0,033 |
| Naive Bayes | GaussianNB padrão (limiar 0,5) | 0,630 | 0,273 | 0,153 | 0,196 |
| SVM (sensível ao custo) | RBF, `class_weight='balanced'` | 0,520 | 0,330 | 0,610 | 0,429 |
| **Naive Bayes (limiar ajustado)** | **GaussianNB, limiar 0,20 (CV no treino)** | 0,455 | 0,331 | **0,831** | **0,473** |

#### Recomendação para produção
- **Métrica prioritária:** **Recall da Classe 1** — o falso negativo (aprovar um inadimplente) gera perda direta de capital.
- **Entre as configurações exigidas**, o **kNN (K = 3)** foi o melhor; os SVMs padrão praticamente não detectam risco (a acurácia de ~70% é enganosa).
- **Modelo recomendado:** **Naive Bayes Gaussiano com limiar 0,20**, que detecta **83%** dos clientes de risco (49 de 59), com o melhor F1 (0,473), além de ser rápido, interpretável e ajustável.
- Clientes sinalizados devem ir para **análise manual ou exigência de garantias**, não para recusa automática (precisão ≈ 0,33).
- Próximos passos: mais atributos, validação cruzada de todos os hiperparâmetros, monitoramento de *data drift* e explicabilidade/revisão humana (LGPD, art. 20).

---

## Como executar

```bash
# 1. Clonar o repositório
git clone https://github.com/mariocezarsouza/SENAI-2026-2.git
cd SENAI-2026-2

# 2. Extrair os trabalhos compactados (Windows: botão direito > Extrair tudo)
unzip TP1_Data_Ingestion_Profiling_Engine-main.zip
unzip "TP2 - Situação de Aprendizagem Predição para Imobiliárias.zip"
unzip TP3_Crawler_ML.zip
unzip "Entregáveis_TP3_limpeza_e_integração.zip"

# 3. Instalar as dependências
pip install pandas numpy scikit-learn matplotlib seaborn jupyter requests beautifulsoup4 fastapi uvicorn httpx

# 4. Abrir os notebooks
jupyter notebook
```

| Trabalho | Como rodar |
|---|---|
| LID – TP1 | `python src/ingestion_pipeline.py` e depois `notebooks/analise_vendas.ipynb` |
| AM – TP2 | `tp2_real_estate.ipynb` (o CSV `imoveis_saopaulo.csv` está na mesma pasta) |
| LID – TP3 | `pipeline_crawler_preparacao.ipynb`; API: `uvicorn api_dados:app --port 8000` |
| AM – TP3 | `tp3_sentinel_ai.ipynb` (o dataset é baixado automaticamente da internet) |

## Tecnologias
- **Linguagem e ambiente:** Python 3, Jupyter Notebook, Google Colab
- **Dados:** pandas, NumPy, SQLite3
- **Coleta web:** requests, BeautifulSoup4
- **Machine learning:** scikit-learn (`LinearRegression`, `DecisionTreeClassifier`, `KNeighborsClassifier`, `SVC`, `GaussianNB`, `StandardScaler`, `MinMaxScaler`, `OrdinalEncoder`, validação cruzada e métricas)
- **Visualização:** Matplotlib, Seaborn
- **API:** FastAPI, Uvicorn

---

<sub>Trabalhos acadêmicos desenvolvidos para fins de estudo — Graduação em Tecnologia de Dados, Faculdade SENAI Centro 4.0 / SENAI-MG, 2026/2.</sub>
