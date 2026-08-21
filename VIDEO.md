# Processamento de vídeos

## É possível?

Sim. O equivalente para vídeo envolve:

1. decodificar o vídeo;
2. remover metadata do contêiner;
3. reencodar vídeo e áudio;
4. mudar GOP, keyframes, bitstream e timestamps internos;
5. opcionalmente aplicar uma alteração visual muito pequena nos frames;
6. calcular o SHA-256 do arquivo final;
7. salvar em MP4 ou WebM.

## Arquitetura recomendada

Para manter tudo local no navegador, use `ffmpeg.wasm` em uma página separada, por exemplo `video.html`.

Fluxo recomendado:

- entrada: MP4, MOV, WebM ou MKV;
- saída padrão: MP4 com H.264 e áudio AAC;
- remoção de metadata: `-map_metadata -1 -map_chapters -1`;
- qualidade visual: CRF configurável;
- alteração sutil de frames: filtro de ruído muito baixo ou micro-overlay discreto;
- otimização de reprodução: `-movflags +faststart`;
- processamento sequencial de vários vídeos;
- salvamento na mesma pasta escolhida pela File System Access API.

## Limitações importantes

- o núcleo WebAssembly precisa ser baixado antes do primeiro uso;
- vídeo consome muito mais memória e CPU que imagem;
- arquivos grandes podem travar ou exceder a memória da aba;
- o processamento no navegador tende a ser mais lento que FFmpeg instalado no computador ou executado em servidor;
- garantir menos de 2 MB depende diretamente da duração do vídeo;
- um vídeo longo só cabe em 2 MB com bitrate, resolução, frame rate ou áudio reduzidos;
- a validação de “1% de pixels diferentes” deve ser feita por amostragem de frames ou pela análise completa de todos os frames, que é muito mais custosa.

## Tamanho de vídeo

Para um alvo aproximado de tamanho:

`bitrate total ≈ tamanho em bits ÷ duração em segundos`

Depois é necessário reservar parte desse bitrate para o áudio. Por isso, a mesma meta de 2 MB pode preservar boa qualidade em um vídeo curto e produzir qualidade baixa em um vídeo longo.

## Recomendação

Mantenha a ferramenta de imagens estável e crie o vídeo como módulo separado. Isso evita carregar aproximadamente dezenas de megabytes de WebAssembly para usuários que só processam imagens e reduz o risco de uma falha de vídeo afetar a fila de imagens.
