# FFKD Holding — Tech

Repositório de referência da organização. Documenta a arquitetura, os produtos e as diretrizes técnicas da FFKD.

---

## Produtos

| Produto | Descrição |
|---|---|
| **EasyFleet** | Plataforma integradora de serviços de gestão de frotas — abastecimento, pneus, manutenção, TCO e demais serviços via API |
| **Carro Verificado** | Plataforma de consulta e verificação de histórico veicular |

---

## Repositórios

| Repositório | Produto | Responsabilidade |
|---|---|---|
| [`easy_fleet`](https://github.com/ffkd-org/easy_fleet) | EasyFleet | Monorepo — API, microserviço, web e mobile |
| [`carro_verificado_app`](https://github.com/ffkd-org/carro_verificado_app) | Carro Verificado | Aplicativo mobile |
| [`carro_verificado_web`](https://github.com/ffkd-org/carro_verificado_web) | Carro Verificado | Portal web do consumidor |
| [`carro_verificado_backend`](https://github.com/ffkd-org/carro_verificado_backend) | Carro Verificado | API REST e motor de consultas |
| [`ffkd_mcp`](https://github.com/ffkd-org/ffkd_mcp) | EasyFleet + Carro Verificado | Servidor MCP unificado |

### Estrutura do monorepo `easy_fleet`

```
apps/
  api/        — API Gateway (NestJS · Prisma · JWT · Swagger)
  service/    — Microserviço de integração (NestJS · RabbitMQ · Redis)
  web/        — Portal web do gestor (React + Vite)
  mobile/     — Aplicativo mobile (React Native + Expo)
packages/
  contracts/  — Tipos e eventos compartilhados entre apps
  tsconfig/   — Configuração TypeScript base
  eslint-config/ — Regras ESLint compartilhadas
```

---

## Governança

> Em construção. As políticas de branching, code review e deploy serão documentadas aqui conforme a organização evolui.

---

## Contexto para Claude Code

Ao clonar qualquer repositório da organização, carregue o onboarding guide no Claude Code:

**https://claude.ai/claude-code/onboard/G0IVm9NOsbBU**
