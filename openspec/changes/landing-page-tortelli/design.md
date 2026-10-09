# Design

## Context

O projeto consiste na criação da landing page institucional da Pizzaria Tortelli, com foco em mobile-first e conversão para o aplicativo oficial de pedidos. Trata-se de um projeto novo (*greenfield*). Para motivação e contexto do negócio, consulte `proposal.md`. Para os requisitos normativos de comportamento, consulte as especificações em `specs/`.

## Goals / Non-Goals

**Goals:**
- Proporcionar arquitetura web de alta performance voltada para dispositivos móveis, com foco em métricas de Core Web Vitals (LCP < 2.5s, CLS < 0.1).
- Estruturar componentes modulares para: Seção Hero com CTA de impacto, História & Diferenciais, Cards individuais das Unidades (Matriz e Filial) com mapas interativos, Galeria de Mídia e Vídeo, Rodapé e Banner de Consentimento LGPD.
- Manter presença persistente de conversão com botão flutuante/fixo na visualização mobile.
- Incorporar metadados semânticos e dados estruturados JSON-LD (`LocalBusiness` / `Restaurant`) para indexação em buscas locais (Google Busca e Google Maps).
- Estabelecer diretrizes técnicas claras em documentação dedicada para o envio de fotos e vídeos pelo cliente.

**Non-Goals:**
- Não haverá sistema de carrinho de compras, montagem de pizzas online ou catálogo transacional no site.
- Não haverá gateway de pagamento ou autenticação de usuários na landing page.

## Decisions

### 1. Stack Tecnológico e Abordagem de Construção
- **Decisão**: Utilizar uma base estática moderna e leve (HTML5 semântico, Tailwind CSS ou CSS moderno utilitário, e JavaScript modular puro / Vanilla JS ou gerador estático como Astro/Vite).
- **Racional**: Garante TTFB mínimo, facilidade extrema de hospedagem (Vercel, Netlify, Cloudflare Pages), pontuação máxima no Lighthouse e ausência de complexidade desnecessária de SSR ou servidores backend.
- **Alternativas consideradas**:
  - *Next.js / SPA pesada*: Descartado por adicionar sobrecarga de JavaScript e tempo de hidratação desnecessários para uma página institucional de conversão.
  - *WordPress*: Descartado pela complexidade de manutenção, vulnerabilidades de segurança e maior dificuldade para manter pontuação de Core Web Vitals alta.

### 2. Integração e Apresentação das Unidades (Matriz e Filial)
- **Decisão**: Criar blocos de componentes independentes e simétricos para Matriz e Filial, contendo:
  - Título e identificação visual da unidade.
  - Endereço formatado com link direto para rota no Google Maps.
  - Mapa embutido via `<iframe>` do Google Maps com atributo nativo `loading="lazy"`.
  - Horários detalhados dia a dia em tabela/lista semântica acessível.
  - Botão de contato rápido integrado via URL scheme do WhatsApp (`https://wa.me/...`).
- **Racional**: O cliente local decide rapidamente qual unidade está mais próxima ou aberta no momento, com atalhos diretos para deslocamento ou contato.

### 3. Otimização de Mídias e Guia do Cliente
- **Decisão**: 
  - Na implementação web: Utilizar tags `<picture>` com suporte a WebP/AVIF e fallback JPEG/PNG, dimensões explícitas (`width`/`height`) e `aspect-ratio` via CSS para prevenir Cumulative Layout Shift (CLS). Implementar carregamento postergado (`loading="lazy"`) para todas as mídias fora da primeira dobra.
  - No guia de mídia: Criar um documento técnico (`docs/guia-envio-midias.md`) especificando:
    - Imagens: Proporção recomendada (16:9 para banners, 4:3 ou 1:1 para pizzas/ambiente), resolução mínima de 1920x1080 (hero) e 800x800 (galeria), peso máximo sugerido de 500KB por imagem.
    - Vídeo: Formato MP4 (codec H.264), resolução Full HD (1080p), sem áudio ou com áudio mudo padrão para autoplay de fundo, peso máximo sugerido de 15MB a 20MB.

### 4. Arquitetura de Conversão (CTAs e Botão Fixo Mobile)
- **Decisão**:
  - Implementar um botão CTA de pedido fixo na base da tela (*sticky bottom bar* ou *floating action button*) ativo exclusivamente em viewports móveis (`< 768px`).
  - Posicionar CTAs principais na dobra inicial (Hero), nos cards de cada unidade e na seção final antes do rodapé.
  - Disponibilizar modal ou seção de badges oficiais das lojas (Google Play, Apple App Store) e atalho para o Web App.
- **Racional**: Em dispositivos móveis, a qualquer momento da rolagem o usuário pode converter com apenas 1 toque, sem precisar retornar ao topo.

### 5. Rastreamento Analítico e Disparo de Eventos
- **Decisão**: Utilizar uma camada de eventos baseada em data-attributes (ex.: `data-track="order_click"`, `data-unit="matriz"`), disparando eventos customizados para `window.gtag` ou `dataLayer` do Google Analytics/Tag Manager.
- **Racional**: Permite desacoplar a marcação visual da lógica de monitoramento analítico e possibilita a medição precisa da taxa de cliques em pedidos por unidade.

### 6. Conformidade com LGPD
- **Decisão**: Desenvolver um componente de banner de consentimento leve, persistindo a escolha no `localStorage`. Scripts de terceiros não essenciais (ex.: rastreamento de anúncios) aguardam o consentimento explícito.

## Risks / Trade-offs

- **[Risco] Mídias pesadas enviadas pelo cliente impactando o tempo de carregamento**
  - *Mitigação*: Criação prévia do guia de envio de mídias, compressão com ferramentas modernas e carregamento sob demanda (*lazy load*).
- **[Risco] Iframe do Google Maps bloquear a renderização inicial**
  - *Mitigação*: Uso de `loading="lazy"` e renderização assíncrona; em conexões mais lentas, manter um card estático com botão de abrir no mapa como alternativa.
- **[Risco] Usuário esperar fazer o pedido diretamente na página institucional**
  - *Mitigação*: Textos e microcopy claros nos botões (ex.: "Peça pelo nosso App", "Baixe o App e Peça Agora"), estabelecendo a expectativa correta logo no primeiro contato.

## Migration Plan

1. Estruturação dos arquivos base do projeto estático (HTML, CSS/Tailwind, JavaScript).
2. Construção dos componentes e validação em navegadores desktop e móveis.
3. Testes de pontuação de Core Web Vitals (Lighthouse) e validação de dados estruturados com o Rich Results Test do Google.
4. Deploy automatizado em plataforma estática com certificado SSL habilitado.
