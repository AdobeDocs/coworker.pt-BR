---
title: Conector externo do Snowflake Cortex AI
description: Saiba como configurar o conector externo do Snowflake Cortex AI no CX Enterprise Coworker com uma conta de serviço ou logon por pessoa para consultar dados do Snowflake.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está na versão beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 942f76a48eabbc9ac795d9e53aad1faceff31393
workflow-type: tm+mt
source-wordcount: '2057'
ht-degree: 0%
---

# Conector externo do Snowflake Cortex AI {#snowflake}

Use o conector externo do [!DNL Snowflake Cortex AI] para fazer perguntas sobre seus dados do [!DNL Snowflake] em linguagem simples no Adobe CX Enterprise Coworker. O conector vincula o Coworker a um servidor MCP gerenciado por [!DNL Snowflake] em sua conta [!DNL Snowflake]. O Co-worker pode então usar as ferramentas que o servidor expõe, como as ferramentas do [!DNL Cortex Analyst], [!DNL Cortex Search] e SQL.

>[!AVAILABILITY]
>
>O conector externo [!DNL Snowflake Cortex AI] está na versão beta. A documentação e a funcionalidade estão sujeitas a alterações.

## Configuração do conector {#connector-configuration}

O processo de configuração do conector tem duas partes separadas:

* **Configuração da organização:** um administrador conecta o Coworker a um servidor MCP [!DNL Snowflake] existente, escolhe como as pessoas entram e seleciona as ferramentas que os membros podem usar.
* **Acesso de membro:** os membros usam a conexão com uma identidade de organização compartilhada ou sua própria identidade [!DNL Snowflake], dependendo da opção de entrada.

O administrador escolhe uma das seguintes opções de logon:

| Opção | O que o administrador oferece | Como o acesso funciona |
| --- | --- | --- |
| **[!UICONTROL Conta de serviço da organização]** | Um PAT (token de acesso programático) [!DNL Snowflake] para uma conta de serviço. | Todos os membros usam as permissões da conta de serviço. A expiração ou revogação do token afeta todos os membros. |
| **[!UICONTROL Cada pessoa entra]** | A ID do cliente e o segredo do cliente de uma integração OAuth [!DNL Snowflake] e uma função [!DNL Snowflake] opcional. | Cada membro entra com sua própria identidade [!DNL Snowflake], e o acesso segue suas permissões [!DNL Snowflake]. |

Nenhuma opção concede privilégios [!DNL Snowflake] que a identidade selecionada ainda não tem. [!DNL Snowflake] aplica permissões em cada solicitação.

## Pré-requisitos {#prerequisites}

O colega de trabalho se conecta a um servidor MCP [!DNL Snowflake] existente. Ele não cria o servidor ou suas ferramentas. Antes de começar, verifique se você tem o seguinte:

* **Para configuração de organização:** uma conta com permissão para gerenciar conectores de organização no Colaborador.
* **Para o servidor MCP [!DNL Snowflake]:** A URL HTTPS completa do servidor, incluindo seu banco de dados, esquema e nome de servidor.
* **Para a opção de conta de serviço:** um PAT para uma conta de serviço dedicada. A função da conta de serviço deve ter somente os privilégios necessários para o servidor MCP e suas ferramentas.
* **Para a opção de entrada por pessoa:** Uma integração OAuth [!DNL Snowflake] com sua ID de cliente e o segredo do cliente. Você também precisa de um administrador [!DNL Snowflake] que possa registrar a URL de redirecionamento do Colaborador e configurar a integração.

>[!IMPORTANT]
>
>Nunca compartilhe PATs, segredos de clientes OAuth ou outras credenciais em capturas de tela, chats ou tíquetes de suporte. Use segredos da organização e uma identidade [!DNL Snowflake] com menos privilégios.

### Configurar o servidor MCP do Snowflake {#configure-snowflake-mcp-server}

Um administrador do [!DNL Snowflake] deve concluir as seguintes tarefas em [!DNL Snowflake] antes de configurar o conector:

1. Crie o servidor MCP e defina as ferramentas que ele expõe.
1. Conceda acesso às atribuições necessárias ao servidor MCP, suas ferramentas e aos objetos subjacentes.

   O acesso ao servidor MCP não concede acesso automático a todas as ferramentas ou objetos.

1. Configure a autenticação para a opção de entrada que você planeja usar:

   * Para a opção conta de serviço, crie um PAT para a conta de serviço.
   * Para a opção de logon por pessoa, crie uma integração OAuth que emita tokens de atualização.

Para obter instruções, consulte a seguinte documentação do [!DNL Snowflake]:

