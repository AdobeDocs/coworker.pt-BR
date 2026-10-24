---
title: Faça perguntas sobre seu conteúdo com o bate-papo com colegas de trabalho
description: Pergunte ao bate-papo com colegas de trabalho sobre seu conteúdo em linguagem simples, de geral a específico, e obtenha respostas precisas do Content Analytics sem conhecimento de analistas.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: f1ffc050071fc0ca48ae36c7aea8bc66eff2a147
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 2%
---

# Faça perguntas sobre o seu conteúdo

<!-- FLAG: Confirm with the PM: (1) availability (GA, beta, or experimental) and whether this page needs an AVAILABILITY note or `hide: true` until launch, and (2) any required Coworker entitlement. Content Analytics itself has no separate permission: users get access through data views that are configured for Content Analytics (Access control section of analytics-platform.en/help/content-analytics/config/configuration.md). -->

Use o Adobe CX Enterprise Coworker Chat para obter respostas precisas sobre o conteúdo do Adobe Content Analytics. Faça uma pergunta específica, como &quot;Quais imagens herói geraram mais receita no último trimestre?&quot;, ou uma pergunta geral, como &quot;Qual tipo de conteúdo devo priorizar?&quot;. Colaborador transforma sua pergunta em uma análise sólida.

O colaborador entende como os dados do Content Analytics são estruturados e aplica as regras de relatório que um analista experiente aplicaria, para que profissionais de marketing e outros usuários empresariais obtenham resultados confiáveis sem um profundo conhecimento sobre o Content Analytics.

Para outros casos de uso de desempenho de conteúdo, consulte [Visão geral de desempenho de conteúdo](/help/chat/use-cases/data-insights/content-performance.md).

**Recomendado para:** usuário empresarial, analista

## Pré-requisitos

<!-- FLAG: Confidence: High. The first two bullets match the other data insights pages. The third bullet follows the Content Analytics docs in analytics-platform.en: Content Analytics components are available only in data views that are configured for Content Analytics (report/report.md), and there's no separate Content Analytics permission (config/configuration.md). -->

Para fazer perguntas sobre o seu conteúdo, é necessário:

* O Chat do Colaborador conectou-se às visualizações de dados do Customer Journey Analytics. Consulte [Introdução à análise de dados com o Chat de Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).
* Acesso de visualização às visualizações de dados que você deseja analisar. O Chat do colega herda suas permissões do Customer Journey Analytics.
* Uma visualização de dados configurada para o Content Analytics. Consulte [Configurar Content Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/content-analytics/configuration/configuration) no guia do Customer Journey Analytics.

## Fazer uma pergunta sobre conteúdo

1. Faça logon no Colaborador.

1. Selecione **[!UICONTROL Novo chat]**.

1. No campo de texto, faça uma pergunta sobre o conteúdo. Por exemplo:

   **Aviso**

   > Que tipo de conteúdo devo priorizar?

   <!-- FLAG: The skill includes activation words and phrases, but they weren't provided. Confirm with the PM whether customers need to use specific words to trigger the skill, or whether any content question routes to it automatically. If specific words are needed, list them here. -->

   O colaborador usa a habilidade `analyze-content` para responder perguntas de conteúdo.

1. (Condicional) Se a sua pergunta estiver aberta a mais de uma interpretação, responda às perguntas esclarecidas pelo Colaborador, como tipo de conteúdo, canal ou intervalo de datas desejado.

1. Revise os resultados.

