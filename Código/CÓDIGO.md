```python
import pandas as pd
import matplotlib.pyplot as plt
```


# 1. CARREGAMENTO DOS DADOS

```
df = pd.read_json('data/transacoes_pix.json')
df = pd.DataFrame(df['value'].tolist())
```

# 2. EXPLORAÇÃO INICIAL

```python
print(df.head())
print(df.info())
print(df.describe())
```


# 3. ANÁLISE POR ESTADO
```python
estado = df.groupby('Estado')[['VL_PagadorPJ', 'VL_PagadorPF']].sum()

estado['Total'] = estado['VL_PagadorPJ'] + estado['VL_PagadorPF']
estado['Perc_PJ'] = estado['VL_PagadorPJ'] / estado['Total']
estado['Perc_PF'] = estado['VL_PagadorPF'] / estado['Total']

top_estados = estado.sort_values(by='Total', ascending=False).head(5)
print(top_estados)
```

# 4. ANÁLISE POR REGIÃO
```python
regiao = df.groupby('Regiao')[['VL_PagadorPF', 'VL_PagadorPJ']].sum()

regiao['Total'] = regiao['VL_PagadorPF'] + regiao['VL_PagadorPJ']
regiao['Perc_PF'] = regiao['VL_PagadorPF'] / regiao['Total']
regiao['Perc_PJ'] = regiao['VL_PagadorPJ'] / regiao['Total']

regiao = regiao.sort_values(by='Perc_PJ', ascending=True)
```


# 5. VISUALIZAÇÃO DOS DADOS
```python
plt.figure(figsize=(15, 5))

plt.bar(regiao.index, regiao['Perc_PF'], label='Pessoa Física')
plt.bar(
    regiao.index,
    regiao['Perc_PJ'],
    bottom=regiao['Perc_PF'],
    label='Pessoa Jurídica'
)

plt.title('Distribuição PF vs PJ por Região')
plt.legend()
plt.show()
```


# 6. COMPARAÇÕES INDIVIDUAIS
```python
plt.figure(figsize=(10, 5))
plt.bar(regiao.index, regiao['Perc_PJ'])
plt.title('Participação de PJ por Região')
plt.show()

plt.figure(figsize=(10, 5))
plt.bar(regiao.index, regiao['Perc_PF'])
plt.title('Participação de PF por Região')
plt.show()
```
