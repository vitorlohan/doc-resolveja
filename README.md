# Documentação do Resolve Já

Site de documentação da plataforma **Resolve Já** — sistema interno de chamados de
infraestrutura e manutenção ([vitorlohan/chamado-patrimonio](https://github.com/vitorlohan/chamado-patrimonio)).

Publicado em <https://resolve-ja.mintlify.site/>, construído com [Mintlify](https://mintlify.com).

## Como funciona

| O quê | Onde |
|---|---|
| **Configuração** — menu, tema, cores, logo | `docs.json` |
| **Conteúdo** — uma página por arquivo | arquivos `.mdx` |
| **Imagens** | `images/` |
| **Logo e favicon** | `logo/`, `favicon.svg` |

O caminho do arquivo é a URL da página: `chamados/abrir-chamado.mdx` → `/chamados/abrir-chamado`.

Uma página só aparece no menu se estiver listada em `docs.json`, dentro de
`navigation.tabs[].groups[].pages[]` — **sem** a extensão `.mdx`.

## Estrutura

```
doc-resolveja/
├── docs.json                  # navegação, tema, cores, logo
├── index.mdx                  # página inicial (/)
├── comecar/                   # visão geral e primeiros passos
├── chamados/                  # guia do solicitante
├── atendimento/               # guia da equipe técnica
├── checklists/                # execução e histórico
├── ajuda/                     # notificações, FAQ, problemas comuns
├── images/                    # capturas de tela
└── logo/                      # logo claro e escuro
```

## Rodar localmente

Instale o CLI uma vez:

```bash
npm i -g mint
```

Na raiz do projeto (onde está o `docs.json`):

```bash
mint dev
```

Preview em <http://localhost:3000>, com recarga automática a cada arquivo salvo.

Se o ambiente não subir, rode `mint update` para atualizar o CLI.

## Publicar

Com o [GitHub App da Mintlify](https://dashboard.mintlify.com/settings/organization/github-app)
instalado no repositório, todo push para a branch `main` publica automaticamente.

```bash
git add .
git commit -m "docs: descreve a mudança"
git push origin main
```

Para mudanças grandes, abra um Pull Request: a Mintlify gera um link de preview
no PR antes de o conteúdo ir ao ar.

## Adicionar uma página

1. Crie o arquivo `.mdx` na pasta certa, com o frontmatter (`title`, `sidebarTitle`, `description`).
2. Registre o caminho em `docs.json`, no grupo desejado.
3. Confira em `mint dev` antes de commitar.

## Capturas de tela

As páginas trazem marcadores `{/* SCREENSHOT: ... */}` nos pontos onde uma imagem
ajuda. Veja [`images/README.md`](images/README.md) para o processo.

## Escrita

Convenções de estilo e terminologia estão em [`AGENTS.md`](AGENTS.md).
