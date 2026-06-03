# Memória Viva — MSCREATIVE.SYSTEMS™

> Uma skill de Claude Code que monta uma **memória viva** dentro do seu repositório: uma pasta de markdown que o sistema **mixa** — liga as fontes, destila o bruto, calibra na sua voz — pra virar artefato. Markdown puro. Versionado. Portável.

Em 3 de abril de 2026, [Andrej Karpathy](https://github.com/karpathy) publicou um gist descrevendo como montar uma wiki pessoal com uma pasta de markdown (`raw/` → `wiki/`) e um LLM. Em 48 horas, a thread no X bateu **16 milhões de views**. A ideia: o repo é a IDE, o LLM é o programador, a wiki é o código-fonte.

Esta skill leva essa ideia adiante com uma lógica de **estúdio**. A memória aqui funciona como uma mesa de mixagem: você junta os samples (o material bruto), **mixa** (liga as fontes, tira o sinal, calibra na sua voz) e **produz** a faixa — post, e-mail, roteiro, proposta. Memória que vira obra.

---

## O ciclo

```
  captura          mixagem               produção
  ───────          ───────               ────────
  raw/      →    liga + destila      →   artefato
                 + calibra na voz        na sua voz
                       │
                     voz.md  (sua assinatura, cresce a cada mixagem)
```

1. **Captura** — tudo que entra vai cru pra `raw/`. Os samples: conversa, ideia, transcrição, recorte.
2. **Mixagem** — o sistema liga cada fonte ao que já existe, destila o sinal, escreve na `wiki/` na sua voz, e reforça seu `voz.md`.
3. **Produção** — sob demanda, produz puxando da `wiki/`, na sua voz, no formato do destino.

A voz é a assinatura. A cada mixagem o sistema aprende como você pensa e escreve. Por isso a faixa soa como você.

---

## Os três verbos

| Comando | O que faz |
|---|---|
| `/mixar [tema]` | Liga o bruto novo de `raw/` ao que já existe, destila pra `wiki/` e atualiza `voz.md` |
| `/lembrar [tema]` | Vasculha a memória: o que você já sabe e já disse, com as conexões |
| `/produzir [tema]` | Gera a faixa: um artefato na sua voz, puxando da memória |

---

## Instalar

```bash
git clone https://github.com/1marcelserrano/mscs-segundo-cerebro.git ~/.claude/skills/mscs-segundo-cerebro
```

Se a pasta já existir, faça backup antes (`mv ... .backup`). Abra o Claude Code dentro do seu repositório e diga:

> Monta minha memória viva.

Pra atualizar depois: `cd ~/.claude/skills/mscs-segundo-cerebro && git pull`.

Confira a instalação com `/skills` — deve aparecer `mscs-segundo-cerebro`.

---

## A estrutura

```
seu-repo/
├── raw/          ← captura: os samples, tudo que entra cru
├── wiki/         ← memória: ligada, destilada, na sua voz
│   ├── index.md
│   └── log.md
├── voz.md        ← assinatura de voz, cresce a cada mixagem
└── CLAUDE.md     ← protocolo da memória viva
```

---

## Pra quem é

- **Comunidade MS CREATIVE KEYS** — é um módulo do programa. Seu repo pessoal ganha uma memória que escreve na sua voz.
- **Qualquer pessoa** — funciona standalone. Você só precisa de um repositório em markdown. Não exige nenhuma skill interna MSCS; se você tiver (`travessia`, `mscs-wiki`), a memória se integra mais fundo.

---

## Créditos

- **Ideia de wiki viva:** [Andrej Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- **Lógica de mixagem e operação por verbos:** MSCREATIVE.SYSTEMS™ · MS CREATIVE KEYS

## Licença

MIT — veja [LICENSE](./LICENSE).

---

*MSCREATIVE.SYSTEMS™ · MS CREATIVE KEYS*
