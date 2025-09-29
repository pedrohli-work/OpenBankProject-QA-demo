<pre>
id: US-015
epic: OBP
title: "Pesquisar tarefas, projetos e usuários"
acs:
  - AC1: "Pesquisa retorna resultados relevantes"
  - AC2: "Resultados respeitam permissões do usuário"
  - AC3: "Resultados são paginados"
  - AC4: "Termos inválidos retornam 400"
tests:
  AC1:
    - "tests/unit/test_search_ranking.py::test_basic_relevance_ranking"
    - "tests/integration/test_search_api.py::test_query_returns_expected_entities"
    - GAP: "Avaliação de relevância com sinônimos/typos (fuzzy) e boost por campo (P2)"
  AC2:
    - "tests/integration/test_search_permissions.py::test_results_scoped_by_user_permissions"
    - "tests/e2e/test_search_roles.py::test_cross_project_isolation"
    - GAP: "Teste de regressão para vazamento em filtros compostos (P1)"
  AC3:
    - "tests/integration/test_search_api.py::test_pagination_consistent_total_and_next_token"
    - "tests/e2e/test_search_pagination.py::test_page_navigation_stable_ordering"
  AC4:
    - "tests/integration/test_search_api.py::test_invalid_terms_return_400"
    - "tests/unit/test_query_validation.py::test_reject_oversized_or_malicious_queries"
summary:
  total_acs: 4
  covered: 3
  gaps: 2
  severity:
    critical: 0
    high: 1
    medium: 1
    low: 0
</pre>
