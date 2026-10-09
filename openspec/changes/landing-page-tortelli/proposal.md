# Proposal

## Why

A Pizzaria Tortelli precisa de uma presença online institucional focada em conversão para suas duas unidades (matriz e filial). O principal gargalo atual é a dispersão de clientes locais que buscam contato ou pedidos sem um canal centralizado e otimizado para celular. A landing page resolverá isso apresentando a história, diferenciais, mídia e informações de cada unidade, direcionando de forma ostensiva e contínua os clientes para o aplicativo proprietário de pedidos.

## What Changes

- Criação da estrutura de landing page institucional responsiva (mobile-first).
- Seção de apresentação institucional com história, diferenciais e estilo das pizzas artesanais.
- Seção dedicada para as duas unidades (Matriz e Filial) contendo endereço completo, mapa interativo incorporado, horário de funcionamento, contatos (telefone/WhatsApp) e descrição do ambiente.
- Vitrine de mídia rica com galeria de fotos e vídeo de destaque, com otimizações de performance (lazy loading e formatos modernos).
- Guia de especificações e recomendações técnicas para envio de arquivos de mídia pelo cliente (peso, resolução e formatos).
- Sistema de conversão e redirecionamento contínuo para o aplicativo de pedidos: botões de ação (CTAs), barra/botão fixo flutuante em dispositivos móveis e links para lojas (App Store, Google Play e versão web).
- Rodapé institucional com redes sociais, canais de atendimento e avisos legais.
- Implementação de SEO local com dados estruturados (`Schema.org` `LocalBusiness`) para ambas as unidades.
- Banner de conformidade com a LGPD (política e consentimento de cookies).
- Rastreamento de métricas e conversão analítica para monitorar cliques nos CTAs de pedido.

## Capabilities

### New Capabilities
- `institutional-showcase`: Apresentação institucional da pizzaria, detalhes e localização das duas unidades (matriz e filial), vitrine de mídia (fotos/vídeos), SEO local estruturado e banner de cookies LGPD.
- `order-redirection`: Elementos de conversão com CTAs contextuais, botão fixo mobile, links para download do app/versão web e instrumentação de eventos analíticos para rastreamento de cliques.

### Modified Capabilities
*(Nenhuma capacidade existente foi modificada, pois este é o início do projeto).*

## Impact

- **Código e Arquitetura**: Novo projeto web frontend estático/JAMstack otimizado para Core Web Vitals e dispositivos móveis.
- **Dependências e Ferramentas**: Integrações externas para mapas (Google Maps Embed), biblioteca de analytics/GTM para rastreamento de eventos, e assets de mídia otimizados.
- **Escopo**: Focado estritamente na landing page e redirecionamento; não inclui carrinho de compras, cardápio interativo com pedidos nem checkout/pagamento no site.
