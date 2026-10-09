# Tasks

## 1. Estrutura Base e Configuração do Projeto

- [x] 1.1 Configurar a estrutura base do projeto frontend (HTML5 semântico, estilos Tailwind/CSS e scripts modulares) e verificar a inicialização no servidor de desenvolvimento local.
- [x] 1.2 Criar arquivo central de configuração e dados (`data/content.json` ou equivalente) contendo as informações das unidades, links dos aplicativos e telefones, e verificar a correta injeção dos dados no template.

## 2. Apresentação Institucional e Vitrine de Mídia

- [x] 2.1 Desenvolver a seção Hero de boas-vindas e a apresentação institucional (história, tradição artesanal e diferenciais da Tortelli), verificando hierarquia visual e responsividade mobile-first.
- [x] 2.2 Implementar a galeria de fotos e a seção de vídeo institucional com suporte a tags `<picture>`, formatos modernos (WebP/AVIF), proporções fixas anti-CLS e atributo `loading="lazy"`, verificando auditoria de performance.
- [x] 2.3 Produzir o documento de diretrizes técnicas para o cliente (`docs/guia-envio-midias.md`) com resoluções, formatos e limites de peso de arquivos recomendados, verificando a clareza e completude das orientações.

## 3. Seção das Unidades (Matriz e Filial)

- [x] 3.1 Construir os cards informativos individualizados da Matriz e Filial contendo endereço formatado, horários de funcionamento por dia da semana e botões de contato direto (WhatsApp e telefone), verificando os links em navegadores móveis e desktop.
- [x] 3.2 Incorporar os mapas interativos do Google Maps para ambas as unidades com carregamento postergado (`loading="lazy"`), verificando que o carregamento dos iframes não degrada a primeira dobra da página.

## 4. Redirecionamento e Conversão para o Aplicativo

- [x] 4.1 Implementar os botões de chamada para ação (CTAs) principais e badges/links de direcionamento para App Store, Google Play e Web App, verificando o correto direcionamento para os links externos.
- [x] 4.2 Desenvolver o botão flutuante/barra fixa de CTA para dispositivos móveis (`< 768px`), verificando sua visibilidade contínua durante toda a rolagem de tela e comportamento não invasivo.
- [x] 4.3 Implementar o módulo de rastreamento de eventos analíticos baseado em `data-attributes` para disparar eventos de clique de conversão por unidade e botão, verificando a emissão no console e dataLayer.

## 5. SEO Local, Rodapé e Conformidade LGPD

- [x] 5.1 Adicionar tags meta de SEO local (Open Graph, descrição geográfica) e blocos JSON-LD estruturados (`Schema.org` `Restaurant`) contemplando matriz e filial, verificando validação semântica com ferramenta de teste de dados estruturados.
- [x] 5.2 Desenvolver o rodapé institucional com links de redes sociais, dados cadastrais e canais de atendimento, verificando acessibilidade de contraste e navegação por teclado.
- [x] 5.3 Implementar o componente de aviso de cookies e privacidade (LGPD) com persistência de preferência via `localStorage`, verificando a exibição no primeiro acesso e ocultação após o aceite do usuário.