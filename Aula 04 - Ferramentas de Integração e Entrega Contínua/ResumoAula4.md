# Comparação entre as Plataformas de CI/CD: Azure DevOps e GitHub

---

## Introdução

Esta pesquisa tem como viés analisar e aprofundar os pontos levantados no estudo "Comparação prática entre as plataformas de CI/CD Azure DevOps e GitHub", por Vladislav Manolov, Daniela Gotseva e Nikolay Hinov no ano de 2025, do Departamento de Sistemas de Computação da Faculdade de Sistemas e Tecnologias de Computação da Universidade Técnica de Sófia.

Com este artigo, foi possível identificar as ferramentas frequentemente utilizadas em CI/CD, realizando uma análise comparativa de suas características, qualidades, limitações e cenários de aplicação. Baseado nisso, este arquivo centraliza as informações como forma de atividade avaliativa da matéria de Integração Contínua (CI) e Entrega/Implantação.

---

## 1. Mapeamento Global de CI/CD

Com base nos dados de adoção apresentados no estudo, o mercado global de plataformas de automação está distribuído da seguinte forma:

* **GitHub:** Líder absoluto de mercado com **33%** de participação, impulsionado por sua forte presença na comunidade de código aberto e pela facilidade de uso do GitHub Actions.
* **Azure DevOps:** Ocupa a segunda posição com **24%** do mercado, sendo a principal escolha para ambientes corporativos integrados.
* **Jenkins:** Mantém **14%** de participação, continuando muito relevante devido ao seu ecossistema clássico de código aberto.
* **GitLab CI/CD:** Representa **9%** do mercado, atraindo equipes que buscam uma solução tudo-em-um para versionamento e entrega.
* **Outras Ferramentas (20% somadas):** Soluções especializadas como Atlassian Bitbucket, JetBrains TeamCity, AWS CodePipeline, TravisCI e CircleCI.

---

## 2. Análise das Ferramentas

### A. GitHub (GitHub Actions)
* **Características:** Plataforma focada no versionamento Git e colaboração distribuída. A automação de CI/CD é realizada de forma nativa pelo GitHub Actions, que utiliza arquivos de configuração YAML no próprio repositório sob um modelo baseado em eventos (como *push* ou *pull requests*).
* **Vantagens:**
  * Interface moderna e altamente intuitiva, reduzindo o tempo de treinamento.
  * GitHub Marketplace com milhares de integrações e ações reutilizáveis da comunidade.
  * Segurança proativa com varredura nativa de dependências (*Dependabot*) e detecção de vazamento de segredos (*Secret Scanning*).
* **Limitações:**
  * Ausência de ferramentas nativas para planos de testes formais ou manuais.
  * Perda de desempenho ao lidar com repositórios legados de grande porte.
  * Necessidade de planos corporativos mais caros (Enterprise) para desbloquear regras avançadas de governança.
* **Indicação:** Recomendado para startups, projetos nativos em nuvem, práticas de GitOps e desenvolvimento open-source.

---

### B. Azure DevOps (Azure Pipelines)
* **Características:** Suíte corporativa integrada para o Gerenciamento do Ciclo de Vida da Aplicação (ALM). Engloba planejamento ágil (*Azure Boards*), controle de versão (*Azure Repos*), pipelines de entrega (*Azure Pipelines*), planos de testes (*Azure Test Plans*) e repositório de pacotes (*Azure Artifacts*). Suporta tanto o Git quanto o versionamento legado TFVC.
* **Vantagens:**
  * Robustez e alta escalabilidade para arquiteturas monolíticas e compilações simultâneas.
  * Gestão nativa e completa para testes manuais e automatizados via Azure Test Plans.
  * Alto nível de governança e segurança com integração ao Azure Active Directory (RBAC) e conformidade com normas regulatórias (ISO 27001, SOC 2, HIPAA, GDPR).
  * Modelo financeiro flexível baseado no consumo de serviços e agentes.
