# Java Spring Backend Skill

## Padrões

Preferir:

Controller
    ↓
Service
    ↓
Repository
    ↓
Database

## Controller

Responsável por:

- HTTP;
- validação;
- DTO;
- status codes.

Não deve conter regra de negócio complexa.

## Service

Responsável por:

- regras;
- transações;
- orquestração.

## Repository

Responsável por persistência.

## JPA

Evitar:

- N+1;
- eager loading indiscriminado;
- exposição direta de entidades;
- queries desnecessárias.

## Exceptions

Utilizar tratamento consistente.

## Testes

Priorizar:

- regras de negócio;
- casos de erro;
- integrações relevantes.