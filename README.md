# 🧠 GUI Marketing Skills

Coleção de skills customizadas para agentes AI (Gemini, Claude Code, Cursor, Windsurf, Cline, etc.) focadas em **marketing digital, Google Tag Manager e criação de anúncios**.

## 📦 Skills Disponíveis

| Skill | Descrição | Trigger |
|-------|-----------|---------|\
| **animation-systems** | Motion product-grade estilo Stripe, Linear, Apple, Vercel. Princípios, easing, choreography, performance. | `animation systems`, `product motion`, `Stripe animation` |
| **animejs** | Anime.js v4 - animações web, timelines, SVG, scroll, draggable, stagger effects. | `anime.js`, `animejs`, `timeline animation` |
| **b2b-meme-troll** | Gera memes, trolls e posts provocativos para Instagram B2B de marketing digital. Conteúdo que quebra o padrão boring do B2B sem soar infantil. | `meme B2B`, `post provocativo`, `meta-troll`, `shitpost marketing` |
| **css-border-gradient** | Gradient borders CSS com pseudo-element mask. Inclui Tailwind e customização. | `gradient border`, `border glow`, `css gradient` |
| **giroguimkt-carousel** | Criar carrosséis completos para a editoria #giroguimkt do Instagram. Textos dos cards, prompts de imagem e legenda no tom editorial gui.marketing. | `#giroguimkt`, `giro da semana`, `carrossel semanal` |
| **gsap** | GSAP (GreenSock) - timelines, ScrollTrigger, stagger, transforms. Animações profissionais web. | `gsap`, `greensock`, `ScrollTrigger` |
| **gtm-expert** | Criar, editar, validar e gerenciar containers GTM JSON. Cobre tags Custom HTML, dataLayer, conversões (Google Ads, Meta Pixel, GA4), e sGTM. | `gtm`, `tag manager`, `container json` |
| **gtm-expert-template-guimarketing** | Customizar o template GTM Leads 2025 da guimarketing para novos clientes. GA4 + Meta Pixel + Google Ads + VisitorAPI + UTM + sGTM. | `new client GTM`, `customize GTM template` |
| **gui-blogpost-style** | Replica o estilo de escrita de blogpost do gui.marketing para criar artigos longos. Tom provocador, estrutura educacional, referências culturais. | `blogpost`, `artigo de blog`, `escreve no meu estilo`, `conteúdo longo` |
| **guimkt-classic-ad-creative** | Gerar conceitos criativos completos para Meta Ads e Google Ads. Copy, conceito visual, sketches de referência. | `meta ads criativos`, `ad creative` |
| **guimkt-image-gen** | Gera prompts de imagem editorial e infográficos no estilo neo-brutalist punk da marca gui.marketing. Dois modos: ilustrações (sem texto) e infográficos (com dados/texto). | `gerar imagem`, `infográfico`, `visual do card`, `ilustração do post` |
| **guimkt-page-animation-boost** | Pacote premium de Motion e UX: GSAP animations, brutalist clip-paths, geometric parallax, CSS neon glows, bottom-up reveals e mobile micro-interactions. | `page animation boost`, `motion boost`, `animação landing page` |
| **ia-marketing-philosophy** | Contexto e filosofia de IA Marketing do gui.marketing. Foco: gerar VALOR REAL, não SLOP. Posicionamento, objeções, consistência filosófica. | `valor vs slop`, `operação IA-first`, `IA no marketing`, `estrategista provocador` |
| **interaction-design** | Design e implementação de microinterações, motion design, transições e feedback patterns. | `microinteraction`, `motion design`, `interaction` |
| **matterjs** | Matter.js - física 2D, Engine/World setup, Render/Runner, bodies e constraints. | `matter.js`, `physics`, `2D physics` |
| **pricing-page** | Design de pricing pages SaaS de alta conversão. Estrutura, copy, SEO/AEO, FAQs, layout patterns. | `pricing page`, `SaaS pricing`, `planos e preços` |
| **progressive-blur** | Progressive blur CSS com backdrop-filter masks em camadas. Top ou bottom. | `progressive blur`, `gradient blur`, `blur overlay` |
| **responsive-design** | Layouts responsivos modernos: container queries, fluid typography, CSS Grid, mobile-first. | `responsive`, `container queries`, `fluid typography` |
| **threejs-animation** | Three.js animation - keyframe animation, skeletal animation, morph targets, animation mixing. | `threejs`, `three.js animation`, `GLTF animation` |
| **vantajs** | Vanta.js - backgrounds WebGL animados (waves, birds, fog, net). Setup e integração React. | `vanta`, `webgl background`, `animated background` |

