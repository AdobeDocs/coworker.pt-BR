---
description: Saiba como conectar o Colaborador para equipes à sua conta da Salesforce para acessar seus clientes potenciais e contatos.
title: Conectar-se ao Salesforce
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: bd7454ee46cb1ee4ca8b7ae6ab07348a23854979
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%
---
# Conectar-se ao Salesforce {#salesforce}

O colega de trabalho para equipes permite conectar sua conta da Salesforce para acessar seus clientes potenciais e contatos.

>[!PREREQUISITES]
>
>Para usar esse conector, primeiro você deve ter:
>
>* Uma conta ativa do Salesforce
>* As seguintes permissões no Salesforce: `api`, `sobjects.Contact.read`, `sobjects.Campaign.read`, `sobjects.CampaignMember.read`
>* Sua URL da Instância do Salesforce, [ID do Cliente e segredo do Cliente](https://help.salesforce.com/s/articleView?id=xcloud.remoteaccess_oauth_client_credentials_flow.htm&type=5#:~:text=DESCRIPTION-,client_id,-The%20consumer%20key){target="_blank"} estão disponíveis

## Como se conectar

1. Na [Página inicial de colegas de trabalho das equipes](https://coworker-campaigns.experience.adobe.com/){target="_blank"}, clique em **Contexto** e selecione **Conectores**.

   ![Colaborador para equipes saiu da navegação com Contexto expandido e Conectores destacados](./assets/salesforce-1.png)

1. Clique em **Adicionar integração**.

   ![Botão Adicionar integração na tela Conectores](./assets/salesforce-2.png)

   >[!NOTE]
   >
   >Se essa não for a primeira integração, o botão exibirá &quot;Adicionar conector&quot;.

1. Na linha Salesforce, clique em **Conectar**.

   ![Mosaico do conector do Salesforce com o botão Conectar](./assets/salesforce-3.png)

1. Digite a **URL da instância**, a **ID do Cliente** e o **segredo do Cliente** do Salesforce. Clique em **Conectar**.

   >[!NOTE]
   >
   >* No Salesforce, ID do cliente = Chave do consumidor e Segredo do cliente = Segredo do consumidor.
   >
   >* Enquanto estiver na sua conta da Salesforce, você poderá encontrar a URL da Instância na barra de endereços do navegador ou navegando até **Configuração** > **Configurações da Empresa** > **Meu Domínio**.

   ![Caixa de diálogo Conectar o Salesforce com campos para URL de instância, ID do Cliente e segredo do Cliente](./assets/salesforce-4.png)

Após a conexão, o Salesforce é exibido na lista Conectores e pode ser selecionado ao vincular um cliente potencial ou lista de contatos para sincronização do Salesforce.

**Para desconectar:**

1. Na tela Conectores, encontre o bloco Salesforce e clique em **Gerenciar**.

   ![Tela Conectores mostrando o Salesforce conectado com o botão Gerenciar realçado](./assets/salesforce-5.png)

1. Clique em **Desconectar** (não é necessário inserir novamente o segredo do cliente neste momento).

   ![Caixa de diálogo Gerenciar Salesforce com o botão Desconectar realçado](./assets/salesforce-6.png)

1. Clique novamente em **Desconectar** para confirmar.

   ![Caixa de diálogo de confirmação para desconectar com o botão Desconectar realçado](./assets/salesforce-7.png)
