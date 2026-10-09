# Spec Delta

## Purpose

Gerencia os fluxos de conversão e direcionamento de usuários da landing page para o aplicativo de pedidos da pizzaria, garantindo presença contínua de CTAs e mensuração de cliques.

## ADDED Requirements

### Requirement: Botões de chamada para ação (CTAs) e botão flutuante mobile
A landing page SHALL apresentar botões de chamada para ação (Call to Action - CTA) para pedidos distribuídos estrategicamente ao longo da página (seção principal/hero, blocos das unidades e rodapé). Em dispositivos móveis, a interface SHALL manter um botão CTA fixo/flutuante continuamente visível durante a rolagem de tela.

#### Scenario: Rolagem de página em dispositivo móvel
- **WHEN** o visitante rola a página em um dispositivo móvel
- **THEN** um botão de ação destacado ("Peça Agora" / "Fazer Pedido") SHALL permanecer fixo na tela para acesso imediato ao aplicativo.

### Requirement: Redirecionamento multicanal para aplicativo e versão web
A landing page SHALL disponibilizar links claros e funcionais para direcionar o usuário para as lojas de aplicativos (Apple App Store e Google Play Store) bem como para a versão web do aplicativo de pedidos.

#### Scenario: Clique em link de download ou acesso ao app
- **WHEN** o visitante clica no botão de direcionamento para o aplicativo ou link das lojas
- **THEN** o navegador SHALL abrir o link correspondente da respectiva plataforma ou iniciar o redirecionamento para o sistema de pedidos externo.

### Requirement: Rastreamento analítico de conversões e cliques
A landing page SHALL integrar disparos de eventos de rastreamento (Google Analytics ou plataforma equivalente) para registrar todos os cliques nos botões de CTA, links de lojas de aplicativos e botões de WhatsApp de cada unidade.

#### Scenario: Rastreamento de clique de conversão
- **WHEN** o visitante aciona qualquer botão ou link que redireciona para o aplicativo ou contato
- **THEN** o sistema SHALL disparar um evento analítico registrando a origem do clique e o destino do pedido.

### Requirement: Delimitação de escopo estritamente institucional sem checkout local
A landing page SHALL funcionar exclusivamente como ponte institucional e de redirecionamento, não devendo conter carrinho de compras, finalização de pedidos local nem sistema de cobrança/pagamento incorporado.

#### Scenario: Interação com fluxo de pedidos
- **WHEN** o visitante manifestar intenção de compra
- **THEN** a interface SHALL encaminhá-lo para a plataforma/aplicativo de pedidos externa, sem processar transações financeiras na landing page.
