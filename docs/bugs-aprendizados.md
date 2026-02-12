# Bugs e Aprendizados

Este documento registra bugs descobertos, soluções aplicadas e aprendizados importantes do projeto.

---

## 2026-02-07 - GitHub Backup System

**Problema:** Necessidade de versionamento e backup do projeto para evitar perda de trabalho.

**Solução aplicada:**

- Configurado Git com `.gitignore` excluindo outputs, dependências e secrets
- Criado repositório privado `guilhermemarketing/gui-toolbox`
- Autenticado GitHub CLI com token pessoal
- Estruturado projeto com pasta `OUTPUT/` para entregáveis
- Criado workflow `/github-backup` para facilitar backups futuros

**Prevenção:**

- Fazer commits frequentes após mudanças significativas
- Usar mensagens descritivas nos commits
- Revisar mudanças com `git status` e `git diff` antes de commitar
- Manter `.gitignore` atualizado para excluir arquivos desnecessários

**Comandos úteis:**

```bash
# Backup rápido
git add . && git commit -m "Descrição" && git push

# Ver status
git status

# Ver histórico
git log --oneline -10

# Desfazer mudanças
git checkout -- <arquivo>
```

---

## 2026-02-07 - Instagram Scraping

**Problema:** Necessidade de baixar imagens de carrosséis do Instagram.

**Solução aplicada:**

- Criado script usando Playwright para navegação automatizada
- Implementado extração de URLs de imagens de alta resolução
- Adicionado download automático com nomeação sequencial

**Aprendizados:**

- Instagram carrega imagens dinamicamente
- URLs de alta resolução estão em `srcset` dos elementos `img`
- Necessário aguardar carregamento completo antes de extrair URLs

---

## 2026-02-07 - Otimização da Pasta /docs

**Problema:** Pasta `/docs` com conteúdo redundante e obsoleto consumindo tokens desnecessariamente.

**Solução aplicada:**

- Deletado `log-updates.md` (apenas 1 registro obsoleto de cliente GTM)
- Deletado `instagram-scraping.md` (detalhes excessivos sobre subagent)
- Mantido apenas `bugs-aprendizados.md` como fonte única de verdade

**Resultado:**

- Redução de 3 arquivos para 1 (-66%)
- Redução de 5KB para 1.6KB (-68%)
- Redução de ~1.250 tokens para ~400 (-68%)

**Prevenção:**

- Manter apenas informações reutilizáveis na documentação
- Evitar duplicação de conteúdo entre arquivos
- Remover logs de casos específicos (usar workflows genéricos)
- Revisar periodicamente a relevância da documentação

---

## 2026-02-11 - Fathom.video Download (CSP + HTTP-only cookies)

**Problema:** Baixar vídeo HLS do Fathom.video protegido por cookies HTTP-only e CSP restritivo.

**Solução aplicada:**

- Relay bridge via `postMessage`: browser baixa segmentos na memória → envia para aba localhost (sem CSP) → POST para servidor Node.js local
- Workflow `/fathom-downloader` criado com passo a passo completo

**Aprendizados:**

- `document.cookie` e `cookieStore.getAll()` NÃO retornam cookies HTTP-only
- CSP `connect-src` bloqueia `fetch`, `XHR`, e `sendBeacon` para hosts não-whitelistados
- `postMessage` NÃO é bloqueado por CSP — é a via de escape universal
- `redirect:'manual'` no `fetch` retorna opaque redirect (Location header inacessível via CORS)
- Extrair dados binários via base64/hex no retorno de JS é inviável para arquivos >10MB

**Prevenção:**

- Para sites com CSP + HTTP-only cookies, ir direto para a solução de relay bridge
- Não perder tempo tentando: curl com cookies parciais, ffmpeg sem auth, extraction via console logs

---
