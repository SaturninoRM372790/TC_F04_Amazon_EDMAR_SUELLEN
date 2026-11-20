# Guia do avaliador — Tech Challenge Fase 4

**FIAP Pós-Tech Data Analytics · Grupo 160**  
Edmar Saturnino César (RM372790) · Francisca Suellen Soares Barros (RM372732)

## Entrega e onde localizar os materiais

A submissão institucional foi planejada como **um arquivo ZIP** contendo:

| Material | Arquivo previsto | Finalidade |
|---|---|---|
| Dashboard Power BI Desktop | `01_POWER_BI/TC_F04_Amazon_Insights_v01.pbix` | Principal artefato interativo |
| Apresentação executiva | `02_VIDEO/Tech_Challenge_Fase 4_EDMAR_SUELLEN_FIAP.mp4` | Vídeo de até 7 minutos, **sem YouTube** |
| Notebook de auditoria | `03_COLAB/TC_F04_00_Validacao_Ambiente.ipynb` | Procedimentos, resultados e registros |
| Base original | `04_DADOS/ORIGINAL/01.amazon.csv` | Proveniência e preservação |
| Base tratada principal | `04_DADOS/POWER_BI/amazon_t4_05_desconto_pct_v01.csv` | Fonte principal do painel |
| Resumo de NLP | `04_DADOS/POWER_BI/amazon_nlp_e6_2_v2_temas_resumo.csv` | Segunda fonte do painel |

**Atenção:** a lista acima descreve a organização **prevista** do ZIP. Não é confirmação de submissão à FIAP nem de que todos os arquivos estão publicados neste GitHub. Os links deste repositório apontam apenas para documentos efetivamente disponíveis.

## Como verificar o Power BI

1. Obter o `.pbix` no pacote entregue à FIAP, instalar/abrir no **Power BI Desktop**.
2. Conferir a página **00 — Auditoria** e as páginas executivas **01 — Visão Executiva**, **02 — Produtos e Categorias**, **03 — Preços e Estratégia Comercial**, **04 — Customer Insights**, **05 — Recomendações Executivas**.
3. Verificar os KPI e comparações por categoria; analisar as notas metodológicas.
4. Para **atualizar dados**, será necessário adequar no Power Query os caminhos dos dois arquivos CSV à máquina do avaliador. A reabertura do arquivo foi validada no computador do projeto; **não foi testada atualização em outra máquina**.

## Como verificar o Colab

1. Abrir o notebook `TC_F04_00_Validacao_Ambiente.ipynb` disponibilizado no pacote institucional.
2. Examinar o código, as células de documentação e, onde presentes, as saídas de execução.
3. Consultar os registros **PBI-38** (preços e descontos por categoria) e **PBI-39** (faixas de desconto) e confrontar com os visuais do PBIX.
4. Para reexecução, disponibilizar os CSVs do pacote no Google Drive e **ajustar caminhos**. Não confundir trechos documentais com células efetivamente executadas.

## Indicadores selecionados

- 1.465 registros; 1.351 produtos distintos; 9 categorias principais.
- Concentração das três principais categorias: **97,19%** dos produtos distintos.
- Desconto médio por registro: **47,69%**; 751 registros (**51,26%**) com descontos anunciados de pelo menos 50%.
- 1.212 blocos distintos de `review_content`; menções temáticas globais: preço/custo-benefício **76,57%**, qualidade/durabilidade **75,74%**, funcionamento/desempenho **68,98%**.

## Integridade, limitações e testes

- Conferir nomes, funções e hashes dos arquivos em [MANIFESTO_DADOS.md](MANIFESTO_DADOS.md).
- Preços em **rupias indianas (INR)**; preços não são faturamento, descontos não comprovam margem, quantidade de reviews não equivale a vendas ou consumidores únicos.
- Temas de NLP **podem se sobrepor** e sua presença **não mede sentimento**; análise é global, não filtrada por categoria.
- Resultados de PBI-38 e PBI-39 foram conciliados conforme saídas fornecidas da execução do Colab. PBI-36 (filtros da página Customer Insights) **não foi executado**, por decisão do grupo.
- Não há modelo preditivo validado apresentado como resultado.
- Fontes originais e artefatos devem ser preservados; não redistribuir materiais didáticos restritos da FIAP.

**Status desta documentação:** orientação publicada no GitHub em 20/11/2026. A integridade do ZIP final e a submissão à FIAP precisam de validação posterior.
