# Aula 03: Gerência de Configuração de Software

**Professor:** Prof. Me. Deivison S. Takatu  
**Instituição:** FATEC (Faculdade de Tecnologia)  

---

## 1. O Problema da Gerência de Configuração
Quando múltiplos desenvolvedores trabalham no mesmo projeto, surgem divergências operacionais clássicas[cite: 3]:
* **Diversidade de Ambientes:** Cada máquina possui versões distintas do sistema operacional, interpretadores/compiladores (ex: Node.js 20 em Dev vs. Node.js 18 em Produção)[cite: 3].
* **Conflito de Dependências:** Bibliotecas em versões diferentes geram comportamentos inconsistentes[cite: 3].
* **Incompatibilidade de Parâmetros:** Variáveis de ambiente, portas de acesso e instâncias de banco de dados desalinhadas[cite: 3].
* **O Dilema "Na minha máquina funciona":** O software roda perfeitamente no ambiente do desenvolvedor, mas falha gravemente ao ser implantado no servidor de produção[cite: 3].

> **O Desafio da Gerência de Configuração:** Garantir a padronização e o rastreamento rigoroso de todos os componentes necessários para que a aplicação execute identicamente em qualquer ambiente[cite: 3].

---

## 2. O que é Configuração e Itens de Configuração?

### Definição
Configuração é o conjunto completo de dados, parâmetros e arquivos que determinam como um sistema deve ser construído, executado e mantido[cite: 3].

### Principais Itens de Configuração (Artifacts)
Para manter o projeto auditável e reproduzível, os seguintes itens devem ser mapeados e versionados[cite: 3]:

| Categoria | Descrição / Exemplo | Arquivos Típicos |
| :--- | :--- | :--- |
| **Código-Fonte** | Lógica de programação principal desenvolvida pela equipe[cite: 3]. | `.js`, `.jsx`, `.java`, `.py`[cite: 3] |
| **Dependências** | Mapeamento explícito de bibliotecas externas e suas versões exatas[cite: 3]. | `package.json`, `package-lock.json`, `pom.xml`[cite: 3] |
| **Configurações de Ambiente** | Parâmetros de runtime, URLs de API, credenciais e chaves[cite: 3]. | `.env`, arquivos `YAML` ou `JSON`[cite: 3] |
| **Banco de Dados** | Estrutura de dados, esquemas e scripts de migração[cite: 3]. | Scripts `.sql`, migrações[cite: 3] |
| **Infraestrutura** | Definição de containers e provisionamento de servidores como código (IaC)[cite: 3]. | `Dockerfile`, `docker-compose.yml`, `Terraform`[cite: 3] |
| **Documentação & Scripts** | Orientações de execução e tarefas automatizadas[cite: 3]. | `README.md`, scripts de build/test/deploy[cite: 3] |

---

## 3. Ambiente de Execução: Node.js e NPM

### O que é Node.js?
O Node.js é um ambiente de execução (*runtime*) que permite rodar código JavaScript no lado do servidor (backend)[cite: 3]. 
* Permite utilizar **JavaScript tanto no frontend quanto no backend**, unificando a linguagem de desenvolvimento[cite: 3].
* Atua como um serviço eficiente para processar requisições e construir APIs[cite: 3].

### O que é NPM (Node Package Manager)?
Gerenciador de pacotes oficial instalado juntamente com o Node.js[cite: 3].
* **Função:** Automatiza a instalação, atualização e remoção de bibliotecas externas, eliminando downloads manuais[cite: 3].
* **`package.json`:** Arquivo central que registra os nomes e as versões das dependências do projeto[cite: 3]. Permite que qualquer membro da equipe instale todas as dependências do projeto executando apenas o comando `npm install`[cite: 3].
* **`package-lock.json`:** Garante a rastreabilidade exata da árvore de dependências (sub-dependências), assegurando que o build seja idêntico em todas as máquinas.
* **`.gitignore`:** Especifica quais arquivos e diretórios pesados ou sensíveis (como `node_modules/` ou senhas no `.env`) **não** devem subir para o repositório Git[cite: 3].

