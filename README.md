# Image Binary Refresh v4

Aplicação web estática para processar imagens em lote diretamente no navegador.

## Principais recursos

- várias seleções são acumuladas na mesma fila;
- seleção múltipla de arquivos;
- importação de uma pasta inteira em navegadores compatíveis;
- prevenção de arquivos duplicados na fila;
- processamento sequencial para reduzir uso de memória;
- falha em uma imagem não interrompe o restante do lote;
- cancelamento após o arquivo atual;
- no mínimo 1% de pixels diferentes, com validação da saída final;
- limite configurável abaixo de 2 MB;
- PNG, JPEG e WebP automáticos;
- SHA-256 original e final;
- download individual;
- ZIP com todas as imagens e relatório CSV;
- gravação direta em uma pasta escolhida pelo usuário;
- salvamento automático nessa pasta após cada imagem aprovada.

## Como atualizar o GitHub Pages

1. Abra o repositório `REPROGRAMAR-IMAGENS`.
2. Substitua o arquivo `index.html` da raiz pelo novo `index.html`.
3. Faça o commit.
4. Aguarde o GitHub Pages republicar.
5. Atualize o site com `Cmd + Shift + R` no Mac ou `Ctrl + Shift + R` no Windows.

## Como selecionar várias imagens

Existem três formas:

1. clique na área de upload e selecione várias imagens de uma vez;
2. clique novamente em **Adicionar arquivos** para acumular novas seleções;
3. use **Adicionar pasta** para importar todas as imagens de uma pasta.

A v4 não substitui a seleção anterior quando você adiciona novos arquivos. Ela acumula tudo na fila e ignora duplicatas exatas de seleção.

## Pasta de saída

No Chrome ou Edge em contexto HTTPS:

1. clique em **Escolher pasta**;
2. selecione a pasta de destino;
3. mantenha **Salvar automaticamente** marcado;
4. processe a fila.

Cada resultado aprovado será gravado diretamente nessa pasta. Também existe o botão **Salvar resultados na pasta** para gravar arquivos já processados.

Em navegadores sem suporte à seleção direta de diretório, use **Baixar tudo em ZIP**. Um site não pode escolher silenciosamente uma pasta do computador sem autorização explícita do usuário.

## Observações de segurança e privacidade

- as imagens são processadas localmente;
- nada é enviado para um servidor pela aplicação;
- o navegador exige autorização para gravar na pasta escolhida;
- o acesso à pasta vale para a sessão e pode precisar ser concedido novamente após recarregar a página.

## Vídeos

Vídeos também podem ser reprocessados, mas devem usar um módulo separado baseado em FFmpeg/WebAssembly. Consulte `VIDEO.md` para o desenho técnico e as limitações.
