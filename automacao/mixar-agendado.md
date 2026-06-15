# /mixar agendado — brief de síntese noturno

> Spec de design. Não roda nada ainda — projeta o fluxo pra deployar quando houver VPS.
> Base: a camada N8N do [[automacao-do-segundo-cerebro]] (thread @DamiDefi). Loop: [[sintese-nao-resumo]], [[captura-sem-friccao]].

## O que é

Um job que roda de madrugada, lê o que entrou em `raw/` nas últimas 24h cruzado com a `wiki/` inteira, e deixa um **brief de síntese** esperando quando eu sento. Não escreve página. Não mexe na memória. Sintetiza e some — regenerável todo dia.

A linha que organiza: **a peneira é da máquina; a decisão é minha.** Mixar (escrever `wiki/`) continua com humano no loop — destila, precisa de voz e julgamento. O brief só aponta onde olhar.

## As 4 seções (fixas)

1. **Conexões não-óbvias** — pares que eu não veria revisando nota por nota: uma captura nova de `raw/` que toca uma página antiga de `wiki/`. Cita as duas pontas.
2. **Padrão se formando** — um tema atravessando ≥3 capturas/notas. O que está pedindo página própria e ainda não tem.
3. **Contradição** — a peça desconfortável. Cruza minhas teses (`wiki/`) contra as fontes novas (`raw/`) e **só procura conflito**. A evidência que ataca, não a que confirma. Surge o que eu estava evitando notar.
4. **Melhor captura pra desenvolver** — qual `raw/` novo tem mais sinal pra virar página ou conteúdo. Uma só. Com o porquê.

Cada seção: 2–4 linhas, na minha voz (`voz.md`). Vazio honesto vence preenchimento — "nada novo cruzou hoje" é resposta válida.

## Fluxo

```
05:00  cron dispara
  │
  ├─ git pull            sincroniza o vault no VPS
  ├─ lê raw/ mtime<24h   só capturas novas
  ├─ lê wiki/ + voz.md   contexto: memória + registro de voz
  │
  ├─ Anthropic API       monta o prompt → brief de 4 seções
  │
  ├─ escreve briefs/AAAA-MM-DD.md
  ├─ git commit + push
  └─ Telegram (opcional) manda o brief no celular ao acordar
```

## Onde o brief mora

`briefs/AAAA-MM-DD.md` — pasta própria, fora de `raw/` (raw nunca se apaga; brief é regenerável). Frontmatter mínimo: `data`, `fontes` (lista dos `raw/` lidos). Entrega paralela opcional no Telegram pra ler antes de abrir o laptop.

## Modelo e custo

- Brief diário: **Sonnet 4.6** — a leitura cruzada é o trabalho pesado.
- Triagem/filtro de arquivos: **Haiku 4.5**, se precisar baratear.
- VPS US$ 5–7/mês + API no volume de um vault pessoal = **alvo US$ 8–15/mês**. Menos que uma hora de assistente.

## Variante semanal — /revisar (caça a contradição)

A seção 3 vira um disparo próprio, semanal e mais fundo. Cron domingo à noite, **Opus** (vale o custo numa vez por semana), lê a `wiki/` inteira contra todo `raw/` da semana e devolve só contradições + páginas órfãs + conceitos sem página. É o `/revisar` do protocolo, agendado. Spec deriva deste arquivo trocando: cron semanal, escopo = wiki inteira, output = `briefs/revisao-AAAA-MM-DD.md`.

## Pré-requisitos pra deployar (sessão com acesso)

- [ ] VPS com Docker (n8n self-hosted). Laptop fechado não dispara — isso quebra tudo.
- [ ] Vault clonado no VPS + deploy key (GitHub SSH) com push.
- [ ] Anthropic API key (credencial httpHeaderAuth no n8n).
- [ ] (opcional) Bot do Telegram via BotFather + chat_id, pra entrega no celular.
- [ ] Importar `automacao/n8n/mixar-noturno.workflow.json`, preencher os `TODO`, ativar.

## Prompt do brief (rascunho — ajustar no deploy)

```
Você é a Memória Viva. Leia voz.md e escreva no registro dele.

CONTEXTO (não repita, use pra cruzar):
- wiki/: {todas as páginas}
- voz.md: {assinatura de voz}

NOVO (últimas 24h):
- raw/: {capturas novas}

Devolva um brief de 4 seções, 2–4 linhas cada, na voz do voz.md:
1) Conexões não-óbvias — capturas novas que tocam páginas antigas. Cite as duas pontas.
2) Padrão se formando — tema em ≥3 fontes pedindo página própria.
3) Contradição — só conflito: tese da wiki vs. fonte nova. A evidência que ataca.
4) Melhor captura pra desenvolver — uma só, com o porquê.

Seção sem matéria-prima real: escreva "—". Não invente sinal.
Síntese, não resumo. Não condense o vault. Cruze o vault.
```
