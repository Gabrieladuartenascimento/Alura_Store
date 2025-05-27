# Alura Store
# Desafio de Análise de Dados de Lojas

Este repositório contém a resolução de um desafio de análise de dados focado no desempenho de múltiplas lojas. O objetivo principal foi extrair insights valiosos sobre faturamento, vendas por categoria, avaliações de clientes, tendências de frete e uma estimativa de "lucro" por loja, tudo isso através da manipulação e visualização de dados.

## 🚀 Tecnologias Utilizadas

* **Python:** Linguagem de programação principal.
* **Pandas:** Biblioteca fundamental para manipulação e análise de dados tabulares.
* **Matplotlib:** Biblioteca para criação de gráficos estáticos e personalizáveis.
* **Seaborn:** Biblioteca de visualização de dados baseada no Matplotlib, oferecendo gráficos mais atraentes e estatísticos.

## 📊 Estrutura dos Dados

O desafio consistiu em analisar 4 datasets independentes, onde cada dataset representava os dados de transações de uma loja específica. A estrutura de cada dataset, conforme visualizado, incluía colunas como:

* `Produto`
* `Categoria do Produto`
* `Preço`
* `Frete`
* `Data da Compra`
* `Vendedor`
* `Local da compra`
* `Avaliação da compra`
* `Tipo de pagamento`
* `Quantidade de parcelas`
* `1st Ion`

## ✨ Análises e Aprendizados Realizados

Durante este desafio, foram executadas diversas análises, resultando em importantes aprendizados sobre manipulação, agregação e visualização de dados:

### 1. Faturamento por Loja

**O que foi feito:**
Calculou-se o faturamento total de cada loja. Inicialmente, a ideia era multiplicar `Preço` por `Quantidade`, mas, ao constatar a ausência da coluna `Quantidade`, optou-se por somar a coluna `Preço` como uma estimativa de faturamento bruto para cada transação e, em seguida, o faturamento total da loja.

**Aprendizados:**
* A importância de validar a existência e o significado das colunas.
* Como adaptar a metodologia de cálculo diante de dados faltantes ou diferentes.
* Utilização de `.sum()` para agregação total de uma coluna.

### 2. Vendas por Categoria em Cada Loja

**O que foi feito:**
Para cada loja, o faturamento (baseado na soma dos `Preço`s) foi agrupado por `Categoria do Produto` para entender quais categorias geram mais receita em cada estabelecimento. Os resultados foram visualizados em gráficos de barras individuais por loja.

**Aprendizados:**
* Uso de `groupby()` para agregar dados por categorias.
* Aplicações de `.sum()` em grupos para obter totais por categoria.
* Criação de múltiplos gráficos para comparar o desempenho de categorias entre diferentes entidades (lojas).
* Personalização de gráficos com `matplotlib.pyplot` e `seaborn` (títulos, rótulos, rotação de ticks, paletas de cores).

### 3. Média de Avaliação das Lojas

**O que foi feito:**
Foi calculada a média das `Avaliação da compra` para cada loja. Esta métrica foi então incorporada nos gráficos de faturamento por categoria como uma linha de referência, e também em um gráfico de barras separado para comparar as médias de avaliação entre todas as lojas.

**Aprendizados:**
* Cálculo de médias com `.mean()`.
* Adição de linhas de referência (`plt.axhline`) em gráficos para contextualizar dados.
* Interpretação da correlação entre faturamento e satisfação do cliente (via avaliação).

### 4. Produtos Mais e Menos "Vendidos" em Cada Loja (Baseado no Frete)

**O que foi feito:**
Dada a ausência da coluna `Quantidade`, o `Frete` foi utilizado como um *proxy* para o volume de "vendas" ou a importância logística de um produto. Agrupou-se os dados por `Produto` e somou-se o `Frete` para cada um, identificando os produtos com maior e menor custo total de frete. Dois gráficos de barras horizontais foram gerados por loja: um para os produtos com maior soma de frete e outro para os com menor.

**Aprendizados:**
* A criatividade na análise de dados quando as métricas diretas não estão disponíveis, utilizando proxies e justificando as suposições.
* Uso de `groupby()` combinado com `sum()` para agregação por produto.
* Utilização de `.nlargest()` e `.nsmallest()` para encontrar os top/bottom N elementos.
* Criação de gráficos de barras horizontais para melhor legibilidade de nomes de itens.

### 5. Frete Médio por Loja

**O que foi feito:**
Calculou-se o frete médio para cada loja, oferecendo um panorama dos custos de envio típicos de cada estabelecimento. O resultado foi visualizado em um gráfico de barras comparando o frete médio entre as lojas.

**Aprendizados:**
* Cálculo de médias simples para uma coluna específica.
* Comparação visual de métricas entre diferentes entidades em um único gráfico.

### 6. Comparação de "Lucro" entre Lojas

**O que foi feito:**
Foi feita uma estimativa de "lucro" para cada loja, subtraindo o custo total do frete do faturamento bruto (soma dos preços). A loja com o menor resultado nessa métrica foi identificada.

**Aprendizados:**
* A importância de definir claramente as métricas financeiras com base nos dados disponíveis.
* Limitações de uma análise de lucro sem dados completos de custo (custo do produto, operacionais, etc.).
* Cálculos de métricas compostas a partir de dados existentes.
* Identificação de valores mínimos em um dicionário ou série Pandas.

## 💡 Conclusão

Este desafio proporcionou uma imersão prática na análise de dados, desde a limpeza e preparação (implícita no carregamento e entendimento da estrutura), passando por diversas agregações e cálculos, até a visualização efetiva para comunicar insights. A necessidade de adaptar a análise devido à ausência de colunas específicas (`Quantidade`) reforçou a importância da flexibilidade e do pensamento crítico em projetos de Data Analytics.
[link do colab]:(https://colab.research.google.com/drive/1UaQsiuvW0J6Eya97HbfHfPRakwm72rDs?usp=sharing)
---


