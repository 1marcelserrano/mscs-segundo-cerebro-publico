---
name: mscs-segundo-cerebro
description: Conduz o usuário na construção de um segundo cérebro de IA que vive dentro do próprio repositório GitHub — versionado, portável e em markdown puro. Use quando alguém quiser montar um segundo cérebro, organizar o histórico de ChatGPT/Claude, montar uma wiki viva estilo Karpathy, conectar o cérebro ao celular via iMessage, ou instalar os slash commands /hoje, /ideias, /criar. Dispara em frases como "montar meu segundo cérebro", "organizar minhas conversas de IA", "wiki viva no meu repo", "exportei meu ChatGPT e agora", "segundo cérebro MSCS", "dar batimento ao meu repo". Use mesmo quando o usuário citar só uma das três fases (Acervo, Wiki Viva, Batimento).
---

# Segundo Cérebro — MSCREATIVE.SYSTEMS™

Esta skill conduz o usuário a transformar anos de conversas com IA, pesquisa bruta e inputs diários num **sistema vivo** que ele consulta — e que cresce sozinho conforme ele alimenta.

A diferença em relação a outros guias de "segundo cérebro": aqui o cérebro **mora dentro do repositório GitHub pessoal** do usuário, em markdown puro. Versionado. Portável entre LLMs. Sem depender de Obsidian, de app pago, ou de plataforma que pode fechar amanhã. O Obsidian entra opcional, só pra visualizar o grafo.

Se o usuário é aluno do MSCREATIVE KEYS, esse repo já existe (foi montado na Semana 2 e organizado na Semana 4). Esta skill dá a ele um cérebro e um batimento.

## A travessia tem três fases

O usuário pode fazer as três ou escolher uma. Confirme no começo qual ele quer.

1. **O Acervo** — exportar o histórico de ChatGPT e Claude e destilá-lo em markdown taggeado e linkado, dentro do repo pessoal.
2. **A Wiki Viva** — uma base de conhecimento que cresce sozinha: o usuário joga fontes brutas em `raw/`, o Claude Code compila artigos estruturados em `wiki/`.
3. **O Batimento** — conectores MCP, iMessage Channels e os slash commands `/hoje`, `/ideias`, `/criar`. O cérebro passa a responder do celular.

## Como conduzir

O usuário pode ser leigo total. Pode estar abrindo o Terminal pela primeira vez. Fale em português claro. Nunca presuma familiaridade com linha de comando. Explique o que cada comando faz **antes** de rodar.

Em cada fase há coisas que o Claude Code faz (criar pastas, baixar arquivos, escrever a wiki) e coisas que só o usuário faz (pedir a exportação na OpenAI, dar permissão no macOS, logar num navegador). Diga sempre de quem é a bola. Quando a vez for do usuário, **pare e espere**.

Se ele disser "pula a fase 1, já fiz" ou "só quero a fase 3", respeite. Confirme o que já existe e entre direto.

Regra de voz: frases curtas, voz ativa, zero floreio. Sem "game-changer", "transformador", "turbinar", "alavancar". Sem "Não é X, é Y". Sem "vale notar que".

## Fase 0: Checagem inicial

Antes de tocar em qualquer coisa, confirme o que o usuário tem:

> Antes de começar, uma checagem rápida. Você tem:
> 1. **Claude Code** instalado e funcionando? (se está falando comigo, tem)
> 2. **Um repositório GitHub pessoal** já criado? (onde o cérebro vai morar)
> 3. Alguma **exportação de dados do ChatGPT ou Claude** já pedida? (a da OpenAI demora 1 a 3 dias, então talvez a gente comece agora e volte)

Se o usuário **não tem repo pessoal ainda**, esse é o pré-requisito. Ofereça montar um do zero: uma pasta local + `git init` + um repo privado no GitHub. Estrutura mínima:

```
meu-cerebro/
├── README.md
├── .gitignore
├── about-me.md          ← quem é o usuário (pra IA ler)
├── acervo/              ← Fase 1: histórico de IA destilado
├── raw/                ← Fase 2: fontes que ainda não viraram wiki
└── wiki/                ← Fase 2: conhecimento compilado e vivo
```

Use um nome de pasta **sem espaços** (`meu-cerebro`, não `meu cerebro`). Espaço no caminho quebra o tratamento de arquivos.

