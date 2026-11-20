---
title: Conector externo do Slack
description: Saiba como configurar o conector externo do Slack no CX Enterprise Coworker com seu próprio aplicativo Slack e como fazer logon para usar suas conversas do Slack no chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está na versão beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 877954880bf6fda5151dcb343af92888db21cef4
workflow-type: tm+mt
source-wordcount: '2268'
ht-degree: 0%
---

# Conector externo do Slack {#slack}

Use o conector externo do [!DNL Slack] para trabalhar com suas conversas do [!DNL Slack] no Adobe CX Enterprise Coworker. Depois de configurar o conector, peça ao Coworker para pesquisar mensagens e arquivos, ler canais e threads e encontrar pessoas. Você também poderá enviar mensagens e respostas se o administrador ativar essas ferramentas. O conector usa o servidor remoto oficial de Protocolo de Contexto de Modelo (MCP) hospedado por [!DNL Slack].

>[!AVAILABILITY]
>
>O conector externo [!DNL Slack] está na versão beta. A documentação e a funcionalidade estão sujeitas a alterações.

## Configuração do conector {#connector-configuration}

O processo de configuração do conector tem três partes separadas:

* Preparação do aplicativo **[!DNL Slack]:** O proprietário de um aplicativo [!DNL Slack] prepara um aplicativo qualificado, registra a URL de redirecionamento do Colaborador e define os escopos do usuário. A Adobe não fornece um aplicativo [!DNL Slack] gerenciado.
* **Configuração da organização:** um administrador de parceiro configura o conector uma vez para toda a organização. O administrador insere as credenciais do aplicativo e escolhe os escopos OAuth do usuário e as ferramentas que os membros podem usar.
* **Entrada de membro:** cada membro entra com sua própria conta [!DNL Slack]. Os membros podem acessar somente o conteúdo que sua conta do [!DNL Slack] pode acessar.

O conector não usa um bot compartilhado ou uma identidade [!DNL Slack] compartilhada. O colaborador envia mensagens e respostas como o membro que está conectado. Salvar a configuração da organização não faz logon em nenhum membro nem concede acesso adicional a [!DNL Slack]. Cada membro deve fazer logon separadamente.

## Pré-requisitos {#prerequisites}

Antes de começar, verifique se você tem o seguinte:

* **Acesso de colaborador:** uma conta com permissão para gerenciar conectores de organização, em uma organização em que o conector [!DNL Slack] está disponível.
* **Um aplicativo [!DNL Slack]:** um aplicativo interno ou um aplicativo [!DNL Slack Marketplace] aprovado para seu espaço de trabalho. Você também precisa de um proprietário do aplicativo que possa confirmar os escopos de usuário aprovados e editar as configurações do aplicativo.
* **Credenciais do aplicativo:** a ID do cliente e o segredo do cliente do aplicativo, compartilhados por meio do processo aprovado para manipulação de credenciais.
* **Decisão de escopo e ferramenta:** as ferramentas de leitura, mensagens e rascunho que sua organização planeja habilitar e os escopos OAuth de usuário que planeja solicitar.
* **Um espaço de trabalho ou canal de teste:** Um local para verificar a conexão com membros que concordam em testá-la. Não envie mensagens de teste nos canais do cliente ou de produção.

>[!IMPORTANT]
>
>Nunca compartilhe segredos do cliente, tokens de acesso ou outras credenciais em capturas de tela, bate-papos ou tíquetes de suporte. Digite credenciais somente nos campos seguros da caixa de diálogo de configuração.

## Preparar seu aplicativo Slack {#prepare-slack-app}

