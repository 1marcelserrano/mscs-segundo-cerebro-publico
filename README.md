# Memória Viva — MSCREATIVE.SYSTEMS™

> Uma skill de Claude Code que monta uma **memória viva** dentro do seu repositório: uma pasta de markdown que o sistema **atravessa** — destila o bruto, conecta, calibra na sua voz — pra virar artefato. Markdown puro. Versionado. Portável.

Em 3 de abril de 2026, [Andrej Karpathy](https://github.com/karpathy) publicou um gist descrevendo como montar uma wiki pessoal com uma pasta de markdown (`raw/` → `wiki/`) e um LLM. Em 48 horas, a thread no X bateu **16 milhões de views**. A ideia: o repo é a IDE, o LLM é o programador, a wiki é o código-fonte.

Esta skill leva essa ideia adiante com o método da MSCS — a **travessia**. A memória aqui não fica parada esperando consulta. Ela atravessa o bruto até virar material calibrado na sua voz, pronto pra produzir. O destino do que entra é virar artefato: post, e-mail, roteiro, proposta. Memória que trabalha.

---

## O ciclo

```
  captura          travessia              produção
  ───────          ─────────              ────────
  raw/      →    destila + conecta    →   artefato
                 + calibra na voz         na sua voz
                       │
                     voz.md  (cresce a cada travessia)
```

1. **Captura** — tudo que entra vai cru pra `raw/`. Conversa, ideia, transcrição, recorte.
2. **Travessia** — o sistema destila o sinal, escreve na `wiki/` na sua voz, conecta, e reforça seu `voz.md`.
3. **Produção** — sob demanda, produz puxando da `wiki/`, na sua voz, no formato do destino.

A voz é a espinha. A cada travessia o sistema aprende como você pensa e escreve. Por isso o que ele produz soa como você.

---

## Os três verbos

| Comando | O que faz |
|---|---|
| `/atravessar` | Pega o bruto novo em `raw/`, destila pra `wiki/`, conecta e atualiza `voz.md` |
| `/lembrar [tema]` | Consulta a memória: o que você já sabe e já disse, com as conexões |
| `/produzir [tema]` | Gera um artefato na sua voz, puxando da memória |

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
├── raw/          ← captura: tudo que entra, cru
├── wiki/         ← memória: destilada, conectada, na sua voz
│   ├── index.md
│   └── log.md
├── voz.md        ← perfil de voz que cresce a cada travessia
└── CLAUDE.md     ← protocolo da memória viva
```

---

## Pra quem é

- **Comunidade MS CREATIVE KEYS** — é um módulo do programa. Seu repo pessoal ganha uma memória que escreve na sua voz.
- **Qualquer pessoa** — funciona standalone. Você só precisa de um repositório em markdown. Não exige nenhuma skill interna MSCS; se você tiver (`travessia`, `mscs-wiki`), a memória se integra mais fundo.

---

## Créditos

- **Ideia de wiki viva:** [Andrej Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- **Método da travessia e operação por verbos:** MSCREATIVE.SYSTEMS™ · MS CREATIVE KEYS

## Licença

MIT — veja [LICENSE](./LICENSE).

---

*MSCREATIVE.SYSTEMS™ · MS CREATIVE KEYS*
