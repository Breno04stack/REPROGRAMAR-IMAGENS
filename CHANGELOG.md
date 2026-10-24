# Changelog

## v5.0.0 — 2026-10-24

- adicionado marketplace padrão para novos arquivos;
- adicionado marketplace individual por item da fila;
- adicionados perfis de Mercado Livre, Shopee, TikTok Shop, SHEIN, Amazon, Outros e Sem perfil;
- adicionadas dimensões personalizadas para Outros marketplaces;
- adicionado modo Encaixar sem cortar;
- adicionado modo Preencher e cortar;
- adicionada cor de fundo configurável;
- adicionado botão para duplicar a mesma imagem para vários destinos;
- adicionada organização em subpastas por marketplace;
- ZIP e relatório CSV agora registram o perfil de destino;
- preservada a numeração contínua e persistente;
- preservado o botão Reiniciar numeração;
- preservados processamento em lote, pasta de saída, limite de tamanho, diferença mínima e validação de qualidade.

## v4.1.0 — 2026-08-21

- adicionada numeração contínua persistente;
- arquivos renomeados como `0001`, `0002`, `0003`...;
- adicionado botão Reiniciar numeração;
- removido `binary-refresh` dos nomes de saída;
- ZIP renomeado para `imagens.zip`.

## v4.0.0 — 2026-08-21

- seleções múltiplas acumuladas na fila;
- importação de pasta inteira;
- status individual por arquivo;
- processamento sequencial robusto;
- erros isolados não interrompem o lote;
- seleção e salvamento em pasta autorizada;
- ZIP como alternativa universal;
- documentação inicial para módulo de vídeos.

## v3.0.0 — 2026-08-21

- tamanho máximo configurável;
- diferença mínima de pixels;
- PSNR mínimo;
- compressão e formato adaptativos;
- redução de dimensões como último recurso;
- nome baseado no hash final antes da adoção da numeração contínua.
