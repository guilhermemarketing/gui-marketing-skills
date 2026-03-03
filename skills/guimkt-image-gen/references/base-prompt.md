# Prompt-Base — Estilo Visual gui.marketing

Este é o prompt-base que DEVE ser incluído em toda geração de imagem. Ele define a
identidade visual da marca. O conteúdo específico de cada imagem (sujeito, cena, metáfora)
é adicionado DEPOIS deste bloco.

## Prompt-Base (copiar integralmente)

```
Mixed-media editorial image with punk zine energy. Combine ONE cutout photograph (person, object, or scene) with raw neo-brutalist graphic accents. The photographic element is the dominant subject — graphic elements are secondary decoration only. The cutout should feel hand-ripped, not digitally clean — rough jagged edges on the photo cutout, as if torn from a magazine page.

COMPOSITION RULES: Single focal point. ONE subject, ONE idea, ONE visual metaphor. Asymmetric placement with generous empty space (at least 30-40% of the canvas must be clean for text to be added in post-production). Do NOT fill the canvas — simplicity is mandatory. No collages, no multiple panels, no mood boards, no UI mockups, no dashboards, no icon grids, no scattered floating objects.

STYLE: Thick solid black outlines (4-6px strokes) and hard solid black offset drop shadows (X+Y offset, zero blur, 100% opacity). Subtle raw textures allowed: paper grain, xerox noise, halftone dot patterns on small areas, ink splatter marks — used sparingly as background texture or accent, never overwhelming the composition. Graphic accents should feel hand-made and analog — rough geometric shapes, bold arrows, crude circles, tape strips, staple marks — like a punk zine or protest poster, not polished vector art.

COLORS: Flat solid fills — Creamy Off-white (#f7f3ed), pure Black (#000000), Electric Purple (#864df9), Pastel Yellow (#F7E397), Mint Green (#b0e4da), Light Lilac (#dcd3ef), Soft Pink (#efcde5). Maximum 2 accent colors per image. Backgrounds must ALWAYS be a single flat solid color or off-white with subtle paper grain texture. Gradients (linear 135°: #f7e396 → #efcde5 → #864df9) permitted ONLY on small accent details like thin dividers or narrow stripes — never on backgrounds or large surfaces. Gradients must occupy less than 5% of the total image area.

ABSOLUTELY FORBIDDEN: Any text, letters, numbers, words, labels, hex codes, watermarks, or typographic elements of any kind. No 3D rendering, no glass/glossy effects, no realistic lighting. No childish or cartoonish style. No corporate clip art. No clean polished vector illustration. No cute or friendly aesthetic.

MOOD: Raw, provocative, intellectually aggressive — like a Bloomberg Businessweek confrontational cover meets a punk zine layout. Professional enough for B2B marketing, rebellious enough to stop the scroll. Think editorial provocation, not decoration.
```

## Paleta de Cores

| Cor | Hex | Uso |
|-----|-----|-----|
| Creamy Off-white | `#f7f3ed` | Fundos, espaços limpos |
| Pure Black | `#000000` | Outlines, sombras, contrastes |
| Electric Purple | `#864df9` | Cor primária da marca, destaques fortes |
| Pastel Yellow | `#F7E397` | Acentos, destaques secundários |
| Mint Green | `#b0e4da` | Acentos pontuais |
| Light Lilac | `#dcd3ef` | Fundos alternativos, suavização |
| Soft Pink | `#efcde5` | Acentos pontuais |

### Regra de uso por imagem

- Fundo: 1 cor sólida (preferencialmente off-white, lilac ou black)
- Acentos: máximo 2 cores da paleta por imagem
- Gradiente: APENAS em detalhes mínimos (dividers, stripes) — máx 5% da área

## Gradiente Oficial

Quando usado (apenas em detalhes mínimos):

```
Linear 135°: #f7e396 → #efcde5 → #864df9
```

Variação estendida:

```
Linear 135°: #f7e396 → #efcce5 → #b0e4db → #864df9
```

## Termos Proibidos nos Prompts

Nunca inclua estes termos — eles desviam o resultado para estéticas indesejadas:

- `3D`, `claymorphism`, `claymorfismo`
- `unreal engine`, `octane render`, `blender`
- `cartoon`, `cute`, `kawaii`, `chibi`, `friendly`
- `clip art`, `stock photo`, `stock illustration`
- `UI design`, `mockup`, `dashboard`, `wireframe`
- `mood board`, `collage`, `grid layout`
- `glass`, `glossy`, `glassy`, `glassmorphism`
- `children`, `kids`, `playful` (no contexto estético)

## Termos Recomendados nos Prompts

Estes termos puxam o resultado na direção certa:

- `editorial`, `magazine cover`, `zine`
- `punk`, `raw`, `analog`, `hand-made`
- `cutout photography`, `torn paper`, `ripped edges`
- `neo-brutalist`, `thick black outlines`, `offset drop shadow`
- `paper grain`, `xerox texture`, `halftone`
- `provocative`, `confrontational`, `aggressive`
- `tape strips`, `staple marks`, `ink splatter`

## Montagem Final do Prompt

A estrutura completa de cada prompt deve ser:

```
[PROMPT-BASE inteiro, copiado acima]

Subject: [descrição do sujeito/cena/metáfora específica]
Composition: [posição do sujeito, onde fica o espaço livre para texto]
Aspect ratio: 3:4, 1080x1350px, high resolution.
```

Mantenha o prompt total abaixo de ~300 palavras para melhor performance.
