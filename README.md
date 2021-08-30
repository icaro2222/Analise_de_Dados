#                  Trabalho de Desenvolvimento para Análise de Dados  
### Desenvolvido por: Ícaro Dias dos Santos
---
#### Este presente trabalho tem por intuito mostrar de forma clara, a analise de dados do enem que compara aspectos dos candidatos considerados normais e candidatos com baixa Visão, também tem finalidade de destacar principis diferenças tanto na parte da nota tirada em cada prova como também das caracteristicas econimicas e sociais.
- Importação de módulos e bibliotecas
---
%matplotlib inline
import pandas as pd
import numpy as np
import matplotlib.patches as mpatches
import seaborn as sns
import matplotlib.pyplot as plt
- Neste primeiro tópico tem finalidade de pegar os dados do microdados do INEP; 
---
microdados_pd = pd.read_csv('F:/Trabalho/Project with Woquiton/Antigo/MICRODADOS_ENEM_2019.csv', sep= ';', encoding = "ISO-8859-1")
- Zero o meu microdados_pd principal, para que tem memoria.
# microdados_pd = 0
# microdados_pd.columns.values;
- Selecionando apenas as colunas que me serão uteis.
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
# microdadosFiltrados_pd = microdados_pd.filter(items=colunasParaMinhaAnalise_pd)
# microdadosFiltrados_pd = 0
# microPd = microdadosFiltrados_pd
microPd
#                  Filtrando Dados 
---
# colunasSociais = ['NU_IDADE', 'TP_SEXO', 'Q024', 'Q025', 'IN_BAIXA_VISAO', 'IN_CEGUEIRA', 'TP_COR_RACA']
# colunasProva = ['NU_NOTA_CN', 'NU_NOTA_CH', 'NU_NOTA_LC', 'NU_NOTA_MT']
# notasProvas = microPd.filter(items =colunasProva)
# QSociais = microPd.filter(items =colunasSociais)
- Removendo colunas com valor NaN
# internetNota = interNota.dropna()
# baixavisaoNota = visaoNota.dropna()
# internetVisao = interVisao.dropna()
# colunasSelecionadas = ['NU_NOTA_CN','Q025']
# interNota = microdados.filter(items =colunasSelecionadas)
# colunasSelecionadas1 = ['IN_BAIXA_VISAO','Q025']
# interVisao = microdados.filter(items =colunasSelecionadas1)
# colunasSelecionadas2 = ['NU_NOTA_CN','IN_BAIXA_VISAO']
# visaoNota = microdados.filter(items =colunasSelecionadas2)
##  Candidatos Normais
- Filtrando Dados dos Candidadtos de baixa Visão:
dadosNormais = microPd[microPd.IN_BAIXA_VISAO==0]
dadosN = dadosNormais

notaN_Cn = dadosN["NU_NOTA_CN"]
notaN_Ch = dadosN['NU_NOTA_CH']
notaN_Lc = dadosN['NU_NOTA_LC']
notaN_Mt = dadosN['NU_NOTA_MT']


baixavisaoN = dadosN['IN_BAIXA_VISAO']


pessoaN = dadosN["Q005"]
rendaN = dadosN["Q006"]
quartoN = dadosN["Q009"]
geladeiraN = dadosN["Q012"]
celularN = dadosN["Q022"]
computadorN = dadosN["Q024"]
internetN = dadosN["Q025"]
idadeAlunoN = dadosN["NU_IDADE"]
sexoAlunoN = dadosN["TP_SEXO"]
corN = dadosN["TP_COR_RACA"]
## Candidatos de Baixa Visão
- Filtrando Dados dos Candidadtos de baixa Visão:
dados = microPd[microPd.IN_BAIXA_VISAO==1]
notaCn = dados["NU_NOTA_CN"]
notaCh = dados['NU_NOTA_CH']
notaLc = dados['NU_NOTA_LC']
notaMt = dados['NU_NOTA_MT']


baixavisao = dados['IN_BAIXA_VISAO']


pessoa = dados["Q005"]
renda = dados["Q006"]
quarto = dados["Q009"]
geladeira = dados["Q012"]
celular = dados["Q022"]
computador = dados["Q024"]
internet = dados["Q025"]
idadeAluno = dados["NU_IDADE"]
sexoAluno = dados["TP_SEXO"]
cor = dados["TP_COR_RACA"]
#                  Resultado das Analises
---
## Fazendo comparações entre notas entre candidatos com baixa visão e visão normal
notaCns = notaCn.dropna()
idade = idadeAluno.dropna()
iN = idadeAlunoN

