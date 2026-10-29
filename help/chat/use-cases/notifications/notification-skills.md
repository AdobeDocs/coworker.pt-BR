---
title: Habilidades de notificação
description: Saiba como revisar e gerenciar notificações com o Adobe CX Enterprise Coworker. Localize itens de ação, defina lembretes e escolha como você receberá as notificações.
role: Admin,User,Developer,Leader
level: Beginner
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 1%
---

# Habilidades de notificação {#notification-skills}

Use Habilidades de notificação no Adobe CX Enterprise Coworker para revisar notificações, identificar itens de ação e gerenciar preferências de notificação por meio de conversas. Trabalhe com as notificações que você já recebe no painel de notificações dos aplicativos da Adobe CX Enterprise.

Resuma notificações, encontre itens específicos e agrupe notificações repetidas em problemas distintos. Abra uma notificação em seu aplicativo, marque-a como lida ou não lida, ou defina um lembrete.

>[!AVAILABILITY]
>
>As habilidades de notificação estão disponíveis para todos os clientes com acesso ao Adobe CX Enterprise Coworker. Nenhuma configuração adicional é necessária para usar as habilidades.
>
>Para receber notificações em [!DNL Slack], sua organização deve ter um espaço de trabalho [!DNL Slack] conectado.

## Antes de começar {#before-you-begin}

Antes de começar, verifique se você tem:

* Acesso ao Adobe CX Enterprise Coworker.
* Acesso a um ou mais aplicativos do Adobe CX Enterprise que enviam notificações.
* Um espaço de trabalho [!DNL Slack] conectado para sua organização, se você quiser receber notificações em [!DNL Slack].

## Revisar e agir sobre as notificações {#review-and-act}

Comece com um resumo, depois refine sua solicitação e aja de acordo com uma notificação específica.

1. Abra o Bate-papo de Colaborador. Para obter instruções, consulte [Introdução ao Chat do Colaborador](/help/chat/ui-guide.md).
1. Insira uma solicitação na caixa **[!UICONTROL Pergunte qualquer coisa ao parceiro]** e selecione **[!UICONTROL Enviar]**. Por exemplo:

   *&quot;O que precisa de minha atenção hoje?&quot;*

1. Revise as notificações que exigem ação e as notificações fornecidas para conscientização.

   ![O Chat do Colaborador lista as notificações que precisam de ação em resposta a uma solicitação sobre o que precisa de atenção hoje.](./assets/review-needs-action.png)

1. Insira uma pergunta complementar para restringir os resultados. Por exemplo:

   *&quot;Dessas notificações, há falhas no Experience Platform que eu deveria saber?&quot;*

   ![O Chat de Colaborador refina os resultados da notificação em resposta a uma pergunta sobre falhas no Experience Platform.](./assets/refine-platform-failures.png)

1. Solicite detalhes sobre uma notificação ou abra-a em seu aplicativo para investigar.
1. Peça para marcar uma notificação como lida ou definir um lembrete. Por exemplo:

   *&quot;Lembre-me amanhã sobre o alerta de taxa de eventos de entrada de alta prioridade.&quot;*

   ![O Chat de Colaborador confirma um lembrete para amanhã depois de especificar qual alerta de taxa de eventos de entrada usar.](./assets/reminder-confirmation.png)

Continuar a conversa sem repetir o contexto de solicitações anteriores. Se sua solicitação puder ser aplicada a várias notificações, aplicativos ou configurações, responda à pergunta esclarecedora antes de continuar.

Você recebe uma solicitação de confirmação antes de uma alteração que se estende além da solicitação.

## Casos de uso aceitos {#supported-use-cases}

Use Habilidades de Notificação para revisar notificações enviadas a você, agir de acordo com elas e gerenciar como você as recebe.

>[!NOTE]
>
>As habilidades de notificação não enviam, compartilham ou excluem notificações.

### Identificar itens de ação {#identify-action-items}

Pergunte quais notificações exigem sua atenção nos aplicativos da Adobe CX Enterprise.

Exemplo de prompts:

