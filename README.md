# 📊 Pesquisa Nacional por Amostra de Domicílios – PNAD 2015 (IBGE)

Este repositório apresenta uma análise descritiva e exploratória de um subconjunto da **Pesquisa Nacional por Amostra de Domicílios (PNAD) – 2015**, conduzida pelo **IBGE**. O objetivo é aplicar técnicas estatísticas e ferramentas de análise de dados para compreender aspectos sociodemográficos da população brasileira, especialmente das **Pessoas de Referência dos domicílios**.

A análise foi realizada com Python e bibliotecas como `pandas`, `seaborn` e `matplotlib`, `scipy.stats(binom/norm)`seguindo os princípios de clareza, organização e fundamentação estatística.

---

## 🎯 Objetivos do Projeto

- Explorar a estrutura e qualidade dos dados;
- Calcular medidas estatísticas (tendência central, dispersão, separatrizes);
- Visualizar distribuições e comparações entre grupos;
- Evidenciar desigualdades raciais, de gênero, regionais e educacionais;
- Consolidar a análise com interpretações técnicas baseadas nos dados.
- Distribuição binomial aplicada à probabilidade de ocorrência de perfis populacionais (ex: chefes de domicílio do sexo masculino);
- Cálculo da média esperada de eventos;
- Planejamento de amostragem com base em orçamento, margem de erro e nível de confiança;
- Estimativa da média populacional;
- Cálculo da nova margem de erro com base nos recursos disponíveis;
- Determinação do custo total da pesquisa conforme o nível de confiança.
  
---

## 🗂️ Estrutura dos Dados

A base utilizada contém informações apenas das Pessoas de Referência dos domicílios.

| Coluna            | Descrição                                                        |
|-------------------|------------------------------------------------------------------|
| UF                | Unidade Federativa                                               |
| Sexo              | Masculino / Feminino                                             |
| Idade             | Em anos completos                                                |
| Cor               | Cor ou raça declarada (5 categorias do IBGE)                     |
| Anos.de.Estudo    | Total de anos de escolaridade                                    |
| Renda             | Renda mensal principal (em reais)                                |
| Altura            | Variável didática criada para análise de distribuição (em metros)|

---

## 🛠️ Tratamentos Aplicados

- Exclusão de registros com `Renda` inválida ou ausente;
- Filtro para manter apenas Pessoas de Referência;
- Conversão e mapeamento de variáveis categóricas;
- Criação de variável `Altura` (valores simulados);
- Normalização de colunas e categorias para fins analíticos.
---

## 🔍 Análises Realizadas

### 📌 Distribuição de Registros por Estado (UF)

