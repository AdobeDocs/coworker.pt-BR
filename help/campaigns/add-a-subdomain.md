---
description: Descrição aqui.
title: Subdomínio
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: d36bbe844cff08b2c820418121dea794a7a347c2
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 4%
---
# Adicionar um subdomínio e remetentes {#subdomain-senders}

Um subdomínio é uma divisão do seu domínio que pode ser usada para isolar suas marcas ou vários tipos de tráfego (por exemplo, comunicações de marketing).

Vamos usar o domínio &quot;mybrand.com&quot;, usado para enviar comunicações de marketing. Nessa situação, é possível configurar um subdomínio específico:

* subdomínio &quot;marketing.mybrand.com&quot; para emails de prospecção.

Ao fazer isso, você ajudará a preservar a reputação do seu domínio e de outros subdomínios. Por exemplo, se o subdomínio &quot;marketing.mybrand.com&quot; acabasse sendo adicionado à lista de bloqueios de um provedor de serviços de Internet devido a práticas de entrega incorretas, isso evitaria que todo o domínio &quot;mybrand.com&quot; e qualquer outro subdomínio que você criasse fossem adicionados.

>[!IMPORTANT]
>
>Como parte da avaliação gratuita, há no máximo dois subdomínios permitidos.

## Como adicionar um subdomínio

1. Na parte inferior esquerda da navegação, clique no seu nome.

   CAPTURA DE TELA

1. Clique em **Configurações**.

   CAPTURA DE TELA

1. Em _Workspace_, selecione **Domínios e remetentes**.

   CAPTURA DE TELA

1. Clique em **Adicionar subdomínio**.

   CAPTURA DE TELA

1. Insira seu subdomínio e clique em **Avançar**.

   CAPTURA DE TELA

1. Clique no ícone de cópia PIC ao lado dos valores aplicáveis que você precisa adicionar ao seu provedor de DNS.

   CAPTURA DE TELA

   >[!NOTE]
   >
   >Se o seu provedor de DNS permitir o carregamento em massa dos campos, você poderá clicar em **Exportar CSV** para exportar todos os campos.

1. Quando terminar de inserir as informações em seu provedor de DNS, clique em **Adicionei estes registros** em Campanhas de Colaborador para continuar.

   CAPTURA DE TELA

   >[!NOTE]
   >
   >As alterações de DNS podem levar até 30 minutos para se propagarem. Se você vir um X vermelho em vez de uma verificação verde em qualquer uma das linhas, as Campanhas do colaborador verificarão a cada dois minutos até serem concluídas.

1. Quando todos os registros forem validados, uma tabela _Registro de validação_ será exibida na parte inferior da janela. Role para baixo, copie todos os valores listados e adicione-os ao seu provedor de DNS.

   CAPTURA DE TELA

1. Quando terminar, clique em **Adicionei este registro** (ou **estes registros** se houver vários) em Campanhas de Colaborador para continuar.

   CAPTURA DE TELA

1. Digite o nome do Remetente, o prefixo do Email, o nome para resposta e o email para resposta e clique em **Concluir e configurar**.

   CAPTURA DE TELA

1. O novo subdomínio aparece na lista. Seu status é _Em andamento_, pois pode levar de alguns minutos a duas horas para que o processo seja concluído.

   CAPTURA DE TELA

1. Quando o processo for concluído, o status será alterado para _Verificado_.

   CAPTURA DE TELA

## Como adicionar um remetente

Texto

