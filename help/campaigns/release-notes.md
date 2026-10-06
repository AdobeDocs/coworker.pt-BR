---
description: Saiba mais sobre as melhorias e correções de recursos nas notas de versão do Adobe CX Enterprise Coworker Campaigns.
title: Notas de versão do CX Enterprise Coworker Campaigns
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: ee66c1cc95ef1dd8c5e45c1fcb699547e63b9c8a
workflow-type: tm+mt
source-wordcount: '3590'
ht-degree: 0%
---
# Notas de versão do Adobe CX Enterprise Coworker Campaigns {#release-notes}

As versões do Co-worker Campaigns operam em um modelo de entrega contínua que permite uma abordagem mais escalável e em fases para a implantação de recursos.

## Setembro de 2026 {#sep-2026}

**Data de lançamento: 17 de setembro de 2026**

* Conecte um espaço de trabalho de Databricks hospedado no Azure, GCP ou um domínio personalizado
* As campanhas não podem mais ser iniciadas até que o workflow esteja totalmente configurado
* Os modelos de campanha foram atualizados com conteúdo atualizado
* Escolha um conector diretamente ao fazer upload do CSV da sua lista de contatos
* Correção de uma falha que poderia ocorrer após a rolagem por uma longa lista de inscrições de avaliação
* Correção de um problema em que o upload de um CSV de público-alvo com cabeçalhos em branco ou duplicados poderia causar falha na página
* Correção do texto de espaço reservado em um prompt de campanha que aparecia não preenchido após ser resolvido
* Correção de uma falha na página Habilidades causada pela ausência de um gradiente de cor
* Fixo bate-papo ficando preso repetindo a mesma pergunta depois que você já respondeu
* As respostas do chat não mostram mais um prefixo de ID perdido na frente da resposta selecionada
* O bate-papo agora sugere respostas rápidas para a próxima etapa que você pode tocar para preencher a caixa de composição
* Os modelos de campanha agora abrem em uma exibição simplificada na página em vez de em uma caixa de diálogo separada
* A barra de progresso expandida do chat agora rola internamente em vez de colocar sua conversa fora da visualização
* As configurações do Campaign agora refletem os detalhes mais recentes do painel com mais precisão
* A caixa de diálogo do plano de atualização agora usa uma aparência mais consistente
* Remoção de um indicador de status redundante do cabeçalho do plano de campanha para uma aparência mais limpa
* As edições rápidas de e-mail agora são salvas juntas como uma única entrada de histórico de versões, em vez de várias
* Correção de títulos de kits de marca ocasionalmente vazando enquanto um rascunho estava sendo gerado
* Editar uma imagem com o Adobe Express diretamente na barra de ferramentas da imagem
* Os dados básicos do público-alvo do agente agora permanecem sincronizados no quadro de campanha sem uma atualização manual
* Os logotipos de marca no quadro de campanha são cortados de forma mais organizada para se ajustarem ao seu espaço
* Transferência visual mais suave quando seu plano de campanha muda para o quadro de campanha

**Data de lançamento: 3 de setembro de 2026**

* Copie qualquer mensagem de chat e classifique as respostas da IA com uma miniatura para cima ou miniatura, diretamente da própria mensagem
* A lista de tarefas do plano de campanha agora permanece fixada acima da entrada do chat enquanto sua campanha está em execução, para que você possa rastrear o progresso sem rolar para fora
* Conectar um DataFracks SQL warehouse como uma nova fonte de dados para suas campanhas
* O editor de email baseado em chat mais antigo foi removido em favor do editor de ativos de email mais recente
* Agora, o Administrador de usuários de avaliação permite excluir usuários do Adobe, facilitando a visualização de inscrições em avaliações reais
* Correção de um problema em que sugestões de campanha semelhante podiam falhar ao carregar
* As mensagens de chat agora têm um espaçamento mais estreito e consistente

**Data de lançamento: 1 de setembro de 2026**

