---
title: Comparar públicos-alvo e segmentos de clientes ao bate-papo com colegas de trabalho
description: Use o Bate-papo com colegas de trabalho para comparar grupos de clientes, encontrar oportunidades de crescimento negligenciadas, rastrear tendências de público-alvo e transformar insights em públicos-alvo que você pode criar.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: f914f4a123216985ae9b562413f26e7b8c29eb0f
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 2%
---

# Visão geral da análise de público-alvo e segmento

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions. -->

Use o Adobe CX Enterprise Coworker Chat para entender quais grupos de clientes se comportam de forma diferente e como, para que você possa se concentrar nos mais importantes. Compare canais, períodos de tempo e segmentos lado a lado, rastreie como os públicos-alvo mudam com o tempo e transforme o que você encontra em um público-alvo que pode criar.

A análise de público-alvo e segmento é um dos vários domínios de análise no Chat do colaborador. Para ver todos os domínios, consulte [Iniciar análise no Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) em Analisar dados com o Chat do Colaborador.

**Recomendado para:** Analista, Usuário empresarial

## Pré-requisitos

<!-- FLAG: Confidence: High for the shared bullets (sourced from the Skills and limitations table and analytics-chat.md). Medium for the "Additional prerequisite" notes on the operational trends rows in the Use cases table: workflows.md lists the operational time-series skill as available for "All Eligible Applications" but doesn't state required permissions. Mapping Track audience size trends to the same requirement is inferred. Low for the "Additional prerequisite" note on the Take an insight into an audience row: inferred from the Audiences section of workflows.md, which lists Real-Time CDP as the application for audience creation. Confirm with the PM. -->

Para usar os casos de uso nesta página, você precisa:

* O Bate-papo com colegas de trabalho conectou-se às visualizações de dados do Customer Journey Analytics ou aos conjuntos de relatórios do Adobe Analytics. Consulte [Introdução à análise de dados com o Chat de Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).
* Acesso de visualização às visualizações de dados ou conjuntos de relatórios que você deseja analisar. O Chat do colega herda suas permissões do Customer Journey Analytics ou do Adobe Analytics.

## Casos de uso

| Caso de uso | Função |
| --- | --- |
| [Comparar desempenho](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Comparar métricas entre canais, períodos ou segmentos lado a lado.<p>**Exemplo de prompt:** &quot;Comparar receita por canal mês a mês&quot;</p><p>Para obter mais informações, consulte [Habilidades e limitações](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| [Comparar grupos de clientes](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Mostra quais grupos se comportam de forma diferente, sem exigir que você grave a lógica de segmentos.<p>**Recomendado para:** usuário empresarial</p><p>**Prompts de exemplo:**</p><ul><li>&quot;Os visitantes sociais pagos são convertidos de forma diferente do email?&quot;</li><li>&quot;Comparar visitantes novos e recorrentes na receita&quot;</li></ul><p>Para obter mais informações, consulte [Habilidades e limitações](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| Encontrar oportunidades de crescimento negligenciadas | Explora públicos, jornadas e canais para identificar oportunidades que os números do desempenho geral podem ocultar.<p>**Prompts de exemplo:**</p><ul><li>&quot;Quais públicos convertem acima da média, mas têm pouco tráfego?&quot;</li><li>&quot;Quais canais são subutilizados em sua taxa de conversão?&quot;</li></ul> |
| [Analisar tendências e causas operacionais](/help/chat/use-cases/workflows.md#data-insights) | Consulte dados históricos de séries temporais para públicos, conjuntos de dados e jornadas e identifique o que causou uma alteração.<p>**Recomendado para:** Administrador, Analista</p><p>**Exemplo de prompt:** &quot;Mostrar tendências de tamanho de público nos últimos 90 dias&quot;</p><p>**Pré-requisito adicional**: além dos [pré-requisitos gerais](#prerequisites), este caso de uso também requer acesso aos públicos, conjuntos de dados ou jornadas que você deseja analisar.</p><p>Para obter mais informações, consulte [Insights de dados](/help/chat/use-cases/workflows.md#data-insights) em casos de uso de Chat de Colaborador.</p> |
| Rastrear tendências de tamanho do público | Mostra públicos-alvo que estão crescendo ou diminuindo e examina a causa.<p>**Recomendado para:** Administrador, Analista</p><p>**Exemplo de prompt:** &quot;Quais públicos-alvo tiveram o crescimento mais rápido neste trimestre?&quot;</p><p>**Pré-requisito adicional** Além dos [pré-requisitos gerais](#prerequisites), este caso de uso também requer acesso aos públicos que você deseja rastrear.</p> |
| Transformar uma insight em um público-alvo | Vai de uma insight para um público-alvo que você pode criar, sem recomeçar.<p>**Prompts de exemplo:**</p><ul><li>&quot;Abrir esta comparação no Analysis Workspace&quot;</li><li>&quot;Ajude-me a criar um público-alvo deste grupo&quot;</li></ul><p>**Pré-requisito adicional:** Além dos [pré-requisitos gerais](#prerequisites), este caso de uso também requer acesso ao Real-Time Customer Data Platform e permissão para criar públicos.</p> |

## Habilidades usadas

<!-- FLAG: Confidence: High for Compare performance and Analyze operational trends and causes (skills listed for "Comparative analysis" and "Operational time-series & causal analysis" in workflows.md). Medium for Compare customer groups and Track audience size trends, which are mapped to the same skills based on their descriptions. Low for `audience-creation-flow`: inferred from the Audiences section of workflows.md. No skill is listed for Find overlooked growth opportunities because no source names one. Only `cja`, `aa`, and the root cause analysis skills currently appear in the Skills and limitations table on analytics-overview.md. -->

O colaborador usa as seguintes habilidades para os casos de uso descritos neste artigo. Para obter uma lista de todas as habilidades de análise, incluindo as permissões necessárias e as que não são abordadas, consulte [Habilidades e limitações](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) em Analisar dados com o Chat do Colaborador.

| Habilidade | Usado para |
| --- | --- |
| `cja`, `aa` | Comparar desempenho<br>Comparar grupos de clientes |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Compare o desempenho |
| `operational-stats-causal-analysis` | Analisar tendências e causas operacionais<br>Rastrear tendências de tamanho de público |
| `audience-creation-flow` | Transformar uma insight em um público-alvo |

## Dicas para obter melhores resultados

* Especifique os segmentos, públicos, canais ou dispositivos que deseja incluir, excluir ou comparar.
* Referencie segmentos e outros componentes pelo nome exato.
* Nomeie a métrica e o intervalo de datas no qual deseja comparar, como mês da receita por mês.
* Pergunte pelas dimensões de contribuição se quiser saber por que um grupo se comporta de forma diferente do outro.

## Próximas etapas

* Para obter uma visão geral da análise de dados com o Chat do Colaborador, incluindo os outros domínios de análise e práticas recomendadas, consulte [Analisar dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-overview.md).
* Para criar públicos diretamente no Chat do Colaborador, consulte [Avaliar a integridade do Experience Platform e criar públicos a partir da linguagem natural com o Colaborador](/help/chat/use-cases/audiences/create-audience-from-natural-language.md).
