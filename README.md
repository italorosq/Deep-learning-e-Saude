<div align="center">

# 🩺 Deep Learning e Saúde

**Classificação automática de transcrições médicas por especialidade usando NLP e Machine Learning**

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![spaCy](https://img.shields.io/badge/spaCy-NLP-09A3D5?logo=spacy&logoColor=white)](https://spacy.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

</div>

---

## 📌 Sobre o Projeto

Este projeto explora a interseção entre **inteligência artificial** e **saúde**, aplicando técnicas de **Processamento de Linguagem Natural (NLP)** e **aprendizado de máquina** para classificar automaticamente transcrições médicas de acordo com a especialidade médica correspondente.

O pipeline completo inclui:

- 📊 Análise exploratória dos dados
- 🧹 Pré-processamento e limpeza de texto com **spaCy**
- ⚖️ Balanceamento do conjunto de dados
- 🔢 Vetorização com **TF-IDF**
- 🤖 Treinamento e avaliação de classificadores **Naive Bayes** (MultinomialNB e ComplementNB)
- 📈 Avaliação com 100 execuções e múltiplos folds de validação cruzada

---

## 📁 Estrutura do Repositório

```
Deep-learning-e-Saude/
│
├── Database/
│   ├── mtsamples.csv                  # Transcrições médicas com especialidades
│   └── Disease precaution.csv         # Precauções por doença
│   ├── df_balanced.csv                # Base balanceada
│   ├── df_balanced_limpo.csv          # Base balanceada e limpa
│   └── resultados_classificadores_nb_balanced_100runs_30folds.csv
│                                     # Resultados consolidados dos classificadores
│
├── Notebooks/
│   └── notebookprincipal.ipynb        # Notebook principal com o pipeline completo
│
└── README.md
```

---

## 🗃️ Datasets

| Arquivo | Descrição | Colunas principais |
|---|---|---|
| `mtsamples.csv` | Mais de 4.000 transcrições médicas reais | `medical_specialty`, `transcription`, `description`, `keywords` |
| `Disease precaution.csv` | Precauções recomendadas para diversas doenças | `Disease`, `Precaution_1` a `Precaution_4` |
| `df_balanced.csv` | Amostra balanceada por especialidade | Derivada de `mtsamples.csv` |
| `df_balanced_limpo.csv` | Texto pré-processado para modelagem | Derivada de `df_balanced.csv` |
| `resultados_classificadores_nb_balanced_100runs_30folds.csv` | Métricas finais dos experimentos | Resultados de 100 execuções |

### Top 10 Especialidades Médicas

O notebook seleciona as **10 especialidades mais frequentes** para o treinamento dos modelos:

> Cirurgia, Consulta, Ortopedia, Radiologia, Gastroenterologia, Neurologia, Urologia, Medicina Interna, Neurociência e mais.

---

## ⚙️ Pipeline

```
Dados Brutos (mtsamples.csv)
        │
        ▼
Análise Exploratória (EDA)
        │
        ▼
Pré-processamento
  └─ Remoção de valores nulos
  └─ Seleção das top 10 especialidades
  └─ Balanceamento (redução de cirurgias para 40%)
        │
        ▼
Limpeza de Texto com spaCy
  └─ Tokenização e lematização
  └─ Remoção de stop words e pontuação
        │
        ▼
Vetorização TF-IDF
        │
        ▼
Treinamento e Avaliação
  └─ MultinomialNB
  └─ ComplementNB
  └─ 100 execuções × múltiplos folds
        │
        ▼
Resultados e Métricas
```

---

## 🛠️ Tecnologias Utilizadas

| Biblioteca | Finalidade |
|---|---|
| `pandas` / `numpy` | Manipulação e análise de dados |
| `matplotlib` / `seaborn` | Visualização de dados |
| `spaCy` | Processamento de linguagem natural |
| `scikit-learn` | Vetorização TF-IDF, modelos e métricas |
| `imbalanced-learn` | Balanceamento de classes (RandomUnderSampler) |

---

## 🚀 Como Executar

### Pré-requisitos

- Python 3.12+
- Jupyter Notebook ou JupyterLab

### Instalação

```bash
# Clone o repositório
git clone https://github.com/italorosq/Deep-learning-e-Saude.git
cd Deep-learning-e-Saude

# Instale as dependências
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn spacy

# Baixe o modelo de linguagem inglês do spaCy
python -m spacy download en_core_web_sm

# Inicie o Jupyter
jupyter notebook Notebooks/notebookprincipal.ipynb
```

> ⚠️ **Atenção:** O notebook usa caminhos absolutos locais para leitura dos CSVs. Antes de executar, atualize as células de leitura para usar os caminhos relativos ao repositório, por exemplo:
> ```python
> df = pd.read_csv('../Database/mtsamples.csv')
> ```

---

## 📊 Resultados

Os classificadores são avaliados ao longo de **100 execuções independentes**, cada uma com split treino/teste aleatório, garantindo resultados robustos e estatisticamente significativos.

| Modelo | Acurácia Média |
|---|---|
| `MultinomialNB` | Baixa — Cerca de 40% por conta da base ser complexa |
| `ComplementNB` | Baixa — Leve aumento por conta de como o classificador funciona |

---

## 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir uma *issue* ou enviar um *pull request*.

---

## 📄 Licença

Este projeto está sob a licença **MIT**. Consulte o arquivo [LICENSE](LICENSE) para mais detalhes.

---

<div align="center">
Feito  por <a href="https://github.com/italorosq">italorosq</a>
</div>
