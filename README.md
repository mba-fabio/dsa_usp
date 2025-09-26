# Otimização da Distribuição de Estoque de Joias com Machine Learning

**Autor:** Fabio Miguel de Barros Albuquerque  
**Projeto:** Trabalho de Conclusão de Curso (TCC) - MBA em Data Science & Analytics, MBA USP/Esalq (2025)

## 1\. Visão Geral do Projeto

Este projeto aborda o desafio da alocação de estoque no mercado de luxo "second hand" de joias no Brasil. O objetivo é desenvolver e comparar três modelos de *machine learning* (Regressão Logística Multinomial, Árvores de Decisão e Florestas Aleatórias) para determinar a abordagem preditiva de maior acurácia e valor prático na decisão de qual loja deve receber cada novo item de inventário.

A análise completa, incluindo a fundamentação teórica e a discussão detalhada dos resultados, está disponível no documento do TCC.

## 2\. Metodologia

O fluxo de trabalho deste estudo foi estruturado em quatro etapas principais:

1.  **Geração de Dados Simulados:** Criação de uma base de dados sintética de alta fidelidade, baseada em pesquisa de mercado, relatórios financeiros públicos e perfis de consumo programados para espelhar a dinâmica do varejo de joias.
2.  **Análise Exploratória:** Aplicação da Análise de Correspondência Múltipla (ACM) para identificar e visualizar as associações entre as características dos produtos e os perfis de cada loja.
3.  **Modelagem Preditiva:** Desenvolvimento, treinamento e otimização de três algoritmos de classificação para prever a loja ideal para cada joia.
4.  **Avaliação de Performance:** Comparação rigorosa dos modelos utilizando métricas como Acurácia, F1-Score, Precisão e Sensibilidade, derivadas da matriz de confusão.

## 3\. Estrutura do Repositório

  * `20250607_joias_simuladas_historico_24meses_sazonal.csv`: A base de dados principal, contendo o histórico de vendas simulado utilizado no estudo.
  * `20250831_Otimizacao_Estoque_Joias_Usadas.ipynb`: Jupyter Notebook contendo todo o código em Python para a geração dos dados, tratamento (`data wrangling`), análise exploratória, modelagem e avaliação dos resultados.
  * `README.md`: Este arquivo.

## 4\. Base de Dados

O arquivo `20250607_joias_simuladas_historico_24meses_sazonal.csv` contém 10.038 registros de vendas simuladas ao longo de 24 meses para 4 lojas distintas. As variáveis são:

| Variável | Descrição |
| :--- | :--- |
| `DATA` | Mês e ano da venda. |
| `TIPO_JOIA` | Categoria da joia (Anel, Brinco, Colar, etc.). |
| `TIPO_PEDRA` | Tipo de pedra da joia (Diamante, Outras, Sem Pedra). |
| `TIPO_MARCA` | Origem da marca (Nacional, Internacional). |
| `LOJA` | Identificador da loja onde a venda ocorreu (A, B, C, D) - **Variável Alvo**. |
| `PRECO` | Preço da joia em R$. |

## 5\. Como Executar

### Pré-requisitos

Para replicar a análise, é necessário ter um ambiente Python com as seguintes bibliotecas instaladas em suas respectivas versões:

```
python==3.11
pandas==2.2
statsmodels==0.14
prince==0.7
scikit-learn==1.6
matplotlib
seaborn
```

### Execução

O script foi desenvolvido em um ambiente Jupyter Notebook (`.ipynb`). Para executar a análise, basta abrir o arquivo `20250831_Otimizacao_Estoque_Joias_Usadas.ipynb` em um ambiente com os pré-requisitos instalados (como o Google Colab ou uma instalação local do Jupyter) e executar as células em ordem sequencial.

## 6\. Principais Resultados

A análise comparativa revelou um achado central: a simplicidade metodológica superou a complexidade.

  * O modelo de **Regressão Logística Multinomial**, o mais simples e interpretável, apresentou a melhor performance geral, com um **F1-Score de 62,9%** no conjunto de teste.
  * Modelos mais complexos, como as **Florestas Aleatórias**, mesmo após otimização de hiperparâmetros, não apresentaram ganhos de acurácia que justificassem a perda de interpretabilidade.
  * A engenharia de atributos com as coordenadas da ACM demonstrou ser **prejudicial à performance** dos modelos baseados em árvores.

A conclusão do estudo valida um *framework* de decisão que, na ausência de ganhos preditivos expressivos, prioriza modelos que oferecem maior clareza e valor estratégico para o negócio.
