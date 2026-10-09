# AGENTS.md

Este repositório é o **dev-workflow**: convenções, prompts, skills e guias do fluxo de desenvolvimento com agentes, copiados para os repositórios dos clientes pelo `docs/fluxo/04-atualizar-fluxo.md`. Aqui não há código de aplicação; o produto é a documentação.

## Estrutura

| Caminho | Conteúdo |
|---|---|
| `docs/fluxo/00-convencoes.md` | Regra normativa. Em conflito com qualquer outro arquivo, ela vence |
| `docs/fluxo/01…04-*.md` | Prompts (preparação, Condutor, sessão visual, atualização), cada um com versão própria no título (`vN`) |
| `docs/fluxo/papeis/` | Um arquivo por papel (01 a 09), lido pelo agente daquele papel |
| `docs/fluxo/skills/` | Skills instaladas nos projetos (`planejar-etapas`, `registrar-linear`) |
| `docs/fluxo/linear/` | Guidance, templates e skill `/nova-issue` do agente do Linear |
| `docs/fluxo/modelos/` | Modelos instalados nos projetos: `AGENTS.md` e `agent-selection-guide.md` (modelo de IA de cada papel) |
| `docs/fluxo/VERSION`, `CHANGELOG.md` | Versão do fluxo (SemVer) e mudanças |
| `docs/guias/` | Os mesmos padrões explicados para pessoas |

## Regras de edição

- **Uma regra, um lugar.** A regra vive em `00-convencoes.md`; prompts e guias apontam para ela ou a aplicam. Mudou uma regra: procure (`grep -rn`) e atualize todos os arquivos que a repetem, na mesma mudança.
- **Guias e fluxo andam juntos.** Mudança de comportamento num prompt exige o ajuste do guia correspondente.
- `registrar-linear` (modo A) e `linear/skills/nova-issue.md` seguem as mesmas regras: mudou uma, mude a outra.
- Prompt alterado: suba o `vN` do título dele.
- No `modelos/AGENTS.md`, preserve os marcadores `<!-- projeto:inicio … -->`, `<!-- projeto:fim -->`, `<!-- dev-workflow:inicio … -->` e `<!-- dev-workflow:fim -->`: o 04 e a preparação dependem deles. O modelo fica com menos de 120 linhas depois de preenchido.
- Trechos de shell dos prompts são executados por agentes: teste-os antes de publicar.
- Português, frases diretas, tabelas para regras. O usuário é chamado de **André**.

## Repositório público

Nunca escreva segredos, dados de clientes, nomes de clientes ou de sistemas de clientes. Exemplos usam nomes fictícios (ex.: "Bruno CRM", `BRU-12`).

## Versão e publicação

1. Branch `feat/<assunto>` ou `fix/<assunto>` a partir da `main`.
2. Suba `docs/fluxo/VERSION` (MAJOR: exige reconfigurar projetos; MINOR: capacidade nova compatível; PATCH: correção de texto ou comando) e acrescente a entrada no `CHANGELOG.md`, sempre com **"Ação necessária nos projetos"** (ou "nenhuma").
3. Mudança que os projetos precisam aplicar em arquivos, e que um agente consegue fazer sem rodar a preparação, entra na "Ação necessária" como item **`[04]`**, com instruções exatas: o 04 executa esses itens ao atualizar. Rodar a preparação de novo só em MAJOR.
4. Commit `<tipo>: <resumo>` (Conventional Commits, resumo em português). PR para a `main`; o merge é do André.
5. Depois do merge, o André cria a tag `vX.Y.Z` (exatamente esse formato: o 04 e o Condutor dependem dela).

Detalhes: `docs/guias/09-manutencao-do-fluxo.md`.
