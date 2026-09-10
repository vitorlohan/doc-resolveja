# Capturas de tela

As páginas de documentação trazem marcadores no formato:

```mdx
{/* SCREENSHOT: formulário "Abrir Chamado" preenchido, com duas fotos anexadas */}
```

Cada marcador indica um ponto onde uma imagem ajuda o leitor. Eles não aparecem no
site publicado — são comentários MDX.

## Como substituir um marcador por uma imagem

1. Tire a captura na plataforma (de preferência em tela cheia, no navegador).
2. Salve nesta pasta com nome descritivo em kebab-case: `abrir-chamado-formulario.png`.
3. Troque o marcador pelo componente `Frame`:

```mdx
<Frame caption="Formulário de abertura de chamado">
  <img src="/images/abrir-chamado-formulario.png" alt="Formulário Abrir Chamado preenchido" />
</Frame>
```

O caminho começa com `/images/` — barra na frente, contado a partir da raiz do projeto.

## Recomendações

- **Formato**: PNG para telas, JPG para fotos.
- **Largura**: entre 1200 px e 1600 px. Acima disso o arquivo pesa sem ganho visível.
- **Dados sensíveis**: nomes reais, e-mails e telefones aparecem nos chamados.
  Use dados de exemplo ou desfoque antes de publicar — a documentação é pública.
- **`alt`**: descreva o que a imagem mostra. Serve para acessibilidade e para o SEO.
- **Tema**: as capturas ficam visíveis nos dois temas do site. Prefira telas claras,
  que é como a plataforma se apresenta.

## Marcadores existentes

| Página | Captura sugerida |
|---|---|
| `index.mdx` | Quadro de chamados com as três colunas |
| `comecar/criar-conta.mdx` | Tela "Criar conta" com o formulário preenchido |
| `comecar/entrar.mdx` | Tela "Painel de Login" |
| `chamados/abrir-chamado.mdx` | Formulário preenchido, com fotos anexadas |
| `chamados/acompanhar-chamado.mdx` | Aba "Meus chamados" com situações diferentes |
| `chamados/avaliar-atendimento.mdx` | Tela "Avalie o atendimento" |
| `atendimento/quadro-de-chamados.mdx` | Quadro com cards de equipes diferentes |
| `atendimento/pegar-chamado.mdx` | Detalhe com o bloco "Pegar este chamado" |
| `atendimento/concluir-chamado.mdx` | Modal "Concluir chamado" preenchido |
| `checklists/executar-checklist.mdx` | Checklist com itens marcados e pendência |
| `checklists/historico-de-checklists.mdx` | Aba Histórico com a tabela do período |
