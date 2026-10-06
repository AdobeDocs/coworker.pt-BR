---
description: 'Saiba mais sobre as Campanhas do colega de trabalho que geram práticas recomendadas: a estrutura CO-STAR, o que fazer e o que não fazer, o conteúdo não suportado e uma lista de verificação de qualidade para prompts.'
title: Práticas recomendadas de criação de prompts
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: ee66c1cc95ef1dd8c5e45c1fcb699547e63b9c8a
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 1%
---
# Solicitação de práticas recomendadas {#best-practices}

Aproveitar ao máximo as Campanhas de colega de trabalho começa com o modo como você solicita. Conheça as práticas que produzem os melhores resultados: a estrutura CO-STAR para estruturar seus prompts, o que incluir e o que evitar, e exemplos baseados em cenários que dão à IA o contexto necessário para gerar conteúdo relevante no destino.

>[!NOTE]
>
>Atualmente, você só pode se conectar a integrações compatíveis com o Co-worker Campaigns. Se você tiver algum aplicativo Adobe Enterprise existente, em que armazene públicos ou compile jornadas, recomendamos que você use o [CX Enterprise Coworker](/help/chat/use-cases/overview.md).

## Usar a estrutura CO-STAR

Para obter melhores resultados, organize seus prompts usando a estrutura CO-STAR. Essa abordagem estruturada garante que a IA entenda exatamente o que você precisa.

| Componente | O que significa | Por que isso importa |
|-|-|-|
| **C - Contexto** | Histórico de sua campanha, produto ou situação | Ajuda a IA a entender o cenário geral |
| **O - Objetivo** | Sua meta de marketing específica | Orienta o que o conteúdo deve alcançar |
| **S - Estilo** | Como você deseja se comunicar | Define a abordagem |
| **T - Tom** | Estilo emocional e voz | Forma como a mensagem é exibida |
| **A - Público** | Público-alvo que você está direcionando | Garante que a mensagem repercuta com as pessoas certas |
| **R - Requisitos** | Restrições específicas ou must-haves | Define limites e elementos críticos |

## Fundamentos do prompt de IA

### Fazer e não fazer

<table style="table-layout: fixed; width: 100%; border: 0;">
<thead style="border: 0; background-color: #FFFFFF;">
<tr>
<th>Fazer</th>
<th>Não</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<p>Usar a estrutura CO-STAR para a estrutura</p>
<p>Concentre-se nos resumos de marketing com orientação específica para extração</p>
<p>Esboçar suas solicitações para produzir a intenção desejada</p>
</td>
<td>
<p>Solicitar alterações estruturais, estilo ou edição de imagem em prompts</p>
<p>Use instruções vagas como "promover nosso produto"</p>
<p>Esperar modificações de layout por meio de prompts</p>
</td>
</tr>
</tbody>
</table>

### Conteúdo suportado em prompts

Use o **editor de email** ou o **Adobe Express** para modificações visuais/de imagem. Os tipos de solicitação a seguir são compatíveis.

- **Especifique a frequência e a cadência da sua campanha**: &quot;Crie uma campanha de email que seja enviada semanalmente...&quot;

- **Direcione um público-alvo específico de uma lista maior**: &quot;Crie uma campanha somente para participantes com cachorros para o evento _Bark in the Park_ de &#39;all-attendees.csv&#39;&quot;

- **Carregar um arquivo do HTML**: &quot;Use meu arquivo do HTML anexado como base para criar uma campanha de email.&quot;

- **Faça alterações no meio da conversa**: &quot;Altere o número de dias antes que esta campanha saia de dois para três.&quot;

### Conteúdo não suportado em prompts

Estas solicitações **não** têm suporte e devem ser tratadas por meio de outras ferramentas:

