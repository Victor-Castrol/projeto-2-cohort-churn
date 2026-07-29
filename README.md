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


## O que os dados mostraram

- Quase todo mundo some depois da primeira compra. A retenção cai de 100% pra
  algo entre 14% e 35% logo no primeiro mes. O problema real da loja é fazer
  o cliente voltar pela segunda vez.
- A turma de dez/2009 é fora da curva. Enquanto as outras seguram uns 10-25%,
  essa fica entre 26% e 50% durante dois anos. Minha leitura: são os
  atacadistas antigos da loja, que já compravam antes e recompram todo mes.
- Perto de setembro/outubro a retenção sobe em várias turmas. Faz sentido,
  é loja de presente, o pessoal volta pra montar estoque de Natal.
