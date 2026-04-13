# 📊 Análise de Transações PIX por Região (PF vs PJ)

## 📌 Sobre o projeto

Este projeto tem como objetivo analisar a participação de pessoas físicas (PF) e pessoas jurídicas (PJ) nas transações PIX no Brasil, com foco na distribuição por região.

A análise busca responder:

* Qual região possui maior participação de PJ?
* Como PF e PJ se distribuem nas regiões?
* Existem inconsistências nos dados?

---

## 🗂️ Estrutura dos dados

Os dados foram disponibilizados em formato JSON, contendo informações agregadas por município, incluindo:

* Região
* Estado
* Valores de transações (PF e PJ)

Foi necessário transformar a estrutura para um formato tabular utilizando Pandas.

---

## ⚙️ Tecnologias utilizadas

* Python
* Pandas
* Matplotlib

---

## 🔄 Tratamento dos dados

Etapas realizadas:

* Extração da estrutura JSON (`value`)
* Conversão para DataFrame
* Criação de métricas:

  * Total de transações
  * Percentual de PF e PJ
* Agregação por região utilizando `groupby`

---

## 📊 Análise por Região

Foi realizada a agregação dos valores por região e o cálculo da participação percentual:

* **Perc_PJ = VL_PagadorPJ / Total**
* **Perc_PF = VL_PagadorPF / Total**

---

## 📈 Visualizações

### 🔹 Composição PF vs PJ por Região

![Composição PF vs PJ](./images/grafico_empilhado.png)

---

### 🔹 Participação de Pessoa Jurídica por Região

![Participação PJ](./images/grafico_pj.png)

---

### 🔹 Participação de Pessoa Física por Região

![Participação PF](./images/grafico_pf.png)

---

## 📊 Principais insights

* A região **Sul** apresenta a maior participação de pessoas jurídicas nas transações PIX
* A região **Sudeste** aparece em seguida, com valores próximos
* O uso de **percentuais** foi essencial para comparar regiões de diferentes tamanhos
* O gráfico de barras simples se mostrou mais eficiente para comparação direta entre regiões

---

## ⚠️ Qualidade dos dados

Foi identificada uma quantidade relevante de registros com a categoria **"Não informado"** na variável região.

Isso pode indicar:

* Falha no preenchimento
* Campo não obrigatório
* Problemas na coleta dos dados

Esses dados foram mantidos na análise, mas podem impactar a interpretação dos resultados.

---

## 🚀 Como executar o projeto

1. Clone o repositório:

```
git clone https://github.com/seu-usuario/analise-transacoes-pix-v2.git
```

2. Instale as dependências:

```
pip install -r requirements.txt
```

3. Execute o notebook:

```
jupyter notebook
```

---

## 📁 Estrutura do projeto

```
analise-transacoes-pix-v2/
│
├── data/
├── notebook/
├── images/
├── README.md
└── requirements.txt
```

---

## 📌 Autor

Projeto desenvolvido por André Alvino como estudo de análise de dados com Python.
