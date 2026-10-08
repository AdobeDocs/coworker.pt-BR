---
title: Integração de dados com o parceiro
description: Saiba como usar a habilidade de integração de dados no CX Coworker para integrar novas fontes de dados ao Adobe Experience Platform por meio de um fluxo de trabalho de conversação.
hide: true
source-git-commit: 8f7d5307b1928c052f020ca5e7aae3feee7af03e
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 2%
---

# Integrar dados com o colega

>[!AVAILABILITY]
>
>A habilidade de integração de dados está na versão beta. A documentação e a funcionalidade estão sujeitas a alterações.
>
>A habilidade de integração de dados está disponível para clientes com acesso ao Adobe CX Enterprise Coworker, onde também deve ser ativada para sua organização. <!-- VERIFY BEFORE PUBLISH: confirm exact permission/entitlement name with Umesh Gohil, PLAT-296546. -->

Use a habilidade de integração de dados no CX Coworker para integrar novos dados ao Adobe Experience Platform por meio de um único fluxo de trabalho de conversa. Em vez de navegar por várias telas para conectar uma origem e criar um esquema manualmente, descreva sua intenção e o Colaborador o orientará por meio da seleção da origem, qualidade dos dados, enriquecimento semântico, mapeamento do esquema, criação do esquema e criação do fluxo de dados.

<!-- VERIFY BEFORE PUBLISH: confirm the loaded skill name ("Onboard Data to Experience Platform") and the exact post-landing prompt/flow with Umesh Gohil once flag access is arranged. -->

## Pré-requisitos {#prerequisites}

Antes de começar, verifique se você tem:

- Acesso ao Adobe Experience Platform e à organização e sandbox apropriadas.
- Acesso ao Adobe CX Enterprise Coworker, com a habilidade de integração de dados ativada para sua organização.
- Permissão para criar esquemas no Adobe Experience Platform.

Para obter instruções sobre como instalar plug-ins, consulte o [Guia da Interface do Usuário do Coworker](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide).

## Usar a habilidade de integração de dados {#use-the-data-onboarding-skill}

Hoje, a Habilidade de integração de dados começa na criação de esquemas na interface do usuário do Experience Platform, o que abre o Co-worker com sua intenção já preenchida.

Para usar a habilidade de integração de dados:

1. No Adobe Experience Platform, navegue até **[!UICONTROL Esquemas]** e selecione **[!UICONTROL Criar esquema]**.
1. Na caixa de diálogo **[!UICONTROL Criar um esquema]**, selecione **[!UICONTROL Dados integrados com IA]** e **[!UICONTROL Selecionar]**.

   ![A caixa de diálogo Criar um esquema com a opção Integrar dados com IA selecionada.](./assets/data-onboarding-skill/create-a-schema-dialog.png)

1. O CX Coworker é aberto em uma nova guia do navegador com um prompt pré-preenchido da intenção de criação do esquema, de modo que não é necessário reafirmá-lo.
1. Escolha uma origem da qual integrar quando solicitado, por exemplo [!DNL Amazon S3], [!DNL Data Landing Zone], [!DNL Delta Share] ou [!DNL Marketo].

   <!-- VERIFY BEFORE PUBLISH: screenshot of the Coworker landing/session-start state does not exist yet anywhere. Capture once flag access is confirmed. -->

1. Continue a conversa com o Colaborador por meio de revisão da qualidade dos dados, enriquecimento semântico, mapeamento de esquemas e criação de esquemas, confirmando cada etapa à medida que você avança.

Para obter mais informações sobre como usar o CX Coworker, consulte o [Guia da Interface do Usuário do Colaborador](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide).

## Casos de uso aceitos {#supported-use-cases}

Explore as partes do fluxo de trabalho de integração e a habilidade de integração de dados ajuda a concluir.

### Selecionar e conectar uma origem

Em vez de localizar e configurar manualmente um conector de origem, descreva os dados que deseja trazer e deixe o Co-worker ajudar a identificar a origem correta.

### Revisar qualidade dos dados

O colaborador exibe sinais de qualidade de dados para a fonte selecionada antes de você confirmar em um esquema, para que você possa detectar problemas anteriormente no processo.

### Enriquecer dados semanticamente

O colaborador sugere significado semântico para campos de entrada, reduzindo o trabalho manual de mapear campos brutos para definições padrão.

### Mapear e criar um esquema

O colaborador mapeia os campos revisados para um esquema novo ou existente e o cria diretamente no Adobe Experience Platform como parte da mesma conversa.

### Criar um fluxo de dados

O colaborador conclui a integração criando o fluxo de dados necessário para trazer os dados de forma contínua.

## Próximas etapas {#next-steps}

Depois de ler este guia, você deve entender como iniciar a habilidade de integração de dados a partir da criação de esquema e o que ela ajuda a realizar no CX Coworker.

Para conhecer os cenários de procedimento e acesso/qualificação da interface do Experience Platform, consulte [Dados integrados com IA](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/schemas#data-onboarding-skill) no guia de esquemas da interface.
