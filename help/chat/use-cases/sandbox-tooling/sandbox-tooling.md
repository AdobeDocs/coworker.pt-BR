---
title: Habilidades dos agentes de ferramentas de sandbox
description: Saiba como usar as habilidades de agente de ferramentas de sandbox para replicar metadados de objetos em ambientes de sandbox.
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%
---

# Habilidades de agente de ferramentas de sandbox

>[!AVAILABILITY]
>
>As habilidades de agente de ferramentas de sandbox estão disponíveis para todos os clientes com acesso ao Adobe CX Enterprise Coworker. Para usar todos os recursos disponíveis, você precisa das seguintes permissões:
>
>**Manage-sandbox** ou **View-sandbox**: essas permissões permitem usar Habilidades de agente de ferramentas de sandbox para exibir sandboxes diretamente no Coworker.
>
>**Gerenciar-pacote**: essa permissão permite que você use Habilidades de Agente de Ferramentas de Sandbox para criar pacotes diretamente no Colaborador.

>[!NOTE]
>
>Atualmente, você pode usar as habilidades de agente de ferramentas de sandbox para descobrir, empacotar e migrar objetos de esquema e público-alvo. A compatibilidade com tipos de objetos adicionais será adicionada em versões futuras.

Use as ferramentas de sandbox para habilidades essenciais a fim de mover metadados de objetos (incluindo esquemas e públicos) em ambientes Adobe Experience Platform, descrevendo o que você deseja realizar em linguagem natural. Com o CX Coworker, você pode descobrir os metadados necessários, identificar dependências automaticamente, criar pacotes de migração e migrar objetos por meio de uma experiência de conversação.

>[!VIDEO](https://video.tv.adobe.com/v/3496706?learn=on)

## Pré-requisitos {#prerequisites}

Antes de começar, verifique se você tem:

- Acesso ao Adobe Experience Platform e à organização e sandbox apropriadas.
- Acesso aos objetos que você deseja descobrir ou migrar.
- O plug-in CXO do Adobe instalado no CX Coworker.

Para obter instruções sobre como instalar plug-ins, consulte o [Guia da Interface do Usuário do Coworker](https://experienceleague.adobe.com/pt-br/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide).

## Usar habilidades de agentes de ferramentas de sandbox {#use-sandbox-tooling-agentic-skills}

Interaja com as habilidades de agentes de ferramentas de sandbox usando a linguagem natural no CX Coworker. Descreva seu objetivo da maneira mais clara possível. Solicitações específicas produzem os melhores resultados, enquanto solicitações vagas ou muito breves podem retornar resultados de qualidade inferior ou não chamar o agente.

Para usar as habilidades de agentes de ferramentas de sandbox:

1. Navegue até **[!UICONTROL CX Coworker]**.
1. Insira uma descrição clara do que você deseja realizar. Por exemplo:

   *&quot;Mover Platina, Membro de Fidelidade do esquema, da sandbox atual para a sandbox de demonstração Acme.&quot;*

1. Revise a tabela de resultados, que mostra as sandboxes de origem e de destino. Quando estiver pronto para continuar, selecione **[!UICONTROL Continuar]** e **[!UICONTROL Enviar]** para confirmar.

   ![Os resultados da solicitação com Continuar selecionado, destacando Enviar.](./assets/sandbox-tooling/results-proceed.png)

1. Selecione um ou mais objetos que você deseja migrar e selecione **[!UICONTROL Enviar]**.

   ![Página de seleção de objeto destacando Enviar.](./assets/sandbox-tooling/object-selection.png)

1. Revise os objetos e dependências que o agente identifica e confirme as ações da operação - *Criar Novo* ou *Usar Existente*. Quando estiver pronto para iniciar a migração, selecione **[!UICONTROL Continuar]** e **[!UICONTROL Enviar]** para confirmar. A migração pode levar vários minutos para ser concluída.

   ![Confirmar o destaque da página do plano de ação.](./assets/sandbox-tooling/action-plan.png)

1. Quando a migração for concluída, os objetos selecionados estarão disponíveis na sandbox de destino.

   ![Página de transferência concluída mostrando o status da solicitação.](./assets/sandbox-tooling/transfer-complete.png)

Para obter mais informações sobre como usar o CX Coworker, consulte o [Guia da Interface do Usuário do Colaborador](https://experienceleague.adobe.com/pt-br/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide).

## Casos de uso aceitos {#supported-use-cases}

Explore maneiras comuns de usar as habilidades de agente de ferramentas de sandbox para simplificar o gerenciamento de sandbox e a migração de metadados.

### Mover metadados de objeto entre sandboxes

Como administrador de sandbox gerenciando várias sandboxes do Adobe Experience Platform, você pode migrar metadados de objeto usando solicitações em linguagem natural, em vez de navegar manualmente pela interface do usuário.

Usando o CX Coworker, você pode migrar metadados de objetos (incluindo esquemas, públicos-alvo e ativos de configuração relacionados) de uma sandbox para outra descrevendo a migração na linguagem natural. As habilidades dos agentes de ferramentas de sandbox identificam e empacotam automaticamente as dependências necessárias, ajudando a garantir uma migração confiável.

Por exemplo:

- &quot;Mover Platina de Membros de Fidelidade da Luma de esquema da sandbox atual para a sandbox de produção.&quot;

### Promover públicos-alvo entre sandboxes

Como administrador de sandbox, você pode promover públicos-alvo entre ambientes sem recriá-los ou reconfigurá-los manualmente.

Por exemplo:

- &quot;Promova o público-alvo &quot;Nome do público-alvo&quot; para a sandbox de preparo.&quot;

As habilidades dos agentes de ferramentas de sandbox identificam o público-alvo especificado, validam suas dependências e migram todos os objetos necessários para a sandbox de destino.

## Exemplo de prompts {#example-prompts}

Use os seguintes prompts como exemplos ao interagir com as Habilidades de agente de ferramentas de sandbox.

### Prompts de esquema

Use esses prompts quando souber o nome do esquema e a sandbox de destino.

- &quot;Mover o esquema &quot;Nome do esquema&quot; da sandbox atual para a sandbox de produção.&quot;

### Prompts de público

Use esses prompts quando você souber o nome do público-alvo.

- &quot;Promova o público-alvo &quot;Nome do público-alvo&quot; para a sandbox de preparo.&quot;

## Próximas etapas {#next-steps}

Depois de ler este guia, você deve entender como usar as habilidades de agente de ferramentas de sandbox para detectar, empacotar e migrar objetos compatíveis entre as sandboxes.

Para obter mais informações sobre as ferramentas de sandbox, consulte o [Guia de ferramentas de sandbox](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sandbox/ui/sandbox-tooling).

