---
name: guimkt-image-gen
description: >
  Gera prompts de imagem editorial e infográficos para o perfil @guilherme.marketing no
  Instagram, seguindo a identidade visual neo-brutalist punk da marca gui.marketing.
  Produz prompts prontos para API de geração de imagem (Vertex AI, Imagen, Midjourney,
  Flux, DALL-E). Suporta dois modos: ilustrações editoriais (sem texto) e infográficos
  (com dados/texto no estilo punk zine). Use esta skill sempre que o usuário pedir para
  criar imagens, ilustrações, infográficos, prompts de imagem, ou visuais para posts do
  Instagram — especialmente para o #giroguimkt e outros conteúdos editoriais. Também use
  quando o usuário mencionar "gerar imagem", "prompt de imagem", "visual do card",
  "ilustração do post", "imagem da notícia", "infográfico", "comparativo visual",
  "diagrama", ou qualquer variação de criação de assets visuais para redes sociais.
---

# guimkt-image-gen — Geração de Imagens e Infográficos Editoriais

Skill para criar prompts de imagens e infográficos no estilo editorial neo-brutalist punk
da marca gui.marketing. Suporta dois modos:

- **Ilustrações editoriais** — imagem sem texto, metáfora visual pura (texto em pós-edição)
- **Infográficos** — dados, comparativos, diagramas, fluxos com texto integrado no estilo punk zine

## Quando Usar

- Criação de imagens para cards do #giroguimkt
- Visuais para qualquer post do Instagram @guilherme.marketing
- Ilustrações editoriais para conteúdo de marketing
- **Infográficos** — comparativos, fluxos, Venn diagrams, dados de performance
- Qualquer asset visual que precise seguir a identidade da marca

## Fluxo de Trabalho

### 1. Identificar o Modo

Antes de tudo, determine se o pedido é **ilustração** ou **infográfico**:

| Modo | Quando usar | Base prompt |
|------|------------|-------------|
| **Ilustração** | Metáforas visuais, cenas editoriais, imagens sem texto | `references/base-prompt.md` |
| **Infográfico** | Dados, comparativos, fluxos, diagramas, Venn diagrams | `references/infographic-base-prompt.md` |

### 2. Entender o Conceito

Antes de escrever o prompt, defina:

- **Qual é a notícia/conceito?** (ex: "Google lança IA que substitui gestores de tráfego")
- **Qual é a metáfora visual?** (ex: "robô sentado na cadeira de um profissional")
- **Qual emoção deve provocar?** (ex: tensão, ironia, impacto, humor ácido)

Se o usuário não especificar a metáfora, proponha 2-3 opções antes de gerar.

### 3. Montar o Prompt

Leia o base prompt correspondente ao modo escolhido (Passo 1).

**Ilustrações** seguem esta estrutura:

```
[BASE-PROMPT] + [SUBJECT] + [COMPOSITION] + [MOOD MODIFIER]
```

**Infográficos** seguem esta estrutura:

```
[INFOGRAPHIC-BASE-PROMPT] + [LAYOUT] + [DATA/CONTENT] + [ACCENT DETAILS]
```

- **BASE-PROMPT / INFOGRAPHIC-BASE-PROMPT**: Estilo visual fixo. Sempre incluir integralmente.
- **SUBJECT / LAYOUT**: Cena ou estrutura do infográfico (split-screen, flow vertical, Venn, etc.).
- **COMPOSITION / DATA**: Posicionamento e dados/textos do infográfico.
- **MOOD MODIFIER / ACCENT DETAILS**: Ajustes de tom e detalhes decorativos punk.

### 4. Regras Inegociáveis

**Ambos os modos:**

1. **UM conceito por imagem.** Uma metáfora, um sujeito, um ponto focal. Não é mood board.
2. **Sem estética infantil.** Nada de clip art, cartoon fofo, ou ilustração de livro infantil.
3. **Prompts em inglês.** Sempre. Melhor performance em qualquer modelo.
4. **Aspect ratio 3:4** (1080x1350px) salvo indicação contrária do usuário.

**Apenas ilustrações:**
5. **ZERO texto na imagem.** Nenhuma letra, número, hex code, label, watermark.
6. **Espaço limpo obrigatório.** 30-40% para overlay de texto em pós-edição.
7. **Foto é protagonista.** Elemento fotográfico domina, grafismos são decoração secundária.

**Apenas infográficos:**
8. **Texto é parte da composição.** Dados, labels e títulos em português são esperados.
9. **Estética punk zine no texto.** Texto deve parecer hand-drawn, tipo pôster de protesto — nunca corporativo limpo.
10. **Decoração analog obrigatória.** Tape strips, ink splatter, staple marks, halftone dots, torn-paper dividers.

### 5. Entrega

Entregue cada prompt como bloco de código markdown, pronto para copiar e colar na API.
Se gerando múltiplas imagens (ex: carrossel), numere cada prompt com o slide correspondente.

## Referências

| Arquivo | Conteúdo | Quando Ler |
|---------|----------|------------|
| `references/base-prompt.md` | Prompt-base para ilustrações editoriais | SEMPRE antes de gerar ilustrações |
| `references/infographic-base-prompt.md` | Prompt-base para infográficos punk zine | SEMPRE antes de gerar infográficos |
| `references/prompt-examples.md` | Exemplos de prompts por tipo de notícia | Quando precisar de referência para metáforas visuais |
