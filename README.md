# 🧠 GUI Marketing Skills

Coleção de skills customizadas para agentes AI (Gemini, Claude Code, Cursor, Windsurf, Cline, etc.) focadas em **marketing digital, Google Tag Manager e criação de anúncios**.

## 📦 Skills Disponíveis

| Skill | Descrição | Trigger |
|-------|-----------|---------|
| **gtm-expert** | Criar, editar, validar e gerenciar containers GTM JSON. Cobre tags Custom HTML, dataLayer, conversões (Google Ads, Meta Pixel, GA4), e sGTM. | `gtm`, `tag manager`, `container json` |
| **gtm-expert-template-guimarketing** | Customizar o template GTM Leads 2025 da guimarketing para novos clientes. GA4 + Meta Pixel + Google Ads + VisitorAPI + UTM + sGTM. | `new client GTM`, `customize GTM template` |
| **guimkt-classic-ad-creative** | Gerar conceitos criativos completos para Meta Ads e Google Ads. Copy, conceito visual, sketches de referência. | `meta ads criativos`, `ad creative` |
| **giroguimkt-carousel** | Criar carrosséis completos para a editoria #giroguimkt do Instagram. Textos dos cards, prompts de imagem e legenda no tom editorial gui.marketing. | `#giroguimkt`, `giro da semana`, `carrossel semanal` |

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
│   ├── guimkt-classic-ad-creative/
│   │   └── SKILL.MD
│   └── giroguimkt-carousel/
│       ├── SKILL.md
│       ├── assets/ (8 reference images)
│       └── references/
│           ├── carousel-structure.md
│           ├── editorial-voice.md
│           ├── image-prompts.md
│           └── caption-structure.md
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