* Agora, emails grandes de campanha são exibidos totalmente no editor, em vez de serem cortados
* O botão de lançamento do painel de campanha agora é rotulado como &quot;Revisar e iniciar&quot; para maior clareza
* A conexão de uma conta do Salesforce não mostra mais uma mensagem de erro incorreta do Marketo
* O Salesforce agora tem seu próprio logotipo na lista de conectores
* Os conectores disponíveis agora estão listados antes dos próximos
* A integração agora mostra um indicador de progresso enquanto o kit da sua marca é carregado
* As visualizações de público-alvo e fonte de conhecimento agora têm um botão Fechar e podem abrir em tela cheia
* Os cartões do plano de campanha não param de mostrar &quot;criação&quot; depois que a campanha começa a funcionar
* O chat não mantém mais mensagens de progresso temporárias (como &quot;Explorando...&quot;) no seu histórico de conversas
* Os controles da barra de ferramentas agora são bloqueados adequadamente enquanto a imagem da IA ou as sugestões de texto estão sendo aplicadas
* Correção de um problema em que substituir uma imagem no editor de ativos não funcionava corretamente

## Agosto de 2026 {#aug-2026}

**Data de lançamento: 26 de agosto de 2026**

* Clicar em qualquer lugar em um cartão de modelo de campanha agora abre sua visualização, não apenas o título
* O espaço reservado da barra de prompt da campanha é exibido novamente corretamente depois que você limpa a entrada, com suporte mais claro ao leitor de tela
* A sugestão &quot;Help me prompt&quot; agora substitui corretamente o texto existente na barra de prompts da campanha
* Baixar cancelamentos de assinatura como um CSV agora reflete somente a execução da campanha que você está visualizando
* A comparação do plano de avaliação agora mostra campanhas do Launch e insights do Campaign como recursos incluídos
* Os públicos-alvo criados sem um fluxo de trabalho completo agora são exibidos corretamente no cartão Público-alvo do quadro de campanha
* Os prompts de feedback de estado vazio são lidos mais naturalmente no aplicativo

**Data de lançamento: 25 de agosto de 2026**

* Fazer logon em uma guia do navegador agora sincroniza as outras automaticamente, corrigindo combinações de contas entre guias
* Clicar em Criar agora faz com que seu plano avance com confiança, em vez de gerá-lo novamente ocasionalmente
* Diagramas de fluxo de trabalho em bate-papo mostram mais telas, de modo que os controles de zoom não cubram mais as etapas
* As guias de detalhes da campanha têm uma aparência atualizada e mais consistente
* Salvar ou remover um domínio de envio em Domínios e remetentes agora é mais rápido e confiável

**Data de lançamento: 24 de agosto de 2026**

* Veja sua estratégia de campanha gerada diretamente no quadro da campanha
* Substitua seu público diretamente da caixa de diálogo de validação de campanha
* Exportações de PDF e Word do Campaign agora incluem seu diagrama de fluxo de trabalho real
* A guia Insights permanece visível com um estado vazio útil logo após o lançamento
* Adicionar ou remover pontos de contato ao revisar campos de campanha
* A barra de ferramentas do quadro do Campaign é mais simples com a remoção de botões desnecessários
* O assistente para Domínios e remetentes limpa subdomínios e orienta a configuração pela primeira vez com uma marca de formatação
* O assistente para Domínios e remetentes mostra erros de validação de subdomínio em linha enquanto você digita
* O call-to-action de campanha pós-prova foi removido para um fluxo mais limpo
* Os nomes dos idiomas chineses agora são exibidos corretamente no seletor de idiomas
* Miniaturas de variante geradas por IA são carregadas de forma confiável sem rótulos duplicados
* Campanhas recém-criadas agora são exibidas imediatamente na lista de campanhas recentes na Página inicial
* Os insights de todas as campanhas agora incluem um resumo gerado por IA do desempenho da campanha da sua organização
* Fornecer a entrada solicitada em uma conversa de fluxo de trabalho não a deixa mais paralisada
* A integração de avaliação não pisca mais uma tela de carregamento extra ao verificar se há um kit de marca existente
* As fontes de público-alvo de amostra obsoletas agora são apagadas automaticamente do seu fluxo de trabalho
* Layout, tema e fontes agora são renderizados corretamente no shell unificado da Experience Cloud
* Sugestões de campanha semelhantes não mostram mais um campo de canal desnecessário