i = idadeAluno
- Gráfico com comparação de notas na máteria de ciência da natureza, entre candidatos com baixa vi~sao e visão normal.
y1 = notaN_Cn

y = notaCn
limits = [300, 960]
plt.figure(figsize = (17,5))

plt.scatter(y1, iN)
plt.scatter(y, i)
plt.xlim(limits)
plt.title('Ciências da Naturaza, Baixa Visão VS Visão Normal')
- Gráfico com comparação de notas na máteria de ciência humanas, entre candidatos com baixa vi~sao e visão normal.
y1 = notaN_Ch

y = notaCh
limits = [300, 960]
plt.figure(figsize = (17,5))

plt.scatter(y1, iN)
plt.scatter(y, i)
plt.xlim(limits)
plt.title('Ciências Humanas, Baixa Visão VS Visão Normal')
- Gráfico com comparação de notas na máteria de portuques, entre candidatos com baixa visão e visão normal.
y1 = notaN_Lc

y = notaLc
limits = [300, 960]
plt.figure(figsize = (17,5))

plt.scatter(y1, iN)
plt.scatter(y, i)
plt.xlim(limits)
plt.title('Linguagens, Baixa Visão VS Visão Normal')
- Gráfico com comparação de notas na máteria de matematica, entre candidatos com baixa vi~sao e visão normal.
y1 = notaN_Mt

y = notaMt
limits = [300, 960]
plt.figure(figsize = (17,5))

plt.scatter(y1, iN)
plt.scatter(y, i)
plt.xlim(limits)
plt.title('Matemática, Baixa Visão VS Visão Normal')
## Fazendo comparações entre notas entre candidatos com baixa visão e visão normal
##   Ciências Humanas AZUL
PROVA_CH = dados[dados.CO_PROVA_CH==507]
PROVA_CH.reset_index(inplace=True)

P = ['TX_RESPOSTAS_CH', 'TX_GABARITO_CH']
pch = PROVA_CH.filter(items = P)

respostasCH = pch['TX_RESPOSTAS_CH']
gabaritoCH = pch['TX_GABARITO_CH']

acertosN = [0]*45
for j in range(0, 45):
    
    for i in range(0, 135):
        linha_da_resposta = respostasCH[i]
        linha_do_gabarito = gabaritoCH[i]
        
        resposta_candidato = linha_da_resposta[j]
        resposta_gabarito = linha_do_gabarito[j]
        
        if resposta_candidato == resposta_gabarito:
            acertosN[j] = acertosN[j] + 1
            resposta_candidato = ''
            resposta_gabarito = ''

PROVA_CH_N = dadosN[dadosN.CO_PROVA_CH==507]
PROVA_CH_N.reset_index(inplace=True)

PN = ['TX_RESPOSTAS_CH', 'TX_GABARITO_CH']
pchN = PROVA_CH_N.filter(items = PN)

respostasCHN = pchN['TX_RESPOSTAS_CH']
gabaritoCHN = pchN['TX_GABARITO_CH']
acertos = [0]*45
for j in range(0, 45):
    for i in range(0, 135):
        linha_da_resposta = respostasCHN[i]
        linha_do_gabarito = gabaritoCHN[i]
        resposta_candidato = linha_da_resposta[j]
        resposta_gabarito = linha_do_gabarito[j]
        if resposta_candidato == resposta_gabarito:
            acertos[j] = acertos[j] + 1
            resposta_candidato = ''
            resposta_gabarito = ''

acertos_pd = pd.DataFrame(acertos)
acertosN_pd = pd.DataFrame(acertosN)
x = acertosN_pd
y = acertosN_pd.index


x1 = acertos_pd
y1 = acertos_pd.index

plt.scatter(y, x)
ax = plt.scatter(y1, x1)
plt.ylabel('Acertos', fontsize=18)
plt.xlabel('Questões', fontsize=18)
plt.title('Numero de Acertos:\nQuestões de Ciências da Natureza, AZUL.\n Baixa Visão VS Visão Normal', fontsize = 18)

limits = [-1,50]
limits1 = [0,135]
sec_lim = 1000
bp = 45

ax = plt.gca()
ax.set_xlim(limits)
ax.set_ylim(limits1)
ax.scatter(y, x, s=1, c='blue', alpha=1)
ax.scatter(y1, x1, s=1, c='red', alpha=1)

