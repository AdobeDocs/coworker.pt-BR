---
description: Colaborador de equipes permite conectar sua conta do Shopify para obter clientes e segmentos.
title: Conectar ao Shopify
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: bd7454ee46cb1ee4ca8b7ae6ab07348a23854979
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 0%
---
# Conectar ao Shopify {#shopify}

Colaborador de equipes permite conectar sua conta do Shopify para obter clientes e segmentos.

>[!PREREQUISITES]
>
>Para usar esse conector, primeiro você deve ter:
>
>* Uma conta ativa do Shopify
>* A seguinte permissão no Shopify: `read_customers`
>* Sua URL de armazenamento do Shopify e o [Token de acesso da API de administração](https://shopify.dev/docs/apps/build/authentication-authorization){target="_blank"} estão disponíveis

## Como se conectar

1. Na [Página inicial de colegas de trabalho das equipes](https://coworker-campaigns.experience.adobe.com/){target="_blank"}, clique em **Contexto** e selecione **Conectores**.

   ![Colaborador para equipes saiu da navegação com Contexto expandido e Conectores destacados](./assets/shopify-1.png)

1. Clique em **Adicionar integração**.

   ![Botão Adicionar integração na tela Conectores](./assets/shopify-2.png)

   >[!NOTE]
   >
   >Se essa não for a primeira integração, o botão exibirá &quot;Adicionar conector&quot;.

1. Na linha Shopify, clique em **Conectar**.

   ![Shopify bloco do conector com o botão Conectar](./assets/shopify-3.png)

1. Revise a permissão necessária e clique em **Continuar**.

   ![Shopify tela de revisão de permissão necessária com o botão Continuar](./assets/shopify-4.png)

1. Insira sua **URL de Armazenamento** do Shopify e o **Token de Acesso da API de Administração**. Clique em **Conectar**.

>[!NOTE]
>
>No Shopify, obtenha seu Token de Acesso da API de Administração via **Configurações** › **Aplicativos** › **Desenvolver aplicativos** › **Criar aplicativo personalizado herdado** › **Configuração da API de Administração** › **Adicionar escopos necessários**.

![Caixa de diálogo Conectar Shopify com campos para URL de Armazenamento e Token de Acesso da API de Administrador](./assets/shopify-5.png)

Após a conexão, Shopify é exibido na lista Connectors.

**Para desconectar:**

1. Na tela Conectores, encontre o bloco Shopify e clique em **Gerenciar**.

1. Clique em **Desconectar** (não é necessário inserir novamente o token de acesso da API de administração neste momento).

1. Clique novamente em **Desconectar** para confirmar.
