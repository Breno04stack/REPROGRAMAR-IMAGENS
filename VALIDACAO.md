# Validação técnica da v5

## Checklist antes de publicar

- [ ] `index.html` abre sem erro de JavaScript.
- [ ] O título mostra `Reprogramador de Imagens v5`.
- [ ] É possível adicionar vários arquivos em uma única seleção.
- [ ] Uma segunda seleção é acumulada na fila.
- [ ] É possível adicionar uma pasta de imagens.
- [ ] Cada item da fila possui seletor de marketplace.
- [ ] O botão de duplicar cria outra linha para o mesmo arquivo.
- [ ] O marketplace padrão é aplicado somente a novos itens.
- [ ] O perfil Mercado Livre gera 1200 × 1200.
- [ ] O perfil Shopee gera 1200 × 1200.
- [ ] O perfil TikTok Shop gera 1000 × 1000.
- [ ] O perfil SHEIN gera 1200 × 1600.
- [ ] O perfil Amazon gera 1600 × 1600.
- [ ] O perfil Outros usa a largura e a altura personalizadas.
- [ ] Encaixar sem cortar preserva todo o conteúdo.
- [ ] Preencher e cortar ocupa todo o quadro.
- [ ] O arquivo final respeita o tamanho máximo configurado.
- [ ] A diferença mínima de pixels é validada.
- [ ] O hash final é diferente do original.
- [ ] A numeração continua entre recarregamentos.
- [ ] Reiniciar numeração faz o próximo arquivo voltar a `0001`.
- [ ] O download individual usa o nome numerado.
- [ ] O ZIP usa subpastas quando a opção estiver marcada.
- [ ] O relatório CSV registra marketplace, perfil e enquadramento.
- [ ] A seleção de pasta funciona em Chrome/Edge via HTTPS.
- [ ] Quando a seleção de pasta não existe, o ZIP permanece disponível.

## Teste rápido recomendado

1. Adicione uma imagem quadrada e outra vertical.
2. Duplique a imagem quadrada três vezes.
3. Atribua Mercado Livre, Amazon e SHEIN.
4. Use Encaixar sem cortar.
5. Processe o lote.
6. Confira as dimensões finais na tabela.
7. Baixe o ZIP com Subpastas por marketplace ativado.
8. Verifique se as pastas e o CSV foram criados.

## Critérios padrão de aprovação

- tamanho máximo: 1,95 MB;
- diferença mínima: 1%;
- PSNR mínimo: configurado pela interface;
- SHA-256 final diferente do original;
- saída legível e visualmente aceitável.

## Limitações conhecidas

- imagens extremamente grandes podem consumir muita memória;
- compressão JPG/WebP altera muitos pixels numericamente, mesmo com aparência muito próxima;
- a File System Access API não funciona em todos os navegadores;
- regras oficiais podem mudar por marketplace e categoria;
- o sistema não verifica automaticamente fundo branco, ocupação do produto ou conteúdo proibido.
