# Segundo Cérebro — MSCREATIVE.SYSTEMS™

> Uma skill de Claude Code que te conduz a construir um segundo cérebro de IA — vivo, buscável, e que **mora dentro do seu próprio repositório GitHub**. Markdown puro. Versionado. Portável entre LLMs.

Em 3 de abril de 2026, [Andrej Karpathy](https://github.com/karpathy) publicou um gist de 1.500 palavras descrevendo como montar uma wiki pessoal com uma pasta de markdown (`raw/` → `wiki/`) e um LLM. Em 48 horas, a thread no X bateu **16 milhões de views**.

Esta skill leva essa ideia adiante, em português, na comunidade MS CREATIVE KEYS. A diferença central: aqui o cérebro não vive num vault de Obsidian solto na sua Mesa. Vive **dentro do seu repositório GitHub pessoal** — o mesmo repo que você usa como sistema operacional criativo. Versionado, com backup, portável pra qualquer LLM. O Obsidian entra opcional, só pra visualizar o grafo.

---

## O que ela faz

A travessia tem três fases. Faça as três ou escolha uma.

1. **O Acervo** — exporta seu histórico de ChatGPT e Claude e o destila em markdown taggeado e linkado, commitado no seu repo.
2. **A Wiki Viva** — você larga fontes brutas em `raw/`, o Claude Code compila artigos estruturados em `wiki/`. Cresce toda vez que você alimenta.
3. **O Batimento** — conectores MCP (Gmail, Granola, NotebookLM) + iMessage Channels + os slash commands `/hoje`, `/ideias`, `/criar`. O cérebro responde do seu celular.

---

## Instalar

O jeito confiável (funciona em qualquer Mac, fácil de atualizar depois):

```bash
git clone https://github.com/1marcelserrano/mscs-segundo-cerebro.git ~/.claude/skills/mscs-segundo-cerebro
```

Se `~/.claude/skills/mscs-segundo-cerebro` já existir, faça backup antes:

```bash
mv ~/.claude/skills/mscs-segundo-cerebro ~/.claude/skills/mscs-segundo-cerebro.backup
```

Abra o Claude Code em qualquer pasta e diga:

> Monta meu segundo cérebro.

Pra atualizar depois:

```bash
cd ~/.claude/skills/mscs-segundo-cerebro && git pull
```

### Conferir se instalou

No Claude Code, digite:

```
/skills
```

Você deve ver `mscs-segundo-cerebro` na lista. Se não aparecer, a pasta está no lugar errado — rode o clone de novo e confira o caminho de destino.

---

## O que vem no pacote

| Arquivo | Função |
|---|---|
| `SKILL.md` | A skill que conduz a travessia das três fases |
| `CLAUDE.md` | O compilador da wiki viva (copiado pra raiz do seu repo) |
| `commands/hoje.md` | Slash command `/hoje` — plano do dia |
| `commands/ideias.md` | Slash command `/ideias` — ideias de conteúdo |
| `commands/criar.md` | Slash command `/criar` — rascunho na sua voz |

---

## Pra quem é

- **Comunidade MS CREATIVE KEYS** — este é um módulo do programa. Seu repo pessoal (montado nas Semanas 2 e 4) ganha um cérebro e um batimento.
- **Qualquer pessoa** — funciona standalone. Você só precisa de um repositório GitHub pessoal pra abrigar o cérebro. Não exige nenhuma skill interna MSCS.

---

## Créditos

- **Padrão de wiki viva:** [Andrej Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- **Adaptação MSCS-native:** MSCREATIVE.SYSTEMS™ · MS CREATIVE KEYS

## Licença

MIT — veja [LICENSE](./LICENSE).

---

*MSCREATIVE.SYSTEMS™ · MS CREATIVE KEYS*
