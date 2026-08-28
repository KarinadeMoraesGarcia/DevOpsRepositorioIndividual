# Aula 02: Conceitos de Integração e Entrega Contínua de Software

**Professor:** Prof. Me. Deivison S. Takatu  
**Instituição:** FATEC (Faculdade de Tecnologia)  

---

## 1. O Problema da Entrega Tradicional de Software
Antes da consolidação da cultura DevOps, as equipes de **Desenvolvimento (Dev)** e **Infraestrutura/Operações (Ops)** trabalhavam de forma isolada (silos)[cite: 2]. Esse modelo tradicional apresentava gargalos constantes:
* **Entregas demoradas e deploys manuais:** Processos manuais são propensos a erros humanos e lentos[cite: 2].
* **Síndrome do "na minha máquina funciona":** Diferenças entre o ambiente do desenvolvedor e o servidor de produção geravam falhas e indisponibilidade constantes[cite: 2].
* **Falta de comunicação:** Conflitos entre quem cria as funcionalidades e quem precisa manter o sistema no ar[cite: 2].

> **A Solução DevOps:** Unir Dev e Ops por meio de automação e colaboração contínua, tornando a entrega de software rápida, confiável e previsível[cite: 2].

---

## 2. O Ciclo Infinito do DevOps (Loop Devops)
O DevOps funciona como um ciclo contínuo composto por 8 etapas principais interligadas[cite: 2]:

1. **PLAN (Planejamento):** Definição do que será feito usando metodologias ágeis[cite: 2].  
   * *Ferramentas:* Jira, Trello, Azure Boards[cite: 2].
2. **CODE (Codificação):** Escrita, revisão e versionamento do código-fonte[cite: 2].  
   * *Práticas:* Código limpo, uso de IDEs, documentação e manter testes[cite: 2].
3. **BUILD (Compilação):** Transformação automática do código em artefatos executáveis (ex: arquivos JAR, imagens Docker ou pacotes NPM)[cite: 2]. Inclui compilação, resolução de dependências e análise estática (ex: SonarQube)[cite: 2].
4. **TEST (Testes Automatizados):** Validação constante do sistema a cada alteração, garantindo que novos códigos não quebrem funcionalidades antigas (evita regressões)[cite: 2].
5. **RELEASE (Liberação):** Aprovação e empacotamento do software com a aplicação do Versionamento Semântico para indicar a nova versão pronta para a publicação[cite: 2].
6. **DEPLOY (Implantação):** Publicação automatizada nos ambientes operacionais, minimizando tempos de inatividade e riscos[cite: 2].
7. **OPERATE (Operação):** Gestão da infraestrutura em produção de forma estável e escalável (ex: Infraestrutura como Código, balanceadores de carga)[cite: 2].
8. **MONITOR (Monitoramento e Observabilidade):** Coleta de dados em tempo real para alimentar novos ciclos de planejamento[cite: 2]:
   * **Métricas:** Dados numéricos do sistema (CPU, consumo de memória, requisições/segundo)[cite: 2].
   * **Logs:** Histórico textual de eventos e erros[cite: 2].
   * **Traces:** Rastreamento do caminho percorrido por uma requisição em arquiteturas complexas[cite: 2].

---

## 3. As Três Práticas Fundamentais de CI/CD

| Conceito | Descrição Explicativa | Objetivo Principal |
| :--- | :--- | :--- |
| **Integração Contínua (CI)** | Prática onde desenvolvedores enviam (*commit*) suas alterações frequentemente para um repositório central[cite: 2]. A cada envio, dispara-se um build e testes automatizados[cite: 2]. | Detectar bugs de forma precoce e evitar conflitos grandes de fusão de código[cite: 2]. |
| **Entrega Contínua (Continuous Delivery)** | Automatiza todo o fluxo até a preparação do pacote de software em staging/produção[cite: 2]. O sistema fica **pronto para ser implantado**, mas a decisão de fazer o deploy final depende de uma aprovação/botão manual[cite: 2]. | Reduzir o risco na liberação de releases e garantir estabilidade[cite: 2]. |
| **Deploy Contínuo (Continuous Deployment)** | Vai um passo além da Entrega Contínua[cite: 2]. **Não há intervenção humana**: se a alteração passar em todos os testes do pipeline automatizado, ela vai **diretamente para produção** de forma automática[cite: 2]. | Garantir publicações imediatas e transparentes ao usuário final[cite: 2]. |

