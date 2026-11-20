---
title: Conector externo Jira / Atlassian Rovo
description: Saiba como configurar o conector externo Jira / Atlassian Rovo no CX Enterprise Coworker e fazer logon com Atlassian para ler e pesquisar itens de trabalho Jira.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está na versão beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 92e7715a5eb7ab4f8feb7348384c94fabc1b78cf
workflow-type: tm+mt
source-wordcount: '1482'
ht-degree: 1%
---

# Conector externo Jira / Atlassian Rovo {#jira-atlassian-rovo}

Use o conector externo [!DNL Jira] / [!DNL Atlassian Rovo] para ler e pesquisar seus itens de trabalho [!DNL Jira] no Adobe CX Enterprise Coworker. Depois de configurar o conector, peça ao Colaborador para localizar itens de trabalho, ler seus detalhes e pesquisar com Jira Query Language (JQL). O conector é um servidor MCP hospedado por [!DNL Atlassian].

>[!AVAILABILITY]
>
>O conector externo [!DNL Jira] / [!DNL Atlassian Rovo] está na versão beta. A documentação e a funcionalidade estão sujeitas a alterações.

## Configuração do conector {#connector-configuration}

O processo de configuração do conector tem três partes separadas:

* **[!DNL Atlassian]preparação:** Um administrador da organização [!DNL Atlassian] permite que o Colaborador redirecione o domínio da URL e revise as políticas de acesso MCP.
* **Configuração da organização:** um administrador de parceiro configura o conector uma vez para toda a organização. O administrador escolhe as ferramentas somente leitura que os membros podem usar.
* **Entrada de membro:** cada membro entra com sua própria conta [!DNL Atlassian]. Os membros podem acessar somente os dados do [!DNL Jira] que a conta tem permissão para exibir.

Salvar a configuração da organização não faz logon em nenhum membro nem concede permissões de [!DNL Jira]. Cada membro deve fazer logon separadamente.

O conector não tem uma conta de serviço compartilhado ou uma opção de token de API. O colega registra o aplicativo OAuth com [!DNL Atlassian] automaticamente, assim você não insere uma ID de cliente ou um segredo de cliente.

Embora o nome do conector inclua [!DNL Atlassian Rovo], o conector solicita [!DNL Jira] somente acesso de leitura e pesquisa. Ele não solicita acesso [!DNL Confluence], específico de [!DNL Rovo], de gravação ou destrutivo. Outros recursos de MCP [!DNL Atlassian] não estão necessariamente disponíveis por meio desse conector.

## Pré-requisitos {#prerequisites}

Antes de começar, verifique se você tem o seguinte:

