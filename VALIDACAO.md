# Validação técnica da v4

A interface foi executada em Chromium headless com três imagens PNG sintéticas.

## Teste de fila acumulativa

- primeira seleção: 2 arquivos;
- segunda seleção: 1 arquivo;
- total final da fila: 3 arquivos;
- resultado: as seleções foram acumuladas corretamente.

## Teste de lote

- 3 arquivos processados na mesma execução;
- 3 resultados aprovados;
- nenhuma falha interrompeu o lote;
- todas as filas terminaram com status `done`.

## Requisitos de saída

| Arquivo | Tamanho final | Pixels diferentes | Resultado |
|---|---:|---:|---|
| teste_1.png | 18.908 bytes | 1,25% | aprovado |
| teste_2.png | 20.106 bytes | 1,25% | aprovado |
| teste_3.png | 21.480 bytes | 1,25% | aprovado |

Todos ficaram abaixo de 2.000.000 bytes e acima da diferença mínima de 1%.

## Teste de pasta de saída

Foi usado um `FileSystemDirectoryHandle` simulado no navegador:

- a pasta foi selecionada uma única vez;
- o salvamento automático gravou os 3 arquivos;
- os nomes salvos corresponderam aos hashes finais;
- o tamanho gravado correspondeu ao Blob aprovado.

A caixa de diálogo real de pasta depende do navegador e precisa ser usada em HTTPS, como no GitHub Pages.
