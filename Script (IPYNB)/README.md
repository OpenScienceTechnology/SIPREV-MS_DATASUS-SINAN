# 🛡️ SIPREV-Mulher/MS — v3.2 (Edição Estendida)

**Sistema Inteligente de Predição e Mapeamento da Violência contra a Mulher em Mato Grosso do Sul**

| | |
|---|---|
| **Disciplina** | Tópicos Interdisciplinares III |
| **Curso** | Ciência dos Dados — UFMS Digital |
| **Semestre** | 2026.1 |
| **Autor** | VIANA |
| **Fonte de dados** | SINAN/DATASUS — VIOL (Violência Doméstica, Sexual e/ou Outras) |
| **Espelho dos microdados** | github.com/OpenScienceTechnology/Microdados_SINAN-DATASUS |
| **Denominadores e malhas** | IBGE — Censo 2022 e API de Localidades/Malhas |

---

## 📦 O que está nesta pasta

| Arquivo | Descrição |
|---|---|
| `SINAN-DATASUS_SIPREV_Mulher_MS_v3.2.ipynb` | **Notebook Jupyter completo** (formato `.ipynb`), pronto para Colab e Jupyter local. |
| `SINAN-DATASUS_SIPREV_Mulher_MS_v3.2.py` | **Script Python** equivalente (mesmas células), para execução via terminal. |
| `README.md` | Este arquivo. |

> Os dois arquivos são **independentes e autossuficientes**: contêm todo o código,
> dicionários de referência (municípios e população do IBGE) e a lógica de exportação.
> Não dependem um do outro.

---

## ✅ Compatibilidade

| Ambiente | `.py` | `.ipynb` |
|---|---|---|
| **Google Colab** (upload direto) | ✔ via terminal | ✔ Executar tudo |
| **Jupyter local** | ✔ via terminal | ✔ Run All |
| **Terminal local** | ✔ `python ...py` | ✔ `jupyter nbconvert --execute` |

O sistema detecta automaticamente o ambiente, ativa **saída UTF‑8** (evita erros de
acento/emoji no Windows) e exibe **todos os resultados *inline*** durante a execução
(tabelas, gráficos, mapas, relatórios), do início ao fim.

---

## ▶️ Como executar

### Google Colab
1. Abra o `.ipynb` no Colab.
2. *(Opcional)* Suba os `VIOLBRyy.csv` para `/content/` ou `/content/Dataset/archive_csv/`.
   Sem CSVs, o notebook tenta **baixar do GitHub**; sem rede, gera **dados sintéticos**
   (claramente sinalizados) para demonstrar todo o *pipeline*.
3. **Ambiente de execução → Executar tudo.** Ao final, o pacote `.zip` é **baixado
   automaticamente**.

### Local (Jupyter)
```bash
python -m venv .venv && source .venv/bin/activate     # (Windows: .venv\Scripts\activate)
pip install pandas numpy matplotlib seaborn plotly scikit-learn statsmodels \
            openpyxl texttable tabulate reportlab requests pyarrow xgboost lightgbm torch
jupyter notebook   # abra o .ipynb e use "Run All"
```
Coloque os CSVs em `Dataset/archive_csv/` (o notebook também procura `../Dataset/...`).

### Local (terminal, via `.py`)
```bash
python SINAN-DATASUS_SIPREV_Mulher_MS_v3.2.py
# Teste rápido (amostra pequena):
SIPREV_SMOKE=1 SIPREV_YEARS=2022-2023 SIPREV_MAX_ROWS=5000 python SINAN-DATASUS_SIPREV_Mulher_MS_v3.2.py
```

---

## ⚙️ Configuração por variáveis de ambiente

| Variável | Efeito |
|---|---|
| `SIPREV_SMOKE=1` | Modo rápido (amostra reduzida + modelos leves) |
| `SIPREV_MAX_ROWS=N` | Limite de linhas lidas por ano |
| `SIPREV_YEARS=2018-2024` | Intervalo de anos a processar |
| `SIPREV_DATA_DIR=...` | Pasta dos CSVs |
| `SIPREV_OUT_DIR=...` | Pasta-raiz de saída |
| `SIPREV_NO_DOWNLOAD=1` | Modo offline (não baixa do GitHub) |
| `SIPREV_INSTALL=1` | Força a instalação de dependências |

---

## 🧠 Modelos treinados (Machine Learning, Deep Learning e Redes Neurais)