**Data de lançamento: 14 de agosto de 2026**

* Excluir domínios de rascunho que não são mais necessários em Domínios e remetentes
* Consulte o status de verificação de DNS para cada registro durante a configuração do domínio
* Os detalhes do domínio agora mostram o remetente de email configurado
* Os valores do registro DNS são truncados perfeitamente com uma dica de ferramenta para o texto completo
* Formatar vários blocos de texto de email de uma só vez com várias seleções
* Receba sugestões de campanha semelhantes ao criar uma nova campanha
* Escopo dos insights da campanha para uma única execução de uma campanha recorrente
* Escolha o idioma de sua preferência no menu de perfil
* Chame a atenção quando as descrições de template de campanha precisarem de mais detalhes
* As notas de versão são mais fáceis de navegar com uma navegação e paginação melhores
* Recolher a lista de campanhas recentes da barra lateral para economizar espaço
* A visualização do inventário da campanha agora permanece do jeito que você deixou
* Reordenar filtros de execução e ir para um intervalo de datas de um seletor de calendário
* Visualizar detalhes do público-alvo mesmo em cartões de público-alvo somente leitura
* Correção de flashes da tela de fluxo de avaliação de integração e um problema de tempo de entrada
* A alça de redimensionamento do painel de chat não bloqueia mais a barra de rolagem da lista de mensagens
* A criação do kit de marca agora mostra o motivo real pelo qual um salvamento falhou

**Data de lançamento: 6 de agosto de 2026**

* O Campaign Insights agora mostra cancelamentos de assinatura com um CSV para download de quem recusou
* Uma tabela de detalhamento de desempenho por email agora está na guia Insights
* Veja seu mapa de jornadas de campanha diretamente na guia Insights
* As etapas de espera com base na duração agora estão visíveis na exibição do fluxo de trabalho do jornada
* As ramificações de jornada ponderadas são mostradas na exibição de edição do fluxo de trabalho
* Listas de contato agora estão conectadas a dados em tempo real
* As campanhas recorrentes mostram 0 envios imediatamente em vez de &quot;insights pendentes&quot;
* Editar texto de prompt de remix diretamente em torno dos chips de espaço reservado
* Aprimoramento de coachmark e chips de espaço reservado mais limpos no editor de remix
* Os cartões de workflow do Campaign agora mostram um estado vazio útil quando nada está em execução
* O botão de plano de atualização não bagunça mais o cabeçalho de detalhes da campanha
* Os cartões de workflow têm um layout mais simples com o nome e a descrição da jornada removidos

## Julho de 2026 {#july-2026}

**Data de lançamento: 30 de julho de 2026**

* Os insights de todas as campanhas agora correspondem ao layout de insights de campanha individuais, além de um novo gráfico de desempenho diário
* Interromper uma campanha ao vivo diretamente da página da campanha
* A duplicação de uma campanha agora solicita apenas um novo nome
* Editar modelos de email diretamente na lista de modelos
* Filtrar a exibição de jornada de campanha recorrente por execução
* Adicionar uma imagem de marca diretamente do quadro de campanha
* A tabela de administração de avaliação agora é compatível com pesquisa de email, paginação e exportação completa de CSV
* O botão &quot;Surprise me&quot; agora responde instantaneamente, sem atraso de animação
* Remoção das configurações de cancelamento de inscrição de email da campanha enquanto este recurso era reprocessado
* Editar a programação de uma campanha depois que ela já estiver definida, sem iniciar novamente
* Abra o editor de estilo de gravação no menu estouro para obter acesso mais rápido
* Pressionar Enter agora envia de forma consistente em cada barra de prompt no aplicativo

