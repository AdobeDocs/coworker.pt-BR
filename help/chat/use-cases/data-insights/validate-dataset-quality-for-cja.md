---
title: Validar dados do Customer Journey Analytics com a habilidade de validação de dados no Co-worker
description: Saiba como validar dados do Customer Journey Analytics usando a habilidade Validação de dados no Colaborador e resolver problemas antes de criar painéis.
feature: AI Tools
role: User
level: Beginner, Intermediate
doc-type: Feature Video
duration: 330
last-substantial-update: 2026-09-16
jira: KT-22622
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%
---
# Validar dados do Customer Journey Analytics com a habilidade de validação de dados em [!DNL Coworker]

A qualidade dos dados é a base de relatórios precisos no Adobe Customer Journey Analytics (CJA). Antes de criar métricas, painéis, segmentos ou jornadas para clientes, é essencial compreender se os dados subjacentes do Adobe Experience Platform (AEP) podem ser confiáveis.

Neste vídeo, você aprenderá a usar a **habilidade de Validação de dados no Colaborador** para avaliar rapidamente a qualidade dos conjuntos de dados que alimentam sua implementação do Customer Journey Analytics, sem escrever consultas ou inspecionar dados manualmente.

>[!VIDEO](https://video.tv.adobe.com/v/3503519/?learn=on&enablevpops)

## Descubra os conjuntos de dados por trás dos relatórios do CJA

Veja como o Colaborador pode identificar:

- Quais conjuntos de dados estão conectados à Customer Journey Analytics
- As conexões e visualizações de dados associadas a uma sandbox específica
- Os conjuntos de dados que alimentam ativamente os relatórios
- Características principais do conjunto de dados, como status de transmissão e namespaces de identidade

Ao entender exatamente quais conjuntos de dados alimentam seus relatórios, você pode concentrar os esforços de validação onde eles são mais importantes.

## Explorar esquemas de conjunto de dados e campos disponíveis

Saiba como inspecionar esquemas de conjunto de dados diretamente da Adobe Experience Platform.

O colaborador recupera detalhes e superfícies do esquema:

- Commerce e campos de transação
- Informações sobre o produto
- Dados de interação na Web
- Campos de identidade
- Atributos de campanha e marketing
- Dimensões geográficas e do dispositivo

Isso fornece um inventário de campos disponíveis para análise e destaca a diferença entre os campos que existem em um esquema e os campos que contêm dados utilizáveis.

## Validar qualidade da identidade

Os dados de identidade são essenciais para o Customer Journey Analytics, pois são compatíveis com relatórios no nível da pessoa e análise de jornada entre canais.

Neste vídeo, você verá como o Coworker:

- Valida campos de identidade
- Verifica valores nulos e a integridade dos dados
- Avalia a qualidade do identificador
- Atributos de identidade ausentes ou indisponíveis nas superfícies

A validação do exemplo mostra que a ECID e as identidades de email estão totalmente preenchidas e são válidas na amostra, enquanto a Analytics ID não pôde ser recuperada. Isso fornece um sinal útil ao decidir quais identificadores podem oferecer suporte à compilação de perfis e aos relatórios.

## Analisar qualidade de campo individual

Um campo pode existir em um conjunto de dados, mas ainda ser inadequado para relatórios.

Veja como o Colaborador valida um campo de rastreamento de campanha e relata:

- Taxas de população
- Porcentagens nulas
- Consistência dos dados
- Detecção de valor inválido

No exemplo, os valores do código de rastreamento presentes são limpos e consistentes, mas aproximadamente 85% das linhas são nulas. Isso revela um ponto cego importante no relatório antes que uma dimensão do CJA ou métrica de campanha seja criada no campo.

## Executar validação do conjunto de dados habilitada por IA

Em vez de validar campos individuais, um de cada vez, o Colaborador pode avaliar um conjunto de dados inteiro.

Você aprenderá como a habilidade Validação de dados:

- Seleciona campos importantes para validação
- Avalia integridade e qualidade
- Compara a integridade dos dados entre campos
- Destaca os pontos fortes e os riscos potenciais de geração de relatórios

Os resultados da validação fornecem um mapa de viabilidade do CJA. Campos limpos, como nome de página da Web e código de email, podem estar prontos para o relatório, enquanto campos esparsos, como valor de compra, nome de campanha e código de rastreamento, exigem investigação.

## Identificar riscos de receita e atribuição

O vídeo também demonstra como a validação de dados pode descobrir problemas que afetam a precisão dos relatórios, incluindo:

- Dados de campanha dispersos
- Informações de atribuição ausentes
- Valores de transação incompletos
- Lacunas na medição de receita

No conjunto de dados exibido, as contagens de compra estão disponíveis, mas os valores dos pedidos não são preenchidos de forma confiável. Esse é um problema a ser investigado antes de confiar em relatórios de receita.

## Por que a validação de dados é importante para o Customer Journey Analytics

O Customer Journey Analytics só é tão confiável quanto os dados por trás dele.

A validação de conjuntos de dados antes de criar relatórios ajuda as equipes a:

- Aumentar a confiança nos resultados da análise
- Melhorar as práticas de governança de dados
- Reduzir erros de relatório
- Identificar problemas de implementação mais cedo
- Solucionar problemas de métricas inesperadas com mais eficiência

Com o Colaborador, essas verificações podem ser iniciadas usando prompts de linguagem natural, tornando a validação de dados mais acessível para usuários técnicos e não técnicos.

