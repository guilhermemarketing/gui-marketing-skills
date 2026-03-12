# Guia de Prompts de Imagem

Os prompts de imagem são escritos em inglês para uso direto na API do Vertex AI / Google Image Pro.
Cada slide que precisa de imagem gerada recebe um prompt específico.

## Slides que Precisam de Imagem

| Slide | Tipo de Imagem | Nível de Importância |
|-------|---------------|---------------------|
| 1 (Capa) | Composição split com 2 cenas | CRÍTICO |
| 2 (Contexto 1) | Background temático | ALTO |
| 3 (Insight 1) | Elemento visual temático | MÉDIO |
| 4 (Contexto 2) | Imagem dramática/impactante | ALTO |
| 5 (Análise 2) | Frame/screenshot contextual | MÉDIO (pode ser screenshot real) |
| 6 (Roundup) | Mini-grid de referências | BAIXO (geralmente screenshots reais) |
| 7 (Resumo) | Avatar/foto do Gui | FIXO (usa foto real) |
| 8 (Bio) | Template fixo | NÃO GERAR |

## Estrutura do Prompt

Cada prompt de imagem deve seguir esta estrutura:

```
[SUBJECT]: Descrição clara do que está na cena
[STYLE]: Estilo visual (fotorrealista, ilustração, editorial, etc.)
[COMPOSITION]: Como os elementos estão dispostos (split, centered, rule of thirds)
[LIGHTING]: Iluminação (studio, natural, dramatic, warm)
[MOOD]: Atmosfera geral (energetic, serious, playful, dramatic)
[TECHNICAL]: Aspect ratio, qualidade, restrições
[NEGATIVE]: O que NÃO deve aparecer
```

## Prompt Template (copiar e adaptar)

```
[Subject description]. [Style: photorealistic editorial photography / digital illustration / 
mixed media]. Composed as [composition details], with [lighting] lighting. The mood is 
[mood description]. Shot in 3:4 aspect ratio, high resolution, editorial quality. 
No text, no watermarks, no logos.
```

## Diretrizes por Slide

### Slide 1 — Capa (Split Composition)
O mais complexo. Precisa comunicar os 2 temas visualmente.

**Padrão do prompt:**
```
A split-screen editorial image divided by a torn paper effect. Left side: [cena do tema 1].
Right side: [cena do tema 2]. The torn paper edge runs diagonally from top-left to bottom-right.
Both sides have vibrant, contrasting color palettes. Photorealistic editorial style, 3:4 aspect
ratio, high resolution. The bottom third should be darker (will have text overlay). 
No text, no watermarks.
```

**Importante:** As duas cenas devem ser visualmente contrastantes mas não desconexas.

### Slide 2 — Background Temático
Imagem que contextualiza a notícia. Pode ser fotorrealística ou estilizada.

**Padrão:**
```
[Cena relevante para a notícia]. Editorial photography style, slightly desaturated with 
[dominant color] tones. The image should have a clear focal point in the center-top area. 
Bottom-right area should be less busy (text card will overlay there). 3:4 aspect ratio, 
high resolution. No text, no logos.
```

### Slide 3 — Elemento Visual para Insight
Menos literal, mais conceitual. Pode ser uma ilustração ou elemento gráfico.

**Padrão:**
```
[Elemento visual metafórico/temático] on a soft lavender/purple gradient background (#DDD6FE 
to #7C3AED). The element should be centered in the top half of the frame. Clean, modern 
illustration style with subtle depth. 3:4 aspect ratio. No text.
```

### Slide 4 — Imagem Dramática
A imagem mais "cinematográfica" do carrossel. Gera impacto emocional.

**Padrão:**
```
[Cena dramática/impactante relacionada à notícia]. Cinematic editorial photography with warm 
golden-hour lighting. The subject should be prominent in the upper two-thirds. The bottom third 
should transition to darker tones (text overlay area). Rich, saturated colors. 3:4 aspect ratio, 
high resolution. No text, no watermarks.
```

### Slide 5 — Frame/Screenshot
Geralmente usa frame real de vídeo/campanha. Se precisar gerar:

**Padrão:**
```
[Cena que simula um frame de vídeo/comercial]. The image should look like a paused video frame 
with natural motion blur. Muted, slightly desaturated colors. The bottom half should be 
significantly darker (will be covered by black overlay with text). 3:4 aspect ratio.
```

## Regras de Consistência Visual

1. **Nunca gere texto dentro das imagens.** Todo texto é adicionado depois no Canva.
2. **Mantenha o espaço para overlay.** Sempre indique no prompt qual área terá texto sobreposto.
3. **Cores consistentes.** Priorize a paleta da marca (roxos, pretos, dourados) como tons dominantes ou complementares.
4. **Sem rostos de pessoas reais identificáveis.** Quando a notícia envolve pessoas específicas, use composições que não dependam de retratos (ex: mãos segurando produto, cena de costas, silhueta).
5. **Estilo editorial, não stock photo.** As imagens devem parecer de revista/jornal, não de banco de imagens genérico.

## Otimização para Vertex AI / Google Image Pro

- Prompts em inglês sempre (melhor performance)
- Ser explícito sobre aspect ratio (3:4)
- Incluir "no text" e "no watermarks" sempre
- Usar termos técnicos de fotografia (aperture, depth of field, golden hour) para mais controle
- Especificar negative prompts quando necessário (no cartoons, no anime, etc.)
- Máximo ~200 palavras por prompt para melhores resultados
