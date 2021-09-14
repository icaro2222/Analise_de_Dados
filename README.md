#                  Trabalho de Desenvolvimento para Análise de Dados  
### Desenvolvido por: Ícaro Dias dos Santos
# ipynb

![Build Status](https://travis-ci.org/yuvipanda/ipynb.svg?branch=master)
---
#### Este presente trabalho tem por intuito mostrar de forma clara, a analise de dados do enem que compara aspectos dos candidatos considerados normais e candidatos com baixa Visão, também tem finalidade de destacar principis diferenças tanto na parte da nota tirada em cada prova como também das caracteristicas econimicas e sociais.
- Importação de módulos e bibliotecas
---
```python
%matplotlib inline
```
```python
import pandas as pd
import numpy as np
import matplotlib.patches as mpatches
import seaborn as sns
import matplotlib.pyplot as plt
```
- Neste primeiro tópico tem finalidade de pegar os dados do microdados do INEP; 
---
```python
microdados_pd = pd.read_csv('F:/Trabalho/Project with Woquiton/Antigo/MICRODADOS_ENEM_2019.csv', sep= ';', encoding = "ISO-8859-1")
```
```python
# microdados_pd = 0
```
```python
# microdados_pd.columns.values;
```
```python
colunasParaMinhaAnalise_pd =['NU_INSCRICAO',
       'NU_IDADE', 'TP_SEXO', 'TP_COR_RACA', 'TP_ESCOLA',
       'IN_BAIXA_VISAO', 'IN_CEGUEIRA',
       'TP_PRESENCA_CN', 'TP_PRESENCA_CH', 'TP_PRESENCA_LC',
       'TP_PRESENCA_MT', 'CO_PROVA_CN', 'CO_PROVA_CH', 'CO_PROVA_LC',
       'CO_PROVA_MT', 'NU_NOTA_CN', 'NU_NOTA_CH', 'NU_NOTA_LC',
       'NU_NOTA_MT', 'TX_RESPOSTAS_CN', 'TX_RESPOSTAS_CH',
       'TX_RESPOSTAS_LC', 'TX_RESPOSTAS_MT', 'TP_LINGUA',
       'TX_GABARITO_CN', 'TX_GABARITO_CH', 'TX_GABARITO_LC',
       'TX_GABARITO_MT', 'NU_NOTA_REDACAO', 
        'Q001', 'Q002', 'Q003', 'Q004', 'Q005', 'Q006',
       'Q007', 'Q008', 'Q009', 'Q010', 'Q011', 'Q012', 'Q013', 'Q014',
       'Q015', 'Q016', 'Q017', 'Q018', 'Q019', 'Q020', 'Q021', 'Q022',
       'Q023', 'Q024', 'Q025']
```
```python
# microdadosFiltrados_pd = microdados_pd.filter(items=colunasParaMinhaAnalise_pd)
```
```python
# microdadosFiltrados_pd = 0
```
```python
# microPd = microdadosFiltrados_pd
```
```python
microPd
```
```python
# microdadosFiltrados_pd = microdados_pd.filter(items=colunasParaMinhaAnalise_pd)
```
```python
# microdadosFiltrados_pd = 0
```
```python
# microPd = microdadosFiltrados_pd
```
```python
microPd
```

