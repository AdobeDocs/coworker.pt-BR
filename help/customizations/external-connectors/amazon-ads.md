---
title: Conector externo do Amazon Ads
description: Saiba como configurar o conector externo do Amazon Ads no CX Enterprise Coworker para sua organização e fazer logon com o Amazon para usar as ferramentas do Amazon Ads no chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está na versão beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 80dda0b442d6c7fe560c965b985f58173b73fe13
workflow-type: tm+mt
source-wordcount: '3078'
ht-degree: 1%
---

# Conector externo do Amazon Ads {#amazon-ads}

Use o conector externo do [!DNL Amazon Ads] para trabalhar com os dados do [!DNL Amazon Ads] no Adobe CX Enterprise Coworker. Depois de configurar o conector, pergunte ao Colaborador quais contas de publicidade você pode acessar e analise campanhas, relatórios, faturamentos e outras informações da conta. O conector é um servidor MCP hospedado por [!DNL Amazon].

>[!AVAILABILITY]
>
>O conector externo [!DNL Amazon Ads] está na versão beta. A documentação e a funcionalidade estão sujeitas a alterações.

## Configuração do conector {#connector-configuration}

O processo de configuração do conector tem três partes separadas:

* **[!DNL Amazon]preparação:** Um administrador de conta [!DNL Amazon Ads] dá a cada membro acesso às contas publicitárias de que ele precisa. Se sua organização usar seu próprio aplicativo OAuth, o proprietário do aplicativo confirmará sua aprovação e registrará o URL de redirecionamento do colaborador.
* **Configuração da organização:** um administrador de parceiro configura o conector uma vez para toda a organização. O administrador escolhe uma região, um aplicativo OAuth e as ferramentas que os membros podem usar.
* **Entrada de membro:** cada membro entra com sua própria conta [!DNL Amazon]. Os membros podem acessar somente as contas publicitárias que a conta [!DNL Amazon] tem permissão para usar.

Salvar a configuração da organização não faz logon em nenhum membro nem concede permissões de [!DNL Amazon Ads]. Cada membro já deve ter o acesso necessário em [!DNL Amazon Ads] e deve entrar separadamente.

## Pré-requisitos {#prerequisites}

Antes de começar, verifique se você tem o seguinte:

