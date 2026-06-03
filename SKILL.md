---
name: mscs-segundo-cerebro
description: Monta e opera uma memória viva no repositório do usuário — uma pasta de markdown que um LLM atravessa (raw → wiki) e calibra na voz do dono, pra virar artefato. Use quando alguém quiser montar um segundo cérebro, uma memória viva, uma wiki viva estilo Karpathy, organizar conversas/pesquisa em markdown, calibrar um sistema na própria voz, ou instalar os comandos de travessia /atravessar, /lembrar, /produzir. Dispara em "montar minha memória viva", "segundo cérebro", "wiki viva no meu repo", "atravessar meu material bruto", "sistema que escreve na minha voz", "exportei meu ChatGPT e agora". Use mesmo que o usuário cite só uma parte (captura, travessia ou produção).
---

# Memória Viva — MSCREATIVE.SYSTEMS™

Andrej Karpathy mostrou uma coisa simples e forte: uma pasta de markdown mais um LLM viram uma wiki viva. Você joga material numa pasta, o LLM organiza, conecta e mantém. O repo é a IDE, o LLM é o programador, a wiki é o código-fonte.

Esta skill leva essa ideia adiante com o método da MSCS: a **travessia**. A memória aqui não fica parada esperando você consultar. Ela atravessa o bruto — tira o sinal, conecta com o que já existe, e calibra tudo na sua voz. O destino do que entra é virar artefato: post, e-mail, roteiro, proposta. Memória que trabalha.

## O ciclo

Três movimentos, em loop:

1. **Captura** — tudo que entra vai cru pra `raw/`. Conversa com IA, ideia solta, transcrição, recorte, nota de reunião. Sem organizar. Só capturar.
2. **Travessia** — o sistema atravessa o que está em `raw/`: destila o sinal, escreve na `wiki/` na sua voz, conecta com wikilinks ao que já existe, e reforça seu perfil de voz. Bruto vira memória.
3. **Produção** — sob demanda, o sistema produz puxando da `wiki/`, na sua voz, no formato do destino.

A voz é a espinha. A cada travessia, o sistema aprende mais sobre como você pensa e escreve, e grava isso em `voz.md`. Por isso o que ele produz soa como você, não como um LLM genérico.

A estrutura, em nomes do Karpathy:

```
seu-repo/
├── raw/          ← captura: tudo que entra, cru
├── wiki/         ← memória: destilada, conectada, na sua voz
│   ├── index.md  ← porta de entrada da memória
│   └── log.md    ← diário das travessias
├── voz.md        ← perfil de voz que cresce a cada travessia
└── CLAUDE.md     ← protocolo da memória viva
```

## Como conduzir

O usuário pode ser leigo. Pode estar abrindo o Terminal pela primeira vez. Fale em português claro. Explique o que cada comando faz antes de rodar. Em cada passo, diga de quem é a bola: o que o Claude Code faz e o que só o usuário faz. Quando a vez for do usuário, pare e espere.

Voz: frases curtas, voz ativa, zero floreio. Sem "game-changer", "transformador", "alavancar". Sem "vale notar que".

## Montagem

### Pré-requisito

Um repositório pessoal em markdown. Se o usuário é aluno do MSCREATIVE KEYS, esse repo já existe (montado na Semana 2, organizado na Semana 4) — a memória viva entra dentro dele. Se não tem repo ainda, ofereça montar: pasta local + `git init` + repo no GitHub. Use nome sem espaços.

### Criar as camadas (o Claude Code faz)

Na raiz do repo:

```bash
mkdir -p raw wiki
```

Crie `voz.md` com um esqueleto curto (como o usuário escreve, o que evita, referências de tom). Se o repo já tem `writing-style.md` ou `voice_profile` (aluno MSCS tem), aponte `voz.md` pra ele em vez de duplicar.

Copie o protocolo da memória pra raiz:

```bash
cp ~/.claude/skills/mscs-segundo-cerebro/CLAUDE.md ./CLAUDE.md
```

Se o repo já tem um `CLAUDE.md`, não sobrescreva. Acrescente a seção da memória viva ao final, preservando o que já existe.

### Semear a memória (opcional)

Pra começar com lastro em vez de pasta vazia, o usuário pode semear `raw/` com o histórico de IA dele.

