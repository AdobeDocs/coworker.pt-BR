---
source-git-commit: e5bf2a0a2ee55513b32442f70d01dc5825ac9d6a
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%
---
# Documentação do CX Enterprise Coworker

Source para o conjunto de documentação do Adobe CX Enterprise Coworker.

## Configuração de publicação

Use os fluxos de trabalho de espelhamento e validação de artigo compartilhado em `.github/workflows/`.
O fluxo de trabalho de validação é executado para solicitações de pull e envios para `main`.
O fluxo de trabalho de espelhamento é executado quando você envia para `main`.

Use `markdownlint_custom.json` para substituições de regras do Markdown e `linkcheckexclude.json`, por exemplo, exclusões de URL.
O arquivo `pipeline.opts` segue a configuração de verificação de link em `cx-enterprise-ai.en`.
Adicionar redirecionamentos de URL a `redirects.csv` usando as colunas `source,dest`.
