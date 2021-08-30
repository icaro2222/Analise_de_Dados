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
---llllllllllllllllllllllllllllllll
# ipynb

[![Build Status](https://travis-ci.org/yuvipanda/ipynb.svg?branch=master)](https://travis-ci.org/yuvipanda/ipynb)

A python package providing an easy way to explicitly import [Jupyter Notebooks](https://github.com/jupyter/notebook) files (`.ipynb`) the same way you would import regular `.py` files.

## Installation ##

You can install ipynb with:

```bash
pip install ipynb
```

## Importing a notebook ##

### Full import ###

You can do a 'full' import - this has the same semantics of importing a .py file. All the code in the .ipynb file is executed, and classes/functions/variables in the top level are available for use.

If you have a notebook file named `server.ipynb`, you can import it via:

```python
import ipynb.fs.full.server
```

You can use the `from ... import ..` too.

```python
from ipynb.fs.full.server import X, Y, X
```

### Definitions only import ###

Sometimes your notebook has been used as a way to run an analysis or other computation, and you only want to import the functions / classes defined in it - and not the extra statements you have in there. This can be accomplished via `ipynb.fs.defs`.

If you have a notebook file named `server.ipynb`, and do:

```python
import ipynb.fs.defs.server
```

It'll only execute and make available the following parts of the code in `server.ipynb`:
 - `class` definitions
 - `def` function definitions
 - `import` statements
 - Assignment statements where the variables being assigned to are ALL_CAPS. These are assumed to be constants.

This skips most computational work and brings in your definitions only, making it easy to reuse functions / classes across similar analyses.

### Relative Imports ###

You can also easily do relative imports, both for full notebooks or for definitions only. This works inside notebooks too.

If you have a notebook called `notebook1.ipynb` in the same dir as your current notebook, you can import it with:

```python
import ipynb.fs  # Boilerplate required

# Do a full import
from .full.notebook1 import foo

# Do a definitions-only import
from .defs.notebook1 import bar
```

This works transitively nicely - other code can import your notebook that's using relative imports and it'll all work well.