* **Limitações:**
  * Curva de aprendizado íngreme e interface complexa.
  * Pouco otimizado para cenários fora do ambiente corporativo privado ou colaboração pública open-source.
* **Indicação:** Indispensável para grandes corporações, setores regulados (saúde, finanças, defesa) e infraestruturas híbridas.

---

### C. Jenkins
* **Características:** Servidor de automação clássico, gratuito e open-source.
* **Vantagens:** Flexibilidade quase ilimitada com milhares de plugins para integração com tecnologias modernas e legadas.
* **Limitações:** Requer manutenção constante, atualizações manuais de segurança e infraestrutura própria.
* **Indicação:** Ambientes locais (*on-premises*) com demandas customizadas e equipe técnica dedicada.

---

### D. GitLab CI/CD
* **Características:** Plataforma unificada projetada como uma solução completa para todo o ciclo de vida do desenvolvimento.
* **Vantagens:** Evita a fragmentação de ferramentas, centralizando planejamento, build, segurança e deploy em uma única interface.
* **Limitações:** Pode se mostrar excessivamente complexo e pesado para projetos simples.
* **Indicação:** Organizações que buscam eliminar a manutenção de ferramentas de múltiplos fornecedores.

---

### E. Atlassian Bitbucket
* **Características:** Serviço de repositórios Git corporativos da Atlassian com o Bitbucket Pipelines integrado.
* **Vantagens:** Integração perfeita com Jira e Confluence.
* **Limitações:** Menos robusto em termos de escalabilidade de pipelines de CI/CD puro.
* **Indicação:** Equipes cujo fluxo de trabalho esteja centralizado no ecossistema Atlassian.

---

### F. JetBrains TeamCity
* **Características:** Servidor comercial focado na eficiência de compilação e qualidade de entrega.
* **Vantagens:** Visualização detalhada do histórico de builds e detecção inteligente de falhas em testes.
* **Limitações:** Custo de licenciamento elevado conforme o volume de builds cresce.
* **Indicação:** Projetos com compilações complexas que exigem alta estabilidade de build e suporte comercial.

---

## 3. Comparativo

| Critério | Azure DevOps | GitHub Actions | Jenkins | GitLab CI/CD |
| :--- | :--- | :--- | :--- | :--- |
| **Público-Alvo** | Grandes Corporações e Setores Regulados | Startups, Desenvolvedores e Times Ágeis | Organizações com Infraestrutura Local | Equipes focadas em Plataforma Única |
| **Versionamento** | Git e TFVC (Legado Centralizado) | Apenas Git (Distribuído) | Compatível com múltiplos (via plugins) | Focado em Git |
| **Gestão de Testes** | Nativa e estruturada (Azure Test Plans) | Depende de ferramentas de terceiros | Via integrações manuais e plugins | Integrações nativas e de terceiros |
| **Segurança** | Baseada em conformidade, AD e isolamento | Segurança ágil (Dependabot, Secret Scanning) | Configuração manual do administrador | Foco em DevSecOps integrado |
| **Modelo de Custos** | Modular por serviço e consumo de agentes | Planos fechados por usuário (SaaS) | Gratuito (Custo oculto na manutenção/infra) | Assinaturas com recursos crescentes |
| **Curva de Aprendizado** | Alta (interface complexa e detalhada) | Baixa (intuitivo para desenvolvedores) | Muito alta (exige competência técnica) | Média |

---

## 4. Conclusão

1. **Adota-se o Azure DevOps** quando a organização necessita de elevada governança corporativa, conformidade rígida de dados (como HIPAA e GDPR), opere com sistemas monolíticos pesados ou utilize infraestrutura de nuvem híbrida com agentes privados.
2. **Adota-se o GitHub** quando o foco da equipe for agilidade de implantação, facilidade de *onboarding*, segurança ágil integrada de código e alinhamento com práticas nativas em nuvem ou GitOps.
