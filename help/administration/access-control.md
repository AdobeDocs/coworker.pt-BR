---
title: Controle de Acesso para Colaborador
description: Saiba mais sobre o controle de acesso para o Adobe CX Enterprise Coworker e as permissões em produtos compatíveis da Adobe. Encontre controles de administrador e obtenha ajuda com o acesso.
last-substantial-update: 2026-11-04
level: beginner
role: Admin
jira: KT-22980
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 11db1488d950f39ccb8c8019f644e54e1f3b8fa6
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%
---
# Controle de acesso para colaborador {#access-control}

Use o controle de acesso do Adobe CX Enterprise Coworker para gerenciar quem pode usar o Colaborador e quais recursos ele pode usar.

>[!NOTE]
>
>Sua organização deve estar habilitada para que o Colaborador use esse recurso. Para obter mais informações, consulte a [Visão geral do Chat do Colaborador](https://experienceleague.adobe.com/pt-br/docs/coworker/content/chat/overview).

## Como o acesso é determinado {#how-access-is-determined}

O acesso do colaborador é controlado por uma configuração em toda a organização e substituições opcionais de usuários ou grupos. A configuração em toda a organização habilita ou desabilita o acesso de colaborador para os usuários em sua organização. O acesso é ativado para todos por padrão.

| Configuração | Como isso afeta o acesso |
| --- | --- |
| Configuração em toda a organização | Habilite o acesso de colaborador para todos ou desabilite-o para sua organização. |
| Substituição de usuário ou grupo de usuários | As substituições dão aos administradores controle sobre o acesso de colegas de trabalho para usuários ou grupos de usuários específicos. |
| Permissões de aplicativo compatíveis | Os controles de acesso do colaborador determinam se você pode acessar qualquer recurso geralmente disponível do colaborador. O Coworker herda suas permissões de usuário de aplicativos compatíveis com o Coworker e respeita as permissões que cada aplicativo já impõe. |


## Adicionar Administradores de colegas {#add-coworker-admins}

Um Administrador de parceiro é um usuário ao qual foi atribuído o **[!UICONTROL Administrador do produto]** ou o **[!UICONTROL Administrador do sistema]** para [!DNL Adobe Experience Platform] em [!DNL Adobe Admin Console].

Use este vídeo para saber como adicionar administradores de colegas.

>[!VIDEO](https://video.tv.adobe.com/v/3507045?captions=por_br&learn=on){transcript=true}

## Gerenciar acesso do usuário {#manage-user-access}

1. Abra a experiência do Colaborador. Para obter instruções, consulte [Entrar no Colaborador](/help/chat/ui-guide.md#sign-in).
2. Abra o menu de perfil e selecione **[!UICONTROL Configurações de administração]**.

   ![Página inicial do colega de trabalho com o controle de menu de perfil realçado.](./assets/access-control/coworker-home.png)

   ![Menu de perfil do colega de trabalho com configurações do Administrador realçadas.](./assets/access-control/admin-settings.png)

3. Selecione **[!UICONTROL Controle de acesso]**.

   ![Configurações de administrador com o cartão de controle de acesso realçado.](./assets/access-control/access-control.png)

   Use este vídeo para saber como gerenciar usuários do Colaborador.

   >[!VIDEO](https://video.tv.adobe.com/v/3507155?captions=por_br&learn=on){transcript=true}

4. No Colaborador, use **[!UICONTROL Usuários]** para gerenciar o acesso de indivíduos ou **[!UICONTROL Grupos de usuários]** para gerenciar o acesso do Colaborador para grupos de usuários. Uma configuração de grupo de usuários se aplica a seus membros.

   Os grupos de usuários de colegas de trabalho são separados de [!DNL Adobe Admin Console] grupos. A sincronização de grupos de usuários de [!DNL Adobe Admin Console] com o Colaborador será adicionada em breve.

   A lista Usuários inclui usuários em sua organização. O acesso de colaborador é ativado para esses usuários por padrão.

   * **Habilitado:** O usuário ou grupo de usuários está ativo.
   * **Desabilitado:** O usuário ou grupo de usuários está inativo.

   Quando o acesso para todos estiver desabilitado, ative **[!UICONTROL Permitir substituições]** e selecione **[!UICONTROL Adicionar substituição]** para adicionar usuários ou grupos que ainda devem ter acesso.

## Permissões em aplicativos do CX Enterprise compatíveis com colegas de trabalho {#permissions-in-compatible-applications}

Aplicativos CX Enterprise compatíveis com colegas de trabalho continuam a aplicar suas próprias permissões.

O colega respeita as permissões em aplicativos compatíveis. Por exemplo, se você não puder acessar um conjunto de dados em [!DNL Adobe Experience Platform], o Co-worker não poderá recuperar ou agir nesse conjunto de dados para você.

## Obter ajuda com o acesso {#get-help-with-access}

Se você não vir o [!UICONTROL Controle de acesso], contate o administrador do Adobe ou o representante da Adobe. Eles podem confirmar se o recurso está ativado para sua organização e se você tem acesso às configurações.

Se o acesso for negado, peça ao administrador para revisar o padrão em toda a organização e todas as configurações de usuário ou grupo. Para um aplicativo do CX Enterprise compatível com o Colaborador, peça que eles verifiquem as permissões gerenciadas separadamente para esse aplicativo.

## Mais ajuda sobre este tópico {#more-help}

Use esses recursos para obter mais informações sobre Colaborador e administração.

* [Visão geral do bate-papo com colegas de trabalho](/help/chat/overview.md)
* [Introdução ao Chat do Colaborador](/help/chat/ui-guide.md)
* [Gerenciar plug-ins e marketplaces](/help/customizations/plugins/manage-plugins-for-your-org.md)
