---
description: Conecte sua conta HubSpot a Campanhas de colega de trabalho usando uma chave de serviço para sincronizar listas de contatos e, em seguida, gerencie ou desconecte a integração a qualquer momento.
title: Conectar-se ao HubSpot
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%
---
# Conectar-se ao HubSpot {#hubspot}

O Adobe Co-worker Campaigns permite que você conecte sua conta HubSpot para obter listas de contatos.

>[!PREREQUISITES]
>
>Para usar esse conector, primeiro você deve ter:
>
>* Uma conta HubSpot ativa
>* Uma [chave de serviço](https://developers.hubspot.com/docs/apps/developer-platform/build-apps/authentication/account-service-keys#create-a-service-key) criada com os seguintes escopos adicionados: `crm.objects.contacts.read`, `crm.objects.leads.read`, `crm.schemas.contacts.read`, `crm.lists.read`, `crm.export`

## Como se conectar

1. Na [página inicial de Campanhas do colega de trabalho](https://coworker-campaigns.experience.adobe.com/), clique em **Personalizar** e selecione **Conectores**.

   ![Personalizar menu expandido na barra lateral com Conectores selecionados](./assets/hubspot-1.png)

1. Clique em **Adicionar integração**.

   ![Botão Adicionar integração na tela Conectores](./assets/hubspot-2.png)

   >[!NOTE]
   >
   >Se essa não for a primeira integração, o botão exibirá &quot;Adicionar conector&quot;.

1. Na linha HubSpot, clique em **Conectar**.

   ![Bloco HubSpot com o botão Conectar realçado](./assets/hubspot-3.png)

1. Um modal é exibido mostrando as permissões necessárias (listadas nos Pré-requisitos na parte superior deste artigo). Clique em **Continuar**.

1. Insira sua **Chave de serviço** do HubSpot e clique em **Conectar**.

   ![Caixa de diálogo Conectar HubSpot com o campo Chave de serviço e botão Conectar](./assets/hubspot-4.png)

Após a conexão, o HubSpot aparece na lista de Conectores e pode ser selecionado ao vincular uma lista de contatos para sincronização a partir do HubSpot.

**Para desconectar:**

1. Na tela Conectores, encontre o bloco HubSpot e clique em **Gerenciar**.

   ![Tela de conectores mostrando o HubSpot conectado com o botão Gerenciar realçado](./assets/hubspot-5.png)

1. Clique em **Desconectar** (não é necessário inserir novamente sua chave de serviço neste momento).

   ![Caixa de diálogo Gerenciar HubSpot com o botão Desconectar realçado](./assets/hubspot-6.png)

1. Clique novamente em **Desconectar** para confirmar.

   ![Caixa de diálogo de confirmação para desconectar com o botão Desconectar realçado](./assets/hubspot-7.png)
