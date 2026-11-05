---
title: Analisar as causas básicas com o Adobe Analytics e o Customer Journey Analytics
description: Use o Adobe CX Enterprise Coworker para investigar alterações de métrica, identificar dimensões e segmentos de contribuição e testar hipóteses no Adobe Analytics e no CJA.
feature: AI Tools
role: User
level: Beginner
doc-type: Feature Video
duration: 186
last-substantial-update: 2026-08-10T00:00:00.000Z
jira: KT-22082
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 7e096fc9cda2157c02501ee909a80bf4df9a2f32
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 0%
---

# Analisar causas raiz com [!DNL Adobe Analytics] e [!DNL Customer Journey Analytics]

Use o Adobe CX Enterprise Coworker Chat para investigar por que uma métrica mudou no Adobe Analytics ou no Customer Journey Analytics (CJA). O colega de trabalho analisa a alteração especificada, exibe as dimensões e os segmentos que contribuem e ajuda a testar as hipóteses usando linguagem natural.

## Usar dados do Customer Journey Analytics para análise de causa básica

O vídeo a seguir demonstra como o Coworker combina IA de conversação com o Customer Journey Analytics. Saiba como fazer perguntas em linguagem natural, visualizar resultados, identificar tendências significativas e descobrir fatores que impulsionam o desempenho sem criar consultas manuais.

>[!VIDEO](https://video.tv.adobe.com/v/3496856/?captions=por_br&learn=on&enablevpops)

### Pré-requisitos

Antes de começar:

1. **Ter acesso ao Chat do Colaborador e conectar ao Customer Journey Analytics.** Confirme se sua organização configurou a integração necessária.
1. **Ter acesso de visualização à visualização de dados do CJA que você deseja analisar.** O colaborador pode usar somente as visualizações de dados e os componentes disponíveis para você.
1. **Escolha a exibição de dados que contém a métrica e as dimensões relevantes.** Se você puder acessar várias visualizações de dados, nomeie aquela que deseja que o Colaborador use.
1. **Identifique a alteração que deseja investigar.** Especifique a métrica, o intervalo de datas e o período de comparação. Também é possível fornecer dimensões, segmentos ou uma hipótese para focalizar a análise.

### Solicitações de exemplo para o Customer Journey Analytics

Substitua o texto entre colchetes pelos nomes dos componentes e períodos da visualização de dados.

* No modo de exibição de dados **[nome da exibição de dados]**, por que a **[métrica]** foi alterada durante o **[intervalo de datas]** em comparação com o **[intervalo de datas de comparação]**? Detalhe a alteração por **[dimensão]** e mostre os segmentos que mais contribuíram.
* No modo de exibição de dados **[nome da exibição de dados]**, a **[dimensão ou segmento]** contribuiu para a diminuição da **[métrica]** do **[intervalo de datas A]** para o **[intervalo de datas B]**? Compare os valores de ambos os períodos e explique o que foi alterado.
* No modo de exibição de dados **[nome da exibição de dados]**, compare a **[métrica]** para o **[segmento A]** e o **[segmento B]** durante o **[intervalo de datas]**. Quais dimensões contribuíram mais para a diferença?
* Na exibição de dados do **[nome da exibição de dados]**, teste esta hipótese: **[declare sua hipótese]**. Analise a **[métrica]** para o **[intervalo de datas]** e mostre as dimensões ou os segmentos que oferecem suporte a ela ou não.

## Usar dados do Adobe Analytics para análise de causa básica

O colaborador pode investigar por que uma métrica foi alterada em um conjunto de relatórios do Adobe Analytics. Ele usa a habilidade `aa-root-cause-analysis` para analisar uma alteração especificada e identificar as dimensões e os segmentos que contribuíram com ela.

### Pré-requisitos

Antes de começar:

1. **Ter acesso ao Chat do Colaborador e conectar ao Adobe Analytics.** No Colaborador, vá para **Personalizações > Integrações** e confirme se a integração do `aa-mcp` está listada e conectada. Se não estiver disponível, peça ao administrador para verificar a configuração da organização. Consulte [Introdução à análise de dados com o Chat de Colaborador](https://experienceleague.adobe.com/pt-br/docs/coworker/content/chat/use-cases/data-insights/analytics-chat) para obter orientação sobre a configuração.
1. **Ter acesso de visualização ao conjunto de relatórios do Adobe Analytics que você deseja analisar.** O Colaborador herda suas permissões do Adobe Analytics e pode usar somente os conjuntos de relatórios e componentes disponíveis para você no Analysis Workspace.
1. **Escolha o conjunto de relatórios que contém os dados relevantes.** Se você puder acessar vários conjuntos de relatórios, nomeie o conjunto de relatórios que deseja que o Colaborador use.
1. **Identifique a alteração que deseja investigar.** Especifique a métrica e o período. Para uma análise mais focada, inclua um período de comparação, dimensões ou segmentos relevantes e qualquer hipótese que você deseja que o Colaborador teste.

### Solicitações de exemplo para o Adobe Analytics

Substitua o texto entre colchetes pelos nomes dos componentes e períodos de tempo do conjunto de relatórios.

* No conjunto de relatórios **[nome do conjunto de relatórios]**, por que a **[métrica]** foi alterada durante o **[intervalo de datas]** em comparação com o **[intervalo de datas de comparação]**? Detalhe a alteração por **[dimensão]** e mostre os segmentos que mais contribuíram.
* No conjunto de relatórios **[nome do conjunto de relatórios]**, a **[dimensão ou segmento]** contribuiu para a diminuição da **[métrica]** do **[intervalo de datas A]** para o **[intervalo de datas B]**? Compare os valores de ambos os períodos e explique o que foi alterado.
* No conjunto de relatórios **[nome do conjunto de relatórios]**, compare **[métrica]** para **[segmento A]** e **[segmento B]** durante o **[intervalo de datas]**. Quais dimensões contribuíram mais para a diferença?

## Recursos relacionados

* [Analisar dados com o Chat do Adobe CX Enterprise Coworker](https://experienceleague.adobe.com/pt-br/docs/coworker/content/chat/use-cases/data-insights/analytics-overview)
* [Introdução à análise de dados com o Chat de colaborador](https://experienceleague.adobe.com/pt-br/docs/coworker/content/chat/use-cases/data-insights/analytics-chat)
