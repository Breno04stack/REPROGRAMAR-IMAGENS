# Image Binary Refresh v2

Aplicação web estática para processar várias imagens sem separar pastas.

## Novidades da v2

- corrige o fluxo para baixar o arquivo realmente processado;
- exige `SHA-256 original != SHA-256 novo`;
- pode operar em dois modos:
  - **pixels idênticos**: mantém a imagem decodificada exatamente igual;
  - **pixels diferentes** (padrão): adiciona microformas geométricas discretas com cor muito próxima ao fundo para alterar poucos pixels;
- mostra quantos pixels mudaram;
- gera ZIP com `relatorio.csv`.

## Como publicar no GitHub Pages

1. Substitua o `index.html` antigo por este novo.
2. Faça commit.
3. O GitHub Pages atualizará automaticamente.

## Observação

A ferramenta muda o arquivo binário e, se o modo padrão estiver ligado, altera poucos pixels de forma quase imperceptível. Isso não impede completamente sistemas de reconhecimento visual de associarem as imagens pelo conteúdo geral.
