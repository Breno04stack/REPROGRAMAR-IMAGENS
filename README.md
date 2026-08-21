# Image Binary Refresh v3

Ferramenta web estática, executada inteiramente no navegador, para processar imagens em lote.

## Requisitos atendidos

- mínimo configurável de pixels diferentes, com padrão de **1%**;
- verificação da imagem final depois da codificação;
- cada arquivo de saída fica abaixo de **1,95 MB** por padrão e sempre abaixo de 2.000.000 bytes;
- tentativa inicial em PNG sem perdas;
- fallback automático para JPG em imagens opacas e WebP em imagens com transparência;
- busca da maior qualidade possível dentro do limite;
- redução gradual das dimensões apenas quando necessária;
- remoção de metadados comuns por reconstrução do arquivo;
- SHA-256 antes e depois;
- relatório CSV;
- ZIP criado pelo próprio código, sem dependências externas.

## Como atualizar no GitHub Pages

1. Substitua o `index.html` atual do repositório por este arquivo.
2. Faça o commit na branch `main`.
3. Aguarde o GitHub Pages publicar a nova versão.
4. Faça um recarregamento forçado no navegador: `Ctrl + Shift + R` ou `Cmd + Shift + R`.

## Estratégia de pixels

A ferramenta aplica micro-padrões geométricos distribuídos. Cada pixel selecionado recebe uma alteração de 1 a 4 níveis em apenas um canal RGB, preservando a textura local. Em seguida, o arquivo é codificado, reaberto e comparado com a imagem de referência. A saída só é aprovada quando o percentual final de pixels diferentes atinge o mínimo configurado.

## Estratégia de tamanho

1. Tenta PNG sem perdas.
2. Se ultrapassar o limite, usa JPG para imagens opacas ou WebP para imagens com transparência.
3. Faz busca binária pela maior qualidade que caiba no limite.
4. Se ainda não couber com qualidade visual mínima, reduz as dimensões em etapas de 10% e tenta novamente.

## Observação

Alterar o arquivo e pelo menos 1% dos pixels não impede sistemas de reconhecimento visual ou perceptual hash de relacionarem imagens com o mesmo conteúdo.
