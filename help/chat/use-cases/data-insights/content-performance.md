---
title: Analisar o conteúdo e o desempenho do Creative com o bate-papo entre colegas
description: Use o Bate-papo com colegas de trabalho para descobrir o que o conteúdo vencedor tem em comum, atribuir receita às imagens que os clientes veem e comparar a criação entre canais e públicos.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 5973a87d21b23d7621366108716cbd476e6f66ae
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 1%
---

# Visão geral do desempenho de conteúdo

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Use o Adobe CX Enterprise Coworker Chat para entender qual conteúdo ganha e por que, até os atributos de cada ativo, para que você possa investir no que funciona. Vá além de quais arquivos receberam cliques para ver quais imagens, mensagens e temas impulsionam o engajamento e a receita em canais e públicos.

O desempenho do conteúdo é um dos vários domínios de análise no Chat do colaborador. Para ver todos os domínios, consulte [Iniciar análise no Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) em Analisar dados com o Chat do Colaborador.

**Recomendado para:** usuário empresarial

## Pré-requisitos

<!-- FLAG: Confidence: High for the first two bullets (sourced from analytics-chat.md and the Skills and limitations table). Low for the third bullet: the attribute-level and image exposure descriptions suggest that these use cases rely on Content Analytics data in Customer Journey Analytics, and implementation-guide.md lists Content Analytics as an implementation path, but no source confirms this. It's a shared bullet rather than a table row because it would apply to every use case on this page. The paid channel row ("Compare Meta ad creative to our web banners") may need an additional data source, which would become an "Additional prerequisite" note on that row in the Use cases table. Confirm with the PM. -->

Para usar os casos de uso nesta página, você precisa:

* O Bate-papo com colegas de trabalho conectou-se às visualizações de dados do Customer Journey Analytics ou aos conjuntos de relatórios do Adobe Analytics. Consulte [Introdução à análise de dados com o Chat de Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).
* Acesso de visualização às visualizações de dados ou conjuntos de relatórios que você deseja analisar. O Chat do colega herda suas permissões do Customer Journey Analytics ou do Adobe Analytics.
* O Content Analytics é configurado no Customer Journey Analytics, para que o Chat do colaborador possa analisar os atributos do conteúdo e a exposição da imagem. Para planejar uma implementação do Content Analytics, consulte [Planejar sua implementação com o Colaborador](/help/chat/use-cases/data-insights/implementation-guide.md).

## Casos de uso

| Caso de uso | Função |
| --- | --- |
| Descubra o que o conteúdo vencedor tem em comum<p>![Descubra o que o conteúdo vencedor tem em comum](assets/content-performance.png)</p> | Mostra quais imagens e mensagens funcionam no nível do atributo, não apenas quais arquivos receberam cliques.<p>**Prompts de exemplo:**</p><ul><li>&quot;O que nossas imagens com melhor desempenho têm em comum?&quot;</li><li>&quot;Quais atributos de conteúdo impulsionam mais engajamento?&quot;</li></ul> |
| Atribuir receita ao conteúdo que os clientes visualizam | Vincula a exposição da imagem à receita, conversões e envolvimento com atribuição algorítmica.<p>**Recomendado para:** Analista, Usuário empresarial</p><p>**Prompts de exemplo:**</p><ul><li>&quot;Quais imagens excelentes geraram mais receita no último trimestre?&quot;</li><li>&quot;Quanta receita está vinculada a este banner?&quot;</li></ul> |
| Comparar o criativo entre canais pagos e próprios | Mostra quais visuais e temas são obtidos em canais da Web, móveis e pagos em uma exibição.<p>**Prompts de exemplo:**</p><ul><li>&quot;Quais temas criativos ganham em páginas pagas e em nosso site?&quot;</li><li>&quot;Compare o anúncio criativo do Meta com nossos banners da Web&quot;</li></ul> |
| Saber quais visuais movem cada público | Mostra quais visuais funcionam para cada público-alvo para orientar a personalização e os resumos criativos.<p>**Prompts de exemplo:**</p><ul><li>&quot;Quais visuais têm melhor desempenho para cada segmento?&quot;</li><li>&quot;Quais imagens funcionam para visitantes novos?&quot;</li></ul> |

<!--
HIDDEN until the skills are confirmed. To publish, remove this comment wrapper.

## Skills used

FLAG: Confidence: Low. No source in the repo (workflows.md, the Skills and limitations table, or any data insights article) names the skills behind these use cases. Get the skill IDs from the PM, replace the placeholder rows, and add the skills to the Skills and limitations table on analytics-overview.md so that the link above the table covers them. When you unhide this section, wrap this FLAG note in its own HTML comment.

Coworker uses the following skills for the use cases described in this article. For a list of all analytics skills, including the permissions they require and what they don't cover, see [Skills and limitations](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analyze data with Coworker Chat.

| Skill | Used for |
| --- | --- |
| *[Skill to be confirmed]* | Find what winning content has in common<br>Attribute revenue to the content customers see<br>Compare creative across paid and owned channels<br>Know which visuals move each audience |

-->

## Dicas para obter melhores resultados

<!-- FLAG: Confidence: Medium. The first two bullets are adapted from the best practices in analytics-overview.md. The third bullet is inferred from the row descriptions. -->

* Nomeie a métrica e o intervalo de datas que deseja analisar, como receita do último trimestre.
* Especifique os segmentos, públicos ou canais que deseja comparar.
* Pergunte sobre atributos de conteúdo, como imagens, temas ou mensagens, em vez de arquivos individuais, quando quiser saber por que o conteúdo tem bom desempenho.

## Próximas etapas

* Para obter uma visão geral da análise de dados com o Chat do Colaborador, incluindo os outros domínios de análise e práticas recomendadas, consulte [Analisar dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-overview.md).
* Para configurar o Chat do Colaborador e percorrer um exemplo funcional, consulte [Introdução à análise de dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).
