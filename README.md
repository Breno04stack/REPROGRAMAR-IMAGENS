# Image Binary Refresh

Aplicação web estática para processar imagens em lote sem separar pastas.

## O que ela faz

- aceita várias imagens via drag-and-drop;
- processa tudo localmente no navegador;
- reconstrói o arquivo PNG;
- remove EXIF/XMP e outros metadados comuns porque gera um PNG novo;
- alterna RGB/RGBA quando isso não muda a aparência;
- usa filtros PNG variáveis por linha;
- usa um nonce binário privado opcional;
- calcula SHA-256 antes/depois;
- reabre o arquivo gerado e confirma igualdade RGBA pixel a pixel;
- permite baixar cada resultado ou tudo em ZIP;
- inclui `relatorio.csv` dentro do ZIP.

## Como usar localmente

Basta abrir `index.html` em um navegador moderno com internet.

A página usa apenas duas bibliotecas carregadas via CDN:
- pako
- JSZip

As imagens não são enviadas para esses serviços; todo o processamento ocorre no navegador.

## Publicar no GitHub Pages

1. Crie um repositório novo no GitHub.
2. Envie `index.html` e `README.md` para a raiz do repositório.
3. Abra **Settings > Pages**.
4. Em **Build and deployment**, selecione **Deploy from a branch**.
5. Selecione a branch `main` e a pasta `/ (root)`.
6. Salve.

O GitHub exibirá a URL pública do site.

## Observação técnica

A ferramenta muda a representação binária do arquivo e pode manter os pixels decodificados idênticos.
Isso não impede sistemas de busca visual ou perceptual hash de reconhecerem o mesmo conteúdo visual.

Para JPG/WebP/BMP, o navegador primeiro decodifica a imagem e o resultado é salvo como PNG lossless.