* **Para configuração da organização:** Uma conta com permissão para gerenciar conectores de organização no Colaborador, em uma organização em que o conector [!DNL Jira] / [!DNL Atlassian Rovo] está disponível.
* **Para preparação de [!DNL Atlassian]:** um administrador de organização [!DNL Atlassian] que pode aprovar o acesso ao MCP e o domínio da URL de redirecionamento do Colaborador.
* **Para entrada de membros:** contas do [!DNL Atlassian] com acesso aos [!DNL Jira] sites, projetos e itens de trabalho pretendidos.
* **Para acesso à rede:** [!DNL Atlassian] incluis na lista de permissões de IP e diretivas de aplicativo que permitem a conexão. Um logon bem-sucedido não confirma se as solicitações de ferramenta são permitidas.
* **[!DNL Rovo]habilitado:** [!DNL Rovo] habilitado para sua organização [!DNL Atlassian] e os sites [!DNL Jira] desejados antes que os membros usem o conector. Para obter mais informações, consulte [Como habilitar o Rovo](https://www.atlassian.com/software/rovo/guides/admin-guide/rovo-activation) na documentação [!DNL Atlassian].

## Preparar acesso de [!DNL Atlassian] {#prepare-atlassian}

Antes que os membros entrem, um administrador da organização [!DNL Atlassian] prepara o acesso em [!DNL Atlassian Administration]:

1. Abra [!DNL Atlassian Administration] e selecione a organização desejada.

1. Selecione **[!UICONTROL Conectores]** > **[!UICONTROL Servidor MCP Atlassian]** > **[!UICONTROL Adicionar domínio]**.

1. Adicione o domínio da **[!UICONTROL URL de redirecionamento]** mostrado na caixa de diálogo de instalação do Colaborador. Para a caixa de diálogo, consulte [Configurar o conector para sua organização](#configure-organization).

   Siga as regras de formato de domínio [!DNL Atlassian] em vez de colar a URL completa. Para obter mais informações, consulte [Domínios disponíveis do servidor Atlassian MCP](https://support.atlassian.com/security-and-access-policies/docs/available-atlassian-mcp-server-domains/) na documentação [!DNL Atlassian].

1. Revise os grupos de permissões MCP, políticas de aplicativos e incluis na lista de permissões de IP com o administrador [!DNL Atlassian]. Para obter mais informações, consulte a seguinte documentação do [!DNL Atlassian]:

   * [Ferramentas Atlassian MCP com suporte](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/), para os grupos de permissão e escopos exigidos por cada ferramenta
   * [Controlar configurações do servidor MCP Atlassian](https://support.atlassian.com/security-and-access-policies/docs/control-atlassian-mcp-server-settings/), para autenticação e incluir na lista de permissões IP

Sempre use o URL de redirecionamento mostrado na caixa de diálogo do Colaborador para o ambiente que você está configurando. Não copie um URL de redirecionamento de outro ambiente.

## Configurar o conector do para sua organização {#configure-organization}

Os administradores disponibilizam o conector [!DNL Jira] / [!DNL Atlassian Rovo] para todos na organização. As alterações na página da organização se aplicam a todos os usuários da organização.

1. Abra **[!UICONTROL Personalizações]**, selecione **[!UICONTROL Org]** e **[!UICONTROL Conectores Externos]**. No cartão **[!UICONTROL Jira / Atlassian Rovo]**, selecione **[!UICONTROL Configurar]**. Os membros não podem configurar ou remover esta conexão.

1. Na caixa de diálogo **[!UICONTROL Connect Jira / Atlassian Rovo]**, revise a **[!UICONTROL URL do Servidor]**, `https://mcp.atlassian.com/v2/mcp` corrigida.

   Revise a **[!UICONTROL URL de redirecionamento]** e certifique-se de que um administrador [!DNL Atlassian] aprove seu domínio, conforme descrito em [Preparar acesso Atlassian](#prepare-atlassian). Você não insere nenhuma credencial OAuth.

1. Em **[!UICONTROL Ferramentas disponíveis para usuários]**, escolha as ferramentas que os membros podem usar. Para obter mais informações, consulte [Ferramentas disponíveis](#available-tools).

   A ferramenta de descoberta de sites `getAccessibleAtlassianResources` é necessária e permanece habilitada. As outras cinco ferramentas são opcionais. Para bloquear uma ferramenta opcional para todos em sua organização, remova-a. Para trazer de volta as ferramentas removidas, selecione **[!UICONTROL Restaurar todas as ferramentas]**. Você pode salvar a configuração com apenas a descoberta de site ativada, mas os membros não poderão ler ou pesquisar itens de trabalho.

   ![Caixa de diálogo Conectar Jira / Atlassian Rovo mostrando a URL do servidor, uma URL de Redirecionamento editada e seis ferramentas disponíveis para os usuários, com a ferramenta getAccessibleAtlassianResources necessária e cinco ferramentas opcionais.](./assets/jira-atlassian-rovo/org-configure.png){width="500" zoomable="yes"}

1. Selecione **[!UICONTROL Salvar conexão]** e examine os detalhes da conexão.

   O conector solicita os seguintes escopos OAuth quando cada membro se conecta:

   | Escopo | Finalidade |
   | --- | --- |
   | `read:me`, `read:account` | Autorização de suporte com a conta [!DNL Atlassian] do membro. |
   | `read:jira:agent-interface` | Ler dados de [!DNL Jira]. |
   | `search:jira:agent-interface` | Pesquisar dados de [!DNL Jira]. |
   | `offline_access` | Atualize o token de entrada. |

   O tempo limite da ferramenta é de 60 segundos. A primeira descoberta de conexão e ferramenta pode levar mais tempo.

### Ferramentas disponíveis {#available-tools}

O conector [!DNL Jira] / [!DNL Atlassian Rovo] fornece as seguintes ferramentas somente leitura:

| Ferramenta | Descrição | Controle do administrador |
| --- | --- | --- |
| `getAccessibleAtlassianResources` | Encontre os sites e as IDs de nuvem do [!DNL Atlassian] que você pode acessar. As ferramentas do [!DNL Jira] precisam dessa ferramenta. | Obrigatório |
| `atlassianUserInfo` | Obter as informações da conta do usuário conectado. | Opcional |
| `getJiraIssue` | Obter um item de trabalho [!DNL Jira] por ID ou chave. | Opcional |
| `searchJiraIssuesUsingJql` | Pesquisar itens de trabalho [!DNL Jira] com JQL. | Opcional |
| `discover` | Encontre operações de ferramenta adicionais e seus esquemas de entrada. | Opcional |
| `executeRead` | Executar operações de leitura encontradas por meio do `discover`, como ler comentários, logs de alterações, projetos, quadros e sprints. | Opcional |

>[!IMPORTANT]
>
>As ferramentas `discover` e `executeRead` dão aos membros acesso a operações de leitura adicionais permitidas como um grupo. Você não pode desativar operações individuais. Se esse acesso não for aceitável para sua organização, remova ambas as ferramentas. O conector não inclui operações de gravação (`executeWrite`) ou operações destrutivas (`executeDestructive`).

A remoção de ferramentas opcionais limita sua disponibilidade no Co-worker. Isso não reduz os escopos OAuth solicitados pelo conector na entrada.

Cada ferramenta precisa de escopos e grupos de permissões [!DNL Atlassian] específicos. Para obter mais informações, consulte [Ferramentas Atlassian MCP com suporte](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/) na documentação [!DNL Atlassian].

## Fazer logon como membro {#sign-in-as-a-member}

Depois que um administrador configura o conector, cada membro entra com sua própria conta [!DNL Atlassian]. Você não precisa de uma ID do cliente, segredo do cliente ou token de acesso para entrar.

1. Abra **[!UICONTROL Personalizações]**, selecione **[!UICONTROL Usuário]** e selecione **[!UICONTROL Conectores Externos]**.

1. Encontre o cartão **[!UICONTROL Jira / Atlassian Rovo]**. Se o cartão exibir **[!UICONTROL Não configurado]** e **[!UICONTROL Ainda não disponível. Seu administrador precisa configurar isso.]**, peça ao seu administrador para [configurar o conector](#configure-organization). Os membros não podem configurar o conector.

1. Selecione **[!UICONTROL Entrar]** e use a conta [!DNL Atlassian] que tem acesso ao site [!DNL Jira] desejado. Conclua qualquer logon único (SSO), autenticação multifator (MFA) e prompts de consentimento necessários. Revise o acesso de leitura e pesquisa solicitado antes de consentir.

   >[!IMPORTANT]
   >
   >Continue apenas se você reconhecer o aplicativo e sua organização aprovar o acesso solicitado.

1. Retorne ao Colaborador e abra os detalhes do conector. A conexão é somente leitura para membros e você pode exibir as ferramentas que o administrador habilitou. Selecione **[!UICONTROL Testar conexão]** para confirmar a conexão.

1. Como opção, execute uma pequena verificação somente leitura, conforme descrito em [Verificar seu acesso ao Jira](#check-access).

Um teste bem-sucedido não confirma se você pode acessar cada [!DNL Jira] site, projeto ou item de trabalho.

## Verifique seu acesso ao [!DNL Jira] {#check-access}

Para confirmar se o conector pode ler seus dados, inicie um chat e insira um prompt somente leitura.

Exemplo de prompt:

* &quot;Procure no Jira até cinco itens de trabalho atribuídos a mim, solicitados pela atualização mais recente. Inclua as chaves e os links. Não modifique nada.&quot;

Para que esse prompt funcione, o administrador deve habilitar uma ferramenta de pesquisa e a conta [!DNL Jira] deve ter permissão para exibir os itens de trabalho.

## Solução de problemas de acesso {#troubleshoot-access}

Se houver falha no logon ou no acesso, verifique o seguinte com o administrador:

| Problema | O que verificar |
| --- | --- |
| Entrada bloqueada para o cliente ou domínio | Confirme se o domínio da URL de redirecionamento para seu ambiente foi aprovado em [!DNL Atlassian Administration], nas configurações do **[!UICONTROL servidor MCP Atlassian]**. |
| O consentimento foi bem-sucedido, mas as chamadas de ferramenta são negadas | Verifique suas permissões do [!DNL Jira], os grupos de permissões MCP do [!DNL Atlassian], as políticas do aplicativo e as incluis na lista de permissões de IP. Para os grupos de permissão exigidos por cada ferramenta, consulte [Ferramentas Atlassian MCP suportadas](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/). |
| A pesquisa JQL falha, mas outras leituras funcionam | Confirme se o administrador habilitou `searchJiraIssuesUsingJql` e se a conexão solicita o escopo `search:jira:agent-interface`. |
| O consentimento retorna `invalid_request` | Peça ao administrador para confirmar que a conexão solicite `read:me` e `read:account` além dos escopos [!DNL Jira]. |
| Você ainda verá escopos mais antigos após uma alteração | Uma substituição de provedor de autenticação `jira_login` de nível de usuário obsoleta pode ter precedência sobre a conexão da organização. Peça a um administrador para atualizar ou remover apenas essa substituição obsoleta e entre novamente. |
| Uma ferramenta está ausente | Peça ao administrador para verificar a seleção da ferramenta. Operações de leitura adicionais precisam de `discover` e `executeRead`, os escopos necessários e as permissões certas. |
| **[!UICONTROL A conexão de teste]** está lenta ou expira | A descoberta de ferramentas pode levar mais tempo do que o tempo limite de 60 segundos da ferramenta. Verifique se o problema é a descoberta lenta ou uma falha de logon antes de alterar as credenciais. |

Quando solicitar ajuda, não compartilhe senhas, tokens, códigos de autorização ou URLs de consentimento. Não os inclua em capturas de tela ou tíquetes de suporte.
