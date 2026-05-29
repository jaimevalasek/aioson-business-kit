---
project_name: "aioson-business-kit"
project_type: "web_app"
profile: "developer"
framework: "Next.js"
framework_installed: false
classification: "MEDIUM"
interaction_language: "pt-BR"
conversation_language: "pt-BR"
design_skill: ""
test_runner: ""
web3_enabled: false
web3_networks: ""
contract_framework: ""
wallet_provider: ""
indexer: ""
rpc_provider: ""
aioson_version: "1.21.3"
generated_at: "2026-05-29T11:04:56-03:00"
---

# Project Context

Aioson Business Kit (Seller Kit) — app open-source que o dev/empresa instala no
próprio domínio para listar, publicar e vender seus apps do ecossistema AIOSON,
recebendo via Stripe próprio e sincronizando licenças, eventos e comissões com o
`aioson.com`. Cliente final instala/usa os apps no `aioson-play` / `aioson-play-online`.

## Stack
- Backend: Node.js / Next.js (API routes)
- Frontend: React (Next.js) + Tailwind CSS
- Database: MariaDB/MySQL (Prisma ORM)
- Auth: Painel do dev (sessão / API key local) — a definir em @architect
- UI/UX: Tailwind CSS

## Services
- Queues: 
- Storage: 
- WebSockets: 
- Email: 
- Payments: Stripe (conta do próprio dev — sem repasse pela Aioson)
- Cache: 
- Search: 

## Integrations
- Aioson API SDK → `aioson.com` (registry de apps, licenças, comissões, eventos)
- Stripe (checkout + webhooks do dev)

## Web3
- Enabled: no
- Networks: [not applicable]
- Contract framework: [not applicable]
- Wallet provider: [not applicable]
- Indexer: [not applicable]
- RPC provider: [not applicable]

## Installation commands
[framework_installed=false — @architect/@dev devem incluir setup antes de implementar]
- npx create-next-app@latest . (App Router, TypeScript, Tailwind, ESLint)
- npm install prisma @prisma/client && npx prisma init --datasource-provider mysql
- npm install stripe @stripe/stripe-js
- Configurar `.env` a partir de `.env.example` (DATABASE_URL MySQL, chaves Stripe, AIOSON_API_*)

## Notes
- Modelo de negócio: dev recebe no Stripe próprio; Aioson NÃO faz repasse; comissão de 10%
  é apurada e cobrada pela Aioson via painel de comissões.
- Dependência externa (plano §17): exige que o `aioson.com` já tenha license server,
  API keys de dev, `POST /api/dev/events`, `GET /api/dev/apps` e commission invoices
  antes da implementação plena do MVP.
- Banco: SQLite estava sugerido no plano para dev/local; substituído por MariaDB/MySQL
  por decisão do dono do projeto (dev e produção).
- Plano de referência: `plans/plano-implementacao-aioson-business-kit.md`
- Projetos relacionados: `c:\dev\aioson` (motor/framework), `c:\dev\aioson-com`
  (registry/marketplace/licenças), `c:\dev\aioson-play` + `c:\dev\aioson-play-online` (runtime).

## Conventions
- Language: pt-BR
- Code comments language: pt-BR
- DB naming: snake_case
- JS/TS naming: camelCase
