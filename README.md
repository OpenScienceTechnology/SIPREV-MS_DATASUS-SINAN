# 🛡️ SIPREV-Mulher/MS

## Sistema Inteligente de Predição e Mapeamento da Violência contra a Mulher em Mato Grosso do Sul

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter)
![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-red?style=for-the-badge&logo=streamlit)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Random%20Forest%20%7C%20XGBoost%20%7C%20LightGBM-green?style=for-the-badge)
![Deep Learning](https://img.shields.io/badge/Deep%20Learning-LSTM%20%7C%20GRU%20%7C%20MLP-purple?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Acad%C3%AAmico%20%7C%20Pesquisa-informational?style=for-the-badge)

---

## 📌 Descrição do Projeto

O **SIPREV-Mulher/MS** é um projeto acadêmico e tecnológico desenvolvido em Python para análise, predição, mapeamento e explicabilidade de dados relacionados à violência contra a mulher no estado de **Mato Grosso do Sul**.

O notebook implementa um pipeline completo de Ciência de Dados aplicado a dados públicos do **SINAN/DATASUS**, contemplando o período de **2009 a 2025**, com foco em:

- 📥 ingestão automatizada de microdados públicos;
- 🧹 limpeza, padronização e validação dos dados;
- 📊 análise exploratória descritiva;
- 🗺️ análise geoespacial por município;
- 🧠 clusterização dos municípios por perfil epidemiológico;
- 🤖 modelos preditivos clássicos de Machine Learning;
- 🔮 modelos de Deep Learning para séries temporais e risco;
- 🔍 explicabilidade algorítmica com SHAP e LIME;
- 📈 dashboard interativo em Streamlit;
- 📦 exportação automatizada de relatórios, gráficos, tabelas e arquivos consolidados.

O objetivo central é apoiar estudos acadêmicos, diagnósticos territoriais, análises epidemiológicas e propostas de políticas públicas baseadas em dados para enfrentamento da violência contra a mulher.

---

## 🗂️ Repositório

```text
https://github.com/OpenScienceTechnology/Microdados_SINAN-DATASUS
```

---

## 🎯 Objetivos

### Objetivo Geral

Desenvolver um sistema inteligente de análise, predição e visualização de registros de violência contra a mulher em Mato Grosso do Sul, utilizando técnicas de Ciência de Dados, Aprendizado de Máquina, Deep Learning, Estatística, Geoprocessamento e Inteligência Artificial Explicável.

### Objetivos Específicos

- 📌 Consolidar microdados anuais do SINAN/DATASUS.
- 📌 Filtrar registros referentes ao estado de Mato Grosso do Sul.
- 📌 Padronizar variáveis categóricas, temporais e geográficas.
- 📌 Criar indicadores derivados de violência, reincidência, óbito, faixa etária e perfil da vítima.
- 📌 Mapear os 79 municípios de Mato Grosso do Sul.
- 📌 Identificar padrões temporais, territoriais e epidemiológicos.
- 📌 Agrupar municípios por similaridade de risco.
- 📌 Treinar modelos de regressão para previsão de notificações.
- 📌 Treinar modelos de classificação para risco municipal.
- 📌 Detectar municípios com comportamento anômalo.
- 📌 Aplicar modelos LSTM, GRU e MLP.
- 📌 Explicar os fatores mais relevantes dos modelos com SHAP e LIME.
- 📌 Gerar relatórios técnicos em `.csv`, `.txt`, `.png`, `.html`, `.parquet` e `.zip`.

---

## 🧩 Estrutura do Notebook

O notebook está organizado em 14 seções principais:

| Seção | Tema | Descrição |
|---:|---|---|
| 0 | ⚙️ Configuração do Ambiente | Instalação de dependências, importações globais e constantes do projeto |
| 1 | 📥 Carregamento dos Dados | Download e leitura dos CSVs do SINAN/DATASUS de 2009 a 2025 |
| 2 | 🧹 Limpeza e Pré-processamento | Conversão de tipos, datas, idade, categóricas, flags e validação |
| 2A | 🚨 Crimes Sexuais e Feminicídio | Criação de flags específicas para estupro, assédio, exploração sexual e feminicídio inferido |
| 3 | 📊 Análise Exploratória | Rankings, prevalência, séries temporais, sazonalidade, perfil etário e correlações |
| 4 | 🗺️ Análise Geoespacial | Mapas coropléticos e mapas interativos com GeoPandas e Folium |
| 5 | 🧠 Clusterização Municipal | Agrupamento dos municípios por K-Means, DBSCAN e HDBSCAN |
| 6 | 🤖 Machine Learning Clássico | Regressão, classificação, anomalias e séries temporais com Prophet |
| 7 | 🔮 Deep Learning | Modelos LSTM, GRU e MLP com TensorFlow/Keras |
| 8 | 🔍 Explicabilidade | Interpretação dos modelos com SHAP e LIME |
| 9 | 📈 Dashboard Streamlit | Geração automática do arquivo `app.py` |
| 10 | 🏛️ Recomendações de Política Pública | Síntese dos achados, limitações, LGPD, ética e recomendações |
| 11 | 📋 Ocorrências | Relatórios por município, ano, mês, faixa etária, local e relação autor-vítima |
| 12 | 🏙️ Ranking Municipal | Ranking dos 79 municípios de MS |
| 13 | 🇧🇷 Ranking Nacional | Comparativo de Mato Grosso do Sul com as demais Unidades da Federação |
| 14 | 📦 Exportação Final | Consolidação dos modelos, relatórios e compactação em `.zip` |

---

## 🗂️ Estrutura Recomendada do Repositório

```bash
SIPREV-Mulher-MS/
│
├── README.md
├── SIPREV_Mulher_MS.ipynb
├── app.py
│
├── data/
│   ├── raw/
│   │   ├── VIOLBR09.csv
│   │   ├── VIOLBR10.csv
│   │   ├── ...
│   │   └── VIOLBR25.csv
│   │
│   └── processed/
│       ├── siprev_ms_consolidado.parquet
│       └── siprev_ms/
│
├── models/
│   ├── reg_lightgbm.joblib
│   ├── cls_lightgbm.joblib
│   ├── lstm_siprev.keras
│   ├── gru_siprev.keras
│   └── mlp_siprev.keras
│
├── outputs/
│   ├── 03_ranking_municipios.png
│   ├── 04_mapa_interativo.html
│   ├── 05_mapa_clusters.png
│   ├── 06_prophet_forecast.png
│   ├── 08_shap_summary_bar.png
│   ├── relatorios/
│   │   ├── municipal/
│   │   ├── nacional/
│   │   └── modelos/
│   └── indice_geral.json
│
├── logs/
│   └── siprev_*.log
│
└── siprev_resultados.zip
```

---

## 🗃️ Fonte dos Dados

O projeto utiliza microdados públicos de violência interpessoal/autoprovocada do **SINAN/DATASUS**, disponibilizados em arquivos CSV anuais.

### 📍 Fonte utilizada no notebook

```text
https://media.githubusercontent.com/media/OpenScienceTechnology/Microdados_SINAN-DATASUS/refs/heads/main/Data/CSV/
```

### 📅 Período analisado

```text
2009 a 2025
```

### 📌 Recorte territorial

```text
Mato Grosso do Sul — Código IBGE UF: 50
```

### 🧾 Arquivos esperados

```text
VIOLBR09.csv
VIOLBR10.csv
VIOLBR11.csv
...
VIOLBR25.csv
```

---

## 🧪 Principais Variáveis Utilizadas

O notebook trabalha com variáveis originais do SINAN e variáveis derivadas.

### Variáveis originais

| Variável | Descrição |
|---|---|
| `SG_UF_NOT` | Unidade Federativa da notificação |
| `ID_MUNICIP` | Código do município |
| `DT_NOTIFIC` | Data da notificação |
| `NU_IDADE_N` | Idade codificada no padrão SINAN |
| `CS_SEXO` | Sexo da vítima |
| `CS_RACA` | Raça/cor |
| `CS_ESCOL_N` | Escolaridade |
| `LOCAL_OCOR` | Local de ocorrência |
| `EVOLUCAO` | Evolução do caso |
| `OUT_VEZES` | Indicação de reincidência |
| `AUTOR_ALCO` | Suspeita de uso de álcool pelo agressor |
| `VIOL_FISIC` | Violência física |
| `VIOL_PSICO` | Violência psicológica |
| `VIOL_SEXU` | Violência sexual |
| `VIOL_NEGLI` | Negligência/abandono |
| `SEX_ESTUPR` | Estupro |
| `SEX_ASSEDI` | Assédio sexual |
| `SEX_EXPLOR` | Exploração sexual |
| `LES_AUTOP` | Lesão autoprovocada |

### Variáveis derivadas

| Variável | Descrição |
|---|---|
| `IDADE_ANOS` | Idade decodificada em anos |
| `FAIXA_ETARIA` | Faixa etária agrupada |
| `RACA_COR` | Raça/cor padronizada |
| `ESCOLARIDADE` | Escolaridade padronizada |
| `LOCAL_OCOR_DESC` | Local de ocorrência decodificado |
| `VIOL_*_FLAG` | Flags binárias para tipos de violência |
| `REINC_FLAG` | Indicador de reincidência |
| `ALCO_FLAG` | Indicador de álcool associado ao agressor |
| `OBITO_FLAG` | Indicador de óbito por violência |
| `FEMINICIDIO_FLAG` | Inferência de feminicídio |
| `N_TIPOS_VIOL` | Número de tipos de violência por registro |
| `RISCO_LABEL` | Classe de risco municipal: Baixo, Médio ou Alto |

---

## ⚙️ Tecnologias e Bibliotecas

### 🧮 Manipulação e processamento de dados

- `pandas`
- `numpy`
- `polars`
- `dask[dataframe]`
- `duckdb`
- `pyarrow`
- `fastparquet`

### 🧹 Qualidade, validação e limpeza

- `pandera`
- `pydantic`
- `great_expectations`
- `missingno`
- `unidecode`
- `rapidfuzz`

### 📊 Estatística e séries temporais

- `scipy`
- `statsmodels`
- `prophet`
- `pmdarima`

### 🗺️ Geoprocessamento

- `geopandas`
- `shapely`
- `folium`
- `contextily`
- `pydeck`
- `geopy`

### 🤖 Machine Learning

- `scikit-learn`
- `xgboost`
- `lightgbm`
- `imbalanced-learn`
- `hdbscan`
- `optuna`

### 🧠 Deep Learning

- `tensorflow`
- `keras`
- `torch`
- `pytorch-lightning`
- `torchmetrics`

### 🔍 Explicabilidade

- `shap`
- `lime`
- `eli5`

### 📈 Visualização e dashboard

- `matplotlib`
- `seaborn`
- `plotly`
- `altair`
- `streamlit`

### 🧰 MLOps e utilitários

- `mlflow`
- `dvc`
- `loguru`
- `hydra-core`
- `joblib`
- `onnx`
- `onnxruntime`
- `requests`
- `tqdm`
- `colorama`

---

## 🚀 Como Executar o Projeto

### 1️⃣ Clone o repositório

```bash
git clone https://github.com/SEU-USUARIO/SIPREV-Mulher-MS.git
cd SIPREV-Mulher-MS
```

### 2️⃣ Crie um ambiente virtual

#### Windows

```bash
python -m venv .venv
.venv\Scripts\activate
```

#### Linux/macOS

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3️⃣ Instale as dependências

```bash
pip install pandas numpy polars dask[dataframe] duckdb pyarrow fastparquet
pip install pandera pydantic great_expectations missingno unidecode rapidfuzz
pip install scipy statsmodels ydata-profiling
pip install geopandas shapely folium contextily pydeck geopy
pip install scikit-learn xgboost lightgbm imbalanced-learn hdbscan optuna
pip install prophet pmdarima
pip install tensorflow torch pytorch-lightning torchmetrics
pip install shap lime eli5
pip install mlflow dvc loguru hydra-core joblib onnx onnxruntime
pip install matplotlib seaborn plotly altair streamlit streamlit-folium
pip install requests tqdm colorama texttable
```

> 💡 O notebook também possui uma célula automática de instalação das dependências.

### 4️⃣ Execute o notebook

```bash
jupyter notebook SIPREV_Mulher_MS.ipynb
```

Ou, se preferir:

```bash
jupyter lab
```

### 5️⃣ Execute as células em ordem

O notebook deve ser executado sequencialmente, da Seção 0 até a Seção 14, pois várias etapas dependem de variáveis, modelos e arquivos gerados nas seções anteriores.

---

## 📈 Como Executar o Dashboard

Após executar o notebook e gerar o arquivo `app.py`, rode:

```bash
streamlit run app.py
```

O dashboard interativo inclui:

- 📊 visão geral dos registros;
- 📈 análise temporal;
- 🗺️ mapa de risco;
- 👤 perfil epidemiológico;
- 🔮 previsões;
- 🔍 explicabilidade dos modelos.

---

## 🤖 Modelos Implementados

### Regressão

Modelos usados para prever o volume mensal de notificações:

| Modelo | Finalidade |
|---|---|
| `RandomForestRegressor` | Previsão robusta com árvores de decisão |
| `XGBoostRegressor` | Gradient boosting regularizado |
| `LightGBMRegressor` | Boosting otimizado para dados tabulares |

### Classificação

Modelos usados para classificar risco municipal em **Baixo**, **Médio** ou **Alto**:

| Modelo | Finalidade |
|---|---|
| `RandomForestClassifier` | Classificação multiclasse interpretável |
| `XGBoostClassifier` | Classificação com boosting |
| `LightGBMClassifier` | Classificação eficiente em dados tabulares |

### Detecção de Anomalias

| Modelo | Finalidade |
|---|---|
| `IsolationForest` | Identificação de municípios com comportamento atípico |
| `LocalOutlierFactor` | Detecção de outliers por vizinhança |

### Séries Temporais

| Modelo | Finalidade |
|---|---|
| `Prophet` | Previsão de notificações para os próximos 12 meses |
| `ARIMA/SARIMA` | Modelagem estatística de séries temporais |

### Deep Learning

| Modelo | Finalidade |
|---|---|
| `LSTM` | Captura de dependências temporais longas |
| `GRU` | Rede recorrente otimizada |
| `MLP` | Classificação de risco com rede neural densa |

---

## 🔍 Explicabilidade dos Modelos

O projeto utiliza técnicas de Inteligência Artificial Explicável para tornar os resultados compreensíveis e auditáveis.

### SHAP

O SHAP é utilizado para identificar a contribuição média das variáveis no desempenho dos modelos de regressão.

Exemplos de saídas:

- `08_shap_summary_bar.png`
- `08_shap_beeswarm.png`
- `08_shap_waterfall.png`
- `08_shap_dependence_reinc.png`
- `08_shap_importancia_barras.png`

### LIME

O LIME é utilizado para explicações locais, permitindo interpretar uma previsão específica do modelo.

Saída gerada:

- `08_lime_local.png`

---

## 🗺️ Análises Geoespaciais

O projeto realiza mapas municipais e nacionais com:

- `GeoPandas`;
- `Folium`;
- shapefiles do IBGE;
- mapas coropléticos;
- mapas HTML interativos;
- mapas de risco por município;
- mapas por indicadores de reincidência, óbito e volume de notificações.

### Principais mapas gerados

```text
04_mapa_coropletico.png
04_mapa_interativo.html
05_mapa_clusters.png
11_mapa_vitimas_municipio.html
11_mapa_taxa_100k.png
12_mapas_indicadores.png
13_mapa_nacional.png
```

---

## 📊 Principais Relatórios Gerados

### Relatórios municipais

```text
11_vitimas_municipio.txt
11_vitimas_municipio.csv
11_vitimas_ano.txt
11_vitimas_ano.csv
11_vitimas_mes.txt
11_vitimas_mes.csv
11_faixa_etaria.txt
11_faixa_etaria.csv
11_taxa_100k.txt
11_taxa_100k.csv
11_locais_incidencia.txt
11_locais_incidencia.csv
11_relacao_autor_vitima.txt
11_relacao_autor_vitima.csv
11_autor_perfil.txt
11_autor_perfil.csv
12_ranking_completo.txt
12_ranking_completo.csv
```

### Relatórios nacionais

```text
13_ranking_nacional.txt
13_ranking_nacional.csv
13_resumo_ms_brasil.txt
```

### Relatórios de modelos

```text
14_relatorio_modelos.txt
14_relatorio_modelos.csv
14_narrativa_modelos.txt
```

### Índice geral

```text
outputs/relatorios/indice_geral.json
```

### Arquivo final compactado

```text
siprev_resultados.zip
```

---

## 📌 Principais Indicadores Analisados

O notebook calcula e compara indicadores como:

- 📍 total de notificações;
- ♀️ percentual de vítimas femininas;
- 🔄 reincidência;
- 🍺 associação com uso de álcool pelo agressor;
- 💀 óbito por violência;
- 🚨 estupro;
- 🚨 assédio sexual;
- 🚨 exploração sexual;
- 🚨 feminicídio inferido;
- 👶 violência contra crianças;
- 👩 perfil etário das vítimas;
- 🏠 local de ocorrência;
- 👥 vínculo autor-vítima;
- 🏙️ ranking municipal;
- 🇧🇷 posição de MS no ranking nacional.

---

## 🧠 Principais Achados Analíticos

A análise do notebook aponta padrões relevantes:

- 🚨 A violência física aparece como o tipo de notificação mais frequente.
- 🏠 A residência se destaca como principal local de ocorrência.
- 👩 A faixa etária de 18 a 29 anos concentra volume expressivo de registros.
- 👶 Crianças de 0 a 11 anos apresentam relevância nos casos associados à negligência e abuso.
- 🏙️ Campo Grande concentra grande parte das notificações do estado.
- 🔄 A reincidência apresenta associação estatística relevante com uso de álcool pelo agressor.
- 🗺️ Municípios do interior podem apresentar subnotificação estrutural.
- 🤖 Modelos de Machine Learning e Deep Learning demonstram potencial para antecipar risco e apoiar planejamento público.
- 🔍 SHAP e LIME ajudam a tornar os modelos mais transparentes para gestores.

---

## 🏛️ Recomendações de Política Pública

O projeto propõe recomendações orientadas por dados, incluindo:

- 🏥 capacitação de profissionais de saúde para identificação e notificação de violência;
- 🧾 padronização de protocolos nas UBS, UPAs e hospitais;
- 🏠 fortalecimento de casas-abrigo e serviços de acolhimento;
- 👮 integração entre saúde, assistência social, segurança pública e Judiciário;
- 📞 integração futura com dados do Ligue 180;
- 🏛️ cruzamento com dados das DEAMs e Casas da Mulher Brasileira;
- 🧠 uso responsável de modelos preditivos com revisão humana;
- 🔍 auditoria periódica de vieses algorítmicos;
- 👥 participação social na validação das ferramentas.

---

## 🔐 Ética, LGPD e Governança de IA

Este projeto trabalha com dados públicos e anonimizados, sem identificação nominal das vítimas.

Mesmo assim, por tratar de tema sensível, recomenda-se:

- 🔒 não tentar reidentificar indivíduos;
- 🔒 não publicar microdados sensíveis enriquecidos com geolocalização precisa;
- 🔒 aplicar os princípios da LGPD;
- 🔒 usar os modelos como apoio à decisão, e não como decisão automatizada final;
- 🔒 manter revisão humana em classificações de alto risco;
- 🔒 auditar vieses por raça/cor, território, idade e classe social;
- 🔒 comunicar limitações, incertezas e margens de erro.

> ⚠️ O sistema não deve ser usado para vigilância individual, estigmatização territorial ou decisões automatizadas sem supervisão humana.

---

## ⚠️ Limitações do Projeto

Algumas limitações devem ser consideradas:

- 📉 possibilidade de subnotificação dos casos de violência;
- 🧾 incompletude em campos como raça/cor, escolaridade e vínculo do agressor;
- 🗺️ análise geográfica limitada ao nível municipal;
- 🔄 dependência da qualidade dos registros oficiais;
- ⏳ necessidade de atualização periódica dos dados;
- 🤖 risco de vieses algorítmicos se os modelos forem utilizados sem auditoria;
- 🧪 necessidade de validação externa com outras bases públicas.

---

## 🔮 Melhorias Futuras

Sugestões de evolução do projeto:

- 📞 integrar dados do Ligue 180;
- 👮 integrar boletins de ocorrência e dados das DEAMs;
- 🏥 integrar dados de unidades de saúde e assistência social;
- 🧭 incluir variáveis socioeconômicas municipais;
- 🌎 criar indicadores por região de saúde;
- 🧠 testar modelos Transformer para séries temporais;
- 🔐 estudar aprendizado federado para preservar privacidade;
- 📊 criar dashboard público com dados agregados;
- 📦 empacotar o pipeline em módulos Python reutilizáveis;
- 🧪 criar testes automatizados para validação dos dados.

---

## 🧾 Como Citar este Projeto

```text
VIANA. SIPREV-Mulher/MS: Sistema Inteligente de Predição e Mapeamento da Violência contra a Mulher em Mato Grosso do Sul. Projeto acadêmico em Ciência dos Dados, UFMS Digital, 2026.
```

---

## 👨‍💻 Autor

**VIANA**  
🎓 Curso: Ciência dos Dados  
🏫 Disciplina: Tópicos Interdisciplinares III  
📅 Semestre: 2026.1  
📍 Mato Grosso do Sul — Brasil  

---

## 📜 Licença

Este projeto é disponibilizado para fins acadêmicos, científicos e educacionais.

Sugestão de licença:

```text
MIT License
```

> ⚠️ Caso o repositório utilize dados públicos sensíveis, recomenda-se incluir uma política adicional de uso ético dos dados.

---

## ✅ Status do Projeto

```text
✅ Pipeline de dados concluído
✅ Análise exploratória implementada
✅ Mapas municipais implementados
✅ Clusterização implementada
✅ Modelos preditivos implementados
✅ Deep Learning implementado
✅ Explicabilidade SHAP/LIME implementada
✅ Dashboard Streamlit gerado
✅ Relatórios finais exportados
✅ Compactação final dos resultados implementada
```

---

## 📦 Resultado Final

Ao final da execução, o projeto gera:

- 📁 bases processadas em `.parquet`;
- 📊 gráficos em `.png`;
- 🗺️ mapas interativos em `.html`;
- 📄 relatórios em `.txt`;
- 📑 tabelas em `.csv`;
- 🤖 modelos treinados em `.joblib` e `.keras`;
- 📈 dashboard `app.py`;
- 📦 pacote final `siprev_resultados.zip`.

---

## 🛡️ SIPREV-Mulher/MS

> Ciência de Dados aplicada à proteção, prevenção e enfrentamento da violência contra a mulher em Mato Grosso do Sul.
