# Papéis

Cada etapa de uma issue tem um dono. O **00 Condutor** (`docs/fluxo/02-condutor.md`) cria um agente novo para cada papel, passa o bastão e confere o portão antes de seguir. O número é a posição no fluxo.

| Papel | Trilha SDD | Trilha Bug | Trilha Manutenção | Modelo (`.traycer/agent-selection-guide.md`) |
|---|---|---|---|---|
| 00 Condutor | conduz | conduz | conduz | Terra Medium · Sonnet 5.5 |
| [01 Especificador](01-especificador.md) | `speckit-specify` | `speckit-bug-assess` | — | Luna Max · Haiku 4.5 |
| [02 Esclarecedor](02-esclarecedor.md) | `speckit-clarify` | — | — | Luna Max · Haiku 4.5 |
| [03 Arquiteto](03-arquiteto.md) | `speckit-plan` | — | — | Sol Max · Opus 5 |
| [04 Planejador](04-planejador.md) | `speckit-tasks` + sub-issues | — | — | Luna Max · Haiku 4.5 |
| [05 Analista](05-analista.md) | `speckit-analyze` | — | — | Luna Max · Haiku 4.5 |
| [06 Implementador](06-implementador.md) | `speckit-implement`, uma fase por agente | `speckit-bug-fix` | implementa a issue | Luna Max · Haiku 4.5 |
| [07 Convergência](07-convergencia.md) | `speckit-converge` | `speckit-bug-test` | — | Luna Max · Haiku 4.5 |
| [08 Revisor](08-revisor.md) | revisão independente | revisão independente | revisão independente | o modelo que **não** implementou |
| [09 Verificador](09-verificador.md) | base atualizada, verificação, PR, ambiente de teste | igual | igual | Luna Max · Haiku 4.5 |

## Regras comuns a todos os papéis

- Um agente faz **um papel, numa issue**, e é arquivado quando o portão passa.
- Nome do agente: `<ID> · <NN Papel>` (ex.: `BRU-23 · 03 Arquiteto`; implementador por fase: `BRU-23 · 06 Implementador · US1`).
- Antes de tudo: ler `.specify/memory/constitution.md` e o arquivo do próprio papel. Do código, só o que a tarefa exige.
- Nunca: fazer o trabalho de outro papel; inventar requisito; esperar resposta no chat; mexer fora da worktree; remover ou desativar testes; fazer merge; dar push em `develop` ou `main`.
- Commits: `<tipo>(<domínio>): <resumo no imperativo> (<ID>)`. **Todo papel commita o que produziu** antes de responder; papéis de documento (01 a 05, 07) usam `docs(<domínio>): spec NNN <etapa> (<ID>)` (bug: `docs(<domínio>): diagnóstico do bug (<ID>)`). O Condutor confere `git status --porcelain` vazio.
- Skills do Spec Kit: `/speckit-<cmd>` no Claude Code, `$speckit-<cmd>` no Codex. Siga à risca.
- **Resposta final, sempre neste formato:**
  ```
  STATUS: ok | bloqueado
  ARQUIVOS: <criados ou alterados>
  PERGUNTAS: <se houver, cada uma com resposta recomendada e motivo>
  OBSERVAÇÕES: <até 3 linhas>
  ```
