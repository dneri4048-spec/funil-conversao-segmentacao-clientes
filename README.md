# Funil de Conversão e Segmentação de Clientes

## Sobre o projeto
Análise de funil de conversão e segmentação comportamental de 8 mil clientes, 
com foco em identificar em qual etapa ocorre a maior perda e quais segmentos 
(canal, faixa etária, tipo de campanha) apresentam melhor performance.

## Ferramentas
Power BI Desktop (Power Query, DAX)

## Fonte de dados
Predict Conversion in Digital Marketing Dataset (Kaggle) — 8 mil registros 
no nível de cliente individual, com dados demográficos, comportamentais 
(visitas, e-mails, compartilhamentos) e resultado de conversão.

## Processo técnico
- Correção de erro de localidade em múltiplas colunas numéricas simultaneamente 
  (Power Query, conversão de tipo "Usando Local")
- Remoção de colunas sem valor analítico (campos censurados/placeholder)
- Criação de faixas etárias customizadas via coluna condicional
- Construção de funil sequencial via medidas DAX (CALCULATE + FILTER), 
  corrigindo uma inconsistência inicial onde a etapa de "engajamento" 
  não era um subconjunto lógico da etapa de "visita" (erro de lógica OU vs E)

## Principais achados
- A maior perda de clientes ocorre entre a etapa de engajamento e a 
  conversão final (~10,65%), sugerindo que o esforço de otimização deveria 
  focar em remover fricção na etapa final (checkout, formulário, oferta), 
  não necessariamente em atrair mais tráfego
- O tipo de campanha "Conversion" apresenta taxa de conversão superior às 
  demais, consistente com a expectativa de que campanhas de fundo de funil 
  convertem mais que campanhas de topo de funil (Awareness)
- Canal de aquisição e faixa etária não mostraram variação significativa 
  de conversão entre si

## Observações sobre os dados
A taxa de conversão geral (87,65%) é muito superior à média real de mercado 
(tipicamente 2-10%), o que é esperado neste dataset sintético — construído 
originalmente para treinamento de modelos de classificação (predição de 
conversão), não para refletir benchmarks reais de marketing. A metodologia 
de segmentação e construção de funil aplicada, no entanto, é a mesma usada 
em análises de dados reais.
