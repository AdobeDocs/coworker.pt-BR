---
title: Habilidades de alerta do cliente
description: Saiba como usar as Habilidades de alerta do cliente no CX Coworker para revisar, analisar e priorizar atividades de alerta por meio de conversas em linguagem natural.
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 4%
---

# Habilidades de alerta do cliente

>[!AVAILABILITY]
>
> As habilidades de alerta do cliente estão disponíveis para todos os clientes com acesso ao Adobe CX Enterprise Coworker.
>
> Para usar as Habilidades de alerta do cliente, você deve ter acesso aos alertas do Adobe Experience Platform e aos recursos associados a esses alertas.

Usar as habilidades de alerta do cliente no CX Coworker para transformar a atividade de alerta em um resumo operacional personalizado. Revise alertas recentes, identifique problemas de alta prioridade, entenda quais recursos são afetados e concentre esforços de investigação por meio de conversas em linguagem natural.

As habilidades de alerta do cliente ajudam você a mudar de sinais de alerta para insights acionáveis sem revisar manualmente visualizações de alertas ou correlacionar informações em várias interfaces. Comece com uma pergunta abrangente sobre a atividade de alerta recente e, em seguida, use perguntas de acompanhamento para identificar padrões de alerta recorrentes, analisar objetos afetados e se concentrar nos alertas que você possui.

