# Tech Challenge — Fase 4 | Amazon Product Performance & Customer Insights

**FIAP · Pós-Tech Data Analytics · Grupo 160**  
**Integrantes:** Edmar Saturnino César (RM372790) e Francisca Suellen Soares Barros (RM372732)

> **Objetivo:** compreender a composição do catálogo Amazon, os preços e descontos anunciados, o engajamento medido por avaliações e os assuntos recorrentes nos comentários, transformando evidências em recomendações executivas.  
> **Projeto acadêmico independente:** dashboard inspirado nas cores da Amazon, **não** produto oficial da empresa.

## 🧭 Comece por aqui

- **[Guia do avaliador](docs/GUIA_DO_AVALIADOR.md)** — como abrir, conferir e interpretar os entregáveis.
- **[Manifesto das bases e hashes SHA-256](docs/MANIFESTO_DADOS.md)** — fonte original → dados tratados → Power BI/NLP.
- **[Endereço do repositório (TXT)](docs/LINK_REPOSITORIO_GITHUB.txt)** — referência a incluir no ZIP enviado à FIAP.

### Entrega principal à FIAP

O pacote ZIP previsto para a plataforma institucional reúne:

| Entregável | Arquivo previsto | Finalidade |
|---|---|---|
| **Dashboard** | `TC_F04_Amazon_Insights_v01.pbix` | Power BI Desktop, 6 páginas (00 auditoria + 5 executivas) |
| **Apresentação executiva** | `Tech_Challenge_Fase 4_EDMAR_SUELLEN_FIAP.mp4` | Vídeo de apresentação, **sem YouTube** |
| **Notebook** | `TC_F04_00_Validacao_Ambiente.ipynb` | Procedimentos Python, análises, registros e validações |
| **Base original** | `01.amazon.csv` | Proveniência dos dados |
| **Dados do Power BI** | `amazon_t4_05_desconto_pct_v01.csv`; `amazon_nlp_e6_2_v2_temas_resumo.csv` | Tabelas realmente usadas no painel |

**Importante:** o ZIP e os arquivos binários/dados acima **ainda não estão comprovadamente presentes neste repositório**. Os nomes indicam os entregáveis confirmados no trabalho, mas não links de download do GitHub. A verificação do conteúdo do ZIP e a submissão na FIAP permanecem etapas posteriores.

## 📊 Painéis Power BI

| Página | Questão de negócio |
|---|---|
| **00 — Auditoria** | Conferência de indicadores e evidências |
| **01 — Visão Executiva** | Qual o panorama do catálogo e sua concentração? |
| **02 — Produtos e Categorias** | Quais categorias se destacam em mix, preços e descontos? |
| **03 — Preços e Estratégia Comercial** | Como se distribuem os preços e descontos anunciados? |
| **04 — Customer Insights** | O que mostram as avaliações e as menções nos comentários? |
| **05 — Recomendações Executivas** | Onde aprofundar as análises para apoiar decisões? |

## 📈 Resultados principais

| Indicador | Resultado |
|---|---:|
| Registros na base principal | **1.465** |
| Produtos distintos | **1.351** |
| Categorias principais | **9** |
| Concentração das 3 maiores categorias | **97,19%** dos produtos distintos |
| Avaliação média por produto | **4,09 / 5** |
| Desconto médio por registro | **47,69%** |
| Registros com desconto anunciado ≥ 50% | **751 (51,26%)** |
| Blocos distintos de comentários analisados | **1.212** |

**NLP exploratório (temas sobrepostos):** menções a preço/custo-benefício em **76,57%**, qualidade/durabilidade em **75,74%** e funcionamento/desempenho em **68,98%** dos textos distintos.

## 🗂️ Bases e transformação

| Arquivo | Papel | Importado no Power BI? |
|---|---|---|
| `01.amazon.csv` | Original preservado, 1.465 × 16 | Não diretamente |
| `amazon_t4_05_desconto_pct_v01.csv` | Principal, 1.465 × 22 no CSV | **Sim** |
| `amazon_nlp_e6_2_v2_temas_resumo.csv` | Resumo NLP, 6 × 4 | **Sim, tabela desconectada** |

O Power BI inclui transformações e medidas adicionais; o NLP é **global**, sem segmentação dinâmica por categoria. Ver [manifesto](docs/MANIFESTO_DADOS.md) para hashes, rastreabilidade e cautelas.

## 🔎 Reprodução e evidências

1. Obter o pacote institucional entregue à FIAP; abrir o `.pbix` no Power BI Desktop.
2. Navegar pelas seis páginas. A reabertura do PBIX foi confirmada no ambiente do projeto; a atualização em outro computador ainda não foi testada.
3. Examinar o notebook no Colab e as saídas salvas, distinguindo procedimentos efetivamente executados de registros documentais.
4. Para reexecutar, disponibilizar os CSVs e **ajustar os caminhos do Google Drive** (Colab) e do Power Query (Power BI).
5. Conferir os hashes informados no [manifesto](docs/MANIFESTO_DADOS.md) com os arquivos efetivamente recebidos.

### Auditorias registradas

- **PBI-34:** reabertura do PBIX informada como validada.
- **PBI-35:** interatividade da página Produtos e Categorias informada como validada.
- **PBI-38:** conciliação Colab × Power BI para preços medianos e descontos médios das **três maiores categorias** — **3/3 aprovadas**.
- **PBI-39:** conciliação das quatro faixas de desconto — **4/4 aprovadas**; total **1.465**.
- **PBI-36:** teste dos filtros em Customer Insights **não executado** por decisão do grupo.

## ⚠️ Interpretação responsável

- Preços apresentados em **rupias indianas (INR)**, não em reais.
- **Preço não é receita**; desconto anunciado não comprova economia, margem ou efeito sobre vendas.
- Quantidade de avaliações **não equivale** a vendas ou clientes únicos.
- Menção a um tema de comentário **não demonstra sentimento positivo/negativo**. Temas se sobrepõem.
- Categorias com um ou dois produtos não são base suficiente para generalizações.
- Não há modelo preditivo implementado e validado como resultado desta entrega.
- A publicação pública dos CSVs requer verificação prévia da licença, proveniência e conteúdo potencialmente sensível. Material didático restrito da FIAP não será redistribuído.

## 🛠️ Tecnologias

**Google Colab · Python (pandas e análises de texto) · Google Drive · Power BI Desktop · Power Query · DAX · GitHub.**

### Estado da publicação — 20/11/2026

Documentação inicial publicada. **Pendente:** envio do notebook, PBIX e bases reais, sujeitos à inspeção e autorização; verificação do ZIP e comprovação da entrega institucional.

---

**Contato acadêmico:** Grupo 160 — FIAP Pós-Tech Data Analytics.
