---
title: Migrar projetos do Adobe Analytics para o Customer Journey Analytics
description: Use o Colaborador para validar, mapear e migrar projetos do Adobe Analytics Workspace e seus componentes para o Customer Journey Analytics e, em seguida, verificar o status da migração.
feature: AI Tools
role: Admin
level: Intermediate
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: decc8d209d4c9c177c6329a30668f0bbb8bd2c00
workflow-type: tm+mt
source-wordcount: '1785'
ht-degree: 1%
---

# Migrar projetos do Adobe Analytics para o Customer Journey Analytics com o Co-worker

<!-- FLAG: Confidence: High for the conversation flow, which is sourced from screenshots of the Coworker UI (October 2026) and the aa-mcp tool descriptions. The component migration tools run through the aa-mcp integration; there's no dedicated skill yet. Medium for statements that Coworker shares mappings and migration rules with migrations in the Adobe Analytics user interface; the user believes this is likely. Confirm with engineering. -->

Use o Adobe CX Enterprise Coworker para migrar projetos do Adobe Analytics e seus componentes associados para o Customer Journey Analytics em uma única conversa.

O parceiro valida se as dimensões e métricas do seu projeto estão mapeadas para a visualização de dados do Customer Journey Analytics, ajuda a mapear qualquer uma que não esteja e recria o projeto no Customer Journey Analytics.

<!-- FLAG: Add the planned general availability date when it's confirmed. -->

>[!AVAILABILITY]
>
>A funcionalidade descrita neste artigo está na fase de Teste limitado da versão e pode ainda não estar disponível em seu ambiente. Essa nota será removida quando a funcionalidade estiver disponível no geral.

>[!IMPORTANT]
>
>Antes de migrar qualquer projeto, leia [Preparar para migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration) na documentação do Adobe Analytics. Ele explica como se preparar para uma migração, o que está incluído, quais elementos causam erros e como os mapeamentos afetam toda a organização. Essas informações se aplicam às migrações no Co-worker.

## Diferenças da migração na interface do usuário do Adobe Analytics

<!-- FLAG: Add rows as differences are confirmed. Who can migrate and How you migrate: SME Scott Tomko (October 2026); Coworker matches the Analytics 2.0 Component Migration APIs, and functionally both methods do much the same thing. Project owner: Coworker behavior is from a test conversation (October 2026); the Adobe Analytics user interface behavior is from component-migration.md in the Adobe Analytics docs. Mapping dimensions and metrics: Confidence Medium for the Coworker column, which is based on the aa-mcp tool descriptions and a test conversation, not on an observed failed validation. Confirm that Coworker suggests and updates mappings, and whether it asks for confirmation before it updates a mapping. The Adobe Analytics user interface behavior is from component-migration.md in the Adobe Analytics docs. -->

A migração de projetos com o Colaborador é diferente da migração na interface do usuário do Adobe Analytics das seguintes maneiras:

