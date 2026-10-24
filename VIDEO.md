# Planejamento do módulo de vídeos

## É possível aplicar tratamento semelhante a vídeos?

Sim. O módulo de vídeo deve ser separado da página principal de imagens porque exige muito mais memória, CPU e armazenamento temporário.

## Arquitetura sugerida

Criar uma página independente, por exemplo:

```text
video.html
```

O processamento local pode usar FFmpeg em WebAssembly.

## Fluxo previsto

1. importar MP4, MOV, WebM ou MKV;
2. remover metadados e capítulos;
3. reencodar vídeo e áudio;
4. aplicar alteração visual discreta nos frames quando necessário;
5. otimizar codec, bitrate e keyframes;
6. validar duração, resolução e tamanho;
7. calcular SHA-256;
8. salvar em MP4 ou WebM;
9. permitir escolha de pasta e lote sequencial.

## Limitações

- vídeos grandes podem exceder a memória da aba;
- o processamento será mais lento que FFmpeg instalado;
- o núcleo WebAssembly precisa ser carregado;
- garantir um tamanho máximo depende da duração;
- vídeos longos exigem reduzir bitrate, resolução, frame rate ou áudio;
- validar diferença de pixels em todos os frames é caro e pode exigir amostragem.

## Recomendação

Manter o módulo de imagens independente e estável. Adicionar vídeos em uma página separada impede que usuários de imagens precisem carregar o motor de vídeo.
