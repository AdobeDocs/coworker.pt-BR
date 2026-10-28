---
description: O colega de trabalho para equipes permite conectar e consultar tabelas do Catálogo de Unidades no espaço de trabalho de Databricks para criar e ativar públicos-alvo da campanha.
title: Conectar-se aos Databricks
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: bd7454ee46cb1ee4ca8b7ae6ab07348a23854979
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%
---
# Conectar-se aos Databricks {#databricks}

O colega de trabalho para equipes permite conectar e consultar tabelas do Catálogo de Unidades no espaço de trabalho de Databricks para criar e ativar públicos-alvo da campanha.

>[!PREREQUISITES]
>
>Para usar esse conector, primeiro você deve ter:
>
>* Uma conta ativa do Databricks
>* Seu host do Workspace Databricks, [caminho do warehouse SQL](https://docs.databricks.com/aws/en/compute/sql-warehouse/create){target="_blank"}, [token de acesso pessoal](https://learn.microsoft.com/en-us/azure/databricks/dev-tools/auth/pat){target="_blank"} e [Catálogos de Unidade](https://learn.microsoft.com/en-us/azure/databricks/discover/database-objects){target="_blank"} estão disponíveis.

## Como se conectar

1. Na [Página inicial de colegas de trabalho das equipes](https://coworker-campaigns.experience.adobe.com/){target="_blank"}, clique em **Contexto** e selecione **Conectores**.

   ![Colaborador para equipes saiu da navegação com Contexto expandido e Conectores destacados](./assets/databricks-1.png)

1. Clique em **Adicionar integração**.

   ![Botão Adicionar integração na tela Conectores](./assets/databricks-2.png)

   >[!NOTE]
   >
   >Se essa não for a primeira integração, o botão exibirá &quot;Adicionar conector&quot;.

1. Na linha Databricks, clique em **Conectar**.

   ![Mosaico do conector de Databricks com o botão Conectar](./assets/databricks-3.png)

1. Insira seus Databricks **Host do Workspace**, **Caminho do SQL warehouse**, **Token de acesso pessoal** e **Catálogos de unidade**. Clique em **Conectar**.

   >[!NOTE]
   >
   >Quando estiver na página inicial do Databricks, o host do Workspace poderá ser encontrado diretamente na barra de endereços do seu navegador. Para localizar todas as outras credenciais, consulte os links em **Pré-requisitos** na parte superior deste artigo.

   ![Caixa de diálogo Conectar Databricks com campos para host do Workspace, caminho de warehouse SQL, token de acesso pessoal e catálogos de Unity](./assets/databricks-4.png)

Após a conexão, os Databricks são exibidos na lista de Conectores.

**Para desconectar:**

1. Na tela Conectores, encontre o bloco Databricks e clique em **Gerenciar**.

1. Clique em **Desconectar** (não é necessário inserir novamente seu token de acesso Pessoal neste momento).

1. Clique novamente em **Desconectar** para confirmar.
