---
title: Analisar dados do Analytics com o bate-papo do Adobe CX Enterprise Coworker
description: Use o Adobe CX Enterprise Coworker Chat para analisar dados do Customer Journey Analytics e do Adobe Analytics, encontrar causas raiz e abrir resultados no Analysis Workspace.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '1363'
ht-degree: 1%
---

# Analisar dados com o Chat do colaborador

As informações nesta página fornecem uma visão geral do Adobe CX Enterprise Coworker Chat e como ele pode ajudar você a analisar os dados da sua organização.

O Bate-papo com colegas de trabalho permite que as equipes automatizem tarefas de produtos Adobe usando linguagem natural, transformando rapidamente ideias em ações com planejamento flexível, habilidades personalizáveis e execução inteligente. Para obter informações mais gerais sobre o Colaborador, consulte [visão geral do CX Enterprise Coworker](/help/home.md).

## Como a análise de dados funciona

O Bate-papo com colegas de trabalho pode executar uma análise de dados avançada que antes só era possível no Analysis Workspace. O Chat de colaborador acessa dados de suas visualizações de dados do Customer Journey Analytics ou conjuntos de relatórios do Adobe Analytics, permitindo que você explore dados e obtenha respostas com prompts em linguagem natural.

O Chat do colega herda permissões do Customer Journey Analytics ou do Adobe Analytics. Você pode acessar somente as visualizações de dados, conjuntos de relatórios, dimensões, métricas e segmentos disponíveis no Analysis Workspace.

