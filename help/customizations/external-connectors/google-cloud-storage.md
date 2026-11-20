---
title: Conector externo do Google Cloud Storage
description: Saiba como configurar o conector externo do Google Cloud Storage no CX Enterprise Coworker com seu aplicativo Google OAuth e fazer logon para ler dados do bucket no chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está na versão beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 70782269f48e3ff87ca95a1341ee74b02da1d7f4
workflow-type: tm+mt
source-wordcount: '2408'
ht-degree: 1%
---

# Conector externo do Google Cloud Storage {#google-cloud-storage}

Use o conector externo [!DNL Google Cloud Storage] para ler seus dados do [!DNL Cloud Storage] no Adobe CX Enterprise Coworker. Depois de configurar o conector, peça ao Coworker para listar buckets em um projeto conhecido, listar objetos por prefixo, inspecionar bucket e metadados de objetos e ler arquivos aprovados. O conector é um servidor MCP hospedado por [!DNL Google].

>[!AVAILABILITY]
>
>O conector externo [!DNL Google Cloud Storage] está na versão beta. A documentação e a funcionalidade estão sujeitas a alterações.

## Configuração do conector {#connector-configuration}

O processo de configuração do conector tem três partes separadas:

* **[!DNL Google Cloud]preparação:** Um administrador do [!DNL Google Cloud] prepara as funções de cobrança, API do [!DNL Cloud Storage] e IAM (Identity and Access Management) para membros. O administrador também prepara um cliente OAuth de propriedade da organização.
* **Configuração da organização:** um administrador de parceiro configura o conector uma vez para toda a organização. O administrador registra o URL de redirecionamento do Colaborador, insere as credenciais do cliente OAuth e seleciona as ferramentas que os membros podem usar.
* **Entrada de membro:** cada membro entra com sua própria conta [!DNL Google]. Os membros podem acessar somente os compartimentos e objetos que o IAM [!DNL Google Cloud] permite para sua conta.

O conector é somente leitura. Ele solicita o escopo `https://www.googleapis.com/auth/devstorage.read_only` e oferece apenas ferramentas de leitura. Sua organização fornece seu próprio aplicativo OAuth [!DNL Google]. Não há nenhum aplicativo OAuth gerenciado pela Adobe para esse conector.

Salvar a configuração da organização não faz logon em nenhum membro nem concede permissões de [!DNL Cloud Storage]. Cada membro já deve ter o acesso necessário ao IAM e deve fazer logon separadamente.

## Pré-requisitos {#prerequisites}

Antes de começar, verifique se você tem o seguinte:

* **Para preparação de [!DNL Google Cloud]:** um projeto com faturamento e a API [!DNL Cloud Storage] habilitada, compartimentos que contêm dados aprovados, concessões IAM para membros e um cliente OAuth [!DNL Google] do tipo **[!UICONTROL Aplicativo Web]**.
* **Para configuração de organização:** uma conta com permissão para gerenciar conectores de organização no Colaborador. Você também precisa da ID do cliente OAuth e do segredo do cliente ou dos segredos da organização existentes que os contêm.
* **Para entrada de membro:** uma conta [!DNL Google] que o público-alvo do aplicativo OAuth e o IAM [!DNL Google Cloud] permitem.

Saber a ID do projeto e os buckets que os membros planejam ler. O conector não tem uma ferramenta para listar projetos. O cliente OAuth pode pertencer a um projeto diferente dos buckets.

## Preparar a Google Cloud {#prepare-google-cloud}

Antes de configurar o conector no Co-worker, prepare seu projeto [!DNL Google Cloud] e acesso de membros. Uma entrada [!DNL Google] bem-sucedida não concede permissões de armazenamento.

### Preparar o projeto e o IAM {#prepare-project-iam}

Um administrador do [!DNL Google Cloud] conclui as seguintes etapas:

