**Análise de Cancelamento de Cartões de Crédito**

**Desafio**
Você trabalha em uma grande empresa de cartões de crédito e o diretor da empresa notou um aumento significativo no número de clientes que cancelam seus cartões, resultando em grandes prejuízos. O objetivo deste projeto é analisar os dados dos clientes para identificar aqueles com maior tendência a cancelar seus cartões e propor estratégias para reduzir essa taxa de cancelamento.

Base de Dados
O projeto utiliza uma base de dados contendo informações sobre clientes atuais e aqueles que cancelaram seus cartões. A base de dados pode ser baixada aqui.

# Passos do Projeto
    * Importar a base de dados
    * Visualizar e tratar a base de dados
    * Analisar a estrutura da base de dados
    * Identificar os motivos de cancelamento dos cartões
    

# Importar a base de dados
tabela = pd.read_csv("/content/drive/MyDrive/Minicurso Análise de Dados/ClientesBanco.csv", encoding="latin1")
tabela = tabela.drop("CLIENTNUM", axis=1)
display(tabela)
Análise Inicial
python
Copiar código
# Remover valores ausentes
tabela = tabela.dropna()
display(tabela.info())
display(tabela.describe().round(2))

# Avaliar a divisão entre Clientes X Cancelados
qtde_categoria = tabela["Categoria"].value_counts()
display(qtde_categoria)
qtde_categoria_perc = tabela["Categoria"].value_counts(normalize=True)
display(qtde_categoria_perc)
Visualização de Dados
Através da visualização, podemos observar tendências entre os clientes e os cancelados:

# Construção do gráfico
import plotly.express as px

for coluna in tabela:
    grafico = px.histogram(tabela, x=coluna, color="Categoria")
    grafico.show()
Insights da Análise
A análise revelou algumas tendências importantes:

    **Clientes com mais produtos contratados têm menor probabilidade de cancelar.**
    **Aumentos no número de transações e no valor médio das transações estão associados a uma menor chance de cancelamento.**
    **Maior número de contatos realizados pelo cliente correlaciona-se com uma maior taxa de cancelamento.**


# Conclusão:

O projeto oferece uma visão clara sobre os fatores que influenciam o cancelamento de cartões de crédito. Com essas informações, a empresa pode desenvolver estratégias direcionadas para reduzir a taxa de cancelamento e melhorar a retenção de clientes.

# Referências
Base de Dados - [Kaggle](https://www.kaggle.com/sakshigoyal7/credit-card-customers)
