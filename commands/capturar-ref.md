---
description: Captura uma referência externa em raw/ e mixa na hora pra wiki/ — tweet, thread, artigo, vídeo, talk, podcast, trecho de livro
argument-hint: [url, texto colado, @arquivo ou "isso"]
---

Capture esta referência externa: $ARGUMENTS

Se eu disser "isso", a referência é a externa mais recente desta conversa (o último tweet, link, trecho ou vídeo que apareceu).

1. Leia a referência inteira. Se for url, puxe o conteúdo; se for texto colado, use o que eu colei; se for `@arquivo`, leia o arquivo.
2. Crie `raw/AAAA-MM-DD_<slug>.md` a partir de `templates/captura_referencia.md`. Preencha os 9 campos na minha voz (leia `voz.md`). Campo sem matéria-prima na fonte = "—". Não encha linguiça.
3. **Quote bruto: copie verbatim.** Não reescreva o trecho da fonte. Se não tenho o texto fiel, deixe "—".
4. **Mixe na hora** (não deixe pra depois): crie ou atualize a página correspondente em `wiki/`, curta e na minha voz, com pelo menos um wikilink `[[...]]` ligando ao que a memória já sabe.
5. Marque a nota de `raw/` como `status: mixado`.
6. Atualize `wiki/index.md` (uma linha) e `wiki/log.md` (data + o que entrou + o que ligou).
7. **Monte o prompt de handoff:** pegue a melhor ideia de aplicação ou conteúdo e transforme num prompt pronto pra colar num Claude Code que implementa aquilo — concreto, na minha voz, com o arquivo/caminho alvo quando souber. Grave no campo "Prompt de handoff" da nota. É a entrega que tira a ideia do papel.
8. Me devolva três linhas: o que entrou, com o que ligou, a melhor ideia que saiu. Depois cole o prompt de handoff e pergunte se rodo agora, guardo, ou ajusto.

Frases curtas. Sem clichê de IA. Sem floreio.
