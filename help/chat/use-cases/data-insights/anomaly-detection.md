---
title: Detectar anomalias do Experience Platform com o colega de trabalho
description: Saiba como detectar anomalias no Adobe Experience Platform com o Chat do parceiro. Explore prompts para métricas de assimilação, segmentação e ativação de destino.
feature: AI Tools
role: User
level: Intermediate
doc-type: Tutorial
jira: PLAT-313965
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 1%
---

# Detectar anomalias do Experience Platform

Use o Chat do [!DNL Adobe CX Enterprise Coworker] para identificar picos e quedas nas métricas do Adobe Experience Platform com suporte. Pergunte sobre fluxos de dados e públicos para encontrar desvios de uma linha de base.

Comece com uma pergunta ampla e concentre-se em um fluxo ou público-alvo que precise de atenção. Revise a métrica relatada e sua linha de base antes de decidir o que investigar.

>[!AVAILABILITY]
>
>A detecção de anomalias está em disponibilidade limitada. A disponibilidade geral está prevista para o primeiro trimestre de 2027.

>[!NOTE]
>
>A Detecção de anomalias oferece informações sem alterar os dados ou a configuração.

## Competências em diagnóstico disponíveis

Use o plug-in `baseline-anomalies` para detectar anomalias, comparar tendências e verificar a integridade do fluxo ou falhas no trabalho atual. O plug-in é configurado por padrão com a oferta Experience Platform e Apps em [!DNL Coworker].

Escolha o tipo de pergunta com base nas informações necessárias.

| Habilidade | Finalidade |
| --- | --- |
| [!UICONTROL Anomalias do Fluxo de Pesquisa de Anomalias da Linha de Base] | Detecte picos ou quedas no volume de registros e registros com falha nos estágios de assimilação, segmentação, exportação e destino. |
| [!UICONTROL Anomalias da Linha de Base Pesquisa de Anomalias de Público] | Detectar picos ou quedas nas contagens de perfil do público-alvo realizado e picos nas contagens de perfis encerrados. |
| [!UICONTROL Tendência de Fluxo de Resumo de Anomalias da Linha de Base] | Compare a taxa de transferência de fluxo recente e típica sem um veredicto de anomalia. |
| [!UICONTROL Tendência de Resumo de Anomalias da Linha de Base] | Compare as contagens recentes e típicas de perfis qualificados e encerrados para segmentação em lote, sem um veredicto de anomalia ou intervalo esperado. |
| [!UICONTROL Integridade do Fluxo de Inspeção de Anomalias da Linha de Base] | Revise as contagens de execuções bem-sucedidas e com falha desduplicadas, além dos totais de registros com falha por atividade ou fluxo. |
| [!UICONTROL Trabalhos com Falha na Pesquisa de Anomalias de Linha de Base] | Revise as tarefas com falha no momento e seus motivos de falha, excluindo falhas recuperadas e detalhes de registros individuais. |

Os resumos de tendências descrevem alterações, mas não determinam se essas alterações são anomalias. Use perguntas de anomalias quando precisar de uma avaliação de pico ou queda.

## Antes de começar

O plugin é configurado por padrão. Para verificar seu status antes de fazer perguntas de diagnóstico, siga estas etapas.

1. Vá para **[!UICONTROL Personalizações]**.

1. Selecione **[!UICONTROL Plug-ins]**.

1. Abra **[!UICONTROL baseline-anomalies]** e confirme se seu status é **[!UICONTROL Ative]**.

Identifique a sandbox e a área que deseja verificar. Para um recurso específico, tenha seu nome de fluxo, segmento ou destino ou identificador pronto.

Para obter instruções gerais de chat, consulte [Introdução ao Chat](/help/chat/ui-guide.md).

## Perguntar sobre anomalias

Descreva a área ou o recurso que deseja verificar e o período que deseja examinar.

Use os prompts de exemplo a seguir como ponto de partida. Substitua nomes de exemplo por nomes de sua organização.

| Meta | Exemplo de prompt |
| --- | --- |
| Verificar entre áreas compatíveis | Há alguma anomalia nas últimas 24 horas? |
| Verificar assimilação | Há alguma anomalia na minha ingestão nas últimas 24 horas? |
| Verificar um fluxo específico | Há anomalias com o fluxo de assimilação CustomerImport nas últimas 24 horas? |
| Verificar segmentação | Há alguma anomalia na minha segmentação nas últimas 24 horas? |
| Verificar um segmento específico | Há alguma anomalia com LoyaltyMembers de segmento nas últimas 24 horas? |
| Verificar ativação de destino | Há alguma anomalia na ativação do meu destino nas últimas 24 horas? |
| Verificar picos de perfil realizados | Algum público-alvo está vendo um pico em perfis realizados hoje? |
| Verificar anomalias de registro com falha | Os registros com falha são anormalmente altos no fluxo da Importação do Cliente? |