## 🚀 Instalação

### Opção 1: Script rápido (recomendado)

```bash
curl -sL https://raw.githubusercontent.com/guilhermemarketing/gui-marketing-skills/main/install.sh | bash
```

### Opção 2: Git Submodule

```bash
# Adicionar como submodule (mantém sincronizado)
git submodule add https://github.com/guilhermemarketing/gui-marketing-skills.git .agent/external-skills

# Atualizar no futuro
git submodule update --remote
```

### Opção 3: Clone manual

```bash
git clone https://github.com/guilhermemarketing/gui-marketing-skills.git /tmp/gui-marketing-skills
cp -r /tmp/gui-marketing-skills/skills/* .agent/skills/
rm -rf /tmp/gui-marketing-skills
```

## 🤖 Configuração para Agentes AI

Adicione ao `.instructions` ou arquivo de configuração do seu projeto:

```markdown
## External Skills
Custom marketing skills estão disponíveis em `.agent/skills/` (ou `.agent/external-skills/skills/` se usando submodule).
Antes de iniciar qualquer tarefa de marketing, GTM ou criação de anúncios, verifique se existe uma skill relevante.
Carregue skills com `view_file` no arquivo SKILL.md correspondente.
```

## 📁 Estrutura

```
gui-marketing-skills/
├── README.md
├── install.sh
├── skills/
│   ├── animation-systems/
│   │   └── SKILL.md
│   ├── animejs/
│   │   └── SKILL.md
│   ├── b2b-meme-troll/
│   │   ├── SKILL.md
│   │   └── references/
│   │       ├── exemplos.md
│   │       ├── formatos-e-tensoes.md
│   │       ├── identidade-visual.md
│   │       └── tom-e-principios.md
│   ├── css-border-gradient/
│   │   └── SKILL.md
│   ├── giroguimkt-carousel/
│   │   ├── SKILL.md
│   │   ├── assets/ (8 reference images)
│   │   └── references/
│   │       ├── carousel-structure.md
│   │       ├── editorial-voice.md
│   │       ├── image-prompts.md
│   │       └── caption-structure.md
│   ├── gsap/
│   │   └── SKILL.md
│   ├── gtm-expert/
│   │   ├── SKILL.md
│   │   ├── references/schema.md
│   │   └── scripts/
│   │       ├── validate_gtm.py
│   │       └── verify_es5.py
│   ├── gtm-expert-template-guimarketing/
│   │   ├── SKILL.md
│   │   ├── references/template_inventory.md
│   │   ├── scripts/customize_template.py
│   │   └── templates/GTM-Web_Modelo_Leads_2025_guimarketing.json
│   ├── gui-blogpost-style/
│   │   └── SKILL.md
│   ├── guimkt-classic-ad-creative/
│   │   └── SKILL.MD
│   ├── guimkt-image-gen/
│   │   ├── SKILL.md
│   │   └── references/
│   │       ├── base-prompt.md
│   │       ├── infographic-base-prompt.md
│   │       └── prompt-examples.md
│   ├── guimkt-page-animation-boost/
│   │   ├── SKILL.md
│   │   └── references/
│   │       ├── 3d-web-experience.md
│   │       ├── interaction-design.md
│   │       └── motion-landing-page.md
│   ├── ia-marketing-philosophy/
│   │   └── SKILL.md
│   ├── interaction-design/
│   │   └── SKILL.md
│   ├── matterjs/
│   │   └── SKILL.md
│   ├── pricing-page/
│   │   └── SKILL.md
│   ├── progressive-blur/
│   │   └── SKILL.md
│   ├── responsive-design/
│   │   └── SKILL.md
│   ├── threejs-animation/
│   │   └── SKILL.md
│   └── vantajs/
│       └── SKILL.md
└── docs/
    └── bugs-aprendizados.md
```

## 🔄 Atualizações

Novas skills serão adicionadas conforme o workflow da agência evolui. Para receber atualizações:

- **Submodule:** `git submodule update --remote`
- **Script:** Re-execute o `install.sh`
- **Clone:** Re-clone o repositório

## 📄 Licença

Uso interno — © guimarketing
