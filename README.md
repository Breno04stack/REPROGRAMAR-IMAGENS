# Reprogramador de Imagens v5 — Marketplaces

Aplicação web estática para preparar imagens de anúncios em lote diretamente no navegador.

## Principais recursos

- seleção de um marketplace padrão para novos arquivos;
- seleção individual do destino de cada imagem na fila;
- duplicação da mesma imagem para gerar versões para vários marketplaces;
- redimensionamento e enquadramento automáticos por perfil;
- modo **Encaixar sem cortar** ou **Preencher e cortar**;
- cor de fundo configurável;
- perfis para Mercado Livre, Shopee, TikTok Shop, SHEIN, Amazon, Outros e Sem perfil;
- dimensões personalizadas para Outros marketplaces;
- processamento em lote com fila visível e status individual;
- importação de vários arquivos ou de uma pasta inteira;
- tamanho máximo configurável, com padrão de 1,95 MB;
- diferença mínima configurável de pixels, com padrão de 1%;
- proteção de qualidade por PSNR;
- formato automático ou definido manualmente;
- redução de dimensões somente quando necessária;
- numeração persistente: `0001`, `0002`, `0003`...;
- botão para reiniciar a numeração;
- seleção de pasta de saída em navegadores compatíveis;
- salvamento automático na pasta autorizada;
- subpastas opcionais por marketplace;
- download individual ou em ZIP;
- relatório CSV com perfil, dimensões, qualidade, hashes e tamanho final;
- processamento local: as imagens não são enviadas a um servidor.

## Perfis incluídos

| Destino | Dimensão operacional | Proporção |
|---|---:|---:|
| Mercado Livre | 1200 × 1200 px | 1:1 |
| Shopee | 1200 × 1200 px | 1:1 |
| TikTok Shop | 1000 × 1000 px | 1:1 |
| SHEIN | 1200 × 1600 px | 3:4 |
| Amazon | 1600 × 1600 px | 1:1 |
| Outros marketplaces | Personalizável | Personalizável |
| Sem perfil | Mantém a dimensão original | Original |

Os perfis são parâmetros operacionais editáveis. Regras podem variar por país, categoria, tipo de anúncio e atualização da plataforma.

## Publicação no GitHub Pages

Consulte [DEPLOY.md](DEPLOY.md).

## Estrutura do projeto

```text
index.html                 Aplicação completa e autocontida
README.md                  Visão geral e instruções básicas
DEPLOY.md                  Passo a passo para atualizar o GitHub Pages
PERFIS-MARKETPLACES.md     Detalhes dos perfis e enquadramento
VALIDACAO.md               Checklist técnico e testes recomendados
CHANGELOG.md               Histórico das versões
VIDEO.md                   Planejamento do módulo de vídeos
.nojekyll                  Impede processamento desnecessário pelo Jekyll
VERSION.txt                Número da versão publicada
```

## Requisitos do navegador

- Chrome ou Edge recente são recomendados;
- HTTPS é necessário para escolher uma pasta diretamente;
- quando a seleção de pasta não estiver disponível, use o download individual ou o ZIP;
- o processamento ocorre no dispositivo e pode usar bastante memória em lotes muito grandes.

## Observação importante

O sistema melhora compatibilidade, dimensão e apresentação técnica da imagem. Isso não garante aprovação, exposição ou ranqueamento. Fundo, conteúdo permitido, enquadramento, categoria, qualidade da oferta e regras comerciais também influenciam cada marketplace.
