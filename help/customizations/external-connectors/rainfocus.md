---
title: Conector externo do RainFocus
description: Saiba como configurar o conector externo do RainFocus no CX Enterprise Coworker para sua organização e fazer logon com o RainFocus para usar as ferramentas de dados do evento no chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está na versão beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: e65f811f1e9c27de372ce924301b68f20ab9c1a6
workflow-type: tm+mt
source-wordcount: '2116'
ht-degree: 0%
---

# Conector externo do RainFocus {#rainfocus}

Use o conector externo [!DNL RainFocus] para trabalhar com os dados de evento [!DNL RainFocus] no Adobe CX Enterprise Coworker. Após configurar o conector, pergunte ao Colaborador sobre as sessões, os participantes e os atributos personalizados que sua conta do [!DNL RainFocus] pode acessar. O conector usa um Perfil MCP [!DNL RainFocus], um servidor MCP (Protocolo de Contexto de Modelo) hospedado por [!DNL RainFocus].

>[!AVAILABILITY]
>
>O conector externo [!DNL RainFocus] está na versão beta. A documentação e a funcionalidade estão sujeitas a alterações.

## Configuração do conector {#connector-configuration}

O processo de configuração do conector tem três partes separadas:

* Preparação de **[!DNL RainFocus]:** Um administrador [!DNL RainFocus] provisiona um Perfil MCP, habilita suas ferramentas e fornece a URL do perfil. Cada membro precisa de uma conta [!DNL RainFocus] com a função correta.
* **Configuração da organização:** um administrador de parceiro salva a URL do perfil MCP uma vez para toda a organização. O conector habilita uma lista fixa de ferramentas de leitura.
* **Entrada de membro:** cada membro entra com sua própria conta [!DNL RainFocus]. Os membros podem acessar somente os dados permitidos pela função [!DNL RainFocus] e pelo perfil.

Salvar a configuração da organização não faz logon em nenhum membro, concede permissões de [!DNL RainFocus] ou executa uma ferramenta de dados [!DNL RainFocus]. Cada membro deve fazer logon separadamente.

## Pré-requisitos {#prerequisites}

Antes de começar, verifique se você tem o seguinte:

