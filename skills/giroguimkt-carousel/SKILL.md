---
name: giroguimkt-carousel
description: >
  Cria carrosséis completos para a editoria #giroguimkt do Instagram (@guilherme.marketing).
  Gera todos os textos dos cards, prompts de imagem detalhados para cada slide, e o texto-legenda
  do post — tudo seguindo a identidade visual e o tom editorial da marca gui.marketing.
  Use esta skill sempre que o usuário mencionar #giroguimkt, "giro da semana", "carrossel semanal
  de marketing", "giro de notícias de marketing", ou pedir para criar conteúdo recorrente da
  editoria semanal de curadoria de marketing. Também use quando o usuário quiser montar um
  carrossel no estilo newsletter visual com curadoria de notícias do mercado.
---

# #giroguimkt — Skill de Criação de Carrosséis

Esta skill produz edições completas do **#giroguimkt**, a editoria semanal de curadoria de marketing
do perfil @guilherme.marketing no Instagram. O objetivo é transformar as notícias e cases mais
relevantes da semana em um carrossel visual, informativo e com opinião — no tom provocador da marca.

## Contexto Editorial

O #giroguimkt é uma "newsletter visual" semanal que cobre o que aconteceu de mais relevante no
universo de marketing, comunicação, negócios e tecnologia. Não é um resumo neutro: é uma curadoria
com opinião, sarcasmo inteligente e análise estratégica. O autor (Gui) se posiciona como
"O Estrategista Provocador" — alguém que desafia os clichês do marketing com dados e raciocínio,
não com fórmulas prontas.

A persona editorial combina:
- **Autoridade técnica** (sabe do que fala, cita dados, analisa a estratégia por trás)
- **Sarcasmo afiado** (humor ácido mas não cruel, ironia inteligente)
- **Provocação construtiva** (questiona práticas do mercado, não por ser contrário, mas por ter padrão alto)
- **Linguagem acessível** (sem jargão desnecessário, tom de conversa com amigo esperto)

Tagline da marca: **"Os gurus mentem, os dados não."**

## Fluxo de Produção

### Etapa 1: Curadoria de Notícias

O usuário pode fornecer o input de duas formas:

**Forma A — Briefing direto:** O usuário lista os temas/notícias que quer cobrir. Neste caso, use
web search para aprofundar cada um, encontrar detalhes, dados e fontes.

**Forma B — Descoberta:** O usuário pede para "montar o giro da semana". Neste caso, pesquise
ativamente as notícias mais relevantes da semana em marketing, publicidade, tecnologia e negócios
(Brasil e mundo). Priorize:
- Cases de marca com execução criativa notável (boa ou má)
- Polêmicas e crises de comunicação
- Lançamentos, campanhas ou estratégias inovadoras
- Movimentações culturais que impactam marcas (memes, trends, protestos digitais)

**Critérios de seleção:**
- Relevância para profissionais de marketing (não notícias genéricas de negócios)
- Potencial de análise estratégica (tem algo pra aprender, não só relatar)
- Variedade de temas (não repetir o mesmo tipo de case)
- Recência (aconteceu na semana corrente ou no máximo 7 dias atrás)

**Output da Etapa 1:** Lista de 2 notícias principais + 3-4 itens rápidos para o roundup. Apresente
ao usuário para validação ANTES de prosseguir. Inclua fontes.

### Etapa 2: Estruturação do Carrossel

O carrossel segue uma estrutura fixa de **7-8 slides** (formato 3:4, 1080x1350px):

Leia `references/carousel-structure.md` para a especificação detalhada de cada slide.

### Etapa 3: Redação dos Cards

Escreva os textos de cada card seguindo as regras em `references/editorial-voice.md`.

Entregue os textos em formato estruturado:

```
## SLIDE 1 — CAPA
Headline: [texto]
Subtítulo: [texto]
Tag: #giroguimkt [número da edição]

## SLIDE 2 — NOTÍCIA 1: CONTEXTO
Título do card: [texto]
Lead (bold): [1-2 frases de impacto]
Body: [desenvolvimento em 2-3 frases]

[... e assim por diante para cada slide]
```

### Etapa 4: Prompts de Imagem

Para cada slide que requer imagem gerada, crie um prompt detalhado seguindo as diretrizes em
`references/image-prompts.md`. Os prompts devem ser específicos o suficiente para manter
consistência visual entre edições.

**Importante:** Atualmente a geração de imagem é feita externamente (Vertex AI / Google Image Pro).
Os prompts devem ser entregues prontos para uso direto na API, em inglês, com especificações
técnicas de composição, estilo e proporção.

### Etapa 5: Texto-Legenda

Escreva o texto-legenda do post seguindo a estrutura em `references/caption-structure.md`.

### Etapa 6: Entrega Final

Compile tudo em um único documento markdown organizado com:
1. Todos os textos dos cards (com indicação de formatting: bold, regular, highlight)
2. Todos os prompts de imagem
3. O texto-legenda completo
4. Lista de hashtags sugeridas

Salve como arquivo e apresente ao usuário.

## Regras Inegociáveis

1. **Nunca invente notícias.** Toda informação factual precisa ser verificável. Se não tem certeza, pesquise.
2. **Sempre cite fontes.** O usuário precisa poder verificar.
3. **Mantenha o tom.** É sarcástico, não maldoso. Provocador, não arrogante. Opinionado, não panfletário.
4. **Respeite a estrutura.** O carrossel tem um ritmo: abertura impactante → desenvolvimento com insight → roundup rápido → fechamento com engajamento. Não quebre esse ritmo.
5. **Nunca use clichês de marketing digital.** Nada de "engajamento orgânico", "conteúdo de valor", "estratégia matadora". A marca existe pra desafiar esses clichês, não pra replicá-los.
6. **Pergunte antes de produzir.** Valide a curadoria com o usuário antes de redigir os cards.
