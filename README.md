# Saude e IA

## Visao geral
Este repositorio apresenta um projeto de estudo aplicado em saude e inteligencia artificial, com foco em classificacao de dados clinicos. O objetivo principal e demonstrar competencias em ciencia de dados, pre-processamento, modelagem e avaliacao de resultados.

## Objetivos
- Comparar métodos de machine lerning e deep leaning.
- Explorar tecnicas de balanceamento e validacao.
- Documentar resultados de experimentos de forma clara.

## Estrutura do repositorio
- Database/ : bases de dados e arquivos de resultados.
- Notebooks/ : notebook principal com a analise e os experimentos.

## Como executar
1. Crie e ative um ambiente virtual.
2. Instale as dependencias conforme sua configuracao local.
3. Abra o notebook principal e execute as celulas na ordem.

## Guia de instalacao
1. Crie o ambiente virtual:
```bash
python -m venv venv
```
2. Ative o ambiente virtual (Windows PowerShell):
```bash
./venv/Scripts/Activate.ps1
```
3. Instale as bibliotecas principais:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn spacy
```
4. Se houver etapas de NLP com spaCy, baixe um modelo:
```bash
python -m spacy download en_core_web_sm
```

## Bibliotecas utilizadas
- numpy
- pandas
- matplotlib
- seaborn
- scikit-learn
- imbalanced-learn
- spacy

## Dados
As bases utilizadas encontram-se em Database/. Caso deseje substituir os dados, mantenha o mesmo formato de colunas para reproduzir os experimentos.

## Resultados
Os resultados dos classificadores e experimentos consolidados estao disponiveis na pasta Database/.

## Licenca
Este projeto e de uso educacional e demonstrativo. Verifique as restricoes de uso das bases de dados caso deseje reutiliza-las.
