# Atualização no GitHub Pages

## Método recomendado

1. Baixe e extraia o pacote completo.
2. Abra o repositório `REPROGRAMAR-IMAGENS` no GitHub.
3. Confirme que está na branch `main`.
4. Clique em **Add file → Upload files**.
5. Arraste todos os arquivos extraídos para a raiz do repositório.
6. Confirme a substituição dos arquivos existentes.
7. Use a mensagem de commit:

```text
Atualizar Reprogramador de Imagens para v5 Marketplaces
```

8. Clique em **Commit changes**.
9. Abra **Actions** e aguarde `Pages build and deployment` ficar verde.
10. Acesse o site adicionando um parâmetro para evitar cache:

```text
https://breno04stack.github.io/REPROGRAMAR-IMAGENS/?v=5.0.0
```

11. Faça uma atualização forçada:

```text
Mac: Cmd + Shift + R
Windows: Ctrl + Shift + R
```

## Configuração do Pages

Em **Settings → Pages**, mantenha:

```text
Source: Deploy from a branch
Branch: main
Folder: / (root)
```

## Arquivos que precisam ficar na raiz

O arquivo obrigatório é `index.html`. Os demais são documentação e configuração do projeto.

```text
REPROGRAMAR-IMAGENS/
├── .nojekyll
├── CHANGELOG.md
├── DEPLOY.md
├── PERFIS-MARKETPLACES.md
├── README.md
├── VALIDACAO.md
├── VERSION.txt
├── VIDEO.md
└── index.html
```

## Verificação após publicar

A página deve mostrar o título:

```text
Reprogramador de Imagens v5
```

Também devem aparecer:

- seletor Marketplace padrão;
- marketplace individual em cada item da fila;
- botão para duplicar uma imagem;
- opção Subpastas por marketplace;
- tamanho para Outros marketplaces;
- numeração contínua;
- botão Reiniciar numeração.

## Quando o site antigo continuar aparecendo

1. Abra o endereço com outro parâmetro, por exemplo `?v=5.0.1`.
2. Use uma janela anônima.
3. Faça atualização forçada.
4. Confira em **Actions** se o deployment corresponde ao último commit.
5. Abra o código-fonte da página publicada e procure por:

```text
window.__REPROGRAMADOR_IMAGENS_V5__
```