![Quantidade de registros por UF (Estado)](https://github.com/user-attachments/assets/7b57a435-ff59-42d5-89ba-b84d8c98f5eb)

São Paulo e Minas Gerais apresentam o maior volume, enquanto Amapá, Roraima e Alagoas registram as menores quantidades. Este padrão reflete uma concentração de registros nas regiões Sudeste e Sul, diminuindo nas demais, o que sugere uma correlação com a distribuição populacional.

---

### 👤 Frequência por Sexo e Cor

### Tabela de Frequência Absoluta – Sexo x Cor

| Sexo       | Amarela | Branca | Indígena | Parda | Preta |
|------------|---------|--------|----------|-------|-------|
| Feminino   | 117     | 9621   | 101      | 10862 | 2889  |
| Masculino  | 235     | 22194  | 256      | 25063 | 5502  |

### Tabela de Frequência Relativa (%) – Sexo x Cor

| Sexo       | Amarela | Branca | Indígena | Parda | Preta |
|------------|---------|--------|----------|-------|-------|
| Feminino   | 0.50    | 40.78  | 0.43     | 46.04 | 12.25 |
| Masculino  | 0.44    | 41.68  | 0.48     | 47.07 | 10.33 |

A amostra indica predominância das etnias Parda e Branca nos domicílios. Há um desequilíbrio de gênero, com acentuada maioria masculina em todas as categorias raciais.

---

### 💰 Renda Média por Sexo e Cor

### Dados Agrupados – Sexo x Cor

| Sexo       | Amarela | Branca | Indígena | Parda | Preta |
|------------|---------|--------|----------|-------|-------|
| Feminino   | 3027.34 | 2109.87| 2464.39  | 1176.76| 1134.60|
| Masculino  | 4758.25 | 2925.74| 1081.71  | 1659.58| 1603.86|

A análise da renda média revela que, majoritariamente, homens percebem valores superiores às mulheres, exceto na categoria Indígena, onde o inverso ocorre. Em termos raciais, indivíduos da etnia Amarela possuem as maiores rendas médias, enquanto Parda e Preta apresentam as menores, destacando marcantes disparidades de gênero e raça.

---

### 📈 Medidas de Tendência Central – Renda

### Medidas de Tendência Central

| Medida  | Valor    |
|---------|----------|
| Média   | 2000.38  |
| Mediana | 1200.00  |
| Moda    | 788,00   |

A grande diferença entre a média, mediana e moda indica uma distribuição de renda assimétrica e concentrada. A média elevada, puxada por outliers de alta renda, mascara que a maioria dos indivíduos possui rendimentos significativamente menores, evidenciando forte concentração de renda nas mãos de poucos.

---

### 📍 Top 5 Estados por Média Salarial
![Top 5 Estados pela Média de Renda](https://github.com/user-attachments/assets/0a1fcfcd-4557-47c7-96d8-ae2a5fe9d256)


Distrito Federal possui a maior média de renda, com uma diferença expressiva. Os demais estados no topo são do Sudeste e Sul, indicando uma acentuada desigualdade regional e concentração econômica nessas áreas do país.

---

### 📊 Distribuição de Altura e Idade
![Distribuicao da altura e idade](https://github.com/user-attachments/assets/bb9700db-75f7-4f16-ac0e-757775473930)

A distribuição da Altura é quase simétrica e mesocúrtica (com curtose similar à de uma distribuição normal), similar a uma curva normal. Já a da Idade apresenta leve assimetria positiva e tendência platicúrtica, com a maior concentração etária entre os 30 e 60 anos.

---

### 🔻 Renda até R$ 15.000 – Histograma com Regra de Sturges
![Distribuição da Renda de Pessoas Responsáveis (até R$15 000, Escala Logarítmica)](https://github.com/user-attachments/assets/1fd678c1-069f-4a65-8091-4ede14ac49e2)

A distribuição de renda mostra alta concentração de baixa renda (0 - R$5.000) e uma cauda longa com poucos indivíduos nas faixas mais altas, evidenciando grande desigualdade.

---

### 📦 Boxplot da Renda até 6 mil
![Distribuição da Renda (até R$6.000)](https://github.com/user-attachments/assets/7f29ec6b-1ab9-47e4-bf46-63ab98564d54)

O boxplot da renda mostra uma distribuição altamente assimétrica: a mediana (R$ 1.200) e a maioria (50% central) concentram-se em baixa renda. A presença de numerosos outliers de alta renda, estendendo-se muito além do corpo principal dos dados, evidencia uma desigualdade estrutural e profunda concentração de renda.

---

### 📦 Boxplot por Sexo e Cor (até Percentil 95%)
![Distribuição da Renda (até 95º percentil) por Sexo e Cor](https://github.com/user-attachments/assets/03b01749-d507-4d24-8ec0-87369a56f86e)

Os dados revelam que as etnias Parda e Preta são as mais vulneráveis economicamente, com destaque para as mulheres desses grupos. Os homens indígenas também apresentam significativa vulnerabilidade de renda.

---

### 🧒 Histograma Acumulado da Idade (Percentil 20%)
![Histograma Acumulado da Idade com Densidade](https://github.com/user-attachments/assets/d4118672-8559-4f09-898a-75d4143a3927)

O gráfico mostra que 20% da população tem até 33 anos, indicando uma amostra com perfil demográfico mais maduro e relativamente pouca população jovem, com implicações para planejamento e análises futuras.

---

### 📉 Medidas de Dispersão – Renda

### Medidas de Dispersão

| Medida de Dispersão  | Valor       |
|----------------------|-------------|
| Desvio Médio Absoluto| 1526.50     |
| Variância            | 11044906.01 |
| Desvio Padrão        | 3323.39     |

As altas medidas de dispersão, notadamente o Desvio Padrão (R$ 3323,39) ser maior que a média, confirmam a extrema variabilidade e forte assimetria na distribuição da renda, evidenciando a acentuada desigualdade e a influência de outliers de alta renda.

---

### 🎓 Estatísticas por Escolaridade

### Renda por Nível de Escolaridade

| **Anos de Estudo** | **Média** | **Mediana** | **Desvio Padrão** |
|---------------------------|-----------|-------------|-------------------|
| Sem instrução e menos de um ano | 732.99    | 600.0       | 955.27            |
| 1 ano                     | 806.52    | 700.0       | 1203.87           |
| 2 anos                    | 842.56    | 788.0       | 1298.87           |
| 3 anos                    | 980.04    | 788.0       | 1907.14           |
| 4 anos                    | 1150.44   | 900.0       | 1293.14           |
| 5 anos                    | 1183.58   | 940.0       | 1328.71           |
| 6 anos                    | 1284.08   | 1000.0      | 1326.14           |
| 7 anos                    | 1289.17   | 1000.0      | 1279.41           |
| 8 anos                    | 1437.74   | 1100.0      | 1404.28           |
| 9 anos                    | 1315.69   | 1000.0      | 1888.37           |
| 10 anos                   | 1495.90   | 1100.0      | 1817.68           |
| 11 anos                   | 1841.67   | 1350.0      | 2457.20           |
| 12 anos                   | 2185.77   | 1500.0      | 3452.73           |
| 13 anos                   | 2758.77   | 2000.0      | 2638.84           |
| 14 anos                   | 3099.84   | 2100.0      | 3413.36           |
| 15 anos ou mais           | 5242.44   | 3500.0      | 6450.49           |
| Não determinados          | 1071.72   | 900.0       | 825.58            |

- A análise revela uma tendência clara: quanto maior a escolaridade, maior a média de renda.
- Os níveis baixos de instrução concentram as menores rendas e menor variabilidade.
- A dispersão aumenta com o nível educacional, refletindo oportunidades mais amplas (inclusive de rendimentos mais altos).
  
---

### 👨‍👩‍👧 Comparativo de Renda até R$15.000 – por Sexo

### Renda por Sexo

| Sexo       | Média   | Mediana | Desvio Padrão |
|------------|---------|---------|---------------|
| Feminino   | 1460.14 | 900.0   | 1763.69       |
| Masculino  | 1964.35 | 1300.0  | 2101.16       |


Os dados explicitam que mulheres possuem renda média e mediana consistentemente inferiores às dos homens. A menor dispersão entre as rendas femininas pode, de fato, indicar menor variabilidade salarial ou acesso mais restrito a posições de alta remuneração. Esta diferença é um indicador claro da persistência da desigualdade salarial de gênero, mesmo considerando faixas de renda intermediárias.

---

### 🗺️ Região Centro-Oeste – Renda até R$10.000 por UF e Sexo
![Distribuição da Renda (até R$10 000) na Região Centro-Oeste por Sexo](https://github.com/user-attachments/assets/4b9c501b-f2c6-4c43-971d-42e5a9962e6c)

A análise das rendas na Região Centro-Oeste revela persistente desigualdade salarial de gênero, com mulheres ganhando menos que homens em todos os estados. Há também grande disparidade entre estados, com o Distrito Federal exibindo rendas significativamente superiores aos demais estados da região.

---

## 📚 Notbook – Estatística 

### Distribuição Binomial 

A Distribuição Binomial foi utilizada para calcular a probabilidade de que, em um grupo de 10 pessoas sorteadas aleatoriamente, exatamente 7 sejam homens e 3 sejam mulheres.

A fórmula empregada é:

$$P(X=k) = \binom{n}{k} \cdot p^k \cdot (1-p)^{n-k}$$

**Onde:**

* $P(X=k)$: Probabilidade de obter exatamente  $k$  sucessos.
* $n$: Número total de tentativas (tamanho do grupo).
* $k$: Número de sucessos desejados (neste caso, o número de homens).
* $p$: Probabilidade de sucesso em uma única tentativa (probabilidade de ser homem).
* $\binom{n}{k}$: Coeficiente binomial, que representa o número de combinações de $n$ elementos tomados $k$ a $k$.

### Resultado

Com $n=10$, $k=7$ e $p=0.70$ (70% de chefes de domicílio sendo homens), o cálculo resultou em **0.26682793**.

Portanto, há cerca de **26.68% de chance** de um grupo de 10 pessoas, sorteadas aleatoriamente sob essas condições, conter exatamente 7 homens e 3 mulheres.

---

### Média da Distribuição Binomial

A **Média da Distribuição Binomial** foi utilizada para estimar quantos grupos de 10 pessoas seria necessário sortear, em média, para obter **100 grupos com a composição desejada**: exatamente 7 homens e 3 mulheres por grupo.

A fórmula empregada é:

$$
\text{Número médio de tentativas} = \frac{\text{Número de sucessos desejados}}{\text{Probabilidade de sucesso por tentativa}}
$$

**Onde:**

* Número de sucessos desejados = 100 grupos com a composição (7 homens);
* Probabilidade de sucesso por tentativa = 0{,}26682793
  (calculada anteriormente com a Distribuição Binomial: $n = 10$, $k = 7$, $p = 0{,}70$)

### Resultado

$$
\frac{100}{0{,}26682793} \approx 375
$$

Portanto, **seriam necessários, em média, 375 grupos sorteados** para atingir o objetivo de formar **100 grupos contendo exatamente 7 homens e 3 mulheres**.

---

### Estimativa da Renda Média: AAS 🇧🇷


Projeto para estimar a renda média dos chefes de domicílio no Brasil via **Amostragem Aleatória Simples (AAS)**, respeitando limites orçamentários e de prazo.


### 📝 Resumo do Projeto

| Parâmetro             |        Detalhe                                          |
| :---------------------| :------------------------------------------------------ |
| **Objetivo**          | Estimar a renda média dos chefes de domicílio no Brasil |
| **Metodologia**       | Amostragem Aleatória Simples (AAS)                      |
| **Prazo**             | 2 meses                                                 |
| **Orçamento**         | R\$ 150.000,00                                          |
| **Custo/Entrevista**  | R\$ 100,00                                              |
| **Margem de Erro**    | 10% da média                                            |
| **Nível de Confiança**| 95%                                                     |

### Tamanho da Amostra

Com base em:
* Média Observada ($\bar{X}$): R\$ 1964,21
* Desvio Padrão (S): R\$ 3139,89
* Valor de Z (95% conf.): 1,96
* Erro (E): 10% de $\bar{X}$ = R\$ 196,42

A fórmula para o tamanho da amostra ($n$) é:

$$n = \frac{Z^2 \cdot S^2}{E^2}$$


$$n = \frac{1.96^2 \cdot 3139.89^2}{196.42^2} \approx \textbf{983 entrevistas}$$


### Viabilidade

O projeto é viável:

### ✅ Viabilidade

O projeto é viável:

* **Custo:** R$ 98.300,00 (983 ⋅ R$ 100), abaixo do orçamento de R$ 150.000,00.
* **Prazo:** 983 entrevistas em 2 meses (≈16-17 por dia) é realizável com planejamento.

---

## 🧠 Conclusões Gerais

- A **distribuição de renda** evidenciou **alta assimetria à direita**, com forte concentração em faixas de valores baixos. A média elevada, influenciada por outliers, não representa adequadamente a condição da maioria da população analisada.  
- As **desigualdades mais acentuadas** ocorrem nas interseções de **gênero e cor/raça**, com **mulheres pretas e pardas** ocupando as posições de maior vulnerabilidade socioeconômica.  
- As **regiões Sudeste e Centro-Oeste**, em especial o **Distrito Federal**, concentram as maiores rendas médias, revelando disparidades econômicas significativas entre as Unidades Federativas.  
- A **escolaridade demonstra correlação positiva com a renda**, especialmente nos níveis mais elevados. No entanto, **o avanço educacional, por si só, não elimina as desigualdades estruturais** existentes, indicando limitações do capital humano como único vetor de mobilidade.  
- Por fim, os dados reforçam a necessidade de **políticas públicas que incorporem recortes interseccionais (gênero, raça, região e educação)** para que sejam eficazes no combate à desigualdade social e na promoção de equidade no acesso a oportunidades.

---

> 📚 *Este notebook é parte das atividades práticas dos cursos "Estatística com Python: Resumindo e Analisando Dados", da Alura, ministrado pela instrutora Danielle Oliveira e "Estatística com Python: probabilidade e amostragem" ministrado pelo instrutor: Rodrigo Fernando Dias.
