---
title: Visão geral do Adobe CX Coworker Gateway
description: O Adobe CX Coworker Gateway é o MCP unificado para Adobe CX Enterprise, oferecendo aos clientes de MCP uma única conexão com as ferramentas de produto compatíveis.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 3%
---
# Adobe CX Coworker Gateway {#mcp-overview}

O Adobe CX Coworker Gateway é o Protocolo de Contexto de Modelo unificado (MCP) do Adobe CX Enterprise. Com uma conexão, os clientes compatíveis com MCP podem acessar as ferramentas de produto do Adobe que sua organização e conta têm direito a usar.

>[!IMPORTANT]
>
>Sua organização da Adobe deve estar habilitada para que você possa usar as ferramentas do **CX Coworker Gateway**.
>
>Se sua organização ainda não tiver acesso, envie um email para [cx-coworker-gateway-support@adobe.com](mailto:cx-coworker-gateway-support@adobe.com) para solicitar a ativação para sua organização.

Use o endpoint do CX Coworker Gateway para todas as configurações de cliente MCP:

```
https://cx-coworker-gateway.adobe.io/mcp
```

Após se conectar, o endpoint expõe as ferramentas disponíveis para sua organização e credenciais da Adobe. As páginas específicas do produto neste guia descrevem o que cada ferramenta de produto pode fazer, quais dados pode acessar e quaisquer limitações específicas do produto.

## O que é o protocolo de contexto de modelo? {#mcp-what-is}

O MCP (Model Context Protocol) é um padrão de código aberto para conectar aplicativos de IA a sistemas externos. Os clientes compatíveis com MCP, como [!DNL Claude], [!DNL ChatGPT], [!DNL Cursor], [!DNL Claude Code], [!DNL Codex] e [!DNL VS Code], podem usar essas ferramentas para recuperar o contexto do produto, executar operações com suporte e retornar respostas em linguagem natural.

O CX Coworker Gateway fornece um endpoint controlado para ferramentas de produto do CX Coworker Gateway. Em vez de adicionar servidores de produtos separados, conecte-se uma vez ao endpoint e use as ferramentas de produto exibidas para suas soluções qualificadas.

## Ferramentas de produto disponíveis {#available-product-tools}

As seguintes ferramentas de produto estão documentadas neste guia:


| Ferramentas do produto | O que ele expõe por meio do endpoint | Disponibilidade | Documentação |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Real-Time CDP** | Públicos, destinos, origens, namespaces de identidade e integridade da ativação (somente leitura) | Beta | [Ferramentas do Real-Time CDP](rtcdp-mcp.md) |
| **Experience Platform** | Esquemas, conjuntos de dados, governança de dados, Serviço de consulta, eventos de auditoria, métricas de observabilidade e avaliações de verificação de integridade da sandbox (somente leitura) | Beta | [Ferramentas do Experience Platform](aep-mcp.md) |
| **Journey Optimizer** | Campanhas, jornadas e configurações de canal (somente leitura); modelos de conteúdo, fragmentos, páginas de aterrissagem e conteúdo de mensagem em linha (leitura e gravação) | Beta | [Ferramentas do Journey Optimizer](ajo-mcp.md) |
| **Customer Journey Analytics** | Visualizações de dados, dimensões, métricas, relatórios, segmentos, intervalos de datas, projetos e públicos-alvo (leitura e gravação) | Disponível | [Ferramentas do Customer Journey Analytics](cja-mcp.md) |
| **Adobe Analytics** | Conjuntos de relatórios, dimensões, métricas, relatórios, segmentos, intervalos de datas e projetos do espaço de trabalho (leitura e gravação para componentes compatíveis) | Disponível | [Ferramentas do Adobe Analytics](analytics-mcp.md) |
| **Workfront** | Ferramentas de gerenciamento de trabalho para projetos, tarefas e fluxos de trabalho de aprovação | Visualização | [Servidor MCP do Workfront](https://experienceleague.adobe.com/pt-br/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview) |


>[!NOTE]
>
>A disponibilidade da ferramenta depende das licenças do produto, da habilitação da organização, das permissões do produto e das credenciais do Adobe usadas para a autenticação. O MCP apenas supera as ferramentas que sua organização e conta de usuário têm direito de acesso. Consulte [Acessar ferramentas do CX Coworker Gateway](access.md).



## Introdução {#mcp-get-started}

1. Revise [Acessar as ferramentas do CX Coworker Gateway](access.md) para confirmar a disponibilidade, a habilitação e as permissões do produto.
2. Siga [Instalar o Adobe para o Gateway do CX Coworker](install.md) para conectar seu cliente MCP ao ponto de extremidade.
3. Revise a página do produto para cada ferramenta de produto que você planeja usar.

