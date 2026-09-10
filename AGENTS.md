# Instruções do projeto de documentação

## Sobre este projeto

- Site de documentação da plataforma **Resolve Já**, construído com [Mintlify](https://mintlify.com)
- Código-fonte do produto: [vitorlohan/chamado-patrimonio](https://github.com/vitorlohan/chamado-patrimonio)
- Páginas são arquivos MDX com frontmatter YAML
- A configuração (navegação, tema, cores) fica em `docs.json`
- **Todo o conteúdo é em português do Brasil**

## Regra principal

A documentação descreve **o que o sistema realmente faz**. Antes de documentar uma
tela ou um fluxo, confira o comportamento no código do produto — não descreva
funcionalidade por suposição. Onde o código e a documentação divergirem, o código manda.

Referências úteis no repositório do produto:

| O quê | Onde |
|---|---|
| Rotas e telas | `web/src/routes/AppRouter.tsx` |
| Permissões e menu | `web/src/auth/catalog.ts`, `web/src/auth/nav.ts` |
| Status, prioridades, rótulos | `web/src/types/index.ts` |
| Regras do ciclo do chamado | `server/src/modules/tickets/tickets.service.ts` |
| Regras dos checklists | `server/src/modules/checklists/checklists.service.ts` |

## Terminologia

Use sempre os termos que aparecem na interface:

| Use | Não use |
|---|---|
| chamado | ticket, ocorrência (como substantivo do registro) |
| solicitante | usuário, cliente, requisitante |
| membro de equipe | técnico, colaborador, funcionário |
| quadro | kanban, board, painel |
| pegar o chamado | assumir, atribuir a si, aceitar |
| protocolo | número, código, ID |
| CD | filial, unidade |
| departamento | setor (no cadastro o campo se chama Departamento) |
| checklist | lista de tarefas, rotina |
| item do checklist | tarefa, atividade (no plural genérico, "atividades" é aceitável) |
| observação | nota, comentário (no checklist) |
| pendência | justificativa (o link é "Justificar pendência") |
| aguardando / em espera | pausado, travado, bloqueado |
| supervisão | gestão, gestor (quando se fala do acesso) |

Nomes de status, exatamente como na interface: **Aberto**, **Em Andamento**,
**Aguardando**, **Concluído**. Para o solicitante: **Aberto**, **Pendente**, **Concluído**.

Prioridades: **Baixa**, **Média**, **Alta**, **Crítica**.

## Estilo

- Voz ativa e segunda pessoa ("você")
- Uma ideia por frase; frases curtas
- Títulos em **frase**, não em Title Case: "Abrir um chamado", não "Abrir Um Chamado"
- **Negrito** para elementos da interface: clique em **Concluir**
- `Código` para nomes de arquivo, comandos, caminhos e valores literais
- Tabelas para comparar; `<Steps>` para sequências; `<AccordionGroup>` para dúvidas
- Diga o que acontece **depois** de cada ação, não apenas onde clicar
- Registre as restrições (o que o perfil **não** pode fazer) — é o que gera mais dúvida
- Sem emoji no corpo do texto

## Callouts

| Componente | Uso |
|---|---|
| `<Note>` | Informação lateral relevante |
| `<Tip>` | Recomendação prática, boa prática |
| `<Info>` | Explicação de como a plataforma funciona por dentro |
| `<Warning>` | Restrição, ação irreversível, bloqueio de permissão |

## Frontmatter

Toda página precisa de:

```yaml
---
title: "Título completo, descritivo, para o H1 e o Google"
sidebarTitle: "Título curto para o menu"
description: "Uma frase que resume a página. Aparece abaixo do título e no Google."
---
```

## Ao criar uma página

1. Crie o `.mdx` na pasta do assunto (`comecar/`, `chamados/`, `atendimento/`, `checklists/`, `ajuda/`)
2. Registre o caminho em `docs.json` (sem `.mdx`) no grupo correto
3. Confira com `mint dev` antes de commitar

## Limites do conteúdo

- **Documentar**: fluxos do solicitante, da equipe técnica e da supervisão; o que cada perfil pode e não pode fazer
- **Não documentar**: variáveis de ambiente, comandos de deploy, esquema do banco, chaves e credenciais — isso pertence ao README do produto, não ao site público
- **Nunca publicar**: dados reais de colaboradores em capturas de tela ou exemplos

## Ainda não documentado

O produto tem módulos que este site ainda não cobre:

- **Uniformes e EPI** — solicitação, aprovação por setor, fila de separação, aluguéis, catálogo, movimentações de estoque, ficha por colaborador
- **Relatórios de chamados** — gráficos, exportação em PDF, relatório de avaliações
- **Administração** — equipes, membros, contatos, usuários, setores, CDs, SMTP, WhatsApp, perfis e permissões, auditoria, lixeira
- **Gestão de checklists** — criação, agendamento de datas, ativação de itens
