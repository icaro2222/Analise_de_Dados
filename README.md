#                  Trabalho de Desenvolvimento para Análise de Dados  
### Desenvolvido por: Ícaro Dias dos Santos
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
