---
title: Meça o impacto do marketing e a atribuição com o bate-papo do colaborador
description: Use o Bate-papo com colegas de trabalho para medir o impacto incremental de cada canal, descobrir onde os gastos ficam saturados, criar cenários de orçamento hipotéticos e verificar a qualidade do modelo de marketing.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 2%
---

# Medição de marketing e visão geral de atribuição

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Use o Adobe CX Enterprise Coworker Chat para entender o impacto incremental de cada canal de marketing e campanha, de modo que você possa alocar gastos para otimizar o ROI. Veja como os canais funcionam juntos, onde os gastos extras param de ser compensados e como as diferentes alocações de orçamento se comparam antes de você confirmar.

A medição e atribuição de marketing é um dos vários domínios de análise no Chat do colaborador. Para ver todos os domínios, consulte [Iniciar análise no Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) em Analisar dados com o Chat do Colaborador.

**Recomendado para:** Analista, Usuário empresarial

## Pré-requisitos

<!-- FLAG: Confidence: High for the shared bullets (sourced from analytics-chat.md and the Skills and limitations table). They're confirmed for Measure campaign performance only; whether the marketing mix modeling use cases also need a data view or report suite connection is unknown. Low for the "Additional prerequisite" notes on the four marketing mix modeling rows in the Use cases table: incremental impact, response curves, budget scenarios, and model retraining describe a marketing mix model, but no source names the product or data that these use cases need. It could be Adobe Mix Modeler or Marketing Campaign Analytics (listed as an implementation path in implementation-guide.md). Confirm with the PM before publishing. -->

Para usar os casos de uso nesta página, você precisa:

* O Bate-papo com colegas de trabalho conectou-se às visualizações de dados do Customer Journey Analytics ou aos conjuntos de relatórios do Adobe Analytics. Consulte [Introdução à análise de dados com o Chat de Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).
* Acesso de visualização às visualizações de dados ou conjuntos de relatórios que você deseja analisar. O Chat do colega herda suas permissões do Customer Journey Analytics ou do Adobe Analytics.

## Casos de uso

| Caso de uso | Função |
| --- | --- |
| Descubra o impacto incremental de cada canal | Mostra o valor incremental de cada canal, como os canais se amplificam uns aos outros e a função de fatores externos.<p>**Prompts de exemplo:**</p><ul><li>&quot;Quais canais geraram mais conversões incrementais?&quot;</li><li>&quot;Como a pesquisa e a exibição pagas se amplificam?&quot;</li></ul><p>**Pré-requisito adicional** Além dos [pré-requisitos gerais](#prerequisites), este caso de uso também requer um modelo de medição de marketing treinado. *[Requisitos de produto e configuração a serem confirmados.]*</p> |
| Descubra onde os gastos começam a saturar<p>![Localizar onde o gasto começa a saturar](assets/marketing-measurement.png)</p> | Mostra curvas de resposta que revelam onde o gasto extra para de ser compensado.<p>**Prompts de exemplo:**</p><ul><li>&quot;Onde a pesquisa paga gasta começa a saturar?&quot;</li><li>&quot;Mostrar curvas de resposta para cada canal&quot;</li></ul><p>**Pré-requisito adicional** Além dos [pré-requisitos gerais](#prerequisites), este caso de uso também requer um modelo de medição de marketing treinado. *[Requisitos de produto e configuração a serem confirmados.]*</p> |
| Criar cenários de orçamento hipotéticos | Compara as opções de alocação lado a lado para dar suporte às decisões de planejamento.<p>**Recomendado para:** usuário empresarial</p><p>**Prompts de exemplo:**</p><ul><li>&quot;Crie cenários de orçamento para o próximo trimestre&quot;</li><li>&quot;E se eu mudar 10% dos gastos da exibição para a pesquisa?&quot;</li></ul><p>**Pré-requisito adicional** Além dos [pré-requisitos gerais](#prerequisites), este caso de uso também requer um modelo de medição de marketing treinado. *[Requisitos de produto e configuração a serem confirmados.]*</p> |
| Verificar a qualidade do modelo e quando treinar novamente | Inspeciona a qualidade do modelo, os detalhes do treinamento e as métricas de pontuação para que você saiba o quanto confiar em uma resposta.<p>**Recomendado para:** analista</p><p>**Prompts de exemplo:**</p><ul><li>&quot;Existem outros fatores que precisamos para esse modelo?&quot;</li><li>&quot;Esse modelo precisa ser retreinado?&quot;</li></ul><p>**Pré-requisito adicional** Além dos [pré-requisitos gerais](#prerequisites), este caso de uso também requer um modelo de medição de marketing treinado. *[Requisitos de produto e configuração a serem confirmados.]*</p> |
| [Meça o desempenho da campanha](/help/chat/use-cases/workflows.md#data-insights) | Veja como as campanhas, os canais e as propriedades da Web foram executados em um determinado período.<p>**Prompt de exemplo:** &quot;Como foi o desempenho das campanhas da Web do Acrobat no mês passado?&quot;</p><p>Para obter mais informações, consulte [Insights de dados](/help/chat/use-cases/workflows.md#data-insights) em casos de uso de Chat de Colaborador.</p> |

## Habilidades usadas

<!-- FLAG: Confidence: High for Measure campaign performance (workflows.md lists `cja`, `aa`, `dx-api`, and `knowledge-graph` for "Campaign performance"). `dx-api` and `knowledge-graph` aren't in the Skills and limitations table on analytics-overview.md. Low for the other four use cases: no source names their skills. Get the skill IDs from the PM, replace the placeholder row, and add the skills to the Skills and limitations table. -->

O colaborador usa as seguintes habilidades para os casos de uso descritos neste artigo. Para obter uma lista de todas as habilidades de análise, incluindo as permissões necessárias e as que não são abordadas, consulte [Habilidades e limitações](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) em Analisar dados com o Chat do Colaborador.

| Habilidade | Usado para |
| --- | --- |
| `cja`, `aa`, `dx-api`, `knowledge-graph` | Medir o desempenho da campanha |
| *[Habilidade a ser confirmada]* | Descubra o impacto incremental de cada canal<br>Descubra onde o gasto começa a ficar saturado<br>Crie cenários de orçamento hipotéticos<br>Verifique a qualidade do modelo e quando treinar novamente |

## Dicas para obter melhores resultados

<!-- FLAG: Confidence: Medium. The first two bullets are adapted from the best practices in analytics-overview.md. The third bullet is inferred from the sample prompts. -->

* Nomeie os canais, campanhas e intervalo de datas que deseja analisar.
* Mencione qualquer hipótese que você já tenha, como dois canais trabalhando juntos, para que o Bate-papo do Colaborador possa validá-la ou descartá-la.
* Indique a mudança de orçamento específica que deseja testar ao criar cenários hipotéticos, como mover 10% dos gastos de um canal para outro.

## Próximas etapas

* Para obter uma visão geral da análise de dados com o Chat do Colaborador, incluindo os outros domínios de análise e práticas recomendadas, consulte [Analisar dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-overview.md).
* Para configurar o Chat do Colaborador e percorrer um exemplo funcional, consulte [Introdução à análise de dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).
