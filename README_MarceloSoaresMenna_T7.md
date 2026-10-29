Projeto Varejo - Análise Exploratória

Como Executar: Abra o arquivo script_varejo.ipynb no VS Code, garanta que o arquivo varejo.csv original está na mesma pasta e rode as células sequencialmente.

Reflexão Teórica (ETL e Qualidade de Dados)

O processo de ETL garantiu a confiabilidade dos dados através do diagnóstico de problemas e limpeza estrutural. A qualidade foi assegurada lidando com registros #N/D, imputando a string "Sem Categoria" para não perder volume analítico de clientes. Para as dimensões físicas, justificamos o uso da mediana na substituição de nulos para isolar o dataset de distorções provocadas por valores extremos (outliers). Também tomamos a decisão analítica de não excluir as linhas duplicadas, garantindo que o volume real de itens por cupom fiscal não fosse artificialmente reduzido.

Principais Insights (Conclusões) 

- Problemas Remanescentes: O alto volume de categorias #N/D indica uma falha no sistema de cadastro de produtos da loja, exigindo revisão na entrada de dados. 
- Desempenho de Vendas: O agrupamento demonstrou claramente qual a categoria de produto que lidera a saída no varejo. 
- Perfil Demográfico: As estatísticas descritivas apontam uma predominância de clientes com famílias pequenas (verificável pela moda e mediana da coluna CL_FHL). 
- Comportamento de Consumo: A média cruzada de filhos por gênero manteve-se estável, indicando pouca variação no perfil dos compradores, independentemente do sexo. 
- Alerta de Inconsistência Estrutural (Duplicatas): Foi identificado um altíssimo volume de linhas idênticas (mais de 96 mil). Como a base de dados não possui uma variável de "Quantidade" para diferenciar itens iguais comprados no mesmo cupom fiscal (CO_ID), optou-se pela não exclusão das duplicatas. Assumimos que cada linha idêntica representa a passagem de mais de um mesmo produto no caixa. Excluí-las causaria uma grave subnotificação do volume real de vendas. 
- Padrão de Consumo por Segmento (Classe): A análise adicional de agrupamento revelou o volume de compras distribuído pela classe do cliente (CL_SEG). Isso permite identificar qual perfil de consumidor movimenta a maior quantidade de itens na loja, entregando inteligência para campanhas de marketing e abastecimento de estoque mais direcionados.