**Data de lançamento: 23 de julho de 2026**

* Programar campanhas para envio imediato, uma vez em um horário escolhido ou de forma recorrente
* Gerencie listas de cancelamento de inscrição de Listas de contatos e defina parâmetros de cancelamento de inscrição nas configurações de email da campanha
* Criar e gerenciar formulários com um novo inventário e editor de formulários
* A configuração do conector mostra orientações mais claras quando as credenciais falham, incluindo ao atualizar uma conexão existente
* As conexões do Marketo agora oferecem suporte a URLs da Experience Cloud
* O assistente de Domínios e remetentes captura mais problemas de registro DNS antes da ativação do domínio
* Adicione conectores diretamente do menu de adição da entrada da campanha
* As páginas de inventário mostram estados vazios ilustrados mais amigáveis quando ainda não há nada para mostrar
* Os insights do Campaign mostram qual fonte de dados habilita cada métrica
* Os editores de marca agora estão integrados na integração para uma configuração inicial mais suave
* Visualize um exemplo de público-alvo antes de confirmar sua campanha
* As Campanhas de colegas de trabalho agora estão no shell de navegação unificado da Experience Cloud
* Remoção da barra de dica de feedback flutuante de um quadro de campanha mais limpo
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 14 de julho de 2026**

* Implantação de domínios e remetentes, progresso do fluxo de trabalho ao vivo e insights reais do campaign
* A configuração Domínios e remetentes agora está totalmente disponível, com sua escolha de remetente salva automaticamente
* Escolha ou atualize o remetente de email da sua campanha diretamente das configurações da campanha
* A guia Remetentes permanece navegável mesmo antes de um domínio ser verificado
* Rascunhos de email adicionados no meio da conversa agora aparecem de forma confiável no quadro de campanha
* Ajuda e feedback são combinados em um popover simplificado
* Iniciar uma nova conversa não mostra mais as mensagens restantes da última
* As conversas em turnos múltiplos não mostram mais prompts desatualizados na gaveta de respostas
* As listas numeradas nas mensagens de chat mantêm a ordem correta
* A configuração do conector HubSpot agora solicita uma chave de serviço, correspondendo à terminologia do próprio HubSpot
* A tabela de administração de avaliação mostra uma contagem de usuários e não corta mais a última linha
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 9 de julho de 2026**

* Um banner de manutenção e uma caixa de diálogo agora avisam você sobre o tempo de inatividade programado
* Domínios e remetentes tem um assistente de configuração guiado para verificar domínios e adicionar remetentes
* As campanhas em rascunho agora solicitam que você conclua a configuração do email e do canal antes de enviar
* A validação de domínio e remetente detecta mais problemas, incluindo casos de borda de registro DNS
* O menu de perfil foi movido para a barra lateral para obter acesso mais rápido
* Os documentos do Source PDF agora são exibidos como um preenchimento dos detalhes do kit da marca
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 26 de junho de 2026**

* Um novo painel de Insights mostra KPIs de desempenho da campanha: envios, aberturas, cliques, rejeições e muito mais
* As campanhas mostram um selo de status ao vivo no quadro para que você possa ver os envios ativos rapidamente
* Dicas contextuais são exibidas no quadro de campanha para orientá-lo pelas próximas etapas
* A integração de novos usuários usa os dados de sua marca real para personalizar a experiência de configuração
* O seletor de cores da marca lida com códigos hexadecimais curtos e abre em um popover organizado
* Os parâmetros UTM e o limite de mensagem agora podem ser configurados nas Configurações do aplicativo
* Os links de ajuda agora abrem o conteúdo mais recente diretamente no Experience League
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 24 de junho de 2026**

* Iniciar uma campanha agora inicia uma celebração de confetes
* As campanhas mostram um selo de status e o painel é bloqueado para somente leitura depois de iniciado
* A visão geral da marca se encaixa em sua tela com prompts de estado vazio e melhor exibição de logotipo
* A validação mostra uma caixa de diálogo limpa mesmo quando um tipo de erro inesperado é retornado
* O conteúdo de email gerado usa sua meta de campanha para obter resultados mais relevantes

