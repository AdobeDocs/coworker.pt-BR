---
title: Criar e executar uma habilidade do portal de qualidade no Co-worker
description: Saiba como usar uma habilidade personalizada do Colaborador para validar automaticamente as ativações de público-alvo em relação a listas de supressão, limites de frequência e padrões de nomenclatura antes da implantação.
role: User
level: Beginner, Intermediate
doc-type: Feature Video
duration: 101
last-substantial-update: 2026-09-08
jira: KT-22379
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 1%
---

# Criar e executar uma habilidade de portal de qualidade usando habilidades de IA personalizadas

As equipes de marketing dependem de regras e processos de governança para garantir que os públicos-alvo sejam ativados corretamente. Antes de iniciar um público-alvo para um destino, as equipes geralmente precisam verificar listas de supressão, limites de frequência, requisitos de consentimento e convenções de nomenclatura.
 
O desafio é que essas verificações dependem frequentemente de conhecimentos tribais e revisões manuais. Quando processos vivem na cabeça das pessoas, erros podem acontecer.

Neste vídeo, você verá como uma habilidade personalizada de colega de trabalho atua como um Portal de ativação, validando automaticamente os públicos-alvo em relação aos padrões de ativação da sua organização antes que eles sejam transferidos para a jusante.

>[!VIDEO](https://video.tv.adobe.com/v/3503162/?learn=on&enablevpops)

## Exemplo de habilidade do portal de qualidade de ativação
 
Você pode criar sua própria habilidade **Portal de Qualidade de Ativação** reutilizável colando um prompt no Colaborador. Os recursos de criação de habilidades do colaborador convertem o prompt em uma habilidade salva em **seu próprio ambiente**. Segue-se um exemplo baseado na demonstração do vídeo.
 
A chave é definir **seus próprios padrões de aprovação/reprovação** para os três portões de governança:
 
1. Supressão / Consentimento
2. Limite de frequência
3. Convenção de nomeação
 
O quadro continua a ser o mesmo para todos. Personalize as seções marcadas com **`[...]`** para corresponder aos padrões da sua organização.

## Prompt mestre

> **Salve como uma habilidade chamada &quot;Portal de Qualidade de Ativação&quot;.**

```text
It's a governance gate that runs a pre-activation checklist before any audience is sent to a destination.

It is read-only. It never activates, mutates, or copies anything.

Resolve the named audience and destination from our Knowledge Graph, evaluate the three gates below, then render one visual scorecard containing:

- An Alert banner
- One MetricCard per gate
- A DataTable with:
- Gate
- Status
- Finding
- Required Fix

Provide a single verdict:

- CLEARED only if all three gates pass
- BLOCKED if any gate fails

For every failed gate, provide the specific remediation needed.
 
All gates fail closed:

- Missing data = BLOCKED
- Never assume success when information is unavailable
 
Trigger phrases:

- "run the activation gate"
- "is this audience ready to activate"
- "pre-activation checklist"
- "can I activate to ..."

The three gates are:
 
[Paste Gate 1, Gate 2, and Gate 3 definitions here]
```

## Portão 1: Supressão / Consentimento
 
> Edite esta seção para corresponder aos requisitos de supressão e consentimento de sua organização.
 

```text
Gate 1 – Suppression List

Pass only if a recognized suppression, opt-out, or consent audience is applied alongside the target audience.

Discover eligible lists using name patterns such as:

- suppress
- opt-in
- opt out
- consent
- do not contact
 
Because suppression lists may live in destination dataflows rather than audience metadata, require the marketer to confirm one is attached.
 
If no suppression or consent list exists anywhere in the sandbox, fail hard.
 
Our standard:

[Example: A consent audience is mandatory for all email and SMS destinations. For direct mail destinations it is optional.]
```

## Porta 2: Limite de frequência

> Edite esta seção para corresponder aos requisitos de frequência de entrega de sua organização.

```text
Gate 2 – Frequency Cap
 
Read the delivery frequency on the resolved destination.

Pass if:

- Frequency is present
- Frequency is bounded

Fail if:

- Frequency is blank
- Frequency is unbounded

Our standard:

[Example: Frequency must be DAILY or less frequent. Any hourly cadence or blank value is blocked.]
```

## Portão 3: Convenção de Nomenclatura
 
> Edite esta seção para corresponder às regras de nomenclatura de público-alvo de sua organização.
 

```text
Gate 3 – Naming Convention

Evaluate the audience name programmatically.

Any rule violation causes failure.

Block names that:

- Contain "test"
- Contain "copy"
- Contain an auto-copy suffix such as _[6-hex]
- Contain timestamps
- Contain 24-character object IDs
- Start with a bare number or cryptic short code
- Are entirely lowercase
- Are excessively short or unclear
- Use generic defaults such as:
- Save audience
- Email
- New Accounts
- Lack a category–qualifier separator

Our standard:

[Example: [Line of Business] – [Criteria] in title case]

Example:

Mortgage – High Propensity Prospects

When blocked on naming, always propose a compliant replacement name.
```

## Orientação

### &#x200B;1. Personalizar apenas as seções entre colchetes

Atualizar somente as seções contidas em **`[...]`**.
 
Essas seções definem os padrões de governança específicos da organização.
 
Todo o resto deve permanecer inalterado:

- Resolução do público
- Avaliação de portal
- Renderização do scorecard
- Lógica de veredicto


### &#x200B;2. Verificar pré-requisitos
 
Essa habilidade depende de:
 
- Acesso ao Gráfico de conhecimento
- Descoberta de públicos-alvo
- Descoberta de destino
- Descoberta da lista de supressão
- Suporte a artefatos visuais
- Banner de alerta
- CartõesMétricos
- Renderização de DataTable

Se esses recursos não estiverem disponíveis no ambiente do cliente, a habilidade não poderá ser executada conforme projetado.

### &#x200B;3. Manter a habilidade como somente leitura

A habilidade deve sempre permanecer somente leitura.

Inclua esse requisito explicitamente no prompt para garantir que a habilidade nunca seja confundida com um fluxo de trabalho de ativação.

O Portal de qualidade de ativação avalia somente a disponibilidade da ativação. Ele **não** ativa públicos, modifica configurações ou copia dados.
