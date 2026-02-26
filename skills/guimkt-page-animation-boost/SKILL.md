---
name: guimkt-page-animation-boost
description: Use when the user requests a "Page Animation Boost" or wants to optimize new/existing web pages or landing pages with a combo of advanced Neo-Brutalist visual optimizations, including GSAP animations, brutalist clip-paths, geometric parallax, CSS neon glows, bottom-up reveals, and specialized mobile micro-interactions.
---

# guimarketing - Page Animation Boost

Esta skill encapsula o pacote premium de otimizações de Motion e UX da Agência do Futuro. Use-a quando o cliente pedir um "Page Animation Boost" ou quando houver a necessidade de dar vida e alto impacto visual a uma interface HTML/React estática, elevando-a para o nível "produto real" e imersivo.

## Componentes do Boost (O Combo de Otimização)

Quando provocado a implementar um boost de animação em uma Landing Page do Agency Studio, avalie e utilize os seguintes elementos arquiteturais:

### 1. Recortes Brutais Animados (`.brutal-clip`)

Nas imagens ancoradas (`Visual Anchors`), ignore os formatos retangulares básicos ou o tradicional `border-radius`. Utilize `.brutal-clip` com cantos agressivamente chanfrados e transições focadas no eixo `:hover` para prender a atenção.

```css
.brutal-clip {
    clip-path: polygon(4% 0, 100% 0, 96% 100%, 0 100%);
    transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}
.group:hover .brutal-clip {
    clip-path: polygon(0 0, 100% 4%, 100% 100%, 4% 96%); /* Inversão brusca e dinâmica */
}
.group:hover .brutal-clip img {
    transform: scale(1.02); /* Suave expansão do conteúdo */
}
```

### 2. Parallax GSAP Cruzado (ScrollTrigger Overlap)

Elementos de altíssimo impacto (ex: Stickers soltos, GIFs de memes corporativos, logos gigantes) devem extrapolar o limite seguro da seção onde residem usando `position: absolute`. Adicione GSAP Parallax neles para passarem a sensação de poster vivo enquanto o usuário dá scroll:

```html
<div class="absolute -top-24 right-20 z-50 transform rotate-6" id="floating-sticker">
    <img src="..." class="border-4 border-black shadow-[7px_5px_0px_0px_#000000]">
</div>
<script>
    if (window.gsap && window.ScrollTrigger && !window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
        gsap.to("#floating-sticker", {
            y: -180,
            rotation: -8,
            ease: "none",
            scrollTrigger: {
                trigger: "#parent-section",
                start: "top bottom",
                end: "bottom top",
                scrub: 1.2
            }
        });
    }
</script>
```

### 3. O Fluxo de Revelação (Bottom-up Clip-Path)

Evite transações 3D "flip" datadas para revelação de cards de conteúdo. Use a máscara de clip-path retraindo de baixo para cima `(100% 0, 0 0)` em cubic-bezier sobre a div frontal para revelar a realidade oculta por baixo.

```css
/* Card frontal deslizando e encolhendo suavemente, varrendo o fundo a partir do topo */
.reveal-front {
    clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%);
    transition: clip-path 0.5s cubic-bezier(0.85, 0, 0.15, 1);
}
.hover-reveal-group:hover .reveal-front {
    clip-path: polygon(0 0, 100% 0, 100% 0, 0 0); 
}
```

### 4. Chamarisco de Descoberta (Neon Glow)

Para sliders, botões primários mudos ou inputs interativos que necessitam de *cue* visível do usuário, acenda um glow pulsante com uma cor forte (ex: Roxo `#864df9` ou Mint `#00E5FF`).

```css
input[type=range]::-webkit-slider-thumb {
    box-shadow: 0 0 15px 5px rgba(134, 77, 249, 0.8); /* Glow halo */
    animation: thumb-pulse 2s infinite;
}
@keyframes thumb-pulse {
    0% { box-shadow: 0 0 10px 2px rgba(134, 77, 249, 0.6); }
    50% { box-shadow: 0 0 20px 8px rgba(134, 77, 249, 1); }
    100% { box-shadow: 0 0 10px 2px rgba(134, 77, 249, 0.6); }
}
```

### 5. Arquitetura Mobile (Anti-Scrollback)

Uma UI fluída em mobile nunca faz o usuário rolar páginas para cima puramente para trocar a aba de algo que ele acabou de ler.
**Regra UX Mobile:** Se houver displays controlados por abas (tabs) muito compridos, crie um **Grid de Navegação Secundário** exclusivo para móbile (`lg:hidden`) injetado **depois** do conteúdo lido.
Esse grid replicará os botões originais das guias, de modo que ao clicar eles não apenas trocam a aba ativa no JS (`showTab('nova')`), mas engatilham `scrollToSection('tab-container')` reacomodando delicadamente a viewport no início do novo conteúdo renderizado.

---

## Dependências & Ecossistema Nativo

Sempre mantenha a filosofia do Neo-Brutalismo nativo (*Agency Studio* design pattern):

- Sombras sharp sem blur (`shadow-[7px_5px_0px_0px_#000000]`)
- Cores saturadas + Bordas grossas.
- Acessibilidade máxima (Sempre honre media queries de preferência contra redução de movimento).

Sempre que aplicar ou debugar conceitos de interatividade atrelados ao boost supracitado, utilize as skills base do ecossistema que se encontram isoladas em nossa pasta de `references/`:

- Leia `references/motion-landing-page.md` para diretrizes universais de Framer-Motion/GSAP scrolls.
- Leia `references/interaction-design.md` para princípios teóricos e melhores práticas sobre tempos de curva (bezier timing) e retornos de transação.
- Leia `references/3d-web-experience.md` caso no "boost" seja requisitado injetar canvas e webGL (Three.js/React Three Fiber).

*A execução desse "Boost" é o golpe de misericórdia entre páginas medianas e produtos IA-First impactantes da gui.marketing.*
