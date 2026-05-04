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
