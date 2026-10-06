---
title: Validar dados do Adobe Analytics para Customer Journey Analytics
description: Saiba como os administradores do Analytics usam a habilidade de validação de dados do CX Enterprise Coworker para comparar os dados do Adobe Analytics e do Customer Journey Analytics durante a atualização.
feature: AI Tools
role: User
level: Intermediate
doc-type: Feature Video
duration:
last-substantial-update: 2026-08-10T00:00:00.000Z
jira: KT-22083
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1527'
ht-degree: 0%
---
# Validar dados com o Colaborador ao atualizar do Adobe Analytics para o Customer Journey Analytics

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as etapas de atualização recomendadas (recomendadas para a maioria das organizações) ou seguir as etapas geradas dinamicamente para sua organização com o Guia de atualização do Customer Journey Analytics. <ul><li>**Etapas de atualização recomendadas** (recomendado para a maioria das organizações)<p>Um conjunto de etapas que levam a uma implementação ideal do Customer Journey Analytics.</p><p>Para obter informações detalhadas, consulte [Atualizar do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations).</p></li><li>**Guia de Atualização do Customer Journey Analytics** (Etapas personalizadas adaptadas às necessidades específicas da sua organização)<p>Um novo guia de atualização está disponível e gera dinamicamente etapas de atualização personalizadas para sua organização e suas circunstâncias exclusivas.</p><p>Para acessar o guia pelo Customer Journey Analytics, selecione a guia **[!UICONTROL Workspace]** e clique em **[!UICONTROL Atualizar para o Customer Journey Analytics]** no painel esquerdo. Siga as instruções na tela.</p></li></ul>

O colaborador inclui uma habilidade de validação que permite validar dados ao atualizar do Adobe Analytics para o Customer Journey Analytics. A validação de dados é concluída em uma única conversa.

Essa habilidade compara automaticamente:

* Cada dimensão, métrica e tendência individualmente em implementações.

* Todos os conjuntos de relatórios do Adobe Analytics em relação a todas as visualizações de dados do Customer Journey Analytics.

Depois de fazer essas comparações, a habilidade gera insights e recomendações orientados por IA que você pode implementar para facilitar a atualização para o Customer Journey Analytics.

## Antes de começar

Para validar dados como parte da atualização, é necessário:

* O conjunto de relatórios do Adobe Analytics que você deseja validar.

* A visualização de dados do Customer Journey Analytics que contém os mesmos dados.

Você não precisa saber como a sua implementação foi arquitetada. A habilidade detecta automaticamente se a implementação do Customer Journey Analytics usa o Analytics Source Connector ou uma nova implementação do Experience Platform Web SDK.

