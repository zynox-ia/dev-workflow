# Prompts

Os prompts que o André cola no Traycer. Cada um é uma linha: o agente lê o arquivo indicado e segue as instruções.

| # | Quando | Onde colar | Prompt | Arquivo |
|---|---|---|---|---|
| 1 | **Começar ou atualizar** um projeto (novo, existente ou com fluxo antigo) | Agente novo, na pasta do repositório do cliente | `Leia https://raw.githubusercontent.com/zynox-ia/dev-workflow/main/docs/fluxo/04-atualizar-fluxo.md e siga as instruções neste repositório.` | [`docs/fluxo/04-atualizar-fluxo.md`](docs/fluxo/04-atualizar-fluxo.md) |
| 2 | **Trabalhar** nas issues, uma por vez, com você testando | Agente novo (Terra Medium) | `Siga docs/fluxo/02-condutor.md. Modo: manual` | [`docs/fluxo/02-condutor.md`](docs/fluxo/02-condutor.md) |
| 3 | **Preparar um lote** de issues (spec, plano, tarefas) e responder as perguntas de uma vez | Agente novo (Terra Medium) | `Siga docs/fluxo/02-condutor.md. Modo: preparar` | idem |
| 4 | **Deixar rodando** (à noite): fila inteira, relatório no fim | Agente novo (Terra Medium) | `Siga docs/fluxo/02-condutor.md. Modo: automático` | idem |
| 5 | **Ajuste visual** conversado, sem spec | Agente novo | `Siga docs/fluxo/03-visual.md. Assunto: <o que vamos ajustar>` | [`docs/fluxo/03-visual.md`](docs/fluxo/03-visual.md) |

O prompt 1 é o único que usa o link do repositório central: ele instala ou atualiza o fluxo, prepara a casa e planeja. Depois dele, os prompts 2 a 5 usam os arquivos que ele copiou para o projeto.

Os demais arquivos de `docs/fluxo/` não são colados por você: a preparação (`01-preparacao-da-casa.md`) é chamada pelo prompt 1, e os papéis (`papeis/01-especificador.md` … `09-verificador.md`) são lidos pelos agentes que o Condutor cria.
