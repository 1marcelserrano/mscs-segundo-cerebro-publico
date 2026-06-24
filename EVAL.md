# EVAL — Captura de referências externas

Teste de fumaça do padrão `/capturar-ref` (captura externa → `raw/` → mixagem na hora → `wiki/`).

## Setup

Como este repo é o **pacote distribuível** da skill (não uma instância do Segundo Cérebro), o eval montou um workspace mínimo e descartável (`raw/`, `wiki/`, `voz.md`), rodou o fluxo do `/capturar-ref` à mão e **removeu o workspace** depois. O repo não deve carregar exemplo de memória.

## Referência testada

Tweet de Andrej Karpathy, 24 jan 2023 — *"The hottest new programming language is English"*. Referência real, quote verbatim, em texto colado (sem rede).

## Resultado — checklist

| Item | Status |
|---|---|
| 9 campos preenchidos sem encher linguiça (campo sem matéria = "—") | ✅ |
| Quote bruto preservado verbatim, não reescrito | ✅ |
| Wikilink criado e página de `wiki/` na voz do dono | ✅ |
| Nota de `raw/` marcada `status: mixado` | ✅ |
| `wiki/index.md` e `wiki/log.md` atualizados | ✅ |
| Prompt de handoff concreto, na voz do dono, com arquivo-alvo | ✅ |

## Resumo (3 linhas)

- **Entrou:** o tweet do Karpathy "the hottest new programming language is English" como nota estruturada de 9 campos.
- **Ligou:** criou `wiki/ingles-como-linguagem-de-programacao` com wikilink pra `index`/memória viva — prompt como código, o LLM compila linguagem natural.
- **Melhor ideia:** abrir a primeira aula do PROMPT ZERO com o tweet — e o handoff já saiu como prompt pronto pra colar num Claude Code no repo do curso, que reescreve a abertura da aula 1.

**Veredito: eval verde.** Padrão (captura + mixagem + handoff) pronto pra propagar a cada install.
