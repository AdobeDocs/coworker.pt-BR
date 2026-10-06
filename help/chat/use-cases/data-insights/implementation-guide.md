---
title: Planeje sua implementação do Customer Journey Analytics ou de mídia de transmissão com o colega
description: Saiba como as habilidades do guia de implementação do Colaborador transformam uma conversa de descoberta em um plano de implementação personalizado e ordenado com listas de verificação exportáveis.
hold: true
source-git-commit: 94cf399a48d13ee83c702804b50fdccd4baa9d71
workflow-type: tm+mt
source-wordcount: '1236'
ht-degree: 1%
---

# Planeje sua implementação com o Colaborador

O Colaborador inclui cinco habilidades de guia de implementação, uma para cada superfície de produto: Customer Journey Analytics, uma atualização do Adobe Analytics para o Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) e mídia de transmissão. Cada habilidade transforma uma breve conversa de descoberta em um plano de implementação personalizado com reconhecimento de dependência, completo com uma lista de verificação interativa e exportações prontas para uso, tudo em uma única conversa de bate-papo com colegas de trabalho.

Se você estiver criando ou migrando para qualquer um desses produtos, poderá usar essas habilidades para obter um plano ordenado e passo a passo, sem pesquisar manualmente os requisitos de implementação do Adobe ou criar um plano de projeto do zero.

>[!NOTE]
>
>Considere o seguinte:
>
>* Essas habilidades do guia de implementação fazem parte de um fluxo de trabalho opcional maior: Etapas de implementação personalizada ou de atualização (esses guias), Implementação (consulte [Gerar uma lista de verificação de implementação com Projetos de Colaborador](./intelligent-checklist.md)) e Validação (por exemplo, [Validar sua atualização do Adobe Analytics para o Customer Journey Analytics](./data-validation-aa-cja.md) ou [Validar sua implementação do Streaming de Mídia](./streaming-media-validation.md)). Você não precisa usar todos os três estágios. Por exemplo, você pode validar seus dados sem nunca gerar um plano ou uma lista de verificação.
>* Essas habilidades não acessam os sistemas Adobe nem fazem alterações. Eles ajudam a planejar a implementação. Eles não o executam ou verificam em relação a um locatário ativo.

Use essas habilidades para:

* Obtenha um plano personalizado e ordenado para configurar o Customer Journey Analytics do zero, incluindo proprietários, estimativas de esforço e dependências para cada etapa.

* Obtenha um plano de migração para atualizar do Adobe Analytics para o Customer Journey Analytics, incluindo mapeamento de paridade de recursos do Adobe Analytics, sequenciamento de preenchimento retroativo histórico e uma porta de validação antes de desativar o Adobe Analytics.

* Obtenha um plano guiado para implementar o Content Analytics (ACA), incluindo licenciamento, privacidade e escopo de PII, e o assistente de configuração guiado.

* Obtenha um plano de integração para o Marketing Campaign Analytics (MCA) que se adapta ao seu caminho de assimilação, independentemente de você usar conectores de origem do Adobe, seu próprio conjunto de dados ou uma abordagem híbrida.

* Obtenha um plano de implementação para a coleção de mídia de transmissão na Edge, incluindo a configuração da sequência de dados, a implementação de SDK/API por plataforma e o modelo de evento de mídia.

## Antes de começar

<!-- FLAG: Best guess, not confirmed by source docs. Requirements doc doesn't state explicit prerequisites for starting a discovery conversation — verify with skills-overview.md or SME before publishing. -->

### Informações necessárias

Para iniciar uma conversa sobre o guia de implementação, é necessário:

* Qual dos cinco caminhos de implementação se aplica a você: Customer Journey Analytics (novo), atualização do Adobe Analytics para Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) ou mídia de streaming.

* Detalhes básicos sobre seu ambiente atual, como se você tem uma implementação existente do Adobe Analytics, seu status de licenciamento ou seu caminho de assimilação de dados planejado. A conversa de descoberta solicita esses detalhes, mas tê-los prontos acelera o processo.

### Limitações

Antes de usar essas habilidades, lembre-se das seguintes limitações:

* **Somente planejamento**: essas habilidades não acessam seus sistemas Adobe nem fazem alterações. Eles não executam a implementação ou a verificam em relação a um locatário ativo.
* **Uma superfície de produto por habilidade**: cada habilidade abrange um único caminho de implementação. Se sua solicitação se aplica a uma superfície de produto diferente, a habilidade direciona você para a correta, em vez de responder diretamente.
* **Não é uma experiência de rastreamento de projeto por conta própria**: essas habilidades geram um plano e exportações, mas não acompanham o status, a colaboração ou as aprovações contínuas. Para acompanhar seu plano ao longo do tempo, transforme-o em um Projeto do parceiro usando um manual predefinido. Consulte [Gerar uma lista de verificação de implementação com Projetos de Colaborador](./intelligent-checklist.md).

## Iniciar uma sessão de planejamento de implementação

1. Faça logon no Colaborador.

1. Selecione [!UICONTROL **Novo chat**].

