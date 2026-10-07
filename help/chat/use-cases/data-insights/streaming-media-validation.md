---
title: Valide a implementação de streaming de mídia com o Co-worker
description: Saiba como a habilidade de validação de mídia de transmissão do Coworker verifica a configuração, as sessões e os logs para confirmar se a implementação está sendo rastreada corretamente.
hold: true
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 0%
---

# Valide a implementação de mídia de transmissão com o Colaborador

O Adobe CX Enterprise Coworker inclui uma habilidade de validação de mídia de transmissão que verifica a implementação de mídia de transmissão do Adobe (Análise de vídeo e áudio) na Edge Network, alimentando o Customer Journey Analytics e/ou o Adobe Analytics. Em vez de fazer referência manual ao Assurance, à configuração do conjunto de dados, aos grupos de campos do esquema XDM, à configuração da Visualização de dados da Customer Journey Analytics e aos logs de rede brutos, você obtém um único relatório de validação.

Se estiver implementando ou solucionando problemas de rastreamento de transmissão de mídia, você pode usar essa habilidade para confirmar se a implementação está configurada corretamente, coletando dados conforme esperado e capturando o que pretendia rastrear, tudo em uma única conversa no Chat do colaborador.

>[!NOTE]
>
>Considere o seguinte:
>
>* Esta habilidade faz parte de um fluxo de trabalho opcional maior: etapas personalizadas de implementação ou atualização (consulte [Planejar sua implementação com o Colaborador](./implementation-guide.md)), Implementação (consulte [Gerar uma lista de verificação de implementação com Projetos de Colaborador](./intelligent-checklist.md)) e Validação (esta habilidade). Você não precisa usar todos os três estágios. Por exemplo, você pode validar a implementação da mídia de transmissão sem nunca gerar um plano ou uma lista de verificação.
>* Essa habilidade valida e diagnostica problemas. Ele não corrige sua configuração ou seus dados. Use suas descobertas para orientar sua própria correção.

Use esta habilidade para:

* Execute uma auditoria de configuração em sua sequência de dados, esquema XDM, conjunto de dados e Visualização de dados do Customer Journey Analytics, com o primeiro ponto de verificação corrompido sinalizado como a causa provável.

  Este recurso está atualmente com a Disponibilidade Limitada.

* Valide uma ID de sessão de vídeo específica e veja exatamente em qual salto, assimilação de conjunto de dados ou mapeamento de Customer Journey Analytics uma discrepância ocorreu.

* Valide uma sessão de um log Charles ou HAR carregado, ou uma lista de URLs mais simples, sem precisar de uma sessão do Assurance em tempo real.

  Este recurso está atualmente com a Disponibilidade Limitada.

* Obtenha uma verificação geral de integridade com um único prompt, nenhuma ID de sessão ou registro necessário, que acumula sua configuração e uma amostra de sessões recentes.

## Antes de começar

<!-- FLAG: General access prerequisite is inferred, not stated explicitly in source docs. Per-mode inputs (session ID, log file) are directly sourced from Functional Requirements. -->

### Informações necessárias

Para validar a implementação da mídia de transmissão, é necessário:

* Acesso ao Colaborador com os dados da Adobe Experience Platform e da Customer Journey Analytics de sua organização conectados.

* Para uma validação de ID de sessão, a ID de sessão de vídeo que você deseja verificar.

* Para uma validação baseada em log, um arquivo de log Charles ou HAR ou uma lista de URLs mais simples no formato .txt, .md ou .json.

Nenhuma entrada específica é necessária para uma auditoria de configuração ou uma verificação de integridade geral. O colaborador lê a configuração existente e faz a amostragem de sessões recentes automaticamente.

### Limitações

Antes de usar essa habilidade, lembre-se do seguinte:

* **Somente diagnóstico**: esta habilidade não corrige sua configuração ou seus dados. Identifica problemas; você faz a alteração.
* **Somente mídia de streaming**: esta habilidade abrange implementações de mídia de streaming na Edge Network. Os conjuntos de dados não relacionados à mídia e as implementações padrão da Web ou do aplicativo do Analytics são cobertos por outras habilidades de validação do colaborador.
* **Somente sob demanda**: esta habilidade não fornece monitoramento contínuo ou em tempo real. Execute-o quando quiser uma verificação, em vez de um alerta contínuo.
* **Nenhum rastreador interno**: esta habilidade não rastrea seu site ou aplicativo para você. Se você quiser validar a cobertura como rastreada, forneça saída de navegador rastreador ou headless como evidência.
* **Somente implementações do Edge Network**: caminhos de implementação herdados somente do Media SDK e do Analytics não são suportados.
* **Os recursos mais amplos ainda não estão incluídos**: validação de evento ao vivo e fluxo de pulsação, validação do manual do cliente ou do cenário, acúmulo do painel histórico de várias plataformas e validação de ativação downstream do Real-Time CDP ou do Adobe Journey Optimizer estão planejados para versões posteriores.

## Iniciar uma sessão de validação

1. Faça logon no Colaborador.

1. Selecione [!UICONTROL **Novo chat**].

1. No campo de texto, descreva o que deseja validar. Por exemplo:

   **Aviso**

   > Validar ID da sessão de vídeo #123.

   Sua solicitação é roteada para a habilidade Validação de mídia de streaming, que executa o modo de validação correspondente.

1. (Condicional) Se a habilidade precisar de mais informações, como uma ID de sessão ou um arquivo de registro, forneça-as quando solicitado.

