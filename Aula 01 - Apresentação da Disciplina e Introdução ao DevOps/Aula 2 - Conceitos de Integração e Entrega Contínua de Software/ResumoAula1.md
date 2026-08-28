# Aula 01: Apresentação da Disciplina e Introdução ao DevOps

**Professor:** Me. Deivison S. Takatu  
**Instituição:** FATEC (Faculdade de Tecnologia)  

---

## 1. Apresentação do Professor e Dinâmica Inicial
* **Perfil Acadêmico e Profissional:** Mestre em Ciência da Computação (2021), pós-graduando em Inteligência Artificial, Gerente de Projetos e Professor Universitário. Possui forte atuação em projetos de Programação Web, Educação Financeira e Gamificação.
* **Apresentação da Turma:** Dinâmica de integração para conhecer as experiências profissionais dos alunos, expectativas quanto ao curso e hobbies/passatempos.

---

## 2. Visão Geral da Disciplina
A disciplina conecta princípios de design visual a tecnologias web modernas para o desenvolvimento de interfaces digitais atraentes e funcionais. Além do desenvolvimento, foca-se na importância de construir e manter um **portfólio de projetos no GitHub**, demonstrando habilidades práticas e facilitando a entrada no mercado de trabalho (estágios e empregos).

---

## 3. Conceitos Fundamentais de DevOps e Versionamento

### 3.1 Controle de Versão
Consiste no registro de alterações em arquivos ao longo do tempo.
* **Benefícios:** Recuperação de versões anteriores, colaboração eficiente em equipe e uso de ramificações (*branches*) para desenvolvimento em paralelo.
* **Ferramentas populares:** GitHub, GitLab e Bitbucket.

### 3.2 Automação de Pipelines (CI/CD)
* **Pipeline:** Sequência automatizada de etapas desde a escrita do código até o deploy final (compilação, testes, análise e publicação).
* **Vantagens:** Redução de erros humanos, aumento da confiabilidade e entrega rápida de *feedbacks*.

### 3.3 Integração Contínua (CI - Continuous Integration)
* Prática de integrar o código ao repositório principal com frequência.
* Executa testes e compilação de forma automática a cada alteração.
* Identifica falhas precocemente e evita conflitos complexos de mesclagem de código.

### 3.4 Entrega Contínua (CD - Continuous Delivery)
* Garante que o software esteja sempre em estado pronto para publicação em produção após passar pela esteira de testes.
* Promove deploys rápidos, estáveis e padronizados, diminuindo riscos durante a implantação.

### 3.5 Qualidade de Software e Testes Automatizados
A validação contínua da qualidade reduz significativamente os custos de correção de erros.
* **Ferramentas automatizadas analisam:** Padronização do código, vulnerabilidades de segurança, complexidade técnica e cobertura de testes.
* **Principais Tipos de Testes:**
  * Testes Unitários
  * Testes de Integração
  * Testes Funcionais
  * Testes Ponta a Ponta (*End-to-End* / E2E)

### 3.6 Containers e Estratégias de Implantação
* **Containers (ex: Docker):** Empacotam a aplicação juntamente com suas dependências, garantindo que o software rode da mesma forma em ambientes de desenvolvimento, teste e produção.
* **Estratégias de Deploy:**
  * *Rolling Update*
  * *Blue-Green Deployment*
  * *Canary Release*
  *(Técnicas utilizadas para minimizar o tempo de inatividade da aplicação e facilitar o rollback em caso de falhas)*.

---

## 4. Critérios de Avaliação

A média do semestre é calculada pela seguinte fórmula:

$$\text{Média Final} = (P1 \times 0.25) + (P2 \times 0.25) + ((PJ + AT) \times 0.25)$$

* **P1:** Prova 1  
* **P2:** Prova 2  
* **PJ:** Projeto  
* **AT:** Atividades Práticas  

---

## 5. Atividades da Aula
1. **Formação de Grupos:** Definição de equipes de 3 a 5 integrantes para o acompanhamento e entrega de tarefas ao longo do semestre.
2. **Criação do Repositório GitHub:** Criação do diretório principal do grupo no GitHub para armazenar os projetos da disciplina e o resumo em Markdown (`.md`) da Aula 01.
3. **Avaliação Diagnóstica:** Preenchimento do formulário inicial de avaliação.

---

## 6. Referências Bibliográficas
* ARUNDEL, J.; DOMINGUS, J. *DevOps nativo de nuvem com Kubernetes*. Novatec, 2019.
* HUMBLE, J.; FARLEY, D. *Entrega Contínua: Como Entregar Software de Forma Rápida e Confiável*. Bookman, 2013.
* KIM, G. et al. *Manual de DEVOPS*. Alta Books, 2018.
* MORAES, G. *Caixa de Ferramentas DevOps*. Casa do Código, 2015.
* MUNIZ, A. et al. *Jornada Devops*. Brasport, 2019.
* PIRES, A.; MILITÃO, J. *Integração Contínua com Jenkins*. Casa do Código, 2019.
* SATO, D. *DevOps na prática*. Casa do Código, 2014.
* SILVA, R. *Entrega contínua em Android*. Casa do Código, 2016.
* SILVERMAN, R. E. *Git: guia prático*. Novatec, 2019.
* VITALINO, J. F. N.; CASTRO, M. A. N. *Descomplicando o Docker*. Brasport, 2018.