1. No campo de texto, descreva a implementação ou migração que deseja planejar. Por exemplo:

   **Aviso**

   > Ajude-me a planejar minha implementação do Customer Journey Analytics.

   Sua solicitação é roteada para a habilidade correspondente do guia de implementação, que inicia uma conversa de descoberta interativa.

1. (Condicional) Se a habilidade não puder determinar qual caminho de implementação se aplica a você, responda à pergunta esclarecedora que ela faz e, em seguida, continue.

## Escolha o caminho de implementação

Cada habilidade do guia de implementação abrange uma superfície de produto.

### Customer Journey Analytics

Obtenha um plano de implementação personalizado e ordenado para configurar o Customer Journey Analytics do zero, sem uma implantação existente do Adobe Analytics para migrar. Seu plano inclui proprietários, estimativas de esforço e dependências para cada etapa.

Exemplo de prompts:

* Ajude-me a planejar minha implementação do Customer Journey Analytics.
* Estou levantando o Customer Journey Analytics do zero. Crie um plano de implementação para mim.

### Atualização do Adobe Analytics para o Customer Journey Analytics

Obtenha um plano de migração que mapeie a paridade de recursos do Adobe Analytics para o Customer Journey Analytics, sequencie o preenchimento retroativo histórico e inclua uma validação e uma porta de execução paralela antes de desativar o Adobe Analytics.

Exemplo de prompts:

* Ajude-me a planejar minha atualização do Adobe Analytics para o Customer Journey Analytics.
* Crie um plano de migração do Adobe Analytics para o Customer Journey Analytics.

### Content Analytics (ACA)

Obtenha um plano guiado para implementar o Content Analytics (ACA), incluindo licenciamento, privacidade e escopo de PII, e o assistente de configuração guiado. Como a ACA não tem a cobertura DULE, CMK ou HIPAA, seu plano inclui etapas de marcação de privacidade.

Exemplo de prompts:

* Ajude-me a planejar minha implementação do Content Analytics.
* Crie um plano de implementação do ACA.

### Marketing Campaign Analytics (MCA)

Obtenha um plano de integração para o Marketing Campaign Analytics (MCA) Essentials que se adapta ao seu caminho de assimilação, independentemente de você usar conectores de origem do Adobe, seu próprio conjunto de dados ou uma abordagem híbrida, para que as etapas de mapeamento e alinhamento de dados do funnel correspondam ao seu ambiente.

Exemplo de prompts:

* Ajude-me a planejar minha implementação do Marketing Campaign Analytics.
* Crie um plano de integração do MCA usando meu próprio conjunto de dados.

### Mídia de transmissão

Obtenha um plano de implementação para a coleção de mídia de transmissão na Edge, abrangendo a configuração da sequência de dados, a implementação de SDK/API por plataforma e o modelo de evento de mídia, para que você instrumente corretamente as sessões, os pings e as conclusões de relatórios do Customer Journey Analytics e/ou Adobe Analytics.

Exemplo de prompts:

* Ajude-me a planejar minha implementação de mídia de streaming.
* Crie um plano para instrumentar a mídia de streaming no Edge.

## Revise os resultados

O colaborador retorna seu plano de implementação como uma lista de verificação interativa e um resumo na mesma conversa.

**Lista de verificação interativa**

Uma lista de verificação do HTML que agrupa as etapas de implementação em fases e marcos. Para cada etapa, a lista de verificação inclui:

* Uma estimativa de esforço
* Um proprietário principal e todos os proprietários de suporte
* Dependências permanentes em outras etapas
* Se a etapa pode ser ignorada
* Um link para a documentação relevante do Experience League ou developer.adobe.com

**Exportações**

Baixe seu plano no formato que se adapta ao seu fluxo de trabalho:

| Exportar | O que inclui |
| --- | --- |
| CSV | Uma lista simples de etapas |
| Jira-import CSV | Etapas formatadas com pontos de história, prioridade e rótulos para importação no Jira |
| WORKFRONT CSV | Etapas formatadas com durações e predecessores para importar para o Workfront |
| Markdown | Uma lista de verificação que você pode colar na documentação ou nos wikis |

**Resumo no chat**

Junto com a lista de verificação, o Colaborador fornece um resumo de três partes diretamente na conversa:

1. Uma visão geral do seu plano
1. A tabela de etapas completa
1. Links de download para cada exportação

## Como o plano é criado

Cada habilidade do guia de implementação segue o mesmo processo de quatro etapas:

* **Descoberta**: uma conversa em etapas faz de 5 a 9 conjuntos de perguntas, específicas ao seu caminho de implementação, para saber mais sobre seu ambiente e suas metas.
* **Computar**: um LLM determina quais etapas condicionais e substituições de dependência se aplicam às suas respostas. Ele não elabora o plano em si.
* **Montar e renderizar**: um processo determinístico resolve dependências entre etapas, ordena-as, calcula o caminho crítico (a cadeia mais longa de etapas dependentes), gera sua lista de verificação e exportações.
* **Entrega**: o parceiro fornece links de download e um resumo do seu plano no chat.

Essa combinação de descoberta guiada e montagem determinística significa que seu plano é gerado consistentemente a partir de suas respostas, em vez de ser escrito à mão livre.
