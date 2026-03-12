# Identidade Visual — gui.marketing

## Estética geral

"Tech streamer meets marketing authority." A estética do Guilherme vive na interseção
entre cultura gamer/tech e autoridade estratégica de negócios. Não é o azul corporativo
do LinkedIn. Não é o pastel do coach. Não é o neon de balada. É o dark mode de quem
trabalha de madrugada otimizando campanha.

---

## Paleta de cores

| Cor | Hex | Uso |
|-----|-----|-----|
| Background principal | `#0D0D12` | Fundo de todos os posts |
| Background grid/sutil | `#1E1E28` | Linhas de grid, elementos de dashboard |
| Roxo elétrico | `#8A2BE2` | Acentos, barras, linhas divisórias |
| Amarelo vibrante | `#FFEA00` | Headlines de destaque, palavras-chave |
| Hot pink | `#FF1464` | CTAs, alertas, punchlines |
| Branco | `#FFFFFF` | Texto principal |
| Cinza médio | `#78788C` | Texto secundário, legendas, @handle |
| Cinza escuro | `#1E1E28` | Elementos de fundo, sombras |

**Hierarquia cromática:**
- Amarelo = a palavra/frase mais importante do slide
- Hot pink = ação, urgência, provocação
- Roxo = estrutura, elegância, separadores
- Branco = corpo do texto
- Cinza = informação secundária, handle, hashtags

**Regra:** nunca use mais de 2 cores de acento no mesmo slide. Amarelo + pink = OK.
Amarelo + pink + roxo todos como destaque = poluição visual.

---

## Tipografia

### Headlines / títulos
- **Estilo:** Bold, condensada, caixa alta
- **Fontes recomendadas:** Big Shoulders Bold, Outfit Bold, Work Sans Bold
- **Uso:** frases de impacto, hooks, punchlines

### Corpo / texto secundário
- **Estilo:** Regular, sem serifa, caixa normal (sentence case)
- **Fontes recomendadas:** Bricolage Grotesque, Instrument Sans, Work Sans Regular
- **Uso:** explicações, contexto, corpo do slide

### Elementos técnicos / dados
- **Estilo:** Monospaced, regular
- **Fontes recomendadas:** Geist Mono, JetBrains Mono, IBM Plex Mono
- **Uso:** @handle, métricas, código, dados, hashtags

### Acentos / destaque especial
- **Estilo:** Display, caixa alta
- **Fontes recomendadas:** Big Shoulders Bold (tamanho maior), Boldonse
- **Uso:** a palavra mais importante do slide quando precisa de impacto extra

---

## Elementos visuais recorrentes

### Grid de dashboard
Linhas sutis de grade (`#1E1E28`) no fundo dos slides que remetem a dashboards de
analytics. Não precisa estar em todos os posts, mas quando presente, cria coesão visual.
Espaçamento recomendado: 40px entre linhas.

### Barras de gráfico abstratas
Barras verticais coloridas (roxo, pink, amarelo) em posições variadas. Não representam
dados reais — são elementos decorativos que remetem ao universo de métricas e performance.
Uso: metade superior do slide como ambientação.

### Arco / semicírculo de progresso
Elemento circular aberto (3/4 de circunferência) em amarelo ou roxo. Remete a gráficos
de donut / progress indicators. Funciona bem sobreposto às barras.

### Barra de acento inferior
Uma linha fina (4-6px) na cor roxa na base do slide. Funciona como assinatura visual
silenciosa que conecta todos os posts da marca.

### Ícone de proibido
Círculo com linha diagonal cruzada em hot pink. Usado especificamente em slides de
reveal/proibição (meta-trolls, alertas).

---

## Layout padrão (post estático 1080x1080)

```
┌──────────────────────────────────┐
│ @guilherme.marketing (topo-esq)  │  ← Geist Mono, cinza, 18px
│                                  │
│   [elementos visuais abstratos]  │  ← barras, arcos, grid
│                                  │
│                                  │
│   HEADLINE PRINCIPAL             │  ← Big Shoulders Bold, branco, 72-96px
│   EM DUAS LINHAS                 │
│   PALAVRA DESTAQUE               │  ← mesma fonte, amarelo
│                                  │
│                                  │
│   texto secundário se houver     │  ← Bricolage/Instrument, cinza, 22px
│                                  │
│ ▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬│  ← barra roxa, 4px
└──────────────────────────────────┘
```

### Margens
- Margens laterais: 40px mínimo
- Margem superior: 40px (espaço pro handle)
- Margem inferior: 40px (espaço pra barra de acento)
- Espaçamento entre headline e texto secundário: 30-40px

### Alinhamento
- Headlines: centralizados horizontalmente
- Handle: alinhado à esquerda no topo
- Texto secundário: centralizado
- Elementos visuais: distribuídos na metade superior, podem sangrar lateralmente

---

## Layout padrão (carrossel — slides internos)

Mesma estrutura do estático, com estas diferenças:
- Slides internos podem ter mais texto (até 6-8 linhas)
- Usar linha divisória roxa entre seções
- Manter o handle em todos os slides (consistência)
- Manter a barra de acento inferior em todos os slides
- Slide final sempre tem o CTA: "SIGA @GUILHERME.MARKETING" em hot pink

---

## O que a identidade visual NÃO é

- NÃO é gradiente azul-roxo de startup (é sólido, escuro, contrastado)
- NÃO é flat design com ícones outline (é tipográfico e gráfico abstrato)
- NÃO é branco com detalhe colorido (é dark-first, sempre)
- NÃO é minimalista sem personalidade (é denso mas organizado)
- NÃO usa fotos do Guilherme em posts de conteúdo (fotos são pra stories/reels)
- NÃO usa stock photos (nunca, em hipótese alguma)
- NÃO usa ilustrações cartoon (a estética é séria, o conteúdo é engraçado)

---

## Geração de imagens com Python/Pillow

Ao gerar imagens programaticamente, usar estas referências:

```python
# Cores
BG_DARK = (13, 13, 18)       # #0D0D12
PURPLE = (138, 43, 226)      # #8A2BE2
YELLOW = (255, 234, 0)       # #FFEA00
HOT_PINK = (255, 20, 100)    # #FF1464
WHITE = (255, 255, 255)
GRAY = (120, 120, 140)       # #78788C
DARK_GRAY = (30, 30, 40)     # #1E1E28

# Canvas
W, H = 1080, 1080

# Fontes (de canvas-fonts/)
FONT_HEADLINE = "BigShoulders-Bold.ttf"      # Headlines
FONT_BODY = "BricolageGrotesque-Regular.ttf"  # Corpo
FONT_BODY_BOLD = "BricolageGrotesque-Bold.ttf"
FONT_MONO = "GeistMono-Regular.ttf"          # Handle, técnicos
FONT_MONO_BOLD = "GeistMono-Bold.ttf"
```

**Nota:** as fontes estão em `/mnt/skills/examples/canvas-design/canvas-fonts/`.
Sempre verificar disponibilidade antes de usar.