## Junho de 2026 {#june-2026}

**Data de lançamento: 23 de junho de 2026**

* Uma etapa de validação verifica se a campanha está pronta antes do lançamento
* Veja por que cada variante de email foi criada com uma nova lógica de variação
* A visualização do plano de campanha mostra um painel de progresso de marcos em tempo real como fluxo de tarefas em
* A integração de novos usuários usa os dados de sua marca real para personalizar a experiência de configuração
* O seletor de cores da marca lida com códigos hexadecimais curtos e abre em um popover organizado
* Os parâmetros UTM e o limite de mensagem agora podem ser configurados nas Configurações do aplicativo
* Os links de ajuda agora abrem o conteúdo mais recente diretamente no Experience League
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 19 de junho de 2026**

* Verifique a compatibilidade do cliente de email para cada elemento antes de enviar
* Procurar e restaurar versões anteriores do email com um novo painel de histórico de versões
* Edite as cores da marca com um seletor hexadecimal e edição em linha na página da marca
* A biblioteca de marcas carrega mais marcas automaticamente à medida que você rolar a tela
* O menu de perfil foi movido para a barra lateral para obter acesso mais rápido
* Os documentos do Source PDF agora são exibidos como um preenchimento dos detalhes do kit da marca
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 12 de junho de 2026**

* Navegue pela ajuda e pelos guias do produto sem sair do aplicativo
* Os planos de campanha são exibidos seção por seção à medida que são gerados
* Continuar conversas de campanha de onde você parou com mais confiança
* Inicie campanhas a partir de um diálogo dedicado quando seu plano estiver pronto para uso
* A integração usa um nome de produto mais claro e orientação de solicitação da página inicial
* A configuração do conector mostra os campos certos para a chave de API e conexões de entrada
* As respostas de bate-papo fora do escopo sugerem o que perguntar a seguir com prompts de um clique
* Exportações de PDF do Campaign mostram ícones, marcas de produto e uma etiqueta de marca de forma confiável
* Fale com um especialista e os fluxos de atualização carregam seus detalhes de avaliação de maneira mais confiável
* As tags de estilo de escrita se expandem para mostrar o texto completo e vincular à página da sua marca
* Inicie uma marca a partir do estado vazio da biblioteca com categorias úteis
* Faça logon novamente sem problemas quando a sessão expirar
* O aplicativo agora está em coworker-campaigns.adobe.com com a mesma experiência
* A inscrição para avaliação direciona você para a próxima etapa direita após criar sua conta
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 11 de junho de 2026**

* As páginas futuras mostram um espaço reservado limpo sem resíduos no plano de fundo
* As barras de ferramentas do editor de e-mail aparecem à direita no tema claro
* Excluir uma imagem de email limpa a seleção para que a barra de ferramentas desapareça
* As importações de público-alvo em CSV não mostram mais uma lista duplicada no cartão de público-alvo
* O item de Bate- Papos na barra lateral é realçado quando você inicia um novo bate- papo
* O cabeçalho do aplicativo agora mostra apenas o assunto do email (ou &quot;Rascunho&quot;) ao editar um email, removendo o prefixo de número &quot;Email N:&quot; de um título mais limpo
* O menu de perfil foi movido para a barra lateral para obter acesso mais rápido
* Os documentos do Source PDF agora são exibidos como um preenchimento dos detalhes do kit da marca
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 10 de junho de 2026**