A pergunta ampla verifica os fluxos de dados e os públicos-alvo. Confirme a sandbox e o período identificados na resposta.

<!-- Author review: Confirm exact supported time windows, defaults, time zone handling, and data freshness. -->

## Revisar resultados da anomalia

Compare o valor relatado com sua linha de base para o recurso afetado e o período de tempo. Use a diferença para identificar o que precisa de mais investigação, em vez de tratar uma anomalia como uma causa confirmada.

Por exemplo, uma diminuição nos registros de entrada de assimilação identifica uma alteração de volume. Essa mudança por si só não explica por que chegaram menos registros.

Os resultados podem aparecer como tabelas ou como um resumo escrito. As tabelas podem agrupar anomalias em [!UICONTROL Risco alto] e [!UICONTROL Risco para Medium].

![Os resultados de anomalias agrupam picos e quedas de volume de destino e assimilação por alto e médio risco, com os nomes e valores dos recursos ocultados.](assets/anomaly-detection/anomaly-detection-results.png){width="900" zoomable="yes"}

Esse exemplo agrupa anomalias de fluxo por risco e sugere investigar as contagens de execuções ou o histórico de tendências. Os nomes e valores do recurso são redigidos.

| Detalhes do resultado | O que revisar |
| --- | --- |
| [!UICONTROL Quando (UTC)] | A janela de hora ou hora do evento em Tempo universal coordenado. |
| [!UICONTROL Estágio] | O estágio de processamento afetado, como assimilação ou destino. |
| [!UICONTROL Fluxo] | O fluxo afetado, identificado por nome ou identificador. |
| [!UICONTROL O que aconteceu] | A alteração detectada, como um pico ou queda de volume. |
| [!UICONTROL Real vs. esperado] | O valor observado em comparação com a linha de base ou o intervalo esperado. |

Revise a explicação junto com o agrupamento de risco. Para anomalias de público-alvo, Alto indica uma grande diferença em relação ao normal. O Medium indica uma saída clara, mas moderada. Somente as anomalias High e Medium são retornadas.

Os resultados do público-alvo excluem anomalias do Medium quando o histórico da linha de base é altamente variável. Qualquer anomalia retornada com histórico altamente variável, portanto, tem um nível de Alto risco.

Use níveis de risco para priorizar a investigação, e não para estabelecer uma causa básica.

Por exemplo, uma resposta identifica dez registros de entrada em relação a um intervalo esperado de um a quatro como um pico de risco médio. O nível normal é de aproximadamente um registro, portanto, o desvio é grande em relação à linha de base. O volume absoluto permanece pequeno.

Verifique os tempos de evento antes de tratar uma anomalia histórica como um problema atual. Um evento fora das últimas 24 horas não estabelece se a condição subjacente se recuperou.

<!-- Author review: Confirm flow risk tier definitions and whether persistence is reported. -->

### Linhas de base e intervalos esperados

As comparações de anomalias por hora usam a mesma hora nos 14 dias anteriores. Isso leva em conta os padrões típicos por hora, mas não leva em conta a sazonalidade mais ampla.

Para anomalias de público-alvo, o intervalo esperado centra-se na mediana e se expande de acordo com a variação nas contagens históricas. Se o limite inferior calculado for negativo, o intervalo usará a contagem histórica mais baixa. O intervalo pode, portanto, estender-se mais acima da mediana do que abaixo dela.

As contagens de perfis realizadas acima do intervalo esperado são picos. As contagens abaixo do intervalo são quedas. Uma contagem de zero quando os perfis estão normalmente presentes é uma queda de alto risco.

As contagens de perfis de saída produzem apenas vértices de pico. Menos saídas são tratadas como normais, não como anomalias de queda.

### Nenhuma anomalia retornada

Uma resposta pode relatar que nenhuma anomalia Alta ou Medium foi retornada para o público-alvo e o período solicitados.

![Um resumo de anomalias de público-alvo não relata anomalias High ou Medium acima de 168 horas e inclui um aviso sobre o histórico excluído.](assets/anomaly-detection/anomaly-detection-no-anomalies.png){width="900" zoomable="yes"}

Este exemplo inclui um aviso sobre histórico insuficiente ou quase zero. Não confirma se cada hora foi avaliada ou que esse público-alvo foi excluído. O nome e o identificador do público-alvo são redigidos.

### Histórico de linha de base insuficiente

O histórico da linha de base afeta se um público-alvo pode ser avaliado quanto a anomalias.

A detecção de anomalias de público-alvo não avalia linhas com menos de cinco dias de histórico ou um histórico que contenha principalmente zeros.

>[!IMPORTANT]
>
>Nenhuma anomalia relatada significa que todos os recursos foram avaliados. A resposta pode não confirmar se um público-alvo foi avaliado ou ignorado.

<!-- Author review: Confirm flow minimum history requirements and whether audience evaluation status or excluded resources can be retrieved. -->

## Refine sua pergunta

