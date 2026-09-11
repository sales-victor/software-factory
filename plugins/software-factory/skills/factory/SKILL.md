---
name: factory
description: Orquestra uma funcionalidade completa através da Software Factory. Use quando o usuário quiser criar, alterar ou implementar uma funcionalidade de software.
---

# Software Factory

Você é o Orchestrator da Software Factory.

Quando esta skill for acionada, execute o workflow completo da fábrica.

## Entrada

A solicitação do usuário é:

$ARGUMENTS

## Workflow

### 1. Discovery

Analise:

- requisito;
- projeto;
- stack;
- estrutura existente;
- funcionalidades semelhantes;
- dependências;
- impactos.

Leia o CLAUDE.md antes de iniciar.

---

### 2. Architecture

Acione o agente `architect`.

Ele deve definir:

- arquitetura;
- componentes;
- responsabilidades;
- dependências;
- riscos;
- estratégia de implementação.

Salvar em:

.factory/architecture.md

---

### 3. UX/UI

Se existir interface, acione `ux-ui`.

Definir:

- fluxo;
- telas;
- componentes;
- estados;
- validações;
- acessibilidade;
- responsividade.

Salvar em:

.factory/ux.md

---

### 4. Database

Se houver persistência, acione `dba`.

Avaliar:

- tabelas;
- relacionamentos;
- índices;
- constraints;
- queries;
- performance;
- migrações.

Salvar em:

.factory/database.md

---

### 5. Contracts

Defina os contratos entre frontend e backend.

Quando aplicável:

- endpoints;
- DTOs;
- modelos;
- validações;
- responses;
- erros.

Salvar em:

.factory/contracts.md

---

### 6. Backend

Acione `backend-dev`.

O backend deve respeitar:

- arquitetura;
- contratos;
- padrões existentes;
- regras de negócio;
- segurança.

Criar ou atualizar testes.

---

### 7. Frontend

Se existir frontend, acione `frontend-dev`.

O frontend deve respeitar:

- UX;
- contratos;
- design system;
- padrões existentes.

Criar ou atualizar testes.

---

### 8. QA

Acione `qa`.

Verificar:

- critérios de aceite;
- happy path;
- validações;
- casos extremos;
- permissões;
- regressões;
- erros.

Salvar:

.factory/qa.md

---

### 9. Security

Acione `security`.

Verificar:

- autenticação;
- autorização;
- SQL Injection;
- XSS;
- CSRF;
- SSRF;
- secrets;
- exposição de dados;
- privilege escalation;
- dependências.

Salvar:

.factory/security.md

---

### 10. Code Review

Acione `code-reviewer`.

Revisar:

- bugs;
- arquitetura;
- segurança;
- performance;
- testes;
- manutenção;
- regressões.

Salvar:

.factory/code-review.md

---

### 11. Build

Execute os comandos de build/teste existentes no projeto.

Não invente comandos se o projeto já possuir scripts/configurações próprias.

---

### 12. Final Report

Criar:

.factory/final-report.md

Com:

# Software Factory Report

## Feature

## Architecture

## UX/UI

## Database

## Contracts

## Backend

## Frontend

## Tests

## Security

## Code Review

## Build

## Files Changed

## Risks

## Status

Status possíveis:

- READY
- READY_WITH_WARNINGS
- BLOCKED
- FAILED

Nunca declarar READY com problemas críticos ou altos conhecidos.