---
name: factory-security
description: Executa uma auditoria de segurança da implementação atual usando o agente Security.
disable-model-invocation: true
---

# Factory Security

Leia o estado atual da Factory.

Delegue para `security`.

Analise:

- authentication
- authorization
- input validation
- injection
- XSS
- CSRF
- secrets
- credentials
- dependencies
- CORS
- headers
- exposição de informações
- logging
- configuração
- OWASP Top 10

Crie:

.factory/stages/security.md

Crie issues classificadas por:

CRITICAL
HIGH
MEDIUM
LOW

Atualize:

.factory/factory.json
.factory/board.md

CRITICAL e HIGH devem bloquear o Security Gate.

Não corrija automaticamente.

Para correções utilize:

/software-factory:factory-fix