> Exporte seu histórico: em chatgpt.com (Settings → Data Controls → Export data, demora até 3 dias) e em claude.ai (Settings → Privacy → Export Data, chega em minutos). Descompacte e arraste pra `raw/historico-ia/`.

Depois é só atravessar (próxima seção). O histórico passa pela mesma travessia que qualquer outro bruto.

## Os três verbos

A memória viva se opera por três comandos. Esta skill traz os três prontos em `commands/`. Copie pro repo do usuário:

```bash
mkdir -p .claude/commands
cp ~/.claude/skills/mscs-segundo-cerebro/commands/*.md ./.claude/commands/
```

- **`/atravessar`** — o verbo central. Pega o que está em `raw/` ainda não processado, destila pra `wiki/`, conecta, e atualiza `voz.md`. É a travessia: bruto vira memória.
- **`/lembrar [tema]`** — consulta a memória. O que você já sabe e já disse sobre um tema, com as conexões. Responde da `wiki/` primeiro; se não cobre, aponta o que falta atravessar.
- **`/produzir [tema]`** — gera um artefato na sua voz, puxando da `wiki/` e do `voz.md`. Marca onde a memória ainda é rasa.

O fluxo do dia a dia: você captura em `raw/` quando algo aparece. Roda `/atravessar` quando quiser que entre na memória. Roda `/lembrar` antes de começar algo. Roda `/produzir` quando for criar.

## A voz que cresce

`voz.md` é o que separa esta memória de um arquivo morto. Toda travessia que revela algo sobre como o usuário pensa ou escreve volta pra lá. Com o tempo, `voz.md` vira um retrato fiel — e o `/produzir` soa como o dono, não como um modelo.

Oriente o usuário a revisar `voz.md` de vez em quando: cortar o que não é mais verdade, reforçar o que é. A voz também atravessa.

## Manutenção

A cada uma ou duas semanas, peça uma checagem de saúde da memória:

> Revise a wiki: páginas que se contradizem, páginas órfãs (sem conexão), conceitos citados em vários lugares que ainda não têm página própria, páginas inchadas que pedem divisão. Proponha os ajustes, não execute ainda.

E termine toda travessia importante com `git add`, `commit`, `push`. A memória só fica segura quando vai pro GitHub.

## Integração com o sistema MSCS

Se o usuário tem o ecossistema MSCS, a memória viva se encaixa como substrato:

- A skill **`travessia`** é o motor profundo de destilação e calibração de voz. Quando instalada, use-a dentro do `/atravessar` pra destilar e calibrar com mais profundidade.
- A skill **`mscs-wiki`** mantém conhecimento persistente por projeto. A memória viva alimenta e é alimentada por ela.
- Skills de produção (supercopy e afins) puxam da `wiki/` e do `voz.md` como fonte.

A skill funciona sozinha, sem nada disso. A integração é bônus pra quem é MSCS.

## Extensão opcional: memória no celular

Quem quiser falar com a memória pelo telefone pode ligar o iMessage Channels do Claude Code (`claude --channels plugin:imessage@claude-plugins-official`) e os conectores MCP (Gmail, Granola). Aí `/lembrar` e `/produzir` respondem por mensagem. É extensão, não o centro — o centro é a travessia.

## O que costuma travar

- **Nome de pasta com espaço** — quebra o tratamento de caminho. Uma palavra só, ou com hífen.
- **Rodar `claude` sem `cd` no repo** — o Claude Code lê da pasta onde o terminal está. Sem o `cd`, não vê `raw/`.
- **Atravessar sem voz** — se `voz.md` está vazio, a wiki sai genérica. Preencha um esqueleto antes da primeira travessia.
- **Capturar e nunca atravessar** — `raw/` vira depósito. A memória só cresce quando você roda `/atravessar`.
- **Esquecer de commitar** — a memória só fica segura no GitHub. Feche cada travessia com `git push`.

---

> Construído sobre a ideia de wiki viva de [Andrej Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f): uma pasta de markdown (`raw/` → `wiki/`) que um LLM compila e mantém viva.
>
> O método da travessia — captura → destilação → calibração na voz → produção — e a operação por verbos são da MSCREATIVE.SYSTEMS™.
>
> MSCREATIVE.SYSTEMS™ · MS CREATIVE KEYS
