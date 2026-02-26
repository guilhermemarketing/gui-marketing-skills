---
name: motion-landing-page
description: Componentes React animados com Motion (Framer Motion) para Landing Pages premium com scroll-triggered animations e micro-interações.
---

# Motion Landing Page

Skill para criação de **Landing Pages dinâmicas** usando a biblioteca [Motion](https://motion.dev) (Framer Motion). Adiciona animações de scroll, micro-interações e transições suaves.

## Quando Usar

- Fase 8c do workflow `/start` (Landing Page Premium opcional)
- Clientes que precisam de presença digital premium
- Páginas de lançamento, campanhas, eventos

## Prerequisites

Template já inclui Motion. Se criar novo projeto:

```bash
npm create vite@latest landing -- --template react-ts
cd landing && npm install motion
```

---

## Componentes Disponíveis

Copiar de `components/` para seu projeto:

| Componente | Descrição | Trigger |
|-----------|-----------|---------|
| `FadeInSection` | Fade + slide up | Scroll (viewport) |
| `ParallaxHero` | Efeito parallax no background | Scroll position |
| `AnimatedCTA` | Botão com pulse/glow | Contínuo |
| `StaggerCards` | Cards com entrada escalonada | Scroll (viewport) |
| `ScrollProgress` | Barra de progresso de leitura | Scroll position |
| `CounterNumber` | Contagem animada de números | Scroll (viewport) |

---

## Padrões de Animação

### Fade In ao entrar no viewport

```tsx
import { motion } from "motion/react";

<motion.div
  initial={{ opacity: 0, y: 30 }}
  whileInView={{ opacity: 1, y: 0 }}
  viewport={{ once: true, margin: "-100px" }}
  transition={{ duration: 0.6, ease: "easeOut" }}
>
  {children}
</motion.div>
```

### Stagger (entrada escalonada)

```tsx
const container = {
  hidden: { opacity: 0 },
  show: {
    opacity: 1,
    transition: { staggerChildren: 0.1 }
  }
};

const item = {
  hidden: { opacity: 0, y: 20 },
  show: { opacity: 1, y: 0 }
};

<motion.ul variants={container} initial="hidden" whileInView="show">
  {items.map(i => <motion.li key={i} variants={item}>{i}</motion.li>)}
</motion.ul>
```

### Parallax no Scroll

```tsx
import { useScroll, useTransform, motion } from "motion/react";

const { scrollYProgress } = useScroll();
const y = useTransform(scrollYProgress, [0, 1], [0, -100]);

<motion.div style={{ y }}>
  <img src="hero-bg.jpg" />
</motion.div>
```

### CTA com Hover Spring

```tsx
<motion.button
  whileHover={{ scale: 1.05 }}
  whileTap={{ scale: 0.95 }}
  transition={{ type: "spring", stiffness: 400, damping: 17 }}
>
  Solicitar Demo
</motion.button>
```

---

## Acessibilidade (CRÍTICO)

**SEMPRE respeitar `prefers-reduced-motion`:**

```tsx
import { useReducedMotion } from "motion/react";

const shouldReduceMotion = useReducedMotion();

const animation = shouldReduceMotion
  ? { opacity: 1 } // Sem movimento
  : { opacity: 1, y: 0 }; // Com movimento
```

**Ou via CSS:**

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## Anti-Patterns (Evitar)

| ❌ NÃO FAZER | ✅ FAZER |
|-------------|----------|
| Animações em loop infinito | Animações únicas (once: true) |
| Efeitos em TODOS os elementos | Animar apenas hero, CTAs, cards |
| Durações > 1s | Durações 0.3s - 0.6s |
| Remover classes do Tailwind para motion | Manter apenas motion para animação |
| Ignorar reduced-motion | Sempre usar `useReducedMotion()` |

---

## Integração com UI/UX Pro Max

Antes de criar a landing page, gerar Design System:

```bash
python3 .agent/skills/ui-ux-pro-max/scripts/search.py "<produto> <indústria>" --design-system -p "<Cliente>"
```

Aplicar tokens (cores, fontes, espaçamento) no `tailwind.config.ts` do template.

---

## Template Base

Usar `templates/template-landing-motion/` como ponto de partida:

```bash
cp -r templates/template-landing-motion entregas/{{CLIENTE}}/08-landing-premium
cd entregas/{{CLIENTE}}/08-landing-premium
npm install
npm run dev  # Preview
npm run build  # Gera dist/ para deploy
```

---

## Checklist Pré-Entrega

- [ ] Animações funcionam no scroll
- [ ] `prefers-reduced-motion` testado
- [ ] Build sem erros (`npm run build`)
- [ ] Lighthouse Performance > 90
- [ ] Links e CTAs funcionais
- [ ] Design System do cliente aplicado
