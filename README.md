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

👩‍💻 Autora

Helli — Data Analytics | UX | Branding | Automação
🔗 Se quiser, geramos aqui também o texto da bio para o GitHub.
