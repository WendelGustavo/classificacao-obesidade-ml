# Classificação do nível de obesidade

Autor: Wendel Gustavo Fillmann. Universidade Feevale, curso de Ciência da Computação.

Repositório: https://github.com/WendelGustavo/classificacao-obesidade-ml

[![Abrir no Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/WendelGustavo/classificacao-obesidade-ml/blob/main/obesidade.ipynb)

Trabalho prático da disciplina de Inteligência Artificial e Computacional. O trabalho compara três algoritmos de classificação supervisionada no conjunto de dados Estimation of Obesity Levels Based On Eating Habits and Physical Condition, disponível no [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/544/estimation+of+obesity+levels+based+on+eating+habits+and+physical+condition).

## Descrição

O atributo classe é `NObeyesdad`, que representa o nível de obesidade em sete categorias. Foram avaliados os algoritmos Árvore de Decisão, Random Forest e KNN (k = 5), por meio de validação cruzada estratificada com 10 partições. As métricas utilizadas foram acurácia, precisão, revocação e medida F (média macro), além do tempo de treinamento.

Foram testadas duas variações de pré-processamento:

* P1: todos os atributos.
* P2: todos os atributos, exceto altura e peso.

## Resultados

| Variação | Algoritmo | Acurácia | Precisão | Recall | F-Measure |
|---|---|---|---|---|---|
| P1 | Árvore de Decisão | 94,30% | 0,9422 | 0,9407 | 0,9407 |
| P1 | Random Forest | 94,92% | 0,9492 | 0,9471 | 0,9473 |
| P1 | KNN (k=5) | 78,44% | 0,7777 | 0,7792 | 0,7724 |
| P2 | Árvore de Decisão | 74,18% | 0,7374 | 0,7361 | 0,7340 |
| P2 | Random Forest | 80,50% | 0,8042 | 0,8005 | 0,7991 |
| P2 | KNN (k=5) | 72,59% | 0,7217 | 0,7201 | 0,7129 |

Os resultados foram obtidos no Google Colab. Os tempos de treinamento estão nos arquivos `logs/resultados_*.csv`.

## Estrutura

| Caminho | Conteúdo |
|---|---|
| `obesidade.ipynb` | Notebook com caracterização, pré-processamento, experimentos e conclusões |
| `relatorio.pdf` | Relatório do trabalho |
| `data/original/` | Arquivo CSV original |
| `data/processed/` | Arquivos pré-processados das variações P1 e P2 |
| `models/` | Modelos treinados no formato joblib |
| `logs/` | Log de execução e tabelas de resultados |
| `figuras/` | Gráficos gerados pelo notebook |

## Execução

### Google Colab

1. Abra o notebook pelo link: https://colab.research.google.com/github/WendelGustavo/classificacao-obesidade-ml/blob/main/obesidade.ipynb
2. No menu, selecione **Ambiente de execução > Executar tudo**.

O notebook baixa automaticamente o conjunto de dados do UCI Machine Learning Repository e gera os arquivos pré-processados, os modelos, os logs e as figuras na pasta de trabalho do Colab.

### Execução local

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute --inplace obesidade.ipynb
```

## Referências

DE-LA-HOZ-CORREA, E. et al. Obesity level estimation software based on decision trees. Journal of Computer Science, v. 15, n. 1, p. 67-77, 2019.

PALECHOR, F. M.; DE LA HOZ MANOTAS, A. Dataset for estimation of obesity levels based on eating habits and physical condition in individuals from Colombia, Peru and Mexico. Data in Brief, v. 25, 2019.
