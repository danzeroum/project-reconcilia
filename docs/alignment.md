<!-- DERIVADO de ci/alignment_report.py. NÃO EDITE À MÃO: regere com
     python ci/alignment_report.py — o --check do CI contradiz qualquer edição manual. -->
# Alinhamento entre departamentos

Matriz derivada do metadado declarado. Ela responde a pergunta que os demais fiscais não
fazem: **o que ficou de fora?**

## Cobertura de risco por capacidade

| Capacidade | risk_level | Riscos que a cobrem |
|---|---|---|
| `CAP-ACCESS-CONTROL` | pending_judgment | — |
| `CAP-ACQUIRER-INTEGRATION` | pending_judgment | — |
| `CAP-ANOMALY-DETECTION` | pending_judgment | — |
| `CAP-CASH-FLOW` | pending_judgment | — |
| `CAP-DASHBOARD-NOTIFICATIONS` | pending_judgment | — |
| `CAP-PLATFORM` | pending_judgment | — |
| `CAP-RECONCILIATION` | pending_judgment | — |

## Componentes

| Componente | Status | Capacidade | Implementa | Coberto por risco |
|---|---|---|---|---|
| `CMP-ACQUIRER-ADAPTERS` | implemented | `CAP-ACQUIRER-INTEGRATION` | REQ-001, REQ-002, REQ-003 | não |
| `CMP-ACQUIRER-PARSERS` | implemented | `CAP-ACQUIRER-INTEGRATION` | REQ-002 | não |
| `CMP-ALERTS` | implemented | `CAP-ANOMALY-DETECTION` | REQ-011 | não |
| `CMP-ANOMALY` | implemented | `CAP-ANOMALY-DETECTION` | — | não |
| `CMP-API-CORE` | implemented | `CAP-PLATFORM` | — | não |
| `CMP-AUTH-API` | implemented | `CAP-ACCESS-CONTROL` | — | não |
| `CMP-BANK-OFX` | implemented | `CAP-RECONCILIATION` | — | não |
| `CMP-CASH-FLOW` | implemented | `CAP-CASH-FLOW` | REQ-019 | não |
| `CMP-CIELO-CONCILIATOR` | implemented | `CAP-ACQUIRER-INTEGRATION` | REQ-001 | não |
| `CMP-DASHBOARD-API` | implemented | `CAP-DASHBOARD-NOTIFICATIONS` | REQ-015 | não |
| `CMP-DECISION-TABLE` | implemented | `CAP-RECONCILIATION` | REQ-007 | não |
| `CMP-DIVERGENCE-API` | implemented | `CAP-ANOMALY-DETECTION` | REQ-011, REQ-012, REQ-013, REQ-014 | não |
| `CMP-DOMAIN-ENTITIES` | implemented | `CAP-PLATFORM` | — | não |
| `CMP-DOMAIN-PORTS` | implemented | `CAP-PLATFORM` | — | não |
| `CMP-DOMAIN-VALUES` | implemented | `CAP-PLATFORM` | — | não |
| `CMP-HTTP-MIDDLEWARE` | implemented | `CAP-ACCESS-CONTROL` | — | não |
| `CMP-INFRA-CORE` | implemented | `CAP-PLATFORM` | — | não |
| `CMP-INGESTION` | implemented | `CAP-ACQUIRER-INTEGRATION` | REQ-001, REQ-006 | não |
| `CMP-INGESTION-API` | implemented | `CAP-ACQUIRER-INTEGRATION` | REQ-005 | não |
| `CMP-MATCHING-ENGINE` | implemented | `CAP-RECONCILIATION` | — | não |
| `CMP-NOTIFICATION` | implemented | `CAP-DASHBOARD-NOTIFICATIONS` | REQ-017 | não |
| `CMP-PERSISTENCE` | implemented | `CAP-PLATFORM` | — | não |
| `CMP-RECONCILIATION-API` | implemented | `CAP-RECONCILIATION` | REQ-007, REQ-008 | não |
| `CMP-RECONCILIATION-JOBS` | implemented | `CAP-RECONCILIATION` | REQ-007 | não |
| `CMP-RECONCILIATION-USECASES` | implemented | `CAP-RECONCILIATION` | REQ-007 | não |
| `CMP-REPORTING` | implemented | `CAP-DASHBOARD-NOTIFICATIONS` | — | não |
| `CMP-SALES` | implemented | `CAP-DASHBOARD-NOTIFICATIONS` | — | não |
| `CMP-SECURITY` | implemented | `CAP-ACCESS-CONTROL` | — | não |
| `CMP-TRANSACTIONS` | implemented | `CAP-DASHBOARD-NOTIFICATIONS` | — | não |
| `CMP-UI-API-CLIENT` | implemented | `CAP-DASHBOARD-NOTIFICATIONS` | REQ-015 | não |
| `CMP-UI-COMPONENTS` | implemented | `CAP-DASHBOARD-NOTIFICATIONS` | REQ-016 | não |
| `CMP-UI-HOOKS` | implemented | `CAP-DASHBOARD-NOTIFICATIONS` | REQ-015 | não |
| `CMP-UI-PAGES-ACCESS` | implemented | `CAP-ACCESS-CONTROL` | — | não |
| `CMP-UI-PAGES-CASH-FLOW` | implemented | `CAP-CASH-FLOW` | REQ-019 | não |
| `CMP-UI-PAGES-DASHBOARD` | implemented | `CAP-DASHBOARD-NOTIFICATIONS` | REQ-015 | não |
| `CMP-UI-PAGES-DIVERGENCES` | implemented | `CAP-ANOMALY-DETECTION` | REQ-012 | não |
| `CMP-UI-PAGES-RECONCILIATION` | implemented | `CAP-RECONCILIATION` | REQ-007 | não |
| `CMP-UI-SHELL` | implemented | `CAP-DASHBOARD-NOTIFICATIONS` | — | não |
| `CMP-USER-PERSISTENCE` | implemented | `CAP-ACCESS-CONTROL` | — | não |

## Riscos por área

| Área | Total | Abertos |
|---|---|---|
| access | 2 | 0 |
| data | 2 | 0 |
| dependencies | 1 | 0 |
| governance | 11 | 0 |
| webqa | 1 | 0 |

## Pendências de alinhamento

Nenhuma. Todo ativo relevante está coberto ou tem isenção declarada.
