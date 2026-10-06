---
description: Saiba como conectar sua conta do Marketo Engage a Campanhas do colega de trabalho para sincronizar listas inteligentes e estáticas do Marketo.
title: Conectar-se ao Marketo Engage
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%
---
# Conectar-se ao Marketo Engage {#marketo}

O Adobe Co-worker Campaigns permite conectar a conta do Marketo Engage para obter listas inteligentes e estáticas.

>[!PREREQUISITES]
>
>Para usar esse conector, primeiro você deve ter:
>
>* Uma conta ativa do Marketo Engage
>* Sua URL da instância **do Marketo**
>* Um [serviço personalizado](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/custom-services#custom-services-1) criado para Campanhas de Colaborador no Marketo, com sua [ID de Cliente e segredo de Cliente](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/authentication#creating-an-access-token) disponíveis

## Como se conectar

1. Na [página inicial de Campanhas do colega de trabalho](https://coworker-campaigns.experience.adobe.com/), clique em **Personalizar** e selecione **Conectores**.

   ![Campanhas do colega de trabalho deixaram a navegação com Personalizar expandido e Conectores destacados](./assets/marketo-1.png)

1. Clique em **Adicionar integração**.

   ![Botão Adicionar integração na tela Conectores](./assets/marketo-2.png)

   >[!NOTE]
   >
   >Se essa não for a primeira integração, o botão exibirá &quot;Adicionar conector&quot;.

1. Na linha Marketo, clique em **Conectar**.

   ![Mosaico do conector do Marketo com o botão Conectar](./assets/marketo-3.png)

1. Digite a **URL da instância**, a **ID do Cliente** e o **segredo do Cliente** do Marketo. Clique em **Conectar**.

   >[!NOTE]
   >
   >Você pode encontrar o URL da instância do Marketo na barra de endereços do navegador ao visualizar a página Meu Marketo.

   ![Caixa de diálogo Conectar o Marketo com campos para URL de instância, ID do Cliente e segredo do Cliente](./assets/marketo-4.png)

Após a conexão, o Marketo é exibido na lista de Conectores e pode ser selecionado ao vincular uma lista de contatos para sincronização no Marketo.

**Para desconectar:**

1. Na tela Conectores, encontre o bloco Marketo e clique em **Gerenciar**.

   ![Tela de conectores com o bloco Marketo mostrando um botão de status Conectado e Gerenciar](./assets/marketo-5.png)

1. Clique em **Desconectar** (não é necessário inserir novamente o segredo do cliente neste momento).

   ![Gerenciar caixa de diálogo do Marketo com campos de URL de instância e ID de Cliente e um botão Desconectar](./assets/marketo-6.png)

   >[!NOTE]
   >
   >Após a URL da instância ser adicionada pela primeira vez, o padrão é a URL do ponto de extremidade REST, terminando em `*.mktorest.com`.

1. Clique novamente em **Desconectar** para confirmar.

   ![Caixa de diálogo de confirmação de desconexão](./assets/marketo-7.png)