* **Acesso de colaborador:** uma conta com permissão para gerenciar conectores de organização, em uma organização em que o conector [!DNL Amazon Ads] está disponível.
* **Contas do Advertising:** as contas publicitárias que você planeja usar e sua região [!DNL Amazon Ads], além de membros com as permissões necessárias para essas contas. Para obter mais informações, consulte [Conceder acesso à conta publicitária](#grant-member-access).
* **Uma decisão de aplicativo OAuth:** Escolha entre as seguintes opções:
  * **Aplicativo OAuth gerenciado pela Adobe:** o Adobe gerencia o registro do aplicativo e suas credenciais. O aplicativo gerenciado deve estar disponível em seu ambiente.
  * **Seu próprio aplicativo OAuth:** Um aplicativo [!DNL Login with Amazon] aprovado para a API [!DNL Amazon Ads], sua ID de cliente OAuth e o segredo do cliente, e um administrador que pode editar seu perfil de segurança. Um perfil de segurança registrado por conta própria não concede a aprovação da API [!DNL Amazon Ads].

A configuração guiada oferece suporte a uma conexão [!DNL Amazon Ads] e a uma região por organização. Cada membro entra com sua própria conta [!DNL Amazon]. O aplicativo gerenciado pela Adobe é um registro de aplicativo compartilhado, não uma conta [!DNL Amazon] compartilhada.

## Preparar o acesso ao Amazon {#prepare-amazon}

Antes de configurar o conector no Coworker, prepare o acesso ao aplicativo e à conta no [!DNL Amazon]. O acesso à configuração do aplicativo e o acesso aos dados de publicidade são separados. Os membros que usam o conector não precisam de permissão para editar o aplicativo.

### Confirmar aprovação do aplicativo {#confirm-app-approval}

Se você usa seu próprio aplicativo OAuth, peça ao proprietário do aplicativo para confirmar o perfil de segurança [!DNL Login with Amazon] correto e sua aprovação da API [!DNL Amazon Ads]. Criar um perfil de segurança ou exibir o aplicativo no console do desenvolvedor [!DNL Amazon] não substitui a aprovação da API [!DNL Amazon Ads]. Para obter mais informações, consulte [Introdução ao MCP do Amazon Ads](https://advertising.amazon.com/API/docs/en-us/mcp/get-started) e [Conexão com o servidor MCP do Ads usando OAuth](https://advertising.amazon.com/API/docs/en-us/mcp/oauth) na documentação do [!DNL Amazon Ads].

Para seu próprio aplicativo, o Coworker aplica as seguintes configurações automaticamente. Esses valores não são inseridos na caixa de diálogo de configuração.

| Configuração | Valor |
| --- | --- |
| URL de autorização | `https://lwa.amazon.com/ap/oa` |
| URL do token | `https://api.amazon.com/auth/o2/token` |
| Escopo solicitado | `advertising::campaign_management` |
| Chave de prova para troca de código (PKCE) | Habilitado |
| Autenticação de cliente de ponto de extremidade de token | `client_secret_post`, como um cliente confidencial |
| Registro dinâmico de cliente | Incompatível |
| Tempo limite de transporte e ferramenta | HTTP transmitido, 60 segundos |

Se você usar o aplicativo OAuth gerenciado pela Adobe, o Adobe gerenciará o registro do aplicativo e suas credenciais. Você não precisa concluir esta etapa ou inserir as credenciais do aplicativo.

### Registrar o URL de redirecionamento {#register-redirect-url}

Se você usa seu próprio aplicativo OAuth, registre a URL de redirecionamento do Colaborador no aplicativo [!DNL Login with Amazon]:

1. No Colaborador, abra a caixa de diálogo **[!UICONTROL Configurar Amazon Ads para sua organização]**, conforme descrito em [Configurar o conector para sua organização](#configure-organization). Selecione **[!UICONTROL Usar meu próprio aplicativo OAuth]** para mostrar a **[!UICONTROL URL de redirecionamento]** e copie o valor completo.
1. No [Logon com o console Amazon](https://developer.amazon.com/loginwithamazon/console/site/lwa/overview.html), encontre o perfil de segurança do seu aplicativo. Selecione **[!UICONTROL Gerenciar]** > **[!UICONTROL Configurações da Web]** e **[!UICONTROL Editar]**.
1. Adicione a URL de redirecionamento completa em **[!UICONTROL URLs de Retorno Permitidos]** e salve. Se outras equipes compartilharem o aplicativo, mantenha os URLs existentes e obtenha aprovação do proprietário do aplicativo antes de alterar as configurações.
1. Observe a ID do cliente OAuth e o segredo do cliente do mesmo perfil de segurança. Insira-os quando [configurar o conector](#configure-organization).

Sempre copie o URL de redirecionamento da caixa de diálogo do Colaborador no ambiente que você está configurando. Não crie o URL por conta própria, use o URL da página de Colaborador no navegador ou reutilize um URL de redirecionamento de outro ambiente ou cliente MCP. Para obter mais informações, consulte [Registrar para Logon com o Amazon](https://developer.amazon.com/docs/login-with-amazon/register-web.html) na documentação [!DNL Amazon].

>[!NOTE]
>
>Se a **[!UICONTROL URL de redirecionamento]** mostrar apenas o caminho `/connectors/oauth/callback`, seu ambiente ainda não oferece suporte para a entrada neste conector. Não registre um caminho parcial ou adivinhe o nome do host. Entre em contato com seu representante Adobe.

### Conceder acesso à conta publicitária {#grant-member-access}

Um administrador da conta [!DNL Amazon Ads] convida cada membro para as contas publicitárias de que ele precisa:

1. Abra o [console do Amazon Ads](https://advertising.amazon.com/) e selecione **[!UICONTROL Alterar conta]** para escolher a conta de anunciante ou de gerente.
1. Selecione **[!UICONTROL Administração]** > **[!UICONTROL Acesso e configurações da conta]** > **[!UICONTROL Usuários]** > **[!UICONTROL Convidar usuários]**. As opções exatas dependem do tipo de conta. Convide a conta [!DNL Amazon] do membro, com as permissões mínimas para as tarefas que ele planeja realizar.
1. Para uma conta de gerente, verifique se o acesso abrange toda a conta de gerente ou apenas anunciantes vinculados selecionados. Peça ao membro para aceitar o convite com a mesma conta [!DNL Amazon] que ele usa para o Colaborador.
1. Confirme se o membro pode selecionar o anunciante em [!DNL Amazon Ads]. Observe o nome da conta, a região e a ID do anunciante esperados em um registro interno aprovado, para que você possa confirmar o acesso posteriormente no Co-worker.

Escolha a função com menos privilégios que ofereça suporte às tarefas que você planeja. Não conceda acesso de administrador apenas para que uma verificação de acesso seja bem-sucedida. O acesso a uma instância [!DNL Amazon Marketing Cloud] é separado do acesso às campanhas do anunciante. Para obter mais informações, consulte a seguinte documentação do [!DNL Amazon Ads]:

* [Gerenciar usuários em uma Conta de gerente](https://advertising.amazon.com/help/G4M4JGKGV2VAY9JC)
* [Adicionar ou remover usuários da sua conta](https://advertising.amazon.com/help/GDQVHVQMY9F88PCA)
* [Compreender as permissões da conta](https://advertising.amazon.com/help/GM4EFDQQPG9LGL3F)
* [Permissões de API do Amazon Ads](https://advertising.amazon.com/API/docs/en-us/guides/account-management/permissions)

## Configurar o conector do para sua organização {#configure-organization}

Os administradores disponibilizam o conector [!DNL Amazon Ads] para todos na organização. As alterações na página da organização se aplicam a todos os usuários da organização. Os membros não podem configurar a conexão da organização no escopo **[!UICONTROL Usuário]**.

1. Abra **[!UICONTROL Personalizações]**, selecione **[!UICONTROL Org]** e **[!UICONTROL Conectores Externos]**. No cartão **[!UICONTROL Amazon Ads]**, selecione **[!UICONTROL Configurar]**.

   A caixa de diálogo **[!UICONTROL Configurar Amazon Ads para sua organização]** é aberta, com as **[!UICONTROL seções Detalhes da conexão]**, **[!UICONTROL Ferramentas disponíveis para usuários]** e **[!UICONTROL Acesso e permissões]**. Após salvar a configuração, o cartão mostra **[!UICONTROL Configuração salva]** e **[!UICONTROL Configurar]** alterações na **[!UICONTROL Exibir configuração]**.

1. Em **[!UICONTROL Região do Amazon Ads]**, selecione a região que corresponde às suas contas publicitárias. O Colaborador mostra o URL do servidor MCP da região abaixo da seleção.

   | Região | URL do servidor MCP |
   | --- | --- |
   | [!UICONTROL América do Norte] (padrão) | `https://advertising-ai.amazon.com/mcp` |
   | [!UICONTROL Europa] | `https://advertising-ai-eu.amazon.com/mcp` |
   | [!UICONTROL Extremo Oriente] | `https://advertising-ai-fe.amazon.com/mcp` |

   A configuração guiada salva uma região. Para alternar regiões posteriormente, remova a conexão e configure-a novamente. Cada membro precisa fazer logon novamente, portanto, planeje a alteração antes de interromper uma conexão em funcionamento.

1. Selecione um **[!UICONTROL aplicativo OAuth]**:

   * **[!UICONTROL Aplicativo OAuth gerenciado pela Adobe]:** O Adobe fornece o aplicativo [!DNL Amazon Ads], portanto, não é necessário inserir credenciais de aplicativo. Cada membro entra com sua própria conta [!DNL Amazon] e autoriza o aplicativo Adobe.

     ![Configure o Amazon Ads para a caixa de diálogo da sua organização com a região da América do Norte, o aplicativo OAuth gerenciado pela Adobe selecionado e os grupos de ferramentas recolhidos.](./assets/amazon-ads/org-configure.png){width="500" zoomable="yes"}

   * **[!UICONTROL Usar meu próprio aplicativo OAuth]:** cada membro autoriza seu aplicativo de organização com sua própria conta [!DNL Amazon]. Em **[!UICONTROL Seu aplicativo do Amazon]**, conclua as seguintes etapas:

     1. Verifique se a **[!UICONTROL URL de redirecionamento]** está registrada no seu aplicativo. Para obter mais informações, consulte [Registrar a URL de redirecionamento](#register-redirect-url).
     1. Insira a **[!UICONTROL ID do aplicativo Amazon]** e o **[!UICONTROL segredo do aplicativo Amazon]**. O campo **[!UICONTROL ID do aplicativo Amazon]** usa a ID de cliente OAuth, não uma ID de anunciante, ID de conta de gerente ou ID do aplicativo [!DNL Amazon]. Colaborador armazena os valores informados como segredos da organização.
     1. Para reutilizar as credenciais salvas, selecione **[!UICONTROL Usar um segredo existente]**. Em seguida, selecione o **[!UICONTROL Segredo que contém a ID do aplicativo]** e o **[!UICONTROL Segredo que contém o segredo do aplicativo]**. Se sua organização ainda não tem segredos, adicione-os em **[!UICONTROL Configurações]** > **[!UICONTROL Segredos]**.

     Ambas as credenciais são obrigatórias. Insira os valores da credencial somente nos campos seguros. Não insira uma referência secreta em um campo de valor simples.

1. Em **[!UICONTROL Ferramentas disponíveis para usuários]**, expanda cada grupo de ferramentas e selecione as ferramentas de que sua organização precisa. Por padrão, somente as ferramentas `ads_accounts-list_ads_accounts` e `ads_accounts-get_ads_account` são selecionadas. Para alterar todas as ferramentas de uma só vez, use **[!UICONTROL Selecionar tudo]** ou **[!UICONTROL Limpar tudo]**. Você deve selecionar pelo menos uma ferramenta.

   Comece com as duas ferramentas de conta para uma verificação de primeiro acesso. Selecione as ferramentas de campanha e relatórios somente quando sua organização precisar e aprová-las. Para obter mais informações, consulte [Grupos de ferramentas](#tool-groups).

1. Selecione **[!UICONTROL Salvar conexão]** e examine os detalhes do conector **[!UICONTROL amazon-ads]** salvo.

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Source]** | O URL do servidor MCP da região selecionada. |
   | **[!UICONTROL Authentication]** | O método de autenticação, `amazon-ads_login`. |
   | **[!UICONTROL Tempo limite da ferramenta]** | O tempo que o Colaborador aguarda uma resposta da ferramenta. |
   | **[!UICONTROL Conexão]** | O aplicativo OAuth em uso e seu próprio status de logon. |
   | **[!UICONTROL Ferramentas]** | As ferramentas selecionadas para membros, com controles **[!UICONTROL Selecionar tudo]** e **[!UICONTROL Limpar]** e uma contagem de ferramentas selecionadas. |

   ![Detalhes do conector amazon-ads salvos mostrando a fonte na América do Norte, o método de autenticação, um Assinado em conexão com os botões Sair e Atualizar e duas das 47 ferramentas selecionadas.](./assets/amazon-ads/org-details.png){width="700" zoomable="yes"}

Ao salvar, você ou qualquer membro não entrará no [!DNL Amazon]. O status **[!UICONTROL Conexão]** nos detalhes do conector se refere à sua própria conexão, não à organização. Para verificar a conexão, selecione **[!UICONTROL Entrar]** na página de detalhes do conector para entrar com sua própria conta [!DNL Amazon] e selecione **[!UICONTROL Testar]**. O resultado mostra **[!UICONTROL Falha na conexão]** ou **[!UICONTROL Falha na conexão]**, com as ferramentas ou erros retornados. Um resultado bem-sucedido não confirma o acesso a uma operação específica do anunciante.

Para alterar as ferramentas disponíveis para membros posteriormente, atualize a seleção em **[!UICONTROL Ferramentas disponíveis]** com **[!UICONTROL Selecionar tudo]** ou **[!UICONTROL Limpar]** e selecione **[!UICONTROL Salvar seleção de ferramenta]**. Pelo menos uma ferramenta deve permanecer selecionada. Os membros não podem alterar a seleção da ferramenta.

Para interromper a oferta do conector para sua organização, selecione **[!UICONTROL Remover]** na página de detalhes do conector.

### Grupos de ferramentas {#tool-groups}

O conector [!DNL Amazon Ads] organiza suas ferramentas nos seguintes grupos:

| Grupo de ferramentas | Ferramentas | O que as ferramentas fazem |
| --- | --- | --- |
| [!UICONTROL Gerenciamento e direcionamento de campanha] | 7 | Consulte campanhas, grupos de anúncios, anúncios, públicos-alvo, portfólios e suas associações e verifique a elegibilidade do produto. |
| [!UICONTROL Contas e organização] | 6 | Liste e obtenha contas publicitárias e consulte links de anunciante e conta, contas de gerente e contas de teste. |
| [!UICONTROL Segurança e acesso do usuário] | 5 | Liste usuários, funções, permissões e convites e receba um convite. |
| [!UICONTROL Relatórios e análises] | 1 | Recuperar um relatório. A criação de relatórios não está incluída. |
| [!UICONTROL Amazon Marketing Cloud] | 6 | Leia fluxos de trabalho e fontes de dados, além dos URLs de status e download das execuções existentes. A execução do fluxo de trabalho não está incluída. |
| [!UICONTROL Resumos financeiros e de cobrança] | 4 | Ler faturas, resumos de faturas, uso do perfil de faturamento e notificações de faturamento. |
| [!UICONTROL Amazon Live] | 12 | Leia informações sobre canal, transmissão, transmissão ao vivo, mídia, carrossel e código promocional. |
| [!UICONTROL Qualificações e ofertas] | 6 | Leia a elegibilidade do programa e do produto, as ofertas e recompensas de promoção e as informações do token de termos. |

As ferramentas em cada grupo podem ser alteradas à medida que [!DNL Amazon] atualiza o conector. A configuração guiada salva a lista exata de ferramentas selecionadas, mesmo quando cada ferramenta é selecionada. As ferramentas que você deixar desmarcadas e as ferramentas que o servidor adicionar posteriormente não estarão disponíveis para os membros até que você as selecione.

>[!IMPORTANT]
>
>A lista de ferramentas de configuração tem curadoria para leitura de dados, mas o conector como um todo não é somente leitura. Os membros autorizam o escopo `advertising::campaign_management`, que é mais amplo do que a lista de configuração. Ao testar a conexão, a lista de ferramentas também pode incluir ferramentas que o servidor retorna. Revise cada definição de ferramenta e as [!DNL Amazon Ads] permissões de seus membros antes de selecionar mais ferramentas.

## Fazer logon como membro {#sign-in-as-a-member}

Depois que um administrador configura o conector, cada membro entra com sua própria conta [!DNL Amazon]. Você não precisa de um segredo do aplicativo ou token de acesso para entrar.

>[!NOTE]
>
>Se o conector informar que a entrada e o **[!UICONTROL Teste]** ainda não estão disponíveis em seu ambiente, pare aqui. A configuração da organização por si só não torna o logon de membro disponível. Entre em contato com seu representante Adobe.

1. Abra **[!UICONTROL Personalizações]**, selecione **[!UICONTROL Usuário]** e selecione **[!UICONTROL Conectores Externos]**. Localize o cartão **[!UICONTROL Amazon Ads]**.

1. Se o cartão exibir **[!UICONTROL Não configurado]**, peça ao administrador [configurar o conector](#configure-organization). Os membros não podem configurar o conector.

1. Quando o cartão mostrar **[!UICONTROL Não conectado]**, selecione **[!UICONTROL Entrar]**. Permitir o pop-up de entrada e entrar com a conta do [!DNL Amazon] que tem acesso às suas contas publicitárias.

1. Conclua os prompts de autenticação [!DNL Amazon], como a autenticação multifator (MFA), e o prompt de consentimento. Revise o nome do aplicativo e o acesso solicitado antes de aprovar.

   Com o aplicativo gerenciado pela Adobe, você autoriza o aplicativo Adobe. Com seu próprio aplicativo da organização, você autoriza esse aplicativo.

   >[!IMPORTANT]
   >
   >Continue apenas se você reconhecer o aplicativo e sua organização aprovar o acesso solicitado.

1. Retorne ao Colaborador e confirme se o cartão mostra **[!UICONTROL Conectado]**. Selecione **[!UICONTROL Exibir detalhes]** e revise as **[!UICONTROL Ferramentas habilitadas pelo administrador]**. Os membros podem exibir as ferramentas, mas não podem alterá-las ou remover a conexão da organização.

1. Selecione **[!UICONTROL Testar]** para verificar a descoberta da ferramenta e o status da conexão.

Um pop-up fechado não confirma se o logon foi bem-sucedido. Um teste bem-sucedido não confirma o acesso a cada anunciante, campanha, relatório ou instância [!DNL Amazon Marketing Cloud]. Quando um administrador se conecta, os outros membros não se conectam.

Para desconectar sua conta do [!DNL Amazon] do conector, selecione **[!UICONTROL Sair]**.

## Verifique o acesso à sua conta publicitária {#check-account-access}

Para confirmar quais contas publicitárias você pode usar, execute uma verificação somente leitura. Use uma conta de teste aprovada e verifique se o administrador habilitou as ferramentas `ads_accounts-list_ads_accounts` e `ads_accounts-get_ads_account`. Em seguida, inicie o chat e insira um aviso.

Exemplo de prompt:

* &quot;Usando o Amazon Ads, liste até cinco contas publicitárias que eu possa acessar na região configurada. Mostrar apenas o nome da conta, ID da conta e região se esses campos forem retornados. Não crie, atualize, exclua, inicie, execute fluxos de trabalho, gere relatórios ou altere permissões. Se um limite de listagem não for suportado, resuma apenas cinco resultados e não solicite páginas adicionais.&quot;

Confirme se o resultado inclui a conta esperada. Para exibir mais detalhes, peça ao Colaborador para obter os detalhes dessa conta, usando a ID da conta do resultado. Não adivinhe IDs de conta e não solicite campanhas somente para testar o logon.

Uma lista de contas vazia nem sempre significa que o conector não está funcionando. Verifique a conta do [!DNL Amazon] com a qual você entrou, seus convites aceitos, os anunciantes vinculados que uma conta de gerente cobre e a região configurada. Uma conta de teste sem campanhas também pode retornar uma lista de campanha vazia. Se uma ferramenta de que você precisa não estiver ativada, pergunte ao administrador. Não use uma ferramenta que altere os dados como substitutos.

## Solução de problemas de acesso {#troubleshoot-access}

Se não conseguir acessar os dados do [!DNL Amazon Ads], verifique o seguinte com o administrador:

| Problema | O que verificar |
| --- | --- |
| O cartão **[!UICONTROL Amazon Ads]** ou **[!UICONTROL Configure]** está ausente | Confirme se o conector está disponível para a sua organização e se você tem permissão para gerenciar conectores da organização. Os membros devem aguardar a configuração da organização. |
| A configuração gerenciada pela Adobe é salva, mas o logon falha | Entre em contato com seu representante da Adobe para confirmar se o aplicativo gerenciado pela Adobe está disponível em seu ambiente. Um salvamento bem-sucedido não confirma isso. |
| O URL de redirecionamento não corresponde | Compare a **[!UICONTROL URL de Redirecionamento]** completa da caixa de diálogo Colaborador com as **[!UICONTROL URLs de Retorno Permitidas]** em [!DNL Login with Amazon], incluindo o esquema, o host e o caminho. Não use um URL de redirecionamento de outro cliente, região ou ambiente MCP, ou o URL da página de Colaborador no seu navegador. |
| A **[!UICONTROL URL de redirecionamento]** mostra somente `/connectors/oauth/callback` | Seu ambiente ainda não mostra a URL de redirecionamento completa ou o logon de suporte e o **[!UICONTROL Teste]**. Não registre um caminho parcial ou adivinhe o nome do host. Entre em contato com seu representante Adobe. |
| Não é possível salvar sua própria configuração de aplicativo do OAuth | Insira a ID do cliente OAuth e o segredo do cliente e mantenha pelo menos uma ferramenta selecionada. Verifique se a **[!UICONTROL ID do aplicativo Amazon]** é a ID do cliente OAuth, não uma ID de anunciante ou a ID do aplicativo [!DNL Amazon]. |
| Falha no consentimento ou na autorização do aplicativo | Verifique a aprovação da API [!DNL Amazon Ads], o perfil de segurança, a ID do cliente e o emparelhamento secreto, o registro da URL de redirecionamento e o aplicativo mostrado na tela de consentimento. Não compartilhe o URL de consentimento, o código de autorização ou os tokens quando solicitar ajuda. |
| Você entra, mas contas ou ferramentas são negadas ou estão vazias | Verifique a conta do [!DNL Amazon] com a qual você entrou, seu convite aceito, os anunciantes vinculados que uma conta de gerente cobre, a região configurada e as permissões que a tarefa requer. O acesso ao aplicativo ou às ferramentas de parceiros não confirma o acesso do anunciante. O acesso de [!DNL Amazon Marketing Cloud] é separado. |
| [!DNL Amazon Ads] diz que a conta atual não pode acessar uma página | Selecione **[!UICONTROL Alterar conta]** e escolha a conta de anunciante ou gerente. Se a conta estiver ausente, peça ao administrador para verificar se você aceitou o convite e se está atribuído à conta. Se a conta estiver presente, mas o gerenciamento de usuários não estiver disponível, peça ao administrador para verificar sua função. |
| Uma ferramenta está ausente ou indisponível | Verifique a seleção de ferramentas da sua organização, as ferramentas que o servidor retorna e as permissões do [!DNL Amazon Ads]. As ferramentas que o servidor adiciona posteriormente não são selecionadas automaticamente. Por padrão, somente as duas ferramentas de conta são ativadas. |
| **[!UICONTROL Test]** relata um conector pessoal com o mesmo nome | Um conector pessoal com o mesmo nome pode ter prioridade sobre o conector da organização. Siga as orientações mostradas para remover ou renomear apenas o conector pessoal conflitante, com a aprovação do proprietário. |
| A janela pop-up de entrada está bloqueada, não termina ou o status não é atualizado | Permita o pop-up e retorne ao Colaborador para verificar o status e os detalhes de qualquer erro. Não assuma o sucesso porque o pop-up fechou ou mostrou uma página de aterrissagem. |
| Uma ferramenta expira ou você deve fazer logon repetidamente | Verifique o **[!UICONTROL Tempo Limite da Ferramenta]** por 60 segundos, os detalhes do erro, a disponibilidade da rede e do [!DNL Amazon] e a configuração do aplicativo. |
| O colaborador diz que a configuração não está habilitada ou que um novo segredo ainda está sendo configurado | Verifique o status com seu representante da Adobe. Não crie as credenciais novamente repetidamente e não trate um salvamento com falha como bem-sucedido. |

Ao entrar em contato com o suporte, inclua apenas o texto do erro, a hora do erro, o ambiente, a região selecionada e a opção de aplicativo OAuth. Não compartilhe segredos do aplicativo, tokens de acesso, códigos de autorização, o cabeçalho de autorização, parâmetros de consulta de consentimento ou redirecionamento ou dados da conta do cliente.