cores=['Baixa Visão', 'Visão Normal']
plt.legend(cores, bbox_to_anchor=(1.5, 1), loc='upper right')

plt.plot(x)
plt.plot(x1)
plt.show()
## Ciências Humanas AMARELA
PROVA_CH = dados[dados.CO_PROVA_CH==508]
PROVA_CH.reset_index(inplace=True)

P = ['TX_RESPOSTAS_CH', 'TX_GABARITO_CH']
pch = PROVA_CH.filter(items = P)

respostasCH = pch['TX_RESPOSTAS_CH']
gabaritoCH = pch['TX_GABARITO_CH']
acertosN = [0]*45


for j in range(0, 45):

    for i in range(0, 4183):
        linha_da_resposta = respostasCH[i]
        linha_do_gabarito = gabaritoCH[i]

        resposta_candidato = linha_da_resposta[j]
        resposta_gabarito = linha_do_gabarito[j]

        if resposta_candidato == resposta_gabarito:
            acertosN[j] = acertosN[j] + 1
            resposta_candidato = ''
            resposta_gabarito = ''

PROVA_CH_N = dadosN[dadosN.CO_PROVA_CH==508]
PROVA_CH_N.reset_index(inplace=True)
PN = ['TX_RESPOSTAS_CH', 'TX_GABARITO_CH']
pchN = PROVA_CH_N.filter(items = PN)

respostasCHN = pchN['TX_RESPOSTAS_CH']
gabaritoCHN = pchN['TX_GABARITO_CH']
acertos = [0]*45
for j in range(0, 45):
    for i in range(0, 4183):
        linha_da_resposta = respostasCHN[i]
        linha_do_gabarito = gabaritoCHN[i]

        resposta_candidato = linha_da_resposta[j]
        resposta_gabarito = linha_do_gabarito[j]

        if resposta_candidato == resposta_gabarito:
            acertos[j] = acertos[j] + 1
            resposta_candidato = ''
            resposta_gabarito = ''

acertos_pd = pd.DataFrame(acertos)
acertosN_pd = pd.DataFrame(acertosN)
x = acertosN_pd
y = acertosN_pd.index


x1 = acertos_pd
y1 = acertos_pd.index

plt.scatter(y, x)
ax = plt.scatter(y1, x1)
plt.ylabel('Acertos', fontsize=18)
plt.xlabel('Questões', fontsize=18)
plt.title('Numero de Acertos:\nCiências da Natureza, AMARELA.\n Baixa Visão VS Visão Normal', fontsize = 18)


limits = [-1,50]
limits1 = [0,4183]
sec_lim = 1000
bp = 45

ax = plt.gca()
ax.set_xlim(limits)
ax.set_ylim(limits1)
ax.scatter(y, x, s=1, c='blue', alpha=1)
ax.scatter(y1, x1, s=1, c='red', alpha=1)

cores=['Baixa Visão', 'Visão Normal']
plt.legend(cores, bbox_to_anchor=(1.5, 1), loc='upper right')

plt.plot(x)
plt.plot(x1)
plt.show()
## Ciências Humanas BRANCA
PROVA_CH = dados[dados.CO_PROVA_CH==509]
PROVA_CH.reset_index(inplace=True)
P = ['TX_RESPOSTAS_CH', 'TX_GABARITO_CH']
pch = PROVA_CH.filter(items = P)
respostasCH = pch['TX_RESPOSTAS_CH']
gabaritoCH = pch['TX_GABARITO_CH']
acertos = [0]*45
for j in range(0, 45):
    for i in range(0, 126):
        linha_da_resposta = respostasCHN[i]
        linha_do_gabarito = gabaritoCHN[i]
        resposta_candidato = linha_da_resposta[j]
        resposta_gabarito = linha_do_gabarito[j]
        if resposta_candidato == resposta_gabarito:
            acertos[j] = acertos[j] + 1
            resposta_candidato = ''
            resposta_gabarito = ''
