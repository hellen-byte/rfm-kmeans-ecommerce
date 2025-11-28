📊 Segmentação de Clientes com RFM + K-Means para E-commerce

## 📌 Índice
- [Descrição Geral](#descrição-geral)
- [Objetivos](#objetivos)
- [Etapas Realizadas](#etapas-realizadas)
- [Resultados e Insights](#resultados-e-insights)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Como Rodar o Projeto](#como-rodar-o-projeto)
- [Autora](#autora)



🧩 Descrição Geral

Este projeto aplica metodologias de análise de clientes amplamente utilizadas no mercado — RFM (Recência, Frequência e Valor) e Clusterização via K-Means — para identificar padrões de comportamento em uma base de pedidos de um e-commerce fictício.

A partir de 1000 pedidos e 363 clientes, construí uma segmentação completa que permite:

identificar clientes mais valiosos,

detectar clientes em risco,

localizar oportunidades de upsell,

e orientar estratégias de marketing personalizadas.

O resultado final é uma estrutura analítica que poderia ser integrada diretamente ao CRM ou ao time de Growth da empresa.

🧠 Objetivos do Projeto

Criar uma segmentação inteligente utilizando a metodologia RFM.

Rankear clientes por comportamento de compra.

Implementar um modelo de clusterização não supervisionado (K-Means).

Comparar segmentos algorítmicos com segmentos de negócio.

Gerar insights acionáveis de marketing e retenção.

Apresentar resultados de forma clara e visual.

🧹 Etapas Executadas
1. Exploração e Tratamento dos Dados

1000 pedidos

14 variáveis (data, categoria, cliente, frete, receita etc.)

Criação de métricas: receita bruta, desconto, receita líquida

2. Cálculo da RFM

Para cada cliente foram calculados:

Recência (dias desde a última compra)

Frequência (número de compras)

Valor Monetário (total gasto)

3. Criação dos Scores RFM (1 a 5)

Recência (5 = compra recente)

Frequência (5 = compra frequente)

Valor (5 = gasta muito)

Combinação resultou em códigos como 555, 421, 233…

4. Segmentação RFM

Criei categorias como:

TOP (Campeões)

Leais

Frequentes

Alto Valor

Atenção

Em risco

5. Clusterização com K-Means

Padronização (StandardScaler)

Teste de k pelo método do cotovelo

Clusters definidos com k = 4

Análise dos perfis médios de cada cluster

6. Visualizações

Receitas por categoria e por canal

Distribuição de pedidos

Gráficos de RFM

Scatterplot dos clusters

Curva ABC

Top 10 clientes por receita

📈 Principais Resultados
Cluster 0 — Clientes em risco

Recência altíssima

Baixo valor e frequência
➡ Estratégia: campanhas de reativação

Cluster 1 — Clientes valiosos

Recência média

Alta frequência

Ticket alto
➡ Estratégia: programa VIP, conteúdo exclusivo

Cluster 2 — Super Premium

Maior valor e maior frequência
➡ Estratégia: retenção forte, reconhecimento, NPS, comunidade

Cluster 3 — Ativos de baixo ticket

➡ Estratégia: Upsell, cross-sell

🛠 Tecnologias Utilizadas

Python

Pandas

NumPy

Matplotlib

Seaborn

Scikit-Learn

📁 Estrutura do Repositório
📦 rfm-kmeans-ecommerce
 ┣ 📂 data
 ┣ 📂 notebooks
 ┣ 📂 img
 ┣ 📄 README.md
 ┣ 📄 requirements.txt
 ┗ 📄 rfm_kmeans.ipynb

A análise de outliers mostrou uma cauda longa de vendas de alto valor, com 6–12 transações fora do padrão dependendo do método (Z-score ou IQR). Esses valores representam compras de ticket alto, não erros, e indicam um grupo de clientes premium que contribui desproporcionalmente para a receita. Eles foram mantidos porque são cruciais para entender comportamento, estratégias de upsell e clusterização.

1. Receita Líquida — Cauda longa forte (modelo típico de e-commerce)

A média está acima da mediana (R$ 1.090 vs R$ 894), mostrando assimetria positiva.
Tradução:
➡️ a maior parte dos pedidos tem receita baixa/média
➡️ poucos pedidos de ticket alto puxam o faturamento lá pra cima

O CV de 0.75 confirma:
➡️ o comportamento de compra é extremamente heterogêneo
➡️ clientes e produtos têm valores MUITO diferentes entre si

Insight: esse tipo de cauda longa é clássico em e-commerce e indica espaço para estratégias de upsell, combos e clusterização de clientes de alto valor (que você já fez no RFM/K-Means).

2. Valor Unitário — Produtos bem distribuídos, mas com faixa de preço ampla

Assimetria praticamente zero (skew = −0.01).
➡️ a distribuição é equilibrada
➡️ não existem produtos extremamente caros que distorcem o conjunto

Mas o CV de 0.55 mostra:
➡️ existe uma variação natural entre categorias (moda, beleza, eletrônicos…)
➡️ o portfólio é diversificado e atinge vários bolsos

Insight: ideal para campanhas segmentadas por faixa de preço.

3. Quantidade — Clientes compram poucas unidades

Média de 3 unidades por pedido.
Quase simétrico.
Variação moderada-alta.

➡️ maioria compra entre 1 e 4 itens
➡️ não existe compra em volume (B2B)
➡️ comportamento típico de varejo B2C

Insight: kits e bundles podem aumentar o AOV (Average Order Value).

4. Frete — Política de frete ampla, variando por região/distância

CV 0.56 mostra dispersão alta.
Assimetria quase zero.

➡️ existe política de frete variada
➡️ possivelmente influenciada por regiões/categorias/peso

Insight: dá para investigar frete por cidade no futuro — isso vira KPI de eficiência logística.

O e-commerce apresenta uma distribuição de receita altamente assimétrica, com poucos pedidos de alto valor responsáveis por grande parte do faturamento. O portfólio é diversificado, com ampla variação de preços e compras em pequenas quantidades, típico de varejo B2C. A política de frete é heterogênea e merece análise regional. A partir dessas estatísticas, identificamos oportunidades diretas de otimização: segmentação de clientes de alto valor, kits de produtos para aumentar o ticket médio e revisão de fretes por cidade.

A clusterização K-Means revelou 4 perfis de clientes no e-commerce:
✔ Um grupo de clientes de alto valor e alta frequência (Champions)
✔ Clientes frequentes, porém de gasto moderado (Potenciais Leais)
✔ Clientes com compras esporádicas (Em Risco)
✔ E clientes inativos com baixo valor (Baixa Prioridade)

Essas segmentações são fundamentais para ações de marketing mais inteligentes, personalização e otimização de CAC/LTV.”

👩‍💻 Autora

Helli — Data Analytics | UX | Branding | Automação
🔗 Se quiser, geramos aqui também o texto da bio para o GitHub.
