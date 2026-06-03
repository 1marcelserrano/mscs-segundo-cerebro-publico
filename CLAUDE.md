# Protocolo da Memória Viva

Este arquivo instrui o Claude Code a manter a memória deste repositório. A base é a ideia de wiki viva do Andrej Karpathy. O método é a travessia da MSCREATIVE.SYSTEMS™.

Karpathy: o repo é a IDE, o LLM é o programador, a wiki é o código-fonte. A travessia é o que mantém a wiki viva.

## As camadas

- **`raw/`** — captura. Fontes como chegaram: conversas, transcrições, recortes, notas, histórico de IA. Material cru, sem ordem. Nunca se apaga nada daqui.
- **`wiki/`** — memória. Páginas curtas, conectadas, escritas na voz do dono. É o que se lê, consulta e usa pra produzir.
- **`voz.md`** — o perfil de voz. A memória escreve nesse registro e bebe dele.

## Operações

### Atravessar (`raw/` → `wiki/`)

Pra cada fonte em `raw/` ainda não processada:

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
4. Conecte com wikilinks (`[[nome-da-pagina]]`). Página sem conexão é sinal de travessia incompleta.
5. Se a fonte revelou algo sobre como o dono pensa ou escreve, registre em `voz.md`.
6. Atualize `wiki/index.md` (cada página, uma linha) e `wiki/log.md` (data, o que entrou, o que mudou).

Regra: a memória destila, não copia. Cada página diz o essencial em menos palavras que o original.

### Lembrar (consulta)

Responda a partir da `wiki/` primeiro, citando as páginas. Mostre as conexões. Se a wiki não cobre, diga, e aponte o que em `raw/` ainda não foi atravessado e poderia cobrir. Não invente o que a memória não tem.

### Produzir (artefato)

Puxe da `wiki/` o que toca o tema. Use o que é do dono, não conhecimento genérico. Escreva na voz dele (`voz.md`), no formato do destino. Marque onde a memória foi rasa.

### Revisar (saúde)

Quando pedirem, varra a `wiki/` e devolva: contradições, páginas órfãs, conceitos sem página própria, páginas inchadas, páginas duplicadas. Proponha os ajustes. Só execute depois de aprovado.

## Regras de escrita

- Português. Frases curtas. Voz ativa.
- Página boa cabe numa tela. Passou disso, são duas páginas.
- Título específico vence genérico. `precificacao-por-valor` vence `notas`.
- Toda página conecta a pelo menos uma outra.
- Sem floreio. Sem "vale notar que".

---

> Base: ideia de wiki viva de [Andrej Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f). Método da travessia: MSCREATIVE.SYSTEMS™.