- **Machine Learning (classificação de risco):** Decision Tree, Random Forest, Extra
  Trees, Gradient Boosting, HistGradientBoosting, AdaBoost, Logistic Regression, KNN,
  Naive Bayes, SVM, **XGBoost, LightGBM, CatBoost** (quando disponíveis).
- **Regressão:** Linear, Ridge, Lasso, **Poisson**, árvores e *boosting* (+ regressão por eixo).
- **Não supervisionado:** K‑Means, DBSCAN, Agglomerative; anomalias com Isolation Forest,
  LOF e One‑Class SVM.
- **Deep Learning / Redes Neurais (PyTorch):** **MLP** (classificação) e **LSTM/GRU**
  (previsão de séries temporais); **TensorFlow/Keras** opcional.
- **Estatística:** **SARIMA** e **Poisson** como *baselines* interpretáveis.
- **Validação:** treino/teste, **validação cruzada**, **validação temporal**, **GridSearch**
  e **ensemble de votação**; explicabilidade por importância de atributos e **SHAP**.

Um **relatório consolidado de todos os modelos** é gerado em `.txt`/`.log` (Texttable),
`.csv`, `.xlsx` e `.json`, com comparativo gráfico.

---

## 📜 Saídas geradas (exportadas e compactadas em `.zip`)

Tudo é salvo em `saidas_SIPREV/SIPREV_Mulher_MS_<data_hora>/` e compactado em
`SIPREV_Mulher_MS_<data_hora>.zip` (baixado automaticamente no Colab):

```
01_tabelas/        .csv / .xlsx  (rankings, painéis, indicadores, dicionário, catálogo)
02_graficos/       .png          (séries, barras, pirâmide, heatmaps, ROC, importâncias…)
03_mapas/          .html / .png  (mapa de calor Folium, estático, coroplético)
04_dashboards/     .html         (painéis Plotly + dashboard consolidado)
05_relatorios/     .txt / .log   (Texttable) + .pdf (relatório mestre)
06_modelos/        métricas e artefatos de modelos
07_dados_processados/  .parquet / .csv  (camadas bronze/silver/gold, tabela longa)
08_logs/           .log          (execução)
09_json/           .json         (indicadores, qualidade, glossário, modelos)
MANIFESTO.csv/.json              (trilha de auditoria de todos os artefatos)
LEIA-ME.txt                      (resumo do pacote)
```

Os relatórios em `.txt` e `.log` usam a biblioteca **Texttable**, conforme exigido.

---

## 🗺️ Cobertura analítica (plano completo)

Ocorrências (ano/mês/dia/hora/local) · perfil das vítimas (idade, faixa, raça/cor,
escolaridade, situação conjugal, ciclo de vida, gestação, orientação/identidade) ·
autores e **vínculo autor‑vítima** (matriz tipo × vínculo) · eixos temáticos (doméstica,
física, psicológica, sexual, **estupro**, ameaça, lesão, negligência, financeira, tráfico,
infantil, **feminicídio**, óbito) · **taxas por 100 mil mulheres** · **rankings municipal e
nacional** (absoluto e por taxa) · análise **geoespacial** e mapas de calor · séries
temporais e previsão · **qualidade dos dados** · **índices avançados** (vulnerabilidade,
concentração, persistência, gravidade, resposta institucional, subnotificação, **Índice de
Alerta**) · resposta institucional (proxy de **medidas protetivas**) · testes de associação
(qui‑quadrado) · *clustering* de municípios · recomendações de política pública.

---

## 🔐 Ética e LGPD

O sistema usa **exclusivamente dados agregados**. Não exibe nem exporta nomes, CPF, RG,
endereço, telefone ou registros individualizados. Aplica **k‑anonimato** (supressão de
células pequenas), mantém **logs sem dados pessoais** e gera **dicionário de dados** e
**trilha de auditoria**. Uso **acadêmico** e de **apoio a políticas públicas** de
enfrentamento à violência contra a mulher.

### Observações metodológicas importantes
- O SINAN é base de **saúde** (notificações), sujeita a **subnotificação**; não equivale a
  registros policiais.
- **Feminicídio**, **tentativa de feminicídio** e **medidas protetivas** são **proxies
  documentados** (o SINAN não os codifica formalmente).
- Taxas usam **denominadores do Censo IBGE 2022**; taxas acumuladas multi‑ano servem à
  comparação relativa, não como incidência anual.
- O **modo sintético** é apenas demonstrativo do *pipeline* — nunca estatística oficial.

---

*SIPREV‑Mulher/MS v3.2 — gerado para a disciplina de Tópicos Interdisciplinares III
(Ciência dos Dados, UFMS Digital, 2026.1).*
