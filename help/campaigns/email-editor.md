---
description: descrição.
title: Entender o editor de email
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 94cf399a48d13ee83c702804b50fdccd4baa9d71
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%
---
# Entender o editor de email {#email-editor}

O editor de email permite refinar um email gerado por IA diretamente no quadro da campanha. Edite a linha de assunto e o pré-cabeçalho, formate o texto e as imagens em linha ou troque em um modelo diferente.

Selecionar um cartão de email no quadro de campanha abre o editor de email como um painel lateral. A partir daí, o usuário pode editar o assunto e o pré-cabeçalho (com alternativas sugeridas pela IA), clicar no corpo do email para selecionar e formatar texto ou imagens, alternar entre variantes geradas pela IA, trocar o modelo do HTML, verificar a compatibilidade do cliente de email e enviar um email de teste para sua própria caixa de entrada. As alterações são salvas automaticamente e as versões anteriores podem ser revisadas e restauradas.

## Como acessar o

1. Abra a campanha desejada e clique em Open editor no cartão de email.

CAPTURA DE TELA

1. Edite os campos **Assunto** e **Pré-cabeçalho** diretamente ou clique em **Sugestões inteligentes** ao lado de qualquer uma das alternativas geradas pela IA.
1. Clique no corpo do email para selecionar um bloco de texto ou uma imagem e, em seguida, use a barra de ferramentas flutuante exibida para formatar o texto ou gerenciar a imagem.
1. Use **Alternar Modelo do HTML** para substituir o corpo do email por um modelo diferente.
1. Use **Enviar email de teste**, insira um endereço de destinatário e clique em **Enviar** para enviar uma visualização ao vivo por email para esse endereço.
1. Use o ícone de histórico da versão para visualizar e restaurar uma versão salva anteriormente.
1. Salvar alterações automaticamente — nenhuma etapa de salvamento manual é necessária.

### Comportamentos principais

- Os uploads de imagem são limitados a 10 MB; imagens com mais ou menos 3 MB são compactadas automaticamente, com uma nota de qualidade recomendando imagens com menos de 3 MB.
- Os campos de assunto e pré-cabeçalho têm a opção de alternativas geradas por IA por meio desse ÍCONE.
- Use Ctrl+z (CMD+z para Mac) para &quot;Desfazer&quot; e reverter sua última ação. Use CTRL+Y (CMD+y para Mac) para &quot;Refazer&quot; e reverter sua última ação de desfazer. KEITH CHECK STANDARD
- As versões salvas anteriores podem ser visualizadas e restauradas em um painel de histórico de versões por meio desse ÍCONE.
- Por padrão, geramos duas variantes por email; é possível selecionar a variante desejada por meio das miniaturas à direita.

## O que este recurso não faz

- Não é um construtor de blocos de arrastar e soltar — não há biblioteca de blocos e os blocos de conteúdo não podem ser adicionados, removidos ou reordenados; a edição acontece diretamente no HTML de email existente.
- No momento, não há suporte para a inserção de tags de personalização/mesclagem.
- Ele não fornece um campo de texto alternativo para imagens.
- Ele não impõe uma linha de assunto, pré-cabeçalho ou outras verificações de nível de conteúdo antes que um email seja considerado &quot;pronto&quot;. As únicas verificações de pré-lançamento são no nível da campanha (configuração de envio, um email de teste enviado, um público real), não verifica o conteúdo do email em si.
- A alternância de visualização de desktop/dispositivo móvel não está disponível na visualização padrão de edição de email da campanha. [PRECISA DE ENTRADA para confirmar o escopo]
- [NEEDS INPUT — para confirmar com o engenheiro: se o editor se torna totalmente somente leitura (não apenas o campo do remetente) depois que uma campanha é ativada/iniciada.]