* O aplicativo agora é Campanhas de colega de trabalho com nomes atualizados em todo o
* Um tour de integração pela primeira vez o orienta a criar uma marca de demonstração
* Inicie campanhas a partir de um diálogo dedicado quando seu plano estiver pronto para uso
* Conecte o HubSpot com uma chave de API do catálogo de integrações
* Navegar pelos bate-papos com uma lista de conversa reprojetada e estados vazios mais claros
* Desfazer e refazer edições de email com atalhos de teclado familiares
* Tente salvar novamente quando o editor de email encontrar um erro temporário
* Substituir imagens de email com o dimensionamento correto e as dimensões do Adobe Express
* Carregue listas de público-alvo do CSV usando uma caixa de diálogo de importação mais clara no chat
* As tags de estilo de escrita se expandem para mostrar o texto completo e vincular à página da sua marca
* Inicie uma marca a partir do estado vazio da biblioteca com categorias úteis
* Faça logon novamente sem problemas quando a sessão expirar
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 9 de junho de 2026**

* Comparar o uso de avaliação e as opções de atualização em uma caixa de diálogo de plano reprojetado
* Procurar e gerenciar conectores de dados de um catálogo em tempo real no aplicativo
* Preencha as configurações gerais e as preferências de notificação em Configurações
* Seu logon permanece atualizado com um aviso claro quando sua sessão expira
* Seu endereço de email aparece automaticamente ao enviar um email de teste
* Confirme antes de tornar um kit de marca seu padrão
* Os uploads do kit de marca agora respeitam um limite de tamanho de arquivo de 100 MB
* Editar seu nome de campanha diretamente no quadro de campanha
* Visualize modelos e confirme antes de enviar uma campanha
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 4 de junho de 2026**

* Bate-papos recentes são exibidos na barra lateral e você pode renomeá-los em linha
* Abrir a página de Bate-papos para pesquisar e continuar conversas passadas
* Os fluxos de trabalho da página inicial agora são modelos de campanha com um fluxo de remix mais simples
* Os modelos de biblioteca usam uma tabela mais clara com descrições e filtros de canal
* Os kits de marca mostram seu padrão primeiro e filtram por publicado ou rascunho
* Depois de publicar um rascunho de marca, você é direcionado ao kit de marcas ativas automaticamente
* Os dados de campanha e marca são carregados com mais confiabilidade logo após você entrar
* Várias melhorias de desempenho e confiabilidade no

## Maio de 2026 {#may-2026}

**Data de lançamento: 29 de maio de 2026**

* Gere variantes de imagens e escolha em suas próprias imagens, diretamente do editor de email
* Adicionar imagens do computador usando um seletor de arquivos local na barra de ferramentas de imagens
* Descreva o que você deseja e deixe que a IA gere a imagem perfeita para seu email
* Exporte o email concluído como um arquivo HTML do menu Mais
* As sugestões de cópia inteligente agora aparecem na barra de ferramentas de email ao editar o texto
* Clique em uma marca no quadro de campanha para exibir instantaneamente os detalhes da marca
* Defina seu kit de marca padrão diretamente da Biblioteca
* Agora os emails no editor seguem a sequência de fluxo de trabalho para obter uma ordem mais clara
* Anexos de arquivos de tela inicial agora são limitados a PDFs para um processamento confiável
* A navegação pelo teclado, o suporte ao leitor de tela e as preferências de movimento são mais consistentes no aplicativo
* Os rótulos de em breve marcam as páginas que estão sendo criadas ativamente
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 21 de maio de 2026**

* Editar imagens de email com o Adobe Express sem sair do editor
* Criar marcas com progresso claro enquanto os ativos são extraídos e publicados
* Gerenciar domínios e remetentes na seção Pessoas
* Procurar e gerenciar listas de contatos na seção Pessoas
* Alternar modelos de ativos ao trabalhar com ativos de marketing
* Baixar planos de campanha como arquivos do Word com diagramas de fluxo de trabalho
* Listas em campanhas, habilidades e fluxos de trabalho compartilham um layout mais claro
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 14 de maio de 2026**

