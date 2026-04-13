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

<img width="1218" height="449" alt="image" src="https://github.com/user-attachments/assets/6f53a060-91e2-4c3b-8d81-2f66b748d767" />


### 🔹 Participação de Pessoa Jurídica por Região

<img width="826" height="448" alt="image" src="https://github.com/user-attachments/assets/10d49ec8-cb6d-496f-8c03-7d3e8f130551" />


### 🔹 Participação de Pessoa Física por Região

<img width="826" height="451" alt="image" src="https://github.com/user-attachments/assets/52746082-e787-4c4d-95f1-22d1e534d75d" />


## 📈 Principais Insights

- A região Sul apresenta a maior participação proporcional de Pessoas Jurídicas (PJ) no volume de transações PIX em 2024, indicando uma maior concentração relativa de atividade empresarial em comparação às demais regiões.

- O Sudeste aparece logo em seguida, mantendo valores próximos ao Sul, o que reforça seu papel como principal polo econômico do país em termos de movimentação financeira via PIX.

- Em todas as regiões analisadas, as transações de Pessoas Físicas (PF) representam a maior parte do volume total, evidenciando a predominância do uso do PIX no contexto de consumo e transferências pessoais.

- A presença de registros classificados como “Não informado” indica possíveis limitações na qualidade ou completude da base de dados, o que pode impactar análises mais granulares.

- A análise percentual foi fundamental para normalizar a comparação entre regiões com diferentes volumes absolutos de transações, permitindo uma leitura mais justa da distribuição entre PF e PJ.
---

## ⚠️ Limitações dos Dados

- Presença de registros “Não informado”, que podem afetar análises regionais mais precisas
- Ausência de granularidade temporal mais detalhada
- Possíveis inconsistências na coleta ou padronização dos dados

Esses dados foram mantidos na análise, mas podem impactar a interpretação dos resultados.
## 📌 Conclusão

A análise das transações PIX em 2024 evidencia uma forte predominância de Pessoas Físicas em todas as regiões do Brasil, enquanto a participação de Pessoas Jurídicas varia de forma mais concentrada em regiões economicamente mais desenvolvidas, como Sul e Sudeste.

Os resultados sugerem diferenças estruturais no perfil de uso do PIX entre regiões, possivelmente relacionadas ao nível de atividade econômica e concentração empresarial.

## 🧰 Ferramentas Utilizadas

- Python
- Pandas
- Matplotlib
- Jupyter Notebook

## 🎯 Problema de Negócio

Entender como se distribuem as transações PIX entre Pessoas Físicas e Jurídicas no Brasil em 2024, e identificar padrões regionais que possam indicar diferenças de comportamento econômico.

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

## 📌 Autor

Projeto desenvolvido por André Alvino como estudo de análise de dados com Python.
