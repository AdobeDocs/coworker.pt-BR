---
description: Saiba como o Co-worker para equipes anexa e preserva automaticamente metadados C2PA em imagens, desde a geração até a entrega de emails.
title: Metadados C2PA no Colaborador para equipes
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 7af4950080b8805d94062567bdf4075d1f57fc13
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 4%
---
# Metadados C2PA no Colaborador para equipes {#overview}

Novas leis estão surgindo em torno da transparência generativa da IA, e a Adobe está trabalhando para atender aos requisitos aplicáveis em todas as jurisdições. [Metadados C2PA](https://c2pa.org/) é a ferramenta de origem que o Adobe usa para atender aos requisitos dessas leis.

Os metadados C2PA são metadados duráveis e invisíveis que registram como um conteúdo foi criado ou editado. Ao gerar ou editar uma imagem com ferramentas de IA gerativas no Co-worker para equipes, os metadados do C2PA são anexados automaticamente a essa imagem. Nenhuma ação é necessária da sua parte.

## Metadados C2PA em campanhas de email {#c2pa-metadate-email}

As imagens enviadas em suas campanhas de email mantêm os metadados do C2PA intactos, para que os recipients possam verificar a origem e a autenticidade de qualquer imagem diretamente do email entregue.

## Ações que anexam metadados C2PA {#actions}

A tabela a seguir resume quando os metadados do C2PA são anexados, com base na ação de imagem executada na geração de imagem no Co-worker para equipes.

| Ação | Descrição | Metadados C2PA anexados? | Exemplo de caso de uso |
| --- | --- | --- | --- |
| **Gerar uma imagem** | Crie uma nova imagem a partir de um prompt de texto ou de uma imagem de referência, ou gere uma imagem semelhante a partir de uma imagem existente. | Sempre. A imagem é gerada por IA gerativa, de modo que sempre transporta metadados C2PA novos. | Uma imagem de banner para uma campanha de email é gerada a partir de um prompt de texto que descreve o visual desejado. |

## Tipos de conteúdo e seu escopo {#content-types}

* **Imagens**: Cobertas. Os metadados C2PA são anexados quando as imagens são geradas com IA gerativa e preservados por meio de operações de recorte, sobreposição de texto e sobreposição de imagem realizadas pela geração de imagens no Co-worker para equipes.
* **Texto**: não aplicável. Saídas somente texto no Coworker para equipes, como geração de cópia, tradução e sugestões de alinhamento de marca, não exigem metadados C2PA.

## O que acontece quando o conteúdo se move {#content-moves}

O colaborador para equipes preserva os metadados C2PA associados aos ativos de imagem compatíveis. Se uma imagem contiver metadados C2PA quando importada para o Colaborador para equipes, essas credenciais serão mantidas quando o ativo for usado no conteúdo da campanha gerado e em experiências de email de saída.

## Recursos adicionais {#resources}

* [Transparência do conteúdo de IA gerativa](https://experienceleague.adobe.com/pt-br/docs/cx-enterprise-ai/experience-cloud-ai/overview/content-transparency){target="_blank"}
* [Diretrizes do usuário da IA gerada da Adobe Experience Cloud](https://www.adobe.com/br/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html?lang=pt-BR){target="_blank"}
* [Medidas de proteção e limitações](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/content-management/generate-content/gs-generative#generative-guardrails){target="_blank"}