* A Biblioteca reúne Assets, Modelos e Marcas em um único local
* A barra lateral e a navegação facilitam o acesso aos públicos-alvo e ao kit de marca padrão
* Baixe seu plano de campanha como um PDF diretamente dos detalhes da campanha
* A edição da marca abre painéis mais claros para visão geral, estilo de escrita e cores
* A contagem regressiva de avaliação aparece no cabeçalho para que os dias restantes permaneçam visíveis
* Os workflows de marketing esportivo estão prontos quando seu resumo se encaixa nessa categoria
* A configuração manual da avaliação lida com endereços de site da empresa de maneira mais previsível
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 8 de maio de 2026**

* O chat da campanha oferece uma tentativa clara quando uma verificação de tarefa em segundo plano falha
* Atualizações de status de tarefas e layout de tela cheia são mais suaves nos quadros de campanha
* O aplicativo é iniciado mais rapidamente carregando rotas e traduções conforme necessário
* Os dados de campanha e marca permanecem consistentes em todo o aplicativo
* Desfazer e refazer edições de email funcionam de forma mais previsível
* Tente salvar novamente quando o editor de email encontrar um erro temporário
* Substituir imagens de email com o dimensionamento correto e as dimensões do Adobe Express
* Fazer upload de listas de público-alvo do CSV usando uma caixa de diálogo de importação mais clara
* As tags de estilo de escrita se expandem para mostrar o texto completo e vincular à página da sua marca
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 6 de maio de 2026**

* Os quadros e as listas de campanha permanecem alinhados aos detalhes mais recentes enquanto você trabalha
* Um aviso de isenção de responsabilidade generativa clara é exibido no bate-papo da campanha e no Construtor de agentes
* Os detalhes de contato de suporte agora usam o endereço de email dedicado do CX Coworker Campaigns
* A página inicial de marketing remove a seção da lista de espera e mostra o vídeo principal com mais clareza
* Mais telas respeitam os formatos de idioma e data locais automaticamente
* Várias melhorias de desempenho e confiabilidade no

## Abril de 2026 {#apr-2026}

**Data de lançamento: 28 de abril de 2026**

* As listas e os quadros do Campaign permanecem sincronizados e se sentem mais ágeis ao abrir ou atualizar uma campanha
* Os fluxos de trabalho da página inicial agora são modelos de campanha com um fluxo de remix mais simples
* Temas escuros e claros usam o estilo atualizado do Spectrum para uma aparência mais consistente no aplicativo
* O Chat lida com o conteúdo vazio do assistente normalmente, com animações de status mais suaves e animações de status mais claras
* As conversas restauradas abrem sem um flash do painel de chat em branco, e a alternância de variantes de email não cintila mais o painel
* Os controles de upload de arquivo saem do caminho depois de enviar ou continuar a conversa
* &quot;Ajude-me a escrever&quot; obtém ideias de prompt somente depois que você abrir o popover
* As atualizações de status só mostram e expandem o controle quando há uma lista para revelar
* Os cartões em campanhas, habilidades e fluxos de trabalho compartilham um layout mais consistente
* As listas de campanha e os dados da marca são carregados de forma mais confiável logo após você entrar
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 19 de abril de 2026**

* O cabeçalho do aplicativo agora mostra apenas o assunto do email (ou &quot;Rascunho&quot;) ao editar um email, removendo o prefixo de número &quot;Email N:&quot; de um título mais limpo
* O menu de perfil foi movido para a barra lateral para obter acesso mais rápido
* Os documentos do Source PDF agora são exibidos como um preenchimento dos detalhes do kit da marca
* O menu de perfil foi movido para a barra lateral para obter acesso mais rápido
* Várias melhorias de desempenho e confiabilidade no

**Data de lançamento: 18 de abril de 2026**

* A entrada da campanha na página inicial agora tem um anel de brilho animado e um gradiente principal mais alto e mais brilhante
* &quot;Surpreenda-me&quot; aciona um brilho gradiente colorido na borda de entrada
* O aplicativo agora é compatível com um layout mais consistente nas páginas de produto
* Os links de documentação agora abrem o conteúdo mais recente diretamente em uma nova guia
* Várias melhorias de desempenho e confiabilidade no
