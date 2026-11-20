---
title: Conector externo do Infobip Observe
description: Saiba como configurar o conector externo do Infobip Observe no CX Enterprise Coworker para sua organização e faça logon com o Infobip para usar as ferramentas de Observação.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está na versão beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 382a5f6fd629b8b10468c0cfe4d41f050a7f3725
workflow-type: tm+mt
source-wordcount: '1458'
ht-degree: 1%
---

# Conector externo do Infobip Observe {#infobip-observe}

Use o conector externo [!DNL Infobip Observe] para analisar o tráfego e os custos do [!DNL Infobip] no Adobe CX Enterprise Coworker. Depois de configurar o conector, pergunte ao Colaborador sobre métricas de tráfego, uso de faturamento, logs de mensagem e códigos de status e erro. O conector é o servidor MCP [!DNL Observe] hospedado por [!DNL Infobip].

>[!AVAILABILITY]
>
>O conector externo [!DNL Infobip Observe] está na versão beta. A documentação e a funcionalidade estão sujeitas a alterações.

## Configuração do conector {#connector-configuration}

O processo de configuração do conector tem duas partes separadas:

* **Configuração da organização:** um administrador configura o conector para toda a organização e aprova as ferramentas que os membros podem usar.
* **Entrada de membro:** cada membro entra com sua própria conta [!DNL Infobip]. Os membros podem acessar somente os dados que a conta [!DNL Infobip] tem permissão para usar.

O conector não tem logon de organização compartilhada. Todos os membros que usam o conector fazem logon separadamente. Salvar a configuração da organização não faz logon em nenhum membro nem concede permissões [!DNL Infobip] adicionais.

## Pré-requisitos {#prerequisites}

O conector funciona somente com o servidor MCP [!DNL Infobip] [!DNL Observe]. Ele não se conecta aos servidores MCP de mensagens, provisionamento ou gerenciamento de conta do [!DNL Infobip].

Antes de começar, verifique se você tem o seguinte:

* **Acesso de colaborador:** uma conta com permissão para gerenciar conectores de organização, em uma organização em que o conector [!DNL Infobip Observe] está disponível.
* Conta **[!DNL Infobip]:** Uma conta [!DNL Infobip] aprovada com acesso a [!DNL Observe] no data center pretendido. [!DNL Infobip] oferece [!DNL Observe] MCP como um recurso de acesso antecipado. Confirme sua qualificação e adequação da conta com [!DNL Infobip].
* **Identidades do membro:** membros com suas próprias contas do [!DNL Infobip] e permissão para acessar os dados desejados.
* **Um escopo aprovado para teste:** Um escopo de teste aprovado e dados não confidenciais antes de você consultar cobrança, tráfego ou logs de mensagens.

