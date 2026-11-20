# Manifesto de dados e rastreabilidade — Fase 4

**Grupo 160 · Amazon Product Performance & Customer Insights**  
**Data do registro documental:** 20/11/2026

| Arquivo | Papel | Dimensão registrada | Alimenta o Power BI? |
|---|---|---|---|
| `01.amazon.csv` | Base original imutável | 1.465 linhas × 16 colunas | **Não diretamente** |
| `amazon_t4_05_desconto_pct_v01.csv` | Base principal tratada | 1.465 linhas × 22 colunas no CSV | **Sim** |
| `amazon_nlp_e6_2_v2_temas_resumo.csv` | Agregado temático NLP global | 6 linhas × 4 colunas | **Sim** |

## SHA-256 registrados nas evidências anteriores

| Arquivo | Hash SHA-256 |
|---|---|
| `01.amazon.csv` | `4BA126C4BA8EDD35E62E94CE1C853073D832DE380184AB4F5F97D1E314882C77` |
| `amazon_t4_05_desconto_pct_v01.csv` | `5EFDD045F3FF6165FDC5865305E744A14E7227F82654DD23983613026194EAA6` |
| `amazon_nlp_e6_2_v2_temas_resumo.csv` | `1e4b16df3b1b0e8fac2b780390e479fdd96f963a1211ba499240b1070aa0efa4` |

**Origem dos hashes:** registros de governança informados no projeto; o hash da base principal foi reconfirmado nas saídas do Colab apresentadas em PBI-38 e PBI-39. O hash do resumo NLP corresponde ao registro de exportação informado anteriormente. **Esta publicação não significa que os CSVs foram reabertos ou recalculados aqui.**

## Linhagem

1. **Original:** `01.amazon.csv`, preservado no Drive em `01_DADOS_ORIGINAIS/`.
2. **Tratamento:** `amazon_t4_05_desconto_pct_v01.csv`, no Drive em `02_DADOS_TRATADOS/`. Esta tabela sustenta os visuais de produtos, categorias, preços, descontos, avaliações e engajamento. A coluna `categoria_principal_pt` e as medidas DAX foram criadas no Power BI, sem alterar o CSV original.
3. **NLP:** `amazon_nlp_e6_2_v2_temas_resumo.csv`, no Drive em `02_DADOS_TRATADOS/`. Colunas `tema_pt`, `textos_identificados`, `total_textos_distintos`, `percentual`. Resume 6 temas não exclusivos sobre **1.212 blocos distintos**. Importada no Power BI como **tabela desconectada**, de escopo global.
4. **Reprodução e verificação:** notebook `TC_F04_00_Validacao_Ambiente.ipynb` e PBIX `TC_F04_Amazon_Insights_v01.pbix`.

## Evidências analíticas

- **PBI-38:** Colab × Power BI — medianas de preços e descontos médios das três maiores categorias: **3 de 3 comparações aprovadas** (duas casas decimais); nove categorias recalculadas no Colab, mas apenas três conciliadas diretamente com o BI.
- **PBI-39:** Contagem de faixas: `234 / 480 / 572 / 179`, total **1.465**, **4 de 4** aprovadas; descontos de pelo menos 50%: **751 (51,26%)**.
- **PBI-34:** reabertura do PBIX informada como validada; **PBI-35:** interatividade da página Produtos e Categorias informada como validada; **PBI-36:** teste funcional de Customer Insights não executado por decisão do grupo.

## Limitações e responsabilidades

- **Não confundir preço com receita, review com venda ou menção temática com sentimento.**
- Categorização em 9 categorias principais e 211 caminhos completos, conforme evidências do projeto.
- Antes de publicar CSVs em repositório **público**, conferir os direitos de redistribuição da fonte e eventual presença de dados pessoais, segredos ou informações identificáveis.
- Arquivos originais, tratados e de NLP precisam ser copiados do Drive efetivamente para o ZIP da FIAP; não se deve inferir sua presença apenas pela referência documental.
