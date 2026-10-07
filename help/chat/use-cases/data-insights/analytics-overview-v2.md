---
title: Analisar dados do Customer Journey Analytics com o bate-papo do colega de trabalho
description: Saiba como usar o Adobe CX Enterprise Coworker Chat para analisar dados do Customer Journey Analytics, criar funis e descobrir onde os clientes chegam na jornada.
hold: true
product_v2:
  internal-label: CX Enterprise Coworker
feature_v2:
  internal-label: CX Enterprise Coworker
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '1944'
ht-degree: 1%
---

# Analisar dados com o Chat do colaborador

As informações nesta página fornecem uma visão geral do Adobe CX Enterprise Coworker Chat e como ele pode ajudar você a analisar os dados da sua organização.

O Bate-papo com colegas de trabalho permite que as equipes automatizem tarefas de produtos Adobe usando linguagem natural, transformando rapidamente ideias em ações com planejamento flexível, habilidades personalizáveis e execução inteligente. Para obter informações mais gerais sobre o Colaborador, consulte [visão geral do CX Enterprise Coworker](/help/home.md).

>[!VIDEO](https://video.tv.adobe.com/v/3503519/?learn=on&enablevpops)

## Como a análise de dados funciona

O Bate-papo com colegas de trabalho pode executar uma análise de dados avançada que antes só era possível no Analysis Workspace. O Chat de colaborador acessa dados de suas visualizações de dados do Customer Journey Analytics ou conjuntos de relatórios do Adobe Analytics, permitindo que você explore dados e obtenha respostas com prompts em linguagem natural.

O Chat do colega herda permissões do Customer Journey Analytics ou do Adobe Analytics. Você pode acessar somente as visualizações de dados, conjuntos de relatórios, dimensões, métricas e segmentos disponíveis no Analysis Workspace.

Ao criar uma visualização no bate-papo do Colaborador, você pode abri-la no Analysis Workspace a qualquer momento para obter mais controle manual.

## Respostas rápidas e trabalho profundo

Você pode usar o Bate-papo de colega de trabalho de duas maneiras, dependendo de quanta análise você precisa:

* **Respostas rápidas** - Faça uma pergunta direta em linguagem simples e obtenha uma resposta imediata. Usuários empresariais geralmente usam o Coworker Chat dessa maneira, e os analistas também o usam quando precisam de uma resposta rápida para uma parte interessada.
* **Trabalho profundo** - Tenha uma conversa estendida, em várias ocasiões, com o Chat do Colaborador para investigar um problema comercial, descartar causas e chegar a uma recomendação. Normalmente, os analistas usam essa abordagem para explorar os dados em profundidade antes de fazer uma recomendação.

## Iniciar análise no Chat do Colaborador

Comece descrevendo o que você deseja saber em linguagem simples. O Chat do colaborador planeja a análise, consulta suas visualizações de dados ou conjuntos de relatórios e cria visualizações e resumos.

Os seguintes casos de uso são agrupados pelo que você deseja realizar. Cada grupo lista as funções para as quais é mais adequado.

### Medir desempenho

**Recomendado para:** Analista, Usuário empresarial

| Caso de uso | Função |
| --- | --- |
| [Analisar dados do Customer Journey Analytics e do Adobe Analytics](/help/chat/use-cases/data-insights/analytics-chat.md)<p>![Analisar dados do Customer Journey Analytics e do Adobe Analytics](../../assets/coworker-funnel-response-card.png)</p> | Responde perguntas em linguagem natural sobre suas visualizações de dados ou conjuntos de relatórios, cria funis e outras visualizações e descobre onde os clientes chegam. É possível abrir qualquer visualização no Analysis Workspace para análise adicional.<p>**Prompt de exemplo:** &quot;Mostrar exibições de página dos últimos 30 dias&quot;</p><p>Para obter mais informações, consulte [Introdução à análise de dados com o Chat de Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).</p> |
| [Comparar desempenho](#skills-and-limitations) | Comparar métricas entre canais, períodos ou segmentos lado a lado.<p>**Exemplo de prompt:** &quot;Comparar receita por canal mês a mês&quot;</p><p>Para obter mais informações, consulte [Habilidades e limitações](#skills-and-limitations).</p> |
| [Meça o desempenho da campanha](/help/chat/use-cases/overview.md#data-insights) | Veja como as campanhas, os canais e as propriedades da Web foram executados em um determinado período.<p>**Prompt de exemplo:** &quot;Como foi o desempenho das campanhas da Web do Acrobat no mês passado?&quot;</p><p>Para obter mais informações, consulte [Insights de dados](/help/chat/use-cases/overview.md#data-insights) em casos de uso de Chat de Colaborador.</p> |
| [Analisar funis](#skills-and-limitations) | Percorra os funis de conversão de várias etapas e veja a devolução em cada estágio.<p>**Recomendado para:** analista</p><p>**Exemplo de prompt:** &quot;Oriente-me durante o check-out do funnel&quot;</p><p>Para obter mais informações, consulte [Habilidades e limitações](#skills-and-limitations).</p> |

### Descubra por que as métricas foram alteradas

**Recomendado para:** analista

| Caso de uso | Função |
| --- | --- |
| [Explorar tendências e causas básicas](/help/chat/use-cases/data-insights/root-cause-analysis.md)<p>![Explorar tendências e causas básicas](../../assets/data-validation-aa-cja/trend-line-card.png)</p> | Identifica tendências em seus dados do Customer Journey Analytics e do Adobe Analytics e os fatores que impulsionam alterações no desempenho, sem consultas manuais.<p>**Exemplo de prompt:** &quot;Por que as conversões caíram na semana passada?&quot;</p><p>Para obter mais informações, consulte [Customer Journey Analytics e Colaborador](/help/chat/use-cases/data-insights/root-cause-analysis.md).</p> |
| [Analisar tendências e causas operacionais](/help/chat/use-cases/overview.md#data-insights) | Consulte dados históricos de séries temporais para públicos, conjuntos de dados e jornadas e identifique o que causou uma alteração.<p>**Recomendado para:** Administrador, Analista</p><p>**Exemplo de prompt:** &quot;Mostrar tendências de tamanho de público nos últimos 90 dias&quot;</p><p>Para obter mais informações, consulte [Insights de dados](/help/chat/use-cases/overview.md#data-insights) em casos de uso de Chat de Colaborador.</p> |

### Preveja o desempenho futuro

**Recomendado para:** analista

| Caso de uso | Função |
| --- | --- |
| [Métricas de previsão](#skills-and-limitations) | Projete valores de métrica futuros a partir de dados históricos do Customer Journey Analytics ou do Adobe Analytics, por exemplo, se você estiver no caminho para atingir uma meta de receita.<p>**Exemplo de prompt:** &quot;Sessões de previsão para os próximos 30 dias&quot;</p><p>Para obter mais informações, consulte [Habilidades e limitações](#skills-and-limitations).</p> |

### Compartilhar insights com as partes interessadas

**Recomendado para:** Analista, Usuário empresarial

| Caso de uso | Função |
| --- | --- |
| [Criar resumos executivos e resumos de KPI](#skills-and-limitations) | Produzir resumos de desempenho, recomendações e resumos de slides prontos para as partes interessadas.<p>**Exemplo de prompt:** &quot;Dê-me um resumo executivo do mês passado&quot;</p><p>Para obter mais informações, consulte [Habilidades e limitações](#skills-and-limitations).</p> |

### Planejar sua implementação ou atualização

**Recomendado para:** Administrador

| Caso de uso | Função |
| --- | --- |
| [Planeje sua implementação](/help/chat/use-cases/data-insights/implementation-guide.md)<p>![Planeje sua implementação](../../assets/ui-guide-6.png)</p> | Cria um plano personalizado e passo a passo para implementar o Customer Journey Analytics, atualizar da Adobe Analytics ou configurar a coleção Content Analytics, Marketing Campaign Analytics ou Streaming de Mídia na Edge. Os planos incluem detalhes como proprietários, estimativas de esforço, dependências e etapas de validação.<p>**Exemplo de prompt:** &quot;Ajude-me a planejar minha implementação do Customer Journey Analytics&quot;</p><p>Para obter mais informações, consulte [Planejar a implementação com o Colaborador](/help/chat/use-cases/data-insights/implementation-guide.md).</p> |
| [Gerar uma lista de verificação de implementação](/help/chat/use-cases/data-insights/intelligent-checklist.md)<p>![Gerar uma lista de verificação de implementação](../../assets/data-validation-aa-cja/date-detail.png)</p> | Transforma seu plano de implementação do Customer Journey Analytics em uma lista de verificação em Projetos de colaboração, onde sua equipe pode atribuir etapas, rastrear status e adicionar portas de aprovação.<p>Para obter mais informações, consulte [Gerar uma lista de verificação de implementação com Projetos de Colaborador](/help/chat/use-cases/data-insights/intelligent-checklist.md).</p> |

### Confirme se os dados estão precisos

**Recomendado para:** Administrador

| Caso de uso | Função |
| --- | --- |
| [Validar dados ao atualizar do Adobe Analytics para o Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md)<p>![Validar dados ao atualizar do Adobe Analytics para o Customer Journey Analytics](../../assets/data-validation-aa-cja/trend-bar-card.png)</p> | Compara dimensões, métricas e tendências entre seus conjuntos de relatórios do Adobe Analytics e visualizações de dados do Customer Journey Analytics e, em seguida, recomenda correções para dar suporte à atualização.<p>**Recomendado para:** Administrador, Analista</p><p>**Prompt de exemplo:** &quot;Comparar meu conjunto de relatórios do AA com minha visualização de dados do CJA&quot;</p><p>Para obter mais informações, consulte [Validar dados com o Colaborador ao atualizar do Adobe Analytics para o Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md).</p> |
| [Validar a implementação de mídia de streaming](/help/chat/use-cases/data-insights/streaming-media-validation.md)<p>![Validar a implementação de mídia de streaming](../../assets/ui-guide-8.png)</p> | Verifica o fluxo de dados, o esquema, o conjunto de dados, a visualização de dados e os dados da sessão para confirmar se o rastreamento de mídia de transmissão está configurado e coletando os dados corretamente.<p>**Exemplo de prompt:** &quot;Qual é a integridade geral da minha implementação de mídia de streaming?&quot;</p><p>Para obter mais informações, consulte [Validar a implementação de mídia de streaming com o Colaborador](/help/chat/use-cases/data-insights/streaming-media-validation.md).</p> |
| [Validar a qualidade do conjunto de dados para o Customer Journey Analytics](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md)<p>![Validar a qualidade do conjunto de dados para o Customer Journey Analytics](../../assets/data-validation-aep/dataset-validation.png)</p> | Identifica os conjuntos de dados que alimentam seus relatórios do Customer Journey Analytics e, em seguida, verifica os esquemas, a qualidade da identidade e a qualidade do campo para que você possa resolver problemas antes de criar painéis.<p>Para obter mais informações, consulte [Validar dados do Customer Journey Analytics com a habilidade de validação de dados no Colaborador](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md).</p> |
| [Validar dados após assimilação no Experience Platform](/help/chat/use-cases/data-insights/data-validation-aep.md)<p>![Validar dados após assimilação no Experience Platform](../../assets/data-validation-aep/null-values.png)</p> | Executa verificações estatísticas e semânticas em conjuntos de dados e campos do Experience Platform para encontrar problemas de qualidade de dados, como valores inválidos ou problemas de mapeamento.<p>**Prompt de exemplo:** &quot;Validar a Amostra 1000 de Eletrônicos do conjunto de dados&quot;</p><p>Para obter mais informações, consulte [Validar os dados do Experience Platform com o Colaborador](/help/chat/use-cases/data-insights/data-validation-aep.md).</p> |

### Automatize análises repetidas

**Recomendado para:** analista

| Caso de uso | Função |
| --- | --- |
| [Criar habilidades personalizadas do Customer Journey Analytics](#skills-and-limitations) | Transforme uma análise que você repete em uma habilidade reutilizável que persiste entre as sessões.<p>**Exemplo de prompt:** &quot;Transformar esta análise semanal de receita em uma habilidade reutilizável&quot;</p><p>Para obter mais informações, consulte [Habilidades e limitações](#skills-and-limitations).</p> |

Para obter mais informações sobre esses casos de uso, incluindo as habilidades que eles usam e mais prompts de amostra, consulte [Casos de uso de insights de dados](/help/chat/use-cases/overview.md#data-insights).

## Habilidades e limitações

As habilidades a seguir estão disponíveis para analisar dados do Customer Journey Analytics ou Adobe Analytics.

| Habilidade | Use-o para | Permissões necessárias | Fora do escopo |
| --- | --- | --- | --- |
| `cja`, `aa` | Consulte as visualizações de dados do Customer Journey Analytics (`cja`) ou os conjuntos de relatórios do Adobe Analytics (`aa`) em tempo real:<ul><li>Extrair métricas, dimensões, segmentos, visualizações de dados e conjuntos de relatórios</li><li>Comparar canais, períodos de tempo ou segmentos lado a lado</li><li>Executar análise de fallout e funnel de várias etapas</li><li>Métricas de previsão baseadas em tendências históricas</li></ul> | Acesso de visualização à visualização de dados ou ao conjunto de relatórios que você deseja consultar | <ul><li>Criar ou editar componentes de visualização de dados ou de conjunto de relatórios</li><li>Dados fora das visualizações de dados ou conjuntos de relatórios aos quais você tem acesso</li><li>Modelagem preditiva além da previsão de métrica</li></ul> |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Investigue por que uma métrica mudou em vez de apenas relatar que mudou:<ul><li>Investigar uma alteração em uma métrica conhecida durante um período conhecido</li><li>Supervisione as dimensões e os segmentos que contribuíram para a alteração</li></ul> | Acesso de visualização à visualização de dados ou ao conjunto de relatórios que está sendo analisado | <ul><li>Detecção de anomalias sobre as quais você não perguntou (nenhum alerta automatizado ou em tempo real)</li><li>Análise de causa básica para métricas fora de uma visualização de dados ou conjunto de relatórios ao qual você tem acesso</li></ul> |
| `cja-executive-summary` | Produzir resumos dos seus dados prontos para as partes interessadas:<ul><li>Resumir o desempenho em um período especificado</li><li>Gerar recomendações prescritivas com base nos dados</li><li>Descrever o conteúdo de um conjunto de slides ou da leitura das partes interessadas</li></ul> | Visualizar o acesso às visualizações de dados ou conjuntos de relatórios abordados no resumo | <ul><li>Criação do conjunto de slides ou arquivo de apresentação final</li><li>Resumos que abrangem visualizações de dados ou conjuntos de relatórios aos quais você não tem acesso</li></ul> |
| `aa-cja-validation` | Comparar, auditar e reconciliar dados entre [!DNL Adobe Analytics] e o Customer Journey Analytics:<ul><li>Comparar valores de métrica entre um conjunto de relatórios e uma visualização de dados</li><li>Sinalizar discrepâncias entre as duas fontes de dados</li></ul> | Visualize o acesso ao conjunto de relatórios [!DNL Adobe Analytics] e a visualização de dados do Customer Journey Analytics sendo comparados | <ul><li>Resolução da causa subjacente de uma discrepância de dados</li><li>Validando fontes de dados diferentes de [!DNL Adobe Analytics] e Customer Journey Analytics</li></ul> |
| `cja-skill-creator` | Transforme uma análise que você já executou em uma habilidade reutilizável:<ul><li>Converter uma análise concluída em uma habilidade nomeada e reutilizável</li><li>Disponibilizar uma habilidade salva em suas futuras sessões de chat</li></ul> | Gerenciar habilidades | <ul><li>Compartilhar uma habilidade salva com outros usuários automaticamente (bibliotecas de habilidades no nível da organização exigem configuração de administrador)</li><li>Editar os componentes da visualização de dados ou do conjunto de relatórios que uma habilidade faz referência</li></ul> |

## Práticas recomendadas ao analisar dados com o Chat do colaborador

### Práticas recomendadas no nível da organização

* Nomeie um analista de sua organização como defensor do Colaborador.

* Crie uma biblioteca de prompts e habilidades verificadas que se correlacionam com os dados e componentes que estão disponíveis para os usuários.

* Crie uma ou mais habilidades que direcionam o Bate-papo com colegas de trabalho para usar somente os componentes que você deseja usar nas análises. Isso ajuda o Bate-papo com colegas de trabalho a fornecer aos usuários em sua organização os dados mais relevantes.

* Ensine os usuários sobre quando pedir uma resposta rápida ao bate-papo com colegas de trabalho, e não quando usá-la para um trabalho de reflexão profunda.

### Práticas recomendadas no nível do usuário

* Use o modo de plano.

  Esse modo é especialmente útil para tarefas complexas, mas também pode produzir melhores resultados para tarefas simples, pois permite que o Colaborador faça perguntas de acompanhamento antes de agir. Para obter mais informações, consulte [Modo de plano](/help/chat/ui-guide.md#plan-mode).

* Ao criar um prompt, seja o mais específico possível:

  * Nomeie as dimensões, as métricas e o intervalo de datas que deseja analisar.
  * Faça referência aos componentes pelo nome exato.
  * Especifique quaisquer segmentos, públicos, canais ou dispositivos que deseja incluir, excluir ou comparar.
  * Indique se deseja um tipo de visualização específico, como funnel, tendência ou tabela de coorte.
  * Peça as próximas etapas recomendadas se desejar que o Bate-papo com colegas de trabalho sugira perguntas de acompanhamento.
  * Solicitar um horizonte de previsão, como &quot;próximos 30 dias&quot;, ao projetar métricas.
  * Mencione qualquer hipótese que você já tenha, para que o Bate-papo com colegas de trabalho possa validá-la ou descartá-la.
  * Solicite as dimensões de contribuição se desejar um detalhamento de uma alteração de métrica.
  * Especifique o público-alvo para um resumo, como liderança ou a equipe de marketing, e solicite uma descrição do conjunto de slides se planeja apresentar os resultados.
  * Nomeie o conjunto de relatórios específico e a visualização de dados que deseja comparar ao validar os dados.
  * Conclua uma análise primeiro e peça ao bate-papo do colaborador para salvá-la como uma habilidade, dando a ela um nome claro e descritivo e observando com que frequência você planeja reutilizá-la.

* Adicione instruções padrão à memória do Chat do colega. Por exemplo, se você sempre usar dados das mesmas visualizações de dados ou conjuntos de relatórios, adicione esses dados à memória. Para obter mais informações, consulte [Adicionar uma visualização de dados ou preferência de conjunto de relatórios na Memória](/help/chat/use-cases/data-insights/analytics-chat.md#add-a-data-view-or-report-suite-preference-in-memory) na Introdução à análise de dados com o Chat de Colaborador.

## Próximas etapas

Para configurar o Chat do Colaborador e percorrer um exemplo funcional, consulte [Introdução à análise de dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).