Confirme onde o cérebro vai viver. Padrão: a raiz do repo pessoal do usuário. Se ele não tem preferência, use `~/Documents/repos/meu-cerebro`.

## Fase 1: O Acervo

A meta: virar anos de conversa com IA em markdown taggeado, linkado e buscável, **commitado no repo**.

### 1a. Pedir as exportações (o usuário faz)

Isto é só do usuário. Conduza pelos dois:

**ChatGPT** (faça PRIMEIRO — demora até 3 dias):
> Vá em chatgpt.com → ícone do seu perfil (canto superior direito) → Settings → Data Controls → "Export data". A OpenAI manda um link por e-mail. Me avise quando tiver pedido.

**Claude** (chega em ~5 minutos):
> Vá em claude.ai → ícone do perfil (canto inferior esquerdo) → Settings → Privacy → "Export Data". O e-mail chega em uns 5 minutos. Me avise quando tiver baixado e descompactado os dois ZIPs.

Espere o usuário confirmar. Se ele disser "a do ChatGPT vai demorar dias, o que faço enquanto isso" — sugira ir pra Fase 2 (Wiki Viva), que não depende das exportações.

### 1b. Trazer os arquivos pro repo (o Claude Code faz)

Quando o usuário tiver os dois ZIPs descompactados, crie a pasta de acervo no repo:

```bash
mkdir -p ~/Documents/repos/meu-cerebro/acervo
```

Peça pro usuário arrastar as duas pastas descompactadas pra dentro de `acervo/`. Depois confirme:

```bash
ls ~/Documents/repos/meu-cerebro/acervo
```

### 1c. Destilar tudo (o Claude Code faz — aqui mora a mágica)

Abra uma sessão de Claude Code apontada pra pasta do repo. Oriente o usuário:

> Abra uma janela nova de Terminal (Cmd+Espaço, digite Terminal, Enter). Cole:
> ```
> cd ~/Documents/repos/meu-cerebro
> claude
> ```
> Com o Claude Code rodando ali, cole este prompt:
> ```
> Organize a pasta acervo/ deste repositório. Converta todas as minhas
> conversas de ChatGPT e Claude em arquivos markdown individuais, cada um
> com frontmatter (titulo, data, tags, categoria). Depois rode sub-agentes
> em paralelo pra ler cada conversa e taggear com inteligência: nomes,
> pessoas, lugares, temas recorrentes, projetos e tópicos. Conecte tudo com
> wikilinks pra que conversas relacionadas se liguem. No fim, escreva um
> acervo/index.md listando cada arquivo com uma linha de descrição.
> ```

Isso roda alguns minutos. Quando terminar, oriente:
> Commite tudo: `git add acervo/ && git commit -m "Acervo destilado" && git push`. Agora seu histórico de IA é versionado e buscável.

**Opcional — grafo no Obsidian.** Se o usuário quiser ver as conexões visualmente:
> Baixe o Obsidian (grátis, em obsidian.md). Abra → "Open folder as vault" → selecione a pasta do seu repo. Cmd+G abre o grafo. Cada conversa é um nó linkado. Dá uma passeada.

## Fase 2: A Wiki Viva

O Acervo organiza o passado. A Wiki Viva é conhecimento que **cresce** toda vez que o usuário joga material novo. Ele larga fontes brutas em `raw/`, o Claude Code compila artigos estruturados em `wiki/`.

A imagem do Karpathy vale citar pro usuário: *"O Obsidian é a IDE. O LLM é o programador. A wiki é o código-fonte."* Aqui troque "Obsidian" por "seu repo".

### 2a. Criar a estrutura (o Claude Code faz)

No mesmo repo, crie as duas pastas e baixe o arquivo de instruções da wiki:

```bash
mkdir -p ~/Documents/repos/meu-cerebro/raw ~/Documents/repos/meu-cerebro/wiki
```

O compilador da wiki é um `CLAUDE.md` na raiz do repo. Esta skill traz uma versão em português, na voz MSCS, no arquivo `CLAUDE.md` deste repositório de skill. Copie esse arquivo pra raiz do repo do usuário:

```bash
cp ~/.claude/skills/mscs-segundo-cerebro/CLAUDE.md ~/Documents/repos/meu-cerebro/CLAUDE.md
```