* &quot;O que precisa de minha atenção hoje?&quot;
* &quot;Pegue-me.&quot;
* &quot;Algo pendente para mim?&quot;

### Resumir notificações {#summarize-notifications}

Solicite um resumo por um período de tempo ou um aplicativo. Analise os itens de ação separadamente das notificações fornecidas para fins de conscientização. As notificações repetidas são agrupadas em problemas distintos em vez de serem listadas individualmente.

Exemplo de prompts:

* &quot;Resumir minhas notificações da semana passada.&quot;
* &quot;Dê-me uma visão geral das minhas notificações do último dia.&quot;
* &quot;Resumir minhas notificações do Adobe Journey Optimizer.&quot;

![O Chat do Colaborador agrupa um resumo de notificação em itens que precisam de ação e itens fornecidos para reconhecimento.](./assets/notification-summary.png)

### Localizar notificações específicas {#find-specific-notifications}

Filtre notificações por critérios como status não lido, solicitações de aprovação, falhas, erros ou versões de produtos.

Exemplo de prompts:

* &quot;Mostrar apenas notificações não lidas.&quot;
* &quot;Mostre-me minhas solicitações de aprovação.&quot;
* &quot;Há algum alerta de falha crítica que eu deva saber?&quot;
* &quot;Mostrar notificações de versão do Experience Platform.&quot;

### Revisar detalhes da notificação {#review-notification-details}

Solicite os detalhes completos de uma notificação quando ela for enviada. Se várias notificações corresponderem à sua solicitação, especifique qual delas você quer dizer.

Exemplo de prompts:

* &quot;Conte-me mais sobre a notificação de jornada.&quot;
* &quot;O que esse alerta significa para mim?&quot;

### Agir nas notificações {#act-on-notifications}

Abra uma notificação em seu aplicativo, marque as notificações como lidas ou não lidas ou defina um lembrete. Escolha um lembrete para cinco minutos, 15 minutos, uma hora ou amanhã.

Exemplo de prompts:

* &quot;Marque essa notificação como lida.&quot;
* &quot;Marcar essa notificação como não lida.&quot;
* &quot;Lembre-me desta notificação em uma hora.&quot;
* &quot;Marcar todas as minhas notificações como lidas.&quot;

### Gerenciar preferências de notificação {#manage-notification-preferences}

Pergunte sobre as configurações atuais antes de alterar o modo como você recebe notificações. Especifique o aplicativo ou categoria de notificação que deseja atualizar.

| Preferência | Alterações disponíveis |
| --- | --- |
| Canais de entrega | Ative ou desative as notificações dentro do aplicativo, notificações por email ou [!DNL Slack] notificações para um aplicativo ou categoria. |
| Frequência de email | Escolha a entrega imediata de email ou um resumo diário ou semanal. |
| Prioridade de categoria | Escolha quais categorias de notificação têm alta prioridade. |
| Alertas pop-up | Escolha quais categorias de notificação exibem alertas pop-up. |

Exemplo de prompts:

* &quot;Quais são minhas configurações de notificação para o Adobe Journey Optimizer?&quot;
* &quot;Desabilitar [!DNL Slack] notificações para o Experience Platform.&quot;
* &quot;Mudar meu resumo diário para semanal.&quot;
* &quot;Silenciar notificações de atualização de versão.&quot;
* &quot;Enviar notificações do Adobe Journey Optimizer somente por email.&quot;

Se o Bate-papo com colegas de trabalho solicitar detalhes do agendamento, especifique o dia, a hora e o fuso horário para o resumo semanal.

![O Chat do Colaborador pergunta em qual dia o resumo semanal deve chegar, com guias adicionais de hora, fuso horário e revisão.](./assets/digest-schedule.png)

## Mais ajuda sobre este tópico {#more-help}

Use esses guias para começar a usar o Bate-papo com colegas de trabalho ou investigar a atividade de alerta do Experience Platform.

* [Introdução ao Chat do Colaborador](/help/chat/ui-guide.md)
* [Habilidades de alerta do cliente](/help/chat/use-cases/customer-alerts/customer-alerts.md)
