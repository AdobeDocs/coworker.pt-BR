---
title: Validar e controlar dados do Analytics com o Chat do parceiro
description: Planeje sua implementação, rastreie-a em uma lista de verificação e valide os dados do Adobe Analytics, Customer Journey Analytics e Experience Platform com o Chat do colaborador.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: f914f4a123216985ae9b562413f26e7b8c29eb0f
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%
---

# Visão geral da governança e validação de dados

Use o Adobe CX Enterprise Coworker Chat para configurar, migrar e gerenciar a implementação de análise e garantir que você possa confiar nos dados por trás de cada resposta. O colaborador pode planejar sua implementação, transformar esse plano em uma lista de verificação que sua equipe pode rastrear e validar seus dados após a coleta.

A governança e validação de dados é um dos vários domínios de análise no Chat de colegas de trabalho. Para ver todos os domínios, consulte [Iniciar análise no Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) em Analisar dados com o Chat do Colaborador.

**Recomendado para:** Administrador

## Como o fluxo de trabalho de implementação se encaixa

Os casos de uso dessa página seguem um fluxo de trabalho opcional de três estágios. Você pode usar qualquer estágio sozinho. Por exemplo, você pode validar seus dados sem gerar primeiro um plano ou uma lista de verificação.

1. **Plano:** obtenha uma implementação personalizada e ordenada ou um plano de atualização. Consulte [Planejar sua implementação com o Colaborador](/help/chat/use-cases/data-insights/implementation-guide.md).
1. **Implementar:** Transforme seu plano em uma lista de verificação em Projetos de Colaborador que sua equipe pode atribuir e acompanhar. Consulte [Gerar uma lista de verificação de implementação com Projetos de Colaborador](/help/chat/use-cases/data-insights/intelligent-checklist.md).
1. **Validar:** Confirme se seus dados estão configurados e coletados corretamente. Consulte os casos de uso de validação na tabela [Casos de uso](#use-cases).

## Pré-requisitos

<!-- FLAG: Confidence: Medium for the shared bullets. They differ from the other domain pages on purpose: planning doesn't query your data, and Experience Platform validation uses Experience Platform datasets rather than data views or report suites. The permission inheritance for Experience Platform is inferred. High for the "Additional prerequisite" notes in the Use cases table, which are sourced from the "Before you begin" section of each linked article. Some of those articles flag their own prerequisites as unconfirmed (implementation-guide.md, intelligent-checklist.md, streaming-media-validation.md), so verify those rows when those flags are resolved. Validate dataset quality for Customer Journey Analytics is a video page with no stated prerequisites, so it isn't listed. -->

Para usar os casos de uso nesta página, você precisa:

* Acesso ao Bate-papo de Colaborador. Consulte [Introdução à análise de dados com o Chat de Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).
* Visualize o acesso aos dados que deseja validar. O Chat do colega herda suas permissões dos aplicativos do Adobe aos quais ele se conecta.

## Casos de uso

| Caso de uso | Função |
| --- | --- |
| [Planeje sua implementação](/help/chat/use-cases/data-insights/implementation-guide.md)<p>![Planeje sua implementação](../../assets/ui-guide-6.png)</p> | Cria um plano personalizado e passo a passo para implementar o Customer Journey Analytics, atualizar da Adobe Analytics ou configurar a coleção Content Analytics, Marketing Campaign Analytics ou Streaming de Mídia na Edge. Os planos incluem detalhes como proprietários, estimativas de esforço, dependências e etapas de validação.<p>**Exemplo de prompt:** &quot;Ajude-me a planejar minha implementação do Customer Journey Analytics&quot;</p><p>**Pré-requisito adicional:** Além dos [pré-requisitos gerais](#prerequisites), este caso de uso também requer que você saiba qual caminho de implementação se aplica a você, além de detalhes básicos sobre o ambiente atual, como o status de licenciamento ou o caminho de assimilação de dados planejado.</p><p>Para obter mais informações, consulte [Planejar a implementação com o Colaborador](/help/chat/use-cases/data-insights/implementation-guide.md).</p> |
| [Gerar uma lista de verificação de implementação](/help/chat/use-cases/data-insights/intelligent-checklist.md)<p>![Gerar uma lista de verificação de implementação](../../assets/data-validation-aa-cja/date-detail.png)</p> <p>Experimental</p> | Transforma seu plano de implementação do Customer Journey Analytics em uma lista de verificação em Projetos de colaboração, onde sua equipe pode atribuir etapas, rastrear status e adicionar portas de aprovação.<p>**Pré-requisito adicional** Além dos [pré-requisitos gerais](#prerequisites), este caso de uso também requer uma conversa de guia de implementação concluída e acesso aos Projetos de Colaborador na sua organização.</p><p>Para obter mais informações, consulte [Gerar uma lista de verificação de implementação com Projetos de Colaborador](/help/chat/use-cases/data-insights/intelligent-checklist.md).</p> |
| [Validar dados ao atualizar do Adobe Analytics para o Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md)<p>![Validar dados ao atualizar do Adobe Analytics para o Customer Journey Analytics](../../assets/data-validation-aa-cja/trend-bar-card.png)</p> | Compara dimensões, métricas e tendências entre seus conjuntos de relatórios do Adobe Analytics e visualizações de dados do Customer Journey Analytics, sinaliza discrepâncias e recomenda correções para oferecer suporte à atualização.<p>**Recomendado para:** Administrador, Analista</p><p>**Prompts de exemplo:**</p><ul><li>&quot;Comparar meu conjunto de relatórios do AA com minha visualização de dados do CJA&quot;</li><li>&quot;Quais métricas não correspondem entre o AA e o CJA?&quot;</li></ul><p>**Pré-requisito adicional:** Além dos [pré-requisitos gerais](#prerequisites), este caso de uso também requer o conjunto de relatórios do Adobe Analytics que você deseja validar e a exibição de dados do Customer Journey Analytics que contém os mesmos dados.</p><p>Para obter mais informações, consulte [Validar dados com o Colaborador ao atualizar do Adobe Analytics para o Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md).</p> |
| [Validar a implementação de mídia de streaming](/help/chat/use-cases/data-insights/streaming-media-validation.md)<p>![Validar a implementação de mídia de streaming](../../assets/ui-guide-8.png)</p> <p>Experimental</p> | Verifica o fluxo de dados, o esquema, o conjunto de dados, a visualização de dados e os dados da sessão para confirmar se o rastreamento de mídia de transmissão está configurado e coletando os dados corretamente.<p>**Exemplo de prompt:** &quot;Qual é a integridade geral da minha implementação de mídia de streaming?&quot;</p><p>**Pré-requisito adicional:** Além dos [pré-requisitos gerais](#prerequisites), este caso de uso também requer que os dados da Experience Platform e da Customer Journey Analytics de sua organização estejam conectados ao Coworker. Para alguns modos de validação, também é necessário uma ID de sessão de vídeo ou um arquivo de log.</p><p>Para obter mais informações, consulte [Validar a implementação de mídia de streaming com o Colaborador](/help/chat/use-cases/data-insights/streaming-media-validation.md).</p> |
| [Validar a qualidade do conjunto de dados para o Customer Journey Analytics](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md)<p>![Validar a qualidade do conjunto de dados para o Customer Journey Analytics](../../assets/data-validation-aep/dataset-validation.png)</p> <p>Experimental (na próxima semana)</p> | Identifica os conjuntos de dados que alimentam seus relatórios do Customer Journey Analytics e, em seguida, verifica os esquemas, a qualidade da identidade e a qualidade do campo para que você possa resolver problemas antes de criar painéis.<p>Para obter mais informações, consulte [Validar dados do Customer Journey Analytics com a habilidade de validação de dados no Colaborador](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md).</p> |
| [Validar dados após assimilação no Experience Platform](/help/chat/use-cases/data-insights/data-validation-aep.md)<p>![Validar dados após assimilação no Experience Platform](../../assets/data-validation-aep/null-values.png)</p> | Executa verificações estatísticas e semânticas em conjuntos de dados e campos do Experience Platform para encontrar problemas de qualidade de dados, como valores inválidos ou problemas de mapeamento, após uma nova implementação ou como parte do gerenciamento contínuo de dados.<p>**Prompts de exemplo:**</p><ul><li>&quot;Validar o conjunto de dados [nome do conjunto de dados]&quot;</li><li>&quot;Validar o [campo de dados] do conjunto de dados [nome do conjunto de dados]&quot;</li></ul><p>**Pré-requisito adicional:** Além dos [pré-requisitos gerais](#prerequisites), este caso de uso também requer o nome ou a ID do conjunto de dados que você deseja validar. Opcionalmente, você pode fornecer o nome de um campo específico para validação.</p><p>Para obter mais informações, consulte [Validar os dados do Experience Platform com o Colaborador](/help/chat/use-cases/data-insights/data-validation-aep.md).</p> |
| [Acelere os insights de dados](/help/chat/use-cases/data-insights/accelerate-data-insights.md) | Mostra em um vídeo como o Coworker planeja sua implementação, executa ações compatíveis e orienta etapas de produto e desenvolvimento na Adobe Experience Manager, Experience Platform, Web SDK e Customer Journey Analytics até que os dados de envolvimento do site estejam prontos para análise.<p>Para obter mais informações, consulte [Acelerar insights de dados com o Colaborador, o AEM e o CJA](/help/chat/use-cases/data-insights/accelerate-data-insights.md).</p> |

## Habilidades usadas

<!-- FLAG: Confidence: High for `aa-cja-validation` (listed in the Skills and limitations table and in workflows.md). Medium for `data-validation`: workflows.md lists it, but with a TODO to confirm the skill ID with engineering. Medium for the implementation guide skills and the Streaming Media Validation skill: the articles name them but don't give technical skill IDs, so they're listed by display name. Only `aa-cja-validation` currently appears in the Skills and limitations table on analytics-overview.md. Add the others there so the link below covers them. -->

O colaborador usa as seguintes habilidades para os casos de uso descritos neste artigo. Para obter uma lista de todas as habilidades de análise, incluindo as permissões necessárias e as que não são abordadas, consulte [Habilidades e limitações](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) em Analisar dados com o Chat do Colaborador.

| Habilidade | Usado para |
| --- | --- |
| Habilidades no guia de implementação (uma para Customer Journey Analytics, uma atualização do Adobe Analytics para Customer Journey Analytics, Content Analytics, Marketing Campaign Analytics e mídia de streaming) | Planejar a implementação |
| `aa-cja-validation` | Validar dados ao atualizar do Adobe Analytics para o Customer Journey Analytics |
| Habilidade de validação de mídia de transmissão | Validar a implementação da mídia de transmissão |
| Habilidade de validação de dados (`data-validation`) | Validar a qualidade do conjunto de dados para o Customer Journey Analytics<br>Validar dados após assimilação no Experience Platform |

## Dicas para obter melhores resultados

* Nomeie o conjunto de relatórios específico e a visualização de dados que deseja comparar ao validar os dados.
* Use os resultados da validação como um guia para suas próprias alterações. As habilidades de Validação de mídia de transmissão e Validação de dados identificam problemas, mas não alteram sua configuração ou dados.
* Execute novamente a validação de mídia de transmissão após cada alteração de implementação. Ele é executado sob demanda e não fornece monitoramento contínuo.
* Use as habilidades do guia de implementação somente para planejamento. Eles não acessam os sistemas Adobe nem executam a implementação.

## Próximas etapas

* Para obter uma visão geral da análise de dados com o Chat do Colaborador, incluindo os outros domínios de análise e práticas recomendadas, consulte [Analisar dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-overview.md).
* Para configurar o Chat do Colaborador e percorrer um exemplo funcional, consulte [Introdução à análise de dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).
