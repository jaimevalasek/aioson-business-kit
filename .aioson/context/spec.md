---
project: "aioson-business-kit"
updated: "2026-05-29T11:04:56-03:00"
---

# Project Spec

## Stack
- Backend: Node.js / Next.js (API routes)
- Frontend: React (Next.js) + Tailwind CSS
- Database: MariaDB/MySQL (Prisma ORM)
- Auth: Painel do dev (sessão / API key local) — a definir em @architect
- UI/UX: Tailwind CSS
- Pagamentos: Stripe (conta do próprio dev)
- Integração: Aioson API SDK → `aioson.com`

## Current state
Projeto recém-inicializado (setup AIOSON concluído). Ainda sem código de aplicação —
existe apenas o scaffolding AIOSON e o plano de implementação em
`plans/plano-implementacao-aioson-business-kit.md`. Próxima fase: PRD com @product.

## Features

### Done
- (nenhuma ainda)

### In progress
- (nenhuma ainda)

### Planned
- Setup inicial: tela de configuração (AIOSON_API_*, chaves Stripe)
- Sincronização de apps publicados com o `aioson.com`
- CRUD local de produtos vinculados a apps do marketplace
- Página pública de venda `/apps/{slug}`
- Checkout Stripe (compra única / assinatura mensal / anual)
- Webhook Stripe com idempotência
- Sync de licenças com o `aioson.com` (created / renewed / past_due / cancelled / refunded)
- Painel de comissões (fatura de 10% da Aioson)
- Painéis: dashboard, clientes, assinaturas, licenças
- Documentação open-source (README, INSTALL, DEPLOY, STRIPE_SETUP, AIOSON_INTEGRATION)

## Open decisions
- Estratégia de auth do painel do dev (sessão local vs. API key vs. outro)
- Sistema visual / `design_skill` (pendente — confirmar em @ux-ui / @product; Tailwind já definido)
- Geração de license key: local no Business Kit vs. solicitada ao `aioson.com`
- Criptografia de settings sensíveis no banco

## Key decisions
- 2026-05-29 Banco MariaDB/MySQL (em vez do SQLite/PostgreSQL sugerido no plano) — decisão do dono do projeto, vale para dev e produção
- 2026-05-29 Classificação MEDIUM — 2 papéis (dev + cliente), Stripe + Aioson API, regras de licença/comissão complexas
- 2026-05-29 Modelo sem repasse financeiro pela Aioson — dev usa Stripe próprio; Aioson cobra comissão de 10%

## Notes
- Dependência externa (plano §17): o MVP só fecha quando o `aioson.com` já tiver license
  server, API keys de dev, `POST /api/dev/events`, `GET /api/dev/apps` e commission invoices.
- Ordem recomendada no ecossistema: aioson-com → aioson-play → aioson (publish) → aioson-business-kit.
- Cliente final instala/usa os apps no `aioson-play` / `aioson-play-online`.
- Plano de referência completo: `plans/plano-implementacao-aioson-business-kit.md`.
