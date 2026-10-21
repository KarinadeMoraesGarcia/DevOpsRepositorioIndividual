# Resumo – Aula 09: Documentação de Software

Resumo da aula do Prof. Me. Deivison S. Takatu (Fatec), abordando o que é documentação de software, sua importância em projetos DevOps, os tipos de documentação, como estruturar um README no GitHub e a atividade proposta.

Aluna: Nicolly Lemos da Silva e Karina de Moraes Garcia 
Projeto documentado: Sistema de Agendamento Online Repositório: https://github.com/nicollylemos/Agendamento

---

## 1. Introdução

### Documentação de projetos DevOps
Pergunta-guia da aula: *"Se eu entrar hoje no GitHub do seu projeto, consigo entender e executar o projeto sem perguntar nada para vocês?"*

A documentação deve **reduzir a dependência de explicações informais** e permitir que outra pessoa compreenda o projeto.
Repositório de exemplo: https://github.com/deivisontakatu/aula-documentacao-software

### O que acontece sem documentação
- Dependência de desenvolvedores específicos
- Dificuldade para novos integrantes entrarem no projeto
- Configurações esquecidas ou executadas de forma diferente
- Maior tempo para manutenção e resolução de problemas
- Conhecimento perdido quando uma pessoa deixa a equipe
- Perguntas repetitivas sobre instalação, execução e deploy

---

## 2. Definição de Documentação de Software

Conjunto de informações que ajuda pessoas a **compreender, utilizar, desenvolver, testar e manter** um sistema.

Uma boa documentação responde:
- O que é o projeto? Para que ele serve?
- Como instalar e configurar?
- Como executar e testar?
- Como contribuir e realizar mudanças?

### Por que documentar

| Necessidade | Descrição |
|---|---|
| Comunicação | Compartilhar conhecimento entre pessoas |
| Manutenção | Facilitar correções e evolução |
| Colaboração | Permitir trabalho conjunto |
| Continuidade | Reduzir a dependência de indivíduos |

> Documentar não é apenas registrar, é tornar o conhecimento **reutilizável**.

### Exemplos de projetos bem documentados
- https://github.com/react/react
- https://github.com/nodejs/node
- https://github.com/docker/docs
- https://github.com/bitcoin/bitcoin
- https://github.com/github/brasil

---

## 3. Documentação e DevOps

DevOps integra **pessoas, processos e tecnologia** para entregar software de forma contínua. A documentação contribui ao registrar:
- como o código é desenvolvido;
- como mudanças são validadas;
- como a pipeline funciona;
- como o sistema é implantado.

### Quem utiliza a documentação

| Papel | Uso da documentação |
|---|---|
| Dev | Inicia o trabalho com menor dependência da equipe |
| Tester | Identifica como executar e validar os testes |
| DevOps | Configura pipeline, ambientes e deploy |
| Gestor | Acompanha processos e decisões |
| Usuário | Aprende a utilizar o produto |

---

## 4. Combinação de Áreas

A documentação reúne informações de várias áreas:

| Área | Conteúdo documentado |
|---|---|
| Engenharia de Software (ES) | Requisitos, arquitetura, código e testes |
| Gestão de Projetos (GP) | Escopo, cronograma, riscos e entregas |
| DevOps | CI/CD, infraestrutura, deploy e monitoramento |
| Segurança da Informação | Vulnerabilidades, políticas, acessos e incidentes |
| Qualidade de Software (QA) | Testes, critérios de aceitação, evidências e qualidade |
| Produto / UX | Requisitos do usuário, jornadas, regras de negócio e usabilidade |

---

## 5. Tipos de Documentação

| Tipo | O que descreve |
|---|---|
| Técnica | Arquitetura, APIs, banco, componentes e configurações |
| De projeto | Objetivos, requisitos, decisões e organização |
| De processo | Branches, commits, Pull Requests, testes, pipeline e deploy |

---

## 6. GitHub – README

O README normalmente é o **primeiro documento consultado** em um repositório. Deve permitir entender rapidamente: propósito do projeto, principais tecnologias, pré-requisitos, instalação e execução, testes, contribuição e links importantes.