Se o repo do usuário **já tem** um `CLAUDE.md` (aluno MSCS tem), não sobrescreva. Em vez disso, acrescente a seção de protocolo da wiki ao final do `CLAUDE.md` existente. Leia os dois, funda com cuidado, preserve o que já estava lá.

### 2b. Colocar fontes no `raw/` (o usuário lidera)

Dois caminhos — deixe o usuário escolher.

**Opção A: arrastar e soltar.** Oriente:
> Abra a pasta `raw/` no Finder. Jogue 5 a 10 fontes de um mesmo tema pra começar — PDFs, artigos salvos, transcrições, notas. Me avise quando terminar.

**Opção B: puxar do NotebookLM.** Requer a skill do NotebookLM. Se o usuário quiser, instale pra ele e conduza o login (mesmo fluxo da Fase 3, conectores). Depois peça a URL do notebook e rode:
> Puxe todas as fontes deste notebook do NotebookLM e salve como arquivos em raw/: [usuário cola a URL]

### 2c. Compilar a wiki (o Claude Code faz)

Com as fontes em `raw/`, rode:

> Processe cada fonte em raw/ usando as instruções de wiki do CLAUDE.md
> na raiz. Pra cada fonte, escreva uma página de resumo em wiki/, crie ou
> atualize as páginas de tópico e conceito relevantes, adicione wikilinks
> entre páginas relacionadas, e mantenha um wiki/index.md com cada página
> e uma linha de descrição.

Quando terminar, oriente o commit: `git add raw/ wiki/ CLAUDE.md && git commit -m "Wiki viva — primeira compilação" && git push`.

### 2d. Iterar (contínuo)

Oriente o usuário sobre o ritmo:
> A wiki não nasce perfeita. Mande o Claude Code ajustar: "divide esta página", "junta estas duas", "detalha mais aqui". A cada uma ou duas semanas, peça uma checagem de saúde: "verifique a wiki: contradições, páginas órfãs, conceitos faltando". Sempre commite depois.

> **Aluno MSCS:** se você tem a skill `travessia` instalada, ela é o motor natural pra atravessar o que está em `raw/` até virar artefato na sua voz. Use `travessia` pra destilar e calibrar, depois deixe o compilador da wiki organizar e linkar.

## Fase 3: O Batimento

Esta fase dá pulso à wiki. O usuário passa a conversar com o cérebro pelo celular. Três sub-passos.

### 3a. Conectores MCP

Três valem ligar primeiro:
- **Gmail** — artigos encaminhados, links de pesquisa, threads de e-mail
- **Granola** — transcrições de reunião, decisões, próximos passos
- **NotebookLM** — pra puxar notebooks existentes

Pra cada um que o usuário quiser, diga ao Claude Code:
> Conecte ao meu [Gmail / Granola / NotebookLM] pra puxar conteúdo novo pra wiki.

O NotebookLM exige um login no navegador **fora do Claude Code**. Conduza:
1. No Claude Code: `Instale a skill do NotebookLM pra eu puxar fontes dos meus notebooks.`
2. Depois de instalar, oriente:
   > Abra uma janela NOVA de Terminal (não rode dentro do Claude Code). Digite:
   > ```
   > notebooklm login
   > ```
   > Um navegador abre. Logue na conta Google, espere o NotebookLM carregar inteiro, volte ao Terminal e aperte Enter. Feche essa janela. Pronto.

### 3b. iMessage Channels

Aqui o cérebro ganha celular. O usuário monta um serviço no Mac que escuta iMessages enviados pro próprio número, processa contra a wiki e responde na mesma conversa.

Conduza:
> No Terminal, rode:
> ```
> claude --channels plugin:imessage@claude-plugins-official
> ```

O Claude Code vai pedir duas permissões do macOS. As duas são só do usuário:

**1. Acesso total ao disco pro Terminal.**
> O macOS vai pedir, ou você faz manual: Ajustes do Sistema → Privacidade e Segurança → Acesso Total ao Disco → ative o Terminal. Isso deixa o Claude Code ler os iMessages que chegam.

**2. Permissão de automação pro Mensagens.**
> Na primeira vez que o Claude Code tentar responder, o macOS pergunta se o Terminal pode controlar o Mensagens. Clique em **Permitir**.