---

## 4. Versionamento e Versionamento Semântico (SemVer)

O versionamento é a atribuição de um identificador único a cada estado do código para garantir auditabilidade, histórico e facilitar a recuperação de versões anteriores (*rollback*)[cite: 2].

### Estrutura do Versionamento Semântico: `MAJOR.MINOR.PATCH` (Ex: `2.1.3`)[cite: 2]
* **MAJOR (Ápice - ex: 2.0.0):** Alterações grandes que causam incompatibilidade com versões anteriores (mudanças na API ou arquitetura)[cite: 2].
* **MINOR (Incremento - ex: 1.1.0):** Adição de uma nova funcionalidade mantendo a compatibilidade retroativa[cite: 2].
* **PATCH (Correção - ex: 1.0.1):** Correção de bugs (*Bug Fix*) sem afetar o funcionamento das funcionalidades existentes[cite: 2].

### Tipos Comuns de Alterações no Código
* **Bug Fix:** Correção de falhas[cite: 2].
* **New Feature:** Adição de novas funções[cite: 2].
* **Feature Enhancement:** Melhoria em funções existentes[cite: 2].
* **Refactoring:** Reorganização do código para legibilidade/eficiência sem mudar o comportamento externo[cite: 2].
* **Security Patch:** Ajustes de vulnerabilidades técnicas de segurança[cite: 2].

---

## 5. Git, Tags e Plataformas de Deploy

### O que é o Git?
Criado por Linus Torvalds, é o sistema distribuído de controle de versão usado localmente e sincronizado com plataformas remotas (GitHub, GitLab, Bitbucket)[cite: 2].

### Tags no Git
As **tags** são marcadores específicos fixados no histórico de commits para sinalizar versões estáveis e marcantes do projeto (releases)[cite: 2]:
* **Tag Leve (*Lightweight*):** Aponta diretamente para um commit específico[cite: 2].
* **Tag Anotada (*Annotated*):** Contém metadados detalhados (autor, data, mensagem explicativa da release)[cite: 2].
* **Comandos principais:**
  * `git tag <nome-da-tag>`: Cria a tag no commit atual (ex: `git tag 1.0.0`)[cite: 2].
  * `git push origin <nome-da-tag>`: Envia a tag criada para o repositório remoto no GitHub[cite: 2].

### O que é Deploy e Plataformas Modernas (Vercel)
Deploy é o ato de colocar a aplicação compilada e configurada em um ambiente real acessível aos usuários[cite: 2].
* **Vercel:** Plataforma de hospedagem focada em projetos web[cite: 2]. Possui integração nativa com o GitHub para realizar deploys automáticos a cada alteração efetuada na branch principal (*Continuous Deployment*)[cite: 2].

---

## 6. Atividade Prática Proposta
1. Instalar o **VS Code** e configurar o usuário Git localmente (`git config --global user.name` e `user.email`)[cite: 2].
2. Criar os arquivos iniciais da aplicação (`index.html`, `style.css` e `script.js`)[cite: 2].
3. Inicializar o repositório Git no VS Code e publicar o código em um repositório no GitHub[cite: 2].
4. Fazer modificações no projeto, registrar novos commits e associar a versão a uma nova **Tag** de versionamento[cite: 2].
5. Documentar as etapas em um arquivo e realizar a entrega pela plataforma da disciplina[cite: 2].

---

## 7. Referências Bibliográficas
* HUMBLE, J.; FARLEY, D. *Entrega Contínua: Como Entregar Software de Forma Rápida e Confiável*. Bookman, 2013[cite: 2].
* KIM, G. et al. *Manual de DEVOPS: Como obter agilidade, confiabilidade e segurança em organizações tecnológicas*. Starlin Alta Editora, 2018[cite: 2].
* MORAES, G. *Caixa de Ferramentas DevOps*. Casa do Código, 2015[cite: 2].
* MUNIZ, A. et al. *Jornada Devops*. Brasport, 2019[cite: 2].
* SATO, D. *DevOps na prática: entrega de software confiável e automatizada*. Casa do Código, 2014[cite: 2].
* SILVERMAN, R. E. *Git: guia prático*. Novatec, 2019[cite: 2].