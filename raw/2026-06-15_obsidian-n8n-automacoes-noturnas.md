---
titulo: 9 automações que rodam no Obsidian enquanto Dami-Defi dorme
fonte: https://x.com/DamiDefi — thread "9 Things My Obsidian Vault Does While I Sleep"
autor: Dami-Defi (@DamiDefi)
data: 2026-06-15
formato: thread
tags: [automacao, segundo-cerebro, n8n, obsidian, claude-api, fluxo-de-trabalho]
status: mixado
---

# 9 automações que rodam no Obsidian enquanto Dami-Defi dorme

## Fonte / autor / data
Thread de Dami-Defi (@DamiDefi) no X, "9 Things My Obsidian Vault Does While I Sleep". Capturei em 2026-06-15.

## Resumo
Ele montou uma camada de N8N por baixo do Obsidian. Não automatiza o pensamento — automatiza a infraestrutura ao redor dele. Nove fluxos rodam de madrugada e de manhã: síntese, triagem do inbox, caça a contradição, ressurgência de highlights antigos, backup. Quando ele senta, seis horas de trabalho já aconteceram. O vault deixa de ser onde ele busca coisa salva e vira um sistema que traz coisa até ele.

## Insights-chave
- A regra que organiza tudo: automatizar a infraestrutura do pensamento, não o pensamento.
- Síntese ≠ resumo. Ele já sabe o que tem no vault. O valor é a IA ler tudo de uma vez e achar a ligação que ele não faria revisando notas isoladas.
- A caça é por contradição, não por concordância. O fluxo só procura a evidência que ataca a tese, não a que confirma.
- Captura sem fricção é o mecanismo inteiro. Ideia em Telegram vira nota no vault em 30 segundos. Quando capturar não custa nada, tudo que vale fica.
- Estrutura de cinco pastas: 00-Inbox, 01-Sources, 02-Ideas, 03-Projects, 04-Claude. As automações operam nos limites entre elas.
- Custo real do stack inteiro: US$ 8–15/mês (Haiku 4.5 pra maioria, Sonnet 4.6 nos pesados, VPS US$ 5–7). Uma hora de assistente custa mais que um mês do sistema.
- Pré-requisito que quebra tudo se ignorado: o N8N precisa rodar fora do laptop (VPS), senão a automação noturna não dispara.
- Backup à meia-noite é o fluxo mais simples e o mais importante: git commit do vault inteiro num repo privado, todo dia.

## Quote bruto
> That is the point of building the N8N layer underneath Obsidian. Not to automate the thinking. To automate the infrastructure around the thinking so that by the time I sit down in the morning, six hours of work has already happened. Connections made. Contradictions surfaced. Sources aged. Inbox processed. Questions tracked.

> This is not a summary. I already know what is in my vault. The brief is a synthesis. Claude reads across everything and finds what I would not have found manually by reviewing yesterday's captures in isolation.

> The vault is not where I go to find things I saved. It is a system that brings things to me.

## Conexão com curso / sistema
É a versão "máquina rodando sozinha" da [[automacao-do-segundo-cerebro]]. A Memória Viva já faz o trabalho cognitivo — mixar, ligar, destilar, caçar contradição na revisão. O que o Dami-Defi mostra é o agendamento: rodar isso sem eu pedir. O gatilho de captura por Telegram é a mesma lógica do "manda isso pro Obsidian" do nosso protocolo, só que sem fricção e a qualquer hora. Liga direto a [[captura-sem-friccao]] e a [[sintese-nao-resumo]].

## Ideia de aplicação pro MSCS
- Um `/mixar` agendado: roda toda manhã sobre o que entrou em `raw/` nas últimas 24h e devolve o brief de síntese no topo do dia.
- Adaptar a "caça a contradição" pro nosso `/revisar`: hoje ele só roda sob demanda. Virar um disparo semanal que cruza `wiki/` (minhas teses) contra o `raw/` novo.
- Pipeline de Telegram → `raw/`: ideia de rua vira sample cru sem abrir o laptop. Mixo depois.
- Backup noturno do repo já é nativo do nosso setup (é git). O dele valida o hábito.

## Ideia de conteúdo adaptado
Post do Fronteirista: "Meu segundo cérebro trabalha enquanto eu durmo." Tese central — não automatize o pensamento, automatize a infraestrutura ao redor dele. Mostrar a diferença entre resumo e síntese com um exemplo real de contradição que eu estava evitando e a máquina jogou na minha cara. Fechar com o custo: menos que uma hora de assistente por mês.