1. Selecione ou crie um projeto no [Google Cloud Console](https://console.cloud.google.com/).
1. Vincule uma conta de faturamento em cada projeto que contenha períodos.

   O acesso somente leitura não é gratuito. As taxas de armazenamento, operação, recuperação e rede ainda podem ser aplicadas. Para obter mais informações, consulte [Preços do armazenamento na nuvem](https://cloud.google.com/storage/pricing).

1. Habilite a **[!UICONTROL API de Armazenamento na Nuvem]** em cada projeto relevante. Se o cliente OAuth pertencer a um projeto separado, ative a API nesse projeto também.
1. Conceder aos membros as funções com menos privilégios na tabela a seguir. Prefira um grupo gerenciado a contas individuais.

| Função | Onde conceder | Finalidade |
| --- | --- | --- |
| [!UICONTROL Usuário da Ferramenta MCP] (`roles/mcp.toolUser`) | O projeto usado para chamadas MCP | Fazer chamadas de ferramenta MCP (`mcp.tools.call`). |
| [!UICONTROL Visualizador do Bucket de Armazenamento] (`roles/storage.bucketViewer`) ou uma função somente leitura personalizada | O projeto que contém os buckets | Listar compartimentos e ler metadados do compartimento (`storage.buckets.list` e `storage.buckets.get`). |
| [!UICONTROL Visualizador de Objetos de Armazenamento] (`roles/storage.objectViewer`) | Cada bucket autorizado ou o projeto, se os membros puderem ler todos os seus buckets | Listar objetos, ler metadados do objeto e ler conteúdo do objeto (`storage.objects.list` e `storage.objects.get`). |

Não conceda a [!UICONTROL Administrador de Armazenamento] somente a compartimentos de lista. Membros sem permissão para listar buckets ainda podem ler um bucket autorizado quando fornecem seu nome. Para obter mais informações, consulte [Funções do IAM de Armazenamento na Nuvem](https://docs.cloud.google.com/storage/docs/access-control/iam-roles) na documentação [!DNL Google Cloud].

[!DNL Google] também oferece uma política de negação IAM opcional que bloqueia ferramentas MCP de leitura-gravação para outros clientes MCP. O conector do Colaborador já usa uma seleção de ferramenta somente leitura e um escopo somente leitura. Analise os efeitos em todo o projeto com o administrador [!DNL Google Cloud] antes de aplicar a política. Para obter mais informações, consulte [Impedir o uso da ferramenta MCP de leitura-gravação](https://docs.cloud.google.com/mcp/prevent-read-write-tool-use).

### Configurações de conexão {#connection-settings}

O colega de trabalho usa as seguintes configurações de conexão. Esses valores não são inseridos na caixa de diálogo de configuração.

| Configuração | Valor |
| --- | --- |
| URL do servidor MCP | `https://storage.googleapis.com/storage/mcp` (somente ponto de extremidade global) |
| Transporte | HTTP transmitido |
| Servidor de autorização | `https://accounts.google.com/` |
| Escopo solicitado | `https://www.googleapis.com/auth/devstorage.read_only` |

Para obter mais informações, consulte [Usar o servidor MCP remoto do Armazenamento em Nuvem](https://docs.cloud.google.com/storage/docs/use-cloud-storage-mcp) e [Autenticar para servidores MCP do Google](https://docs.cloud.google.com/mcp/authenticate-mcp) na documentação [!DNL Google Cloud].

## Configurar o conector do para sua organização {#configure-organization}

Os administradores disponibilizam o conector [!DNL Google Cloud Storage] para todos na organização. As alterações na página da organização se aplicam a todos os membros da organização.

1. Abra **[!UICONTROL Personalizações]**, selecione **[!UICONTROL Org]** e **[!UICONTROL Conectores Externos]**. No cartão **[!UICONTROL Google Cloud Storage]**, selecione **[!UICONTROL Configurar]**.

   Se o conector já estiver configurado, abra a configuração salva.

1. Na caixa de diálogo **[!UICONTROL Configurar o Google Cloud Storage para sua organização]**, em **[!UICONTROL Seu aplicativo do Google]**, copie a **[!UICONTROL URL de redirecionamento]** concluída.

   O URL de redirecionamento difere por ambiente e região. Sempre copiar o valor exato da caixa de diálogo. Não use o URL da página do Co-worker no seu navegador, o URL do servidor MCP ou um URL de redirecionamento de outro ambiente.

1. Prepare o cliente OAuth para sua organização na [Plataforma de Autenticação da Google](https://console.cloud.google.com/auth/overview):

   1. Configure o **[!UICONTROL Branding]** e o **[!UICONTROL Audience]** para sua organização. Para um aplicativo externo em teste, adicione os membros desejados como usuários de teste. Conclua os requisitos de publicação e verificação do [!DNL Google] que se aplicam antes de um uso mais amplo.
   1. Em **[!UICONTROL Acesso aos Dados]**, inclua o escopo `https://www.googleapis.com/auth/devstorage.read_only`. O conector não precisa de escopos de leitura-gravação ou controle total.
   1. Em **[!UICONTROL Clientes]**, crie ou selecione um cliente OAuth com o **[!UICONTROL Tipo de aplicativo]** definido como **[!UICONTROL Aplicativo Web]**.
   1. Adicione a URL de redirecionamento copiada para **[!UICONTROL URIs de redirecionamento autorizados]**. Se um cliente atender a vários ambientes, registre o URL de redirecionamento de cada ambiente.
   1. Obtenha a **[!UICONTROL ID do Cliente]** e o **[!UICONTROL segredo do Cliente]** por meio do processo de tratamento secreto aprovado pela sua organização.

   Os membros autorizam esse aplicativo OAuth de propriedade da organização. Mantenha as credenciais fora dos bate-papos, tíquetes e documentação.

1. Em **[!UICONTROL De onde vêm as credenciais]**, selecione uma das seguintes opções:

   * **[!UICONTROL Inserir novo]:** Insira a **[!UICONTROL ID do cliente Google OAuth]** e o **[!UICONTROL segredo do cliente Google OAuth]**. Colaborador armazena os valores informados como segredos da organização.
   * **[!UICONTROL Usar um segredo]:** Selecione os segredos da organização salvos que contêm a ID do cliente e o segredo do cliente.

   Não use segredos pessoais para um conector de organização.

   ![Configure o Google Cloud Storage para a caixa de diálogo da sua organização mostrando uma URL de redirecionamento redigida, as opções Inserir novo e Usar um segredo existente, os campos ID do cliente do Google OAuth e segredo do cliente e o aviso Antes que as pessoas possam entrar.](./assets/google-cloud-storage/org-configure.png){width="500" zoomable="yes"}

1. Expandir **[!UICONTROL Procurar e ler (5 de 5)]**. Mantenha todas as cinco ferramentas selecionadas ou selecione apenas as ferramentas de que os membros precisam. Você deve selecionar pelo menos uma ferramenta. Para obter mais informações, consulte [Ferramentas disponíveis](#available-tools).

   Em **[!UICONTROL Acesso e permissões]**, leia os avisos de **[!UICONTROL Acesso somente leitura]** e **[!UICONTROL Cada pessoa entra separadamente]**. Em seguida, selecione **[!UICONTROL Salvar conexão]**.

   ![Seção Ferramentas disponíveis para os usuários com todas as cinco ferramentas Procurar e ler selecionadas, seguidas pelo acesso Somente leitura e cada pessoa inscreve avisos separadamente.](./assets/google-cloud-storage/org-tools.png){width="500" zoomable="yes"}

1. Revise os detalhes do conector **[!UICONTROL google-cloud-storage]** salvo.

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Source]** | A URL do servidor MCP, `https://storage.googleapis.com/storage/mcp`. |
   | **[!UICONTROL Authentication]** | O método de autenticação, `google-cloud-storage_login`. |
   | **[!UICONTROL Conexão]** | Seu próprio status de logon. |
   | **[!UICONTROL Ferramentas]** | As ferramentas selecionadas para membros, com controles **[!UICONTROL Selecionar tudo]** e **[!UICONTROL Limpar]** e uma contagem de ferramentas selecionadas. |

   ![Detalhes do conector google-cloud-storage salvos mostrando a origem, o método de autenticação, uma conexão Não conectado com um botão Entrar e cinco das cinco ferramentas selecionadas.](./assets/google-cloud-storage/org-details.png){width="700" zoomable="yes"}

O status **[!UICONTROL Não conectado]** nos detalhes do conector se refere à sua própria conexão, não à organização. Salvar a configuração da organização não faz logon nem de nenhum membro e não confirma o acesso a um período. Para usar o conector sozinho, siga as etapas em [Fazer logon como membro](#sign-in-as-a-member).

Para alterar as ferramentas disponíveis para membros posteriormente, atualize a seleção na página de detalhes do conector e selecione **[!UICONTROL Salvar seleção da ferramenta]**. Os membros não podem alterar a seleção da ferramenta.

Para interromper a oferta do conector para sua organização, selecione **[!UICONTROL Remover]** na página de detalhes do conector.

### Ferramentas disponíveis {#available-tools}

O conector [!DNL Google Cloud Storage] fornece as seguintes ferramentas somente leitura no grupo **[!UICONTROL Procurar e ler]**:

| Ferramenta | Descrição | Permissão necessária |
| --- | --- | --- |
| `list_buckets` | Liste os buckets em um projeto [!DNL Google Cloud] conhecido, com filtragem e paginação de prefixo. | `storage.buckets.list` no projeto |
| `list_objects` | Listar objetos e prefixos em um bucket autorizado. A listagem não é recursiva por padrão. | `storage.objects.list` no bucket |
| `get_bucket_metadata` | Configuração do bucket de leitura, como localização, classe de armazenamento, retenção e controle de versão. | `storage.buckets.get` |
| `get_object_metadata` | Leia o tamanho do objeto, o tipo de conteúdo, os carimbos de data e hora, a geração e os metadados personalizados. | `storage.objects.get` |
| `read_object` | Ler texto ou conteúdo binário suportado, até 8 MiB por objeto. | `storage.objects.get` |

Cada chamada de ferramenta também requer a permissão `mcp.tools.call`, geralmente por meio da função de [!UICONTROL Usuário da Ferramenta MCP] no projeto relevante.

O conector não oferece a ferramenta `read_text` obsoleta ou as ferramentas `write_text`, `create_bucket`, `delete_object` e `delete_bucket`. Não há opção para ativar as ferramentas de gravação. As ferramentas que o [!DNL Google] adicionar ao servidor posteriormente não se tornarão disponíveis automaticamente, mesmo quando você selecionar todas as cinco ferramentas.

## Fazer logon como membro {#sign-in-as-a-member}

Depois que um administrador configura o conector, cada membro entra com sua própria conta [!DNL Google]. Você não precisa do segredo do cliente OAuth para entrar.

1. Abra **[!UICONTROL Personalizações]**, selecione **[!UICONTROL Usuário]** e selecione **[!UICONTROL Conectores Externos]**. No cartão **[!UICONTROL Google Cloud Storage]**, selecione **[!UICONTROL Entrar]**.

   Antes de entrar, o cartão mostra **[!UICONTROL Não conectado]**. Se o cartão exibir **[!UICONTROL Não configurado]**, peça ao administrador [configurar o conector](#configure-organization).

1. Na tela [!DNL Google] **[!UICONTROL Escolher uma conta]**, selecione a conta que tem o acesso IAM necessário ou selecione **[!UICONTROL Usar outra conta]**. Conclua todas as etapas de logon necessárias para sua organização, como logon único (SSO) ou autenticação multifator (MFA).

   Essa conta pode ser diferente da conta usada para o Colaborador.

   ![Google Escolha uma tela de conta com contas redigidas e a opção Usar outra conta.](./assets/google-cloud-storage/member-choose-account.png){width="500" zoomable="yes"}

1. Se [!DNL Google] mostrar **[!UICONTROL a Google não verificou este aplicativo]**, confirme o aplicativo e seu proprietário com o administrador.

   Se sua organização aprovar o uso deste aplicativo, selecione **[!UICONTROL Continuar]**. Caso contrário, selecione **[!UICONTROL Voltar à segurança]** e peça ao proprietário do aplicativo para resolver os requisitos de público-alvo, publicação ou verificação.

   ![Tela do Google informando que o Google não verificou este aplicativo porque ele está sendo testado, com as opções Continuar e Voltar para segurança.](./assets/google-cloud-storage/member-unverified-app.png){width="500" zoomable="yes"}

   Revise o nome do aplicativo e o acesso solicitado na tela de consentimento e selecione **[!UICONTROL Continuar]**. O conector solicita **[!UICONTROL Exibir seus dados no Google Cloud Storage]**, que corresponde ao escopo somente leitura.

   Nas capturas de tela, o aplicativo é denominado adobe.io. O aplicativo de sua organização mostra seu próprio nome. Esse nome não significa que a Adobe fornece o aplicativo OAuth.

   >[!IMPORTANT]
   >
   >Continue apenas se você reconhecer o aplicativo e sua organização aprovar o acesso solicitado.

   ![Tela de consentimento da Google na qual um aplicativo de exemplo chamado adobe.io solicita acesso para exibir seus dados no Google Cloud Storage, com uma conta editada e os botões Cancelar e Continuar.](./assets/google-cloud-storage/member-consent.png){width="500" zoomable="yes"}

1. Retorne ao Colaborador e confirme se o logon foi concluído. Revise as **[!UICONTROL Ferramentas habilitadas pelo administrador]** nos detalhes do conector. Você pode usar somente as ferramentas que o administrador ativou.

Se a conexão for encerrada ou se a sessão expirar, entre novamente. Quando um administrador se conecta, os outros membros não se conectam.

## Verifique o acesso ao seu bucket {#check-bucket-access}

Um logon bem-sucedido ou uma lista de ferramentas não confirma se você pode acessar um bucket específico. [!DNL Google] não requer autenticação para listar as ferramentas do servidor. Para confirmar o acesso, inicie um novo chat e insira um prompt somente leitura. Substitua os espaços reservados por recursos aprovados.

Exemplo de prompts:

* &quot;Listar os buckets no projeto `YOUR_PROJECT_ID`.&quot;
* &quot;Liste até 25 objetos em `reports/` no compartimento `YOUR_BUCKET`. Verifique o tamanho e o tipo de conteúdo de `reports/example.txt`, depois leia seus primeiros 4096 bytes e resuma-os.&quot;

Confirme se o resultado inclui a categoria ou o objeto que você espera. Para listar objetos em prefixos aninhados, peça explicitamente uma listagem recursiva. Verifique os metadados do objeto antes de ler um objeto.

## Limites e tratamento de dados {#limits-data-handling}

Lembre-se dos seguintes limites e considerações de manuseio de dados ao usar o conector:

* **ID do Projeto:** Forneça uma ID de projeto em sua solicitação. O conector não pode listar projetos.
* **Prefixos:** os prefixos de objeto são nomes literais, não pastas reais. As listagens não são recursivas por padrão e retornam resultados em páginas.
* **Tamanho da página:** uma página de lista pode conter até 1.000 itens. Use um tamanho de página pequeno, como 25 a 100, e um prefixo estreito.
* **Tamanho do objeto:** O tamanho máximo do objeto para uma leitura é de 8 MiB. A leitura somente de parte de um objeto maior não ignora esse limite. O suporte para arquivos binários depende do modelo e do cliente.
* **Custos e cotas:** encargos de armazenamento, solicitação, recuperação e rede podem ser aplicados. [!DNL Google] também aplica cotas ao servidor MCP. Para obter mais informações, consulte [Cotas de MCP de armazenamento na nuvem](https://docs.cloud.google.com/storage/quotas#gcs-mcp).
* **Manuseio de dados**: o conteúdo, os nomes e os metadados personalizados do objeto entram em sua conversa com o Colaborador. Usar somente dados aprovados.
* **Logs de auditoria:** [!DNL Cloud Storage] leituras aparecem em [!DNL Cloud Audit Logs] somente quando os logs de Acesso a Dados aplicáveis estão habilitados.

O conector não pode carregar, substituir, criar ou excluir arquivos ou compartimentos. Ele também não pode salvar resumos em [!DNL Cloud Storage].

## Solução de problemas de acesso {#troubleshoot-access}

Se houver falha no logon ou no acesso, verifique o seguinte com o administrador:

| Problema | O que verificar |
| --- | --- |
| O cartão mostra **[!UICONTROL Não configurado]** | Salve a conexão da organização ativa. |
| `redirect_uri_mismatch` | Registre a **[!UICONTROL URL de redirecionamento]** exata da caixa de diálogo Colaborador no **[!UICONTROL Aplicativo Web]** cliente OAuth. |
| `invalid_client` | Verifique o tipo de cliente, a ID do cliente, o segredo do cliente e os segredos da organização selecionados. |
| `access_denied` ou um aviso de aplicativo não verificado | Verifique o público-alvo do aplicativo, a qualificação do usuário de teste e o status de verificação com o proprietário do aplicativo. Não aprove um aplicativo desconhecido. |
| HTTP 401 ou sua sessão foi encerrada | Entre novamente. |
| `mcp.tools.call` foi negado | Verifique a função de [!UICONTROL Usuário da Ferramenta MCP] e quaisquer políticas de negação IAM aplicáveis. |
| A listagem de buckets é negada, mas um bucket conhecido é legível | Verifique a permissão `storage.buckets.list` no projeto. Permissões de objeto por si só não permitem listar buckets em um projeto. |
| Os metadados do bucket foram negados | Verifique a permissão `storage.buckets.get`. |
| A listagem ou leitura do objeto foi negada | Verifique a função de [!UICONTROL Visualizador de Objetos de Armazenamento] no bucket e a conta do [!DNL Google] com a qual você entrou. |
| `SERVICE_DISABLED` | Habilite a API [!DNL Cloud Storage] no projeto chamado no erro. |
| HTTP 403 que requer faturamento | Verifique o faturamento do projeto que contém os buckets, incluindo o projeto em sua solicitação `list_buckets`. |
| `OutOfRange` em leitura | O objeto excede o limite de 8 MiB. Use uma alternativa aprovada fora deste conector. |
| Uma ferramenta está ausente | Verifique a seleção da ferramenta que o administrador salvou. As ferramentas obsoletas e de gravação não estão disponíveis. |
| Falha em uma solicitação de upload, substituição, criação ou exclusão | O conector é somente leitura e não oferece suporte a essas ações. |
