MVP — Pipeline de Dados na Nuvem (Olist E-commerce)

Autor: Pietro Santos Thompson da Cunha 

Este projeto constrói um pipeline de dados de ponta a ponta no Databricks (Unity Catalog e Delta Lake) a partir do dataset público de e-commerce da Olist (cerca de 100 mil pedidos entre 2016 e 2018, licença CC BY-NC-SA 4.0), com o objetivo de entender como o desempenho logístico se relaciona com a satisfação do cliente. As perguntas de negócio tratam do efeito do atraso e do frete nas notas de avaliação, das categorias e dos vendedores com mais atrasos e da receita e do ticket médio por estado.

O pipeline segue a Arquitetura Medalhão. Os CSVs são copiados do GitHub para um Volume e gravados como tabelas Delta na camada Bronze, sem transformação; a Silver faz a tipagem, remove duplicatas e mantém uma avaliação por pedido; e a Gold organiza um esquema estrela com a tabela fato fato_pedidos, no grão de um item de pedido. Os notebooks estão em notebooks/ e devem ser executados na ordem MVP → MVP-download → MVP-Bronze → MVP-Silver → MVP-Gold → MVP-Analise. O arquivo de geolocalização foi deixado de fora por ser pesado e desnecessário para as perguntas.

Os resultados mostram que o atraso é o fator mais associado à satisfação: a nota média cai de 4,23 para 1,69 entre as entregas com folga e as atrasadas em oito dias ou mais, enquanto o frete tem efeito bem menor. SP concentra 38,3% da receita, os maiores tickets médios estão no Norte e Nordeste, e o vendedor líder em receita atrasa 10,5% dos pedidos contra 3,0% do segundo colocado. São associações observadas, não relações de causa e efeito, e há pontos conhecidos que não foram tratados, como pedidos com datas inconsistentes e outliers.

O relatório completo (Word/PDF), com prints, gráficos, qualidade de dados e catálogo de dados, acompanha a entrega; os comentários de tabela e de coluna da camada Bronze foram gerados pela IA do Databricks. Dados: Brazilian E-Commerce Public Dataset by Olist.