Com as duas concedidas, teste:
> No celular, abra o iMessage e **mande uma mensagem pro seu próprio número**. Em segundos, o Claude Code detecta, processa contra a wiki e responde na mesma conversa.

Aviso pro usuário: se ele fechar o Claude Code no Mac, o Channels para de escutar. `claude --resume` retoma. Vale avisar antes pra ele não achar que quebrou.

### 3c. Os slash commands (o Claude Code faz)

Três comandos pra começar. Esta skill traz os três prontos na pasta `commands/`. Copie pro repo do usuário:

```bash
mkdir -p ~/Documents/repos/meu-cerebro/.claude/commands
cp ~/.claude/skills/mscs-segundo-cerebro/commands/*.md ~/Documents/repos/meu-cerebro/.claude/commands/
```

Ou scaffolde na hora, com os prompts abaixo. Em todos, peça pro usuário aprovar a escrita do arquivo.

**`/hoje`** — plano do dia (precisa de Gmail + Google Calendar + wiki):
> Crie um slash command chamado /hoje que lê meu Google Calendar do dia, checa o Gmail por algo urgente, e cruza os dois com a minha wiki pra puxar contexto sobre as pessoas e projetos envolvidos. Me dê um plano priorizado do dia. Salve como arquivo pra eu rodar /hoje quando quiser.

**`/ideias`** — ideias de conteúdo (precisa de Granola + Gmail + wiki):
> Crie um slash command chamado /ideias que lê minhas transcrições recentes do Granola, threads do Gmail e páginas da wiki, acha padrões e temas emergentes, e gera ideias de conteúdo pra criar, tópicos pra escrever e oportunidades que estou deixando passar. Salve como arquivo.

**`/criar`** — rascunho de conteúdo na voz do usuário (precisa da wiki + about-me):
> Crie um slash command chamado /criar que recebe um tema ou ideia, puxa o contexto relevante da minha wiki, lê meu about-me.md pra capturar minha voz, e produz uma peça pronta. Posts, rascunho de newsletter, roteiro de vídeo, esboço de carrossel. Salve como arquivo.

Depois de salvos, os comandos funcionam do celular também. Mandar `/hoje` pro próprio número no iMessage devolve o briefing do dia.

## Fechamento

Depois das três fases, diga ao usuário o que ele tem agora:
- Todo o histórico de IA, taggeado e linkado, versionado no repo
- Uma wiki que cresce toda vez que ele larga uma fonte nova
- Acesso pelo celular via iMessage
- Três comandos que puxam o dia, levantam ideias e rascunham na voz dele

Sugira o próximo gesto: largar uma fonte nova em `raw/`, depois mandar `/criar [tema dessa fonte]` pra si mesmo e sentir o ciclo fechar.

Se travou em algum passo, debug aquele ponto específico em vez de recomeçar do zero.

## O que costuma dar errado

- **Nome de pasta com espaço** ("meu cerebro" em vez de "meu-cerebro") — o tratamento de caminho quebra. Sempre uma palavra só, ou com hífen.
- **Rodar `claude` sem `cd` antes** — o Claude Code lê da pasta onde o terminal está. Sem o `cd`, os sub-agentes não veem os arquivos. Reconfirme o diretório antes de qualquer passo de organizar/processar.
- **Login do NotebookLM dentro do Claude Code** — tem que ser uma janela separada de Terminal. Senão o navegador não entrega o login.
- **Channels para depois do Mac dormir / Claude Code fechar** — `claude --resume` retoma. Avise antes.
- **Acesso Total ao Disco não apareceu** — às vezes o macOS precisa reiniciar o Terminal depois de conceder. Saia do Terminal de vez (Cmd+Q) e reabra.
- **Esquecer de commitar** — o cérebro só fica seguro quando vai pro GitHub. Termine cada fase com `git add`, `commit`, `push`.

---

> Baseado no padrão de wiki viva de [Andrej Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f): uma pasta de markdown (`raw/` → `wiki/`) que um LLM compila e mantém viva.
>
> Esta versão move o cérebro pra dentro do repositório GitHub pessoal — versionado e portável — e calibra a condução na voz MSCREATIVE.SYSTEMS™.
>
> MSCREATIVE.SYSTEMS™ · MS CREATIVE KEYS