* [Servidor MCP gerenciado pela Snowflake](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-agents-mcp){target="_blank"}
* [Criar servidor MCP](https://docs.snowflake.com/en/sql-reference/sql/create-mcp-server){target="_blank"}
* [Visão geral do controle de acesso](https://docs.snowflake.com/en/user-guide/security-access-control-overview){target="_blank"}
* [Configurar o Snowflake OAuth para clientes personalizados](https://docs.snowflake.com/en/user-guide/oauth-custom){target="_blank"}
* [Criar integração de segurança (Snowflake OAuth)](https://docs.snowflake.com/en/sql-reference/sql/create-security-integration-oauth-snowflake){target="_blank"}
* [Utilização de tokens de acesso programático para autenticação](https://docs.snowflake.com/en/user-guide/programmatic-access-tokens){target="_blank"}

## Configurar o conector do para sua organização {#configure-organization}

Os administradores disponibilizam o conector [!DNL Snowflake Cortex AI] para todos na organização. As alterações na página da organização se aplicam a todos os usuários da organização.

1. Abra **[!UICONTROL Personalizações]**, selecione **[!UICONTROL Org]** e **[!UICONTROL Conectores Externos]**. No cartão **[!UICONTROL Snowflake Cortex AI]**, selecione **[!UICONTROL Configurar]**.

1. Na caixa de diálogo **[!UICONTROL Conectar Snowflake Cortex AI]**, insira a URL completa do servidor MCP [!DNL Snowflake] na **[!UICONTROL URL do Servidor]**. O URL deve usar HTTPS e seguir este padrão:

   ```text
   https://<account-host>/api/v2/databases/<database>/schemas/<schema>/mcp-servers/<server-name>
   ```

   Use a URL exata para sua conta do [!DNL Snowflake] e o servidor MCP. O nome de host da conta não deve conter um sublinhado, incluindo um sublinhado codificado (`%5F`). Não inclua credenciais no URL. O colaborador verifica o esquema, o host e o caminho HTTPS antes de salvar.

1. Em **[!UICONTROL Quem entra?]**, selecione uma opção de entrada e conclua as configurações.

   * **[!UICONTROL Conta de serviço da organização]:** As solicitações usam as permissões da conta de serviço por meio de um PAT (token de acesso programático). Use esta opção para acesso gerenciado centralmente. Use uma conta de serviço dedicada com uma função de escopo restrito, não uma conta pessoal.

     ![Caixa de diálogo Conectar Snowflake com a conta de serviço Organização selecionada, mostrando o campo URL do Servidor, as opções de token da conta de Serviço, o campo token de acesso programático e um aviso de que todos agem com as permissões do proprietário do token.](./assets/snowflake/org-service-account.png){width="500" zoomable="yes"}

     | Configuração | Descrição |
     | --- | --- |
     | **[!UICONTROL Token da conta de serviço]** | Escolha a origem do token. Selecione **[!UICONTROL Inserir novo]** para inserir um PAT ou **[!UICONTROL Usar um segredo existente]** para reutilizar um segredo de organização que já contenha o token. Um segredo existente deve conter o valor completo para o cabeçalho `Authorization`, não apenas o token bruto. |
     | **[!UICONTROL Token de acesso programático]** | Necessário ao selecionar **[!UICONTROL Inserir novo]**. Crie o token para uma conta de serviço [!DNL Snowflake] dedicada com apenas as permissões necessárias. Para obter instruções, selecione **[!UICONTROL Como criar um token de acesso programático]** na caixa de diálogo. O Colaborador armazena o token como um segredo da organização. |

     >[!IMPORTANT]
     >
     >Todos os usuários que usam essa conexão atuam com as permissões do proprietário do token. Se o token expirar ou for revogado, a conexão parará de funcionar para todos os membros.

     A criação e o uso de um PAT podem estar sujeitos a [!DNL Snowflake] diretivas de rede e autenticação. Se a criação ou autenticação de token estiver bloqueada, peça ao administrador do [!DNL Snowflake] para verificar essas políticas.

   * **[!UICONTROL Cada pessoa entra]:** As solicitações usam [!DNL Snowflake] permissões de cada pessoa. Use essa opção para acesso controlado e orientado pelo usuário.

     ![A caixa de diálogo Conectar Snowflake com cada pessoa faz logon selecionado, mostrando a URL de Redirecionamento, as opções de credenciais de integração do OAuth, a ID do cliente de integração do OAuth, os campos de segredo do cliente e o campo de função opcional do Snowflake.](./assets/snowflake/org-oauth.png){width="500" zoomable="yes"}

     | Configuração | Descrição |
     | --- | --- |
     | **[!UICONTROL URL de redirecionamento]** | Somente leitura. Copie esta URL e registre-a como o URI de redirecionamento na sua integração de segurança OAuth [!DNL Snowflake]. O valor deve corresponder exatamente. Para obter instruções, selecione **[!UICONTROL Como criar uma integração OAuth do Snowflake]** na caixa de diálogo. O URL de redirecionamento difere entre os ambientes, portanto, sempre o copie da caixa de diálogo. |
     | **[!UICONTROL Credenciais de integração do OAuth]** | Escolha de onde vêm as credenciais. Selecione **[!UICONTROL Inserir novo]** para inserir a ID do cliente e o segredo do cliente ou **[!UICONTROL Use um segredo existente]** para selecionar os segredos da organização que os contêm. |
     | **[!UICONTROL ID do cliente de integração OAuth]** | Necessário ao selecionar **[!UICONTROL Inserir novo]**. A ID do cliente da sua integração do OAuth com o [!DNL Snowflake] gerenciada pelo cliente. |
     | **[!UICONTROL Segredo do cliente da integração OAuth]** | Necessário ao selecionar **[!UICONTROL Inserir novo]**. O segredo do cliente da mesma integração OAuth. Os membros nunca inserem essas credenciais. |
     | **[!UICONTROL Função da Snowflake]** | Opcional. A função que cada sessão usa, solicitada por meio do escopo OAuth `session:role:ROLE_NAME`. A função deve ser concedida a seus membros e ter acesso ao servidor MCP. Deixe o campo em branco para usar a função padrão de cada membro. |

     O colaborador deriva os endpoints OAuth do URL da conta e solicita um token de atualização. Configure a integração OAuth para emitir tokens de atualização. O escopo solicitado sozinho não substitui a configuração de integração.

     O colaborador converte o nome da função em maiúsculas. Funções criadas com um nome em minúsculas entre aspas não podem ser usadas. Se a integração OAuth bloquear a função, ou um membro não tiver a função, o logon ou o acesso poderá falhar.

1. Em **[!UICONTROL Ferramentas disponíveis para usuários]**, escolha as ferramentas que os membros podem usar. Cada servidor MCP [!DNL Snowflake] define suas próprias ferramentas, de modo que a caixa de diálogo não mostra uma lista fixa. Insira nomes de ferramentas conforme definidos no servidor MCP, não tipos de ferramentas como `CORTEX_ANALYST_MESSAGE`. Para exibir os nomes da ferramenta, execute `DESCRIBE MCP SERVER` em [!DNL Snowflake].

   ![Caixa de diálogo Conectar Snowflake mostrando o campo de função do Snowflake, a seção Ferramentas disponíveis aos usuários com os campos Nomes de ferramenta permitidos e Nomes de ferramenta bloqueados, o aviso de Acesso e permissões e um resumo com autenticação OAuth (integração de clientes), conexão HTTP e um tempo limite de ferramenta de 300 segundos.](./assets/snowflake/org-tools.png){width="500" zoomable="yes"}

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Nomes de ferramenta permitidos]** | As ferramentas que os membros podem usar. Separe os nomes com vírgulas ou espaços. Deixe o campo vazio para permitir todas as ferramentas que o servidor expõe, exceto as ferramentas bloqueadas. |
   | **[!UICONTROL Nomes de ferramentas bloqueados]** | As ferramentas que os membros nunca podem usar. Separe os nomes com vírgulas ou espaços. As ferramentas bloqueadas permanecem indisponíveis mesmo que você também as permita. |

   >[!IMPORTANT]
   >
   >Se você deixar **[!UICONTROL Nomes de ferramenta permitidos]** vazios, os membros poderão usar todas as ferramentas, inclusive qualquer ferramenta de execução SQL. As ferramentas de execução SQL executam o SQL como a identidade conectada. Revise as definições de ferramenta no servidor e permita somente as ferramentas de que sua organização precisa.

   As descrições da ferramenta não substituem os privilégios [!DNL Snowflake] ou outros controles de acesso. Para ferramentas [!DNL Cortex Analyst], configure uma exibição semântica e as concessões necessárias, incluindo a função de banco de dados `SNOWFLAKE.CORTEX_USER`. Para ferramentas do [!DNL Cortex Agent], configure ferramentas somente leitura e desative a execução do código no [!DNL Snowflake]. Os membros não podem alterar a seleção da ferramenta.

1. Revise **[!UICONTROL Acesso e permissões]** e selecione **[!UICONTROL Salvar conexão]**. O cartão **[!UICONTROL Snowflake Cortex AI]** mostra a **[!UICONTROL Configuração salva]**.

   Selecione **[!UICONTROL Exibir configuração]** para examinar a URL do servidor, o tipo de autenticação e a política da ferramenta. Em seguida, selecione **[!UICONTROL Testar conexão]** para verificar o acesso e descobrir as ferramentas do servidor.

   As novas conexões [!DNL Snowflake] usam um tempo limite de ferramenta de 300 segundos. Uma conexão mais antiga sem um tempo limite salvo pode usar o padrão de 60 segundos. Verifique o tempo limite mostrado para uma conexão existente.

Um teste bem-sucedido não confirma que todas as ferramentas ou objetos [!DNL Snowflake] estão disponíveis para cada membro.

## Usar o conector como um membro {#use-as-member}

Depois que um administrador configurar o conector, abra-o a partir da sua própria visualização de **[!UICONTROL Personalizações]**.

1. Abra **[!UICONTROL Personalizações]**, selecione **[!UICONTROL Usuário]** e selecione **[!UICONTROL Conectores Externos]**.

   Se o cartão **[!UICONTROL Snowflake Cortex AI]** exibir **[!UICONTROL Não configurado]**, peça ao administrador [configurar o conector](#configure-organization).

1. Abra o **[!UICONTROL Snowflake Cortex AI]**. Os detalhes do conector são somente leitura para membros. Não é possível alterar a URL do servidor, as credenciais ou a seleção da ferramenta.

1. Se a conexão usar uma conta de serviço da organização, as solicitações usarão a identidade da organização. Você não precisa entrar. Nunca insira ou compartilhe o PAT.

1. Se a conexão usar entrada por pessoa, inicie a entrada e se autentique com a conta pretendida do [!DNL Snowflake]. Conclua todas as etapas necessárias de logon único (SSO) ou autenticação multifator (MFA). Confirme a organização, o aplicativo e a função solicitados, se houver.

1. Se necessário, selecione **[!UICONTROL Testar conexão]**. Um teste bem-sucedido mostra **[!UICONTROL Conexão bem-sucedida]** e o número de ferramentas disponíveis.

   ![Detalhes do conector do Snowflake mostrando um status Conectado, uma mensagem de Conexão bem-sucedida com cinco ferramentas disponíveis, um aviso de que o administrador configurou o conector e a URL do servidor, a opção de entrada, a autenticação, a conexão e o tempo limite da ferramenta.](./assets/snowflake/member-details.png){width="700" zoomable="yes"}

   Antes de um teste bem-sucedido, os detalhes podem mostrar apenas os nomes das ferramentas permitidas pelo administrador ou solicitar que você execute o teste. Após o teste, cada ferramenta é exibida com sua descrição.

   ![Detalhes do conector do Snowflake mostrando o tipo de conexão, tempo limite da ferramenta, status Conectado, botões Sair e Atualizar e cinco ferramentas de exemplo habilitadas pelo administrador.](./assets/snowflake/member-tools.png){width="700" zoomable="yes"}

As ferramentas no exemplo são definidas por um servidor MCP [!DNL Snowflake]. As ferramentas que você vê dependem do servidor e da seleção de ferramentas do administrador.

Os detalhes de autenticação da conexão mostram se ela usa um PAT, OAuth de máquina ou OAuth por pessoa. Para desconectar sua conta do [!DNL Snowflake], selecione **[!UICONTROL Sair]**.

O status **[!UICONTROL Conectado]** não garante acesso a uma ferramenta ou objeto de dados específico. [!DNL Snowflake] concessões, políticas e a função selecionada ainda se aplicam.

## Solução de problemas de acesso {#troubleshoot-access}

Se a configuração, o logon ou o acesso falhar, verifique o seguinte com o administrador:

| Problema | O que verificar |
| --- | --- |
| O URL do servidor foi rejeitado | A URL usa HTTPS e o caminho `/api/v2/databases/<database>/schemas/<schema>/mcp-servers/<server-name>` completo. O nome de host da conta não tem sublinhados e o URL não tem credenciais. |
| O PAT não pode ser criado nem usado | A política de rede, a política de autenticação, a expiração do token e a função da conta de serviço. Se você usar um segredo existente, confirme se ele contém o valor completo do cabeçalho `Authorization`. |
| O URL de redirecionamento do OAuth não corresponde | A integração OAuth [!DNL Snowflake] tem a URL de redirecionamento exata do mesmo ambiente de Colaborador. |
| Entrada bem-sucedida, mas as solicitações falham | A função é concedida ao membro e permitida pela integração OAuth. Os problemas de integração atualizam os tokens, e a ID do cliente e o segredo pertencem à integração desejada. |
| Uma ferramenta está ausente ou foi negada | As configurações **[!UICONTROL Nomes de ferramenta permitidos]** e **[!UICONTROL Nomes de ferramenta bloqueados]**, a disponibilidade de ferramenta no servidor MCP e as concessões [!DNL Snowflake] no servidor, na ferramenta e nos objetos subjacentes. |
| Uma chamada de ferramenta atinge o tempo limite | O **[!UICONTROL tempo limite da ferramenta]** nos detalhes do conector. As novas conexões usam 300 segundos. Conexões mais antigas sem um tempo limite salvo podem usar 60 segundos. |
