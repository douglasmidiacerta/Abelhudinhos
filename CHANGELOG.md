# Changelog - Abelhudinhos

## [1.2.0] - 2026-05-03

### Adicionado
- **Nova Seção de Músicas Favoritas**: Criada uma aba no `presente.html` dedicada a listar faixas musicais do casal com um visual moderno que remete a playlists do Spotify (Capa, Título, Artista e botão de play).
- **Biblioteca Lucide Icons**: Todos os emojis de layout estrutural (Landing Page e Presente) foram substituídos por ícones vetorizados escaláveis nativos (`<i data-lucide="...">`).

### Corrigido e Melhorado
- **Jogo de Palavras (Correção Crítica)**: Corrigida falha silenciosa que não renderizava a grade e teclado devido à ausência do ID `wg-hint` no DOM do HTML.
- **UX (Navegação):** Botões "Próxima Seção" nos slides interativos (Roleta e Jogo de Palavras) agora permanecem visíveis o tempo todo, permitindo que o usuário avance independentemente de ter completado a interação.

## [1.1.0] - 2026-05-03

### Corrigido (presente.html)
- **Navegação (Toques Indesejados)**: Implementada lógica dinâmica que desabilita o toque nas margens (nav-left e nav-right) quando o usuário entra em seções interativas (Jogo de Palavras, Roleta, Mapa e Galeria).
- **Roleta Surpresa**: Corrigido o offset angular de cálculo da fatia vencedora na roleta. Agora a matemática reconhece corretamente a opção que parou embaixo do cursor.
- **Auto-Avanço (Timer)**: O timer da barra superior agora é barrado também nas seções de Galeria e Mapa (além das outras interativas), para não avançar enquanto o usuário explora.
- **Áudio Placebo**: Implementada integração real do botão de som, reproduzindo trilha instrumental ("mixkit-romantic-piano-122") em loop a partir do primeiro slide após a capa.
- **Jogo de Palavras**: A `secretWord` agora é sanitizada e tem seus acentos removidos na memória (ex: "VOCÊ" vira "VOCE") para permitir adivinhação sem falhas com o teclado base sem acentos.

## [1.0.0] - Versão Inicial
### Adicionado
- Landing page principal (`index.html`) concluída.
- Plataforma de demonstração de presente digital (`presente.html`) implementada com UI simulada de Stories, incluindo carrossel de fotos, linha do tempo, jogo da forca (Wordle) e roleta animada.
