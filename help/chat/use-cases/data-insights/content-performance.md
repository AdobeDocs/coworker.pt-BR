---
title: Analisar o conteúdo e o desempenho do Creative com o bate-papo entre colegas
description: Use o Bate-papo com colegas de trabalho para descobrir o que o conteúdo vencedor tem em comum, atribuir receita às imagens que os clientes veem e comparar a criação entre canais e públicos.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 1%
---

# Visão geral do desempenho de conteúdo

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Use o Adobe CX Enterprise Coworker Chat para entender qual conteúdo ganha e por que, até os atributos de cada ativo, para que você possa investir no que funciona. Vá além de quais arquivos receberam cliques para ver quais imagens, mensagens e temas impulsionam o engajamento e a receita em canais e públicos.

O desempenho do conteúdo é um dos vários domínios de análise no Chat do colaborador. Para ver todos os domínios, consulte [Iniciar análise no Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) em Analisar dados com o Chat do Colaborador.

**Recomendado para:** usuário empresarial

## Pré-requisitos

<!-- FLAG: Confidence: High for the first two bullets (sourced from analytics-chat.md and the Skills and limitations table). High for the third bullet: attribute-level and asset analysis needs Content Analytics components, which are available only in data views that are configured for Content Analytics (report/report.md in analytics-platform.en). This applies whichever skill runs the analysis. It's a shared bullet rather than a table row because it applies to every use case on this page. The SME confirmed (October 2026) that the skill doesn't support paid media yet, so the paid channel use case was rewritten for web and mobile. Support is planned, either in this skill or in a separate add-on skill (not decided). When it ships, consider restoring paid channels to that row with an "Additional prerequisite" note: paid media needs the Paid Media channel enabled in Content Analytics through an Experience Platform paid media source connector, such as Meta Ads or Google Ads, and comparing paid creative with on-site revenue needs custom tracking-key mapping (config/paid-media.md in analytics-platform.en). -->

Para usar os casos de uso nesta página, você precisa:

* O Bate-papo com colegas de trabalho conectou-se às visualizações de dados do Customer Journey Analytics ou aos conjuntos de relatórios do Adobe Analytics. Consulte [Introdução à análise de dados com o Chat de Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).
* Acesso de visualização às visualizações de dados ou conjuntos de relatórios que você deseja analisar. O Chat do colega herda suas permissões do Customer Journey Analytics ou do Adobe Analytics.
* Uma visualização de dados configurada para o Content Analytics. Consulte [Configurar Content Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/configuration/configuration) no guia do Customer Journey Analytics.

## Casos de uso

| Caso de uso | Função |
| --- | --- |
| Descubra o que o conteúdo vencedor tem em comum<p>![Descubra o que o conteúdo vencedor tem em comum](assets/content-performance.png)</p> | Mostra quais imagens e mensagens funcionam no nível do atributo, não apenas quais arquivos receberam cliques.<p>**Prompts de exemplo:**</p><ul><li>&quot;O que nossas imagens com melhor desempenho têm em comum?&quot;</li><li>&quot;Quais atributos de conteúdo impulsionam mais engajamento?&quot;</li></ul> |
| Atribuir receita ao conteúdo que os clientes visualizam | Vincula a exposição da imagem à receita, conversões e envolvimento com atribuição algorítmica.<p>**Recomendado para:** Analista, Usuário empresarial</p><p>**Prompts de exemplo:**</p><ul><li>&quot;Quais imagens geraram mais receita no último trimestre?&quot;</li><li>&quot;Quanta receita está vinculada à imagem em https://www.example.com/images/spring-sale.jpg?&quot;</li></ul> |
| Comparar o criativo na Web e em dispositivos móveis | Mostra quais visuais e temas são premiados em seu site e em seu aplicativo móvel em uma única visualização.<p>**Prompts de exemplo:**</p><ul><li>&quot;Quais temas criativos ganham em nosso aplicativo móvel e em nosso site?&quot;</li><li>&quot;Compare o desempenho da imagem em nosso aplicativo móvel e em nosso site&quot;</li></ul> |
| Saber quais visuais movem cada público | Mostra quais visuais funcionam para cada público-alvo para orientar a personalização e os resumos criativos.<p>**Prompts de exemplo:**</p><ul><li>&quot;Quais visuais têm melhor desempenho para cada segmento?&quot;</li><li>&quot;Quais imagens funcionam para visitantes novos?&quot;</li></ul> |

## Habilidades usadas

<!-- FLAG: Confidence: Medium. The `analyze-content` skill is a foundational skill for content questions, so it's listed for every use case on this page. Confirm with the PM that it covers all four. -->

O colaborador usa as seguintes habilidades para os casos de uso descritos neste artigo. Para obter uma lista de todas as habilidades de análise, incluindo as permissões necessárias e as que não são abordadas, consulte [Habilidades e limitações](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) em Analisar dados com o Chat do Colaborador.

| Habilidade | Usado para |
| --- | --- |
| `cja`,`analyze-content` <br/> (Disponibilidade Limitada) | Descubra o que o conteúdo vencedor tem em comum<br>Atribua receita aos clientes do conteúdo.<br>Compare o criativo na Web e em dispositivos móveis<br>Saiba quais visuais movem cada público<p>Para obter mais informações, consulte [Fazer perguntas sobre o seu conteúdo](/help/chat/use-cases/data-insights/ask-content-questions.md).</p> |

## Dicas para obter melhores resultados

<!-- FLAG: Confidence: High for the first bullet (SME feedback, October 2026). Medium for the rest: the second and third bullets are adapted from the best practices in analytics-overview.md, and the fourth bullet is inferred from the row descriptions. -->

* Quando você perguntar sobre uma imagem específica, inclua o URL ou a ID do ativo. O colaborador não pode identificar uma imagem pela sua função na página, como uma imagem herói ou um banner.
* Nomeie a métrica e o intervalo de datas que deseja analisar, como receita do último trimestre.
* Especifique os segmentos, públicos ou canais que deseja comparar.
* Pergunte sobre atributos de conteúdo, como imagens, temas ou mensagens, em vez de arquivos individuais, quando quiser saber por que o conteúdo tem bom desempenho.

## Próximas etapas

* Para saber como o Colaborador responde a perguntas sobre conteúdo, consulte [Fazer perguntas sobre seu conteúdo](/help/chat/use-cases/data-insights/ask-content-questions.md) (Disponibilidade limitada).
* Para obter uma visão geral da análise de dados com o Chat do Colaborador, incluindo os outros domínios de análise e práticas recomendadas, consulte [Analisar dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-overview.md).
* Para configurar o Chat do Colaborador e percorrer um exemplo funcional, consulte [Introdução à análise de dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).
