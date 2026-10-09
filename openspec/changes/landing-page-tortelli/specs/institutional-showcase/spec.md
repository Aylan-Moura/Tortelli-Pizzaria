# Spec Delta

## Purpose

Apresenta a identidade da Pizzaria Tortelli, a exibição detalhada de suas unidades (matriz e filial), vitrine multimídia de alta performance e conformidade com SEO local e LGPD.

## ADDED Requirements

### Requirement: Apresentação institucional e diferenciais da marca
A landing page SHALL exibir uma seção institucional de destaque contendo a história da Pizzaria Tortelli, o estilo artesanal das pizzas e os diferenciais de qualidade dos ingredientes e atendimento.

#### Scenario: Visualização da apresentação da marca
- **WHEN** o visitante acessa a página inicial
- **THEN** a história, os diferenciais e o estilo gastronômico da pizzaria SHALL ser renderizados com destaque visual e leitura clara.

### Requirement: Exibição individualizada das unidades (Matriz e Filial)
A landing page SHALL apresentar blocos de informação dedicados para a Matriz e para a Filial, contendo obrigatoriamente para cada unidade: nome da unidade, endereço completo, mapa interativo incorporado (Google Maps), horários de funcionamento discriminados por dia da semana, canais diretos de contato (telefone e link direto para WhatsApp) e descrição do ambiente e experiência de atendimento.

#### Scenario: Consulta de informações e localização da unidade
- **WHEN** o visitante navega até a seção de unidades
- **THEN** o sistema SHALL exibir blocos independentes para a Matriz e Filial com endereço completo, mapa interativo incorporado, tabela/lista de horários de funcionamento e botões clicáveis para contato direto.

### Requirement: Vitrine de mídia otimizada com galeria e vídeo
A landing page SHALL conter uma galeria de fotos destacando as pizzas, os ambientes e as duas unidades, além de seção de vídeo institucional em destaque. Todas as mídias visuais SHALL utilizar formatos modernos (WebP/AVIF para imagens, MP4/WebM otimizado para vídeos) com carregamento lento (*lazy loading*) para ativos fora da primeira dobra, garantindo conformidade com as métricas do Core Web Vitals.

#### Scenario: Carregamento eficiente de fotos e vídeos
- **WHEN** o usuário acessa a página em conexão móvel
- **THEN** as imagens e vídeos abaixo da dobra inicial SHALL ser carregados sob demanda (*lazy load*), mantendo a renderização inicial veloz e fluida.

### Requirement: Orientações técnicas para envio de mídias pelo cliente
O projeto SHALL disponibilizar uma documentação de especificações técnicas para o cliente contendo as diretrizes de envio de fotos e vídeos, detalhando formatos aceitos, resoluções recomendadas, limites de peso de arquivo e proporções (aspect ratio) adequadas para banners, galerias e destaques.

#### Scenario: Consulta de diretrizes de mídia pelo cliente
- **WHEN** o cliente for preparar e enviar os arquivos fotográficos e audiovisuais
- **THEN** a documentação técnica SHALL listar claramente as recomendações de resolução mínima, peso máximo em MB e formatos adequados para cada seção do site.

### Requirement: SEO local e marcação com dados estruturados
A landing page SHALL conter metadados semânticos completos de SEO local (títulos, descrições, Open Graph) e marcação estruturada em JSON-LD (`Schema.org` do tipo `Restaurant` ou `LocalBusiness`) contemplando individualmente os dados das duas unidades (endereço, telefone, coordenadas e horários).

#### Scenario: Rastreamento por mecanismos de busca
- **WHEN** robôs de busca indexarem a página
- **THEN** o código HTML SHALL conter blocos JSON-LD válidos com os dados estruturados de localização e funcionamento de ambas as unidades.

### Requirement: Aviso de privacidade e consentimento de cookies (LGPD)
A landing page SHALL disponibilizar um aviso de privacidade e consentimento de cookies em conformidade com a LGPD, visível para novos usuários antes do armazenamento de cookies analíticos não essenciais.

#### Scenario: Primeiro acesso do usuário
- **WHEN** um usuário visita o site pela primeira vez
- **THEN** um banner de consentimento de cookies SHALL ser exibido permitindo ao usuário aceitar ou gerenciar o uso de dados de navegação.
