# Compilador da Wiki Viva

Este arquivo instrui o Claude Code a manter a wiki deste repositório. Adaptado do padrão de wiki viva do Andrej Karpathy.

A imagem que organiza tudo: **o repo é a IDE. O LLM é o programador. A wiki é o código-fonte.**

## As três camadas

- **`raw/`** — fontes como chegaram. PDFs, artigos, transcrições, notas soltas, recortes. Entra material cru, sem organização. Você nunca apaga nada daqui.
- **`wiki/`** — conhecimento compilado. Páginas curtas, em português, linkadas entre si. É o que você lê e consulta.
- **`acervo/`** — histórico de IA destilado (ChatGPT, Claude). Tratado como fonte de consulta, não reescrito.

## Operações

### Ingerir (`raw/` → `wiki/`)

Quando eu pedir pra processar fontes novas, pra cada arquivo em `raw/`:

1. Leia a fonte inteira.
2. Escreva uma **página de resumo** em `wiki/`, com frontmatter:
   ```
   ---
   titulo: <título claro e específico>
   fonte: <arquivo de origem em raw/>
   data: <AAAA-MM-DD>
   tags: [<tema>, <conceito>, <projeto>]
   ---
   ```
3. Identifique os **conceitos e tópicos** que a fonte toca. Pra cada um, crie ou atualize uma página de conceito em `wiki/`. Concentre o que várias fontes dizem sobre o mesmo conceito numa página só.
4. Adicione **wikilinks** (`[[nome-da-pagina]]`) entre páginas relacionadas. Uma página sem nenhum link é sinal de que faltou conectar.
5. Atualize `wiki/index.md` com a página nova e uma linha de descrição.
6. Registre o que foi feito em `wiki/log.md` (data + fontes processadas + páginas criadas/atualizadas).

Regra: **não reescreva a fonte bruta.** A wiki é destilação, não cópia. Cada página da wiki diz o essencial em menos palavras que o original.

### Consultar (responder a partir da wiki)

Quando eu fizer uma pergunta, responda **a partir da wiki primeiro**. Se a wiki não cobre, diga isso e aponte qual fonte em `raw/` ou `acervo/` poderia cobrir. Cite as páginas que usou.

### Revisar (saúde da wiki)

Quando eu pedir uma checagem de saúde, varra `wiki/` e me devolva:
- **Contradições** — páginas que afirmam coisas opostas.
- **Páginas órfãs** — sem nenhum wikilink de entrada ou saída.
- **Conceitos faltando** — temas citados em várias páginas que ainda não têm página própria.
- **Páginas inchadas** — longas demais, que pedem divisão.
- **Páginas duplicadas** — dois títulos pro mesmo conceito, que pedem fusão.

Proponha as correções. Só execute depois da minha aprovação.

## Regras de escrita

- Português. Frases curtas. Voz ativa.
- Página de wiki boa cabe numa tela. Se passou disso, provavelmente são duas páginas.
- Título específico vence título genérico. `precificacao-por-valor` vence `notas`.
- Toda página termina linkando pra pelo menos uma outra. Conhecimento isolado não é wiki.
- Sem floreio. Sem "vale notar que". Sem "em suma".

## index.md

Mantenha `wiki/index.md` como porta de entrada: cada página listada com uma linha. É a primeira coisa que eu (ou outro LLM) leio pra entender o que existe aqui.

## log.md

Mantenha `wiki/log.md` como diário da wiki: cada compilação, cada revisão, com data. É o histórico de como o cérebro cresceu.

---

> Padrão de wiki viva: [Andrej Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f). Adaptação MSCREATIVE.SYSTEMS™.
