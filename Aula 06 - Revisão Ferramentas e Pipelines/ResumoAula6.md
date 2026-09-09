# Aula 06 — Revisão: Ferramentas e Pipelines

Nesta aula foi feita uma revisão sobre **DevOps, ferramentas e pipelines**, mostrando como a automação pode ser utilizada durante o desenvolvimento e a entrega de software.

Foi apresentado que **DevOps** é uma cultura que integra as equipes de desenvolvimento e operações, buscando melhorar a qualidade, a confiabilidade e a velocidade na entrega dos sistemas.

O ciclo do DevOps foi apresentado como um processo contínuo formado pelas etapas **Plan, Code, Build, Test, Release, Deploy, Operate e Monitor**. No planejamento são definidas as atividades e prioridades. Na codificação ocorre o desenvolvimento e versionamento do código. O Build prepara o sistema e gera os artefatos, enquanto os testes verificam se as alterações funcionam corretamente. Depois, o Release prepara e controla as versões, o Deploy realiza a implantação e o Operate mantém o sistema funcionando. Por fim, o Monitor acompanha a aplicação por meio de métricas, logs e traces.

Também foi explicado o conceito de **pipeline**, que consiste em uma sequência de etapas automatizadas para conduzir o software desde o código até sua implantação. A pipeline pode envolver processos de **build, testes, qualidade, segurança, geração e armazenamento de artefatos, deploy e release**.

Um ponto importante apresentado foi que o software deve ser construído uma única vez e o mesmo artefato deve ser utilizado nos diferentes ambientes, passando de **desenvolvimento para homologação e depois produção**. Caso alguma etapa apresente uma falha, o fluxo deve ser interrompido.

A aula também apresentou o **GitHub Actions**, uma ferramenta integrada ao GitHub que permite criar workflows para automatizar processos de **CI/CD**. Esses workflows podem ser executados automaticamente a partir de eventos como `push`, `pull request`, criação de tags ou releases. Também foi apresentado o **GitHub Actions Marketplace**, que disponibiliza Actions prontas para diferentes etapas das pipelines.

Por fim, foi proposta uma atividade prática para integrar uma pipeline utilizando GitHub Actions, configurando sua execução a partir de um `push` na branch `main`. Também foi solicitado analisar projetos do GitHub que utilizam pipelines, observando suas características, funcionalidades, gatilhos e histórico.
