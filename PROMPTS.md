# Prompts

## O prompt (sempre este)

Num **agente novo** do Traycer (Terra Medium), na pasta principal do repositório do cliente — projeto novo, existente, com fluxo antigo ou no dia a dia:

```
Leia https://raw.githubusercontent.com/zynox-ia/dev-workflow/main/docs/fluxo/02-condutor.md e siga as instruções neste repositório. Modo: manual
```

O **00 Condutor** abre a sessão conferindo a casa. Se o fluxo não está instalado ou está desatualizado, se a preparação falta ou se não há roadmap, ele mostra o diagnóstico e, com o seu ok, resolve ele mesmo com você, seguindo o roteiro `04-preparador.md` (PRs, perguntas da stack, time do Linear, roadmap). Com a casa pronta, passa o turno para um Condutor de conversa limpa, que monta o time e leva as issues, uma por vez.

| Modo | Troque o final por | Quando |
|---|---|---|
| manual | `Modo: manual` | Primeiro uso e dia a dia: você testa e mescla cada issue |
| preparar | `Modo: preparar` | Lote de issues até o plano e as tarefas, perguntas juntas |
| automático | `Modo: automático` | À noite: fila inteira e relatório. Exige a casa pronta |

## Fora do Condutor

Ajuste visual conversado, sem spec (agente novo):
```
Siga docs/fluxo/03-visual.md. Assunto: <o que vamos ajustar>
```

## Os outros arquivos

Você não cola nenhum outro arquivo. O `04-preparador.md` é o roteiro que o Condutor executa na abertura, o `01-preparacao-da-casa.md` é chamado por ele, e os `papeis/01…09` são lidos pelos agentes do time que o Condutor monta.
