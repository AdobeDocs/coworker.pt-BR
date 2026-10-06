---
description: Descrição
title: Conectar-se ao Salesforce
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 12ee914ed944c82694b9373f611e19cf040e2229
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%
---
# Conectar-se ao Salesforce {#salesforce}

O Adobe Co-worker Campaigns permite que você conecte sua conta da Salesforce para acessar seus leads e contatos.

>[!PREREQUISITES]
>
>Para usar esse conector, primeiro você deve ter:
>
>* Uma conta ativa do Salesforce
>* As seguintes permissões no Salesforce: `api`, `sobjects.Contact.read`, `sobjects.Campaign.read`, `sobjects.CampaignMember.read`
>* Sua URL da Instância do Salesforce, [ID do Cliente e segredo do Cliente](https://help.salesforce.com/s/articleView?id=xcloud.remoteaccess_oauth_client_credentials_flow.htm&type=5#:~:text=DESCRIPTION-,client_id,-The%20consumer%20key) estão disponíveis

## Como se conectar

1. Na [página inicial de Campanhas do colega de trabalho](https://coworker-campaigns.experience.adobe.com/), clique em **Personalizar** e selecione **Conectores**.

   ![Campanhas do colega de trabalho deixaram a navegação com Personalizar expandido e Conectores destacados](./assets/salesforce-1.png)

1. Clique em **Adicionar integração**.

   ![Botão Adicionar integração na tela Conectores](./assets/salesforce-2.png)

   >[!NOTE]
   >
   >Se essa não for a primeira integração, o botão exibirá &quot;Adicionar conector&quot;.

1. Na linha Salesforce, clique em **Conectar**.

   ![](./assets/salesforce-3.png)

1. Digite a **URL da instância**, a **ID do Cliente** e o **segredo do Cliente** do Salesforce. Clique em **Conectar**.

   >[!NOTE]
   >
   >* No Salesforce, ID do cliente = Chave do consumidor e Segredo do cliente = Segredo do consumidor.
   >
   >* Enquanto estiver na sua conta da Salesforce, você poderá encontrar a URL da Instância na barra de endereços do navegador ou navegando até **Configuração** > **Configurações da Empresa** > **Meu Domínio**.

   ![](./assets/salesforce-4.png)

Após a conexão, o Salesforce é exibido na lista Conectores e pode ser selecionado ao vincular um cliente potencial ou lista de contatos para sincronização do Salesforce.

**Para desconectar:**

1. Na tela Conectores, encontre o bloco Salesforce e clique em **Gerenciar**.

   ![](./assets/salesforce-5.png)

1. Clique em **Desconectar** (não é necessário inserir novamente o segredo do cliente neste momento).

   ![](./assets/salesforce-6.png)

1. Clique novamente em **Desconectar** para confirmar.

   ![](./assets/salesforce-7.png)
