# Mapa de relacionamento dos metadados

> **Gerado** por `ci/generate_graph.py` a partir dos metadados reais. Não editar à mão —
> regenerar com `python ci/generate_graph.py`. É um artefato derivado, não fonte de verdade.

Legenda: azul-escuro = projeto · azul = capacidade (`CAP-`) · ciano = componente (`CMP-`) ·
roxo = interface (`IFC-`) · verde = regra (`RULE-`) · rosa = superfície de UI (`UI-`) ·
amarelo = ADR · vermelho = risco (`RISK-`).

```mermaid
graph TD
  PROJ_danzeroum_project_reconcilia["danzeroum-project-reconcilia"]
  TEST_workspace_target_conciliaai_frontend_tests_unit_components_DataTable_test_tsx{{"DataTable.test.tsx"}}
  TEST_workspace_target_conciliaai_frontend_tests_unit_hooks_useSales_test_tsx{{"useSales.test.tsx"}}
  TEST_workspace_target_conciliaai_frontend_tests_unit_hooks_useTransactions_test_tsx{{"useTransactions.test.tsx"}}
  TEST_workspace_target_conciliaai_frontend_tests_unit_utils_formatters_test_ts{{"formatters.test.ts"}}
  TEST_workspace_target_conciliaai_frontend_tests_unit_utils_validators_test_ts{{"validators.test.ts"}}
  TEST_workspace_target_tests_integration_test_acquirer_clients_py{{"test_acquirer_clients.py"}}
  TEST_workspace_target_tests_integration_test_auth_endpoints_py{{"test_auth_endpoints.py"}}
  TEST_workspace_target_tests_integration_test_cielo_integration_py{{"test_cielo_integration.py"}}
  TEST_workspace_target_tests_integration_test_postgresql_repositories_py{{"test_postgresql_repositories.py"}}
  TEST_workspace_target_tests_integration_test_protected_endpoints_py{{"test_protected_endpoints.py"}}
  TEST_workspace_target_tests_integration_test_reconciliation_flow_py{{"test_reconciliation_flow.py"}}
  TEST_workspace_target_tests_integration_test_rede_edi_upload_py{{"test_rede_edi_upload.py"}}
  TEST_workspace_target_tests_unit_infrastructure_test_cielo_conciliator_client_py{{"test_cielo_conciliator_client.py"}}
  TEST_workspace_target_tests_unit_infrastructure_test_ofx_parser_py{{"test_ofx_parser.py"}}
  TEST_workspace_target_tests_unit_infrastructure_test_rede_edi_parser_py{{"test_rede_edi_parser.py"}}
  TEST_workspace_target_tests_unit_parsers_test_rede_edi_parser_positional_py{{"test_rede_edi_parser_positional.py"}}
  TEST_workspace_target_tests_unit_security_test_jwt_handler_py{{"test_jwt_handler.py"}}
  TEST_workspace_target_tests_unit_security_test_password_hasher_py{{"test_password_hasher.py"}}
  TEST_workspace_target_tests_unit_security_test_rate_limiter_py{{"test_rate_limiter.py"}}
  TEST_workspace_target_tests_unit_test_anomaly_detection_service_py{{"test_anomaly_detection_service.py"}}
  TEST_workspace_target_tests_unit_test_auto_bank_reconciliation_py{{"test_auto_bank_reconciliation.py"}}
  TEST_workspace_target_tests_unit_test_auto_import_alert_py{{"test_auto_import_alert.py"}}
  TEST_workspace_target_tests_unit_test_exact_matcher_py{{"test_exact_matcher.py"}}
  TEST_workspace_target_tests_unit_test_export_service_py{{"test_export_service.py"}}
  TEST_workspace_target_tests_unit_test_fuzzy_matcher_py{{"test_fuzzy_matcher.py"}}
  TEST_workspace_target_tests_unit_test_rbac_and_audit_middleware_py{{"test_rbac_and_audit_middleware.py"}}
  TEST_workspace_target_tests_unit_test_rede_api_client_py{{"test_rede_api_client.py"}}
  TEST_workspace_target_tests_unit_test_security_hardening_py{{"test_security_hardening.py"}}
  TEST_workspace_target_tests_unit_test_stats_dashboard_response_py{{"test_stats_dashboard_response.py"}}
  TEST_workspace_target_tests_unit_use_cases_test_import_cielo_report_py{{"test_import_cielo_report.py"}}
  TEST_workspace_target_tests_unit_use_cases_test_reconcile_bank_statement_py{{"test_reconcile_bank_statement.py"}}
  CAP_ACCESS_CONTROL["CAP-ACCESS-CONTROL<br/>Controle de acesso e isolamento por tenant"]
  PROJ_danzeroum_project_reconcilia -->|capacidade| CAP_ACCESS_CONTROL
  CAP_ACQUIRER_INTEGRATION["CAP-ACQUIRER-INTEGRATION<br/>Integração com adquirentes"]
  PROJ_danzeroum_project_reconcilia -->|capacidade| CAP_ACQUIRER_INTEGRATION
  CAP_ANOMALY_DETECTION["CAP-ANOMALY-DETECTION<br/>Detecção de anomalias"]
  PROJ_danzeroum_project_reconcilia -->|capacidade| CAP_ANOMALY_DETECTION
  CAP_CASH_FLOW["CAP-CASH-FLOW<br/>Previsão de fluxo de caixa"]
  PROJ_danzeroum_project_reconcilia -->|capacidade| CAP_CASH_FLOW
  CAP_DASHBOARD_NOTIFICATIONS["CAP-DASHBOARD-NOTIFICATIONS<br/>Dashboard e notificações"]
  PROJ_danzeroum_project_reconcilia -->|capacidade| CAP_DASHBOARD_NOTIFICATIONS
  CAP_PLATFORM["CAP-PLATFORM<br/>Plataforma: domínio, persistência e superfície HTTP"]
  PROJ_danzeroum_project_reconcilia -->|capacidade| CAP_PLATFORM
  CAP_RECONCILIATION["CAP-RECONCILIATION<br/>Reconciliação automática"]
  PROJ_danzeroum_project_reconcilia -->|capacidade| CAP_RECONCILIATION
  CMP_ACQUIRER_ADAPTERS["CMP-ACQUIRER-ADAPTERS<br/>__init__.py"]
  CMP_ACQUIRER_ADAPTERS -->|realiza| CAP_ACQUIRER_INTEGRATION
  CMP_ACQUIRER_ADAPTERS -->|depende| CMP_DOMAIN_ENTITIES
  CMP_ACQUIRER_ADAPTERS -->|depende| CMP_DOMAIN_VALUES
  CMP_ACQUIRER_ADAPTERS -->|depende| CMP_INFRA_CORE
  CMP_ACQUIRER_ADAPTERS -.->|implementa| REQ_001
  CMP_ACQUIRER_ADAPTERS -.->|implementa| REQ_002
  CMP_ACQUIRER_ADAPTERS -.->|implementa| REQ_003
  CMP_ACQUIRER_ADAPTERS -.->|testa| TEST_workspace_target_tests_integration_test_acquirer_clients_py
  CMP_ACQUIRER_ADAPTERS -.->|testa| TEST_workspace_target_tests_unit_infrastructure_test_cielo_conciliator_client_py
  CMP_ACQUIRER_ADAPTERS -.->|testa| TEST_workspace_target_tests_unit_test_rede_api_client_py
  CMP_ACQUIRER_PARSERS["CMP-ACQUIRER-PARSERS<br/>__init__.py"]
  CMP_ACQUIRER_PARSERS -->|realiza| CAP_ACQUIRER_INTEGRATION
  CMP_ACQUIRER_PARSERS -->|depende| CMP_DOMAIN_ENTITIES
  CMP_ACQUIRER_PARSERS -->|depende| CMP_DOMAIN_VALUES
  CMP_ACQUIRER_PARSERS -.->|implementa| REQ_002
  CMP_ACQUIRER_PARSERS -.->|testa| TEST_workspace_target_tests_unit_infrastructure_test_rede_edi_parser_py
  CMP_ACQUIRER_PARSERS -.->|testa| TEST_workspace_target_tests_unit_parsers_test_rede_edi_parser_positional_py
  CMP_ALERTS["CMP-ALERTS<br/>alert_service.py"]
  CMP_ALERTS -->|realiza| CAP_ANOMALY_DETECTION
  CMP_ALERTS -->|depende| CMP_DOMAIN_ENTITIES
  CMP_ALERTS -->|depende| CMP_DOMAIN_PORTS
  CMP_ALERTS -->|depende| CMP_DOMAIN_VALUES
  CMP_ALERTS -->|depende| CMP_INFRA_CORE
  CMP_ALERTS -->|depende| CMP_NOTIFICATION
  CMP_ALERTS -->|depende| CMP_PERSISTENCE
  CMP_ALERTS -.->|implementa| REQ_011
  CMP_ANOMALY["CMP-ANOMALY<br/>anomaly_detection_service.py"]
  CMP_ANOMALY -->|realiza| CAP_ANOMALY_DETECTION
  CMP_ANOMALY -->|depende| CMP_DOMAIN_ENTITIES
  CMP_ANOMALY -->|depende| CMP_DOMAIN_VALUES
  CMP_ANOMALY -.->|testa| TEST_workspace_target_tests_unit_test_anomaly_detection_service_py
  CMP_API_CORE["CMP-API-CORE<br/>__init__.py"]
  CMP_API_CORE -->|realiza| CAP_PLATFORM
  CMP_API_CORE -->|depende| CMP_ACQUIRER_ADAPTERS
  CMP_API_CORE -->|depende| CMP_CIELO_CONCILIATOR
  CMP_API_CORE -->|depende| CMP_DOMAIN_ENTITIES
  CMP_API_CORE -->|depende| CMP_HTTP_MIDDLEWARE
  CMP_API_CORE -->|depende| CMP_INFRA_CORE
  CMP_API_CORE -->|depende| CMP_INGESTION
  CMP_API_CORE -->|depende| CMP_MATCHING_ENGINE
  CMP_API_CORE -->|depende| CMP_PERSISTENCE
  CMP_API_CORE -->|depende| CMP_RECONCILIATION_JOBS
  CMP_API_CORE -->|depende| CMP_RECONCILIATION_USECASES
  CMP_API_CORE -->|depende| CMP_SECURITY
  CMP_API_CORE -->|depende| CMP_USER_PERSISTENCE
  CMP_AUTH_API["CMP-AUTH-API<br/>auth.py"]
  CMP_AUTH_API -->|realiza| CAP_ACCESS_CONTROL
  CMP_AUTH_API -->|depende| CMP_API_CORE
  CMP_AUTH_API -->|depende| CMP_SECURITY
  CMP_AUTH_API -->|depende| CMP_USER_PERSISTENCE
  CMP_AUTH_API -.->|testa| TEST_workspace_target_tests_integration_test_auth_endpoints_py
  CMP_AUTH_API -.->|testa| TEST_workspace_target_tests_integration_test_protected_endpoints_py
  CMP_BANK_OFX["CMP-BANK-OFX<br/>__init__.py"]
  CMP_BANK_OFX -->|realiza| CAP_RECONCILIATION
  CMP_BANK_OFX -->|depende| CMP_INFRA_CORE
  CMP_BANK_OFX -.->|testa| TEST_workspace_target_tests_unit_infrastructure_test_ofx_parser_py
  CMP_CASH_FLOW["CMP-CASH-FLOW<br/>cash_flow.py"]
  CMP_CASH_FLOW -->|realiza| CAP_CASH_FLOW
  CMP_CASH_FLOW -->|depende| CMP_API_CORE
  CMP_CASH_FLOW -->|depende| CMP_DOMAIN_ENTITIES
  CMP_CASH_FLOW -->|depende| CMP_DOMAIN_PORTS
  CMP_CASH_FLOW -->|depende| CMP_PERSISTENCE
  CMP_CASH_FLOW -->|depende| CMP_RECONCILIATION_USECASES
  CMP_CASH_FLOW -.->|implementa| REQ_019
  CMP_CIELO_CONCILIATOR["CMP-CIELO-CONCILIATOR<br/>__init__.py"]
  CMP_CIELO_CONCILIATOR -->|realiza| CAP_ACQUIRER_INTEGRATION
  CMP_CIELO_CONCILIATOR -->|depende| CMP_ACQUIRER_ADAPTERS
  CMP_CIELO_CONCILIATOR -->|depende| CMP_DOMAIN_ENTITIES
  CMP_CIELO_CONCILIATOR -->|depende| CMP_PERSISTENCE
  CMP_CIELO_CONCILIATOR -->|depende| CMP_RECONCILIATION_USECASES
  CMP_CIELO_CONCILIATOR -.->|implementa| REQ_001
  CMP_CIELO_CONCILIATOR -.->|testa| TEST_workspace_target_tests_integration_test_cielo_integration_py
  CMP_CIELO_CONCILIATOR -.->|testa| TEST_workspace_target_tests_unit_use_cases_test_import_cielo_report_py
  CMP_DASHBOARD_API["CMP-DASHBOARD-API<br/>notifications.py"]
  CMP_DASHBOARD_API -->|realiza| CAP_DASHBOARD_NOTIFICATIONS
  CMP_DASHBOARD_API -->|depende| CMP_API_CORE
  CMP_DASHBOARD_API -->|depende| CMP_DOMAIN_ENTITIES
  CMP_DASHBOARD_API -->|depende| CMP_PERSISTENCE
  CMP_DASHBOARD_API -->|depende| CMP_REPORTING
  CMP_DASHBOARD_API -->|depende| CMP_SALES
  CMP_DASHBOARD_API -->|depende| CMP_TRANSACTIONS
  CMP_DASHBOARD_API -.->|implementa| REQ_015
  CMP_DASHBOARD_API -.->|testa| TEST_workspace_target_tests_unit_test_stats_dashboard_response_py
  CMP_DECISION_TABLE["CMP-DECISION-TABLE<br/>decision_table.py"]
  CMP_DECISION_TABLE -->|realiza| CAP_RECONCILIATION
  CMP_DECISION_TABLE -.->|implementa| REQ_007
  CMP_DIVERGENCE_API["CMP-DIVERGENCE-API<br/>alerts.py"]
  CMP_DIVERGENCE_API -->|realiza| CAP_ANOMALY_DETECTION
  CMP_DIVERGENCE_API -->|depende| CMP_ALERTS
  CMP_DIVERGENCE_API -->|depende| CMP_API_CORE
  CMP_DIVERGENCE_API -->|depende| CMP_DOMAIN_ENTITIES
  CMP_DIVERGENCE_API -->|depende| CMP_PERSISTENCE
  CMP_DIVERGENCE_API -.->|implementa| REQ_011
  CMP_DIVERGENCE_API -.->|implementa| REQ_012
  CMP_DIVERGENCE_API -.->|implementa| REQ_013
  CMP_DIVERGENCE_API -.->|implementa| REQ_014
  CMP_DOMAIN_ENTITIES["CMP-DOMAIN-ENTITIES<br/>__init__.py"]
  CMP_DOMAIN_ENTITIES -->|realiza| CAP_PLATFORM
  CMP_DOMAIN_ENTITIES -->|depende| CMP_DOMAIN_VALUES
  CMP_DOMAIN_PORTS["CMP-DOMAIN-PORTS<br/>__init__.py"]
  CMP_DOMAIN_PORTS -->|realiza| CAP_PLATFORM
  CMP_DOMAIN_PORTS -->|depende| CMP_DOMAIN_ENTITIES
  CMP_DOMAIN_VALUES["CMP-DOMAIN-VALUES<br/>__init__.py"]
  CMP_DOMAIN_VALUES -->|realiza| CAP_PLATFORM
  CMP_HTTP_MIDDLEWARE["CMP-HTTP-MIDDLEWARE<br/>__init__.py"]
  CMP_HTTP_MIDDLEWARE -->|realiza| CAP_ACCESS_CONTROL
  CMP_HTTP_MIDDLEWARE -->|depende| CMP_API_CORE
  CMP_HTTP_MIDDLEWARE -->|depende| CMP_PERSISTENCE
  CMP_HTTP_MIDDLEWARE -->|depende| CMP_SECURITY
  CMP_HTTP_MIDDLEWARE -.->|testa| TEST_workspace_target_tests_unit_test_rbac_and_audit_middleware_py
  CMP_INFRA_CORE["CMP-INFRA-CORE<br/>__init__.py"]
  CMP_INFRA_CORE -->|realiza| CAP_PLATFORM
  CMP_INGESTION["CMP-INGESTION<br/>auto_import_service.py"]
  CMP_INGESTION -->|realiza| CAP_ACQUIRER_INTEGRATION
  CMP_INGESTION -->|depende| CMP_ACQUIRER_ADAPTERS
  CMP_INGESTION -->|depende| CMP_ALERTS
  CMP_INGESTION -->|depende| CMP_DOMAIN_ENTITIES
  CMP_INGESTION -->|depende| CMP_DOMAIN_PORTS
  CMP_INGESTION -->|depende| CMP_DOMAIN_VALUES
  CMP_INGESTION -->|depende| CMP_INFRA_CORE
  CMP_INGESTION -->|depende| CMP_PERSISTENCE
  CMP_INGESTION -.->|implementa| REQ_001
  CMP_INGESTION -.->|implementa| REQ_006
  CMP_INGESTION -.->|testa| TEST_workspace_target_tests_integration_test_rede_edi_upload_py
  CMP_INGESTION -.->|testa| TEST_workspace_target_tests_unit_test_auto_import_alert_py
  CMP_INGESTION_API["CMP-INGESTION-API<br/>acquirers.py"]
  CMP_INGESTION_API -->|realiza| CAP_ACQUIRER_INTEGRATION
  CMP_INGESTION_API -->|depende| CMP_ACQUIRER_ADAPTERS
  CMP_INGESTION_API -->|depende| CMP_API_CORE
  CMP_INGESTION_API -->|depende| CMP_CIELO_CONCILIATOR
  CMP_INGESTION_API -->|depende| CMP_DOMAIN_ENTITIES
  CMP_INGESTION_API -->|depende| CMP_PERSISTENCE
  CMP_INGESTION_API -.->|implementa| REQ_005
  CMP_MATCHING_ENGINE["CMP-MATCHING-ENGINE<br/>__init__.py"]
  CMP_MATCHING_ENGINE -->|realiza| CAP_RECONCILIATION
  CMP_MATCHING_ENGINE -->|depende| CMP_DOMAIN_ENTITIES
  CMP_MATCHING_ENGINE -->|depende| CMP_DOMAIN_VALUES
  CMP_MATCHING_ENGINE -.->|testa| TEST_workspace_target_tests_unit_test_exact_matcher_py
  CMP_MATCHING_ENGINE -.->|testa| TEST_workspace_target_tests_unit_test_fuzzy_matcher_py
  CMP_NOTIFICATION["CMP-NOTIFICATION<br/>__init__.py"]
  CMP_NOTIFICATION -->|realiza| CAP_DASHBOARD_NOTIFICATIONS
  CMP_NOTIFICATION -->|depende| CMP_DOMAIN_ENTITIES
  CMP_NOTIFICATION -->|depende| CMP_DOMAIN_PORTS
  CMP_NOTIFICATION -->|depende| CMP_INFRA_CORE
  CMP_NOTIFICATION -.->|implementa| REQ_017
  CMP_PERSISTENCE["CMP-PERSISTENCE<br/>__init__.py"]
  CMP_PERSISTENCE -->|realiza| CAP_PLATFORM
  CMP_PERSISTENCE -->|depende| CMP_DOMAIN_ENTITIES
  CMP_PERSISTENCE -->|depende| CMP_DOMAIN_PORTS
  CMP_PERSISTENCE -->|depende| CMP_DOMAIN_VALUES
  CMP_PERSISTENCE -.->|testa| TEST_workspace_target_tests_integration_test_postgresql_repositories_py
  CMP_RECONCILIATION_API["CMP-RECONCILIATION-API<br/>bank_reconciliation.py"]
  CMP_RECONCILIATION_API -->|realiza| CAP_RECONCILIATION
  CMP_RECONCILIATION_API -->|depende| CMP_API_CORE
  CMP_RECONCILIATION_API -->|depende| CMP_DECISION_TABLE
  CMP_RECONCILIATION_API -->|depende| CMP_DOMAIN_ENTITIES
  CMP_RECONCILIATION_API -->|depende| CMP_PERSISTENCE
  CMP_RECONCILIATION_API -->|depende| CMP_RECONCILIATION_JOBS
  CMP_RECONCILIATION_API -->|depende| CMP_RECONCILIATION_USECASES
  CMP_RECONCILIATION_API -.->|implementa| REQ_007
  CMP_RECONCILIATION_API -.->|implementa| REQ_008
  CMP_RECONCILIATION_JOBS["CMP-RECONCILIATION-JOBS<br/>reconciliation_job_service.py"]
  CMP_RECONCILIATION_JOBS -->|realiza| CAP_RECONCILIATION
  CMP_RECONCILIATION_JOBS -->|depende| CMP_PERSISTENCE
  CMP_RECONCILIATION_JOBS -.->|implementa| REQ_007
  CMP_RECONCILIATION_USECASES["CMP-RECONCILIATION-USECASES<br/>__init__.py"]
  CMP_RECONCILIATION_USECASES -->|realiza| CAP_RECONCILIATION
  CMP_RECONCILIATION_USECASES -->|depende| CMP_BANK_OFX
  CMP_RECONCILIATION_USECASES -->|depende| CMP_DECISION_TABLE
  CMP_RECONCILIATION_USECASES -->|depende| CMP_DOMAIN_ENTITIES
  CMP_RECONCILIATION_USECASES -->|depende| CMP_DOMAIN_PORTS
  CMP_RECONCILIATION_USECASES -->|depende| CMP_MATCHING_ENGINE
  CMP_RECONCILIATION_USECASES -->|depende| CMP_PERSISTENCE
  CMP_RECONCILIATION_USECASES -.->|implementa| REQ_007
  CMP_RECONCILIATION_USECASES -.->|testa| TEST_workspace_target_tests_integration_test_reconciliation_flow_py
  CMP_RECONCILIATION_USECASES -.->|testa| TEST_workspace_target_tests_unit_test_auto_bank_reconciliation_py
  CMP_RECONCILIATION_USECASES -.->|testa| TEST_workspace_target_tests_unit_use_cases_test_reconcile_bank_statement_py
  CMP_REPORTING["CMP-REPORTING<br/>export_service.py"]
  CMP_REPORTING -->|realiza| CAP_DASHBOARD_NOTIFICATIONS
  CMP_REPORTING -->|depende| CMP_DOMAIN_ENTITIES
  CMP_REPORTING -->|depende| CMP_PERSISTENCE
  CMP_REPORTING -.->|testa| TEST_workspace_target_tests_unit_test_export_service_py
  CMP_SALES["CMP-SALES<br/>sales_service.py"]
  CMP_SALES -->|realiza| CAP_DASHBOARD_NOTIFICATIONS
  CMP_SALES -->|depende| CMP_DOMAIN_ENTITIES
  CMP_SALES -->|depende| CMP_DOMAIN_VALUES
  CMP_SALES -->|depende| CMP_PERSISTENCE
  CMP_SECURITY["CMP-SECURITY<br/>__init__.py"]
  CMP_SECURITY -->|realiza| CAP_ACCESS_CONTROL
  CMP_SECURITY -->|depende| CMP_INFRA_CORE
  CMP_SECURITY -.->|testa| TEST_workspace_target_tests_unit_security_test_jwt_handler_py
  CMP_SECURITY -.->|testa| TEST_workspace_target_tests_unit_security_test_password_hasher_py
  CMP_SECURITY -.->|testa| TEST_workspace_target_tests_unit_security_test_rate_limiter_py
  CMP_SECURITY -.->|testa| TEST_workspace_target_tests_unit_test_security_hardening_py
  CMP_TRANSACTIONS["CMP-TRANSACTIONS<br/>transaction_service.py"]
  CMP_TRANSACTIONS -->|realiza| CAP_DASHBOARD_NOTIFICATIONS
  CMP_TRANSACTIONS -->|depende| CMP_ACQUIRER_PARSERS
  CMP_TRANSACTIONS -->|depende| CMP_DOMAIN_ENTITIES
  CMP_TRANSACTIONS -->|depende| CMP_DOMAIN_VALUES
  CMP_TRANSACTIONS -->|depende| CMP_PERSISTENCE
  CMP_UI_API_CLIENT["CMP-UI-API-CLIENT<br/>auth.api.ts"]
  CMP_UI_API_CLIENT -->|realiza| CAP_DASHBOARD_NOTIFICATIONS
  CMP_UI_API_CLIENT -.->|implementa| REQ_015
  CMP_UI_COMPONENTS["CMP-UI-COMPONENTS<br/>AccuracyTrendChart.test.tsx"]
  CMP_UI_COMPONENTS -->|realiza| CAP_DASHBOARD_NOTIFICATIONS
  CMP_UI_COMPONENTS -.->|implementa| REQ_016
  CMP_UI_COMPONENTS -.->|testa| TEST_workspace_target_conciliaai_frontend_tests_unit_components_DataTable_test_tsx
  CMP_UI_HOOKS["CMP-UI-HOOKS<br/>useExport.test.tsx"]
  CMP_UI_HOOKS -->|realiza| CAP_DASHBOARD_NOTIFICATIONS
  CMP_UI_HOOKS -.->|implementa| REQ_015
  CMP_UI_HOOKS -.->|testa| TEST_workspace_target_conciliaai_frontend_tests_unit_hooks_useSales_test_tsx
  CMP_UI_HOOKS -.->|testa| TEST_workspace_target_conciliaai_frontend_tests_unit_hooks_useTransactions_test_tsx
  CMP_UI_PAGES_ACCESS["CMP-UI-PAGES-ACCESS<br/>ProtectedRoute.tsx"]
  CMP_UI_PAGES_ACCESS -->|realiza| CAP_ACCESS_CONTROL
  CMP_UI_PAGES_CASH_FLOW["CMP-UI-PAGES-CASH-FLOW<br/>CashFlowDashboard.tsx"]
  CMP_UI_PAGES_CASH_FLOW -->|realiza| CAP_CASH_FLOW
  CMP_UI_PAGES_CASH_FLOW -.->|implementa| REQ_019
  CMP_UI_PAGES_DASHBOARD["CMP-UI-PAGES-DASHBOARD<br/>Dashboard.tsx"]
  CMP_UI_PAGES_DASHBOARD -->|realiza| CAP_DASHBOARD_NOTIFICATIONS
  CMP_UI_PAGES_DASHBOARD -.->|implementa| REQ_015
  CMP_UI_PAGES_DIVERGENCES["CMP-UI-PAGES-DIVERGENCES<br/>AlertsPage.tsx"]
  CMP_UI_PAGES_DIVERGENCES -->|realiza| CAP_ANOMALY_DETECTION
  CMP_UI_PAGES_DIVERGENCES -.->|implementa| REQ_012
  CMP_UI_PAGES_RECONCILIATION["CMP-UI-PAGES-RECONCILIATION<br/>BankReconciliationUpload.tsx"]
  CMP_UI_PAGES_RECONCILIATION -->|realiza| CAP_RECONCILIATION
  CMP_UI_PAGES_RECONCILIATION -.->|implementa| REQ_007
  CMP_UI_SHELL["CMP-UI-SHELL<br/>App.tsx"]
  CMP_UI_SHELL -->|realiza| CAP_DASHBOARD_NOTIFICATIONS
  CMP_UI_SHELL -->|depende| CMP_UI_COMPONENTS
  CMP_UI_SHELL -->|depende| CMP_UI_PAGES_ACCESS
  CMP_UI_SHELL -->|depende| CMP_UI_PAGES_DASHBOARD
  CMP_UI_SHELL -->|depende| CMP_UI_PAGES_DIVERGENCES
  CMP_UI_SHELL -->|depende| CMP_UI_PAGES_RECONCILIATION
  CMP_UI_SHELL -.->|testa| TEST_workspace_target_conciliaai_frontend_tests_unit_utils_formatters_test_ts
  CMP_UI_SHELL -.->|testa| TEST_workspace_target_conciliaai_frontend_tests_unit_utils_validators_test_ts
  CMP_USER_PERSISTENCE["CMP-USER-PERSISTENCE<br/>__init__.py"]
  CMP_USER_PERSISTENCE -->|realiza| CAP_ACCESS_CONTROL
  CMP_USER_PERSISTENCE -->|depende| CMP_DOMAIN_ENTITIES
  CMP_USER_PERSISTENCE -->|depende| CMP_DOMAIN_PORTS
  CMP_USER_PERSISTENCE -->|depende| CMP_INFRA_CORE
  CMP_USER_PERSISTENCE -->|depende| CMP_PERSISTENCE
  IFC_ACQUIRER_REGISTRY(["IFC-ACQUIRER-REGISTRY<br/>Registro plugável de adquirentes"])
  CMP_ACQUIRER_ADAPTERS -.->|provê| IFC_ACQUIRER_REGISTRY
  IFC_ACQUIRER_REGISTRY -.->|consome| CMP_INGESTION
  IFC_MATCHING_STRATEGY(["IFC-MATCHING-STRATEGY<br/>Porta de estratégia de conciliação"])
  CMP_MATCHING_ENGINE -.->|provê| IFC_MATCHING_STRATEGY
  IFC_MATCHING_STRATEGY -.->|consome| CMP_RECONCILIATION_USECASES
  IFC_RECONCILIATION_POLICY(["IFC-RECONCILIATION-POLICY<br/>Tabela de decisão da política de conciliação"])
  CMP_DECISION_TABLE -.->|provê| IFC_RECONCILIATION_POLICY
  IFC_RECONCILIATION_POLICY -.->|consome| CMP_RECONCILIATION_USECASES
  IFC_TRANSACTION_REPOSITORY(["IFC-TRANSACTION-REPOSITORY<br/>Porta de repositório de transações de adquirente"])
  CMP_DOMAIN_PORTS -.->|provê| IFC_TRANSACTION_REPOSITORY
  IFC_TRANSACTION_REPOSITORY -.->|consome| CMP_PERSISTENCE
  RULE_MDR_001["RULE-MDR-001"]
  CAP_ACQUIRER_INTEGRATION -->|regra| RULE_MDR_001
  RULE_MDR_002["RULE-MDR-002"]
  CAP_ACQUIRER_INTEGRATION -->|regra| RULE_MDR_002
  RULE_MDR_003["RULE-MDR-003"]
  CAP_ACQUIRER_INTEGRATION -->|regra| RULE_MDR_003
  RULE_MDR_004["RULE-MDR-004"]
  CAP_ACQUIRER_INTEGRATION -->|regra| RULE_MDR_004
  RULE_MDR_005["RULE-MDR-005"]
  CAP_ACQUIRER_INTEGRATION -->|regra| RULE_MDR_005
  RULE_ANOMALY_001["RULE-ANOMALY-001"]
  CAP_ANOMALY_DETECTION -->|regra| RULE_ANOMALY_001
  RULE_ANOMALY_001 -.->|verifica| TEST_workspace_target_tests_unit_test_anomaly_detection_service_py
  RULE_ANOMALY_002["RULE-ANOMALY-002"]
  CAP_ANOMALY_DETECTION -->|regra| RULE_ANOMALY_002
  RULE_ANOMALY_003["RULE-ANOMALY-003"]
  CAP_ANOMALY_DETECTION -->|regra| RULE_ANOMALY_003
  RULE_ANOMALY_004["RULE-ANOMALY-004"]
  CAP_ANOMALY_DETECTION -->|regra| RULE_ANOMALY_004
  RULE_ANOMALY_005["RULE-ANOMALY-005"]
  CAP_ANOMALY_DETECTION -->|regra| RULE_ANOMALY_005
  RULE_CHARGEBACK_001["RULE-CHARGEBACK-001"]
  CAP_ANOMALY_DETECTION -->|regra| RULE_CHARGEBACK_001
  RULE_CHARGEBACK_002["RULE-CHARGEBACK-002"]
  CAP_ANOMALY_DETECTION -->|regra| RULE_CHARGEBACK_002
  RULE_MATCH_001["RULE-MATCH-001"]
  CAP_RECONCILIATION -->|regra| RULE_MATCH_001
  RULE_MATCH_001 -.->|verifica| TEST_workspace_target_tests_unit_test_exact_matcher_py
  RULE_MATCH_002["RULE-MATCH-002"]
  CAP_RECONCILIATION -->|regra| RULE_MATCH_002
  RULE_MATCH_002 -.->|verifica| TEST_workspace_target_tests_unit_test_fuzzy_matcher_py
  RULE_MATCH_003["RULE-MATCH-003"]
  CAP_RECONCILIATION -->|regra| RULE_MATCH_003
  RULE_MATCH_003 -.->|verifica| TEST_workspace_target_tests_unit_test_fuzzy_matcher_py
  RULE_MATCH_004["RULE-MATCH-004"]
  CAP_RECONCILIATION -->|regra| RULE_MATCH_004
  RULE_MATCH_005["RULE-MATCH-005"]
  CAP_RECONCILIATION -->|regra| RULE_MATCH_005
  UI_ALERTS["UI-ALERTS"]
  UI_ALERTS -->|experiência| CAP_ANOMALY_DETECTION
  UI_ALERTS -.->|satisfaz| REQ_011
  UI_BANK_RECONCILIATION["UI-BANK-RECONCILIATION"]
  UI_BANK_RECONCILIATION -->|experiência| CAP_RECONCILIATION
  UI_CASH_FLOW["UI-CASH-FLOW"]
  UI_CASH_FLOW -->|experiência| CAP_CASH_FLOW
  UI_CASH_FLOW -.->|satisfaz| REQ_019
  UI_DASHBOARD["UI-DASHBOARD"]
  UI_DASHBOARD -->|experiência| CAP_DASHBOARD_NOTIFICATIONS
  UI_DASHBOARD -.->|satisfaz| REQ_015
  UI_DIVERGENCES["UI-DIVERGENCES"]
  UI_DIVERGENCES -->|experiência| CAP_ANOMALY_DETECTION
  UI_DIVERGENCES -.->|satisfaz| REQ_012
  UI_LOGIN["UI-LOGIN"]
  UI_LOGIN -->|experiência| CAP_ACCESS_CONTROL
  UI_NOTIFICATIONS["UI-NOTIFICATIONS"]
  UI_NOTIFICATIONS -->|experiência| CAP_DASHBOARD_NOTIFICATIONS
  UI_NOTIFICATIONS -.->|satisfaz| REQ_017
  UI_RECONCILIATION["UI-RECONCILIATION"]
  UI_RECONCILIATION -->|experiência| CAP_RECONCILIATION
  UI_RECONCILIATION -.->|satisfaz| REQ_007
  UI_REPORTS["UI-REPORTS"]
  UI_REPORTS -->|experiência| CAP_DASHBOARD_NOTIFICATIONS
  UI_SALES["UI-SALES"]
  UI_SALES -->|experiência| CAP_DASHBOARD_NOTIFICATIONS
  UI_SETTINGS["UI-SETTINGS"]
  UI_SETTINGS -->|experiência| CAP_ACCESS_CONTROL
  UI_TRANSACTIONS["UI-TRANSACTIONS"]
  UI_TRANSACTIONS -->|experiência| CAP_DASHBOARD_NOTIFICATIONS
  MET_AUTO_APPROVAL[["MET-AUTO-APPROVAL"]]
  REQ_001["REQ-001<br/>in_progress"]
  REQ_001 -->|requisito| CAP_ACQUIRER_INTEGRATION
  REQ_001 -.->|regido por| RULE_MDR_001
  REQ_001 -.->|regido por| RULE_MDR_002
  REQ_001 -.->|regido por| RULE_MDR_003
  REQ_002["REQ-002<br/>in_progress"]
  REQ_002 -->|requisito| CAP_ACQUIRER_INTEGRATION
  REQ_003["REQ-003<br/>in_progress"]
  REQ_003 -->|requisito| CAP_ACQUIRER_INTEGRATION
  REQ_004["REQ-004<br/>proposed"]
  REQ_004 -->|requisito| CAP_ACQUIRER_INTEGRATION
  REQ_005["REQ-005<br/>in_progress"]
  REQ_005 -->|requisito| CAP_ACQUIRER_INTEGRATION
  REQ_006["REQ-006<br/>in_progress"]
  REQ_006 -->|requisito| CAP_ACQUIRER_INTEGRATION
  REQ_007["REQ-007<br/>in_progress"]
  REQ_007 -->|requisito| CAP_RECONCILIATION
  REQ_007 -.->|regido por| RULE_MATCH_001
  REQ_007 -.->|regido por| RULE_MATCH_002
  REQ_007 -.->|regido por| RULE_MATCH_003
  REQ_007 -.->|regido por| RULE_MATCH_004
  REQ_007 -.->|regido por| RULE_MATCH_005
  REQ_008["REQ-008<br/>in_progress"]
  REQ_008 -->|requisito| CAP_RECONCILIATION
  REQ_009["REQ-009<br/>proposed"]
  REQ_009 -->|requisito| CAP_RECONCILIATION
  REQ_010["REQ-010<br/>proposed"]
  REQ_010 -->|requisito| CAP_RECONCILIATION
  REQ_011["REQ-011<br/>in_progress"]
  REQ_011 -->|requisito| CAP_ANOMALY_DETECTION
  REQ_011 -.->|regido por| RULE_ANOMALY_001
  REQ_012["REQ-012<br/>in_progress"]
  REQ_012 -->|requisito| CAP_ANOMALY_DETECTION
  REQ_012 -.->|regido por| RULE_ANOMALY_002
  REQ_013["REQ-013<br/>in_progress"]
  REQ_013 -->|requisito| CAP_ANOMALY_DETECTION
  REQ_013 -.->|regido por| RULE_ANOMALY_003
  REQ_013 -.->|regido por| RULE_CHARGEBACK_001
  REQ_014["REQ-014<br/>in_progress"]
  REQ_014 -->|requisito| CAP_ANOMALY_DETECTION
  REQ_014 -.->|regido por| RULE_ANOMALY_004
  REQ_015["REQ-015<br/>in_progress"]
  REQ_015 -->|requisito| CAP_DASHBOARD_NOTIFICATIONS
  REQ_016["REQ-016<br/>in_progress"]
  REQ_016 -->|requisito| CAP_DASHBOARD_NOTIFICATIONS
  REQ_017["REQ-017<br/>in_progress"]
  REQ_017 -->|requisito| CAP_DASHBOARD_NOTIFICATIONS
  REQ_018["REQ-018<br/>proposed"]
  REQ_018 -->|requisito| CAP_DASHBOARD_NOTIFICATIONS
  REQ_019["REQ-019<br/>in_progress"]
  REQ_019 -->|requisito| CAP_CASH_FLOW
  REQ_020["REQ-020<br/>proposed"]
  REQ_020 -->|requisito| CAP_CASH_FLOW
  RISK_ALIGN_001["RISK-ALIGN-001"]
  RISK_CHANGE_001["RISK-CHANGE-001"]
  RISK_CONF_001["RISK-CONF-001"]
  RISK_CONF_002["RISK-CONF-002"]
  RISK_DEP_001["RISK-DEP-001"]
  RISK_DERIV_001["RISK-DERIV-001"]
  RISK_DERIV_002["RISK-DERIV-002"]
  RISK_INGEST_001["RISK-INGEST-001"]
  RISK_INGEST_002["RISK-INGEST-002"]
  RISK_META_001["RISK-META-001"]
  RISK_META_002["RISK-META-002"]
  RISK_ORIENT_001["RISK-ORIENT-001"]
  RISK_PRIV_001["RISK-PRIV-001"]
  RISK_PRIV_002["RISK-PRIV-002"]
  RISK_SEC_001["RISK-SEC-001"]
  RISK_STAGE_001["RISK-STAGE-001"]
  RISK_WEBQA_001["RISK-WEBQA-001"]
  ADR_001["ADR-001"]
  ADR_001 -->|mitiga| RISK_WEBQA_001
  ADR_002["ADR-002"]
  ADR_002 -->|mitiga| RISK_META_001
  ADR_003["ADR-003"]
  ADR_003 -->|mitiga| RISK_DEP_001
  ADR_004["ADR-004"]
  ADR_004 -->|mitiga| RISK_CHANGE_001
  ADR_005["ADR-005"]
  ADR_006["ADR-006"]
  ADR_006 -->|mitiga| RISK_CONF_001
  ADR_006 -->|mitiga| RISK_STAGE_001
  ADR_007["ADR-007"]
  ADR_007 -->|mitiga| RISK_PRIV_001
  ADR_007 -->|mitiga| RISK_PRIV_002
  ADR_008["ADR-008"]
  ADR_008 -->|mitiga| RISK_DERIV_001
  ADR_008 -->|mitiga| RISK_DERIV_002
  ADR_009["ADR-009"]
  ADR_009 -->|mitiga| RISK_DERIV_002
  ADR_009 -->|mitiga| RISK_INGEST_001
  ADR_010["ADR-010"]
  ADR_010 -->|mitiga| RISK_INGEST_001
  ADR_010 -->|mitiga| RISK_INGEST_002
  ADR_011["ADR-011"]
  ADR_011 -->|mitiga| RISK_ALIGN_001
  ADR_012["ADR-012"]
  ADR_012 -->|mitiga| RISK_CONF_002
  ADR_012 -->|mitiga| RISK_DERIV_001
  ADR_013["ADR-013"]
  ADR_013 -->|mitiga| RISK_DEP_001
  ADR_013 -->|mitiga| RISK_SEC_001
  ADR_014["ADR-014"]
  ADR_014 -->|mitiga| RISK_META_001
  ADR_014 -->|mitiga| RISK_ORIENT_001
  classDef project fill:#1f2937,stroke:#111827,color:#fff;
  class PROJ_danzeroum_project_reconcilia project;
  classDef cap fill:#2563eb,stroke:#1e40af,color:#fff;
  class CAP_ACCESS_CONTROL,CAP_ACQUIRER_INTEGRATION,CAP_ANOMALY_DETECTION,CAP_CASH_FLOW,CAP_DASHBOARD_NOTIFICATIONS,CAP_PLATFORM,CAP_RECONCILIATION cap;
  classDef cmp fill:#0891b2,stroke:#0e7490,color:#fff;
  class CMP_ACQUIRER_ADAPTERS,CMP_ACQUIRER_PARSERS,CMP_ALERTS,CMP_ANOMALY,CMP_API_CORE,CMP_AUTH_API,CMP_BANK_OFX,CMP_CASH_FLOW,CMP_CIELO_CONCILIATOR,CMP_DASHBOARD_API,CMP_DECISION_TABLE,CMP_DIVERGENCE_API,CMP_DOMAIN_ENTITIES,CMP_DOMAIN_PORTS,CMP_DOMAIN_VALUES,CMP_HTTP_MIDDLEWARE,CMP_INFRA_CORE,CMP_INGESTION,CMP_INGESTION_API,CMP_MATCHING_ENGINE,CMP_NOTIFICATION,CMP_PERSISTENCE,CMP_RECONCILIATION_API,CMP_RECONCILIATION_JOBS,CMP_RECONCILIATION_USECASES,CMP_REPORTING,CMP_SALES,CMP_SECURITY,CMP_TRANSACTIONS,CMP_UI_API_CLIENT,CMP_UI_COMPONENTS,CMP_UI_HOOKS,CMP_UI_PAGES_ACCESS,CMP_UI_PAGES_CASH_FLOW,CMP_UI_PAGES_DASHBOARD,CMP_UI_PAGES_DIVERGENCES,CMP_UI_PAGES_RECONCILIATION,CMP_UI_SHELL,CMP_USER_PERSISTENCE cmp;
  classDef ifc fill:#7c3aed,stroke:#5b21b6,color:#fff;
  class IFC_ACQUIRER_REGISTRY,IFC_MATCHING_STRATEGY,IFC_RECONCILIATION_POLICY,IFC_TRANSACTION_REPOSITORY ifc;
  classDef rule fill:#16a34a,stroke:#15803d,color:#fff;
  class RULE_MDR_001,RULE_MDR_002,RULE_MDR_003,RULE_MDR_004,RULE_MDR_005,RULE_ANOMALY_001,RULE_ANOMALY_002,RULE_ANOMALY_003,RULE_ANOMALY_004,RULE_ANOMALY_005,RULE_CHARGEBACK_001,RULE_CHARGEBACK_002,RULE_MATCH_001,RULE_MATCH_002,RULE_MATCH_003,RULE_MATCH_004,RULE_MATCH_005 rule;
  classDef ui fill:#db2777,stroke:#9d174d,color:#fff;
  class UI_ALERTS,UI_BANK_RECONCILIATION,UI_CASH_FLOW,UI_DASHBOARD,UI_DIVERGENCES,UI_LOGIN,UI_NOTIFICATIONS,UI_RECONCILIATION,UI_REPORTS,UI_SALES,UI_SETTINGS,UI_TRANSACTIONS ui;
  classDef req fill:#0d9488,stroke:#0f766e,color:#fff;
  class REQ_001,REQ_002,REQ_003,REQ_004,REQ_005,REQ_006,REQ_007,REQ_008,REQ_009,REQ_010,REQ_011,REQ_012,REQ_013,REQ_014,REQ_015,REQ_016,REQ_017,REQ_018,REQ_019,REQ_020 req;
  classDef met fill:#ea580c,stroke:#c2410c,color:#fff;
  class MET_AUTO_APPROVAL met;
  classDef test fill:#57534e,stroke:#44403c,color:#fff;
  class TEST_workspace_target_conciliaai_frontend_tests_unit_components_DataTable_test_tsx,TEST_workspace_target_conciliaai_frontend_tests_unit_hooks_useSales_test_tsx,TEST_workspace_target_conciliaai_frontend_tests_unit_hooks_useTransactions_test_tsx,TEST_workspace_target_conciliaai_frontend_tests_unit_utils_formatters_test_ts,TEST_workspace_target_conciliaai_frontend_tests_unit_utils_validators_test_ts,TEST_workspace_target_tests_integration_test_acquirer_clients_py,TEST_workspace_target_tests_integration_test_auth_endpoints_py,TEST_workspace_target_tests_integration_test_cielo_integration_py,TEST_workspace_target_tests_integration_test_postgresql_repositories_py,TEST_workspace_target_tests_integration_test_protected_endpoints_py,TEST_workspace_target_tests_integration_test_reconciliation_flow_py,TEST_workspace_target_tests_integration_test_rede_edi_upload_py,TEST_workspace_target_tests_unit_infrastructure_test_cielo_conciliator_client_py,TEST_workspace_target_tests_unit_infrastructure_test_ofx_parser_py,TEST_workspace_target_tests_unit_infrastructure_test_rede_edi_parser_py,TEST_workspace_target_tests_unit_parsers_test_rede_edi_parser_positional_py,TEST_workspace_target_tests_unit_security_test_jwt_handler_py,TEST_workspace_target_tests_unit_security_test_password_hasher_py,TEST_workspace_target_tests_unit_security_test_rate_limiter_py,TEST_workspace_target_tests_unit_test_anomaly_detection_service_py,TEST_workspace_target_tests_unit_test_auto_bank_reconciliation_py,TEST_workspace_target_tests_unit_test_auto_import_alert_py,TEST_workspace_target_tests_unit_test_exact_matcher_py,TEST_workspace_target_tests_unit_test_export_service_py,TEST_workspace_target_tests_unit_test_fuzzy_matcher_py,TEST_workspace_target_tests_unit_test_rbac_and_audit_middleware_py,TEST_workspace_target_tests_unit_test_rede_api_client_py,TEST_workspace_target_tests_unit_test_security_hardening_py,TEST_workspace_target_tests_unit_test_stats_dashboard_response_py,TEST_workspace_target_tests_unit_use_cases_test_import_cielo_report_py,TEST_workspace_target_tests_unit_use_cases_test_reconcile_bank_statement_py test;
  classDef adr fill:#ca8a04,stroke:#a16207,color:#fff;
  class ADR_001,ADR_002,ADR_003,ADR_004,ADR_005,ADR_006,ADR_007,ADR_008,ADR_009,ADR_010,ADR_011,ADR_012,ADR_013,ADR_014 adr;
  classDef risk fill:#dc2626,stroke:#991b1b,color:#fff;
  class RISK_ALIGN_001,RISK_CHANGE_001,RISK_CONF_001,RISK_CONF_002,RISK_DEP_001,RISK_DERIV_001,RISK_DERIV_002,RISK_INGEST_001,RISK_INGEST_002,RISK_META_001,RISK_META_002,RISK_ORIENT_001,RISK_PRIV_001,RISK_PRIV_002,RISK_SEC_001,RISK_STAGE_001,RISK_WEBQA_001 risk;
```
