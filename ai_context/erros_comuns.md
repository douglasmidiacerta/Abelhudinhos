# Erros Comuns e Soluções - Abelhudinhos

## Escopo do DOM em Carrosséis JS
- **Problema**: O conteúdo do carrossel (`feat-carousel`) pode piscar ou não carregar as animações de opacidade se os tempos dos timeouts não corresponderem à transição de CSS.
- **Solução**: Garantir que o valor em JS (`setTimeout`) esteja sincronizado com a classe `.ph-screen.fade` ou `opacity` no CSS, permitindo a transição visual suave.

## Responsividade de IFrames/Simuladores de Celular
- **Problema**: Em resoluções menores, os três celulares da seção `feat-phones` vazam a tela ou quebram o layout.
- **Solução**: Usar `@media` queries para esconder ou dimensionar os celulares das laterais (`.ph-side`), centralizando apenas a visualização principal em telas pequenas.

## Custom Properties e Cores
- **Problema**: Dificuldade em manter paleta consistente ou adaptar para tema escuro futuramente.
- **Solução**: O CSS original utiliza variáveis no `:root` (`--p`, `--dark`). Sempre utilizar estas variáveis ao invés de hardcodar hexadecimal novo.

## Race Conditions na Inicialização de Componentes Dinâmicos (JS)
- **Problema**: Componentes iterativos como "Jogo de Palavras" ou "Linha do Tempo" que dependem de injeção em containers no DOM, falhando esporadicamente porque o container não estava pronto ou estava usando `.innerHTML.trim() !== ''` para validação antes dos elementos existirem.
- **Solução**: Remover atrasos assíncronos desnecessários (como timeouts para buscar containers). Injetar o conteúdo diretamente e usar `children.length > 0` em vez de validação por string para verificar a inicialização do container.

## Ícones SVG Lucide em Conteúdo Injetado
- **Problema**: Os ícones (`<i data-lucide="..."></i>`) não aparecem quando são adicionados via JavaScript dinâmico (em modais, em arrays de features JS, em popups de mapa, ou roleta).
- **Solução**: Ao injetar HTML contendo ícones Lucide no DOM dinamicamente, é mandatório rodar a função global `lucide.createIcons()` logo após o elemento ser adicionado ao documento para que o framework transforme as tags `<i>` nos respectivos SVGs.

## Interatividade do Mapa Leaflet
- **Problema**: O mapa no slide "Jornada" não possuía zoom ou interação, parecendo estático e irritando o usuário.
- **Solução**: Ao configurar a instância do `L.map`, não forçar opções como `zoomControl: false`, `scrollWheelZoom: false` ou `dragging: false` caso se espere que o usuário tenha interação com a visualização espacial do mapa.
