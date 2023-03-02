import pandas as pd
import yfinance as yf
import numpy as np

ticker = 'BTC-USD'
start_date = "2021-01-01"
end_date = "2023-03-02"

data = yf.download(ticker, start=start_date, end=end_date)

# Selecionar a coluna "Adj Close" e calcular os retornos
retorno = data['Close']
retorno = retorno.pct_change()
volatilidade = retorno.std() * 100

confianca = 0.95  # nível de confiança desejado
dias = 1  # horizonte de tempo em dias
var = np.abs(retorno.quantile(1 - confianca) * data['Close'].iloc[-1])  # cálculo do VaR

print(f'Volatilidade: {volatilidade:.2f}%')
print(f'VaR a {confianca:.0%} de confiança para {dias} dia(s): {var:.2f}')
