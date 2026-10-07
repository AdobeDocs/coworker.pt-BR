---
title: Gerar uma lista de verificação de implementação em projetos de colaboração
description: Saiba como o Co-worker Projects gera uma lista de verificação de implementação pré-preenchida a partir do seu plano de Guias de implementação, com etapas que você pode atribuir e rastrear.
hold: true
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%
---

# Gerar uma lista de verificação de implementação com Projetos de colaboração

O Adobe CX Enterprise Coworker pode gerar um projeto de Lista de verificação de implementação em Projetos de cooperação, pré-preenchido com as etapas solicitadas do plano do guia de implementação para Customer Journey Analytics, uma atualização do Adobe Analytics para o Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) ou Mídia de transmissão. O Colaborador automatiza ou auxilia com o máximo de etapas tecnicamente possível, para que você e sua equipe tenham um único local rastreável para trabalhar na implementação.

Se você estiver liderando uma implementação, executando etapas técnicas ou precisar apenas de visibilidade do progresso, poderá usar essa lista de verificação para atribuir trabalho, acompanhar o status e colaborar com a sua equipe, sem sair do Co-Worker.

>[!NOTE]
>
>Considere o seguinte:
>
>* Este recurso faz parte de um fluxo de trabalho opcional maior: Etapas de implementação personalizada ou atualização (consulte [Planejar sua implementação com o Colaborador](./implementation-guide.md)), Implementação (esta lista de verificação) e Validação (por exemplo, [Validar sua atualização do Adobe Analytics para o Customer Journey Analytics](./data-validation-aa-cja.md) ou [Validar sua implementação de mídia de streaming](./streaming-media-validation.md)). Você não precisa usar todos os três estágios, mas gerar essa lista de verificação requer um plano de guia de implementação concluído.
>* As etapas que o Colaborador executa ou auxilia incluem automaticamente um sinal de confiança ou verificação. Revise essas etapas antes de marcá-las como concluídas — o Colaborador não apresenta resultados automatizados como fato verificado.

Use esta lista de verificação para:

* Inicie uma implementação ou migração com um conjunto ordenado e pré-preenchido de etapas para o caminho do seu produto, em vez de montar um plano manualmente.

* Verifique o status durante a implementação, incluindo o que está bloqueado e o que vem a seguir, sem perguntar diretamente ao líder da implementação.

* Planeje uma implementação de várias plataformas ou de várias regiões, em que as etapas sejam executadas em paralelo ou em fases, em vez de em uma única linha reta.

* Permitir que o Co-worker execute etapas diretamente, quando possível, como executar uma verificação de validação entre as configurações do Adobe Analytics e do Customer Journey Analytics.

* Apresente portas de aprovação para etapas que precisam ser aprovadas antes que sua equipe avance.


## Antes de começar

<!-- FLAG: Open question — release note confirms a "predefined playbook" transforms the guide plan into a Coworker Project, but it's unconfirmed whether Coworker runs that playbook automatically or the user has to trigger/follow it manually. Written below as if Coworker does it automatically; verify before publishing. Exact UI mechanics also unconfirmed since Coworker Projects platform documentation doesn't exist yet. -->

### Informações necessárias

Para gerar uma Lista de verificação de implementação, você precisa:

* Uma conversa concluída com o guia de implementação para o caminho do seu produto. Consulte [Planejar sua implementação com o Colaborador](./implementation-guide.md). O Colaborador transforma esse plano em um Projeto do Colaborador automaticamente, usando um manual predefinido — você não precisa exportar nada sozinho.

* Acesso aos Projetos de Colaborador na sua organização.

### Limitações

Antes de usar esse recurso, lembre-se do seguinte:

* **Não é proprietário do conteúdo do guia**: esse recurso consome planos das habilidades do guia de implementação. Ele não cria ou mantém esse conteúdo subjacente.
* **O comportamento de sincronização ainda não está totalmente definido**: a lista de verificação deve permanecer sincronizada com as atualizações do plano do guia de implementação, mas o mecanismo de sincronização exato ainda está sendo definido. Verifique manualmente se há atualizações de plano de guia se sua implementação abranger uma linha do tempo longa.
* **Requer Projetos de Colaborador**: esse recurso depende da plataforma Projetos de Colaborador estar disponível em sua organização.

## Gerar uma lista de verificação

<!-- FLAG: Best guess, not confirmed by source docs. Coworker Projects UI isn't documented in this repo yet — verify exact navigation and UI labels once available. -->

1. Faça logon no Colaborador.

1. Selecione [!UICONTROL **Projetos**] no painel de navegação.

1. Selecione [!UICONTROL **Novo projeto**] e selecione o manual predefinido que corresponde ao plano do guia de implementação.

   O colaborador transforma seu plano em um projeto pré-preenchido com as etapas ordenadas para seu caminho.

## Revise os resultados

O Colaborador gera a Lista de verificação de implementação como um projeto do Colaborador do qual você e sua equipe podem trabalhar.

**Exibição do projeto**

Seu projeto agrupa as etapas de implementação ordenadas do seu plano. Para cada etapa, é possível:

* Atribuir um proprietário
* Atualizar status, como em andamento ou concluído
* Marcar uma etapa como não aplicável ou ignorá-la se não se aplicar à sua implementação
* Adicione comentários e colabore com sua equipe
* Exigir aprovação antes que uma etapa seja considerada concluída, para etapas que precisam de aprovação

**Etapas automatizadas e assistidas**

Quando tecnicamente viável, o Colaborador executa ou auxilia com uma etapa diretamente, como configuração de exibição ou dados de status do Adobe Analytics ou do Customer Journey Analytics. Essas etapas incluem um sinal de confiança ou verificação, conforme descrito acima.

**Exportações**

Exporte sua lista de verificação ou seu progresso em nível de resumo para Jira, Workfront ou Excel, para que você possa dobrá-la em seu fluxo de trabalho de gerenciamento de projeto existente.

**Várias listas de verificação**

Se estiver gerenciando várias implementações simultâneas, como vários conjuntos de relatórios, regiões ou marcas, você pode manter vários projetos de Lista de verificação de implementação, em vez de ficar limitado a um.