Para obter informações sobre Alertas de clientes, consulte a [visão geral sobre Alertas de clientes](https://experienceleague.adobe.com/pt-br/docs/experience-platform/observability/alerts/overview).

## Pré-requisitos {#prerequisites}

Antes de começar, verifique se você tem:

- Acesso ao Adobe Experience Platform.
- Permissão para exibir alertas relevantes para sua organização.
- O plug-in CXO do Adobe instalado no CX Coworker.

Para obter instruções sobre como instalar plug-ins, consulte o [Guia da Interface do Usuário do Coworker](../../ui-guide.md).

## Usar habilidades de alerta do cliente {#use-customer-alert-skills}

Interaja com as habilidades de alerta do cliente por meio do CX Coworker usando solicitações em linguagem natural. Faça perguntas sobre atividades de alerta, assinaturas, tendências de alerta ou objetos afetados. Continue a conversa com perguntas de acompanhamento para refinar os resultados e concentrar sua análise.

Para usar as Habilidades de Alerta do Cliente:

1. Navegue até **[!UICONTROL CX Coworker]**.

1. Insira uma pergunta ou solicitação sobre seus alertas. Por exemplo:

   *&quot;Listar todos os alertas disparados nas últimas 24 horas?&quot;*

   ![A primeira pergunta feita no CX Coworker](./assets/alerts/initial-question.png)

1. Revise os resultados retornados pelas Habilidades de alerta do cliente.

   ![A tabela de resultados retornou da pergunta inicial.](./assets/alerts/results-table.png)

1. Refine os resultados com perguntas de acompanhamento. Por exemplo:

   *&quot;Mostre-me os três principais tipos de alertas disparados nas últimas 24 horas.&quot;*

   ![Resultados refinados mostrando os três principais tipos de alerta.](./assets/alerts/alert-types.png)

1. Continue a limitar o escopo até identificar os alertas, padrões ou objetos afetados que exigem atenção. Por exemplo:

   *&quot;Listar os 5 principais objetos que são afetados por alertas de alta severidade&quot;*

   ![Resultados refinados mostrando os cinco principais objetos afetados.](./assets/alerts/objects-impacted.png)

As Habilidades de alerta do cliente mantêm o contexto conversacional, permitindo que você avance da atividade de alerta para a investigação focada sem repetir solicitações anteriores.

## Casos de uso aceitos {#supported-use-cases}

Use as habilidades de alerta do cliente para monitorar a atividade operacional, investigar problemas e se concentrar nos alertas mais relevantes para sua função.

### Revisar atividade de alerta

Revise o status de alerta atual ou investigue a atividade de alerta histórica em um período específico.

Por exemplo:

- &quot;Quais alertas foram acionados nas últimas 24 horas?&quot;
- &quot;Mostrar alertas ativos dos últimos sete dias.&quot;

### Identificar padrões de alerta recorrentes

Revise o histórico de alertas para identificar os tipos de alertas que ocorrem com mais frequência em sua empresa. Em vez de revisar um grande número de eventos de alerta individuais, use as Habilidades de alerta do cliente para resumir padrões recorrentes e destacar áreas que podem exigir atenção.

Por exemplo:

- &quot;Mostrar os 3 principais tipos de alertas acionados.&quot;
- &quot;Quais tipos de alerta ocorreram com mais frequência neste mês?&quot;

### Concentre-se em questões de alta prioridade

Limite os resultados a um nível de gravidade específico para priorizar os esforços de investigação.

Por exemplo:

- &quot;Mostrar apenas alertas de alta severidade.&quot;
- &quot;Quais alertas críticos foram acionados esta semana?&quot;

### Entender o raio de impacto dos alertas

Identifique quais objetos são afetados com mais frequência e entenda onde a investigação deve começar.

As habilidades de alerta do cliente analisam a atividade de alerta e destacam os objetos associados a alertas recorrentes ou de alta gravidade, ajudando você a se concentrar nas áreas com maior impacto operacional.

Por exemplo:

- &quot;Quais são os 5 principais objetos afetados?&quot;
- &quot;Quais objetos estão associados aos alertas de mais alta severidade?&quot;

### Conectar tipos de alerta a objetos afetados

Entenda como a atividade de alerta afeta recursos específicos.

As habilidades de alerta do cliente conectam os objetos afetados aos tipos de alertas que os acionaram, ajudando a identificar padrões e determinar a provável origem de problemas operacionais.

Por exemplo:

- &quot;Quais tipos de alerta afetaram esse conjunto de dados com mais frequência?&quot;
- &quot;Mostrar a relação entre tipos de alerta e objetos afetados.&quot;
- &quot;Qual tipo de alerta afetou o objeto impactado com mais frequência?&quot;

### Foco em Meus Alertas

Analise os alertas nos quais você se inscreve e que são responsáveis pelo monitoramento.

Use a experiência do [!DNL My Alerts] para analisar atividades recentes, priorizar problemas de alta severidade e focalizar a análise operacional nos alertas mais relevantes para sua função.

Por exemplo:

- &quot;Mostre-me os alertas de alta severidade que eu assinar.&quot;
- &quot;Quais alertas de [!DNL My Alerts] foram acionados esta semana?&quot;
- &quot;Algum dos meus alertas cadastrados requer atenção?&quot;

### Gerenciar assinaturas de alerta

Revisar e gerenciar assinaturas de alerta por meio de conversas em idioma natural.

Por exemplo:

- &quot;Quais alertas eu assino?&quot;
- &quot;Assinar este alerta para mim.&quot;
- &quot;Remover minha assinatura deste alerta.&quot;

## Exemplo de prompts {#example-prompts}

Use os prompts a seguir como exemplos ao interagir com as Habilidades de alerta do cliente.

### Prompts de atividade de alerta

- O que aconteceu nas últimas 24 horas?
- &quot;Quais alertas foram acionados nas últimas 24 horas?&quot;
- &quot;Mostrar todos os alertas acionados esta semana.&quot;
- &quot;Tenho alertas ativos?&quot;

### Prompts de tendência de alerta

- &quot;Mostrar os 3 principais tipos de alertas acionados.&quot;
- &quot;Quais tipos de alerta ocorreram com mais frequência neste mês?&quot;
- &quot;Que padrões de alerta você vê nos últimos sete dias?&quot;

### Prompts de análise de gravidade

- &quot;Mostrar apenas alertas de alta severidade.&quot;
- &quot;Mostrar alertas críticos dos últimos 30 dias.&quot;
- &quot;Quais alertas de alta severidade ocorreram com mais frequência?&quot;

### Prompts da análise de impacto

- &quot;Quais são os 5 principais objetos afetados?&quot;
- &quot;Quais objetos estão associados à maioria dos alertas?&quot;
- &quot;Mostrar a relação entre tipos de alerta e objetos afetados.&quot;
- &quot;Qual tipo de alerta afetou o objeto impactado com mais frequência?&quot;

### Meus prompts de alertas

- &quot;Mostre-me os alertas de alta severidade que eu assinar.&quot;
- &quot;Quais alertas de [!DNL My Alerts] foram acionados esta semana?&quot;
- &quot;Algum dos meus alertas que assinei está ativo no momento?&quot;
- &quot;Algum dos meus alertas cadastrados requer atenção?&quot;

### Prompts de gerenciamento de assinaturas

- &quot;Quais alertas eu assino?&quot;
- &quot;Assinar este alerta para mim.&quot;
- &quot;Remover minha assinatura deste alerta.&quot;

## Próximas etapas {#next-steps}

Depois de ler este manual, você deve entender como usar as Habilidades de alerta do cliente no CX Coworker para revisar as atividades de alerta, analisar tendências de alerta, gerenciar assinaturas de alerta e investigar problemas operacionais por meio de conversas em linguagem natural.

Para obter mais informações sobre alertas, consulte a [Visão geral dos Alertas do cliente](https://experienceleague.adobe.com/pt-br/docs/experience-platform/observability/alerts/overview).
