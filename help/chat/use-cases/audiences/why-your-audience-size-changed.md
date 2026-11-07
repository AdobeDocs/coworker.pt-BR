---
title: Analisar alterações de público-alvo do Adobe Experience Platform com o CX Enterprise Coworker
description: Saiba como a CX Enterprise Coworker usa a habilidade Estatísticas operacionais e Análise causal para explicar alterações no público-alvo, identificar causas prováveis, avaliar o impacto downstream e recomendar as próximas etapas.
feature: AI Tools
role: User
level: Beginner
doc-type: Feature Video
duration: 216
last-substantial-update: 20261105
jira: KT-22454
autotag-review: '2026-11-05T15:16:40.881Z'
TQID: 'https://experienceleague.adobe.com/mj3rSj7AxRsmhxipLJLR69bzfujK-eCVaXQMFlgg-NA'
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 41216c2254d4c98f05c608f02bc6da31da3dd3c6
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%
---

# Por que meu público-alvo da Experience Platform teve um pico/queda?

Saiba como o [!DNL CX Enterprise Coworker] pode ajudar a investigar alterações inesperadas nos objetos principais [!DNL Adobe Experience Platform] usando a habilidade Estatísticas Operacionais e Análise Causal.

## O que você vai aprender

Neste vídeo, você verá como usar prompts em linguagem simples no Coworker para investigar um aumento inesperado em um público-alvo do Adobe Experience Platform antes de um lançamento de campanha. A apresentação mostra como a análise causal pode conectar alterações no tamanho do público-alvo com dados operacionais, descartar alterações de configuração e expor explicações prováveis sem esperar por uma investigação de engenharia.

>[!VIDEO](https://video.tv.adobe.com/v/3507347/?captions=por_br&learn=on&enablevpops)

Você aprenderá a:

- Execute uma análise de causa usando as habilidades de Estatísticas Operacionais e Análise de Causa.
- Compare as alterações no tamanho do público com as alterações na contagem total de perfis da sandbox.
- Entenda como as regras de qualificação de público-alvo podem fazer com que perfis recém-assimilados entrem em um público-alvo automaticamente.
- Verifique a atividade do pipeline e da configuração para determinar se a configuração do público-alvo foi alterada.
- Use as próximas etapas sugeridas pelo Colaborador para refinar os critérios de público-alvo e continuar investigando a fonte do crescimento do perfil.
- Avalie o impacto downstream identificando públicos dependentes, campanhas, destinos e jornadas não publicadas.
- Identifique o que validar antes do lançamento quando uma alteração de público upstream afetar o direcionamento.

## Como a análise funciona

O exemplo segue um público-alvo cujo tamanho muda inesperadamente durante vários dias. O colaborador analisa a janela de tempo selecionada e compara possíveis causas. A análise conclui que as alterações diárias do público-alvo se alinham com o crescimento na população total de perfis da sandbox.

Como o público-alvo inclui perfis sem uma ID de fidelidade, os perfis recém-assimilados que atendem a essa condição podem se qualificar automaticamente. O colaborador também verifica o histórico do pipeline e da configuração para ajudar a distinguir as alterações de dados recebidos das alterações feitas na configuração do público-alvo.

## Avaliar o impacto downstream

Encontrar a causa é apenas parte da investigação. O vídeo também demonstra como perguntar ao Colaborador o que a mudança de público afeta downstream. O colaborador examina objetos dependentes e realces em que o público-alvo maior pode influenciar o direcionamento futuro, incluindo públicos-alvo e jornadas relacionados.

Isso oferece às equipes de operações de marketing um caminho mais rápido, desde detectar uma alteração inesperada no público até entender sua causa provável, seu impacto potencial e as verificações a serem feitas antes do lançamento.

## Principais pontos

O CX Enterprise Coworker pode ajudar a explicar por que objetos importantes do Adobe Experience Platform mudam com o tempo, combinando estatísticas operacionais, análise causal, informações de dependência e ações de acompanhamento recomendadas em um fluxo de trabalho conversacional.