Para testar o conector, você pode se inscrever para obter uma conta de avaliação gratuita do [!DNL Infobip]. Uma conta de avaliação não garante o isolamento de dados nem custo zero. Para obter mais informações, consulte [Usando servidores MCP Infobip](https://www.infobip.com/docs/mcp/using-mcp){target="_blank"} e [Observe o MCP](https://www.infobip.com/docs/mcp/observe-mcp){target="_blank"} na documentação [!DNL Infobip].

>[!IMPORTANT]
>
>Nunca compartilhe senhas, chaves de API, tokens, códigos de autorização ou URLs de consentimento e retorno de chamada em capturas de tela, bate-papos ou tíquetes de suporte.

## Modelo de conexão e logon {#connection-model}

O colega de trabalho aplica as seguintes configurações automaticamente. Você não cria um aplicativo OAuth nem insere credenciais de aplicativo.

| Configuração | Valor |
| --- | --- |
| URL do servidor | `https://mcp.infobip.com/observe` |
| Transporte | HTTP transmitido |
| Descoberta de servidor de autorização | `https://mcp.infobip.com/observe/.well-known/oauth-authorization-server` |
| Entrar | Cada membro faz logon com o OAuth, usando o registro de cliente dinâmico |
| Configuração do OAuth | Descoberto automaticamente. Os administradores não inserem uma ID do cliente, segredo do cliente, escopos ou pontos de extremidade OAuth. |
| Seleção da ferramenta | Quatro ferramentas aprovadas. Os administradores podem restringir a seleção. |

A descoberta de [!DNL Infobip] e o consentimento de cada membro determinam o acesso que o Colaborador recebe. [!DNL Infobip] documenta os escopos `billing:usage:view`, `metrics:manage`, `messages-api:manage` e `error-codes:read` para o MCP [!DNL Observe]. Revise o acesso solicitado na tela de consentimento antes de aprovar.

O [!DNL Infobip] também oferece suporte à autenticação de chave de API para MCP [!DNL Observe] em outros clientes MCP. O colega de trabalho não usa chaves de API para este conector. Os membros fazem logon somente com OAuth.

## Configurar o conector do para sua organização {#configure-organization}

Os administradores disponibilizam o conector [!DNL Infobip Observe] para todos na organização. As alterações na página da organização se aplicam a todos os usuários da organização. Os membros não podem configurar a conexão da organização.

1. Abra **[!UICONTROL Personalizações]**, selecione **[!UICONTROL Org]** e **[!UICONTROL Conectores Externos]**.

1. Localize o **[!UICONTROL Infobip Observe]** e selecione **[!UICONTROL Configurar]**.

1. Na caixa de diálogo **[!UICONTROL Observar Infobip da Conexão]**, examine a **[!UICONTROL URL do Servidor]**, `https://mcp.infobip.com/observe` corrigida.

   Não é necessário inserir uma ID de cliente OAuth, um segredo de cliente ou escopos.

1. Em **[!UICONTROL Ferramentas disponíveis para usuários]**, revise as quatro ferramentas inicialmente selecionadas. Remova qualquer ferramenta que os membros da sua organização não devam usar. Pelo menos uma ferramenta deve permanecer.

   Para obter mais informações, consulte [Ferramentas disponíveis](#available-tools).

   ![Caixa de diálogo de Observação do Connect Infobip mostrando a URL do servidor, as quatro ferramentas disponíveis aos usuários, o aviso de Acesso e permissões e as configurações de autenticação OAuth, conexão HTTP e tempo limite de ferramenta de 60 segundos.](./assets/infobip-observe/org-configure.png){width="500" zoomable="yes"}

1. Selecione **[!UICONTROL Salvar conexão]**. Em seguida, abra novamente a configuração para verificar se a seleção da ferramenta persiste.

Ao salvar, você ou qualquer membro não entrará no [!DNL Infobip]. Para verificar a conexão você mesmo, entre como descrito em [Entre como um membro](#sign-in-as-a-member).

Para tornar todas as quatro ferramentas disponíveis novamente depois de remover qualquer uma, selecione **[!UICONTROL Restaurar todas as ferramentas]**. Essa opção restaura somente as quatro ferramentas aprovadas. O colega de trabalho não habilita ferramentas que [!DNL Infobip] adiciona posteriormente. Não é possível salvar a configuração sem nenhuma ferramenta selecionada.

### Ferramentas disponíveis {#available-tools}

O conector [!DNL Infobip Observe] fornece as ferramentas a seguir. O [!DNL Infobip] pode alterar os limites de cada ferramenta, portanto, verifique a documentação do [!DNL Infobip] antes de confiá-los.

| Ferramenta | Finalidade | Limites |
| --- | --- | --- |
| `get_traffic_performance_metrics` | Métricas agregadas de tráfego, entrega e envolvimento. | Até 366 dias de dados. As janelas por hora abrangem até 14 dias e as janelas diárias, até 93 dias. Retorna os dados da conta conectada por padrão. Incluir subcontas explicitamente. |
| `get_billing_usage_costs` | Uso e custos que se alinham às faturas. | Os dois meses atuais e anteriores. Inclui a hierarquia completa da conta por padrão. Os dados de um mês são provisionais até o quinto dia do mês seguinte. |
| `get_message_logs` | Logs de mensagens individuais. | As últimas 48 horas. Os logs podem incluir identificadores de recipients, informações pessoais e conteúdo de mensagens. |
| `look_up_status_and_error_codes` | Descrições de status conhecidos e nomes de código de erro. | Até 50 nomes por solicitação. [!DNL Infobip] pode omitir nomes desconhecidos dos resultados. |

Os resultados estão limitados a um data center de [!DNL Infobip]. A seleção da ferramenta controla quais ferramentas os membros podem usar no Co-worker. Ele não restringe o acesso de [!DNL Infobip] que os membros concedem ao entrar, à hierarquia de conta ou às permissões que [!DNL Infobip] impõe.

>[!IMPORTANT]
>
>Os logs de mensagens podem conter dados pessoais, como identificadores de recipients e conteúdo de mensagens. As informações de faturamento são confidenciais e abrangem a hierarquia completa da conta por padrão. Ative essas ferramentas somente quando sua organização aprovar o uso delas. Use filtros de conta explícitos e aprovados e consultas limitadas.

## Fazer logon como membro {#sign-in-as-a-member}

Depois que um administrador configura o conector, cada membro entra com sua própria conta [!DNL Infobip]. Sua entrada pertence somente a você. Outros membros não usam suas credenciais.

1. Abra **[!UICONTROL Personalizações]**, selecione **[!UICONTROL Usuário]** e selecione **[!UICONTROL Conectores Externos]**. Localizar **[!UICONTROL Observação Infobip]**.

   Se o cartão exibir **[!UICONTROL Não configurado]** e **[!UICONTROL Ainda não disponível. Seu administrador precisa configurar isso.]**, peça ao seu administrador para [configurar o conector](#configure-organization).

1. Selecione **[!UICONTROL Entrar]** e use a conta [!DNL Infobip] desejada. Complete o logon único (SSO), a autenticação multifator (MFA) e os prompts de consentimento. Antes de aprovar, revise o acesso solicitado, a conta e o data center.

1. Retorne ao Colaborador e abra os detalhes do conector. Revise as ferramentas que seu administrador ativou.

   Os membros podem exibir as ferramentas, mas não podem alterar a configuração da organização.

1. Selecione **[!UICONTROL Testar conexão]**.

   Um teste bem-sucedido confirma que o Colaborador pode se conectar e listar as ferramentas. Isso não confirma se cada ferramenta é executada com êxito.

1. Se você estiver autorizado e o administrador tiver habilitado a ferramenta `look_up_status_and_error_codes`, execute a pesquisa em [Verifique a conexão](#check-connection).

1. Para desconectar sua conta do [!DNL Infobip] do conector, selecione **[!UICONTROL Sair]**.

   Sair não revoga necessariamente o acesso que você concedeu em [!DNL Infobip].

## Verifique sua conexão {#check-connection}

Para confirmar se o conector funciona com sua conta, execute uma pesquisa somente leitura. Verifique se o administrador habilitou a ferramenta `look_up_status_and_error_codes`. Em seguida, inicie o chat e insira um aviso.

Exemplo de prompt:

* &quot;Usando o Infobip Observe, procure o código de status NO_ERROR e descreva o que ele significa. Não consulte métricas de tráfego, cobrança ou registros de mensagem.&quot;

Confirme se o resultado inclui uma descrição de `NO_ERROR` sem uma mensagem de erro. Uma pesquisa bem-sucedida não confirma se as ferramentas de registro de tráfego, faturamento ou mensagem funcionam para a sua conta. Não consulte registros de mensagens ou cobrança somente para testar a conexão.

## Solução de problemas de acesso {#troubleshoot-access}

Se não conseguir acessar os dados do [!DNL Infobip], verifique o seguinte com o administrador:

| Problema | O que verificar |
| --- | --- |
| O conector **[!UICONTROL Infobip Observe]** está ausente | Confirme se o conector está disponível para a sua organização e se você tem permissão para gerenciar conectores da organização. Entre em contato com seu representante da Adobe, se necessário. |
| Falha no consentimento ou no logon | Verifique a conta do [!DNL Infobip] usada, seus direitos do [!DNL Observe] e o data center. Não compartilhe o URL de consentimento, URL de retorno de chamada ou códigos de autorização quando solicitar ajuda. |
| Entrada bem-sucedida, mas uma ferramenta falha | Verifique as permissões [!DNL Infobip] efetivas, a conta e o data center com os quais você entrou e o erro que [!DNL Infobip] retorna. Um logon bem-sucedido não confirma se uma ferramenta é executada com êxito. |
| Ferramenta indisponível | Verifique as ferramentas que o administrador ativou. O colega de trabalho não habilita as novas ferramentas [!DNL Infobip] automaticamente. |
| Não é possível salvar a configuração | Mantenha pelo menos uma ferramenta selecionada. Para interromper a oferta do conector, remova-o. |
| Os resultados da cobrança incluem contas inesperadas | Os resultados da cobrança incluem a hierarquia de conta completa por padrão. Pare o e revise os filtros e as permissões de conta aprovados. |
| Os logs de mensagem mostram dados confidenciais | Interrompa a consulta e limite consultas posteriores a dados aprovados e não confidenciais. Não cole registros brutos em bate-papos ou tíquetes de suporte. |
| A pesquisa do código de status foi bem-sucedida, mas outra solicitação falhou | Investigue a solicitação com falha separadamente. Uma pesquisa bem-sucedida não confirma se cada ferramenta ou conta funciona. |
