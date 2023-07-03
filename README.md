
Olá a todos, bem-vindos ao nosso tutorial de hoje, onde vamos explorar o emocionante mundo da análise financeira utilizando Python. Hoje, vamos focar-nos no Ethereum, uma das criptomoedas mais populares, e vamos utilizar alguns conceitos estatísticos chave: o desvio padrão e a distribuição normal.


Vamos começar com uma breve introdução a estes conceitos.

O desvio padrão é uma medida da quantidade de variação ou dispersão de um conjunto de valores. Um baixo desvio padrão indica que os valores tendem a estar próximos da média do conjunto, enquanto um alto desvio padrão indica que os valores estão dispersos numa gama mais ampla.

Por outro lado, a distribuição normal, também conhecida como curva de sino, é uma função que representa a distribuição de muitos conjuntos de dados na natureza e na sociedade, incluindo finanças.


Agora, vamos ver como podemos usar Python para obter os dados do Ethereum, calcular o desvio padrão e gerar uma distribuição normal. Para isso, vamos utilizar a biblioteca yfinance, que nos permite extrair dados financeiros do Yahoo Finance, e as bibliotecas numpy e scipy para os nossos cálculos e análises estatísticas.

Primeiro, precisamos de obter os dados do Ethereum.


# Importamos as bibliotecas necessárias
import yfinance as yf
import numpy as np
from scipy.stats import norm

# Baixamos os dados do Ethereum
eth_data = yf.download('ETH-USD', start='2020-01-01', end='2023-12-31')
Depois, podemos calcular o desvio padrão destes dados.


# Calculamos o desvio padrão dos preços de fecho
eth_std = np.std(eth_data['Close'])
print('Desvio padrão dos preços de fecho do Ethereum: ', eth_std)
Além disso, podemos ajustar os nossos dados a uma distribuição normal.


# Ajustamos os dados a uma distribuição normal
mu, std = norm.fit(eth_data['Close'])
print('Média: ', mu)
print('Desvio padrão: ', std)
Por fim, podemos gerar uma distribuição normal a partir dos nossos dados e visualizá-la.


import matplotlib.pyplot as plt

# Geramos uma distribuição normal
data_normal = np.random.normal(mu, std, 10000)

# Criamos um histograma para visualizar a distribuição
plt.hist(data_normal, bins=30, density=True, alpha=0.6, color='g')
plt.show()


E aí está, uma introdução básica sobre como você pode usar Python para realizar uma análise financeira do Ethereum utilizando o desvio padrão e a distribuição normal. Esperamos que este tutorial tenha sido útil para você, e lembre-se, você sempre pode aprofundar mais nesses conceitos e explorar outras bibliotecas e ferramentas Python para suas análises financeiras. Até a próxima!
