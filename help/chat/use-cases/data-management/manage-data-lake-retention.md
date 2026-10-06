---
title: Gerenciar retenção de data lake
description: Saiba como usar o CX Coworker para identificar dados do evento de experiência que merecem ser otimizados, analisar o uso do conjunto de dados e o impacto da retenção e gerenciar as políticas de retenção do data lake.
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 1%
---
# Gerenciar retenção de data lake

Use o CX Coworker para entender o valor dos dados do Evento de experiência em sua sandbox e identificar os dados que podem se beneficiar da otimização. Você pode começar com uma solicitação ampla, como pedir ao Coworker para otimizar seus dados de sandbox ou limpar conjuntos de dados. O Colaborador usa o Agente de gerenciamento de dados para exibir conjuntos de dados que merecem ser investigados, analisar como ativamente um conjunto de dados é usado, modelar o impacto de um período de retenção e, quando apropriado, ajudar você a gerenciar sua política de retenção de data lake.

## Antes de começar {#before-you-begin}

Verifique se você está trabalhando na sandbox que contém os conjuntos de dados que deseja revisar. Você também precisa de acesso ao Agente de gerenciamento de dados e às permissões necessárias do Adobe Experience Platform. Consulte [pré-requisitos do Agente de Gerenciamento de Dados](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/agents/data-management#prerequisites).

## Otimizar dados em sua sandbox {#optimize-data-in-your-sandbox}

Use essas habilidades em conjunto como um workflow. Comece com uma meta ampla de gerenciamento de dados, como entender o valor dos dados ou otimizar os dados em sua sandbox. O Colaborador ajuda você a encontrar conjuntos de dados que merecem ser investigados, verificar como ativamente um conjunto de dados é usado, modelar o impacto de um possível período de retenção e, em seguida, definir, alterar ou remover uma política de retenção quando você estiver pronto para agir.

### Encontre dados que merecem ser otimizados {#find-data-worth-optimizing}

Para decidir por onde começar, peça ao Colaborador para identificar conjuntos de dados de Evento de experiência que merecem ser investigados. Você pode começar perguntando sobre o valor dos seus dados, a otimização de dados ou a limpeza do conjunto de dados. Use a habilidade Listar conjuntos de dados para revisar o tamanho do armazenamento, a contagem de linhas, o status de retenção existente e a ativação do perfil. Você pode filtrar os resultados por critérios como tamanho do conjunto de dados, contagem de linhas ou acesso recente para restringir a lista. A habilidade é somente leitura. O Colaborador retorna uma tabela que pode ser digitalizada e comparada, juntamente com visualizações que destacam conjuntos de dados por tamanho, contagem de linhas e idade dos dados.

![Resultados de colegas de trabalho mostrando conjuntos de dados de Evento de Experiência em uma tabela com armazenamento, contagem de linhas, informações de retenção e visualizações do tamanho do conjunto de dados e da idade dos dados.](../../assets/data-management/dataset-discovery-results.png)

Depois de restringir a lista, use a habilidade Analisar uso do conjunto de dados para descobrir como ativamente um conjunto de dados específico é usado.

Nem todos os conjuntos de dados não utilizados ou abandonados exibidos por essa habilidade são um bom candidato para uma política de retenção de data lake. Se precisar remover um conjunto de dados inteiro ou gerenciar dados em outro armazenamento do Experience Platform, consulte [Escolher o recurso de gerenciamento do ciclo de vida dos dados correto](https://experienceleague.adobe.com/en/docs/experience-platform/data-lifecycle/choose-a-capability). Antes de definir uma política de retenção de data lake, confirme se o conjunto de dados é um conjunto de dados de Evento de experiência.

Exemplo de prompts:

- &quot;Sinto que meus dados podem ser otimizados.&quot;
- &quot;Ajude-me a entender o valor dos meus dados.&quot;
- &quot;Otimizar meus dados de sandbox.&quot;
- &quot;Limpar meus conjuntos de dados de sandbox.&quot;
- &quot;Mostre-me meus maiores conjuntos de dados de eventos.&quot;
- &quot;Mostre-me conjuntos de dados com mais de 100 GB que não tenham o conjunto de retenção do data lake.&quot;
- &quot;Preciso remover cerca de 2 TB de dados. Por onde começar?&quot;
- &quot;Você pode me ajudar a encontrar dados órfãos, abandonados ou não utilizados?&quot;
- &quot;Priorize conjuntos de dados que não foram acessados nos últimos 90 dias.&quot;

### Verificar ativamente o uso de um conjunto de dados {#check-how-actively-a-dataset-is-used}

Antes de decidir se um conjunto de dados é um bom candidato para uma política de retenção de data lake, descubra como ativamente o conjunto de dados é usado. Use a habilidade Analisar uso do conjunto de dados para avaliar um conjunto de dados específico entre vários sinais de uso. Esses sinais incluem atividade de assimilação recente, atividade de consulta, estabilidade do esquema e se o conjunto de dados alimenta outros aplicativos do Adobe Experience Platform. A habilidade é somente leitura. O colaborador retorna um nível de uso geral, um detalhamento dos sinais e um resumo em linguagem simples do que eles indicam sobre o conjunto de dados.

<!-- TODO: Confirm the final usage-tier thresholds with engineering after the planned update from a 7-day to a 30-day analysis window is complete. Update this section with the final definitions before publishing. -->

>[!NOTE]
>
>As métricas mostradas têm como objetivo fornecer sinais úteis e podem não representar todos os fatores relevantes para sua decisão. Recomendamos revisar os detalhes disponíveis e aplicar seu contexto comercial antes de tomar uma ação.

![Análise de uso do conjunto de dados do colaborador mostrando a camada de uso, os sinais de uso individuais e um resumo da atividade do conjunto de dados.](../../assets/data-management/dataset-usage-analysis.png)

Exemplo de prompts:

- &quot;Quão ativamente meu conjunto de dados de Eventos da Web está sendo usado?&quot;

### Modelar o impacto de um período de retenção {#model-the-impact-of-a-retention-period}

Antes de se comprometer com um período de retenção específico, descubra quantos dados seriam mantidos ou removidos. Use a habilidade Analisar retenção do conjunto de dados para revisar as métricas de armazenamento de um conjunto de dados e a distribuição por idade de seus dados. Em seguida, ele usa essa distribuição para modelar a quantidade de dados que um período de retenção proposto manteria ou removeria. O colega de trabalho mostra o impacto estimado por contagem de linhas e tamanho de armazenamento.

![Colaborador comparando o número de linhas mantidas e removidas por períodos de retenção de 30, 60 e 90 dias.](../../assets/data-management/retention-period-comparison.png)

A habilidade é somente leitura. O colaborador retorna a idade dos dados e a análise de impacto diretamente na conversa, para que você possa comparar os resultados com as configurações de retenção atuais do conjunto de dados antes de decidir se deseja alterá-los.

Exemplo de prompts:

- &quot;Qual seria o impacto se eu definisse um período de retenção de 60 dias nesse conjunto de dados?&quot;

### Definir, alterar ou remover uma política de retenção {#set-change-or-remove-a-retention-policy}

>[!IMPORTANT]
>
>O período mínimo de retenção do data lake é de 30 dias. Não há suporte para períodos mais curtos.

Depois de decidir um período de retenção, use a habilidade Gerenciar retenção do conjunto de dados para definir, alterar ou remover uma política de retenção de data lake em um conjunto de dados. A habilidade mostra o impacto proposto antes da aplicação de qualquer alteração. A política é aplicada somente após a aprovação explícita da solicitação. A descrição da alteração desejada não a aplica.

![Colaborador mostrando a política de retenção de data lake proposta, seu impacto e a confirmação necessária antes que a alteração seja aplicada.](../../assets/data-management/retention-impact-preview.png)

Após confirmar uma política de retenção, pode levar algum tempo para que a alteração apareça na interface do usuário do Adobe Experience Platform. A política de retenção não exclui os dados expirados imediatamente. O trabalho de retenção inicial começa dentro de 24 horas após a aplicação da política. Após a execução inicial, um trabalho agendado avalia e exclui registros expirados a cada 30 dias. Consulte o [guia de retenção do conjunto de dados (TTL) do Evento de Experiência](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/experience-event-dataset-retention-ttl-guide) para obter mais informações sobre retenção e limpeza.

Cada alteração na política de retenção é registrada em uma trilha de auditoria, inclusive quando uma política é definida, alterada ou removida. A trilha de auditoria registra quem fez cada alteração, quando ela ocorreu e o que foi modificado. Você pode seguir o link fornecido pelo Colaborador para revisar esses eventos na guia Log de auditoria do conjunto de dados no Adobe Experience Platform. Para obter mais informações, consulte a [Visão geral dos logs de auditoria](https://experienceleague.adobe.com/pt-br/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview).

![Log de auditoria do Adobe Experience Platform mostrando uma atualização de política de retenção de data lake, incluindo carimbo de data/hora, usuário, conjunto de dados, ação e status.](../../assets/data-management/retention-audit-log.png)

Exemplo de prompts:

- &quot;Defina a retenção neste conjunto de dados para 60 dias.&quot;
- &quot;Remover a política de retenção neste conjunto de dados.&quot;

## Práticas recomendadas {#best-practices}

Lembre-se das seguintes práticas ao usar o Agente de gerenciamento de dados:

- **Comece com uma meta ampla.** Se você não souber qual conjunto de dados precisa de atenção, peça ao Coworker para ajudá-lo a entender o valor dos dados ou otimizá-los na sandbox. Use a habilidade Listar conjuntos de dados para identificar conjuntos de dados com sinais que sugerem uso baixo ou nenhum uso recente antes de analisar um conjunto de dados individual.
- **Revise a visualização do impacto antes de confirmar.** Analise o que seria mantido e removido antes de aprovar uma alteração de retenção.
- **Permitir que as alterações apareçam.** Depois de confirmar uma alteração de retenção no CX Coworker, aguarde um curto período para que a interface do usuário do Adobe Experience Platform reflita a alteração.

## Próximas etapas {#next-steps}

Para saber mais sobre as habilidades, escopo, comportamento e limitações do Agente de Gerenciamento de Dados, consulte a [visão geral do Agente de Gerenciamento de Dados](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/agents/data-management). Para obter mais informações sobre como as políticas de retenção de data lake funcionam no Adobe Experience Platform, consulte o [guia de retenção do conjunto de dados (TTL) de eventos de experiência](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/experience-event-dataset-retention-ttl-guide).