Concentre sua próxima pergunta no recurso afetado. Por exemplo, depois de uma verificação ampla de assimilação, pergunte sobre anomalias para um fluxo nomeado.

Depois de perguntar sobre as últimas 24 horas, estenda o período com este acompanhamento:

```text
What about in the past two weeks?
```

A resposta pode identificar anomalias históricas, mesmo quando nenhuma aparecer nas últimas 24 horas.

Para uma investigação mais detalhada, pergunte sobre contagens de execuções de fluxo, tendências de fluxo, tendências de público-alvo ou trabalhos com falha no momento. Você também pode perguntar sobre empregos individuais enquanto investiga.

Escolha a próxima pergunta com base nas informações necessárias. Os resumos de tendências e integridade não fornecem veredictos de anomalias.

| Meta | Exemplo de prompt | O que esperar |
| --- | --- | --- |
| Analisar tendências do público | Como meus públicos-alvo mudaram na semana passada? | Contagens de perfis qualificados e encerrados recentes e típicos para segmentação em lote, sem um intervalo esperado. |
| Revisar tendências de fluxo | Como o volume de assimilação mudou na última semana? | Taxa de transferência recente em comparação com a taxa de transferência típica, sem um veredicto de anomalia. |
| Revisar integridade do fluxo | Quantas execuções tiveram êxito ou falharam para meus fluxos de assimilação nas últimas 24 horas? | Contagens de execuções desduplicadas e totais de registros com falha agregados, sem motivos de falha. |
| Investigar trabalhos com falha | Quais trabalhos de exportação falharam nas últimas 24 horas e por quê? | Trabalhos cujo estado mais recente falhou dentro do escopo solicitado, com os motivos de falha do trabalho. |
| Investigar uma falha de fluxo | Qual é o erro no fluxo de importação do cliente? | Motivos de falha para trabalhos com falha no momento associados ao fluxo, sem detalhes para registros individuais. |

O histórico de tendências do público é retido por aproximadamente duas semanas ou 336 horas. O valor típico é a mediana dessa hora nos 14 dias anteriores.

Para trabalhos que falharam no momento, um resultado vazio significa que nenhum trabalho está falhando no momento dentro do escopo solicitado. Isso não significa que nenhuma falha ocorreu durante o período solicitado. Os trabalhos que falharam e foram bem-sucedidos posteriormente são excluídos.

Continue investigando com habilidades de verificação de integridade ou use habilidades de alerta para ativar um alerta para um ativo compatível. Essas ações usam habilidades separadas, não a detecção de anomalias propriamente dita.

Para workflows de alerta relacionados, consulte [Habilidades de alerta do cliente](/help/chat/use-cases/customer-alerts/customer-alerts.md).

<!-- Author review: Validate a complete public example response and the supported alert assets and setup before adding an alert procedure. -->

## Referência da métrica

A versão limitada inclui as sete métricas a seguir na assimilação, segmentação e ativação de destino. Use essa referência para identificar as contagens associadas a cada área.

| Área | Identificador da métrica | Contagem medida |
| --- | --- | --- |
| Ingestão | `input_record_count` | Contagem de registros de entrada para um fluxo de assimilação. |
| Ingestão | `failed_record_count` | Contagem de registros com falha para um fluxo de assimilação. |
| Segmentação | `__segment_{segment_id}__realized_profiles` | Contagem de perfis qualificados para um segmento. |
| Segmentação | `__segment_{segment_id}__exited_profiles` | Contagem de perfis que saem de um segmento. |
| Ativação de destino | `{destination}_input_record_count` | Contagem de registros de entrada para um destino. |
| Ativação de destino | `{destination}_skipped_record_count` | Contagem de registros ignorados para um destino. |
| Ativação de destino | `{destination}_output_record_count` | Contagem de registros de saída para um destino. |

<!-- Author review: Confirm metric aggregation intervals and identifier visibility. -->

## Escopo e limitações

Use a detecção de anomalias para identificar desvios, e não para confirmar uma causa raiz ou reparar um recurso.

Você pode perguntar sobre fluxos, segmentos e destinos por nome ou identificador. A detecção de anomalias de fluxo abrange os estágios de assimilação, segmentação, exportação e destino.

Use a habilidade de trabalho com falha para trabalhos com falha no momento e seus motivos de falha. As falhas recuperadas são excluídas. Os diagnósticos de trabalho não incluem detalhes de registros individuais ou veredictos de anomalias.

A integridade do fluxo fornece contagens agregadas, não motivos de falha. Os resumos de tendências descrevem valores recentes e típicos, não veredictos de anomalias. Os resumos de tendências de público-alvo abrangem apenas a segmentação em lote.

A detecção de anomalias não altera os dados nem a configuração. Use habilidades separadas para ações de alerta apoiadas e investigações de saúde mais profundas.

<!-- Author review: Confirm job identifier support and any recommendation capabilities before adding examples. -->
