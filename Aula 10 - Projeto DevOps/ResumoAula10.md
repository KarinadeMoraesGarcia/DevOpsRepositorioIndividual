# Resumo – Aula 10: Projeto DevOps

Resumo da aula do Prof. Me. Deivison S. Takatu (Fatec), que apresenta o **Projeto Final de DevOps**: objetivos, arquitetura, requisitos técnicos (Git/GitHub, testes, CI/CD, Docker, monitoramento, segurança), entregáveis e resultado esperado.

---

## 1. Visão Geral do Projeto Final

- Desenvolvimento de uma **aplicação web em grupo**
- **Integração dos conceitos e ferramentas** da disciplina
- **Automação** do desenvolvimento, testes e implantação
- **Colaboração, qualidade e melhoria contínua**

Link da atividade: https://github.com/deivisontakatu/aula-devops/tree/main/Atividade

### Objetivos
- Aplicar os conceitos de DevOps na prática
- Desenvolver uma aplicação web funcional e integrada
- Automatizar testes, integração e deploy
- Padronizar ambientes de desenvolvimento e execução
- Monitorar o funcionamento da aplicação

### Tema
- Tema e funcionalidades **definidos pelo grupo**
- Solução para um problema ou necessidade identificável
- Aplicação compatível com os requisitos técnicos da disciplina

---

## 2. Arquitetura da Aplicação

| Camada | Responsabilidade |
|---|---|
| Front-end | Interface com o usuário |
| Back-end | Regras de negócio e endpoints |
| Banco de dados | Persistência das informações |
| Middleware | Integração, autenticação ou validação, quando aplicável |

---

## 3. Requisitos Técnicos

### 3.1 Git e GitHub
- Repositório com código-fonte e documentação
- Branches para funcionalidades e correções
- Commits organizados e descritivos
- Pull Requests para integração de alterações
- Revisão de código por outros integrantes
- Relacionamento entre tarefas e alterações

### 3.2 Testes Automatizados

| Tipo | O que valida |
|---|---|
| Unitários | Funções, componentes e regras de negócio isoladamente |
| Integração | Comunicação entre componentes |
| E2E | Principais fluxos do usuário |
| Performance | Latência, volume e erros |

### 3.3 Integração Contínua (CI)
- Uso do **GitHub Actions** ou ferramenta autorizada
- Instalação das dependências
- Validação da estrutura do projeto
- Execução dos testes automatizados
- Build da aplicação, quando aplicável
- Verificações de qualidade

### 3.4 Docker e Padronização do Ambiente
- Dockerfile para o back-end
- Dockerfile para o front-end, quando aplicável
- Configuração de portas e variáveis de ambiente
- Organização dos serviços e dependências
- Instruções para construção e execução dos contêineres
- Demonstração da aplicação containerizada

### 3.5 Entrega Contínua e Deploy (CD)
- Construção automatizada das imagens Docker
- Implantação automatizada
- Verificação após o deploy
- Documentação do processo de implantação
- Identificação da versão publicada

### 3.6 Logs, Monitoramento e Observabilidade
- Registro de eventos importantes
- Registro de erros relevantes
- Verificação de disponibilidade
- Coleta de métricas operacionais
- Monitoramento do ambiente implantado ou de demonstração

### 3.7 Configuração e Segurança
- Separação entre código e configuração
- Uso de variáveis de ambiente
- Arquivo `.env.example` **sem credenciais reais**
- Proteção de senhas, tokens e chaves privadas
- Configuração adequada de permissões na pipeline
- Verificação de vulnerabilidades, quando viável

---

## 4. Entregáveis

| Entregável | Conteúdo |
|---|---|
| Repositório GitHub | Código, histórico, branches e Pull Requests |
| Testes | Testes automatizados e evidências de execução |
| Pipeline CI/CD | Verificações, build e deploy automatizados |
| Docker | Dockerfiles e configuração dos serviços |
| Documentação | README e instruções técnicas |
| Aplicação implantada | Endereço público ou implantação reproduzível |
| Apresentação técnica | Demonstração dos requisitos implementados |

---

## 5. Apresentação Técnica

Roteiro dos pontos a demonstrar:
1. Objetivo e funcionalidades da aplicação
2. Arquitetura e comunicação entre componentes
3. Organização do GitHub e fluxo de Pull Requests
4. Execução dos testes
5. Construção e execução dos contêineres
6. Processo de deploy

---

## 6. Resultado Esperado

- Aplicação web funcional e integrada
- Desenvolvimento colaborativo com Git e GitHub
- Testes automatizados executáveis
- Integração contínua configurada
- Ambiente padronizado com Docker
- Entrega e implantação automatizadas

---

## 7. Materiais de Apoio

- Projeto DevOps: https://github.com/deivisontakatu/projeto-devops
- Projeto Docker: https://github.com/deivisontakatu/projeto-docker
- Projeto Kubernetes: https://github.com/deivisontakatu/projeto-kubernetes
- DevOps com GitHub Actions e testes: https://github.com/deivisontakatu/projeto-devops-testes
- Variáveis de ambiente: https://github.com/deivisontakatu/projeto-variavel-ambiente

---

## Referências da aula

- HUMBLE, J.; PRIKLADNICKI, R. *Entrega Contínua: Como Entregar Software de Forma Rápida e Confiável*. São Paulo: Bookman, 2013.
- MUNIZ, A. et al. *Jornada DevOps*. São Paulo: Brasport, 2019.
- SATO, D. *DevOps na prática*. São Paulo: Casa do Código, 2014.
- SILVA, R. *Entrega contínua em Android*. São Paulo: Casa do Código, 2016.
- ARUNDEL, J.; DOMINGUS, J. *DevOps nativo de nuvem com Kubernetes*. São Paulo: Novatec, 2019.
- MORAES, G. *Caixa de Ferramentas DevOps*. São Paulo: Casa do Código, 2015.
- PIRES, A.; MILITÃO, J. *Integração Contínua com Jenkins*. São Paulo: Casa do Código, 2019.
- VITALINO, J. F. N.; CASTRO, M. A. N. *Descomplicando o Docker*. 2. ed. São Paulo: Brasport, 2018.
- SILVERMAN, R. E. *Git: guia prático*. São Paulo: Novatec, 2019.
- KIM, G.; HUMBLE, J.; DEBOIS, P.; WILLIS, J. *Manual de DevOps*. São Paulo: Alta Books, 2018.