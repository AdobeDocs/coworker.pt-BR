---
title: Analise as Jornadas do cliente e a devolução com o bate-papo com colegas de trabalho
description: Use o Bate-papo com colegas de trabalho para criar funis, descobrir onde os clientes abandonam, diagnosticar rejeições de conversão e comparar jornadas entre períodos nos dados de análise.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: f1ffc050071fc0ca48ae36c7aea8bc66eff2a147
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 2%
---

# Visão geral da análise de jornada

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Use o Adobe CX Enterprise Coworker Chat para descobrir onde e por que os clientes desistem da jornada para conversão em canais, dispositivos e segmentos. Descreva a jornada em linguagem simples, e o Chat do colaborador cria a funnel, mostra a entrega em cada etapa e ajuda a investigar a causa.

A análise de jornada é um dos vários domínios de análise no Chat do colaborador. Para ver todos os domínios, consulte [Iniciar análise no Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) em Analisar dados com o Chat do Colaborador.

**Recomendado para:** Analista, Usuário empresarial

## Pré-requisitos

Para usar os casos de uso nesta página, você precisa:

* O Bate-papo com colegas de trabalho conectou-se às visualizações de dados do Customer Journey Analytics ou aos conjuntos de relatórios do Adobe Analytics. Consulte [Introdução à análise de dados com o Chat de Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).
* Acesso de visualização às visualizações de dados ou conjuntos de relatórios que você deseja analisar. O Chat do colega herda suas permissões do Customer Journey Analytics ou do Adobe Analytics.

## Casos de uso

| Caso de uso | Função |
| --- | --- |
| [Analisar dados do Customer Journey Analytics e do Adobe Analytics](/help/chat/use-cases/data-insights/analytics-chat.md)<p>![Analisar dados do Customer Journey Analytics e do Adobe Analytics](../../assets/coworker-funnel-response-card.png)</p> | Responde perguntas em linguagem natural sobre suas visualizações de dados ou conjuntos de relatórios, cria funis e outras visualizações e descobre onde os clientes chegam. É possível abrir qualquer visualização no Analysis Workspace para análise adicional.<p>**Prompt de exemplo:** &quot;Mostrar exibições de página dos últimos 30 dias&quot;</p><p>Para obter mais informações, consulte [Introdução à análise de dados com o Chat de Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).</p> |
| [Descubra onde os clientes chegam](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Cria uma funnel a partir de uma pergunta em linguagem simples, classifica os maiores vazamentos e sugere as próximas etapas.<p>**Recomendado para:** usuário empresarial</p><p>**Prompts de exemplo:**</p><ul><li>&quot;Onde estamos perdendo pessoas a caminho de comprar?&quot;</li><li>&quot;Mostre-me o funnel de check-out&quot;</li></ul><p>Para obter mais informações, consulte [Habilidades e limitações](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| Diagnosticar rejeições de conversão | Investiga onde os clientes abandonam e avalia o que contribuiu para a alteração.<p>**Prompts de exemplo:**</p><ul><li>&quot;Por que as conversões caíram na semana passada?&quot;</li><li>&quot;Onde os clientes abandonaram o site após a mudança?&quot;</li></ul> |
| Isolar a causa de uma devolução | A exclusão faz com que um de cada vez isole o canal, dispositivo ou segmento por trás do problema.<p>**Prompts de exemplo:**</p><ul><li>&quot;O abandono do carrinho é pior em dispositivos móveis ou em desktops?&quot;</li><li>&quot;Quais canais são mais vazados entre o carrinho e a compra?&quot;</li></ul> |
| Comparar jornadas entre períodos | Mostra, passo a passo, se as alterações enviadas moveram a funnel.<p>**Recomendado para:** usuário empresarial</p><p>**Prompts de exemplo:**</p><ul><li>&quot;Comparar a conversão de check-out deste trimestre em último&quot;</li><li>&quot;Como minha funnel mudou após a reformulação?&quot;</li></ul> |

## Exemplo: descobrir onde os clientes chegam

Para obter um exemplo completo de conversa, da primeira pergunta a uma recomendação, consulte [Exemplo: Descubra onde os clientes abandonam](/help/chat/use-cases/data-insights/analytics-chat.md#example-find-where-customers-drop-off) em Introdução à análise de dados com o Chat de colega.

## Habilidades usadas

<!-- FLAG: Confidence: High for `cja` and `aa` (the Skills and limitations table lists funnel and fallout analysis and side-by-side comparison of time periods). Medium for the root cause analysis skills: workflows.md maps the prompt "Why did conversions drop last week?" to them, but the mapping to the slide rows "Diagnose conversion declines" and "Isolate the cause of a drop-off" is inferred. Confirm with the PM. -->

O colaborador usa as seguintes habilidades para os casos de uso descritos neste artigo. Para obter uma lista de todas as habilidades de análise, incluindo as permissões necessárias e as que não são abordadas, consulte [Habilidades e limitações](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) em Analisar dados com o Chat do Colaborador.

| Habilidade | Usado para |
| --- | --- |
| `cja`, `aa` | Analisar dados do Customer Journey Analytics e do Adobe Analytics<br>Descubra onde os clientes chegam<br>Comparar jornadas entre períodos |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Diagnosticar recusas de conversão<br>Isolar a causa de uma entrega |

## Dicas para obter melhores resultados

<!-- FLAG: Confidence: High, except the first bullet (Medium), which moved here from Prerequisites and is inferred from how funnel prompts work. The rest are adapted from the best practices in analytics-overview.md. -->

* Nomeie as etapas de jornada que deseja analisar, como página do produto, carrinho, check-out e compra.
* Nomeie as dimensões, as métricas e o intervalo de datas que deseja analisar, e faça referência aos componentes pelo nome exato.
* Solicite uma visualização de funnel ou fallout, se for o que deseja ver.
* Especifique os segmentos, canais ou dispositivos que deseja incluir, excluir ou comparar.
* Mencione qualquer hipótese que você já tenha, como uma alteração recente no site, para que o Bate-papo do Colaborador possa validá-la ou descartá-la.
* Peça as próximas etapas recomendadas se desejar que o Bate-papo com colegas de trabalho sugira perguntas de acompanhamento.
* Abra qualquer visualização no Analysis Workspace quando quiser mais controle manual. Consulte [Abrir uma visualização no Analysis Workspace](/help/chat/use-cases/data-insights/analytics-chat.md#open-a-visualization-in-analysis-workspace).

## Próximas etapas

* Para obter uma visão geral da análise de dados com o Chat do Colaborador, incluindo os outros domínios de análise e práticas recomendadas, consulte [Analisar dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-overview.md).
* Para configurar o Chat do Colaborador e percorrer um exemplo funcional, consulte [Introdução à análise de dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).
