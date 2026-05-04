# Changelog - Abelhudinhos

## [1.8.0] - 2026-05-04

### Corrigido / Finalizado
- **Remoção definitiva de nomes estáticos**: O Mapa das Estrelas agora usa "Nosso Amor" como padrão e sincroniza corretamente com o `CONFIG`, eliminando os nomes "Edu e Ana" que estavam hardcoded.
- **Sincronização de Coordenadas**: As coordenadas padrão do Mapa das Estrelas agora refletem o início da jornada em Juatuba, MG (29/11/2025), conforme solicitado.
- **Robustez na Interação**: Adicionados listeners de carregamento global para garantir que a Roleta e o Player de Música inicializem corretamente mesmo em conexões lentas.

## [1.7.0] - 2026-05-04

### Corrigido / Melhorado
- **Jornada no Mapa (Tela Cheia)**: O mapa da jornada agora ocupa a tela inteira, proporcionando uma navegação muito mais imersiva.
- **Mapa das Estrelas Customizável**: Nomes e coordenadas agora são lidos do objeto `CONFIG`, permitindo ajustes fáceis pelo usuário.
- **Correção na Roleta**: Corrigido bug que impedia o giro e ajustada a lógica de cálculo do resultado para maior precisão.
- **Player de Música (Correção)**: Adicionado tratamento de erro para reprodução de áudio, garantindo que o play funcione após a interação do usuário.
- **Variedade na Galeria**: Legendas e localizações das fotos foram revisadas para remover repetições e tornar a jornada mais dinâmica.

## [1.6.0] - 2026-05-04

### Adicionado / Modificado
- **Galeria Tinder-style**: O feed do Instagram foi substituído por cards em tela cheia com arraste lateral (scroll-snap), trazendo uma experiência mais imersiva e parecida com o Tinder/Stories.
- **Player de Música Customizado**: Os iframes pequenos do Spotify foram substituídos por um player nativo em tela cheia, controlando o áudio de fundo com barra de progresso, botões de play/pause e design similar ao Spotify.
- **Mapa das Estrelas**: A exibição agora é tela inteira. Adicionada uma animação em SVG que desenha as conexões da constelação ao abrir o slide.
- **Roleta Surpresa**: O tamanho do componente na tela foi ampliado de 220px para 300px, melhorando a visibilidade e toque em dispositivos móveis.

## [1.5.0] - 2026-05-04

### Adicionado
- **Galeria Instagram**: O visual de polaroids foi substituído por um feed escuro inspirado no Instagram, contendo foto de perfil, botão de like, localização e comentários.
- **Integração Real com Spotify**: A lista de músicas favoritas foi convertida em reprodutores autênticos do Spotify, permitindo dar play na música diretamente da página.

### Corrigido
- **Botões de Navegação Presos**: As setas de "Próximo" e "Anterior" foram separadas da zona de clique invisível, garantindo que sempre funcionem mesmo nas abas de interatividade complexa (Roleta, Wordle, Mapa, etc).

## [1.4.0] - 2026-05-04

### Adicionado
- **Funil de Conexão (O Que Devemos Saber)**: Implementada uma nova seção massiva de interatividade em forma de cartões (Nível 1, 2 e 3) contendo as principais curiosidades, alinhamentos e preferências do casal, projetada com grid responsivo e cores temáticas (Ele x Ela).
- **Trilha Sonora**: Adicionada a faixa "Eu te escolheria todo dia" como música favorita principal da playlist interativa.

## [1.3.0] - 2026-05-04

### Adicionado
- **Botões de Navegação**: Adicionados botões visíveis de seta ("chevron-left" e "chevron-right") nas bordas da tela no `presente.html` para pular entre os slides facilmente.

### Corrigido e Melhorado
- **Migração Completa para Lucide SVG**: Todos os emojis nativos foram substituídos definitivamente por ícones Lucide no `index.html` e `presente.html`.
- **Nossa Jornada**: Corrigido o bug onde a timeline não renderizava devido a falha na lógica de verificação de preenchimento (`children.length > 0`).
- **Jogo de Palavras**: Removida a condição de corrida (race conditions) causada por timeouts e timeouts desnecessários, resolvendo o bug onde o componente não inicializava.
- **Mapa Interativo**: Habilitada a interatividade (zoom e pan) no componente de mapa com `Leaflet.js`.
- **Roleta**: O resultado da roleta agora renderiza corretamente ícones de SVG através de injeção assíncrona (`lucide.createIcons()`).

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
