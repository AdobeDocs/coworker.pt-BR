---
title: Ferramentas do Journey Optimizer no CX Coworker Gateway
description: Saiba quais ferramentas do Adobe Journey Optimizer estão disponíveis por meio do CX Coworker Gateway.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 2%
---
# Ferramentas do Adobe Journey Optimizer no CX Coworker Gateway {#ajo-mcp}

Use as ferramentas de produto do Adobe Journey Optimizer para inspecionar campanhas, jornadas e configurações de canal de um cliente compatível com MCP. Essas ferramentas estão disponíveis por meio do [CX Coworker Gateway](overview.md) quando sua organização está habilitada e sua conta de usuário tem as permissões necessárias do Journey Optimizer.

Para obter mais informações, consulte [Trabalhar com clientes MCP](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/content-management/combine/ajo-mcp){target="_blank"} na documentação do Adobe Journey Optimizer.

Para obter uma experiência de conversação e agilidade para criar, analisar e simular jornadas, consulte a [Journey Agent](https://experienceleague.adobe.com/pt-br/docs/cx-enterprise-ai/experience-cloud-ai/agents/ajo-agent).

>[!AVAILABILITY]
>
>As ferramentas do produto Journey Optimizer estão no Beta. O acesso é apenas por convite e requer a habilitação da organização da Adobe. Consulte [Acessar ferramentas do CX Coworker Gateway](access.md).

## Principais recursos {#mcp-capabilities}

As ferramentas do Journey Optimizer fornecem uma superfície somente leitura para campanha, jornada e revisão da configuração do canal. Você pode:

- Listar campanhas do Journey Optimizer e filtrar por status.
- Recupere detalhes da campanha, incluindo o direcionamento, a programação, o canal e os metadados de configuração de conteúdo.
- Liste e inspecione jornadas em sua sandbox, incluindo ramificação, condições e ações.
- Listar configurações de canal para canais de email, SMS, push e WhatsApp.
- Listar ações de marketing disponíveis para aplicação de política de governança de dados.
- Analise a configuração da campanha, do jornada e do canal em idioma natural, sem navegar pelas telas do produto.

>[!IMPORTANT]
>
>Todas as ferramentas do Journey Optimizer na Beta atual são somente leitura. Não há suporte para criar, atualizar, excluir, iniciar, parar ou publicar campanhas ou jornadas.

## Ferramentas disponíveis {#mcp-tools}

| Ferramenta | Descrição |
| --- | --- |
| `ajo_campaign_list` | Navegue pelas campanhas de marketing do Journey Optimizer. Suporta filtragem por status, como `DRAFT`, `LIVE`, `STOPPED` e `COMPLETED`. |
| `ajo_campaign_get` | Busque detalhes e a configuração de uma campanha específica por ID, incluindo o direcionamento de público, a programação, o canal e os metadados de configurações de conteúdo. |
| `ajo_journey_list` | Navegue por todas as jornadas na sandbox do Journey Optimizer. |
| `ajo_journey_get` | Busque detalhes completos para uma jornada específica por ID, incluindo sua ramificação, condições e ações. |
| Visualização de jornada | Renderize a estrutura e o fluxo de uma jornada para exploração visual e interativa. |
| `ajo_channel_configuration_list`, `ajo_channel_configuration_get` | Exibir predefinições de superfície e de marca para email, SMS, push ou [!DNL WhatsApp] canais. |
| `ajo_channel_configuration_resource_list`, `ajo_channel_configuration_resource_get` | Liste e recupere recursos de configuração de suporte referenciados pelas configurações de canal, como credenciais de push, subdomínios de email, pools de IP, credenciais de SMS e credenciais [!DNL WhatsApp]. |
| `ajo_marketing_action_list` | Liste as ações de marketing disponíveis para a aplicação da política de governança de dados. |

## Exemplo de prompts {#mcp-use-cases}

| Meta | Exemplo de prompt |
| --- | --- |
| Visão geral da campanha | &quot;Mostre-me todas as minhas campanhas do Journey Optimizer.&quot; |
| Auditoria de status | &quot;Quais campanhas estão ativas no momento?&quot; |
| Detalhes da campanha | &quot;Obtenha os detalhes completos da campanha `[campaign ID]`.&quot; |
| Visão geral da jornada | &quot;Mostre-me todas as minhas jornadas do Journey Optimizer.&quot; |
| Detalhes da jornada | &quot;Obtenha os detalhes completos da jornada `[journey ID]`, incluindo ramificação e condições.&quot; |
| Público-alvo e direcionamento | &quot;Qual público-alvo é direcionado na campanha `[campaign ID]`?&quot; |
| Agendamento e tempo | &quot;Quando a campanha `[campaign ID]` está agendada para execução?&quot; |
| Solução de problemas | &quot;Revise a configuração da campanha `[campaign ID]` e sinalize possíveis problemas.&quot; |
| Configuração de canais | &quot;Quais configurações de canal de email estão disponíveis?&quot; |
| Auditoria de canal | &quot;Quais configurações de canal estão ausentes ou incompletas?&quot; |
| Governança | &quot;Quais ações de marketing estão disponíveis na minha sandbox?&quot; |

## Ferramentas de gerenciamento de conteúdo {#mcp-content-management}

Além das ferramentas de produto somente leitura mencionadas acima, os usuários do Journey Optimizer podem descobrir e gerenciar ativos de conteúdo — modelos de conteúdo, fragmentos, páginas de aterrissagem e conteúdo de mensagem em linha do jornada ou da campanha — diretamente do CX Coworker usando prompts em linguagem natural. Esse recurso é alimentado por um conjunto separado de ferramentas MCP com capacidade de leitura e gravação para conteúdo Journey Optimizer e está disponível para todos os clientes que têm acesso ao CX Coworker.

Para obter mais informações, consulte [Ferramentas de gerenciamento de conteúdo](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/get-started/essentials/ajo-coworker-skills#content-management){target="_blank"} na documentação do Adobe Journey Optimizer.

As ferramentas de gerenciamento de conteúdo permitem:

- Navegue por modelos de conteúdo, fragmentos e páginas de aterrissagem e recupere sua estrutura, metadados e status.
- Recupere o conteúdo da mensagem em linha configurado em um nó de ação de campanha ou do jornada.
- Crie e atualize modelos de conteúdo para qualquer canal.
- Criar, atualizar, clonar e publicar fragmentos.
- Substituir uma variante de canal em uma mensagem integrada do nó de ação de campanha ou jornada.

>[!IMPORTANT]
>
>Ao contrário das ferramentas de produto somente leitura mencionadas acima, as ferramentas de gerenciamento de conteúdo são compatíveis com operações de gravação. A pesquisa de texto completo em modelos ou fragmentos, a validação de modelo ou fragmento, a criação ou publicação de páginas de aterrissagem e a exclusão de modelos de conteúdo, fragmentos ou páginas de aterrissagem não são compatíveis.

## Contexto e permissões do produto {#mcp-context}

Sua conta de usuário deve ter permissão para exibir as campanhas do Journey Optimizer, as jornadas e as configurações de canal que você consulta. O MCP não ignora permissões de produto.

Se sua organização usar várias sandboxes, especifique a sandbox ou o contexto de ambiente no prompt quando precisar de resultados de uma sandbox específica.

## Limitações conhecidas {#mcp-limitations}

| Limitação | Descrição | Solução alternativa |
| --- | --- | --- |
| Superfície somente leitura | As ferramentas do Journey Optimizer só expõem as operações de recuperação. Não é possível criar, atualizar, excluir, iniciar, parar ou publicar campanhas ou jornadas. | Use a interface do usuário do Journey Optimizer ou as APIs para operações de gravação. |
| Sem envolvimento ou métricas de desempenho | As ferramentas não retornam dados de relatório como impressões, taxas de click-through, conversões ou estatísticas de delivery. | Use os relatórios do Journey Optimizer, as ferramentas do Customer Journey Analytics ou as ferramentas do Adobe Analytics para obter métricas de desempenho. |
| A paginação de lista de campanhas é limitada | A listagem de campanha retorna a primeira página de resultados, até 50 campanhas classificadas alfabeticamente. Os valores de deslocamento e limite não são aplicados. | Use `Get Campaign` diretamente se a ID da campanha for conhecida. Use a interface do usuário do Journey Optimizer para navegação e filtragem completas. |
| Nenhuma filtragem do lado do servidor por data, canal ou programação | A listagem de campanha oferece suporte à filtragem de status, mas não à filtragem de data de publicação, data de agendamento, canal ou tipo de campanha. | Use a lista de campanha da interface do usuário do Journey Optimizer para filtragem de data nativa e canal. |
| Recuperação de conteúdo de mensagens indisponível por meio das ferramentas do produto | O HTML de mensagem, as linhas de assunto, os tokens de personalização e o conteúdo da oferta não estão disponíveis por meio das ferramentas de produto somente leitura acima. | Use as [ferramentas de gerenciamento de conteúdo](#mcp-content-management) para recuperar e atualizar o conteúdo da mensagem integrada ou exibi-lo diretamente na interface do usuário do Journey Optimizer. |