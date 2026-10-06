---
description: Saiba como iniciar uma campanha, agendar quando ela sai e com que frequência e parar permanentemente uma campanha ao vivo que está enviando ativamente.
title: Iniciar e gerenciar uma campanha
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 2%
---
# Iniciar e gerenciar uma campanha {#launch-campaign}

Depois que a campanha for criada, saiba como iniciá-la, agendar quando ela for lançada e, se necessário, interrompê-la.

>[!AVAILABILITY]
>
>No momento, a campanha de lançamento está disponível apenas para usuários em regiões da América do Norte.

## Iniciar uma campanha

1. Na campanha concluída, clique em **Revisar e iniciar**.

   >[!NOTE]
   >
   >Se algo estiver faltando, uma caixa de diálogo será exibida, listando o que você precisa concluir. Faça as correções e selecione novamente **Revisar e iniciar**.

1. Depois que a campanha passa a verificação de preparação, a caixa de diálogo de inicialização é aberta, mostrando uma pré-visualização do email e do público-alvo.

1. Revise o agendamento mostrado na caixa de diálogo. Para alterá-la, use as opções de agendamento descritas em [Agendar quando uma campanha for iniciada](#schedule-when-a-campaign-launches) e, em seguida, clique em **Salvar**.

1. Clique em **Iniciar campanha** quando terminar.

>[!NOTE]
>
>- Uma campanha não pode ser iniciada com um público-alvo de amostra (não real), rascunhos de email que não foram revisados ou configurações de envio não definidas.
>
>- Se você agendar uma campanha, ainda poderá editá-la antes do seu lançamento. Não há necessidade de alternar para o modo de rascunho.

## Agendar o lançamento de uma campanha {#schedule-when-a-campaign-launches}

Ao iniciar uma campanha, você pode escolher exatamente quando ela será lançada: imediatamente, em uma data e hora futura específicas ou em um cronograma recorrente. Você também pode voltar mais tarde e alterar a programação de uma campanha que já foi iniciada ou programada.

### Pré-requisitos

A campanha deve estar pronta para ser iniciada (todas as configurações necessárias foram concluídas).

### Programar uma campanha no lançamento

1. Na campanha, clique em **Revisar e iniciar**.

1. Na caixa de diálogo de inicialização, escolha uma opção de programação:
   - **Agora**: a campanha começa a ser enviada imediatamente após o lançamento.
   - **Agendar uma vez**: escolha uma **Data de início** futura (data e hora juntas).
   - **Recorrente**: escolha uma **Frequência** (Diariamente, Semanalmente ou Mensalmente) e uma hora de início, depois defina o padrão de recorrência (consulte os campos abaixo).

1. Se a opção Recorrente estiver selecionada, escolha se a campanha termina **Nunca** ou **Em uma data** e escolha uma data final, se aplicável.

1. Confirme para iniciar a campanha com a programação selecionada.

### Editar uma programação existente

1. Abra a campanha e vá para as configurações.

1. Localize a seção programação e selecione o resumo da programação atual.

1. Atualize a programação usando as mesmas opções descritas acima.

1. Salve a alteração.

### Campos de entrada

| Campo | Descrição | Obrigatório? |
| --- | --- | --- |
| Modo de agendamento | Opção de Agora, Agendar uma vez ou Recorrente | Sim |
| Data inicial | Data e hora em que a campanha começa (modo Agendar uma vez) | Sim, para Agendar uma vez |
| Frequência | Diariamente, Semanalmente ou Mensalmente (modo Recorrente) | Sim, para Recorrente |
| Hora de início | Hora do dia que a campanha recorrente envia | Sim, para Recorrente |
| Dias da semana | Em quais dias a campanha se repete | Sim, para a frequência Semanal |
| Dia do mês | Em qual dia do mês a campanha se repete | Sim, para frequência Mensal |
| Encerrar campanha | Nunca ou em uma data final específica | Sim, para Recorrente |

### Itens a serem observados

- As campanhas recorrentes podem ser definidas para serem executadas indefinidamente ou até uma data final específica. Campanhas únicas e imediatas não têm uma opção de data de término, pois são executadas uma vez.
- A programação não é compatível com intervalos de repetição personalizados, como &quot;a cada 2 semanas&quot; ou &quot;a cada 3 dias&quot;. Também não oferece suporte para recorrência mensal relativa, como &quot;a segunda segunda-feira do mês&quot;.

## Interromper uma campanha {#stop-campaign}

Você pode interromper uma campanha que está enviando ativamente (uma campanha &quot;em tempo real&quot;) diretamente da página de detalhes da campanha.

>[!CAUTION]
>
>Interromper uma campanha é permanente. Os recipients param de avançar pela campanha imediatamente e a campanha não pode ser retomada ou reiniciada posteriormente. Para enviar novamente, você deve criar uma nova campanha e iniciá-la.

<!--

### Prerequisites

- [NEEDS INPUT - to confirm with engineer: does stopping a campaign require a specific role or permission, or can any user with campaign access do this?]

-->

### Como interromper uma campanha

1. Abra uma campanha que esteja ativa no momento.

1. No cabeçalho de detalhes da campanha, clique em **Parar Campanha**.

1. Clique em **Parar** para confirmar.
