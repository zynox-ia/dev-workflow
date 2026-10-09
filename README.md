# dev-workflow

Fluxo de desenvolvimento com agentes de IA: convenções, prompts, skills e documentação usados em todos os repositórios de clientes.

- **Documentação:** [`docs/README.md`](docs/README.md)
- **Versão atual:** [`docs/fluxo/VERSION`](docs/fluxo/VERSION) · [Changelog](docs/fluxo/CHANGELOG.md)

## O que tem aqui

| Pasta | Conteúdo |
|---|---|
| `docs/guias/` | Padrões explicados: visão geral, Linear, nomenclatura, git e releases, ordem de construção, ambiente local, trilhas e qualidade, glossário, manutenção |
| `docs/fluxo/` | Prompts operacionais (preparação, Diretor, Coordenador, atualização), convenções normativas, skills, configuração do agente do Linear e o modelo do `AGENTS.md` dos projetos |

## Instalar ou atualizar num projeto

Num agente novo do Traycer, na pasta do projeto do cliente:
```
Leia https://raw.githubusercontent.com/zynox-ia/dev-workflow/main/docs/fluxo/04-atualizar-fluxo.md e siga as instruções para instalar o fluxo neste repositório.
```
Depois de instalado, as atualizações usam o arquivo local:
```
Siga as instruções do arquivo docs/fluxo/04-atualizar-fluxo.md.
```

## Contribuir

Melhorias são feitas **somente aqui**, nunca direto nos projetos:
1. Branch `fix/<assunto>` ou `feat/<assunto>`.
2. Editar, atualizar `docs/fluxo/VERSION` e `docs/fluxo/CHANGELOG.md` (com a seção "Ação necessária nos projetos").
3. PR → merge na `main` → tag `vX.Y.Z`.

Detalhes: [`docs/guias/09-manutencao-do-fluxo.md`](docs/guias/09-manutencao-do-fluxo.md).
