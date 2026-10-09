# dev-workflow

Fluxo de desenvolvimento com agentes de IA: convenções, prompts, skills e documentação usados em todos os repositórios de clientes.

- **Documentação:** [`docs/README.md`](docs/README.md)
- **Versão atual:** [`docs/fluxo/VERSION`](docs/fluxo/VERSION) · [Changelog](docs/fluxo/CHANGELOG.md)

## O que tem aqui

| Pasta | Conteúdo |
|---|---|
| `docs/guias/` | Padrões explicados: visão geral, Linear, nomenclatura, git e releases, ordem de construção, ambiente local, trilhas e qualidade, glossário, manutenção |
| `docs/fluxo/` | Prompts operacionais (preparação, Condutor, sessão visual, atualização), papéis 01 a 09, convenções normativas, skills, configuração do agente do Linear e o modelo do `AGENTS.md` dos projetos |

## Instalar ou atualizar num projeto

Num agente novo do Traycer, na pasta do projeto do cliente:
```
Leia https://raw.githubusercontent.com/zynox-ia/dev-workflow/main/docs/fluxo/04-atualizar-fluxo.md e siga as instruções para instalar o fluxo neste repositório.
```
Para atualizar, use o mesmo link (nunca a cópia local, que é da versão antiga):
```
Leia https://raw.githubusercontent.com/zynox-ia/dev-workflow/main/docs/fluxo/04-atualizar-fluxo.md e siga as instruções para atualizar o fluxo neste repositório.
```
Atualizar não reinstala o Spec Kit nem refaz a preparação: troca a documentação, as skills e o bloco do fluxo no `AGENTS.md`, e aplica as migrações que o changelog pedir, tudo num PR para a develop.

## Contribuir

Melhorias são feitas **somente aqui**, nunca direto nos projetos:
1. Branch `fix/<assunto>` ou `feat/<assunto>`.
2. Editar, atualizar `docs/fluxo/VERSION` e `docs/fluxo/CHANGELOG.md` (com a seção "Ação necessária nos projetos").
3. PR → merge na `main` → tag `vX.Y.Z`.

Detalhes: [`docs/guias/09-manutencao-do-fluxo.md`](docs/guias/09-manutencao-do-fluxo.md).
