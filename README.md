## Análise de Cohort e Previsão de Churn — E-commerce

Segundo projeto do meu portfólio de dados. Peguei as transações de um
e-commerce do Reino Unido (Online Retail II, cerca de 1 milhão de linhas
entre 2009 e 2011) pra entender quantos clientes voltam a comprar depois
da primeira compra e, na sequência, treinar um modelo que aponta quais
clientes têm maior risco de abandonar a loja.

## Etapas

1. Limpeza dos dados (devoluções, valores nulos, registros inválidos) — feito
2. Análise de cohort com heatmap de retenção mensal — feito
3. Criação de variáveis RFM (recência, frequência, valor monetário) — feito
4. Features comportamentais + treino do modelo Random Forest — feito
5. Avaliação do modelo e análise das variáveis mais importantes — feito

## Retenção por cohort

![Heatmap de retenção por cohort](heatmap_retencao.png)

Cada linha do heatmap é uma turma de clientes, agrupada pelo mes da primeira
compra. As colunas mostram quantos % dessa turma voltaram a comprar 1, 2, 3...
meses depois. Quanto mais escuro, mais gente voltou.

O que eu vi nos dados:

- A retenção despenca logo no primeiro mes: de 100% pra uma faixa de 14% a
  35%, dependendo da turma. A maior parte dos clientes compra uma vez e não
  volta. O desafio real dessa loja não é atrair cliente, é conseguir a
  segunda compra.
- A turma de dez/2009 é diferente de todas as outras. Segura retenção entre
  26% e 43% por dois anos e chega a bater 50% no decimo mes. Como dez/2009
  é o primeiro mes do dataset, minha leitura é que essa turma carrega os
  clientes antigos da loja, muitos deles atacadistas que recompram todo mes.
- Tem sazonalidade clara: em varias turmas a retenção volta a subir entre
  setembro e outubro. Faz sentido pra uma loja de artigos de presente, os
  revendedores voltam pra montar estoque de fim de ano.
- A turma de dez/2010 foi a pior de todas, rodando entre 3% e 12% quase o
  tempo inteiro. Provavelmente cliente de Natal: comprou presente uma vez
  e nunca mais apareceu.

## Previsão de churn

Depois do cohort, o passo seguinte foi prever quais clientes ativos têm
maior risco de abandonar a loja. Separei os dados em dois períodos: o
passado gera as variáveis do modelo, o futuro serve só pra observar quem
de fato deu churn. Sem essa separação o modelo enxergaria o futuro e os
números sairiam inflados (data leakage).

Além do RFM tradicional, criei variáveis de comportamento: variedade de
produtos comprados, ticket médio, ritmo de compra em dias e tempo como
cliente.

## Resultado do Random Forest:

- AUC-ROC de 0.79
- Recall de 82% na classe churn: de cada 100 clientes que realmente
  abandonariam a loja, o modelo pega 82 antes de irem embora
- As variáveis comportamentais respondem por 49% do poder preditivo do
  modelo. O RFM sozinho não capturava metade da história.

![Importância das variáveis](feature_importance.png)

O que eu vi nos dados:

- Dias desde a última compra segue sendo o fator mais forte (23.6%), mas
  variedade de produtos e ticket médio juntos pesam mais que o valor
  total gasto. Cliente que compra pouca variedade tende a sumir, mesmo
  gastando bem.
- Frequência bruta virou a variável menos importante (8.8%). O ritmo de
  compra e o tempo como cliente capturam a mesma informação de forma
  mais rica.

## Ferramentas

Python (pandas, matplotlib, seaborn), scikit-learn, Google Colab.


