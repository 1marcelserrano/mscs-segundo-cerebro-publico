# Changelog

## v2.0.0 — 2026-06-03

Reinvenção como **memória viva**. Deixa de ser uma localização do fluxo de segundo cérebro e passa a ser uma adaptação própria da MSCS sobre a ideia do Karpathy.

- Método novo: o **ciclo da travessia** — captura (`raw/`) → travessia (destila + conecta + calibra na voz) → produção. A memória trabalha pra virar artefato, não pra arquivar.
- `voz.md`: perfil de voz que cresce a cada travessia e calibra o que o sistema produz.
- Operação por verbos: `/atravessar`, `/lembrar`, `/produzir` (substituem `/hoje`, `/ideias`, `/criar`).
- `CLAUDE.md` reescrito como protocolo da memória viva (operações Atravessar / Lembrar / Produzir / Revisar).
- iMessage e MCP viram extensão opcional, não o centro.
- Crédito mantido só à ideia de wiki viva do Karpathy. Método da travessia é da MSCS.

## v1.0.0 — 2026-06-03

Primeira versão pública.

- Skill `mscs-segundo-cerebro`: conduz a travessia das três fases (Acervo, Wiki Viva, Batimento).
- `CLAUDE.md`: compilador da wiki viva em português, voz MSCS, adaptado do padrão Karpathy.
- Slash commands `/hoje`, `/ideias`, `/criar`.
- Baseado no padrão de wiki viva de Andrej Karpathy. Diferença MSCS-native: o cérebro vive dentro do repositório GitHub pessoal, versionado e portável, em vez de num vault Obsidian solto.