## Escolha seu modo de validação

A habilidade Validação de mídia de transmissão inclui quatro modos.

### Auditoria de configuração

Este recurso está atualmente com a Disponibilidade Limitada.

Valide todo o fluxo do Adobe Experience Platform, desde a sequência de dados até a visualização de dados da Customer Journey Analytics, incluindo o esquema XDM, o conjunto de dados e quaisquer regras de Preparo de dados ou campos derivados do Customer Journey Analytics. O colaborador relata um scorecard de aprovação/falha por salto e sinaliza o primeiro ponto de verificação com falha como a causa provável.

Exemplo de prompts:

* Validar a configuração da mídia de transmissão para a visualização de dados, o conjunto de dados e a sequência de dados.
* Verificar minha configuração de streaming de mídia de ponta a ponta.
* A sequência de dados do meu Media Analytics está configurada corretamente para o Customer Journey Analytics?

### Validação da ID da sessão

Compare as linhas do conjunto de dados do Adobe Experience Platform com a Visualização de dados do Customer Journey Analytics para uma sessão de vídeo específica e aponte se uma lacuna é um problema de assimilação de conjunto de dados ou um problema de mapeamento do Customer Journey Analytics.

Exemplo de prompts:

* Validar ID da sessão de vídeo #123.
* Por que a sessão abc-123 não está sendo exibida no Customer Journey Analytics?
* Compare a sessão xyz entre o conjunto de dados e a Visualização de dados do Customer Journey Analytics.

### Validação baseada em log

Este recurso está atualmente com a Disponibilidade Limitada.

Valide uma sessão de um log Charles ou HAR que você fez upload ou de uma lista de URLs mais simples, sem precisar de uma sessão do Assurance em tempo real. O colega valida padrões de ponto de extremidade, códigos de resposta, sequenciamento de eventos e cadência de ping e estados que as verificações foram executadas com confiança total, confiança reduzida ou foram ignoradas.

Exemplo de prompts:

* Validar logs anexados de dados de mídia de transmissão.
* Verifique esse log Charles para a ID de sessão #456.
* Valide esta lista de URLs em relação aos pings de mídia esperados.

### Painel de validação

Obtenha uma verificação geral de integridade com um único prompt. O colaborador acumula a auditoria de configuração e uma verificação de sessão leve e amostrada em um status, e declara explicitamente que as verificações baseadas em log não foram executadas se nenhum log fosse fornecido.

Exemplo de prompts:

* Verifique os dados da mídia de transmissão.
* Fornecer um relatório sobre minha implementação de mídia de transmissão.
* Qual é a integridade da minha implementação de mídia de transmissão em geral?

## Revise os resultados

Cada modo retorna resultados em um formato adequado à sua validação.

**Resultados da auditoria de configuração**

Um scorecard de aprovação/falha por salto que abrange a sequência de dados, o esquema XDM, o conjunto de dados, a Visualização de dados do Customer Journey Analytics e o Preparo de dados ou regras de campos derivados. O Colaborador identifica o primeiro salto com falha como a causa raiz provável.

**Resultados da validação da ID de sessão**

Um resumo de relatórios somente no Customer Journey Analytics, incluindo a ID da sessão, os metadados do conteúdo, as contagens de linhas por tipo de evento, os valores da métrica principal e uma observação de integridade. Se houver uma lacuna, o Coworker identifica se isso aconteceu na assimilação do conjunto de dados ou na etapa de mapeamento do Customer Journey Analytics.

>[!NOTE]
>
>As IDs de sessão e os valores de identidade autenticados são excluídos de qualquer resumo exportado ou compartilhado por padrão.

**Resultados da validação com base em log**

Uma validação estrutural e de sequência do log carregado, abrangendo padrões de endpoint, códigos de resposta, ordem de evento e cadência de ping. Estados de colegas de trabalho que verificam foram executados com confiança total, que foram executados com confiança reduzida e que foram ignorados com base no fato de você ter fornecido uma captura de log completa ou uma lista de URLs mais simples.

**Resultados do painel**

Um único status consolidado chamado &quot;Configuração + Dados disponíveis&quot;, combinando seus resultados de auditoria de configuração com uma verificação de amostragem de sessões recentes. Colaboradores nomeiam quais sessões foram amostradas e afirmam explicitamente que as verificações baseadas em log não foram executadas porque nenhum log foi fornecido.

## Como a validação funciona

Cada modo mapeia para um mecanismo dedicado:

* **Mecanismo de Validação da Configuração**: lê a configuração da sequência de dados, do esquema XDM, do conjunto de dados e do Modo de Exibição de Dados do Customer Journey Analytics e a avalia em relação a um conjunto fixo de pontos de verificação.
* **Mecanismo de verificação cruzada de sessões**: com uma ID de sessão fornecida, o consulta seu conjunto de dados e o Customer Journey Analytics Data View, calcula a contagem e o tipo de linhas esperados para essa sessão e compara os resultados reais em cada salto.
* **Analisador de Log e Validador**: analisa o log carregado ou a lista de URLs, reconstrói a sequência de solicitações e o tempo e aplica verificações estruturais, de sequenciamento e de camada de rede.
* **Mecanismo de Agregação de Painel**: executa o Mecanismo de Validação da Configuração e uma execução de amostra do Mecanismo de Verificação Cruzada da Sessão, combinando-os em um único status quando você não fornece uma ID de sessão, um log ou um manual.
