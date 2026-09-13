# Análise de Pipelines de CI/CD no GitHub

Análise de três repositórios reais que utilizam integração de pipelines (CI/CD) via GitHub Actions, destacando características, funcionalidades, gatilhos e histórico de execução.

---

## 1. freeCodeCamp/freeCodeCamp

**Link:** https://github.com/freeCodeCamp/freeCodeCamp/actions/runs/34620592130
**Workflow analisado:** `github-pr-guidelines.yml`

### Características
Pipeline leve e rápido, focado em governança de contribuições — não compila nem testa código, apenas valida a qualidade do processo de pull request.

### Funcionalidades
O pipeline executa 5 jobs encadeados:
- **No Commits on GitHub Web** — bloqueia commits feitos direto pela interface web
- **No PRs from Main Branch** — impede PRs abertos a partir da branch main do fork
- **Fix PR Title** — valida/corrige o título do PR
- **Check PR Template** — garante que o template de contribuição foi preenchido
- **Report** — consolida o resultado

### Gatilho
`pull_request_target` — gatilho mais sensível que roda com permissões do repositório base, mesmo em PRs vindos de forks (comum em projetos que precisam validar contribuições externas com segurança).

### Histórico
No exemplo analisado, a execução foi disparada pelo usuário *zxlinw* ao abrir o PR #69999 ("fix(curriculum): update test to allow 2px solid yellow" #4469), concluída com sucesso em apenas **33 segundos** — reforçando que é um pipeline de validação leve, não de build/teste pesado.

---

## 2. vercel/next.js

**Link:** https://github.com/vercel/next.js/actions/runs/34755131249
**Workflow analisado:** `build_and_deploy.yml`

### Características
Pipeline complexo e paralelizado, típico de um projeto de infraestrutura crítica (o compilador/framework Next.js), com uso intenso de matrizes de build.

### Funcionalidades
- **deploy-target / build** — build principal da aplicação
- **generate-native-matrix** — geração de matriz de builds nativos
- **build-wasm (web) / build-wasm (nodejs)** — testes WASM em dois ambientes
- **stable - x86_64-unknown-linux-gnu - node@20** — compilação nativa estável
- **Prepare preview tarball** — empacotamento de pré-visualização
- **Potentially publish release** — publicação condicional de release
- **report publish failure to slack** — notificação de falhas no Slack (integração externa)

### Gatilho
`pull_request`, no evento **synchronize** (disparado a cada novo commit no PR). O exemplo mostra o usuário *sokra* atualizando o PR #97789 na branch `codex/turbopack-wasm/wasm-t...`.

### Histórico
Execução concluída com sucesso em **7 minutos e 5 segundos**, gerando 7 artefatos — evidenciando um pipeline muito mais pesado que o do freeCodeCamp, coerente com o teste de um compilador em múltiplas plataformas.

---

## 3. apache/airflow

**Link:** https://github.com/apache/airflow/actions/runs/34749460305
**Workflow analisado:** `refresh-image-registry-cache.yml`

### Características
Pipeline de infraestrutura/manutenção (não valida PRs de contribuidores, mas mantém a própria esteira de CI), organizado em matrizes por arquitetura.

### Funcionalidades
- **Build info** — job inicial que alimenta as matrizes seguintes
- **Refresh cache linux/amd64** (matriz com 5 jobs)
- **Refresh cache linux/arm64** (matriz com 1 job)

Esses jobs atualizam o cache de imagens Docker usadas nos builds do Airflow, otimizando o tempo das próximas execuções de CI.

### Gatilho
`push` — disparado diretamente por push de commit, sem depender de pull request.

### Histórico
O exemplo mostra o mantenedor *potiuk* (committer frequente do projeto) fazendo push do commit `c320f96` na branch `v3-3-test`, com a execução concluída em **10 minutos e 26 segundos** — tempo condizente com a construção/atualização de múltiplas imagens de container.

---

## Comparativo final

| Projeto | Gatilho | Duração | Foco do pipeline |
|---|---|---|---|
| freeCodeCamp | `pull_request_target` | 33s | Governança/validação de PR |
| Next.js | `pull_request` (synchronize) | 7m 5s | Build e teste multiplataforma |
| Airflow | `push` | 10m 26s | Manutenção de infraestrutura de CI (cache de imagens) |

Os três projetos usam **GitHub Actions**, mas cada um emprega um gatilho e uma estratégia diferente conforme o objetivo do pipeline: validar contribuições (freeCodeCamp), testar um produto complexo (Next.js) ou manter a própria esteira de automação eficiente (Airflow).

---

## Links para consulta

- freeCodeCamp/freeCodeCamp: https://github.com/freeCodeCamp/freeCodeCamp/actions/runs/34620592130
- vercel/next.js: https://github.com/vercel/next.js/actions/runs/34755131249
- apache/airflow: https://github.com/apache/airflow/actions/runs/34749460305