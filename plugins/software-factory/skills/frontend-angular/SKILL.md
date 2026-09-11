# Angular Skill

## Arquitetura

Separar:

- Components
- Services
- Models
- Guards
- Interceptors
- Shared components

## RxJS

Evitar subscriptions manuais quando alternativas mais seguras existirem.

Considerar:

- async pipe;
- takeUntil;
- switchMap;
- debounceTime;
- catchError.

## Forms

Preferir Reactive Forms para formulários complexos.

## Components

Manter componentes pequenos.

Evitar componentes que concentram:

- API;
- regras;
- layout;
- validação;
- navegação.

Separar responsabilidades.