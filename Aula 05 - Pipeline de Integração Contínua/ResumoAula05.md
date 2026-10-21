# Pipeline de Integração Contínua

## 📚 Resumo da Aula

Nesta aula foi apresentado o conceito de **Pipeline de Integração Contínua** e como ela pode ser utilizada para automatizar várias etapas do desenvolvimento e entrega de um software.

A pipeline é uma sequência de etapas automatizadas que valida o sistema durante o processo de desenvolvimento. Quando uma alteração é enviada para o GitHub, a pipeline pode executar automaticamente o build, testes, verificações de qualidade e segurança, até chegar ao deploy.

Uma regra importante é que **se uma etapa falhar, o processo é interrompido** e as próximas etapas não continuam.

## 🔄 Fluxo da Pipeline

```text
Código
  ↓
Build
  ↓
Testes
  ↓
Qualidade
  ↓
Segurança
  ↓
Package
  ↓
Deploy
  ↓
Release e Monitoramento
```

Também foi apresentado o conceito de **Build uma única vez**, onde o mesmo artefato gerado é promovido entre os ambientes de:

**Desenvolvimento → Homologação → Produção**

## 🛠️ Pipeline de Build

O Build prepara o software para execução ou distribuição.

As principais funções são:
* Compilar o projeto automaticamente;
* Gerar os artefatos;
* Verificar a integridade inicial do código.

Os artefatos podem ser arquivos como:
* `.jar`
* `.war`
* `.apk`
* Containers Docker

## 🧪 Pipeline de Testes

Depois do Build, são executados testes automaticamente.

O objetivo é verificar se as alterações realizadas não quebraram funcionalidades que já existiam no sistema.

A automação dos testes também ajuda a identificar falhas mais rapidamente.

## 📊 Pipeline de Qualidade

A pipeline de qualidade realiza verificações automáticas para identificar problemas no código.

Ela procura principalmente:

* Problemas de qualidade;
* Inconsistências;
* Possíveis falhas;
* Código que não segue os padrões definidos.

A ideia é encontrar esses problemas antes que o sistema avance para as próximas etapas.

## 🔐 Pipeline de Segurança

A pipeline de segurança verifica o sistema em busca de vulnerabilidades e riscos.

Pode realizar verificações como:

* Análise de vulnerabilidades no código;
* Verificação das dependências;
* Identificação de configurações inseguras;
* Detecção de informações sensíveis expostas.

## 📦 Pipeline de Artefatos (Package)

Essa etapa é responsável por empacotar e armazenar os resultados gerados durante o Build.

As principais funções são:

* Empacotar a aplicação;
* Gerar arquivos de distribuição;
* Versionar os artefatos;
* Armazenar os artefatos em repositórios.

## 🚀 Pipeline de Deploy

O Deploy é responsável por publicar o software em um ambiente depois que ele passou pelas validações.

Nessa etapa pode acontecer:

* Preparação do ambiente;
* Publicação do artefato;
* Configuração de variáveis e parâmetros;
* Execução automática do deploy.

## 📋 Pipeline de Release e Monitoramento

A etapa de Release prepara uma versão específica do software para ser disponibilizada aos usuários ou em produção.

Ela envolve:

* Criação e identificação de versões;
* Publicação das releases;
* Controle das versões disponibilizadas;
* Monitoramento da aplicação em produção.

## ⚙️ GitHub Actions

O **GitHub Actions** é uma ferramenta integrada ao GitHub que permite criar e executar workflows automatizados.

Esses workflows podem ser iniciados através de eventos do repositório, como:

* `push`
* Pull Request
* Criação de Tags
* Criação de Releases

Com isso, é possível automatizar processos de **integração contínua, testes e deploy**.

### Exemplo

```yaml
on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
```

Nesse exemplo, a pipeline é iniciada quando ocorre um `push` no repositório.

## 🛒 GitHub Actions Marketplace

O GitHub Marketplace possui várias Actions prontas que podem ser utilizadas nos workflows.

Elas podem ajudar em diferentes etapas da pipeline, como:

* Build;
* Testes;
* Qualidade;
* Segurança;
* Deploy;
* Cache.

As Actions podem ser desenvolvidas pelo GitHub, por parceiros ou pela comunidade.

## 🔧 DevOps

O **DevOps** integra desenvolvimento, testes e operações através da automação.

As pipelines são importantes porque ajudam a automatizar as validações durante o ciclo de entrega do software, aumentando a qualidade e a estabilidade e reduzindo falhas.

De forma resumida, a pipeline conduz o software desde o **commit até o deploy** de maneira automatizada.

## 📝 Atividade da Aula

A atividade proposta foi escolher **3 Actions disponíveis no GitHub Marketplace** e desenvolver um projeto utilizando essas ferramentas em uma pipeline automatizada.

Cada Action deve ser aplicada em uma etapa adequada do processo.

Também é necessário documentar:

* Quais Actions foram utilizadas;
* Qual a função de cada uma;
* Em qual etapa da pipeline foram utilizadas;
* Como contribuíram para a automação do projeto.

