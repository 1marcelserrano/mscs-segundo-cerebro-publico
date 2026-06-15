---
titulo: Automação do segundo cérebro
fonte: raw/2026-06-15_obsidian-n8n-automacoes-noturnas.md
data: 2026-06-15
tags: [automacao, segundo-cerebro, n8n, obsidian, fluxo-de-trabalho]
---

# Automação do segundo cérebro

A regra: **automatizar a infraestrutura do pensamento, não o pensamento.**

A Memória Viva já faz o trabalho cognitivo — mixar, ligar, destilar. O que falta é o agendamento: rodar isso sem eu pedir, de madrugada, pra que de manhã o trabalho já esteja feito. Conexões prontas. Contradições na mesa. Inbox triado.

O Dami-Defi montou isso com uma camada de N8N por baixo do Obsidian. Nove fluxos. Quando ele senta, seis horas de trabalho já aconteceram.

## O que vale roubar

- **Brief de síntese diário** — a IA lê tudo que entrou na semana e devolve: conexões não-óbvias, padrão se formando, contradição, melhor captura pra desenvolver. É [[sintese-nao-resumo]], não relatório.
- **Caça a contradição agendada** — cruza minhas teses contra as fontes novas. Só procura conflito. Vira disparo semanal do `/revisar`.
- **Triagem do inbox** — classifica cada captura crua: desenvolver, arquivar, deletar. A decisão é minha; a peneira é da máquina.
- **Ressurgência** — highlights antigos lidos contra o que estou pensando agora. Conexão que estava parada acorda.
- **Backup noturno** — git commit do vault inteiro, todo dia. No nosso setup já é nativo.

## O pré-requisito que quebra tudo

O motor precisa rodar **fora do laptop**. Num VPS. Laptop fechado, automação noturna não dispara — e aí o sistema inteiro é teatro. Custo do stack: US$ 8–15/mês. Menos que uma hora de assistente.

## O ponto

O vault deixa de ser onde eu busco o que salvei. Vira sistema que traz coisa até mim. A captura por Telegram em [[captura-sem-friccao]] alimenta isso a qualquer hora.