Ao criar uma visualização no bate-papo do Colaborador, você pode abri-la no Analysis Workspace a qualquer momento para obter mais controle manual. Consulte [Abrir uma visualização no Analysis Workspace](/help/chat/use-cases/data-insights/analytics-chat.md#open-a-visualization-in-analysis-workspace).

## Respostas rápidas e trabalho profundo

Você pode usar o Bate-papo de colega de trabalho de duas maneiras, dependendo de quanta análise você precisa:

* **Respostas rápidas** - Faça uma pergunta direta em linguagem simples e obtenha uma resposta imediata. Usuários empresariais geralmente usam o Coworker Chat dessa maneira, e os analistas também o usam quando precisam de uma resposta rápida para uma parte interessada.
* **Trabalho profundo** - Tenha uma conversa estendida, em várias ocasiões, com o Chat do Colaborador para investigar um problema comercial, descartar causas e chegar a uma recomendação. Normalmente, os analistas usam essa abordagem para explorar os dados em profundidade antes de fazer uma recomendação.

## Iniciar análise no Chat do Colaborador

Comece descrevendo o que você deseja saber em linguagem simples. O Chat do colaborador planeja a análise, consulta suas visualizações de dados ou conjuntos de relatórios e cria visualizações e resumos.

Os casos de uso a seguir são agrupados por domínio de análise. Cada domínio tem sua própria página com casos de uso, exemplos de prompts, pré-requisitos e as habilidades que usa.

| Domínio | O que você pode fazer | Melhor para |
| --- | --- | --- |
| [Implementação e administração inteligentes](/help/chat/use-cases/data-insights/data-governance-and-validation.md) | Configure, migre e gerencie sua implementação e verifique se você pode confiar nos dados por trás de cada resposta. | Administrador |
| [análise de Jornada](/help/chat/use-cases/data-insights/journey-analysis.md) | Descubra onde os clientes abandonam a jornada para conversão e por que, em canais, dispositivos e segmentos. | Analista, usuário empresarial |
| [Análise de público-alvo e segmento](/help/chat/use-cases/data-insights/audience-and-segment-analysis.md) | Entenda quais grupos de clientes se comportam de maneira diferente e como, para que você possa se concentrar nos mais importantes. | Analista, usuário empresarial |
| [Desempenho empresarial](/help/chat/use-cases/data-insights/business-performance.md) | Entenda como a empresa está se saindo, por que uma métrica foi movida, para onde se dirige e o que fazer em seguida. | Analista, usuário empresarial |
| [Desempenho do conteúdo](/help/chat/use-cases/data-insights/content-performance.md) | Entenda qual conteúdo ganha e por que, até os atributos de cada ativo, para que você possa investir no que funciona. | Usuário empresarial |
| [Medição e atribuição de marketing](/help/chat/use-cases/data-insights/marketing-measurement-and-attribution.md) | Entenda o impacto incremental de cada canal de marketing e campanha para que você possa alocar gastos para otimizar o ROI. | Analista, usuário empresarial |

## Habilidades e limitações

As habilidades a seguir estão disponíveis para analisar dados do Customer Journey Analytics ou Adobe Analytics.

| Habilidade | Use-o para | Permissões necessárias | Fora do escopo |
| --- | --- | --- | --- |
| `cja`, `aa` | Consulte as visualizações de dados do Customer Journey Analytics (`cja`) ou os conjuntos de relatórios do Adobe Analytics (`aa`) em tempo real:<ul><li>Extrair métricas, dimensões, segmentos, visualizações de dados e conjuntos de relatórios</li><li>Comparar canais, períodos de tempo ou segmentos lado a lado</li><li>Executar análise de fallout e funnel de várias etapas</li><li>Métricas de previsão baseadas em tendências históricas</li></ul> | Acesso de visualização à visualização de dados ou ao conjunto de relatórios que você deseja consultar | <ul><li>Criar ou editar componentes de visualização de dados ou de conjunto de relatórios</li><li>Dados fora das visualizações de dados ou conjuntos de relatórios aos quais você tem acesso</li><li>Modelagem preditiva além da previsão de métrica</li></ul> |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Investigue por que uma métrica mudou em vez de apenas relatar que mudou:<ul><li>Investigar uma alteração em uma métrica conhecida durante um período conhecido</li><li>Supervisione as dimensões e os segmentos que contribuíram para a alteração</li></ul> | Acesso de visualização à visualização de dados ou ao conjunto de relatórios que está sendo analisado | <ul><li>Detecção de anomalias sobre as quais você não perguntou (nenhum alerta automatizado ou em tempo real)</li><li>Análise de causa básica para métricas fora de uma visualização de dados ou conjunto de relatórios ao qual você tem acesso</li></ul> |
| `cja-executive-summary` | Produzir resumos dos seus dados prontos para as partes interessadas:<ul><li>Resumir o desempenho em um período especificado</li><li>Gerar recomendações prescritivas com base nos dados</li><li>Descrever o conteúdo de um conjunto de slides ou da leitura das partes interessadas</li></ul> | Visualizar o acesso às visualizações de dados ou conjuntos de relatórios abordados no resumo | <ul><li>Criação do conjunto de slides ou arquivo de apresentação final</li><li>Resumos que abrangem visualizações de dados ou conjuntos de relatórios aos quais você não tem acesso</li></ul> |
| `analyze-content`<br/>(Disponibilidade Limitada)<!-- FLAG: Confirm the Out of scope items with the PM. --> | Responda a perguntas gerais ou específicas sobre seu conteúdo usando os dados do Content Analytics no Customer Journey Analytics:<ul><li>Descubra o que os ativos e as experiências de melhor desempenho têm em comum</li><li>Vincular a exposição do conteúdo a conversões e receita</li><li>Comparar conteúdo entre canais e públicos</li></ul>Para obter mais informações, consulte [Fazer perguntas sobre o seu conteúdo](/help/chat/use-cases/data-insights/ask-content-questions.md). | Acesso de visualização a uma visualização de dados configurada para o Content Analytics | <ul><li>Instalação ou configuração do Content Analytics</li><li>Conteúdo que o Content Analytics não coleta</li><li>Conteúdo de mídia paga</li></ul> |
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

* Para configurar o Chat do Colaborador e percorrer um exemplo funcional, consulte [Introdução à análise de dados com o Chat do Colaborador](/help/chat/use-cases/data-insights/analytics-chat.md).
* Para ver todos os fluxos de trabalho do Chat do Colaborador e as habilidades por trás dele, consulte [Fluxos de trabalho do Chat do Colaborador](/help/chat/use-cases/workflows.md).