Antes de configurar o conector no Coworker, o proprietário do aplicativo prepara o aplicativo [!DNL Slack]. Um administrador de aplicativo de espaço de trabalho ou organização também pode precisar aprová-lo. Para os requisitos de [!DNL Slack], consulte [servidor MCP do Slack](https://docs.slack.dev/ai/slack-mcp-server/) na documentação do desenvolvedor do [!DNL Slack].

### Escolha um aplicativo qualificado {#choose-eligible-app}

[!DNL Slack] dá suporte ao servidor MCP somente para aplicativos personalizados internos e aplicativos publicados no [!DNL Slack Marketplace]. Aplicativos não listados e distribuídos fora da organização não podem usar o servidor MCP [!DNL Slack]. Ativar a distribuição pública sozinha não torna um aplicativo qualificado.

1. Escolha o espaço de trabalho ou a organização que será proprietária do aplicativo e o proprietário do aplicativo.
1. Em [gerenciamento de aplicativos Slack](https://api.slack.com/apps), crie um novo aplicativo nesse espaço de trabalho. Para reutilizar um aplicativo elegível existente, obtenha aprovação do proprietário primeiro.
1. Nas configurações do aplicativo, selecione **[!UICONTROL Informações Básicas]** > **[!UICONTROL Credenciais do Aplicativo]**. Anote a **[!UICONTROL ID do Cliente]** e o **[!UICONTROL Segredo do Cliente]**.

   Insira apenas esses dois valores em Colaborador. Não use a ID do aplicativo, o segredo de assinatura, um token de bot ou um token no nível do aplicativo.

### Registrar o URL de redirecionamento {#register-redirect-url}

Registre a URL de redirecionamento do Colaborador no aplicativo [!DNL Slack]:

1. No Colaborador, abra a caixa de diálogo **[!UICONTROL Conectar Slack]**, conforme descrito em [Configurar o conector para sua organização](#configure-organization). Copie o valor completo da **[!UICONTROL URL de redirecionamento]**.

   Você pode abrir a caixa de diálogo para copiar o URL antes de concluir ou salvar a configuração.

1. Nas configurações do aplicativo [!DNL Slack], selecione **[!UICONTROL OAuth e permissões]**. Em **[!UICONTROL URLs de redirecionamento]**, adicione a URL de redirecionamento completa e salve.

Sempre copie o URL de redirecionamento da caixa de diálogo do Colaborador no ambiente que você está configurando. Registre o esquema exato, o nome do host, a porta, se houver um, e o caminho. Não crie você mesmo o URL ou reutilize um URL de redirecionamento de outro ambiente. Se você usar mais de um ambiente, registre cada URL de redirecionamento separadamente.

### Definir os escopos do usuário {#set-user-scopes}

O conector usa escopos OAuth de usuário, que autorizam a conta de cada membro. Ele não usa escopos de bot.

1. Nas configurações do aplicativo [!DNL Slack], selecione **[!UICONTROL OAuth e permissões]** > **[!UICONTROL Escopos]** > **[!UICONTROL Escopos de Token de Usuário]**.
1. Adicione os escopos de usuário que sua organização aprova. Compare-os com os [escopos padrão](#review-scopes) no Coworker e adicione apenas os escopos que você planeja solicitar.

   Os escopos padrão são o conjunto de recursos padrão de Colaborador, não um mínimo exigido por [!DNL Slack]. Use os escopos `search:read.*` granulares, não o escopo `search:read` mais antigo. Em um manifesto de aplicativo, os escopos de usuário pertencem a `oauth_config.scopes.user`, não a `oauth_config.scopes.bot`.

O escopo de usuário `chat:write` permite que o Co-worker envie mensagens como o membro que está conectado. Caso sua organização não planeje enviar mensagens, deixe-a de fora.

Seu espaço de trabalho ou organização corporativa [!DNL Slack] pode exigir aprovação do aplicativo e revisão do escopo. A aprovação do aplicativo não substitui o consentimento de cada membro. Uma política que permite que somente aplicativos [!DNL Slack Marketplace] possam bloquear um aplicativo interno. Para obter mais informações, consulte [Gerenciar aprovação de aplicativo para seu espaço de trabalho](https://slack.com/help/articles/222386767-Manage-app-approval-for-your-workspace).

Se o aplicativo usar restrições de endereço IP permitidas, [!DNL Slack] também as aplicará às solicitações MCP. Entre em contato com seu representante da Adobe para confirmar os endereços permitidos. Não adivinhe intervalos de endereço IP. Alguns recursos, como a pesquisa semântica, podem depender do seu plano [!DNL Slack].

### Revisar configurações irreversíveis do aplicativo {#review-irreversible-settings}

O colega de trabalho se conecta como um cliente OAuth confidencial com a ID do cliente e o segredo do cliente. Algumas configurações do aplicativo [!DNL Slack] não podem ser revertidas, portanto, reveja o seguinte antes de alterá-las:

* **Chave de Prova para Troca de Código (PKCE):** Não ative a configuração PKCE [!DNL Slack] para este conector sem confirmação. [!DNL Slack] documentos indicam que esta configuração altera o aplicativo para um cliente público, e somente o suporte do [!DNL Slack] pode revertê-lo. Para obter mais informações, consulte [Usando PKCE](https://docs.slack.dev/authentication/using-pkce/).
* **Rotação de tokens:** A rotação de tokens de [!DNL Slack] não pode ser desativada após ser ativada. Entre em contato com o representante da Adobe antes de ativá-lo para este aplicativo. Para obter mais informações, consulte [Usando rotação de token](https://docs.slack.dev/authentication/using-token-rotation/).

### Recursos de bot não obrigatórios {#bot-features-not-required}

O conector não precisa de recursos de bot. Você não precisa de escopos de token de bot, uma URL de solicitação [!DNL Events API], uma URL de solicitação de interatividade, webhooks de entrada, comandos de barra, [!DNL Socket Mode] ou tokens de nível de aplicativo. Se um aplicativo existente usar esses recursos para outra finalidade, mantenha-os.

O servidor MCP [!DNL Slack] não oferece suporte a registro dinâmico de cliente ou a eventos enviados por servidor (SSE). O Colaborador usa seu aplicativo registrado e o transporte HTTP transmissível.

## Configurar o conector do para sua organização {#configure-organization}

Os administradores disponibilizam o conector [!DNL Slack] para todos na organização. As alterações na página da organização se aplicam a todos os usuários da organização. Conclua [Preparar seu aplicativo Slack](#prepare-slack-app) antes que os membros entrem.

1. Abra **[!UICONTROL Personalizações]**, selecione **[!UICONTROL Org]** e **[!UICONTROL Conectores Externos]**. No cartão **[!UICONTROL Slack]**, selecione **[!UICONTROL Configurar]**.

   A caixa de diálogo **[!UICONTROL Conectar Slack]** é aberta. O conector usa a URL fixa do servidor MCP [!DNL Slack], `https://mcp.slack.com/mcp`. Use o escopo da organização para esta configuração, não uma conexão pessoal.

1. Verifique se a **[!UICONTROL URL de redirecionamento]** em **[!UICONTROL aplicativo do Slack]** está registrada no seu aplicativo, conforme descrito em [Registrar a URL de redirecionamento](#register-redirect-url). Em seguida, insira a **[!UICONTROL ID do cliente]** e o **[!UICONTROL segredo do cliente]** do seu aplicativo. Ambos os campos são obrigatórios.

   Não insira a ID do aplicativo, o segredo de assinatura ou um token de bot. O Colaborador armazena as credenciais como segredos, não como configurações de conector de texto simples.

   ![Caixa de diálogo Conectar Slack mostrando a seção do aplicativo Slack com uma URL de Redirecionamento redigida, campos vazios de ID do Cliente e segredo do Cliente, os escopos padrão de OAuth do Usuário e as primeiras ferramentas disponíveis para os usuários.](./assets/slack/org-configure.png){width="500" zoomable="yes"}

1. Revise os **[!UICONTROL escopos OAuth do usuário]**. Para obter mais informações, consulte [Revisar os escopos OAuth do usuário](#review-scopes).

1. Em **[!UICONTROL Ferramentas disponíveis aos usuários]**, remova todas as ferramentas que os membros não devem usar. Pelo menos uma ferramenta deve permanecer. Para obter mais informações, consulte [Ferramentas disponíveis](#available-tools).

1. Revise **[!UICONTROL Acesso e permissões]** e selecione **[!UICONTROL Salvar conexão]**. O cartão **[!UICONTROL Slack]** mostra a **[!UICONTROL Configuração salva]**.

   A caixa de diálogo também mostra o método de **[!UICONTROL Autenticação]**, o tipo de **[!UICONTROL Conexão]** e o **[!UICONTROL Tempo limite da ferramenta]**. O colega de trabalho não salva a configuração quando um campo de credencial ou a lista de escopo está vazia.

   Recarregue a página, selecione **[!UICONTROL Exibir configuração]** e confirme se a configuração e a seleção da ferramenta foram salvas antes que os membros entrem.

   ![Caixa de diálogo Conectar Slack mostrando os escopos OAuth do usuário, todas as 16 ferramentas disponíveis para os usuários, o aviso de acesso e permissões e as configurações de autenticação OAuth, conexão HTTP e tempo limite de ferramenta de 60 segundos.](./assets/slack/org-scopes-tools.png){width="500" zoomable="yes"}

Ao salvar, você ou qualquer membro não entrará no [!DNL Slack]. Para verificar a conexão, entre como você mesmo, conforme descrito em [Entre como um membro](#sign-in-as-a-member).

### Revisar os escopos OAuth do usuário {#review-scopes}

O campo **[!UICONTROL Escopos OAuth de usuário]** é obrigatório. Separe os escopos com espaços ou vírgulas e corresponda aos escopos do usuário aprovados para seu aplicativo. Por padrão, o campo contém os 22 escopos a seguir:

```text
search:read.public search:read.private search:read.im search:read.mpim search:read.files search:read.users channels:history groups:history im:history mpim:history channels:read groups:read im:read mpim:read users:read users:read.email files:read canvases:read lists:read emoji:read reactions:read chat:write
```

Seu espaço de trabalho pode não aprovar todos os escopos padrão. Revise os escopos solicitados com o proprietário do aplicativo.

>[!IMPORTANT]
>
>Os escopos padrão incluem conteúdo privado, como canais privados, mensagens de grupo e mensagens diretas. Eles também incluem `chat:write`, que permite que o Colaborador envie mensagens e respostas como o membro que está conectado. Decida explicitamente se sua organização ativa as ferramentas de envio de mensagens. A remoção de uma ferramenta não remove seus escopos OAuth. Se não quiser que membros enviem mensagens, remova a ferramenta `slack_send_message` e o escopo `chat:write`.

A seleção de ferramentas e os escopos OAuth são independentes. Ao restringir o acesso, revise a lista de ferramentas e o campo de escopo. Uma ferramenta habilitada não dá a um membro mais acesso de [!DNL Slack] do que a conta dele tem.

### Ferramentas disponíveis {#available-tools}

O conector [!DNL Slack] fornece as 16 ferramentas a seguir. Por padrão, todos estão disponíveis para membros.

| Recurso | Ferramenta |
| --- | --- |
| Pesquisar | `slack_search_public` |
| Pesquisar | `slack_search_public_and_private` |
| Pesquisar | `slack_search_channels` |
| Pesquisar | `slack_search_users` |
| Ler conversas | `slack_read_channel` |
| Ler conversas | `slack_read_thread` |
| Ler conversas | `slack_list_channel_members` |
| Ler conversas | `slack_list_user_channels` |
| Ler conteúdo e perfis | `slack_read_canvas` |
| Ler conteúdo e perfis | `slack_read_user_profile` |
| Ler conteúdo e perfis | `slack_read_file` |
| Ler conteúdo e perfis | `slack_read_list` |
| Emoji e reações | `slack_search_emojis` |
| Emoji e reações | `slack_get_reactions` |
| Mensagens e rascunhos | `slack_send_message` |
| Mensagens e rascunhos | `slack_send_message_draft` |

O conector não é somente leitura. Os membros podem enviar mensagens e respostas a menos que você remova a ferramenta `slack_send_message`. Não estão incluídos criação de canais, mensagens programadas, uploads de arquivos, adição de reações e alterações na tela ou lista.

## Fazer logon como membro {#sign-in-as-a-member}

Depois que um administrador configura o conector, cada membro entra com sua própria conta [!DNL Slack]. Você não precisa do segredo do cliente para entrar.

1. Abra **[!UICONTROL Personalizações]**, selecione **[!UICONTROL Usuário]** e selecione **[!UICONTROL Conectores Externos]**.

1. Localize o cartão **[!UICONTROL Slack]**. Se o cartão exibir **[!UICONTROL Não configurado]** e **[!UICONTROL Ainda não disponível. Seu administrador precisa configurar isso.]**, peça ao seu administrador para [configurar o conector](#configure-organization).

   Não solicite nem copie o segredo do cliente da organização.

1. Depois que o administrador configurar o conector, o cartão **[!UICONTROL Slack]** mostrará **[!UICONTROL Entrada necessária]**. Selecione **[!UICONTROL Entrar]** no cartão.

   Você também pode abrir os detalhes do conector **[!UICONTROL Slack]**. Antes de entrar, a seção **[!UICONTROL Conexão]** mostra **[!UICONTROL Não entrou]**, com um botão **[!UICONTROL Entrar]**.

   ![Detalhes do conector do Slack para um membro, mostrando um status obrigatório de Entrada, o botão Testar conexão, a URL do servidor, Cada usuário entra, uma conexão Não entrou com um botão Entrar e as ferramentas habilitadas pelo administrador.](./assets/slack/member-details.png){width="700" zoomable="yes"}

1. Conclua a autorização [!DNL Slack] com a conta e o espaço de trabalho [!DNL Slack] que você planeja usar. Revise as permissões solicitadas e os requisitos de aprovação do espaço de trabalho.

   >[!IMPORTANT]
   >
   >Continue apenas se você reconhecer o aplicativo e sua organização aprovar o acesso solicitado.

1. Retorne ao Colaborador e revise o status da conexão. Selecione **[!UICONTROL Testar conexão]** e [verifique seu acesso ao Slack](#check-access) antes de confiar na conexão.

1. Analise cuidadosamente as ações de mensagens. O colaborador envia mensagens e respostas como sua conta do [!DNL Slack].

Como membro, você pode testar a conexão ou sair, mas não pode alterar as configurações da organização. Você pode acessar somente o conteúdo que [!DNL Slack] e os escopos concedidos permitem. Este conteúdo inclui conversas privadas somente quando sua própria conta do [!DNL Slack] pode acessá-las.

Para desconectar sua conta do [!DNL Slack] do conector, selecione **[!UICONTROL Sair]**.

## Verifique seu acesso ao Slack {#check-access}

Para confirmar se o conector pode ler o conteúdo do [!DNL Slack], inicie um chat e insira um prompt somente leitura. Verifique se o administrador habilitou a ferramenta `slack_list_user_channels`.

Exemplo de prompt:

* &quot;Usando o Slack, liste até cinco canais aos quais pertenço. Mostrar apenas os nomes dos canais. Não envie mensagens, não crie rascunhos, nem altere nada.&quot;

Se sua organização ativar as ferramentas de mensagens, teste o envio somente em um canal que esteja reservado para teste e com aprovação. Peça a um segundo membro para entrar separadamente e confirme se cada membro vê somente seu próprio conteúdo [!DNL Slack].

## Solução de problemas de acesso {#troubleshoot-access}

Se a configuração, o logon ou o acesso falhar, verifique o seguinte com o administrador:

| Problema | O que verificar |
| --- | --- |
| Não é possível salvar a configuração | Insira a ID do cliente e o segredo do cliente, mantenha pelo menos um escopo OAuth de usuário e pelo menos uma ferramenta. Não insira uma ID do aplicativo, um segredo de assinatura ou um token de bot. |
| A **[!UICONTROL URL de redirecionamento]** está ausente ou [!DNL Slack] relata uma incompatibilidade de redirecionamento | Compare a URL de redirecionamento completa da caixa de diálogo do Colaborador, incluindo o esquema, o host, a porta e o caminho com as **[!UICONTROL URLs de redirecionamento]** salvas no aplicativo [!DNL Slack]. Se o URL estiver ausente ou os valores forem diferentes, entre em contato com o representante da Adobe. |
| [!DNL Slack] falha ao entrar ou solicitar | Verifique a aprovação do aplicativo, os escopos de usuário concedidos, a conta e o espaço de trabalho do [!DNL Slack] com os quais você entrou, e todas as restrições de endereço IP no aplicativo. Se as solicitações continuarem falhando, saia e entre novamente. |
| Uma ação de leitura ou envio não está disponível | Verifique a seleção da ferramenta de sua organização, os escopos solicitado e concedido e as [!DNL Slack] permissões do membro. Essas configurações são independentes. |
| Um membro não pode alterar as configurações do aplicativo | Esse comportamento é esperado para uma conexão gerenciada pela organização. Pergunte ao administrador. Os membros nunca inserem o segredo do cliente da organização. |
