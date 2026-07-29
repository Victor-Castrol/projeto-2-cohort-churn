# Análise de Cohort e Previsão de Churn — E-commerce
Segundo projeto do meu portfólio de dados. A ideia é entender o comportamento
de recompra dos clientes de um e-commerce e, a partir disso, treinar um modelo
que aponta quais clientes têm maior risco de abandonar a loja.

# Perguntas que o projeto responde
- Quantos clientes voltam a comprar depois da primeira compra?
- Como a retenção varia entre grupos de clientes (cohorts) mês a mês?
- Quais clientes têm maior probabilidade de churn nos próximos 90 dias?

# Dataset
Online Retail II: transações de um e-commerce do Reino Unido entre 2009 e 2011,
com cerca de 1 milhão de linhas. As colunas incluem número da fatura, produto,
quantidade, data, preço e código do cliente.

# Etapas
1. Limpeza dos dados (devoluções, valores nulos, registros inválidos)
2. Análise de cohort com heatmap de retenção mensal
3. Criação de variáveis RFM (recência, frequência, valor monetário)
4. Definição de churn e treino do modelo Random Forest
5. Avaliação do modelo e análise das variáveis mais importantes

# Ferramentas
- Python (pandas, matplotlib, seaborn)
- scikit-learn
- Google Colab

# Status
Em desenvolvimento.

![Heatmap de retenção por cohort](heatmap_retencao.png)