PROVA_CH_N = dadosN[dadosN.CO_PROVA_CH==509]
PROVA_CH_N.reset_index(inplace=True)
PN = ['TX_RESPOSTAS_CH', 'TX_GABARITO_CH']
pchN = PROVA_CH_N.filter(items = PN)
respostasCHN = pchN['TX_RESPOSTAS_CH']
gabaritoCHN = pchN['TX_GABARITO_CH']
acertosN = [0]*45
for j in range(0, 45):
    
    for i in range(0, 123):
        linha_da_resposta = respostasCH[i]
        linha_do_gabarito = gabaritoCH[i]
        
        resposta_candidato = linha_da_resposta[j]
        resposta_gabarito = linha_do_gabarito[j]
        
        if resposta_candidato == resposta_gabarito:
            acertosN[j] = acertosN[j] + 1
            resposta_candidato = ''
            resposta_gabarito = ''
acertos_pd = pd.DataFrame(acertos)
acertosN_pd = pd.DataFrame(acertosN)
x = acertosN_pd
y = acertosN_pd.index


x1 = acertos_pd
y1 = acertos_pd.index

plt.scatter(y, x)
ax = plt.scatter(y1, x1)
plt.ylabel('Acertos', fontsize=18)
plt.xlabel('Questões', fontsize=18)
plt.title('Numero de Acertos:\nQuestões de Ciências da Natureza, BRANCA.\n Baixa Visão VS Visão Normal', fontsize = 18)


limits = [-1, 45]
limits1 = [0,123]
bp = 45

ax = plt.gca()
ax.set_xlim(limits)
ax.set_ylim(limits1)
ax.scatter(y, x, s=1, c='blue', alpha=1)
ax.scatter(y1, x1, s=44, c='red', alpha=1)

cores=['Baixa Visão', 'Visão Normal']
plt.legend(cores, bbox_to_anchor=(1.5, 1), loc='upper right')

plt.plot(x)
plt.plot(x1)
plt.show()
## Ciências Humanas ROSA
PROVA_CH = dados[dados.CO_PROVA_CH==510]
PROVA_CH.reset_index(inplace=True)
P = ['TX_RESPOSTAS_CH', 'TX_GABARITO_CH']
pch = PROVA_CH.filter(items = P)
respostasCH = pch['TX_RESPOSTAS_CH']
gabaritoCH = pch['TX_GABARITO_CH']
acertos = [0]*45
for j in range(0, 45):
    
    for i in range(0, 126):
        linha_da_resposta = respostasCH[i]
        linha_do_gabarito = gabaritoCH[i]
        
        resposta_candidato = linha_da_resposta[j]
        resposta_gabarito = linha_do_gabarito[j]
        
        if resposta_candidato == resposta_gabarito:
            acertos[j] = acertos[j] + 1
            resposta_candidato = ''
            resposta_gabarito = ''
PROVA_CH_N = dadosN[dadosN.CO_PROVA_CH==510]
PROVA_CH_N.reset_index(inplace=True)
PN = ['TX_RESPOSTAS_CH', 'TX_GABARITO_CH']
pchN = PROVA_CH_N.filter(items = PN)
respostasCHN = pchN['TX_RESPOSTAS_CH']
gabaritoCHN = pchN['TX_GABARITO_CH']
acertosN = [0]*45
for j in range(0, 45):
    for i in range(0, 126):
        linha_da_resposta = respostasCHN[i]
        linha_do_gabarito = gabaritoCHN[i]
        resposta_candidato = linha_da_resposta[j]
        resposta_gabarito = linha_do_gabarito[j]
        if resposta_candidato == resposta_gabarito:
            acertosN[j] = acertosN[j] + 1
            resposta_candidato = ''
            resposta_gabarito = ''
acertos_pd = pd.DataFrame(acertos)
acertosN_pd = pd.DataFrame(acertosN)
x = acertosN_pd
y = acertosN_pd.index


x1 = acertos_pd
y1 = acertos_pd.index

plt.scatter(y, x)
ax = plt.scatter(y1, x1)
plt.ylabel('Acertos', fontsize=18)
plt.xlabel('Questões', fontsize=18)
plt.title('Numero de Acertos:\nQuestões de Ciências da Natureza, ROSA.\n Baixa Visão VS Visão Normal', fontsize = 18)

limits = [-1,50]
limits1 = [0,126]
sec_lim = 1000
bp = 45

ax = plt.gca()
ax.set_xlim(limits)
ax.set_ylim(limits1)
ax.scatter(y, x, s=1, c='blue', alpha=1)
ax.scatter(y1, x1, s=1, c='red', alpha=1)

cores=['Baixa Visão', 'Visão Normal']
plt.legend(cores, bbox_to_anchor=(1.5, 1), loc='upper right')

plt.plot(x)
plt.plot(x1)
plt.show()
