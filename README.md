# Análise de Cohort e Previsão de Churn — E-commerce

Segundo projeto do meu portfólio de dados. Peguei as transações de um
e-commerce do Reino Unido (Online Retail II, ~1 milhão de linhas entre
2009 e 2011) pra entender quantos clientes voltam a comprar depois da
primeira compra e, na sequência, treinar um modelo que aponta quem tá
prestes a abandonar a loja.

## Etapas

1. Limpeza dos dados (devoluções, valores nulos, registros inválidos) — feito
2. Análise de cohort com heatmap de retenção mensal — feito
3. Criação de variáveis RFM (recência, frequência, valor monetário)
4. Definição de churn e treino do modelo Random Forest
5. Avaliação do modelo e análise das variáveis mais importantes

## Retenção por cohort

![Heatmap de retenção por cohort](heatmap_retencao.png)

Cada linha é uma turma de clientes agrupada pelo mes da primeira compra.
As colunas mostram quantos % voltaram 1, 2, 3... meses depois. Quanto mais
escuro, mais gente voltou.

[AQUI ENTRAM OS TEUS ACHADOS - escreve com as tuas palavras o que você
viu no gráfico: a queda do primeiro mes, a turma de dez/2009, o Natal]

## Ferramentas

Python (pandas, matplotlib, seaborn), scikit-learn, Google Colab.