<table style="table-layout: fixed; border: 0;">
<thead style="border: 0; background-color: #FFFFFF">
<tr>
<th>modificações na estrutura do email</th>
<th>Alterações no estilo visual</th>
<th>Operações do editor- interno@ info: tooltip</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<ul>
<li>Selecionar seções específicas para alterar</li>
<li>Exclusão ou clonagem de elementos</li>
<li>Seleções condicionais</li>
<li>Adição ou remoção de seções de layout</li>
</ul>
</td>
<td>
<ul>
<li>Fontes personalizadas</li>
<li>Modificações de cores</li>
<li>Estilo de layout (bordas, preenchimento, margens)</li>
<li>Efeitos visuais (sombras)</li>
</ul>
</td>
<td>
<ul>
<li>Alterações de fundo</li>
<li>Adicionar sobreposições de texto ou logotipos</li>
<li>Recorte ou redimensionamento de imagem</li>
<li>Ajustes de cor</li>
</ul>
</td>
</tr>
</tbody>
</table>

### Lista de verificação de qualidade

Antes de gerar o conteúdo, verifique o seguinte:

✓ **Limpar objetivo**: indica claramente a ação, o produto/serviço, o valor e o contexto.

✓ **Público-alvo definido**: especifica a demografia, a função ou o segmento.

✓ **Marca correta atribuída como padrão**: as diretrizes de marca apropriadas estão selecionadas.

✓ **Escopo realista**: evitar solicitações de alterações de layout, estilo ou edições estruturais.

## Exemplos de prompt baseados em cenário

Sempre forneça contexto e a proposta de valor para que a IA possa gerar conteúdo relevante.

>[!NOTE]
>
>Embora atualmente você só possa gerar e iniciar campanhas de email, você sempre pode pedir ao Colaborador para gerar uma cópia para mídias sociais, WhatsApp ou SMS.

<table style="table-layout: fixed; border-collapse: collapse; border: 0;">
<thead>
<tr style="border: 0;background-color: #FFFFFF;">
<th>Setor</th>
<th>Exemplo de prompt</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Tecnologia B2B</strong></td>
<td>"Gere uma campanha de e-mail de quatro toques para demonstrar o ROI e as especificações técnicas enquanto lida com as preocupações de segurança para os tomadores de decisão de TI que avaliam nossa solução de infraestrutura em nuvem, enfatizando 99,9% de tempo de atividade do SLA, conformidade com SOC 2 e 40% de economia de custos."</td>
</tr>
<tr>
<td><strong>Varejo de comércio eletrônico</strong></td>
<td>"Gere uma campanha de toque único para criar urgência em torno de itens de feriado de estoque limitado, destacando o frete gratuito e retornos fáceis para compradores de última hora, enfatizando quantidades limitadas (menos de 50 restantes) e corte de frete de 24 horas."</td>
</tr>
<tr>
<td><strong>Educação e treinamento</strong></td>
<td>"Gere uma campanha de dois contatos que enfatize os resultados do avanço da carreira e as certificações do setor e, ao mesmo tempo, mostre a experiência do instrutor, destacando a taxa de 92% de colocação em cargos e o currículo baseado em projetos."</td>
</tr>
<tr>
<td><strong>Consultoria</strong></td>
<td>"Gere uma campanha de três contatos para promover clientes potenciais, apresentando três histórias de sucesso de clientes com métricas detalhadas de ROI (IBM: 45% de redução de custos, Accenture: 200% de aumento de lead, Microsoft: 60% de economia de tempo), direcionando diretores de TI para empresas com mais de 1.000 funcionários."</td>
</tr>
</tbody>
</table>

## Ideias gerais de prompts de marketing

### Marketing de conteúdo

- &quot;Gerar 20 tópicos de blog que respondam a perguntas comuns de compradores de casa pela primeira vez.&quot;
- &quot;Brainstorm LinkedIn postou ideias para uma start-up de segurança cibernética B2B.&quot;
- &quot;Crie um calendário de conteúdo de três meses com foco na educação de novos clientes.&quot;
- &quot;Sugira temas de conteúdo que podem ser redefinidos em blogs, vídeos, boletins informativos e postagens sociais.&quot;

### Marketing por email

- &quot;Gerar uma sequência de email de boas-vindas para novos assinantes interessados em moda sustentável.&quot;
- &quot;Elementos de assunto do debate que criam curiosidade sem soar como clickbait.&quot;
- &quot;Sugira ideias de campanha de reengajamento para clientes inativos.&quot;
- &quot;Crie ideias de e-mail de ciclo de vida para usuários que concluíram a integração.&quot;

>[!MORELIKETHIS]
>
>Procure mais [padrões de prompt](use-cases.md) para Campanhas de Colaborador.