---

## 4. Ecossistema React e Estrutura de Projetos

### Criando uma Aplicação com `create-react-app`
O comando `npx create-react-app <nome-do-projeto>` gera uma estrutura padronizada e pronta para produção[cite: 3]:
* **`npx`:** Executador de pacotes da biblioteca do NPM sem necessidade de instalá-lo globalmente[cite: 3].
* **Configurações Embutidas:** Webpack (sistema de empacotamento/build), Babel (transpilação de JavaScript moderno para compatibilidade de navegadores) e servidor local de desenvolvimento[cite: 3].

### Comandos de Fluxo de Trabalho:
1. `npx create-react-app meu-projeto`: Cria a estrutura completa[cite: 3].
2. `cd meu-projeto`: Navega para a pasta criada[cite: 3].
3. `code .`: Abre a pasta no VS Code[cite: 3].
4. `npm start`: Inicializa o servidor local em `http://localhost:3000`[cite: 3].

### Estrutura Principal de Pastas do React:
* **`node_modules/`:** Armazena fisicamente o código de todas as dependências baixadas via NPM[cite: 3].
* **`public/`:** Contém o arquivo `index.html` estático, favicon, manifestos e assets globais[cite: 3].
* **`src/`:** Código-fonte principal da aplicação[cite: 3]:
  * `index.js`: Ponto de entrada que injeta e renderiza a aplicação React no DOM do navegador[cite: 3].
  * `App.js`: Componente raiz (estrutura central da interface)[cite: 3].
  * `App.css` / `index.css`: Estilizações específicas e globais[cite: 3].

---

## 5. Reutilização de Código: Busca de Templates
Para acelerar o ciclo de desenvolvimento, desenvolvedores costumam utilizar modelos *open-source* reutilizáveis fornecidos pela comunidade[cite: 3].

* **GitHub:** Busca por repositórios base para clonar via `git clone <url>`[cite: 3].
* **Vercel Templates:** Modelos pré-configurados com frameworks modernos prontos para deploy instantâneo[cite: 3].
* **CodeSandbox:** Ambiente de desenvolvimento na nuvem para buscar, testar e exportar projetos/templates interativos sem necessidade de instalação local[cite: 3].

---

## 6. Atividade Prática Proposta
1. Pesquisar e selecionar um template de projeto desenvolvido em **React** (via GitHub ou CodeSandbox)[cite: 3].
2. Importar o projeto localmente, realizar customizações/alterações no código e versionar as alterações em um repositório no **GitHub**[cite: 3].
3. Realizar o **deploy** da aplicação customizada na plataforma **Vercel**[cite: 3].
4. Documentar todas as etapas em um relatório (descrições técnicas, screenshots da aplicação e links públicos do GitHub e da Vercel)[cite: 3].

---

## 7. Referências Bibliográficas
* ARUNDEL, J.; DOMINGUS, J. *DevOps nativo de nuvem com Kubernetes*. Novatec, 2019[cite: 3].
* BANKS, A.; PORCELLO, E. *Learning React*. O'Reilly Media, 2017[cite: 3].
* HUMBLE, J.; PRIKLANDNICKI, R. *Entrega Contínua: Como Entregar Software de Forma Rápida e Confiável*. Bookman, 2013[cite: 3].
* KIM, G. et al. *Manual de DEVOPS*. Starlin Alta Editora, 2018[cite: 3].
* MORAES, G. *Caixa de Ferramentas DevOps*. Casa do Código, 2015[cite: 3].
* MUNIZ, A. et al. *Jornada Devops*. Brasport, 2019[cite: 3].
* SATO, D. *DevOps na prática*. Casa do Código, 2014[cite: 3].
* SILVA, R. *Entrega contínua em Android*. Casa do Código, 2016[cite: 3].
* SILVERMAN, R. E. *Git: guia prático*. Novatec, 2019[cite: 3].
* VITALINO, J. F. N.; CASTRO, M. A. N. *Descomplicando o Docker*. Brasport, 2018[cite: 3].