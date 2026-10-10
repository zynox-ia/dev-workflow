# dev-workflow

Fluxo de desenvolvimento com agentes de IA: convenções, prompts, skills e documentação usados em todos os repositórios de clientes.

- **Prompts para colar no Traycer:** [`PROMPTS.md`](PROMPTS.md)
- **Documentação:** [`docs/README.md`](docs/README.md)
- **Versão atual:** [`docs/fluxo/VERSION`](docs/fluxo/VERSION) · [Changelog](docs/fluxo/CHANGELOG.md)

## O que tem aqui

| Pasta | Conteúdo |
|---|---|
| `docs/guias/` | Padrões explicados: visão geral, Linear, nomenclatura, git e releases, ordem de construção, ambiente local, trilhas e qualidade, glossário, manutenção |
| `docs/fluxo/` | Prompts operacionais (preparação, Condutor, sessão visual, atualização), papéis 01 a 09, convenções normativas, skills, configuração do agente do Linear e o modelo do `AGENTS.md` dos projetos |

## Instalar ou atualizar num projeto

Num agente novo do Traycer, na pasta do projeto do cliente (sempre pelo link, nunca a cópia local):
```
Leia https://raw.githubusercontent.com/zynox-ia/dev-workflow/main/docs/fluxo/04-atualizar-fluxo.md e siga as instruções neste repositório.
```
O **prompt mestre** lê o repositório, mostra um diagnóstico e faz só o que falta:

| Etapa | Não existe | Existe |
|---|---|---|
| Fluxo | Instala | Atualiza se houver versão nova (com as migrações) |
| Casa (Spec Kit, constituição, comandos, ambiente, Linear) | Prepara do zero | Refaz só as fases que falham |
| Planejamento | Planeja o roadmap | Audita: onde estamos e o que vem |

Fluxo e casa saem num PR único; o roadmap, em outro. Ele para só no plano de ação, nas suas respostas e nos merges. O mesmo prompt serve para projeto novo, projeto existente e atualização.

## Contribuir

Melhorias são feitas **somente aqui**, nunca direto nos projetos:
1. Branch `fix/<assunto>` ou `feat/<assunto>`.
2. Editar, atualizar `docs/fluxo/VERSION` e `docs/fluxo/CHANGELOG.md` (com a seção "Ação necessária nos projetos").
3. PR → merge na `main` → tag `vX.Y.Z`.

Detalhes: [`docs/guias/09-manutencao-do-fluxo.md`](docs/guias/09-manutencao-do-fluxo.md).