* **Acesso de colaborador:** uma conta de administrador de colaborador com configurações de organização ativadas, em uma organização em que o conector [!DNL RainFocus] está disponível.
* **Um Perfil MCP:** Um Perfil MCP [!DNL RainFocus] provisionado e sua URL completa de perfil HTTPS, fornecidos pelo administrador [!DNL RainFocus]. Para obter mais informações, consulte [Obter a URL do perfil MCP](#get-profile-url).
* **Contas de membro:** Para cada membro, uma conta [!DNL RainFocus] com uma função de segurança que dá acesso aos dados de que precisam.

Você não insere uma ID do cliente, segredo do cliente ou token de acesso no Coworker. Cada membro entra no [!DNL RainFocus] com sua própria conta.

## Preparar acesso de [!DNL RainFocus] {#prepare-rainfocus}

Antes de configurar o conector no Colaborador, prepare o Perfil MCP e o acesso de membro no [!DNL RainFocus]. [!DNL RainFocus] é proprietário do perfil, de suas ferramentas habilitadas, das funções de membro e de quaisquer encargos. O Colaborador armazena a URL de perfil e a lista de ferramentas de sua organização, além da entrada de cada membro.

### Obter o URL do perfil MCP {#get-profile-url}

O [!DNL RainFocus] geralmente configura Perfis MCP para seus clientes com base em seus requisitos. Se o administrador do [!DNL RainFocus] configurar o perfil, o processo será o seguinte:

1. Em [!DNL RainFocus], abra o **[!UICONTROL Conjunto de Integração]** > **[!UICONTROL Perfis Ativos]** > **[!UICONTROL Perfis MCP]** e crie um perfil.
1. Habilite somente as ferramentas necessárias ao seu caso de uso e deixe as outras ferramentas desativadas.
1. Copie o URL do servidor MCP gerado. A URL é específica do perfil.

Forneça o URL completo ao administrador do Colaborador que configura o conector. Não adivinhe um nome de perfil ou crie você mesmo o URL. Para obter mais informações, consulte o [anúncio de Perfis MCP RainFocus](https://www.rainfocus.com/company/news-press/rainfocus-launches-ai-agent-connectivity-for-event-data-with-mcp-profiles/).

### Confirmar acesso do membro {#confirm-member-access}

Cada membro entra com sua própria conta [!DNL RainFocus]. A função de segurança da conta e as ferramentas ativadas no perfil controlam quais dados um membro pode acessar. Peça ao administrador do [!DNL RainFocus] para confirmar que cada membro tem a função com menos privilégios para suas tarefas.

## Configurar o conector do para sua organização {#configure-organization}

Os administradores disponibilizam o conector [!DNL RainFocus] para todos na organização. As alterações na página da organização se aplicam a todos os usuários da organização. O escopo **[!UICONTROL Org]** aparece somente para administradores com configurações de organização ativadas.

1. Abra **[!UICONTROL Personalizações]**, selecione **[!UICONTROL Org]** e **[!UICONTROL Conectores Externos]**.
1. Localize o cartão **[!UICONTROL RainFocus]**, que tem um rótulo Beta e mostra **[!UICONTROL Não configurado]**. Selecione **[!UICONTROL Configurar]**.

1. Na caixa de diálogo **[!UICONTROL Configurar RainFocus]**, digite a **[!UICONTROL URL do perfil de desenvolvimento]**. Use a URL completa do perfil MCP fornecida pelo administrador do [!DNL RainFocus].

   A URL deve começar com `https://`. Ele não pode conter espaços, barras invertidas, uma sequência de consulta (`?`), um fragmento (`#`), um nome de usuário ou senha, uma porta não padrão ou segmentos de caminho `.` ou `..`. Se o URL não corresponder a uma regra, o Colaborador mostrará uma mensagem descrevendo a regra. O colaborador verifica somente o formato do URL. Ele não verifica se o perfil existe ou se você pode usá-lo.

1. Revise as **[!UICONTROL seções Acesso e permissões]** e **[!UICONTROL incluo na lista de permissões de ferramenta de leitura fixo]**. O conector ativa todas as 10 ferramentas de leitura e você não pode adicioná-las, removê-las ou editá-las nesta caixa de diálogo. Algumas ferramentas retornam dados pessoais de participantes ou exportações em massa. Para obter mais informações, consulte [Ferramentas disponíveis](#available-tools).

   ![Configurar a caixa de diálogo RainFocus mostrando o campo vazio da URL do perfil de desenvolvimento, a seção Acesso e permissões, o incluo na lista de permissões fixo da ferramenta de leitura com 10 ferramentas e o botão Salvar conexão.](./assets/rainfocus/org-configure.png){width="500" zoomable="yes"}

1. Selecione **[!UICONTROL Salvar conexão]**. Enquanto o Colaborador salva a conexão, não é possível editar ou cancelar o formulário.

Se o salvamento falhar, a caixa de diálogo mostra **[!UICONTROL Não foi possível salvar a conexão]** e mantém a URL inserida. Algumas configurações podem ser salvas mesmo quando houver falha ao salvar. Reabra a configuração e verifique-a antes de tentar novamente. Para evitar alterações conflitantes, verifique se apenas um administrador configura o conector por vez.

### Verificar a configuração salva {#verify-configuration}

Depois de salvar a conexão, verifique a configuração:

1. Depois de salvar, a caixa de diálogo abre os detalhes do conector salvo. Retorne à lista **[!UICONTROL Conectores Externos]** e confirme se o cartão **[!UICONTROL RainFocus]** mostra a **[!UICONTROL Configuração salva]** e a **[!UICONTROL Configuração de exibição]**.
1. Recarregue a página e selecione **[!UICONTROL Exibir configuração]**.
1. Confirme os seguintes detalhes:

   * **[!UICONTROL Source]** mostra a URL do perfil que você inseriu.
   * **[!UICONTROL Autenticação]** presente.
   * **[!UICONTROL Política de ferramenta]** > **[!UICONTROL Padrões ou nomes de ferramenta permitidos]** lista as mesmas 10 ferramentas que a seção [Ferramentas disponíveis](#available-tools).

1. Para verificar sua própria conexão, selecione **[!UICONTROL Testar]**. Se o Colaborador solicitar que você entre, use sua própria conta do [!DNL RainFocus], conforme descrito em [Entrar como membro](#sign-in-as-a-member).

   **[!UICONTROL Test]** lista as ferramentas do servidor e atualiza a contagem de **[!UICONTROL Ferramentas]**. Se o servidor não retornar nenhuma ferramenta, os detalhes mostrarão **[!UICONTROL 0 ferramentas disponíveis]**. Se o teste falhar, os detalhes mostrarão **[!UICONTROL Falha na conexão]**.

   ![Detalhes do conector de foco de chuva salvos que mostram uma fonte redigida, o método de autenticação rainfocus_login, uma conexão Não conectado com um botão Entrar e os botões Testar e Remover.](./assets/rainfocus/org-details.png){width="700" zoomable="yes"}

Os controles de **[!UICONTROL Conexão]**, **[!UICONTROL Teste]** e de entrada nos detalhes do conector se aplicam somente à sua própria conexão. Quando você entra como administrador, nenhum membro entra. Um teste bem-sucedido lista somente as ferramentas. O teste não executa uma ferramenta de dados [!DNL RainFocus] nem confirma se um membro pode acessar dados específicos.

Os detalhes do conector não têm opção para editar o URL do perfil. **[!UICONTROL Remover]** abre uma confirmação e remove a conexão de toda a organização. Trate a remoção como uma decisão deliberada do administrador, não como uma etapa de solução de problemas.

### Ferramentas disponíveis {#available-tools}

O conector [!DNL RainFocus] habilita uma lista fixa de 10 ferramentas de leitura:

| Ferramenta | Área de dados |
| --- | --- |
| `get_attendeeInfo` | Participantes |
| `get_attendee_load` | Participantes |
| `get_attendee_search` | Participantes |
| `get_attribute_load` | Atributos personalizados |
| `get_attribute_search` | Atributos personalizados |
| `get_attributevalue_load` | Atributos personalizados |
| `get_entityDataDump_attendee` | Participantes, exportação em massa |
| `get_entityDataDump_session` | Sessões, exportação em massa |
| `get_session_load` | Sessions |
| `get_session_search` | Sessions |

As ferramentas que não estão nessa lista, incluindo as que o [!DNL RainFocus] adiciona posteriormente, não são habilitadas automaticamente. A lista não substitui as funções de segurança [!DNL RainFocus] ou as configurações de ferramenta do perfil, que ainda controlam o acesso aos dados.

>[!IMPORTANT]
>
>Várias ferramentas podem retornar dados pessoais e informações de contato sobre participantes. Duas ferramentas exportam dados em massa e seus resultados podem ser grandes. As leituras também podem incorrer em encargos de acordo com os termos do [!DNL RainFocus]. Revise essas ferramentas com seus proprietários de governança de dados antes que os membros façam logon.

## Fazer logon como membro {#sign-in-as-a-member}

Depois que um administrador configura o conector, cada membro entra com sua própria conta [!DNL RainFocus]. Você não precisa de uma ID do cliente, segredo do cliente ou token de acesso para entrar.

1. Abra **[!UICONTROL Personalizações]** e selecione **[!UICONTROL Conectores Externos]**. Os membros usam o escopo **[!UICONTROL Usuário]** por padrão. Localize o cartão **[!UICONTROL RainFocus]**.
1. Se o cartão mostrar **[!UICONTROL Ainda não disponível. Seu administrador precisa configurar isso.]**, peça ao seu administrador para [configurar o conector](#configure-organization). Os membros não podem inserir a URL de seu próprio perfil.
1. Verifique o status no cartão. O cartão mostra o status **[!UICONTROL Entrada necessária]**, **[!UICONTROL Conectada]**, **[!UICONTROL Configurada pelo administrador]** ou **[!UICONTROL Falha de conexão]**.

   **[!UICONTROL Configurar pelo administrador]** significa que o Colaborador não pode confirmar seu status de entrada. Isso não significa que você está conectado ou desconectado.

1. Selecione **[!UICONTROL Entrar]**. Você também pode abrir os detalhes do cartão e selecionar **[!UICONTROL Entrar]** na seção **[!UICONTROL Conexão]**. Na janela [!DNL RainFocus], conclua os prompts de entrada, logon único (SSO), autenticação multifator (MFA) e consentimento. Revise o acesso que você aprova.

   Se **[!UICONTROL Descobrir autorização]** for exibido, o Coworker lerá os detalhes de entrada do servidor, não suas ferramentas. Se a descoberta falhar ou o painel solicitar um **[!UICONTROL ID do Cliente]** ou **[!UICONTROL segredo do Cliente]**, pare e contate o administrador. Não insira ou suponha credenciais.

   ![Detalhes do conector RainFocus de um membro, mostrando um status obrigatório de Entrada, uma URL de servidor redigida, Cada usuário entra, uma conexão Não entrou com um botão de autorização Descobrir e as 10 ferramentas habilitadas pelo administrador.](./assets/rainfocus/member-details.png){width="700" zoomable="yes"}

1. Retorne ao Colaborador e confirme se o status mostra **[!UICONTROL Conectado]**. Uma janela de entrada fechada não confirma o sucesso. Se fechar a janela antecipadamente, nada será alterado e você poderá tentar novamente.
1. Abra os detalhes do cartão para revisar a configuração com o administrador. Você pode exibir a **[!UICONTROL URL do Servidor]**, **[!UICONTROL Quem entra]**, a **[!UICONTROL Autenticação]** e as **[!UICONTROL Ferramentas habilitadas pelo seu administrador]**.
1. Selecione **[!UICONTROL Testar]** no cartão ou **[!UICONTROL Testar conexão]** nos detalhes para verificar a conexão com sua conta.

   Um teste bem-sucedido mostra que [!DNL RainFocus] respondeu usando sua conta, com o número de ferramentas disponíveis. O teste lista somente as ferramentas. Ele não executa uma ferramenta de dados nem confirma o acesso a eventos ou registros específicos. Para renovar sua entrada e listar as ferramentas novamente, selecione **[!UICONTROL Atualizar]**. Se o Coworker não puder renovar a entrada, o botão mostrará **[!UICONTROL Recarregar ferramentas]**, que somente lista as ferramentas novamente.

1. Se o teste falhar, o Colaborador mostra **[!UICONTROL Não foi possível se conectar ao RainFocus]**, com **[!UICONTROL Tente novamente]** e **[!UICONTROL Detalhes técnicos]**. Se você estiver desconectado, entre novamente. Se o problema continuar, entre em contato com o administrador.

Os membros podem fazer logon, fazer logoff, testar, atualizar e visualizar as ferramentas ativadas. Os membros não podem alterar ou remover a conexão da organização, editar a URL do perfil ou alterar as ferramentas. Todos os membros que abrirem os detalhes poderão exibir o URL do perfil. Quando um administrador se conecta, os outros membros não se conectam.

Para desconectar sua conta do [!DNL RainFocus] do conector, selecione **[!UICONTROL Sair]**. Você pode entrar novamente a qualquer momento.

## Verifique o acesso aos dados do evento {#check-event-access}

Para confirmar se você pode usar os dados do [!DNL RainFocus], execute uma verificação somente leitura com uma solicitação limitada. Use um evento com o qual você esteja aprovado para trabalhar e evite ferramentas que retornem dados do participante ou exportações em massa para essa verificação. Inicie um chat e insira um aviso.

Exemplo de prompt:

* &quot;Usando o RainFocus, encontre até cinco sessões que eu possa acessar. Mostrar somente o título da sessão e a ID se esses campos forem retornados. Não exporte dados, retorne informações do participante ou altere nada.&quot;

Confirme se o resultado inclui sessões esperadas. Um resultado vazio nem sempre significa que o conector não está funcionando. Verifique a conta do [!DNL RainFocus] com a qual você entrou, sua função de segurança e as ferramentas habilitadas no perfil. Se um resultado for inesperadamente grande ou incluir dados confidenciais, pare e restrinja sua solicitação.

## Solução de problemas de acesso {#troubleshoot-access}

Se não conseguir acessar os dados do [!DNL RainFocus], verifique o seguinte com o administrador:

| Problema | O que verificar |
| --- | --- |
| O cartão **[!UICONTROL RainFocus]** está ausente | Confirme com seu representante da Adobe se o conector está disponível para sua organização. |
| O escopo **[!UICONTROL Org]** está ausente | Confirme se você é um administrador e se as configurações da organização estão ativadas para a sua organização. |
| O colaborador rejeita o URL do perfil | Siga a regra na mensagem. Use a URL completa do perfil do administrador [!DNL RainFocus] e não adivinhe um nome de perfil. |
| **[!UICONTROL Não foi possível salvar a conexão]** aparece | Algumas configurações podem ser salvas. Reabra a configuração e verifique-a antes de tentar novamente. Verifique se apenas um administrador configura o conector de cada vez. |
| O cartão mostra **[!UICONTROL Ainda não disponível. Seu administrador precisa configurar isto.]** | Configuração da organização ausente. Peça ao administrador para [configurar o conector](#configure-organization). |
| A entrada pede uma **[!UICONTROL ID do Cliente]** ou **[!UICONTROL segredo do Cliente]**, ou a descoberta falha | Pare o e entre em contato com o administrador. Não insira ou suponha credenciais ou registre um aplicativo. |
| Falha na entrada após a aprovação do acesso em [!DNL RainFocus] | Verifique a conta [!DNL RainFocus] e a função de segurança que você usou. Peça ao seu representante da Adobe e ao [!DNL RainFocus] para verificarem a configuração de entrada do seu ambiente. Não compartilhar o URL de entrada. |
| **[!UICONTROL Teste]** bem-sucedido, mas as solicitações de dados falham | **[!UICONTROL Test]** lista apenas ferramentas. Verifique sua função de segurança do [!DNL RainFocus], as ferramentas habilitadas no perfil e os filtros exigidos pela ferramenta. |
| **[!UICONTROL Não foi possível conectar ao RainFocus]** aparece quando você está conectado | Selecione **[!UICONTROL Tentar novamente]**. Se o problema continuar, entre em contato com o administrador. |
| Um resultado é inesperadamente grande ou inclui dados confidenciais | Interrompa e restrinja sua solicitação. Não cole dados brutos do evento em tíquetes ou bate-papo. |

Ao entrar em contato com o suporte, inclua apenas o texto do erro, a hora do erro e o ambiente. Não compartilhe detalhes técnicos, URLs de perfil, capturas de entrada, senhas, tokens ou códigos de autorização.
