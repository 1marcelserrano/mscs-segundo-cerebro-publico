# Protocolo da Memória Viva

Este arquivo instrui o Claude Code a manter a memória deste repositório. A base é a ideia de wiki viva do Andrej Karpathy. A lógica é de estúdio: a mixagem da MSCREATIVE.SYSTEMS™.

Karpathy: o repo é a IDE, o LLM é o programador, a wiki é o código-fonte. A mixagem é o que mantém a wiki viva.

## As camadas

- **`raw/`** — captura. Os samples: conversas, transcrições, recortes, notas, histórico de IA. Material cru, sem ordem. Nunca se apaga nada daqui.
- **`wiki/`** — memória. Páginas curtas, ligadas, escritas na voz do dono. É o que se lê, consulta e usa pra produzir.
- **`voz.md`** — a assinatura de voz. A memória escreve nesse registro e bebe dele.

## Operações

### Mixar (`raw/` → `wiki/`)

Pra cada fonte em `raw/` ainda não mixada:

1. Leia inteiro. Extraia o sinal — a ideia, a decisão, o aprendizado. Descarte o ruído.
2. Escreva ou atualize a página correspondente em `wiki/`, curta e na voz do dono (consulte `voz.md`). Frontmatter:
   ```
   ---
   titulo: <claro e específico>
   fonte: <arquivo de origem em raw/>
   data: <AAAA-MM-DD>
   tags: [<tema>, <conceito>, <projeto>]
   ---
   ```
3. Concentre numa página só o que várias fontes dizem sobre o mesmo conceito.
4. Conecte com wikilinks (`[[nome-da-pagina]]`). Página sem conexão é sinal de mixagem pela metade.
5. Se a fonte revelou algo sobre como o dono pensa ou escreve, registre em `voz.md`.
6. Atualize `wiki/index.md` (cada página, uma linha) e `wiki/log.md` (data, o que entrou, o que mudou).

Regra: a memória destila, não copia. Cada página diz o essencial em menos palavras que o original.

### Lembrar (consulta)

Responda a partir da `wiki/` primeiro, citando as páginas. Mostre as conexões. Se a wiki não cobre, diga, e aponte o que em `raw/` ainda não foi mixado e poderia cobrir. Não invente o que a memória não tem.

### Produzir (artefato)

Puxe da `wiki/` o que toca o tema. Use o que é do dono, não conhecimento genérico. Escreva na voz dele (`voz.md`), no formato do destino. Marque onde a memória foi rasa.

### Revisar (saúde)

Quando pedirem, varra a `wiki/` e devolva: contradições, páginas órfãs, conceitos sem página própria, páginas inchadas, páginas duplicadas. Proponha os ajustes. Só execute depois de aprovado.

### Captura de referências externas (padrão)

Toda referência externa de conhecimento — tweet, thread, artigo, vídeo, talk, podcast, trecho de livro — vira nota estruturada em `raw/` e é mixada na hora pra `wiki/`.

**Gatilhos naturais:** "manda isso pro Obsidian", "joga no Obsidian", "salva no Obsidian", "captura isso". O "isso" é a referência externa mais recente da conversa. O verbo explícito é `/capturar-ref`.

**Sugestão proativa:** quando uma referência externa de peso aparece na conversa e eu não pedi pra capturar, ofereça os dois de uma vez — "quer que eu capture isso pro segundo cérebro e já monte um prompt de handoff pra implementar a ideia?". Não capture nem implemente sem aval.

**Fluxo:**

1. Crie `raw/AAAA-MM-DD_<slug>.md` a partir de `templates/captura_referencia.md`, com os 9 campos: fonte/autor/data; formato + tags; resumo; insights-chave; quote bruto; conexão com curso/sistema; ideia de aplicação pro MSCS; ideia de conteúdo adaptado; prompt de handoff. Campo sem matéria-prima = "—".
2. Quote bruto: verbatim. Não reescreva a fonte.
3. Mixe na hora: crie ou atualize a página em `wiki/` na minha voz, com pelo menos um wikilink. Atualize `wiki/index.md` e `wiki/log.md`. Marque a nota de `raw/` como `status: mixado`.
4. **Prompt de handoff:** a melhor ideia de aplicação ou conteúdo vira um prompt pronto pra colar num Claude Code que implementa aquilo — concreto, na minha voz, com o arquivo/caminho alvo quando der. Grave no campo da nota e me ofereça rodar, guardar ou ajustar. É a entrega que tira a ideia do papel.

## Regras de escrita

- Português. Frases curtas. Voz ativa.
- Página boa cabe numa tela. Passou disso, são duas páginas.
- Título específico vence genérico. `precificacao-por-valor` vence `notas`.
- Toda página conecta a pelo menos uma outra.
- Sem floreio. Sem "vale notar que".

---

> Base: ideia de wiki viva de [Andrej Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f). Lógica de mixagem: MSCREATIVE.SYSTEMS™.