>[!VIDEO](https://video.tv.adobe.com/v/3496846/?learn=on&enablevpops)

## Iniciar uma sessão de validação

1. Faça logon no Co-worker.

1. Selecione [!UICONTROL **Novo Chat**].

1. No campo de texto, solicite que o agente valide sua atualização do Adobe Analytics para o Customer Journey Analytics:

   **Aviso**

   > Ajude-me a validar a atualização de minha empresa do Adobe Analytics para o Customer Journey Analytics.

   Sua solicitação é roteada para a habilidade de validação de dados, que inicia um processo de configuração interativo.

1. Para cada pergunta no processo de configuração, selecione uma resposta e, em seguida, selecione [!UICONTROL **Enviar**].

   O processo de configuração inclui as perguntas da tabela abaixo.

   >[!NOTE]
   >
   >É possível alterar qualquer uma dessas seleções posteriormente na mesma conversa. Por exemplo, peça ao agente para alterar o conjunto de relatórios ou a visualização de dados, e o agente repete apenas as etapas necessárias para atualizar essa seleção, sem reiniciar todo o processo de configuração.

   | Pergunta | Contexto adicional |
   |---------|----------|
   | [!UICONTROL **Selecione sua empresa do Analytics**] | Esta é a sua empresa de logon na Adobe Analytics. |
   | [!UICONTROL **Selecione seu conjunto de relatórios**] <!--In the UI, recommend change to "Select your Adobe Analytics report suite"--> | Esse é o conjunto de relatórios no Adobe Analytics que contém os dados que você deseja validar em relação aos dados do Customer Journey Analytics. |
   | [!UICONTROL **Selecione sua visualização de dados do Customer Journey Analytics**] | Essa é a visualização de dados no Customer Journey Analytics que contém os mesmos dados que o conjunto de relatórios do Adobe Analytics selecionado. |

1. Revise o resumo da configuração para confirmar se você está validando os dados corretos antes de continuar.

   O resumo inclui a empresa, o conjunto de relatórios e a visualização de dados selecionados, juntamente com uma visualização das métricas e dimensões principais de cada sistema.

1. Continue com a seguinte seção, [Escolha os dados a serem validados](#choose-the-data-to-validate).

## Escolher os dados para validar

É possível validar métricas ou dimensões individuais, ou validar todas as métricas e dimensões incluídas no conjunto de relatórios e na visualização de dados.

1. Selecione entre as seguintes opções:

   | Opção de validação | Descrição |
   |---------|----------|
   | [!UICONTROL **Comparação de métrica única**] | Comparar a tendência de uma métrica entre o Adobe Analytics e o Customer Journey Analytics. Use-a quando quiser verificar rapidamente uma métrica específica, como exibições de página ou visitas. |
   | [!UICONTROL **Comparação de dimensões únicas**] | Compare o detalhamento de uma única dimensão entre o Adobe Analytics e o Customer Journey Analytics. Use isso quando suspeitar de uma diferença de mapeamento ou classificação para uma dimensão específica. |
   | [!UICONTROL **Auditoria completa do conjunto de relatórios e da visualização de dados**] | Compare até 40 métricas do Adobe Analytics e 20 dimensões com seus equivalentes do Customer Journey Analytics em uma única execução. Use-a quando quiser ter uma visão abrangente da integridade geral da sua atualização. |

1. Continue com a seguinte seção, [Revise a análise](#review-the-analysis).

## Revisar a análise

1. Selecione a guia [!UICONTROL **Taxa de correspondência geral**] para exibir uma porcentagem que indique a proximidade entre os dados do conjunto de relatórios do Adobe Analytics e os da exibição de dados do Customer Journey Analytics.

   Essa pontuação sempre aparece primeiro, antes de qualquer outro resultado. Ela pesa cada métrica comparada e dimensão igualmente para garantir que métricas de alto volume, como exibições de página, não distorçam a pontuação.

   Use a escala a seguir para interpretar a pontuação:

   | Pontuação | Classificação | O que significa |
   |---------|----------|----------|
   | 97%-100% | ![Quadrado verde](../../assets/data-validation-aa-cja/excellent-square.svg) [!UICONTROL Excelente] | Todas as propriedades são altamente alinhadas. Nenhuma ação necessária. |
   | 90% a 96% | ![Círculo amarelo](../../assets/data-validation-aa-cja/good-circle.svg) [!UICONTROL Bom] | Pequenas lacunas estão presentes. Monitore tendências e investigue se elas declinam. |
   | 75% a 89% | ![Círculo laranja](../../assets/data-validation-aa-cja/review-circle.svg) [!UICONTROL Revisão] | Existem lacunas significativas. Investigue as causas raiz antes de depender dos dados do Customer Journey Analytics. |
   | Menos de 75% | ![Círculo vermelho](../../assets/data-validation-aa-cja/critical-circle.svg) [!UICONTROL Ruim] | Desalinhamento significativo. Execute uma ação imediata antes de usar os dados do Customer Journey Analytics. |

1. Selecione a guia [!UICONTROL **Key insights**] para exibir duas a quatro caixas de texto explicativo curtas, cada uma resumindo uma descoberta da análise em uma única frase.

   As chamadas de retorno são codificadas por cores de acordo com a gravidade, para que você possa identificar primeiro os achados mais importantes.

1. Selecione a guia [!UICONTROL **Resumo**] para exibir as seguintes informações:

   * Totais do Adobe Analytics

   * Totais do Customer Journey Analytics

   * Variação total

   * Dias passados

     Reflete quantos dias no intervalo de datas se enquadram no status de variação [!UICONTROL **Aprovado**] descrito abaixo.

   * Dias críticos

     Reflete quantos dias no intervalo de datas estão no status de variação [!UICONTROL **Crítico**] descrito abaixo.

1. (Condicional) Ao fazer uma comparação de dimensão única ou de métrica única, selecione a guia [!UICONTROL **Tendência diária**] para exibir uma comparação lado a lado dos dados do Adobe Analytics e do Customer Journey Analytics.

   Para métricas, é um gráfico de linhas que compara a tendência diária.

   ![Guia de tendência diária mostrando um gráfico de linhas](../../assets/data-validation-aa-cja/trend-line.png)

   Para dimensões, é um gráfico de barras que compara os valores principais.

   ![Guia de tendência diária mostrando um gráfico de barras horizontal](../../assets/data-validation-aa-cja/trend-bar.png)

1. (Condicional) Ao fazer uma comparação de dimensão única ou de métrica única, selecione a guia [!UICONTROL **Detalhes da data**] para exibir as seguintes informações para cada métrica comparada ou valor de dimensão:

   * Data

   * Valor do Adobe Analytics

   * Valor do Customer Journey Analytics

   * Porcentagem de variação

   * Selo de status

   ![Guia de detalhes de data mostrando uma tabela de porcentagens de variação e selos de status](../../assets/data-validation-aa-cja/date-detail.png)

   As colunas de variação e status usam a seguinte escala:

   | Variância | Status | O que significa |
   |---------|----------|----------|
   | Menos de 3% | ![Marca de seleção verde](../../assets/data-validation-aa-cja/pass-check.svg) [!UICONTROL Aprovado] | Os dados estão bem alinhados. Nenhuma ação necessária. |
   | 3%-10% | ![Triângulo de aviso amarelo](../../assets/data-validation-aa-cja/flagged-warning.svg) [!UICONTROL Sinalizador] | Monitore a diferença e investigue se ela continua ou piora. |
   | Maior que 10% | ![Círculo vermelho](../../assets/data-validation-aa-cja/critical-circle.svg) [!UICONTROL Crítico] | Investigue imediatamente. Isso geralmente aponta para um esquema, assimilação ou problema de mapeamento. |

1. (Condicional) Ao executar um conjunto de relatórios completo e uma auditoria de visualização de dados, selecione a guia [!UICONTROL **Scorecard**] para exibir as seguintes informações:

   * Contagens de passagens

   * Contagens sinalizadas

   * Contagens críticas

   * Tabelas que listam as cinco principais métricas e dimensões correspondentes e as cinco mais baixas

1. Role para baixo na análise para visualizar padrões adicionais e problemas descobertos durante a análise, causas prováveis para esses padrões e ações sugeridas para resolver quaisquer discrepâncias de dados.

   >[!NOTE]
   >
   >Alguma variação é esperada e não indica um problema com sua atualização para o Customer Journey Analytics.

   Problemas comuns incluem:

   * O Adobe Analytics conta visitantes baseados em dispositivos, enquanto o Customer Journey Analytics conta pessoas, usando a compilação de identidade entre dispositivos.
   * O Adobe Analytics processa dados no momento da coleta, enquanto o Customer Journey Analytics processa dados no momento do relatório.
   * As definições de sessão são diferentes: as visitas do Adobe Analytics usam um tempo limite fixo, enquanto as sessões do Customer Journey Analytics são configuráveis.
   * O Adobe Analytics filtra bots por padrão, enquanto a filtragem de bot do Customer Journey Analytics é aceita.
   * O Adobe Analytics relata os valores ausentes como &quot;Não especificado&quot; ou &quot;Nenhum&quot;, enquanto o Customer Journey Analytics os relata como &quot;Nenhum valor&quot;.
   * Podem resultar diferenças de canal de marketing das regras de processamento do Adobe Analytics em comparação aos campos derivados do Customer Journey Analytics aplicados retroativamente.
   * Se os valores de Customer Journey Analytics forem consistentemente aproximadamente o dobro dos valores de Adobe Analytics em todas as métricas, isso geralmente indicará dados duplicados na visualização de dados, em vez de um efeito de identificação.

1. Verifique se as ações sugeridas são válidas e resolva-as no Adobe Experience Platform ou no Adobe Analytics.

1. (Opcional) Continue sua análise analisando outra métrica, analisando outra dimensão ou executando outro relatório de até 40 métricas e 20 dimensões, conforme descrito em [Escolha os dados que serão validados](#choose-the-data-to-validate).

   Não é necessário repetir o processo de configuração para fazer isso; as seleções de empresa, conjunto de relatórios e visualização de dados continuam durante toda a conversa.

1. Continue seguindo as [etapas de atualização recomendadas](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) ou as etapas de atualização geradas dinamicamente no Guia de Atualização do Customer Journey Analytics.

   Para acessar o Guia de Atualização do Customer Journey Analytics no Customer Journey Analytics, selecione a guia **[!UICONTROL Workspace]** e clique em **[!UICONTROL Atualizar para o Customer Journey Analytics]** no painel esquerdo. Siga as instruções na tela.