| | Coworker | Interface do usuário do Adobe Analytics |
| --- | --- | --- |
| **Quem pode migrar projetos** | Administradores e usuários do Adobe Analytics com a permissão [!UICONTROL **Migração de componentes**] | Somente administradores do Adobe Analytics |
| **Proprietário do projeto** | O usuário que está executando a migração | O usuário especificado no campo [!UICONTROL **Proprietário do projeto**] |
| **Mapeamento de dimensões e métricas** | O colaborador valida o projeto e lista como cada dimensão e métrica é mapeada. Para os que não podem ser mapeados automaticamente, o Colaborador sugere uma dimensão ou métrica em sua visualização de dados e atualiza o mapeamento. | Na seção [!UICONTROL **Mapear esquema**], você seleciona cada dimensão ou métrica com um status [!UICONTROL **Não mapeado**] e mapeia-a manualmente. |
| **Como você migra** | Descreva o que você deseja em um prompt. Colaborador faz o trabalho, fazendo algumas perguntas ao longo do caminho. Por exemplo, o Colaborador pode criar um projeto com os componentes que você nomeia e, em seguida, migrá-lo. Consulte [Iniciar com componentes específicos](#start-from-specific-components). | Crie um projeto no Analysis Workspace, adicione os componentes que deseja migrar e salve o projeto. Em seguida, em [!UICONTROL **Migração de componentes**], selecione o projeto, especifique um proprietário de projeto, mapeie o esquema para cada conjunto de relatórios e selecione [!UICONTROL **Migrar**]. |

## Pré-requisitos

<!-- FLAG: Confidence: High for the Adobe Analytics MCP and permission bullets, which come from the release announcement and SME Scott Tomko (October 2026): like the Analytics 2.0 Component Migration APIs, Coworker lets non-admins with the Component Migration permission migrate projects, while the Adobe Analytics UI is admin-only. Open question: Coworker makes the user who runs the migration the owner of the new project, but the aa-mcp tool description says the owner "should be an admin" and the Adobe Analytics component migration docs say the owner must be a Customer Journey Analytics administrator. Confirm whether a non-admin who runs a migration needs Customer Journey Analytics admin rights, or whether Coworker assigns a different owner. -->

Para migrar projetos com o Colaborador, é necessário:

* Acesso ao Adobe Analytics MCP. As ferramentas de migração de componentes são ativadas automaticamente para clientes com acesso ao Adobe Analytics MCP. Para confirmar que [!UICONTROL **aa-mcp**] está conectado, consulte [Introdução à análise de dados com o Chat de Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).

* Direitos de administrador do Adobe Analytics ou a permissão [!UICONTROL **Migração de componentes**] no Admin Console. Você não precisa ser um administrador.

* Os [pré-requisitos](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#prerequisites) para migração de componente na documentação do Adobe Analytics.

* Um projeto que usa conjuntos de relatórios de base. Os conjuntos de relatórios virtuais não podem ser migrados.<!-- FLAG: Sourced from Coworker's response in the UI. The Adobe Analytics component migration docs don't mention virtual report suites. Confirm, and consider adding it to those docs. -->

## Examine os mapeamentos do conjunto de relatórios antes de migrar

<!-- FLAG: Confidence: Medium. The recommendation to review mappings before the first migration from a report suite is inferred from the Adobe Analytics guidance to decide mappings as an organization; Coworker also validates mappings during each migration. Confirm with Scott. -->

Considere revisar como as dimensões e métricas de um conjunto de relatórios são mapeadas antes da primeira migração desse conjunto de relatórios. Os mapeamentos se aplicam a todos os projetos migrados pela sua organização, portanto, defini-los primeiro ajuda os projetos posteriores a serem aprovados na validação. Para obter orientação sobre como escolher mapeamentos, consulte [Decidir como uma organização como mapear componentes](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#decide-as-an-organization-how-you-will-map-components) na documentação da Adobe Analytics.

Para revisar os mapeamentos, selecione [!UICONTROL **Revisar somente os mapeamentos**] na guia [!UICONTROL **Escopo**] ou pergunte diretamente ao Colaborador:

**Solicitações**

* &quot;Mostrar como as dimensões e métricas do meu conjunto de relatórios são mapeadas para a minha visualização de dados&quot;
* &quot;Quais dimensões e métricas do meu conjunto de relatórios não são mapeadas para a minha visualização de dados?&quot;

Você também pode pedir ao Colaborador para atualizar mapeamentos.

Se você ignorar esta revisão, o Colaborador ainda [verificará os mapeamentos para cada projeto migrado](#review-the-validation-results-and-mappings).

## Iniciar uma migração

<!-- FLAG: Confidence: High that migration works at the project level and that components migrate with their project (component-migration.md in the Adobe Analytics docs), and that components that already exist in Customer Journey Analytics aren't re-created (prepare-component-migration.md). Medium-low for when to use each method and for combining them; this guidance is inferred and isn't in the Adobe Analytics docs. Confirm with Scott. Also confirm whether Coworker creates a project automatically when you ask it to migrate only components (for example, "Migrate my Spring sale segments to CJA"), or whether you must ask it to create the project. -->

O colaborador sempre migra um projeto e seus componentes associados. Para migrar componentes específicos, peça ao Colaborador para adicioná-los a um novo projeto e, em seguida, migrar esse projeto.

Os componentes que já existem no Customer Journey Analytics não são recriados, portanto, você pode usar ambos os métodos. Por exemplo, migre primeiro os projetos mais importantes e depois migre os componentes restantes. Escolha onde começar com base no que você deseja no Customer Journey Analytics:

* **Migre um projeto** quando quiser manter os painéis e as visualizações do projeto no Customer Journey Analytics. Consulte [Iniciar com um projeto](#start-from-a-project).
* **Migre componentes específicos** quando quiser componentes como segmentos, métricas calculadas ou intervalos de datas no Customer Journey Analytics, mas não precisar de nenhum dos projetos que os utilizam. Por exemplo, você pode planejar criar novos projetos no Customer Journey Analytics que os incluam. Consulte [Iniciar com componentes específicos](#start-from-specific-components).

### Iniciar com base em um projeto

Para migrar um projeto e seus componentes associados:

1. Faça logon no Colaborador.

1. Selecione **[!UICONTROL Novo chat]**.

1. No campo de texto, solicite que o Colaborador migre seu projeto. Por exemplo:

   **Aviso**

   > Quero migrar componentes do Adobe Analytics para o Customer Journey Analytics.

   O Colaborador descreve o que pode ser migrado e inicia um questionário.

1. Na guia [!UICONTROL **Escopo**], selecione uma das seguintes opções e, em seguida, selecione [!UICONTROL **Avançar**]:

   <!-- FLAG: Confidence: Medium for the "Plan a full upgrade" description. It likely hands off to the implementation guide skill and leaves the migration flow. Confirm with engineering. Also confirm what the Source & target tab asks; it was skipped in the screenshots. The Next and Submit buttons on the first questionnaire's Source & target and Review tabs are assumed to work like the second questionnaire. -->

   | Opção | Descrição |
   | --- | --- |
   | [!UICONTROL **Um projeto específico do AA**] | Migre um projeto que você nomeia. Siga as etapas restantes nesta seção. |
   | [!UICONTROL **Revisar somente os mapeamentos**] | Verifique como as métricas e dimensões de um conjunto de relatórios são mapeadas para uma visualização de dados, sem migrar nada. Consulte [Revisar os mapeamentos do conjunto de relatórios antes de migrar](#review-report-suite-mappings-before-you-migrate). |
   | [!UICONTROL **Planejar uma atualização completa**] | Obtenha um plano completo para mudar do Adobe Analytics para o Customer Journey Analytics. Consulte [Planejar sua implementação com o Colaborador](/help/chat/use-cases/data-insights/implementation-guide.md). |

1. (Opcional) Responda às perguntas da guia [!UICONTROL **Source e target**] e selecione [!UICONTROL **Avançar**].

1. Na guia [!UICONTROL **Revisão**], confirme suas respostas e selecione [!UICONTROL **Enviar**].

   O Colaborador verifica a quais empresas do Adobe Analytics você tem acesso, quantos conjuntos de relatórios básicos cada um tem e, em seguida, inicia um segundo questionário.

1. Responda às seguintes perguntas, selecionando [!UICONTROL **Próximo**] após cada uma:

   | Tabulação | Pergunta | Contexto adicional |
   | --- | --- | --- |
   | [!UICONTROL **Projeto**] | Qual é o nome do projeto do AA que você deseja migrar? | Um nome parcial está correto. |
   | [!UICONTROL **Conjunto de relatórios**] | Qual conjunto de relatórios o projeto usa? | Selecione um conjunto de relatórios na lista ou digite o nome de outro conjunto. |
   | [!UICONTROL **Visualização de dados**] | Para qual visualização de dados do CJA ele deve ser migrado? | (Opcional) Digite o nome de uma visualização de dados ou deixe-a em branco e o Colaborador sugere visualizações de dados correspondentes. |

1. Na guia [!UICONTROL **Revisão**], confirme suas respostas e selecione [!UICONTROL **Enviar**].

   Para ignorar o questionário em qualquer etapa, selecione [!UICONTROL **Ignorar questionário**] e descreva o que deseja no chat.

1. Continue com [Revise os resultados e os mapeamentos da validação](#review-the-validation-results-and-mappings).

### Começar com componentes específicos

<!-- FLAG: Sourced from a prompt that SME Scott Tomko ran in Coworker (October 2026). The example is generalized; the original prompt named a customer. Coworker may ask a few questions along the way. Confirm what happens to the project that Coworker creates in Adobe Analytics, and to its migrated copy in Customer Journey Analytics, if you only wanted the components. -->

Para migrar componentes específicos:

1. Peça ao Colaborador para criar um projeto com esses componentes e, em seguida, migrá-lo. Por exemplo:

   **Aviso**

   > Quero migrar todos os meus segmentos do Analytics com &quot;Liquidação de primavera&quot; no nome para CJA. Crie um novo projeto do Workspace com todos esses segmentos adicionados e migre esse projeto para o CJA.

   O colaborador cria o projeto no Adobe Analytics.

1. Continue com a seguinte seção, [Revise os resultados e mapeamentos da validação](#review-the-validation-results-and-mappings).

## Revisar os resultados e mapeamentos da validação

<!-- FLAG: Confidence: Medium for the steps that fix a failed validation. They're based on the aa-mcp tool descriptions and on a test conversation where validation passed only after the project's panel was switched to a base report suite. Confirm how Coworker presents a failed validation, and whether it asks for confirmation before it updates a mapping. -->

O colaborador valida o projeto em relação à visualização de dados selecionada e relata se o projeto pode ser migrado. Os resultados listam cada dimensão e métrica no projeto e a dimensão ou métrica da Customer Journey Analytics para a qual ela está mapeada. Por exemplo:

* **Métrica:** Ocorrências torna-se Eventos
* **Dimension:** hora permanece como Hora

Para os componentes e elementos de projeto migrados, consulte [Entender o que está incluído na migração](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#understand-what-is-included-in-a-migration) na documentação do Adobe Analytics.

Se a validação não for aprovada:

* **Dimensões ou métricas que não podem ser mapeadas automaticamente:** O Colaborador sugere uma dimensão ou métrica em sua visualização de dados para a qual mapear cada uma, atualiza o mapeamento e valida o projeto novamente. Você também pode informar ao Colaborador a dimensão ou métrica para a qual mapeá-la, por exemplo, &quot;Mapear Exibições de página para web.webPageDetails.pageViews.value&quot;.

* **Elementos sem suporte:** Remova todos os elementos sem suporte do projeto no Adobe Analytics. Por exemplo, verifique se cada painel usa um conjunto de relatórios base em vez de um conjunto de relatórios virtual. Em seguida, peça ao colaborador para verificar o projeto novamente. Para obter a lista de elementos sem suporte, consulte [Entender os elementos sem suporte que causam erros](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#understand-unsupported-elements-that-cause-errors) na documentação do Adobe Analytics.

Para verificar os mapeamentos de um conjunto de relatórios inteiro antes de migrar, consulte [Revisar mapeamentos de conjuntos de relatórios antes de migrar](#review-report-suite-mappings-before-you-migrate).

## Migrar o projeto

1. Quando a validação é aprovada, o Colaborador pergunta se é necessário criar a versão do Customer Journey Analytics do projeto na visualização de dados selecionada. Selecione [!UICONTROL **Sim, migrar**] e [!UICONTROL **Enviar**].

   Para parar sem migrar, selecione [!UICONTROL **Não, pare aqui**].

   O colaborador recria o projeto no Customer Journey Analytics, com você como o proprietário do projeto. Seu projeto original do Adobe Analytics não é alterado.

1. Continue com a seguinte seção, [Verifique o status da migração](#check-the-migration-status).

## Verifique o status da migração

As migrações são executadas em segundo plano, portanto, o novo projeto pode não estar pronto imediatamente.

1. Avisar o colega para verificar o status da migração:

   **Aviso**

   > Verificar status

   <!-- FLAG: The Failed row links to Retry a failed migration in the Adobe Analytics docs, but those steps use the Component migration page in the Adobe Analytics UI, which is admin-only. A non-admin with the Component Migration permission can't follow them. Confirm with Scott whether Coworker can retry a failed migration (for example, "Retry the migration"). If so, replace the link with a prompt. -->

   O colaborador relata um dos seguintes status:

   | Status | O que significa |
   | --- | --- |
   | Em fila | A migração está aguardando para iniciar. |
   | Iniciado | A migração está em andamento. |
   | Concluído | Migração concluída. O Colaborador fornece um resumo do que foi migrado, incluindo o nome do projeto e a visualização de dados. |
   | Falha | Falha na migração. Você pode repetir a migração. Consulte [Repetir uma migração com falha](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/component-migration/component-migration#retry-a-failed-migration) na documentação do Adobe Analytics. |

1. Quando a migração for concluída, abra o novo projeto na lista de projetos no Customer Journey Analytics Workspace.

1. (Opcional) Transfira a propriedade do projeto para qualquer usuário no Customer Journey Analytics. Para obter mais informações, consulte [Transferir ativos](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/tools/asset-transfer/transfer-assets).

Depois que uma migração for concluída, o Colaborador poderá sugerir outro projeto para migrar.

## Dicas para obter melhores resultados

* Deixe a visualização de dados em branco no questionário se não tiver certeza de qual usar. O colaborador sugere visualizações de dados que correspondam ao conjunto de relatórios.
* Depois de migrar, compare os dados do Adobe Analytics e do Customer Journey Analytics para confirmar se os relatórios são correspondentes. Consulte [Validar dados com o Colaborador ao atualizar do Adobe Analytics para o Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md).

## Próximas etapas

* Para migrar projetos na interface do usuário do Adobe Analytics, consulte [Migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/component-migration/component-migration) na documentação do Adobe Analytics.
* Para os outros casos de uso de implementação e administração, consulte [Visão geral de implementação e administração inteligente](/help/chat/use-cases/data-insights/data-governance-and-validation.md).
