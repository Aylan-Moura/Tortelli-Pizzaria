# Guia de Envio de Mídias - Pizzaria Tortelli

Este documento estabelece as diretrizes técnicas e especificações recomendadas para o envio de arquivos de imagem e vídeo pelo cliente para utilização na landing page da Pizzaria Tortelli.

---

## 1. Diretrizes para Imagens (Fotos de Pizzas, Ambientes e Unidades)

Para garantir o equilíbrio ideal entre alta qualidade visual (nitidez nas pizzas e nos pratos) e tempo de carregamento rápido (Core Web Vitals), solicitamos que as fotos sigam as seguintes especificações:

- **Formatos Recomendados**: JPEG, PNG ou arquivos brutos (RAW/HEIC que serão convertidos para WebP/AVIF no deploy).
- **Resolução Mínima**:
  - *Banner Principal (Hero)*: Mínimo de 1920x1080 pixels (Proporção 16:9).
  - *Galeria de Produtos e Ambiente*: Mínimo de 1200x1200 pixels (Proporção 1:1 quadrada) ou 1200x900 pixels (Proporção 4:3).
- **Peso Máximo do Arquivo**:
  - Preferencialmente abaixo de **500 KB** por imagem otimizada.
- **Dicas de Produção**:
  - Fotografar com boa iluminação natural ou luz quente direcionada.
  - Evitar uso excessivo de filtros pesados para manter a fidelidade das cores dos ingredientes.

---

## 2. Diretrizes para Vídeos (Institucional / Destaque)

Os vídeos exibidos na landing page devem transmitir a experiência artesanal da pizzaria sem comprometer a fluidez de navegação em dispositivos móveis.

- **Formato Recomendado**: MP4 (Codec H.264 para máxima compatibilidade com navegadores).
- **Resolução Recomendada**: Full HD (1080p - 1920x1080).
- **Taxa de Quadros (FPS)**: 30 fps.
- **Áudio**: Vídeos de fundo (*autoplay*) devem ser entregues **sem áudio** (mudos) para conformidade com as políticas de autoplay dos navegadores.
- **Peso Máximo**:
  - Idealmente entre **10 MB e 20 MB**, com duração curta (10 a 30 segundos em loop).

---

## 3. Canal de Envio
Os arquivos devem ser compactados em pasta `.zip` e enviados via Google Drive, WeTransfer ou canal oficial de atendimento técnico da equipe de desenvolvimento.