1. (Opcional) Faça perguntas de acompanhamento na mesma conversa para aprofundar ou abra uma visualização no Analysis Workspace para ter mais controle manual. Consulte [Abrir uma visualização no Analysis Workspace](/help/chat/use-cases/data-insights/analytics-chat.md#open-a-visualization-in-analysis-workspace).

## Exemplo de prompts

A tabela a seguir mostra prompts de exemplo para diferentes tipos de perguntas de conteúdo. Use-as como ponto de partida e adapte-as ao seu próprio conteúdo.

| Tipo de pergunta | Exemplo de prompts |
| --- | --- |
| Amplo ou exploratório | <ul><li>&quot;Que tipo de conteúdo devo priorizar?&quot;</li><li>&quot;Como está o desempenho do nosso conteúdo?&quot;</li></ul> |
| Nível do atributo | <ul><li>&quot;O que nossas imagens com melhor desempenho têm em comum?&quot;</li><li>&quot;Quais atributos de conteúdo impulsionam mais engajamento?&quot;</li></ul> |
| Receita e conversões | <ul><li>&quot;Quais imagens excelentes geraram mais receita no último trimestre?&quot;</li><li>&quot;Quanta receita está vinculada a este banner?&quot;</li></ul> |
| Canais e públicos | <ul><li>&quot;Quais temas criativos ganham em páginas pagas e em nosso site?&quot;</li><li>&quot;Quais imagens funcionam para visitantes novos?&quot;</li></ul> |

## Como o Colaborador responde a perguntas sobre conteúdo

<!-- FLAG: Confidence: High for the list of what the skill includes, metric matching, filtering pages by Experience ID, and choosing an attribution model per question (sourced from the PM's skill description and feature summary). Medium for the remaining details, which combine the skill description with the Content Analytics component reference in the Customer Journey Analytics guide. The skill's specific query defaults, attribution models, and visualization rules weren't provided. Confirm with the PM before adding them. -->

O colaborador responde perguntas de conteúdo com a habilidade `analyze-content`, que inclui o contexto e as medidas de proteção a seguir. A habilidade é emparelhada com a habilidade `cja` e executa todas as consultas nas visualizações de dados do Customer Journey Analytics por meio das mesmas ferramentas do Customer Journey Analytics.

### Padrões de consulta e esclarecimento de perguntas

Se a sua pergunta deixa de fora um detalhe, a habilidade aplica um padrão sensato. Se a habilidade não tem certeza do que você quer dizer, ela faz uma pergunta esclarecedora em vez de adivinhar.

### Correspondência de métricas para ativos e experiências

<!-- FLAG: The table covers web and mobile content. Paid media content uses separate summary metrics, such as Impressions, Clicks, and Spend with a reporting-level suffix (for example, Clicks | Asset Summary), that can't be combined with event metrics such as Asset Views (config/paid-media.md in analytics-platform.en). Confirm with the PM how the skill handles paid media, then add a row or note. -->

O Content Analytics rastreia dois tipos de conteúdo: ativos e experiências. Cada uma tem suas próprias métricas. A habilidade sempre emparelha a métrica com o tipo de conteúdo sobre o qual você pergunta.

| Tipo de conteúdo | O que é | Métricas usadas pela habilidade |
| --- | --- | --- |
| Ativos | Um conteúdo individual, como uma imagem | Exibições de ativos, cliques em ativos, taxa de cliques em ativos (CTR) |
| Experiências | Todo o texto em uma página da Web ou a combinação de texto, ativos e chamadas para ação em um aplicativo móvel | Exibições de experiência, Cliques de experiência, Taxa de cliques de experiência (CTR) |

### Arquitetura de dados do Content Analytics

A habilidade entende como os dados do Content Analytics são estruturados. Por exemplo:

* **Experience IDs:** quando você pergunta sobre uma página específica, os filtros de habilidades por ID de experiência de conteúdo que identifica essa página.
* **Atributos gerados por IA:** cada ativo e experiência é descrito por atributos como estilo de fotografia, cores, tom e estratégia de persuasão. A habilidade usa esses atributos para explicar por que o conteúdo tem bom desempenho, não apenas qual conteúdo tem bom desempenho.

Para obter a lista completa dos componentes, consulte [componentes do Content Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/content-analytics/report/components) no guia do Customer Journey Analytics.

### Atribuição

A habilidade escolhe o modelo de atribuição que se adapta à sua pergunta. Por exemplo, uma pergunta sobre cliques em uma imagem é respondida de forma diferente de uma pergunta sobre a receita para a qual essa imagem contribuiu. Para obter mais informações, consulte [Modelos de atribuição](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/attribution/models#attribution-models) no manual do Customer Journey Analytics.

### Análises e fluxos de trabalho comuns

A habilidade inclui instruções para análises de conteúdo comuns, como:

* Encontrar os atributos que ativos ou experiências de melhor desempenho têm em comum.
* Vincular a exposição do conteúdo a conversões e receita.
* Comparação de conteúdo entre canais da Web, móveis e de mídia paga.
* Comparação de qual conteúdo funciona para públicos e segmentos diferentes.
* Identificação do conteúdo que está superutilizado ou subutilizado.

### Visualizações

A habilidade seleciona visualizações que se ajustam à sua pergunta e aos dados, de modo que os resultados sejam fáceis de ler e compartilhar.

## Dicas para obter melhores resultados

* Comece bem se não tiver certeza do que perguntar. O colega de trabalho pode transformar uma pergunta geral em uma análise focada, e você pode refinar a partir daí.
* Diga se você quer dizer ativos individuais, como imagens, ou experiências inteiras, como páginas, quando souber qual deles deseja.
* Nomeie a métrica e o intervalo de datas que deseja analisar, como receita do último trimestre.
* Especifique os segmentos, públicos ou canais que deseja comparar.
* Pergunte sobre atributos de conteúdo, como imagens, temas ou mensagens, em vez de arquivos individuais, quando quiser saber por que o conteúdo tem bom desempenho.
* Adicione sua visualização de dados preferida à memória do Chat do colaborador se você sempre analisar a mesma. Consulte [Adicionar uma visualização de dados ou preferência de conjunto de relatórios na Memória](/help/chat/use-cases/data-insights/analytics-chat.md#add-a-data-view-or-report-suite-preference-in-memory).

## Próximas etapas

* Para obter mais casos de uso de desempenho de conteúdo, consulte [Visão geral de desempenho de conteúdo](/help/chat/use-cases/data-insights/content-performance.md).
* Para saber mais sobre o Content Analytics, consulte [visão geral do Content Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/content-analytics/content-analytics) no guia do Customer Journey Analytics.
* Para obter uma visão geral da análise de dados com o Chat do Colaborador, incluindo as práticas recomendadas, consulte [Analisar dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-overview.md).
