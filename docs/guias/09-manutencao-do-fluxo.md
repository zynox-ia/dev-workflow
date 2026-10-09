# 09 · Manutenção do fluxo

O fluxo (guias, prompts, skills e convenções) é usado em vários repositórios de clientes. Para todos usarem a mesma versão e as melhorias chegarem a todos, ele vive num **repositório central** e é copiado para cada projeto com versão.

## 1. Repositório central

O repositório público [`zynox-ia/dev-workflow`](https://github.com/zynox-ia/dev-workflow), com a mesma estrutura que vai para os projetos:

```
dev-workflow/
├── README.md                    como usar e como contribuir
└── docs/
    ├── README.md
    ├── guias/                   documentação explicativa
    └── fluxo/
        ├── VERSION              versão atual (ex.: 1.2.0)
        ├── CHANGELOG.md         o que mudou em cada versão e a ação necessária nos projetos
        ├── 00-convencoes.md … 04-atualizar-fluxo.md
        ├── skills/              planejar-etapas, registrar-linear
        └── linear/              guidance, templates e skills do agente do Linear
```

O que **não** fica no central, porque é de cada projeto: `docs/roadmap/`, `.specify/` (constituição, `projeto.md`) e `.pipeline/`.

Por ser público, qualquer agente baixa o fluxo com `git clone`, sem precisar de autenticação. Por isso, **nunca coloque no fluxo** segredos, dados de clientes ou nomes de sistemas: o conteúdo específico de cada projeto vive no repositório do projeto.

## 2. Versões do fluxo (SemVer)

| Sobe | Quando | Exemplo |
|---|---|---|
| **MAJOR** | Exige reconfigurar projetos: muda status, labels, estrutura do Linear, ou pede para rodar a preparação de novo | Trocar os status do Linear |
| **MINOR** | Capacidade nova, compatível | Nova skill, nova fase opcional |
| **PATCH** | Correção de texto, de comando ou de clareza | Ajustar um brief do Diretor |

Toda versão tem uma entrada no `CHANGELOG.md`, sempre com a seção **"Ação necessária nos projetos"** (ou "nenhuma").

## 3. Melhorar o fluxo

1. Algo deu errado num projeto (um portão que falhou à toa, um brief confuso, uma pergunta que sempre se repete). Anote.
2. No repositório central, branch `fix/<assunto>` ou `feat/<assunto>`; edite o arquivo; atualize `VERSION` e `CHANGELOG.md`.
3. PR, revisão e merge na `main` do central.
4. Tag `vX.Y.Z` e release no GitHub.
5. Atualize os projetos (seção 4).

Nunca edite `docs/fluxo/` direto num projeto: a mudança some na próxima atualização. Se for urgente, corrija no central e publique um PATCH.

## 4. Instalar ou atualizar num projeto

Num agente novo do Traycer, na pasta do projeto:
```
Siga as instruções do arquivo docs/fluxo/04-atualizar-fluxo.md.
```
Num projeto que ainda não tem o fluxo, use o arquivo direto do central:
```
Leia https://raw.githubusercontent.com/zynox-ia/dev-workflow/main/docs/fluxo/04-atualizar-fluxo.md e siga as instruções para instalar o fluxo neste repositório.
```
O agente copia `docs/guias/` e `docs/fluxo/` da versão pedida, instala as skills para Claude Code e Codex, mostra o changelog e as ações necessárias, e abre um PR `chore(fluxo): atualizar para vX.Y.Z` para a develop.

O Coordenador avisa na abertura de cada sessão quando o projeto está numa versão mais antiga que a última do central.

## 5. Skills: onde cada uma é usada

| Skill | Onde vive | Quem usa | Para quê |
|---|---|---|---|
| `registrar-linear` | Repositório (`.claude/skills`, `.agents/skills`) | Você no Traycer; o Diretor na fase de tasks | Criar demandas no padrão (modo A) e as sub-issues de uma spec (modo B) |
| `planejar-etapas` | Repositório | Você no Traycer; o Coordenador (auditoria) | Planejar projetos e specs, auditar, quebrar issues XL |
| `/nova-issue` | Linear (skill pessoal) | Você, conversando com o agente do Linear | O mesmo que o modo A da `registrar-linear`, sem abrir o Traycer |

`registrar-linear` (modo A) e `/nova-issue` seguem as mesmas regras. Ao mudar uma, mude a outra na mesma versão do fluxo. No Linear, atualize a skill pessoal colando o texto novo e salvando de novo.

**No Traycer**, em qualquer agente do projeto: `/registrar-linear bug: a etapa do cliente não salva ao fechar o modal` (Claude Code) ou `$registrar-linear ...` (Codex).