### 6.1 Tecnologias e pré-requisitos
- Informar a **stack** necessária para executar o projeto.
- Exemplos: linguagem e versão, framework, banco de dados, gerenciador de pacotes, Docker (quando utilizado), Git e outras ferramentas.
- Indicar **versões mínimas ou recomendadas** quando isso fizer diferença.

### 6.2 Instalação e execução
A documentação deve transformar o processo em uma **sequência reproduzível**. Fluxo de exemplo:
1. Clonar o repositório
2. Acessar a pasta
3. Instalar dependências
4. Configurar variáveis
5. Executar o projeto
6. Acessar a aplicação
7. Executar os testes

### 6.3 Configuração e variáveis
Explicar as configurações necessárias **sem expor informações sensíveis**: quais variáveis existem, para que servem, quais são obrigatórias, como criar o arquivo de configuração e quais valores podem servir de exemplo.

```env
PORT=3000
DATABASE_URL=sua_url_aqui
API_KEY=sua_chave_aqui
```

### 6.4 Execução e testes
Mostrar como verificar se o projeto está funcionando, com comandos para: iniciar a aplicação, executar testes unitários, de integração e de performance (quando houver), e verificar resultados e falhas.

### 6.5 Estrutura do projeto
- Apresentar a organização das principais pastas e arquivos. Exemplo: `src/` (aplicação), `tests/` (testes), `docs/` (documentação) e `.github/workflows/` (pipelines).
- Explicar a responsabilidade das partes relevantes.
- **Evitar** documentar cada arquivo se isso não ajudar o leitor a compreender ou operar o sistema.

---

## 7. Documentação do Processo DevOps

| Etapa | O que documentar |
|---|---|
| Desenvolvimento | Implementação de funcionalidades e correções no código |
| Git | Controle de versão e histórico das alterações |
| Pull Request | Solicitação de revisão e integração das mudanças |
| Build | Compilação ou preparação do software para execução |
| Testes | Validação do funcionamento e identificação de falhas |
| Pipeline CI/CD | Automação das etapas de integração, validação e entrega |
| Deploy | Publicação da aplicação em um ambiente de execução |

### Tecnologias utilizadas
- **Stack:** linguagens, frameworks, bancos de dados e ferramentas.
- **Versões e ferramentas:** registro das versões para facilitar a compatibilidade e a reprodução do ambiente.
- **Pré-requisitos:** runtimes, gerenciadores de pacotes, banco de dados, Git e Docker, quando aplicável.

### Instalação e execução
- **Dependências e configuração inicial:** instalar pacotes, configurar variáveis de ambiente e preparar serviços externos (ex.: bancos de dados).
- **Como iniciar a aplicação:** sequência de comandos para executar o projeto e acessá-lo.
- **Validação do ambiente:** orientações para identificar erros comuns e confirmar que a aplicação funciona corretamente.

---

## 8. O que NÃO colocar na documentação

| Item | Por quê |
|---|---|
| Senhas e credenciais | Nunca registrar senhas de usuários, administradores ou bancos de dados |
| Chaves de API e tokens | Não expor credenciais que permitam acessar serviços, sistemas ou recursos privados |
| Dados sensíveis | Evitar informações pessoais, dados confidenciais de clientes e informações internas restritas |
| Arquivos de configuração sigilosos | Não publicar arquivos `.env` ou configurações que contenham segredos |
| Informações de infraestrutura restritas | Não divulgar detalhes que facilitem acessos indevidos ou comprometam a segurança |

---

## 9. Atividade

1. **Escolher um projeto de software** e elaborar sua documentação, apresentando:
   - objetivo e problema que pretende resolver;
   - escopo;
   - principais requisitos funcionais e não funcionais;
   - tecnologias utilizadas, arquitetura da aplicação e organização dos principais componentes.
2. **Criar ou atualizar o `README.md`** do repositório no GitHub, incluindo pré-requisitos, instruções de instalação, configuração e execução do projeto.
3. **Quando aplicável**, documentar também as APIs, o banco de dados, as variáveis de ambiente e os procedimentos de testes e deploy.

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